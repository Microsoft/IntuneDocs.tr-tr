---
title: Microsoft Intune - Azure’da SCEP ile üçüncü taraf CA kullanma | Microsoft Docs
description: Microsoft Intune'da, SCEP protokolünü kullanarak mobil cihazlara sertifikalar vermesi için bir satıcı veya üçüncü taraf sertifika yetkilisi (CA) ekleyebilirsiniz. Bu genel bakışta, bir Azure Active Directory (Azure AD) uygulaması Microsoft Intune'a sertifikaları doğrulamak için izinler verir. Ardından, sertifikaları vermek için SCEP sunucunuzun kurulumunda AAD uygulamasının uygulama kimliğini, kimlik doğrulama anahtarını ve kiracı kimliğini kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ee5a39ee8a146fbc6a85a9f4438b8e14a408a735
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321846"
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

## <a name="overview"></a>Genel bakış

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

Azure AD uygulamasını kaydetmek için gerekli izinlere sahip olduğunuzdan emin olun. [Gerekli izinler](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) altında adımlar listelenir.

**1. Adım: Azure AD uygulaması oluşturma**

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Azure Active Directory** > **Uygulama kayıtları** > **Yeni uygulama kaydı**'nı seçin.
3. Bir ad ve oturum açma URL'si girin. Uygulama türü olarak **Web uygulaması / API**'yi seçin.
4. **Oluştur**’u seçin.

[Uygulamaları Azure Active Directory ile tümleştirme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications), URL ve ad ipuçlarıyla birlikte uygulama oluşturmayla ilgili bazı yönergeler içerir.

**2 Adım: İzinleri verme**

Uygulamanızı oluşturduktan sonra, Microsoft Intune API'sine gerekli izinleri verin:

1. Azure AD uygulamanızda **Ayarlar** > **Gerekli İzinler**'i açın.  
2. **Ekle** > **API seçin** > **Microsoft Intune API'si** > **Seç** öğesini seçin.
3. **İzinleri seçin** alanında **SCEP sınama doğrulaması** > **Seç** öğesini seçin.
4. Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

**3. Adım: Uygulama kimliğini ve kimlik doğrulama anahtarını alma**

Ardından, Azure AD uygulamanızın kimlik ve anahtar değerlerini alın. Aşağıdaki değerler gerekir:

- Uygulama kimliği
- Kimlik doğrulama anahtarı
- Kiracı kimliği

**Uygulama kimliğini ve kimlik doğrulama anahtarını almak için**:

1. Azure AD'de, yeni uygulamanızı seçin (**Uygulama kayıtları**).
2. **Uygulama kimliği**'ni kopyalayın ve uygulama kodunuzda depolayın.
3. Sonra bir kimlik doğrulama anahtarı oluşturun. Azure AD uygulamanızda **Ayarlar** > **Anahtarlar**'ı açın.
4. **Parolalar**'da, açıklama girin ve anahtarın süresini seçin. Yaptığınız değişiklikleri **kaydedin**. Gösterilen değeri kopyalayın ve kaydedin.

    > [!IMPORTANT]
    > Bu anahtarı hemen kopyalayıp kaydedin çünkü bunlar yeniden gösterilmez. Bu anahtar değeri üçüncü taraf CA uygulamanız için gereklidir. Uygulama Kimliği, Uygulama Anahtarı ve Kiracı Kimliğinin nasıl yapılandırılmasını istedikleri konusundaki yönergelerini gözden geçirin.

**Kiracı Kimliği**, hesabınızın @ işaretinden sonraki etki alanı metnidir. Örneğin hesabınız `admin@name.onmicrosoft.com` ise, kiracı kimliğiniz **name.onmicrosoft.com**'dur.

[Uygulama kimliğini ve kimlik doğrulama anahtarını alma](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key) başlığı altında bu değerleri alma adımları listelenir ve Azure AD uygulamalarıyla ilgili daha fazla ayrıntı sağlar.

### <a name="configure-and-deploy-a-scep-certificate-profile"></a>SCEP sertifika profilini yapılandırma ve dağıtma
Yönetici olarak, kullanıcıları veya cihazları hedefleyecek bir SCEP sertifika profili oluşturun. Sonra, profili atayın.

- [SCEP sertifika profili oluşturma](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Sertifika profilini atama](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Sertifikaları kaldırma

Cihazın kaydını kaldırdığınızda veya cihazı temizlediğinizde, sertifikalar kaldırılır. Sertifikalar iptal edilmez.

## <a name="third-party-certification-authority-partners"></a>Üçüncü taraf kök sertifika yetkilisi iş ortakları
Aşağıdaki üçüncü taraf sertifika yetkilileri Intune'u destekler:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)

Ürününüzü Intune ile tümleştirmek isteyen bir üçüncü taraf CA'ysanız, API kılavuzunu gözden geçirin:

- [Intune SCEP API'si GitHub deposu](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA'lar için Intune SCEP API'si kılavuzu](scep-libraries-apis.md)

## <a name="see-also"></a>Ayrıca bkz:

- [Sertifika profillerini yapılandırma](certificates-scep-configure.md)
- [Intune SCEP API'si GitHub deposu](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Üçüncü taraf CA'lar için Intune SCEP API'si kılavuzu](scep-libraries-apis.md)
