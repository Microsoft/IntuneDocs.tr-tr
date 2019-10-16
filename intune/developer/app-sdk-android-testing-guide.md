---
title: Android için uygulama SDK 'Sı test Kılavuzu Microsoft Intune
description: Android için Microsoft Intune uygulama SDK 'Sı test Kılavuzu, Intune ile yönetilen Android uygulamanızı test etmenize yardımcı olur.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
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
ms.openlocfilehash: 9a41d41464ace665301241a5962f59396a131107
ms.sourcegitcommit: 60ed93682a21860e9d99ba1592ede120477f2b4d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379788"
---
# <a name="microsoft-intune-app-sdk-for-android-testing-guide"></a>Android için uygulama SDK 'Sı test Kılavuzu Microsoft Intune

Bu kılavuz, geliştiricilerin Intune tarafından yönetilen Android uygulamalarını test etmesine yardımcı olur.  

## <a name="prerequisite-test-accounts"></a>Önkoşul test hesapları
Önceden oluşturulmuş verilerle veya olmadan yeni hesaplar oluşturabilirsiniz. Yeni bir hesap oluşturmak için:
1. [Microsoft gösterileri](https://demos.microsoft.com/environments/create/tenant) sitesine gidin. 
2. [Intune](../fundamentals/setup-steps.md) 'u mobil cihaz YÖNETIMI (MDM) etkinleştirecek şekilde ayarlayın.
3. [Kullanıcı oluşturun](../fundamentals/users-add.md).
4. [Grupları oluşturun](../fundamentals/groups-add.md).
5. Test testiniz için uygun şekilde [lisans atayın](../fundamentals/licenses-assign.md) .


## <a name="azure-portal-policy-configuration"></a>Azure portal ilkesi yapılandırması
[Azure Portal Intune dikey](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview)penceresinde [Uygulama koruma ilkeleri oluşturun ve atayın](../apps/app-protection-policies.md) . Ayrıca, Intune dikey penceresinde [uygulama yapılandırma ilkenizi](../apps/app-configuration-policies-overview.md) oluşturup atayabilirsiniz.

> [!NOTE]
> Uygulamanız Azure portal listelenmemişse, **diğer uygulamalar** seçeneğini belirleyerek ve metin kutusunda paket adını sağlayarak bu ilkeyi bir ilkeyle hedefleyebilirsiniz.

## <a name="test-cases"></a>Test çalışmaları

Aşağıdaki test çalışmaları yapılandırma ve onay adımları sağlar. Intune tarafından yönetilen Android uygulama sorunlarını gidermeye yardımcı olması için bu kılavuzu kullanın.

### <a name="required-pin-and-corporate-credentials"></a>Gerekli PIN ve şirket kimlik bilgileri

Şirket kaynaklarına erişmek için PIN 'ı zorunlu kılabilirsiniz. Ayrıca, kullanıcıların yönetilen uygulamaları kullanabilmesi için önce şirket kimlik doğrulamasını uygulayabilirsiniz. Şöyle yapılır:

1. **Erişim IÇIN PIN gerektir** ' i ayarlayın ve **Evet**' e **erişmek için kurumsal kimlik bilgileri gerektir** . Daha fazla bilgi için, bkz. [Microsoft Intune Android uygulama koruma ilkesi ayarları](../apps/app-protection-policy-settings-android.md#access-requirements).
2. Aşağıdaki koşulları onaylayın:
    - Uygulama başlatma, PIN girişi veya Şirket Portalı kayıt sırasında kullanılan üretim kullanıcısı için bir istem sunmalıdır.
    - Geçerli bir oturum açma istemi sunamaması, özellikle Azure Active Directory kimlik doğrulaması kitaplığı (ADAL) Tümleştirmesi (SkipBroker, ClientID ve Authority) için değerler olarak yanlış yapılandırılmış bir Android bildiriminin nedeni olabilir.
    - Herhangi bir istem sunma hatası yanlış tümleşik `MAMActivity` değerinden kaynaklanıyor olabilir. @No__t-0 hakkında daha fazla bilgi için bkz. [Android Için uygulama SDK 'sı geliştirici kılavuzu Microsoft Intune](app-sdk-android.md).

> [!NOTE] 
> Önceki test çalışmıyorsa, aşağıdaki testler de başarısız olur. [SDK](app-sdk-android.md##sdk-integration) ve [adal](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) tümleştirmesini gözden geçirin.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Diğer uygulamalarla veri aktarımını ve almayı kısıtlama
Kurumsal yönetilen uygulamalar arasında veri aktarımını şu şekilde denetleyebilirsiniz:

1. **Uygulamanın diğer uygulamalara veri aktarmasına Izin ver** **ilkesini ilkeyle yönetilen uygulamalar**olarak ayarlayın.
2. **Uygulamanın diğer uygulamalardan tüm uygulamalara veri almasına Izin ver** 'i ayarlayın. Amaç ve içerik sağlayıcılarının kullanımı, bu ilkelerden etkilenir.
3. Aşağıdaki koşulları onaylayın:
    - Yönetilmeyen bir uygulamadan uygulama işlevlerinizi doğru açma.
    - Yönetilen uygulamalar arasında içerik paylaşımına izin verilir.
    - Yönetilen uygulamalardan Yönetilemeyen uygulamalara (örneğin, Chrome) paylaşılması engellenir.

### <a name="restrict-cut-copy-and-paste"></a>Kesme, kopyalama ve yapıştırmayı kısıtla
Sistem panosunu yönetilen uygulamalarla kısıtlamak için aşağıdaki adımları kullanabilirsiniz:

1. **' In yapıştırma ile yönetilen ilkeye** **, diğer uygulamalarla kesme, kopyalama ve yapıştırmayı Kısıtla seçeneğini** belirleyin.
2. Aşağıdaki koşulları onaylayın:
    - Uygulamanızdan yönetilmeyen bir uygulamaya (örneğin, Iletiler) metin kopyalama engellenir.

### <a name="prevent-save"></a>Kaydetmeyi engelle
Farklı **Kaydet** işlevlerini aşağıdaki şekilde denetleyebilirsiniz:

1. Uygulamanız [Tümleşik farklı kaydet denetimleri](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted)gerektiriyorsa, **' farklı Kaydet '** seçeneğini **Evet**olarak belirleyin.
2. Aşağıdaki koşulları onaylayın:
    - Kaydet yalnızca uygun yönetilen konumlara kısıtlıdır.

### <a name="file-encryption"></a>Dosya şifreleme
Aygıttaki verileri aşağıdaki gibi şifreleyebilirsiniz:

1. **Uygulama verilerini şifreleyin** ' i **Evet**olarak ayarlayın.
2. Aşağıdaki koşulları onaylayın:
    - Normal uygulama davranışı etkilenmez.

### <a name="prevent-android-backups"></a>Android yedeklemelerini engelle
Uygulama yedeklemesini aşağıdaki şekilde kontrol edebilirsiniz:

1. [Tümleşik yedekleme kısıtlamaları](app-sdk-android.md#protecting-backup-data)ayarladıysanız, **Android yedeklemelerini** **Evet**olarak ayarlayın seçeneğini belirleyin.
2. Aşağıdaki koşulları onaylayın:
    - Yedeklemeler kısıtlıdır.

### <a name="unenrollment"></a>Kayıt kaldırmaya
Yönetilen uygulamaları, şirket e-posta ve belgelerinin bulunduğu bir şekilde uzaktan temizleyebilirsiniz ve artık yönetilmediğinde kişisel verilerin şifresi çözülür. Şöyle yapılır:

1. Azure portal, [silme](../apps/apps-selective-wipe.md)işlemi yapın.
2. Uygulamanız herhangi bir silme işleyicisine kaydolmazsa, aşağıdaki koşulları onaylayın:
    - Uygulamanın tam temizleme işlemi gerçekleşir.
3. Uygulamanız `WIPE_USER_DATA` veya `WIPE_USER_AUXILARY_DATA` için kaydedilmişse, aşağıdaki koşulları onaylayın:
    - Yönetilen içerik uygulamadan kaldırılır. Daha fazla bilgi için bkz. [Android Için Intune uygulama SDK 'sı Geliştirici Kılavuzu-seçmeli silme](app-sdk-android.md#selective-wipe).

### <a name="multi-identity-support"></a>Çoklu kimlik desteği
[Çoklu kimlik desteğini](app-sdk-android.md#multi-identity-optional) tümleştirme, kapsamlı bir şekilde test olması gereken yüksek riskli bir değişiklik. En yaygın sorunlar, kimlik (bağlam ve tehdit düzeyi) ve izleme dosyalarını (`MAMFileProtectionManager`) yanlış ayarlamadığı için oluşur.

En düşük düzeyde, aşağıdakileri onaylayın:

- **Farklı kaydet** ilkesi, Yönetilen kimlikler için doğru şekilde çalışıyor.
- Kopyalama ve yapıştırma kısıtlamaları, yönetilene doğru şekilde uygulanır.
- Yalnızca yönetilen kimliğe ait veriler şifrelenir ve kişisel dosyalar değiştirilmez.
- Kayıt kaldırma sırasında seçmeli Temizleme yalnızca yönetilen kimlik verilerini kaldırır.
- Yönetilmeyen bilgisayardan yönetilen bir hesaba (yalnızca ilk kez) değiştirirken kullanıcıdan koşullu başlatma yapması istenir.

### <a name="app-configuration-optional"></a>Uygulama yapılandırması (isteğe bağlı)
Yönetilen uygulamaların davranışını yapılandırabilirsiniz. Uygulamanız herhangi bir uygulama yapılandırma ayarını kullanıyorsa, uygulamanızın sizin (yönetici olarak) ayarlayabileceğiniz tüm değerleri doğru bir şekilde işlediğini test etmelisiniz. Intune 'da [uygulama yapılandırma ilkeleri](../apps/app-configuration-policies-overview.md) oluşturabilir ve atayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune Android iş kolu uygulaması ekleme](../apps/lob-apps-android.md)
