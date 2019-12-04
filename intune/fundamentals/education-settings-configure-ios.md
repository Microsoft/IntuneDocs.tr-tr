---
title: iOS Classroom uygulaması için Intune ayarları
titleSuffix: Microsoft Intune
description: iOS cihazlarındaki Classroom uygulamasının ayarlarını denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6814b4d98b8512ce95119b05cc299964e486ac64
ms.sourcegitcommit: 78faf608510fbaca09bc410d63df1aa5254dee45
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74784230"
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>iOS Classroom uygulaması için Intune ayarlarını yapılandırma

> [!NOTE]
> Intune Şu anda derslik uygulamasının yapılandırılmasını desteklememektedir. Bu makale yalnızca Intune 'da mevcut iOS Eğitim profillerine sahip olan kullanıcılar için geçerlidir.  

## <a name="introduction"></a>Giriş
[Classroom](https://itunes.apple.com/app/id1085319084), öğretmenlerin öğrenmeye yol göstermesine ve sınıftaki öğrenci cihazlarını denetlemesine yardımcı olan bir uygulamadır. Örneğin bu uygulama sayesinde bir öğretmen:

- Öğrenci cihazlarında uygulamalar açabilir
- iPad ekranını kilitleyebilir ve ekranın kilidini açabilir
- Bir öğrencinin iPad ekranını görüntüleyebilir
- Öğrenci iPad’lerini bir yer işaretine veya kitaptaki bir bölüme yönlendirebilir
- Apple TV’de bir öğrenci iPad’inin ekranını görüntüleyebilir

Cihazınızda Classroom’u ayarlamak için bir Intune iOS eğitim cihaz profili oluşturmanız ve yapılandırmanız gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Bu ayarları yapılandırmaya başlamadan önce, aşağıdakilere dikkat edin:

- Hem öğretmen hem de öğrenci iPad cihazlarının Intune’a kayıtlı olması gerekir.
- Öğretmenin cihazına [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) uygulamasını yüklediğinizden emin olun. Uygulamayı el ile yükleyebilir veya [Intune uygulama yönetimi](../apps/app-management.md)'ni kullanabilirsiniz.
- Öğretmen ve öğrenci cihazları arasındaki bağlantıların kimliğini doğrulamak için sertifikaları yapılandırmanız gerekir (bkz. 2. Adım, Intune’da biriOS Education profili oluşturma ve atama).
- Öğretmen ve öğrencilerin iPad cihazları aynı Wi-Fi ağında olmalı ve cihazların Bluetooth özellikleri etkin olmalıdır.
- Classroom uygulaması iOS 9.3 veya üzerini çalıştıran denetimli iPad cihazlarında çalışır.
- Bu sürümde, Intune her öğrencinin kendine ait bir iPad cihazının olduğu 1:1 senaryosunu yönetmeyi destekler.


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>1\. Adım - Okul verilerinizi Azure Active Directory'ye aktarın

Mevcut Öğrenci Bilgi Sisteminden (SIS) Azure Active Directory’ye (Azure AD) okul kayıtlarını içeri aktarmak için Microsoft'un School Data Sync (SDS) özelliğini kullanın.
SDS, SIS bilgilerinizi eşitler ve Azure AD'de depolar. Azure AD, kullanıcıları ve cihazları düzenlemenize yardımcı olan bir Microsoft yönetim sistemidir. Ardından öğrencilerinizi ve sınıflarınızı yönetmenize yardımcı olması için bu verileri kullanabilirsiniz. [SDS dağıtma hakkında daha fazla bilgi edinin](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>SDS kullanarak veri aktarma

Aşağıdaki yöntemlerden birini kullanarak SDS’ye bilgi aktarabilirsiniz:

- [CSV dosyaları](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) - Virgülle ayrılmış değer (.csv) dosyalarını el ile dışa aktarma ve derleme
- [PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) - Azure AD ile eşitlemeyi basitleştiren bir SIS sağlayıcısı
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) - Azure AD ile eşitlemek için dışarı aktarabileceğiniz ve dönüştürebileceğiniz bir CSV biçimi

### <a name="find-out-more"></a>Daha fazla bilgi edinin

- [Şirket içi okul verilerini Azure AD’ye eşitleme deneyiminin tümü hakkında bilgi edinin](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Microsoft School Data Sync hakkında daha fazla bilgi edinin](https://sds.microsoft.com/)
- [Azure Active Directory'de lisanslama hakkında daha fazla bilgi edinin](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>2\. Adım - Intune’da bir iOS Eğitim profili oluşturun ve atayın

### <a name="configure-general-settings"></a>Genel ayarları yapılandırma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
5. Profiller bölmesinde **Profil oluştur**’u seçin.
6. **Profil oluştur** bölmesinde, iOS eğitim profili için **Ad** ve **Açıklama** girin.
7. **Platform** açılan listesinden **iOS**’yi seçin.
8. **Profil türü** açılan listesinde **Eğitim**’i seçin.
9. **Ayarlar** > **Yapılandır**’ı seçin.


Sonraki bölümde, öğretmen ve öğrencilerin iPad cihazları arasında bir güven ilişkisi kurmak için sertifikalar oluşturacaksınız. Sertifikalar, kullanıcı adları ve parolaları girmeye gerek olmadan cihazlar arasında bağlantıların kimliğini sorunsuz ve sessiz bir şekilde doğrulamak için kullanılır.

>[!IMPORTANT]
>Kullandığınız öğretmen ve öğrenci sertifikalarının, farklı sertifika yetkilileri (CA’lar) tarafından verilmiş olması gerekir. Mevcut sertifika altyapınıza bağlı iki yeni alt CA oluşturmanız gerekir; biri öğretmenler, diğeri öğrenciler için.

iOS eğitim profilleri yalnızca PFX sertifikalarını destekler. SCEP sertifikaları desteklenmez.

Oluşturulan sertifikaların, kullanıcı kimlik doğrulaması ve sunucu kimlik doğrulamasını desteklemesi gerekir.

### <a name="configure-teacher-certificates"></a>Öğretmen sertifikalarını yapılandırma

**Eğitim** bölmesinde **Öğretmen sertifikaları**’nı seçin.

#### <a name="configure-teacher-root-certificate"></a>Öğretmen kök sertifikasını yapılandırma

**Öğretmen kök sertifikası** altında gözat düğmesini seçin. Kök sertifikayı şunlardan biriyle seçin:
- .cer uzantısı (DER ve Base64 kodlanmış) 
- .P7B uzantısı (tam zincirle veya tam zincirsiz)

#### <a name="configure-teacher-pkcs12-certificate"></a>Öğretmen PKCS#12 sertifikasını yapılandırma

**Öğretmen PKCS #12 sertifikası** altında aşağıdaki değerleri yapılandırın:

- **Konu adı biçimi** - Intune, öğretmen sertifikası ortak adlarının başına otomatik olarak **lider** ifadesini getirir. Öğrenci sertifikası ortak adlarının önünde **üye** ifadesi bulunur.
- **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. 
- **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
- **Sertifika şablonu adı** - Sertifika verme yetkilisine eklenmiş bir sertifika şablonunun adını girin. 
- **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
- **Sertifika geçerlilik süresi** - Sertifikanın süresi dolmadan önce kalan süreyi belirtin.
Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, sertifika verme yetkilisinin sertifikası için kalan geçerlilik süresinden düşük olması gerekir.

Sertifikaları yapılandırmayı bitirdiğinizde **Tamam**’ı seçin.

### <a name="configure-student-certificates"></a>Öğrenci sertifikalarını yapılandırma

1. **Eğitim** bölmesinde **Öğrenci sertifikaları**’nı seçin.
2. **Öğrenci sertifikaları** bölmesinde, **Öğrenci cihaz sertifikaları** türü listesinde yazın, **1:1** seçeneğini belirleyin.

#### <a name="configure-student-root-certificate"></a>Öğrenci kök sertifikasını yapılandırma

**Öğrenci kök sertifikası** altında gözat düğmesini seçin. Kök sertifikayı şunlardan biriyle seçin:
- .cer uzantısı (DER ve Base64 kodlanmış) 
- .P7B uzantısı (tam zincirle veya tam zincirsiz)

#### <a name="configure-student-pkcs12-certificate"></a>Öğrenci PKCS#12 sertifikasını yapılandırma

**Öğrenci PKCS #12 sertifikası** altında aşağıdaki değerleri yapılandırın:

- **Konu adı biçimi** - Intune, öğretmen sertifikası ortak adlarının başına otomatik olarak **lider** ifadesini getirir. Öğrenci sertifikası ortak adlarının önünde **üye** ifadesi bulunur.
- **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez. 
- **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
- **Sertifika şablonu adı** - Sertifika verme yetkilisine eklenmiş bir sertifika şablonunun adını girin. 
- **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
- **Sertifika geçerlilik süresi** - Sertifikanın süresi dolmadan önce kalan süreyi belirtin.
Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, sertifika verme yetkilisinin sertifikası için kalan geçerlilik süresinden düşük olması gerekir.

Sertifikaları yapılandırmayı bitirdiğinizde **Tamam**’ı seçin.

## <a name="finish-up"></a>Bitirme

1. **Eğitim** bölmesinde Tamam'ı seçin.
2. **Profil Oluştur** bölmesinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

Okul verilerinizi Azure AD ile eşitlediğinizde oluşturulan sınıf gruplarındaki öğrenci cihazlarına profili atayın (bkz. [Cihaz profilleri atama](../configuration/device-profile-assign.md).

## <a name="next-steps"></a>Sonraki adımlar

Böylece bir öğretmen Classroom uygulamasını kullandığında, öğrenci cihazları üzerinde tam denetime sahip olur.

Classroom uygulaması hakkında daha fazla bilgi için Apple web sitesindeki [Classroom yardımı](https://help.apple.com/classroom/ipad/2.0/) bölümüne bakın.

Öğrenciler için paylaşılan iPad cihazları yapılandırmak istiyorsanız bkz. [Paylaşılan iPad cihazları için Intune eğitim ayarlarını yapılandırma](education-settings-configure-ios-shared.md).
