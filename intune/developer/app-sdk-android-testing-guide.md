---
title: Android için uygulama SDK 'Sı geliştirici test Kılavuzu Microsoft Intune
description: Android için Microsoft Intune uygulama SDK 'Sı test Kılavuzu, Intune ile yönetilen Android uygulamanızı test etmenize yardımcı olur.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
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
ms.openlocfilehash: a8ffc81ec2dba3eac0af4eeb94e22002ec8afa87
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730361"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Android için Microsoft Intune uygulama SDK 'Sı geliştiriciler test Kılavuzu

Android için Microsoft Intune uygulama SDK 'Sı test Kılavuzu, Intune ile yönetilen Android uygulamanızı test etmenize yardımcı olmak için tasarlanmıştır.  

## <a name="prerequisite-test-accounts"></a>Önkoşul test hesapları
Yeni hesaplar önceden oluşturulmuş verilerle ve ile oluşturulabilir. Yeni bir hesap oluşturmak için:
1. [Microsoft gösterileri](https://demos.microsoft.com/environments/create/tenant) sitesine gidin. 
2. [Intune](../fundamentals/setup-steps.md) 'u mobil cihaz YÖNETIMI (MDM) etkinleştirecek şekilde ayarlayın.
3. [Kullanıcı oluşturun](../fundamentals/users-add.md).
4. [Grupları oluşturun](../fundamentals/groups-add.md).
5. Test testiniz için uygun şekilde [lisans atayın](../fundamentals/licenses-assign.md) .


## <a name="azure-portal-policy-configuration"></a>Azure portal ilkesi yapılandırması
[Azure Portal Intune dikey](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview)penceresinde [Uygulama koruma ilkeleri oluşturun ve atayın](../apps/app-protection-policies.md) . [Uygulama yapılandırma ilkeniz](../apps/app-configuration-policies-overview.md) da, Intune dikey penceresinde oluşturulup atanabilir.

> [!NOTE]
> Uygulamanız Azure portal listelenmemişse, **daha fazla uygulama** seçeneğini belirleyerek ve metin kutusunda paket adını sağlayarak bu ilkeyi bir ilkeyle hedefleyebilirsiniz.

> [!IMPORTANT]
> Uygulama yapılandırma ilkesinin uygulanabilmesi için, kaydolan Kullanıcı bir [Intune uygulama koruma ilkesi](../apps/app-protection-policy.md)tarafından hedeflenmelidir.

## <a name="test-cases"></a>Test çalışmaları

Aşağıdaki test çalışmaları yapılandırma ve onay adımları sağlar. Intune tarafından yönetilen Android uygulama sorunlarını gidermeye yardımcı olması için bu kılavuzu kullanın.

### <a name="required-pin-and-corporate-credentials"></a>Gerekli PIN ve şirket kimlik bilgileri

Şirket kaynaklarına erişmek için PIN 'i zorunlu kılabilirsiniz. Ayrıca, kullanıcıların yönetilen uygulamaları kullanabilmesi için önce şirket kimlik doğrulamasını uygulayabilirsiniz. Bu gereksinimleri ayarlamak için aşağıdaki adımları kullanın:

1. **Erişim IÇIN PIN gerektir** ' i yapılandırın ve **Evet**'e **erişmek için kurumsal kimlik bilgileri gerektir** . Daha fazla bilgi için, bkz. [Microsoft Intune Android uygulama koruma ilkesi ayarları](../apps/app-protection-policy-settings-android.md#access-requirements).
2. Aşağıdaki koşulları onaylayın:
    - Uygulama başlatma, PIN girişi/kurulumu ve/veya Şirket Portalı kayıt sırasında kullanılan üretim kullanıcısı için bir istem sunmalıdır.
    - Geçerli bir oturum açma istemi sunamaması, özellikle ADAL tümleştirmesi (SkipBroker, ClientID ve Authority) değerleri için yanlış yapılandırılmış bir Android bildirimi nedeniyle olabilir.
    - Herhangi bir istem sunma hatası, yanlış tümleşik `MAMActivity` değeri nedeniyle olabilir. @No__t-0 hakkında daha fazla bilgi için bkz. [Android Için uygulama SDK 'sı geliştirici kılavuzu Microsoft Intune](app-sdk-android.md).

> [!NOTE] 
> Yukarıdaki test çalışmıyorsa aşağıdaki testler de başarısız olur. [SDK](app-sdk-android.md##sdk-integration) ve [adal](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) tümleştirmesini gözden geçirin.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Diğer uygulamalarla veri aktarımını ve almayı kısıtlama
Kurumsal yönetilen uygulamalar arasında veri aktarımını şu şekilde denetleyebilirsiniz:

1. **Uygulamanın diğer uygulamalara veri aktarmasına Izin ver** **ilkesini ilkeyle yönetilen uygulamalar**olarak ayarlayın.
2. **Uygulamanın diğer uygulamalardan tüm uygulamalara veri almasına Izin ver** 'i ayarlayın. Amaç ve içerik sağlayıcılarının kullanımı, bu ilkelerden etkilenmez.
3. Aşağıdaki koşulları onaylayın:
    - Yönetilmeyen bir uygulamadan uygulama işlevlerinizi doğru açma.
    - Yönetilen uygulamalar arasında içerik paylaşımına izin verilir.
    - Yönetilen uygulamalardan Yönetilemeyen uygulamalara (örneğin, Chrome) paylaşılması engellenir.

### <a name="restrict-cut-copy-and-paste"></a>Kesme, kopyalama ve yapıştırmayı kısıtla
Sistem panosunu yönetilen uygulamalarla şu şekilde kısıtlayabilirsiniz:

1. **' In yapıştırma ile yönetilen ilkeye** **, diğer uygulamalarla kesme, kopyalama ve yapıştırmayı Kısıtla seçeneğini** belirleyin.
2. Aşağıdaki koşulları onaylayın:
    - Uygulamanızdan yönetilen yönetilmeyen bir uygulamaya (örneğin, Iletiler) metin kopyalama engellenir.

### <a name="prevent-save-as"></a>**Farklı kaydet** 'i engelle
Farklı **Kaydet** işlevlerini aşağıdaki şekilde denetleyebilirsiniz:

1. Uygulamanız [Tümleşik ' farklı Kaydet ' denetimleri](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted)gerektiriyorsa, **' farklı Kaydet '** seçeneğini **Evet**olarak belirleyin.
2. Aşağıdaki koşulları onaylayın:
    - Kaydet yalnızca uygun yönetilen konumlara kısıtlıdır.

### <a name="file-encryption"></a>Dosya şifreleme
Cihazdaki verileri aşağıdaki gibi şifreleyebilirsiniz:

1. **Uygulama verilerini şifreleyin** ' i **Evet**olarak ayarlayın.
2. Aşağıdaki koşulları onaylayın:
    - Normal uygulama davranışı etkilenmez.

### <a name="prevent-android-backups"></a>Android yedeklemelerini engelle
Uygulama yedeklemesini şöyle denetleyebilirsiniz:

1. [Tümleşik yedekleme kısıtlamaları](app-sdk-android.md#protecting-backup-data)ayarladıysanız, yapılandırma **Android yedeklemelerini** **Evet**olarak engelleyin.
2. Aşağıdaki koşulları onaylayın:
    - Yedeklemeler kısıtlıdır.

### <a name="unenrollment"></a>Kayıt kaldırmaya
Yönetilen uygulamaları, şirket e-postalarından ve belgelerinden uzaktan temizleyebilirsiniz ve kişisel veriler artık şu şekilde yönetilmediğinde çözülür:

1. Azure portal, [silme](../apps/apps-selective-wipe.md)işlemi yapın.
2. Uygulamanız herhangi bir silme işleyicisine kaydolmadığından, aşağıdaki koşulları onaylayın:
    - Uygulamanın tam temizleme işlemi gerçekleşir.
3. Uygulamanız `WIPE_USER_DATA` veya `WIPE_USER_AUXILARY_DATA` için kaydedilmişse, aşağıdaki koşulları onaylayın:
    - Yönetilen içerik uygulamadan kaldırılır. Daha fazla bilgi için bkz. [Android Için Intune uygulama SDK 'sı Geliştirici Kılavuzu-seçmeli silme](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Çoklu Kimlik
[Çoklu kimlik desteğini](app-sdk-android.md#multi-identity-optional) tümleştirme, kapsamlı bir şekilde test olması gereken yüksek riskli bir değişiklik. En yaygın sorunlar, kimliğin (bağlam ve tehdit düzeyi) yanlış ayarı ve ayrıca izleme dosyaları (`MAMFileProtectionManager`) nedeniyle olacaktır.

Çoklu kimlik için aşağıdaki senaryolar yeniden doğrulanması gerekir:

- **Farklı kaydet** ilkesi, Yönetilen kimlikler için doğru şekilde çalışıyor.
- Kopyalama yapıştırma kısıtlamaları, yönetilene doğru şekilde uygulanır.
- Yalnızca yönetilen kimliğe ait veriler şifrelenir ve kişisel dosyalar değiştirilmez.
- Kayıt kaldırma sırasında seçmeli Temizleme yalnızca yönetilen kimlik verilerini kaldırır.
- Yönetilmeyen bilgisayardan yönetilen hesaba (yalnızca ilk kez) değiştirilirken, son kullanıcıdan koşul başlatması istenir.

### <a name="app-configuration-optional"></a>Uygulama yapılandırması (isteğe bağlı)
Yönetilen uygulamaların davranışını aşağıdaki gibi yapılandırabilirsiniz:

1. Uygulamanız herhangi bir uygulama yapılandırma ayarını kullanıyorsa, uygulamanızın sizin (yönetici olarak) ayarlayabileceğiniz tüm değerleri doğru bir şekilde işlediğini test etmelisiniz. [Uygulama yapılandırma ilkeleri](../apps/app-configuration-policies-overview.md) , Intune kullanılarak oluşturulabilir ve atanabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune için bir Android iş kolu uygulaması ekleyin](../apps/lob-apps-android.md).
