---
title: SCEP Microsoft Intune - Azure ile üçüncü taraf sertifika yetkilileri (CA) kullanma | Microsoft Docs
description: Microsoft Intune'da, SCEP protokolünü kullanarak mobil cihazlara sertifikalar vermesi için bir satıcı veya üçüncü taraf sertifika yetkilisi (CA) ekleyebilirsiniz. Bu genel bakışta, bir Azure Active Directory (Azure AD) uygulaması Microsoft Intune'a sertifikaları doğrulamak için izinler verir. Ardından, sertifikaları vermek için SCEP sunucunuzun kurulumunda AAD uygulamasının uygulama kimliğini, kimlik doğrulama anahtarını ve kiracı kimliğini kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ed95507d8a7486bc1c1cca2c2a067658239eed8
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043534"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>SCEP kullanarak Intune'da iş ortağı sertifika yetkilisi ekleme

Microsoft Intune'da, üçüncü taraf sertifika yetkilileri (CA) eklenebilir. Bu CA'lar Basit Sertifika Kayıt Protokolü'nü (SCEP) kullanarak mobil cihazlara sertifikalar verebilir. Bu özellik Windows, iOS, Android ve macOS cihazlarında yeni sertifikalar verebilir ve sertifikaları yenileyebilir.

Bu özelliğin kullanımı iki bölümden oluşur: açık kaynak API'si ve Intune yönetici görevleri.

**1. Bölüm - Açık kaynak API'sini kullanma**  
Microsoft sertifikaları doğrulamak, başarı veya başarısızlık bildirimleri göndermek ve SSL (özel olarak SSL soket fabrikası) kullanarak Intune'la iletişim kurmak için Intune'la tümleştirilen bir API oluşturdu.

API'yi [Intune SCEP API genel GitHub deposundan](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) indirebilir ve çözümlerinizde kullanabilirsiniz. Cihaza sertifika vermeden önce Intune'da özel sınama doğrulama gerçekleştirmek için bu API'yi üçüncü taraf SCEP sunucularıyla kullanın.

[Intune SCEP yönetim çözümüyle tümleştirme](scep-libraries-apis.md) başlığı altında API'nin kullanımı, yöntemleri ve derlediğiniz çözümün testi hakkında daha fazla ayrıntı sağlanır.

**2. Bölüm - Uygulamayı ve profili oluşturma**  
Azure Active Directory (Azure AD) uygulamasını kullanarak, cihazlardan gelen SCEP isteklerini işlemesi için Intune'a temsilci hakları verebilirsiniz. Azure AD uygulaması, geliştiricinin oluşturduğu API çözümü içinde kullanılan uygulama kimliğini ve kimlik doğrulama anahtarını içerir. Bundan sonra yöneticiler Intune'u kullanarak SCEP sertifikaları oluşturabilir ve dağıtabilir. Ayrıca cihazlara dağıtım durumuyla ilgili raporları da görüntüleyebilirsiniz.

Bu makalede Azure AD uygulaması oluşturma da dahil olmak üzere Yönetici perspektifinden bu özelliğe bir genel bakış sağlanır.

## <a name="overview"></a>Genel Bakış

Aşağıdaki adımlar Intune'da SCEP sertifikaları verme işlemine genel bir bakış sağlar:

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

![Üçüncü taraf sertifika yetkilisi SCEP Microsoft Intune ile nasıl tümleştirilir?](./media/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Üçüncü taraf CA tümleştirmesini ayarlama

### <a name="validate-third-party-certification-authority"></a>Üçüncü taraf sertifika yetkilisini doğrulama

Üçüncü taraf sertifika yetkililerini Intune ile tümleştirmeden önce, kullandığınız CA'nın Intune'u desteklediğini onaylayın. [Üçüncü taraf CA iş ortakları](#third-party-certification-authority-partners) (bu makalede) bir liste içerir. Daha fazla bilgi için sertifika yetkilinizin kılavuzunu da gözden geçirebilirsiniz. CA, bunları uygulamaya özgü kurulum yönergeleri de içerebilir.

### <a name="authorize-communication-between-ca-and-intune"></a>CA ile Intune arasındaki iletişimi yetkilendirme

Üçüncü taraf SCEP sunucusunun özel sınama doğrulaması çalıştırmasına izin vermek için, Azure AD'de bir uygulama oluşturun. Bu uygulama Intune'a SCEP isteklerini doğrulaması için temsilci hakları verir.

Azure AD uygulamasını kaydetmek için gerekli izinlere sahip olduğunuzdan emin olun. Bkz: [gerekli izinler](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions), Azure AD belgelerinde.

#### <a name="create-an-application-in-azure-active-directory"></a>Azure Active Directory'de uygulama oluşturma  

1. İçinde [Azure portalında](https://portal.azure.com)Git **Azure Active Directory** > **uygulama kayıtları**ve ardından **yeni kayıt**.  

2. Üzerinde **bir uygulamayı kaydetme** sayfasında, aşağıdaki bilgileri belirtin:  
   - İçinde **adı** bölümünde, anlamlı uygulama adı girin.  
   - İçin **desteklenen hesap türleri** bölümünden **herhangi bir kuruluş dizini hesaplarında**.  
   - İçin **yeniden yönlendirme URI'si**, varsayılan Web değerini bırakın ve ardından üçüncü taraf SCEP sunucusu için oturum açma URL'si belirtin.  

3. Seçin **kaydetme** uygulama oluşturmak için ve yeni bir uygulama için genel bakış sayfasını açın.  

4. Uygulamasında **genel bakış** sayfasında, kopya **uygulama (istemci) kimliği** değeri ve daha sonra kullanmak üzere kaydedin. Bu değer daha sonra ihtiyacınız olacak.  

5. Uygulama için Gezinti bölmesinde, Git **sertifikaları ve parolaları** altında **Yönet**. Seçin **yeni gizli** düğmesi. Açıklamasında bir değer girin, herhangi bir seçenek seçin **Expires**ve ardından seçin **Ekle** oluşturmak için bir *değer* için istemci gizli anahtarı. 
   > [!IMPORTANT]  
   > Bu sayfadan ayrılmadan önce gizli anahtar değerini kopyalayın ve daha sonra kullanmak, üçüncü taraf CA uygulamanız ile kaydedin. Bu değeri yeniden gösterilmez. Uygulama kimliği, kimlik doğrulama anahtarı nasıl istedikleri şirket, üçüncü taraf CA için Kılavuzu gözden geçirdiğinizden emin olun ve Kiracı kimliği yapılandırılır.  

6. Kayıt, **Kiracı kimliği**. Kiracı kimliği sonra etki alanı metindir hesabınızda oturum @. Örneğin, hesabınız olup olmadığını *admin@name.onmicrosoft.com*, Kiracı Kimliğinizi ise **name.onmicrosoft.com**.  

7. Uygulama için Gezinti bölmesinde, Git **API izinleri** altında **Yönet**ve ardından **bir izin eklemek**.  

8. Üzerinde **istek API izinleri** sayfasında **Intune**ve ardından **uygulama izinleri**. Onay kutusunu seçip **scep_challenge_provider** (SCEP sınama doğrulaması).  

   Seçin **izinleri eklemek** bu yapılandırmayı kaydetmek için.  

9. Kalır **API izinleri** sayfasında ve seçin **Microsoft için yönetici onayı vermek**ve ardından **Evet**.  
   
   Azure AD'de uygulama kayıt işlemi tamamlanmıştır.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>SCEP sertifika profilini yapılandırma ve dağıtma
Yönetici olarak, kullanıcıları veya cihazları hedefleyecek bir SCEP sertifika profili oluşturun. Sonra, profili atayın.

- [SCEP sertifika profili oluşturma](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Sertifika profilini atama](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Sertifikaları kaldırma

Cihazın kaydını kaldırdığınızda veya cihazı temizlediğinizde, sertifikalar kaldırılır. Sertifikalar iptal edilmez.

## <a name="third-party-certification-authority-partners"></a>Üçüncü taraf kök sertifika yetkilisi iş ortakları
Aşağıdaki üçüncü taraf sertifika yetkilileri Intune'u destekler:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)
- [EJBCA GitHub açık kaynak sürümü](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [IDnomic](https://www.idnomic.com/)
- [Sectigo](https://sectigo.com/products)

Ürününüzü Intune ile tümleştirmek isteyen bir üçüncü taraf CA'ysanız, API kılavuzunu gözden geçirin:

- [Intune SCEP API'si GitHub deposu](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA'lar için Intune SCEP API'si kılavuzu](scep-libraries-apis.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Sertifika profillerini yapılandırma](certificates-scep-configure.md)
- [Intune SCEP API'si GitHub deposu](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA'lar için Intune SCEP API'si kılavuzu](scep-libraries-apis.md)
