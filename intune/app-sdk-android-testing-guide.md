---
title: Microsoft Intune App SDK test Android Geliştirici Kılavuzu
description: Microsoft Intune App SDK Android test kılavuzu için Intune tarafından yönetilen Android uygulamanızı test etmenize yardımcı olur.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f8fa8f361e886c8eac697bb585ccf15eb9152f1
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043850"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Microsoft Intune App SDK Kılavuzu test Android geliştiricileri için

Microsoft Intune App SDK Android test kılavuzu için Intune tarafından yönetilen Android uygulamanızı test etmenize yardımcı olmak için tasarlanmıştır.  

## <a name="prerequisite-test-accounts"></a>Önkoşul test hesapları
Yeni hesaplar, önceden oluşturulan verileri olmadan ve oluşturulabilir. Yeni bir hesap oluşturmak için:
1. Gidin [Microsoft Demos](https://demos.microsoft.com/environments/create/tenant) site. 
2. [Intune'u ayarlama](https://docs.microsoft.com/intune/setup-steps) mobil cihaz Yönetimi (MDM) etkinleştirmek için.
3. [Kullanıcılar oluşturma](https://docs.microsoft.com/intune/users-add).
4. [Grup oluşturma](https://docs.microsoft.com/intune/groups-add).
5. [Lisans atama](https://docs.microsoft.com/intune/licenses-assign) testiniz için uygun şekilde.


## <a name="azure-portal-policy-configuration"></a>Azure portal ilkesi yapılandırma
[Uygulama koruma ilkeleri oluşturma ve atama](https://docs.microsoft.com/intune/app-protection-policies) içinde [Azure portal'ın Intune dikey penceresinde](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). [Uygulama yapılandırma İlkesi](https://docs.microsoft.com/intune/app-configuration-policies-overview) de oluşturulabilir ve Intune dikey penceresinde atanmış.

> [!NOTE]
> Uygulamanızı Azure portalında listede yoksa, onu bir ilkeyle seçerek hedefleyebilir **daha fazla uygulama** seçeneği ve paket adı metin kutusunda sağlama.

> [!IMPORTANT]
> Uygulamak bir uygulama yapılandırma ilkesi için kaydolan kullanıcı tarafından hedeflenmelidir bir [Intune uygulama koruma İlkesi](https://docs.microsoft.com/intune/app-protection-policy).

## <a name="test-cases"></a>Test çalışmaları

Aşağıdaki test çalışmaları, yapılandırma ve doğrulama adımlarını sağlar. Intune ile yönetilen Android uygulaması sorunlarını gidermenize yardımcı olması için bu kılavuzu kullanın.

### <a name="required-pin-and-corporate-credentials"></a>Gerekli PIN ve Kurumsal kimlik bilgileri

Şirket kaynaklarına erişim için PIN'i zorunlu kılabilir. Ayrıca, kullanıcılar yönetilen uygulamaları kullanabilmesi için önce şirket kimlik doğrulamasını zorunlu kılabilir. Bu gereksinimleri ayarlamak için aşağıdaki adımları kullanın:

1. Yapılandırma **erişim için PIN'i zorunlu kıl** ve **erişim için Kurumsal kimlik bilgilerini gerektir** için **Evet**. Daha fazla bilgi için [Android uygulama koruma İlkesi ayarları Microsoft Intune](app-protection-policy-settings-android.md#access-requirements).
2. Aşağıdaki koşulları doğrulayın:
    - Uygulama başlatma, PIN girişi/Kurulum ve/veya Şirket portalı kayıt sırasında kullanılan üretim kullanıcı için bir istem sunmalıdır.
    - Geçerli bir oturum açma istemi sunmak için hata, yanlış yapılandırılmış bir android bildirimi, özellikle ADAL tümleştirme (SkipBroker ClientID ve yetkilisi) için değerleri nedeniyle olabilir.
    - Herhangi bir istemi sunmak için hata nedeniyle yanlış tümleşik olabilir `MAMActivity` değeri. Hakkında daha fazla bilgi için `MAMActivity`, bkz: [Android Geliştirici Kılavuzu için Microsoft Intune App SDK](app-sdk-android.md).

> [!NOTE] 
> Yukarıdaki test çalışmazsa, aşağıdaki testleri büyük olasılıkla de başarısız olur. Gözden geçirme [SDK](app-sdk-android.md##sdk-integration) ve [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) tümleştirme.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Diğer uygulamalarla veri almak ve aktarma kısıtlama
Aşağıdaki gibi Kurumsal yönetilen uygulamalar arasında veri aktarımını denetleyebilirsiniz:

1. Ayarlama **uygulamanın diğer uygulamalara veri aktarmasına izin ver** için **ilkeyle yönetilen uygulamalar**.
2. Ayarlama **uygulamanın diğer uygulamalardan veri almasına izin ver** için **tüm uygulamalar**. Hedefleri ve içerik sağlayıcıları bu ilkelerden etkilenir.
3. Aşağıdaki koşulları doğrulayın:
    - Yönetilmeyen bir uygulamadan uygulama işlevlerinizi doğru açılıyor.
    - Yönetilen uygulamalar arasında içerik paylaşımını izin verilir.
    - Yönetilen uygulamalarda yönetilmeyen uygulamalara (örneğin, Chrome) paylaşım ise engellenir.

### <a name="restrict-cut-copy-and-paste"></a>Kesme, kopyalama ve yapıştırma işlemlerini kısıtla
Yönetilen uygulamalar için sistem panosuna aşağıda açıklandığı şekilde kısıtlayabilirsiniz:

1. Ayarlama **kısıtlama kesme, kopyalama ve yapıştırma diğer uygulamalarla** için **yapıştırma seçeneğiyle ilke ile yönetilen**.
2. Aşağıdaki koşulları doğrulayın:
    - Metin uygulamanızdan yönetilen kopyalama, yönetilmeyen bir uygulamaya (örneğin, iletiler) engellenir.

### <a name="prevent-save-as"></a>Engelleme **Farklı Kaydet**
Denetleyebileceğiniz **Kaydet** işlevselliğini aşağıdaki gibi:

1. Uygulamanızı gerektiriyorsa [tümleşik 'Kaydet' denetimleri](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted)ayarlayın **Engelle 'Kaydet'** için **Evet**.
2. Aşağıdaki koşulları doğrulayın:
    - Kaydetme yalnızca uygun yönetilen konumlara sınırlıdır.

### <a name="file-encryption"></a>Dosya şifreleme
Ayrıca verileri cihaz üzerinde gibi şifreleme de yapabilirsiniz:

1. Ayarlama **uygulama verilerini şifrele** için **Evet**.
2. Aşağıdaki koşulları doğrulayın:
    - Normal uygulama davranışı etkilenmeyecektir.

### <a name="prevent-android-backups"></a>Android yedeklemelerini engelle
Uygulama yedeğini aşağıdaki gibi denetleyebilirsiniz:

1. Ayarladıysanız [tümleşik yedekleme kısıtlamaları](app-sdk-android.md#protecting-backup-data), yapılandırma **Android yedeklemelerini engelle** için **Evet**.
2. Aşağıdaki koşulları doğrulayın:
    - Yedeklemeleri kısıtlanır.

### <a name="unenrollment"></a>Kayıt kaldırma
Şirket e-posta ve belgelerini içeren yönetilen uygulamalarının uzaktan silebilir ve artık şu şekilde yönetildiğini, kişisel verilerin şifresi çözülür:

1. Azure portalından [bir temizleme sorunu](https://docs.microsoft.com/intune/apps-selective-wipe).
2. Aşağıdaki koşullardan herhangi bir temizleme işleyicileri onaylamak için uygulamanızı kaydedilmiyorsa:
    - Uygulamanın tam temizleme gerçekleşir.
3. Uygulamanız için kayıtlı olmadığını `WIPE_USER_DATA` veya `WIPE_USER_AUXILARY_DATA`, aşağıdaki koşulları doğrulayın:
    - Yönetilen içerik uygulamadan kaldırılır. Daha fazla bilgi için [Android Geliştirici Kılavuzu - seçmeli silme için Intune uygulama SDK'sı](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Çoklu Kimlik
Tümleştirme [çoklu kimlik desteği](app-sdk-android.md#multi-identity-optional) baştan sona test edilmesi gereken bir yüksek riskli değişikliktir. Yaygın sorunların çoğunu hatalı ayarı (tehdit düzeyi ve bağlam) kimliğini ve ayrıca dosyaların izlenmesi için son (`MAMFileProtectionManager`).

En düşük düzeyde aşağıdaki senaryolar için birden çok kimliği yeniden doğrulanır:

- **Farklı Kaydet** ilke yönetilen kimlikleri için doğru çalışıyor.
- Kopyala-yapıştır kısıtlamaları doğru gelen kişisel yönetilen uygulanır.
- Yalnızca yönetilen kimliğine ait veriler şifrelenir ve kişisel dosyaları değiştirilmedi.
- Kayıt kaldırma sırasında seçmeli silme yalnızca yönetilen kimlik verilerini kaldırır.
- Son kullanıcı koşullu başlatma için yönetilmeyen disklerden yönetilen hesabı (yalnızca ilk kez) değiştirirken istenir.

### <a name="app-configuration-optional"></a>Uygulama Yapılandırma (isteğe bağlı)
Yönetilen uygulamaların davranışı aşağıdaki gibi yapılandırabilirsiniz:

1. Uygulamanızı herhangi bir uygulama yapılandırma ayarlarını kullanırsa, uygulamanızın doğru şekilde (Yönetici) olarak ayarlayabileceğiniz tüm değerleri işler test etmeniz gerekir. [Uygulama yapılandırma ilkeleri](https://docs.microsoft.com/intune/app-configuration-policies-overview) oluşturulabilir ve Intune kullanarak atanmış.

## <a name="next-steps"></a>Sonraki adımlar

- [Android iş kolu satır uygulama Microsoft Intune ekleme](lob-apps-android.md).
