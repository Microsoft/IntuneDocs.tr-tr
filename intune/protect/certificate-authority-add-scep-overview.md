---
title: Microsoft Intune-Azure 'da SCEP ile üçüncü taraf sertifika yetkilileri (CA) kullanma | Microsoft Docs
description: Microsoft Intune, SCEP protokolünü kullanarak mobil cihazlara sertifika vermek için bir satıcı veya üçüncü taraf sertifika yetkilisi (CA) ekleyebilirsiniz. Bu genel bakışta, bir Azure Active Directory (Azure AD) uygulaması, sertifikaları doğrulamak için Microsoft Intune izinleri verir. Ardından, sertifika vermek için SCEP sunucunuzun kurulumunda AAD uygulamasının uygulama KIMLIĞI, kimlik doğrulama anahtarı ve kiracı KIMLIĞINI kullanın.
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
ms.openlocfilehash: 4b82124fe8f6da7116c8333e293f219d7c667f9c
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310920"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>SCEP kullanarak Intune 'A iş ortağı sertifika yetkilisi ekleme

Intune ile üçüncü taraf sertifika yetkilileri (CA) kullanın. Üçüncü taraf CA 'Lar, Basit Sertifika Kayıt Protokolü (SCEP) kullanarak yeni veya yenilenen sertifikalarla mobil aygıtlar sağlayabilir ve Windows, iOS, Android ve macOS cihazlarını destekleyebilir.

Bu özelliği kullanmanın iki bölümü vardır: açık kaynaklı API ve Intune yönetici görevleri.

**1. Bölüm-açık kaynaklı API kullanma**  
Microsoft, Intune ile tümleşecek bir API oluşturdu. API, sertifikaları doğrulayabilir, başarı veya başarısızlık bildirimleri gönderebilir ve Intune ile iletişim kurmak için SSL (özellikle SSL soket fabrikası) kullanabilirsiniz.

API 'niz, çözümlerinizde indirmeniz ve kullanmanız için [ıNTUNE SCEP API genel GitHub deposunda](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) kullanılabilir. SCEP bir cihaza sertifika sağlamadan önce Intune 'da özel sınama doğrulaması çalıştırmak için bu API 'YI üçüncü taraf SCEP sunucularıyla birlikte kullanın.

[INTUNE SCEP yönetimi çözümüyle tümleştirme](scep-libraries-apis.md) , API 'yi, yöntemlerini ve oluşturduğunuz çözümü test etme hakkında daha fazla ayrıntı sağlar.

**2. Bölüm-uygulamayı ve profili oluşturma**  
Azure Active Directory (Azure AD) uygulaması kullanarak, cihazlardan gelen SCEP isteklerini işlemek üzere Intune 'a haklar atayabilirsiniz. Azure AD uygulaması, geliştirici oluşturduğu API çözümünde kullanılan uygulama KIMLIĞI ve kimlik doğrulama anahtarı değerlerini içerir. Daha sonra Yöneticiler, Intune kullanarak SCEP sertifikaları profilleri oluşturup dağıtır ve cihazlarda dağıtım durumundaki raporları görüntüleyebilir.

Bu makalede, Azure AD uygulaması oluşturma da dahil olmak üzere bir yönetici perspektifinden bu özelliğe genel bir bakış sunulmaktadır.

## <a name="overview"></a>Genel Bakış

Aşağıdaki adımlarda, Intune 'da sertifikalar için SCEP kullanılmasına genel bir bakış sağlanmaktadır:

1. Intune 'da, bir yönetici bir SCEP sertifika profili oluşturur ve ardından profili kullanıcılara veya cihazlara hedefler.
2. Cihaz Intune 'a iade eder.
3. Intune, benzersiz bir SCEP sınaması oluşturur. Ayrıca, beklenen konu ve SAN gibi ek bütünlük denetimi bilgileri de ekler.
4. Intune hem zorluk hem de bütünlük denetimi bilgilerini şifreler ve imzalar ve bu bilgileri, SCEP isteğiyle cihaza gönderir.
5. Cihaz, Intune 'dan gönderilen SCEP sertifika profilini temel alan cihazda bir sertifika imzalama isteği (CSR) ve ortak/özel anahtar çifti oluşturur.
6. CSR ve şifreli/imzalı sınama, üçüncü taraf SCEP sunucu uç noktasına gönderilir.
7. SCEP sunucusu, CSR 'yi ve sınamayı Intune 'a gönderir. Daha sonra Intune imzayı doğrular, yükün şifresini çözer ve CSR 'yi bütünlük denetimi bilgileriyle karşılaştırır.
8. Intune, SCEP sunucusuna bir yanıt gönderir ve sınama doğrulamasının başarılı olup olmadığını belirtir.  
9. Sınama başarıyla doğrulanırsa, SCEP sunucusu sertifikayı cihaza yayınlar.

Aşağıdaki diyagramda, Intune ile üçüncü taraf SCEP tümleştirmesinin ayrıntılı bir akışı gösterilmektedir:

![Üçüncü taraf sertifika yetkilisi SCEP Microsoft Intune ile nasıl tümleştirilir?](./media/certificate-authority-add-scep-overview/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Üçüncü taraf CA tümleştirmesini ayarlama

### <a name="validate-third-party-certification-authority"></a>Üçüncü taraf sertifika yetkilisini doğrula

Üçüncü taraf sertifika yetkililerini Intune ile tümleştirmadan önce, kullanmakta olduğunuz CA 'nın Intune desteklediğinden emin olun. [Üçüncü taraf CA iş ortakları](#third-party-certification-authority-partners) (Bu makalede) bir liste içerir. Daha fazla bilgi için sertifika yetkilinizin kılavuzunu da denetleyebilirsiniz. CA, uygulamalarına özgü kurulum yönergelerini içerebilir.

### <a name="authorize-communication-between-ca-and-intune"></a>CA ve Intune arasında iletişimi yetkilendirme

Üçüncü taraf bir SCEP sunucusunun Intune ile özel sınama doğrulaması çalıştırmasına izin vermek için Azure AD 'de bir uygulama oluşturun. Bu uygulama, SCEP isteklerini doğrulamak için Intune 'a temsilci izinleri verir.

Azure AD uygulamasını kaydetmek için gerekli izinlere sahip olduğunuzdan emin olun. Azure AD belgelerinde [gerekli izinlere](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions)bakın.

#### <a name="create-an-application-in-azure-active-directory"></a>Azure Active Directory’de uygulama oluşturma  

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





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Bir SCEP sertifika profilini yapılandırma ve dağıtma
Yönetici olarak, kullanıcılara veya cihazlara hedeflemek için bir SCEP sertifika profili oluşturun. Ardından, profili atayın.

- [SCEP sertifika profili oluşturma](certificates-profile-scep.md#create-a-scep-certificate-profile)

- [Sertifika profilini atama](certificates-profile-scep.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Sertifikaları kaldırma

Cihazın kaydını kaldırdığınızda veya sildiğinizde, sertifikalar kaldırılır. Sertifikalar iptal edilmez.

## <a name="third-party-certification-authority-partners"></a>Üçüncü taraf sertifika yetkilisi iş ortakları
Aşağıdaki üçüncü taraf sertifika yetkilileri Intune 'U destekler:

- [Entrust Datacard](https://info.entrustdatacard.com/pki-eval-tool)
- [EJBCA GitHub açık kaynaklı sürümü](https://github.com/agerbergt/intune-ejbca-connector)
- [Her yaprak güveni](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [Idnomıc](https://www.idnomic.com/)
- [Sectıgo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)
- [Venafi](https://www.venafi.com/platform/enterprise-mobility)
- [SCEPman](https://azuremarketplace.microsoft.com/marketplace/apps/gluckkanja.scepman)

Ürününüzü Intune ile tümleştirmeyle ilgilenen bir üçüncü taraf CA 'nız varsa API kılavuzunu gözden geçirin:

- [Intune SCEP API GitHub deposu](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA 'Lar için Intune SCEP API Kılavuzu](scep-libraries-apis.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Sertifika profillerini yapılandırma](certificates-scep-configure.md)
- [Intune SCEP API GitHub deposu](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA 'Lar için Intune SCEP API Kılavuzu](scep-libraries-apis.md)
