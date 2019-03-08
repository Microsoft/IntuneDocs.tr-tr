---
title: iOS Classroom uygulaması için Intune paylaşılan cihaz ayarları
titleSuffix: Microsoft Intune
description: iOS cihazlarındaki Classroom uygulamasının ayarlarını denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/06/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e0b8230a842a7b4e3b1368388cb186defa8df72
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566599"
---
# <a name="configure-intune-education-settings-for-shared-ipad-devices"></a>Paylaşılan iPad cihazları için Intune eğitim ayarlarını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> Classroom uygulaması için Intune ayarlarını Intune'da artık kullanılmıyor. Bu makale, yalnızca Intune’da mevcut eğitim profilleri olan kullanıcılar için geçerlidir.

Intune, öğretmenlerin sınıfta öğrenimi yönlendirmesine ve öğrenci cihazlarını denetlemesine yardımcı olan iOS Classroom uygulamasını destekler. Classroom uygulamasına ek olarak Apple, öğrenci iPad cihazlarının, birden çok öğrenci tek bir cihazı paylaşacak şekilde yapılandırılmasını destekler. Bu belge, Intune ile bu hedefe ulaşmada size yol gösterir.

Ayrılmış (1:1) iPad cihazlarını Classroom uygulamasında kullanmak üzere yapılandırma hakkında daha fazla bilgi için bkz. [Intune ayarlarını iOS Classroom uygulaması için yapılandırma](education-settings-configure-ios.md).

## <a name="before-you-start"></a>Başlamadan önce

Paylaşılan iPad özelliklerini kullanmak için önkoşullar şunlardır:

- [Apple School Manager](apple-school-manager-set-up-ios.md) ve [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617)’i kurma.
- Apple School Manager kurulumunun bir parçası olarak [Apple kimliklerini yönet](http://help.apple.com/schoolmanager/#/tes78b477c81)'i öğrenciler için yapılandırın. [Yönetilen Apple kimlikleri hakkında daha fazla bilgi edinin](https://support.apple.com/HT205918).
- Apple School Manager'dan eşitlenmiş cihaz seri numaraları için bir kayıt profili oluşturun.

## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>1. Adım - Okul verilerinizi Azure Active Directory'ye aktarın

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


## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>2. Adım - Intune’da bir iOS Eğitim profili oluşturun ve atayın

### <a name="configure-general-settings"></a>Genel ayarları yapılandırma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
5. Profiller bölmesinde **Profil oluştur**’u seçin.
6. **Profil oluştur** bölmesinde, iOS eğitim profili için **Ad** ve **Açıklama** girin.
7. **Platform** açılan listesinden **iOS**’yi seçin.
8. **Profil türü** açılan listesinde **Eğitim**’i seçin.
9. **Ayarlar** > **Yapılandır**’ı seçin.

Ardından, öğretmen ve öğrencilerin iPad cihazları arasında bir güven ilişkisi kurmak için sertifikalara ihtiyacınız olacaktır. Sertifikalar, kullanıcı adları ve parolaları girmeye gerek olmadan cihazlar arasında bağlantıların kimliğini sorunsuz ve sessiz bir şekilde doğrulamak için kullanılır.

>[!Important]
>Kullandığınız öğretmen ve öğrenci sertifikalarının farklı sertifika yetkilileri (CA'lar) tarafından verilmiş olması gerekir. Mevcut sertifika altyapınıza bağlı iki yeni alt CA oluşturmanız gerekir; biri öğretmenler, diğeri öğrenciler için.

iOS eğitim profilleri yalnızca PFX sertifikalarını destekler. SCEP sertifikaları desteklenmez.

Oluşturduğunuz sertifikaların, kullanıcı kimlik doğrulamasına ek olarak sunucu kimlik doğrulamasını da desteklemesi gerekir.

### <a name="configure-teacher-certificates"></a>Öğretmen sertifikalarını yapılandırma

**Eğitim** bölmesinde **Öğretmen sertifikaları**’nı seçin.

#### <a name="configure-teacher-root-certificate"></a>Öğretmen kök sertifikasını yapılandırma

**Öğretmen kök sertifikası** altında, .cer (DER veya Base64 ile kodlanmış) veya .P7B (tam zincir içeren veya içermeyen) uzantısına sahip öğretmen kök sertifikasını seçmek için gözat düğmesini seçin.

#### <a name="configure-teacher-pkcs12-certificate"></a>Öğretmen PKCS#12 sertifikasını yapılandırma

**Öğretmen PKCS #12 sertifikası** altında aşağıdaki değerleri yapılandırın:

- **Konu adı biçimi** - Intune, öğretmen sertifikası için **lider**, öğrenci sertifikası içinse **üye** ön ekini sertifika ortak adına otomatik olarak ekler.
- **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez.
- **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
- **Sertifika şablonu adı** - Sertifika verme yetkilisine eklenmiş bir sertifika şablonunun adını girin.
- **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
- **Sertifika geçerlilik süresi** - Sertifikanın süresi dolmadan önce kalan süreyi belirtin. Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, sertifika verme yetkilisinin sertifikası için kalan geçerlilik süresinden düşük olması gerekir.

Öğretmen sertifikalarını yapılandırmayı bitirdiğinizde **Tamam**'ı seçin.

### <a name="configure-student-certificates"></a>Öğrenci sertifikalarını yapılandırma

1. **Eğitim** bölmesinde **Öğrenci sertifikaları**’nı seçin.
2. **Öğrenci sertifikaları** bölmesinde, **Öğrenci cihaz sertifikaları türü** listesinden **Paylaşılan iPad**'i seçin.

#### <a name="configure-student-root-certificate"></a>Öğrenci kök sertifikasını yapılandırma

**Cihaz kök sertifikası** altından, uzantısı .cer (DER veya Base64 ile kodlanmış) veya .P7B (tam zincir içeren veya içermeyen) olan öğrenci kök sertifikasını seçmek için gözat düğmesini seçin.

#### <a name="configure-device-pkcs12-certificate"></a>Cihaz PKCS#12 sertifikasını yapılandırma

**Öğrenci PKCS #12 sertifikası** altında aşağıdaki değerleri yapılandırın:

- **Konu adı biçimi** - Intune, öğretmen sertifikası için lider, cihaz sertifikası içinse üye ön ekini sertifika ortak adına otomatik olarak ekler.
- **Sertifika yetkilisi** - Windows Server 2008 R2 veya üzeri bir Enterprise sürümünde çalışan Kuruluş Sertifika Yetkilisi (CA). Tek Başına CA desteklenmez.
- **Sertifika yetkilisi adı** - Sertifika yetkilinizin adını girin.
- **Sertifika şablonu adı** - Sertifika verme yetkilisine eklenmiş bir sertifika şablonunun adını girin.
- **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
- **Sertifika geçerlilik süresi** - Sertifikanın süresi dolmadan önce kalan süreyi belirtin. Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, sertifika verme yetkilisinin sertifikası için kalan geçerlilik süresinden düşük olması gerekir.

Sertifikaları yapılandırmayı bitirdiğinizde **Tamam**’ı seçin.

### <a name="complete-certificate-setup"></a>Sertifika Kurulumunu Tamamlama

1. **Eğitim** bölmesinde **Tamam**'ı seçin.
2. **Profil Oluştur** bölmesinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

## <a name="step-3---create-a-device-category"></a>3. Adım - Bir cihaz kategorisi oluşturun

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz kaydı**'nı seçin.
4. **Cihaz kaydı - Genel Bakış** bölmesinde **Cihaz kategorileri**’ni seçin.
5. **Cihaz kaydı - Cihaz Kategorileri** bölmesinde **Oluştur**'u seçin.
6. **Cihaz kategorisi oluştur** bölmesinde kategori için bir **Ad** ve **Açıklama** girin.
7. **Cihaz kategorisi oluştur** bölmesinde **Oluştur**'u seçin.

Cihaz kategorisi **Kayıt – Cihaz Kategorileri** bölmesinde oluşturulur.

## <a name="step-4--create-a-dynamic-group"></a>4. Adım – Dinamik bir grup oluşturun

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Gruplar**'ı seçin.
4. **Kullanıcılar ve Gruplar – Tüm Gruplar** bölmesinde **Yeni grup**'u seçin.
5. **Grup** bölmesinde **Grup türü**'nü seçin ve grup için **Ad** ve **Açıklama** girin.
6. **Üyelik türü** açılan listesinde, **Dinamik Cihaz**'ı seçin.
7. Üyelik kuralları oluşturmak için **Dinamik cihaz üyeleri**'ni seçin.
8. **Dinamik üyelik kuralları** bölmesinde:
1. Açılan **Şu koşullara uyan cihaz ekle** listesinden **deviceCategory**'yi seçin.
2. **Eşittir**'i seçin.
3. Oluşturduğunuz cihaz kategorisini boş metin kutusuna girin.
9. **Dinamik üyelik kuralları** bölmesinde **Sorgu ekle**'yi seçin.
10. **Grup** bölmesinde **Oluştur**'u seçin.

Dinamik grup **Kullanıcılar ve Gruplar – Tüm Gruplar** bölmesinde oluşturulur.

## <a name="step-5--assign-a-device-to-a-category-carts"></a>5. Adım – Bir kategoriye cihaz atayın (Sepetler)

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihazlar**’ı seçin.
4. **Cihazlar** bölmesinde **Tüm cihazlar**'ı seçin.
5. **Cihazlar – Tüm cihazlar** bölmesinde bir cihaz seçin.
6. Cihaz bölmesinde **Özellikler**'i seçin.
7. Cihazın özellikler bölmesinde, **Cihaz kategorisi** metin kutusuna cihaz kategorisini girin.
8. Cihaz bölmesinde **Kaydet**'i seçin.

Cihaz artık cihaz kategorisiyle ilişkilendirilmiştir. Bu işlemi, oluşturduğunuz cihaz kategorisiyle ilişkilendirmek istediğiniz tüm cihazlar için yineleyin.

## <a name="step-6--create-classroom-profiles"></a>6. Adım – Sınıf profilleri oluşturma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz yapılandırması** bölmesinde **Yönet** > **Sepet Profilleri**'ni seçin.
5. Profiller bölmesinde **Profil Oluştur**’u seçin.
6. **İlişkilendirme Oluştur** bölmesinde, bir **Ad** ve **Açıklama** girin.
7. Grupları Sepet Profili ile ilişkilendirmek için **Sınıf Seç** > **Yapılandır** seçeneklerini belirleyin.
8. Sepet Profili'ne dahil edilecek sınıfları seçin sonra **Seç**'i işaretleyin. 
9. Grupları Sepet Profili ile ilişkilendirmek için **Sepet Seç** > **Yapılandır**'ı seçin.
10. Sepet Profili'ne dahil etmek istediğiniz grupları seçin, sonra **Seç**'i işaretleyin.
11. **İlişkilendirme Oluştur** bölmesinde, Sepet Profili'ni kaydetmek için **Kaydet**'i seçin.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

## <a name="step-7---assign-the-cart-profile-to-classes"></a>7. Adım - Sepet Profilini Sınıflara Atama

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz yapılandırması** bölmesinde, **İzle** > **Atama durumu**'nu seçin.
5. **Atama durumu** bölmesinde, oluşturduğunuz **Sepet Profili**'ni seçin.
6. **Sepet Profili** bölmesinde **Atamalar**'ı seçin, sonra **Dahil Et**'in altından **Dahil edilecek grupları seç**'i seçin.
7. Sepet profilinin hedeflemesini istediğiniz sınıfları seçin (bir grup seçmeyin), sonra **Seç**'i işaretleyin. 
8. İşiniz bittiğinde **Kaydet**’i seçin.

Atama tamamlanır ve Intune, sınıf atamasını temel alarak Classroom profilini hedeflenen cihazlara dağıtır.

## <a name="next-steps"></a>Sonraki Adımlar

Artık öğrenciler cihazları aralarında paylaşabilir ve sınıftaki herhangi bir iPad'i alıp, bir PIN ile oturum açıp iPad'i kendi içerikleriyle kişiselleştirebilir. Paylaşılan iPad'ler hakkında daha fazla bilgi için [Apple web sitesine](https://www.apple.com/education/it/) bakın.
