---
title: Microsoft Intune-Azure 'da SCEP ile üçüncü taraf sertifika yetkilileri (CA) kullanma | Microsoft Docs
description: Microsoft Intune, SCEP protokolünü kullanarak mobil cihazlara sertifika vermek için bir satıcı veya üçüncü taraf sertifika yetkilisi (CA) ekleyebilirsiniz. Bu genel bakışta, bir Azure Active Directory (Azure AD) uygulaması Microsoft Intune'a sertifikaları doğrulamak için izinler verir. Ardından, sertifikaları vermek için SCEP sunucunuzun kurulumunda AAD uygulamasının uygulama kimliğini, kimlik doğrulama anahtarını ve kiracı kimliğini kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3f9b78685e2bbe40a91c80fe71403123dbfaac90
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729845"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>SCEP kullanarak Intune'da iş ortağı sertifika yetkilisi ekleme

Intune ile üçüncü taraf sertifika yetkilileri (CA) kullanın. Üçüncü taraf CA 'Lar, Basit Sertifika Kayıt Protokolü (SCEP) kullanarak yeni veya yenilenen sertifikalarla mobil aygıtlar sağlayabilir ve Windows, iOS, Android ve macOS cihazlarını destekleyebilir.

Bu özelliğin kullanımı iki bölümden oluşur: açık kaynak API'si ve Intune yönetici görevleri.

**1. Bölüm - Açık kaynak API'sini kullanma**  
Microsoft, Intune ile tümleşecek bir API oluşturdu. API, sertifikaları doğrulayabilir, başarı veya başarısızlık bildirimleri gönderebilir ve Intune ile iletişim kurmak için SSL (özellikle SSL soket fabrikası) kullanabilirsiniz.

API'yi [Intune SCEP API genel GitHub deposundan](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) indirebilir ve çözümlerinizde kullanabilirsiniz. SCEP bir cihaza sertifika sağlamadan önce Intune 'da özel sınama doğrulaması çalıştırmak için bu API 'YI üçüncü taraf SCEP sunucularıyla birlikte kullanın.

[Intune SCEP yönetim çözümüyle tümleştirme](scep-libraries-apis.md) başlığı altında API'nin kullanımı, yöntemleri ve derlediğiniz çözümün testi hakkında daha fazla ayrıntı sağlanır.

**2. Bölüm - Uygulamayı ve profili oluşturma**  
Azure Active Directory (Azure AD) uygulamasını kullanarak, cihazlardan gelen SCEP isteklerini işlemesi için Intune'a temsilci hakları verebilirsiniz. Azure AD uygulaması, geliştiricinin oluşturduğu API çözümü içinde kullanılan uygulama kimliğini ve kimlik doğrulama anahtarını içerir. Daha sonra Yöneticiler, Intune kullanarak SCEP sertifikaları profilleri oluşturup dağıtır ve cihazlarda dağıtım durumundaki raporları görüntüleyebilir.

Bu makalede Azure AD uygulaması oluşturma da dahil olmak üzere Yönetici perspektifinden bu özelliğe bir genel bakış sağlanır.

## <a name="overview"></a>İlke

Aşağıdaki adımlarda, Intune 'da sertifikalar için SCEP kullanılmasına genel bir bakış sağlanmaktadır:

1. Intune'da, yönetici SCEP sertifika profilini oluşturur ve ardından profille kullanıcıları veya cihazları hedefler.
2. Cihaz Intune'a iade edilir.
3. Intune benzersiz bir SCEP sınaması oluşturur. Ayrıca, beklenen konunun ve SAN'ın ne olması gerektiği gibi başka veri bütünlüğü denetimi bilgileri de ekler.
4. Intune hem sınama hem de veri bütünlüğü denetimi bilgilerini şifreler, imzalar ve sonra bu bilgileri SCEP isteğiyle birlikte cihaza gönderir.
5. Cihaz, Intune'dan gönderilen SCEP sertifika profili temelinde bir sertifika imzalama isteği (CSR) ve ortak/özel anahtar çifti oluşturur.
6. CSR ve şifrelenmiş/imzalanmış sınama üçüncü taraf SCEP sunucu uç noktasına gönderilir.
7. SCEP sunucusu CSR'yi ve sınamayı Intune'a gönderir. Ardından Intune imzayı doğrular, yükün şifresini çözer ve CSR'yi veri bütünlüğü denetimi bilgileriyle karşılaştırır.
8. Intune geriye SCEP sunucusuna bir yanıt gönderir ve sınama doğrulamasının başarılı olup olmadığını belirtir.  
9. Sınama başarıyla doğrulanırsa, SCEP sunucusu sertifikayı cihaza verir.

Aşağıdaki diyagramda Intune'la üçüncü taraf SCEP tümleştirmesinin ayrıntılı akışı gösterilir:

![Üçüncü taraf sertifika yetkilisi SCEP Microsoft Intune ile nasıl tümleştirilir?](./media/certificate-authority-add-scep-overview/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Üçüncü taraf CA tümleştirmesini ayarlama

### <a name="validate-third-party-certification-authority"></a>Üçüncü taraf sertifika yetkilisini doğrulama

Üçüncü taraf sertifika yetkililerini Intune ile tümleştirmeden önce, kullandığınız CA'nın Intune'u desteklediğini onaylayın. [Üçüncü taraf CA iş ortakları](#third-party-certification-authority-partners) (bu makalede) bir liste içerir. Daha fazla bilgi için sertifika yetkilinizin kılavuzunu da gözden geçirebilirsiniz. CA, bunları uygulamaya özgü kurulum yönergeleri de içerebilir.

### <a name="authorize-communication-between-ca-and-intune"></a>CA ile Intune arasındaki iletişimi yetkilendirme

Üçüncü taraf SCEP sunucusunun özel sınama doğrulaması çalıştırmasına izin vermek için, Azure AD'de bir uygulama oluşturun. Bu uygulama Intune'a SCEP isteklerini doğrulaması için temsilci hakları verir.

Azure AD uygulamasını kaydetmek için gerekli izinlere sahip olduğunuzdan emin olun. Azure AD belgelerinde [gerekli izinlere](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions)bakın.

#### <a name="create-an-application-in-azure-active-directory"></a>Azure Active Directory bir uygulama oluşturma  

1. [Azure Portal](https://portal.azure.com), **Azure Active Directory** > **uygulama kaydı**' na gidin ve ardından **Yeni kayıt**' ı seçin.  

2. **Uygulama kaydetme** sayfasında, aşağıdaki ayrıntıları belirtin:  
   - **Ad** bölümünde anlamlı bir uygulama adı girin.  
   - **Desteklenen hesap türleri** bölümü için **herhangi bir kuruluş dizininde hesaplar**' ı seçin.  
   - **Yeniden yönlendirme URI 'si**için, varsayılan Web 'i bırakın ve ardından üçüncü taraf SCEP sunucusu için oturum açma URL 'sini belirtin.  

3. Uygulamayı oluşturmak için **Kaydet** ' i seçin ve yeni uygulama Için genel bakış sayfasını açın.  

4. Uygulamaya **genel bakış** sayfasında, **uygulama (istemci) kimlik** değerini kopyalayın ve daha sonra kullanmak üzere kaydedin. Bu değere daha sonra ihtiyacınız olacak.  

5. Uygulamanın gezinti bölmesinde, **Yönet**' ın altındaki **Sertifikalar & gizlilikler** ' a gidin. **Yeni istemci parolası** düğmesini seçin. Açıklama ' ya bir değer girin, **süre sonu**için herhangi bir seçenek belirleyin ve ardından **Ekle** ' yi seçerek istemci parolası için bir *değer* oluşturun. 
   > [!IMPORTANT]  
   > Bu sayfadan ayrılmadan önce, istemci sırrı için değeri kopyalayın ve daha sonra üçüncü taraf CA uygulamanız ile kullanmak üzere kaydedin. Bu değer bir daha gösterilmez. Üçüncü taraf sertifika yetkilinizin kılavuzunu, uygulama KIMLIĞI, kimlik doğrulama anahtarı ve kiracı KIMLIĞI 'nin nasıl yapılandırılacağını istediğlerine göre gözden geçirdiğinizden emin olun.  

6. **KIRACı kimliğinizi**kaydedin. Kiracı KIMLIĞI, hesabınızdaki @ işaretinden sonra gelen etki alanı metindir. Örneğin, hesabınız *admin@name.onmicrosoft.com* ise, kiracı kimliğiniz **Name.onmicrosoft.com**olur.  

7. Uygulamanın gezinti bölmesinde, **Yönet**' ın altındaki **API izinleri** ' ne gidin ve **izin Ekle**' yi seçin.  

8. **API Izinleri iste** sayfasında, **Intune**' u seçin ve ardından **Uygulama izinleri**' ni seçin. **Scep_challenge_provider** (SCEP sınama doğrulaması) onay kutusunu seçin.  

   Bu yapılandırmayı kaydetmek için **Izin Ekle** ' yi seçin.  

9. **API izinleri** sayfasında kalır ve **Microsoft Için yönetici onayı ver**' i seçin ve ardından **Evet**' i seçin.  
   
   Azure AD 'de uygulama kayıt işlemi tamamlanmıştır.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>SCEP sertifika profilini yapılandırma ve dağıtma
Yönetici olarak, kullanıcıları veya cihazları hedefleyecek bir SCEP sertifika profili oluşturun. Sonra, profili atayın.

- [SCEP sertifika profili oluşturma](certificates-profile-scep.md#create-a-scep-certificate-profile)

- [Sertifika profilini atama](certificates-profile-scep.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Sertifikaları kaldırma

Cihazın kaydını kaldırdığınızda veya cihazı temizlediğinizde, sertifikalar kaldırılır. Sertifikalar iptal edilmez.

## <a name="third-party-certification-authority-partners"></a>Üçüncü taraf kök sertifika yetkilisi iş ortakları
Aşağıdaki üçüncü taraf sertifika yetkilileri Intune'u destekler:

- [Entrust Datacard](https://info.entrustdatacard.com/pki-eval-tool)
- [EJBCA GitHub açık kaynak sürümü](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [Idnomıc](https://www.idnomic.com/)
- [Sectıgo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)
- [SCEPman](https://azuremarketplace.microsoft.com/marketplace/apps/gluckkanja.scepman)

Ürününüzü Intune ile tümleştirmek isteyen bir üçüncü taraf CA'ysanız, API kılavuzunu gözden geçirin:

- [Intune SCEP API'si GitHub deposu](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA'lar için Intune SCEP API'si kılavuzu](scep-libraries-apis.md)

## <a name="see-also"></a>Ayrıca bkz:

- [Sertifika profillerini yapılandırma](certificates-scep-configure.md)
- [Intune SCEP API'si GitHub deposu](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA'lar için Intune SCEP API'si kılavuzu](scep-libraries-apis.md)
