---
title: Microsoft Intune - Azure’daki yenilikler | Microsoft Docs
titleSuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 45f816a8fb42068398afea912525d9ccb7ec98fe
ms.sourcegitcommit: 42183c87b137710b8529049f8710d47127e99900
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75303062"
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler

Microsoft Intune’daki haftalık yenilikleri öğrenin. Ayrıca, [önemli bildirimler](#notices), [Geçmiş yayınlar](whats-new-archive.md)ve [Intune hizmet güncelleştirmelerinin nasıl yayımlandığına](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728)ilişkin bilgileri de bulabilirsiniz. 

> [!Note]
> Her [aylık güncelleştirmenin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) piyasaya çıkma üç güne kadar sürebilir ve şu sırada olacaktır:
>
> - Gün 1: Asya Pasifik (APAC)
> - Gün 2: Avrupa, Orta Doğu, Afrika (EMEA)
> - Gün 3: Kuzey Amerika
>
> Bazı özelliklerin piyasaya çıkması birkaç haftayı bulabilir ve tüm özellikler ilk hafta bütün müşterilerimize sunulmamış olabilir.
>
> Bir sürümdeki yaklaşan özelliklerin bir listesi için [geliştirme sayfasını](in-development.md) inceleyin.

**RSS akışı**: aşağıdaki URL 'yi kopyalayıp akış okuyucunuzun içine yapıştırarak Bu sayfa güncelleştirildikten sonra bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control
-->  


<!-- ########################## -->
## <a name="week-of-december-9-2019-1912-service-release"></a>9 Aralık 2019 (1912 hizmet sürümü) haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi

#### <a name="migrating-to-microsoft-edge-for-managed-browsing-scenarios---5173762---"></a>Yönetilen gözatma senaryolarında Microsoft Edge 'e geçiş<!-- 5173762 -->
Intune Managed Browser emekliliğe yaklaşarak, kullanıcılarınızı uçtan uca taşımak için gereken adımları basitleştirmek amacıyla uygulama koruma ilkelerinde değişiklikler yaptık. Uygulama koruma ilkesi ayarı, **diğer uygulamalarla Web içeriği aktarımını kısıtla** seçeneklerini, aşağıdakilerden biri olacak şekilde güncelleştirdik:

- Herhangi bir uygulama
- Intune Yönetilen Tarayıcı
- Microsoft Edge
- Yönetilmeyen tarayıcı 

**Microsoft Edge**' i seçtiğinizde, son kullanıcılarınız Microsoft Edge 'in yönetilen gözatma senaryolarında gerekli olduğunu bildiren koşullu erişim mesajlaşmasını görür. Henüz yapmadıysanız, bu kullanıcıların AAD hesaplarıyla Microsoft Edge 'i indirmesi ve oturum açması istenir.  Bu, MAM özellikli uygulamalarınızı, uygulama yapılandırma ayarıyla `com.microsoft.intune.useEdge` **true**olarak ayarlanmış şekilde hedefleyen bir değer olacaktır. **İlke ile yönetilen tarayıcılar** ayarının kullanıldığı mevcut uygulama koruma ilkeleri artık **Intune Managed Browser** seçili olacak ve davranışta hiçbir değişiklik görmez. Bu, **useedge** uygulama yapılandırma ayarını **doğru**olarak ayarladıysanız kullanıcılarınızın Microsoft Edge 'i kullanmak için mesajlaşma göreceği anlamına gelir. Yönetilen gözatma senaryolarından yararlanan tüm müşterilerin, Microsoft Edge 'e geçiş yapmak için uygun Kılavuzu görmesini sağlamak üzere, kullanıcıların bağlantıları hangi uygulamadan başlatdıklarından emin olmak için, uygulama koruma ilkelerini **diğer uygulamalarla kısıtla** . 

#### <a name="configure-app-notification-content-for-organization-accounts---2576686----"></a>Kuruluş hesapları için uygulama bildirim içeriğini yapılandırma<!-- 2576686  -->
Android ve iOS cihazlarında Intune uygulama koruma ilkeleri (uygulama), kuruluş hesapları için uygulama bildirim içeriğini denetlemenize olanak tanır. Seçili uygulama için kuruluş hesaplarına yönelik bildirimlerin nasıl gösterileceğini belirtmek için bir seçenek (Izin ver, kuruluş verilerini engelle veya engellendi) seçeneğini belirleyebilirsiniz. Bu özellik, uygulamalardan destek gerektirir ve UYGULAMANıN etkinleştirildiği tüm uygulamalar için kullanılamayabilir. İOS için Outlook sürüm 4.15.0 (veya üzeri) ve Outlook for Android 4.83.0 (veya üzeri), bu ayarı destekler. Ayar konsolunda mevcuttur, ancak işlevsellik 16 Aralık 2019 ' den sonra devreye girer. UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](../apps/app-protection-policy.md).

#### <a name="microsoft-app-icons-update--4677605----"></a>Microsoft uygulama simgeleri güncelleştirmesi<!--4677605  -->
Uygulama koruma ilkeleri ve uygulama yapılandırma ilkeleri için uygulama hedefleme bölmesinde Microsoft uygulamaları için kullanılan simgeler güncelleştirilmiştir.

#### <a name="require-use-of-approved-keyboards-on-android--4761794----"></a>Android üzerinde onaylanan Klavye kullanımını gerektir<!--4761794  -->
Uygulama koruma ilkesinin bir parçası olarak, yönetilen Android uygulamalarıyla hangi Android klavyeleri kullanılabileceğini yönetmek için [**onaylanan klavyeler**](../apps/app-protection-policy-settings-android.md#data-protection) ayarını belirtebilirsiniz. Bir Kullanıcı yönetilen uygulamayı açtığında ve bu uygulama için henüz onaylanmış bir klavye kullanmıyorsa, bu kullanıcılara cihazlarında zaten yüklü olan onaylanmış klavyelerin birine geçiş yapması istenir. Gerekirse, bunlar tarafından yüklenip ayarlanabilecek Google Play Store onaylanan bir klavyeyi indirmek için bir bağlantı sunulur. Kullanıcı, yönetilen bir uygulamadaki metin alanlarını, etkin klavyesi onaylanan klavyelerin biri olmadığında düzenleyebilir.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578----"></a>İOS, ıpados ve macOS cihazlarınızdaki uygulamalar ve Web siteleri için çoklu oturum açma deneyimi güncelleştirildi<!-- 4999578  -->
Intune, iOS, ıpados ve macOS cihazları için daha fazla çoklu oturum açma (SSO) ayarı ekledi. Artık kuruluşunuz tarafından veya kimlik sağlayıcınız tarafından yazılmış yeniden yönlendirme SSO uygulaması uzantılarını yapılandırabilirsiniz. OAuth ve SAML2 gibi modern kimlik doğrulama yöntemlerini kullanan uygulamalar ve Web siteleri için sorunsuz bir çoklu oturum açma deneyimi yapılandırmak üzere bu ayarları kullanın. 

Bu yeni ayarlar, SSO uygulama uzantıları ve Apple 'ın yerleşik Kerberos uzantısı için önceki ayarlarda (**cihazlar** > **cihaz yapılandırma** > **profillerinin** > profil **oluşturma** > **iOS/ıpados** veya **MacOS** ' u, profil türü için > **cihaz özellikleri** ) genişletir. 

Yapılandırabileceğiniz SSO uygulama uzantısı ayarlarının tam aralığını görmek için, [macOS 'Ta](../configuration/macos-device-features-settings.md#single-sign-on-app-extension)IOS ve SSO ['daki SSO](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) ' ya gidin.

Uygulama hedefi:
- iOS/ıpados
- Mac OS

#### <a name="weve-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352-wnready-----"></a>İOS ve ıpados cihazları için iki cihaz kısıtlama ayarı güncelleştirdik ve davranışlarını düzeltir<!-- 5701352 WNReady   -->
İOS cihazlarında, **Kablosuz PKI güncelleştirmelerine izin** veren cihaz kısıtlama profilleri OLUŞTURABILIR ve **USB kısıtlı modunu** (**cihazlar** > **cihaz yapılandırma** > **profilleri** için > **profil oluşturma** > **iOS/ıpados** ' ı profil türü için iOS > **cihaz kısıtlamalarına** göre engeller). Bu sürümden önce, aşağıdaki ayarlar için Kullanıcı arabirimi ayarları ve açıklamaları hatalıydı ve şimdi düzeltildi. Bu sürümden itibaren, ayarlar davranışı aşağıdaki gibidir:

**Kablosuz PKI güncelleştirmelerini engelle**: **blok** , cihazın bir bilgisayara bağlı olmadığı durumlar dışında yazılım güncelleştirmelerini almasını engeller. **Yapılandırılmadı** (varsayılan): bir cihazın bir bilgisayara bağlı olmadan yazılım güncelleştirmelerini almasına izin verir.
- Daha önce, bu ayar, kullanıcılarınızın cihazlarını bir bilgisayara bağlamadan yazılım güncelleştirmeleri almasına Izin veren: **Izin ver**olarak yapılandırmanızı sağlar.
**Cihaz KILITLIYKEN USB donatılara Izin ver**: **ızın ver** , USB aksesuarları 'nin bir saatten daha fazla kilitlenmiş bir cihazla veri alışverişi yapmasına olanak sağlar. **Yapılandırılmamış** (varsayılan), USB kısıtlı modunu cihazda güncelleştirmez ve USB aksesuarları bir saatten daha fazla kilitleniyorsa cihazdan veri aktarımını engellenecektir.
- Bu ayar daha önce bu ayarı olarak yapılandırmanızı sağlar: denetimli cihazlarda USB kısıtlı modunu devre dışı bırakmayı **engeller** .

Yapılandırabileceğiniz ayar hakkında daha fazla bilgi için bkz. [iOS ve ıpados cihaz ayarları Intune kullanarak özellikleri izin vermek veya kısıtlamak için](../configuration/device-restrictions-ios.md).

Bu özellik şu platformlarda geçerlidir:
- OS/ıpados

#### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>MacOS cihazları için kablolu ağ cihaz yapılandırma profilleri<!-- 3508686  -->
   > [!NOTE]
   > Bu özellik gecikti, ancak yakında yayımlanacak.

#### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998---"></a>Kullanıcıların, Android kurumsal cihaz sahibi cihazlarda yönetilen anahtar deposunda sertifika kimlik bilgilerini yapılandırmalarını engelleyin<!-- 3311998 -->
Android kurumsal cihaz sahibi cihazlarda, kullanıcıların yönetilen anahtar deposunda (**cihaz yapılandırma** > **profiller** ** > sertifika** kimlik bilgilerini yapılandırmalarını engelleyen yeni bir ayar yapılandırabilirsiniz. > **Android Enterprise** for platform > cihaz sahibi yalnızca profil türü > **Kullanıcılar + hesaplar**) için **cihaz kısıtlamalarını >** .

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="protected-wipe-action-now-available--51150000---"></a>Korumalı silme eylemi şimdi kullanılabilir<!--51150000 -->
Artık bir cihazın korumalı silme işlemini gerçekleştirmek için cihazı silme eylemini kullanma seçeneğiniz vardır. Korumalı wpes 'ler, standart wpes ile aynıdır, ancak cihaz kapatılanarak bu dosyalar atlatılabilir. Korumalı silme işlemi başarılı olana kadar cihazı sıfırlamaya çalışmaya devam edecektir. Bazı yapılandırmalarda bu eylem cihazın yeniden başlatılamamasından çıkamayabilir. Daha fazla bilgi için bkz. [cihazları devre dışı bırakma veya silme](../remote-actions/devices-wipe.md).

#### <a name="device-ethernet-mac-address-added-to-devices-overview-page--5562275---"></a>Cihazın genel bakış sayfasına eklenen cihaz Ethernet MAC adresi<!--5562275 -->
Artık cihaz ayrıntıları sayfasında bir cihazın Ethernet MAC adresini görebilirsiniz (**cihazlar > aygıtlar** > bir cihaz seçin **** > **genel bakış**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Cihaz güvenliği

#### <a name="improved-experience-on-a-shared-device-when-device-based-conditional-access-policies-are-enabled---1734096----"></a>Cihaz tabanlı koşullu erişim ilkeleri etkinken paylaşılan bir cihazda geliştirilmiş deneyim<!-- 1734096  -->
İlke zorlarken Kullanıcı için en son uyumluluk değerlendirmesini denetleyerek, cihaz tabanlı koşullu erişim ilkesiyle hedeflenen birden fazla kullanıcıyla paylaşılan bir cihazda deneyim geliştirdik. Daha fazla bilgi için aşağıdaki genel bakış makalelerine bakın:
- [Koşullu erişim için Azure genel bakış](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Intune cihaz uyumluluğuna genel bakış](../protect/device-compliance-get-started.md)

#### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529----"></a>Sertifikalar ile cihaz sağlamak için PKCS sertifika profillerini kullanma<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529  -->
Artık, Wi-Fi ve VPN için olanlar gibi profillerle ilişkilendirildiğinde, Android for Work, iOS ve Windows çalıştıran *cihazlara* sertifika vermek için PKCS sertifika profillerini kullanabilirsiniz. Daha önce bu üç platform yalnızca Kullanıcı tabanlı sertifikaları desteklemekte ve cihaz tabanlı destek, macOS ile sınırlandırılmıştır.

Cihaz tabanlı bir sertifika kullanmak için, desteklenen platformlar için [PKCS sertifika profili oluştururken](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) **Ayarlar**' ı seçin. Artık, cihaz veya Kullanıcı seçeneklerini destekleyen **sertifika türü**ayarını görürsünüz.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="centralized-audit-logs--5603185-5697164---"></a>Merkezi denetim günlükleri<!--5603185, 5697164 -->
Yeni bir merkezi denetim günlüğü deneyimi artık tüm kategoriler için Denetim günlüklerini tek bir sayfada toplar. Aradığınız verileri almak için günlüklere filtre uygulayabilirsiniz. Denetim günlüklerini görmek için, **kiracı yönetimi** > **Denetim günlükleri**' ne gidin. 

#### <a name="scope-tag-information-included-in-audit-log-activity-details--5763534---"></a>Denetim günlüğü etkinlik ayrıntılarına dahil edilen kapsam etiketi bilgileri<!--5763534 -->
Denetim günlüğü etkinlik ayrıntıları artık kapsam etiketi bilgilerini içerir (kapsam etiketlerini destekleyen Intune nesneleri için). Denetim günlükleri hakkında daha fazla bilgi için bkz. [olayları izlemek ve izlemek için Denetim günlüklerini kullanma](monitor-audit-logs.md).


<!-- ########################## -->
## <a name="week-of-december-2-2019"></a>2 Aralık 2019 haftası

#### <a name="new-microsoft-endpoint-configuration-manager-co-management-licensing--5027281--"></a>Yeni Microsoft uç noktası Configuration Manager ortak yönetim lisansı<!--5027281-->
Yazılım Güvencesi kapsamındaki müşterilerin, ortak yönetim için ek bir Intune lisansı satın almak zorunda kalmadan Windows 10 bilgisayarları için Intune ortak yönetimine sahip Configuration Manager olanak sağlayan yeni bir lisans kullanıma sunulmuştur. Müşteriler, Windows 10 ' un ortak yönetimi için son kullanıcılarına ayrı Intune/EMS lisansları atamaya gerek kalmaz.
- Configuration Manager tarafından yönetilen ve ortak yönetime kaydedilen cihazlar, Intune tek başına MDM ile yönetilen bilgisayarlar ile neredeyse aynı haklara sahiptir. Ancak, sıfırlandıktan sonra Autopilot kullanılarak yeniden sağlanamazlar.
- Diğer yollarla Intune 'a kayıtlı Windows 10 cihazları tam Intune lisansları gerektirir.
- Diğer platformlardaki cihazlarda hala tam Intune lisansları gerekir.

Daha fazla bilgi için bkz. [Lisans koşulları](https://www.microsoft.com/en-us/Licensing/product-licensing/products).


<!-- ########################## -->
## <a name="week-of-november-18-2019-1911-service-release"></a>18 Kasım 2019 (1911 hizmet sürümü) haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi

#### <a name="smime-support-with-microsoft-outlook-for-ios---2669398----"></a>İOS için Microsoft Outlook ile S/MIME desteği<!-- 2669398  -->

   > [!NOTE]
   > Bu özellik gecikti, ancak yakında yayımlanacak.



#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Uygulama verilerini seçmeli olarak silme sırasında kullanıcı arabirimi güncelleştirmesi<!-- 4102028 -->
Intune 'da uygulama verilerini seçmeli olarak silme Kullanıcı arabirimi güncelleştirilmiştir. UI değişiklikleri şunları içerir:
- Bir bölme içinde bir sihirbaz stili biçim kullanarak basitleştirilmiş bir deneyim.
- Atamaları eklemek için akış oluşturma için bir güncelleştirme.
- Yeni bir ilke oluşturmadan veya bir özellik düzenlenirken önce özellikleri görüntülerken ayarlanan tüm öğelerin özetlenen sayfası. Ayrıca, Özellikler düzenlenirken, Özet yalnızca düzenlenmekte olan özellikler kategorisinden öğe listesini gösterir.

Daha fazla bilgi için bkz. [Intune tarafından yönetilen uygulamalardan kurumsal verileri temizleme](~/apps/apps-selective-wipe.md).

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>iOS ve ıpados üçüncü taraf klavye desteği<!-- 4922950 -->
Mart 2019 ' de, "üçüncü taraf klavyeleri" iOS uygulama koruma ilkesi ayarı için desteğin kaldırıldığını duyurduk. Bu özellik hem iOS hem de ıpados desteğiyle Intune 'a döndürülüyor. Bu ayarı etkinleştirmek için, yeni veya mevcut bir iOS/ıpados uygulama koruma ilkesinin **veri koruma** sekmesini ziyaret edin ve **veri aktarımı**altında **üçüncü taraf klavyeler** ayarını bulun.

Bu ilke ayarının davranışı, önceki uygulamadan biraz farklılık gösterir. SDK sürüm 12.0.16 ve üstünü kullanan çoklu kimlik uygulamalarında, bu ayar **engellenecek**şekilde yapılandırılmış olan uygulama koruma ilkeleri tarafından hedeflenirse, son kullanıcılar hem kuruluşlarındaki hem de kişisel hesaplarındaki üçüncü taraf klavyeleri kabul etmeyecektir. SDK 12.0.12 ve önceki sürümlerini kullanan uygulamalar, blog gönderdiğimiz başlığında belgelenen davranışı göstermeye devam edecektir, [bilinen sorun: üçüncü taraf klavyeleri, kişisel hesaplar Için iOS 'ta engellenmiyor](https://aka.ms/3rdparty_iOS_Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>JAMF yönetimini gerektirecek macOS Kullanıcı gruplarını hedefleme<!-- 4061739  --> 
[JAMF tarafından yönetilen MacOS cihazlarını](../protect/conditional-access-integrate-jamf.md)alacak belirli kullanıcı gruplarını hedefleyebilirsiniz. Bu, diğer cihazlar Intune tarafından yönetilirken, JAMF uyumluluk tümleştirmesini macOS cihazlarının bir alt kümesine uygulamanızı sağlar. JAMF tümleştirmesini zaten kullanıyorsanız, tüm kullanıcılar tümleştirme için varsayılan olarak hedeflenmeyecektir.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>İOS cihazlarında e-posta cihaz yapılandırma profili oluştururken yeni Exchange ActiveSync ayarları<!-- 4892824   --> 
İOS/ıpados cihazlarında, bir cihaz yapılandırma profilinde e-posta bağlantısını yapılandırabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil **oluşturmak** > için **IOS/ıpados** > profil türü **e-postası** ). 

Aşağıdakiler dahil olmak üzere kullanılabilir yeni Exchange ActiveSync ayarları vardır:
- **Eşitlenecek Exchange verileri**: Takvim, kişiler, anımsatıcılar, notlar ve e-posta Için eşitlenecek Exchange hizmetlerini seçin (veya eşitlemeyi engelleyin).
- **Kullanıcıların eşitleme ayarlarını değiştirmesine Izin ver**: kullanıcıların cihazlarında bu hizmetler için eşitleme ayarlarını değiştirmesine izin ver (veya engelle).  

Bu ayar hakkında daha fazla bilgi için, [Intune 'Da iOS cihazları Için e-posta profili ayarları](../configuration/email-settings-ios.md)' na gidin. 

Uygulama hedefi:
- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri

#### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-fully-managed-and-dedicated-devices---5353228-----"></a>Kullanıcıların Android kurumsal tam olarak yönetilen ve adanmış cihazlara kişisel Google hesapları eklemesini engelleyin<!-- 5353228   -->
Android kurumsal tam yönetilen ve adanmış cihazlarda, kullanıcıların kişisel Google hesapları > **oluşturmalarına** engel olan yeni bir ayar vardır (**cihaz yapılandırma** > **profilleri** > bir cihaz sahibi > yalnızca **Kullanıcı ve hesap ayarları** > **kişisel Google hesapları** **) için** **cihaz kısıtlamaları** >.

Yapılandırabileceğiniz ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi:
- Android kurumsal tam yönetilen cihazlar
- Android kurumsal adanmış cihazlar

#### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-iosipados-device-restrictions-profile----5468501-----"></a>Siri komutları ayarı için sunucu tarafı günlüğü, iOS/ıpados cihaz kısıtlamaları profilinde kaldırılır <!-- 5468501   -->
İOS ve ıpados cihazlarında, **Siri Için sunucu tarafı günlük kaydı** , Microsoft Endpoint Manager Yönetici konsolundan (**cihaz yapılandırma** > **profilleri** > profil **oluşturma** > **iOS/ıpados** > **cihaz kısıtlamaları** > **yerleşik uygulamalar**) kaldırılır. 

Bu ayarın cihazlar üzerinde hiçbir etkisi yoktur. Bu ayarı mevcut profillerden kaldırmak için, profili açın, tüm değişiklikleri yapın ve ardından profili kaydedin. Profil güncelleştirilir ve ayar cihazlardan silinir.

Yapılandırabileceğiniz tüm ayarları görmek için [iOS ve ıpados cihaz ayarları ' na bakın ve Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama hedefi:
- iOS/ıpados

#### <a name="windows-10-feature-updates-public-preview---2384877---"></a>Windows 10 özellik güncelleştirmeleri (Genel Önizleme)<!-- 2384877 -->
Windows 10 [özellik güncelleştirmelerini](../protect/windows-update-for-business-configure.md#windows-10-feature-updates) artık Windows 10 cihazlara dağıtabilirsiniz. Windows 10 özellik güncelleştirmeleri, cihazların yüklenmesini ve devam etmek istediğiniz Windows 10 sürümünü ayarlayan yeni bir yazılım güncelleştirme ilkesidir. Bu yeni ilke türünü, mevcut Windows 10 güncelleştirme halkalarınızla birlikte kullanabilirsiniz.

Windows 10 özellik güncelleştirmeleri ilkesini alan cihazlar Windows 'un belirtilen sürümünü yükler ve ardından ilke düzenlenene veya kaldırılana kadar o sürümde kalır. Windows 'un daha sonraki bir sürümünü çalıştıran cihazlar güncel sürümlerinde kalır. Windows 'un belirli bir sürümünde tutulan cihazlar, Windows 10 güncelleştirme halkalarından bu sürüm için kalite ve güvenlik güncelleştirmeleri yüklemeye devam edebilir.

Bu yeni ilke türü bu hafta kiracılar için kullanıma sunulmaya başlar. Bu ilke henüz kiracınızda yoksa, yakında olacaktır.

#### <a name="add-and-change-key-information-in-plist-files-for-macos-applications---4736278---"></a>MacOS uygulamaları için plist dosyalarında anahtar bilgilerini ekleme ve değiştirme<!-- 4736278 -->
MacOS cihazlarında artık, bir uygulamayla veya cihazla ilişkili bir özellik listesi**dosyasını (.** plist) karşıya yükleyen bir cihaz yapılandırma profili oluşturabilirsiniz (Platform > için SDK > **yapılandırma profilleri** > profil **oluşturma** > **MacOS** profil türü için bir **tercih dosyası** ).

Yalnızca bazı uygulamalar yönetilen tercihleri destekler ve bu uygulamalar tüm ayarları yönetmenize izin vermiyor. Kullanıcı kanalı ayarlarını değil cihaz kanalı ayarlarını yapılandıran bir özellik listesi dosyasını karşıya yüklediğinizden emin olun.

Bu özellik hakkında daha fazla bilgi için, bkz. [Microsoft Intune kullanarak macOS cihazlarına özellik listesi dosyası ekleme](../configuration/preference-file-settings-macos.md).

Uygulama hedefi:
- 10,7 ve daha yeni çalıştıran macOS cihazları

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="edit-device-name-value-for-autopilot-devices---2640074---"></a>Autopilot cihazlar için cihaz adı değerini Düzenle<!-- 2640074 -->
Azure AD 'ye katılmış Autopilot cihazları için cihaz adı değerini düzenleyebilirsiniz.  Daha fazla bilgi için bkz. [Autopilot cihaz özniteliklerini düzenleme](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

#### <a name="edit-group-tag-value-for-autopilot-devices---4816775-----"></a>Autopilot cihazlar için Grup etiketi değerini Düzenle<!-- 4816775   -->
Autopilot cihazlar için Grup etiketi değerini düzenleyebilirsiniz. Daha fazla bilgi için bkz. [Autopilot cihaz özniteliklerini düzenleme](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="updated-support-experience---5012398---"></a>Güncelleştirilmiş destek deneyimi<!-- 5012398 -->

Bugünden itibaren, [Intune 'a yönelik yardım ve destek almak](get-support.md) için güncelleştirilmiş ve kolaylaştırılmış bir konsol deneyimi kiracılara gönderilir. Henüz bu yeni deneyim yoksa, yakında sunulacaktır.

Genel sorunlar ve destek ile iletişim kurmak için kullandığınız iş akışı için konsol içi arama ve geri bildirim geliştirdik. Bir destek sorunu açarken, bir geri çağırma veya e-posta yanıtı beklendiğinde gerçek zamanlı tahminleri görürsünüz ve Premier ve Birleşik destek müşterileri, daha hızlı destek almaya yardımcı olmak için kendi sorunları için kolayca önem derecesi belirtebilir.

#### <a name="improved-intune-reporting-experience-public-preview----3791418---"></a>İyileştirilmiş Intune raporlama deneyimi (Genel Önizleme) <!-- 3791418 -->
Intune artık yeni rapor türleri, daha iyi rapor organizasyonu, daha odaklanmış görünümler, geliştirilmiş rapor işlevselliği ve daha tutarlı ve zamanında veriler de dahil olmak üzere gelişmiş bir raporlama deneyimi sunmaktadır. Yeni rapor türleri aşağıdakilere odaklanılmıştır:
- **İşletimsel** -negatif bir sistem durumu odaklı yeni kayıtlar sağlar. 
- **Kuruluş** -genel durumun daha geniş bir özetini sağlar.
- **Geçmiş** -bir süre boyunca desenler ve eğilimler sağlar.
- **Uzman** -kendi özel raporlarınızı oluşturmak için ham verileri kullanmanıza olanak sağlar.

Yeni raporların ilk kümesi cihaz uyumluluğuna odaklanır. Daha fazla bilgi için bkz. [blog-Microsoft Intune raporlama çerçevesi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) ve [Intune raporları](~/fundamentals/reports.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="duplicate-custom-or-built-in-roles----1081938-----"></a>Yinelenen özel veya yerleşik roller <!-- 1081938   -->
Artık yerleşik ve özel rolleri kopyalayabilirsiniz. Daha fazla bilgi için bkz. [rolü kopyalama](../fundamentals/create-custom-role.md#copy-a-role).

#### <a name="new-permissions-for-school-administrator-role----5621805----"></a>Okul Yöneticisi rolü için yeni izinler <!-- 5621805  -->  
İki yeni izin, **profil** ve **eşitleme cihazı** ata, **kayıt programları** > **okul yöneticisi rolüne eklenmiştir**. Eşitleme profili izni, grup yöneticilerinin Windows Autopilot cihazlarını eşitlemesini sağlar. Profil atama izni, kullanıcıların başlattığı Apple kayıt profillerini silmesine izin verir. Ayrıca, Autopilot cihaz atamalarını ve Autopilot dağıtım profili atamalarını yönetme izni verir. Tüm okul yöneticisi/Grup Yöneticisi izinlerinin listesi için bkz. [Grup yöneticileri atama](https://docs.microsoft.com/intune-education/group-admin-delegate). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="security"></a>Güvenlik

#### <a name="bitlocker-key-rotation---2564951----"></a>BitLocker anahtar döndürme<!-- 2564951  -->
Windows sürüm 1909 veya üstünü çalıştıran yönetilen cihazlar için [BitLocker kurtarma anahtarlarını uzaktan döndürmek](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) üzere bir Intune cihaz eylemi kullanabilirsiniz. Kurtarma anahtarlarının döndürülmeyeceğini nitelemek için cihazların kurtarma anahtarı döndürmesini destekleyecek şekilde yapılandırılması gerekir.  

#### <a name="updates-to-dedicated-device-enrollment-to-support-scep-device-certificate-deployment----5198878----"></a>SCEP cihaz sertifikası dağıtımını desteklemek için adanmış cihaz kaydına yönelik güncelleştirmeler <!-- 5198878  -->
Intune artık, Wi-Fi profillerine sertifika tabanlı erişim için Android kurumsal adanmış cihazlara SCEP cihaz sertifikası dağıtımını desteklemektedir. Dağıtımın çalışması için cihazda Microsoft Intune uygulamanın mevcut olması gerekir. Sonuç olarak, Android kurumsal adanmış cihazlara yönelik kayıt deneyimini güncelleştirdik. Yeni kayıtlar yine de aynı (QR, NFC, sıfır-Touch veya cihaz tanımlayıcısı ile) hala başlatılır, ancak artık kullanıcıların Intune uygulamasını yüklemesini gerektiren bir adım vardır. Mevcut cihazlar, uygulamayı düzenli olarak otomatik olarak yüklenecek şekilde başlatacak.

#### <a name="intune-audit-logs-for-business-to-business-collaboration--5670211---"></a>İşletmeden işletmeye işbirliği için Intune denetim günlükleri<!--5670211 -->
İşletmeden işletmeye (B2B) işbirliği, şirketinizin uygulamalarını ve hizmetlerini başka bir kuruluştan Konuk kullanıcılarla güvenli bir şekilde paylaşmanızı sağlarken kendi şirket verileriniz üzerinde denetim sağlar. Intune artık B2B Konuk kullanıcıları için Denetim günlüklerini desteklemektedir. Örneğin, Konuk kullanıcılar değişiklik yaparken, Intune bu verileri denetim günlükleri aracılığıyla yakalayabilir. Daha fazla bilgi için bkz. [Azure ACTIVE DIRECTORY B2B 'de Konuk Kullanıcı erişimi nedir?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)


<!-- ########################## -->
## <a name="week-of-november-11-2019"></a>11 Kasım 2019 haftası  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi  

#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Şirket Portalı 'de geliştirilmiş macOS kayıt deneyimi <!-- 5074349  -->  
MacOS kayıt deneyiminin Şirket Portalı, iOS kayıt deneyimi için Şirket Portalı daha yakından hizalanan daha basit bir kayıt işlemine sahiptir. Cihaz kullanıcıları şimdi şunları görür:  

* Bir uyleyici Kullanıcı arabirimi.  
* İyileştirilmiş bir kayıt denetim listesi.  
* Cihazlarını nasıl kaydedebileceğinize ilişkin daha net yönergeler.  
* Gelişmiş sorun giderme seçenekleri.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Windows Şirket Portalı uygulamasından başlatılan web uygulamaları<!-- 5030972 -->
Son kullanıcılar artık doğrudan Windows Şirket Portalı uygulamasından Web uygulamaları başlatabilir. Son kullanıcılar Web uygulamasını seçip **tarayıcıda aç**seçeneğini belirleyebilir. Yayınlanan Web URL 'SI doğrudan bir Web tarayıcısında açılır. Bu işlevsellik bir sonraki hafta boyunca alınacaktır. Web Apps hakkında daha fazla bilgi için bkz. [Microsoft Intune Web Apps ekleme](~/apps/web-app.md).  


#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950----"></a>Windows 10 için Şirket Portalı yeni atama türü sütunu <!-- 5459950  -->
Şirket Portalı > **yüklü uygulamalar** > **atama türü** sütunu, **kuruluşunuzun gerektirdiği**şekilde yeniden adlandırıldı.  Bu sütunda, kullanıcılar bir uygulamanın gerekli olduğunu ya da kuruluşlarına göre isteğe bağlı olduğunu göstermek için **Evet** veya **Hayır** değeri görür. Cihaz kullanıcıları kullanılabilir uygulamalar kavramı hakkında karışdığı için bu değişiklikler yapılmıştır. Kullanıcılarınız, [cihazınızdaki uygulamaları yükleme ve paylaşma](/intune-user-help/install-apps-cpapp-windows)konusundaki Şirket portalı uygulamaları yükleme hakkında daha fazla bilgi bulabilir. Kullanıcılarınız için Şirket Portalı uygulamasını yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](~/apps/company-portal-app.md).  

<!-- ########################## -->
## <a name="week-of-november-4-2019"></a>4 Kasım 2019 haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Cihaz güvenliği

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>Güvenlik temelleri Microsoft Azure Kamu destekleniyor<!-- 4062552 -->

*Microsoft Azure Kamu* barındırılan Intune örnekleri artık kullanıcılarınızın ve cihazlarınızın güvenliğini sağlamanıza ve korumanıza yardımcı olan [güvenlik temellerini](../protect/security-baselines.md) kullanabilir.

<!-- ########################## -->
## <a name="week-of-october-28-2019"></a>28 Ekim 2019 haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Android için Şirket Portalı App 'te geliştirilmiş denetim listesi tasarımı<!-- 5550857 -->  
Android için Şirket Portalı uygulamasındaki kurulum denetim listesi, hafif bir tasarım ve yeni simgelerle güncelleştirilmiştir. Değişiklikler, iOS için Şirket Portalı uygulamasına yapılan son güncelleştirmelerle birlikte hizalanır. Değişikliklerin yan yana karşılaştırması için bkz. [uygulama kullanıcı arabirimindeki](whats-new-app-ui.md)yenilikler. Güncelleştirilmiş kayıt adımlarına bakmak için bkz. [Android iş profiline kaydolma](/intune-user-help/enroll-device-android-work-profile) ve [Android cihazınızı kaydetme](/intune-user-help/enroll-device-android-company-portal).  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Windows 10 S modundaki cihazlarda Win32 uygulamaları<!-- 3747604 --> 
Windows 10 S modunda yönetilen cihazlara Win32 uygulamaları yükleyebilir ve çalıştırabilirsiniz. Bunu yapmak için, Windows Defender uygulama denetimi (WDAC) PowerShell araçlarını kullanarak S modu için bir veya daha fazla ek ilke oluşturabilirsiniz. Ek ilkeleri Device Guard Imzalama portalı ile imzalayın ve ardından Intune aracılığıyla ilkeleri karşıya yükleyin ve dağıtın. Intune 'da, bu özelliği **Windows 10 S ek ilkeleri** > **istemci uygulamaları** ' nı seçerek bulacaksınız. Daha fazla bilgi için bkz. [S modundaki cihazlarda Win32 uygulamalarını etkinleştirme](~/apps/apps-win32-s-mode.md).

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>Bir tarih ve saate göre Win32 uygulama kullanılabilirliğini ayarlama<!-- 3510685 -->
Yönetici olarak, gerekli bir Win32 uygulaması için başlangıç saatini ve son tarih saatini yapılandırabilirsiniz. Başlangıç zamanında, Intune yönetim uzantısı uygulama içeriğini indirmeyi başlatacak ve önbelleğe alacak. Uygulama son tarihte yüklenecektir. Kullanılabilir uygulamalar için, uygulama Şirket Portalı görünür olduğunda başlangıç zamanı görüntülenir. Daha fazla bilgi için bkz. [Intune Win32 uygulama yönetimi](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Win32 uygulama yüklemesi sonrasında yetkisiz kullanım süresi temelinde cihaz yeniden başlatması iste<!-- 3136567 -->
Bir Win32 uygulaması başarıyla yüklendikten sonra cihazın yeniden başlatılmasını zorunlu kılabilirsiniz. Daha fazla bilgi için bkz. [Win32 uygulama yönetimi-uygulama yükleme ayrıntılarını yapılandırma](~/apps/apps-win32-app-management.md#step-4-configure-app-installation-details).

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>İOS Şirket Portalı için koyu mod<!-- 4911422 -->
İOS Şirket Portalı için koyu mod kullanılabilir. Kullanıcılar şirket uygulamalarını indirebilir, cihazlarını yönetebilir ve cihaz ayarlarına bağlı olarak tercih ettikleri renk düzeninde BT desteği alabilir. İOS Şirket Portalı, son kullanıcının cihaz ayarlarını koyu veya hafif modda otomatik olarak eşleştirecektir. Daha fazla bilgi için bkz. [iOS için Microsoft Intune şirket portalı üzerinde koyu moda giriş](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453). İOS Şirket Portalı hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>Android Şirket Portalı En düşük uygulama sürümünü zorunlu<!-- 2378776 -->
Bir uygulama koruma ilkesinin **Min Şirket portalı sürümü** ayarını kullanarak, bir son kullanıcı cihazında zorlanan Şirket portalı belirli bir en düşük tanımlı sürümü belirtebilirsiniz. Bu koşullu başlatma ayarı, değeri karşılanmazsa **erişimi engellemeyi**, **verileri silmeyi**veya olası eylemler olarak **uyarmasını** sağlar. Bu değer için olası biçimler *[ana] düzenine uyar. [ İkincil]*, *[birincil]. [ İkincil]. [Derleme]* veya *[birincil]. [ İkincil]. [Derleme]. [Düzeltme]*.

Yapılandırılmışsa **Min Şirket Portalı sürüm** ayarı, Şirket Portalı sürüm 5.0.4560.0 ve gelecekteki tüm şirket portalı sürümlerini alan son kullanıcıları etkileyecektir. Bu ayarın, bu özelliğin yayımlandığı sürümden daha eski bir Şirket Portalı sürümünü kullanan kullanıcılar üzerinde hiçbir etkisi olmayacaktır. En son Şirket Portalı sürümünde olabilecekleri için, cihazlarından uygulama otomatik güncelleştirmelerini kullanan son kullanıcılar bu özellikten hiçbir iletişim kutusu görmeyecektir. Bu ayar yalnızca kayıtlı ve kayıtlı olmayan cihazlar için uygulama korumasıyla Android 'dir. Daha fazla bilgi için bkz. [Android uygulama koruma ilkesi ayarları-koşullu başlatma](~/apps/app-protection-policy-settings-android.md#conditional-launch).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->

### <a name="microsoft-365-device-management"></a>Microsoft 365 cihaz yönetimi

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Microsoft 365 cihaz yönetiminde Endpoint Security düğümünü tanıtma<!-- 5630102 -->

**Uç nokta güvenlik** düğümü artık https://devicemanagement.microsoft.com' de Microsoft 365 cihaz yönetimi uzman çalışma alanında genel olarak kullanıma sunulmuştur, bu, örneğin:

- Güvenlik temelleri: Microsoft tarafından önerilen bilinen ayar grubunu ve varsayılan değerleri uygulamanıza yardımcı olan önceden yapılandırılmış ayarlar grubu.

- Güvenlik görevleri: Microsoft Defender ATPs tehdidi ve güvenlik açığı yönetimi 'nin (TVM) avantajlarından yararlanın ve uç nokta zayıf noktalarını düzeltmek için Intune 'U kullanın.

- Microsoft Defender ATP: güvenlik ihlallerinin engellenmesine yardımcı olmak için tümleşik Microsoft Defender Gelişmiş tehdit koruması (ATP).

Bu ayarlar, cihazlar gibi diğer ilgili düğümlerin erişimine açık olmaya devam edecektir ve geçerli yapılandırılmış durum, bu özellikleri nerede eriştiğinize ve etkinleştirdiğiniz her durumda aynı olacaktır.

Bu geliştirmeler hakkında daha fazla bilgi için Microsoft Tech Community Web sitesinde [Intune müşteri başarısı blog gönderisine](https://aka.ms/Endpoint_security_node) bakın.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>Intune, iOS 11 ve üstünü destekler<!-- 4665324  -->

Intune kaydı ve Şirket Portalı artık iOS sürümleri 11 ve üstünü desteklemektedir. Eski sürümler desteklenmez.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Cihaz güvenliği

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Microsoft Edge taban çizgisi (Önizleme)<!--  3787164  -->

[Microsoft Edge ayarları](../protect/security-baseline-settings-edge.md)için güvenlik temeli önizlemesi ekledik. 

<!-- ########################## -->
## <a name="week-of-october-21-2019-1910-service-release"></a>21 Ekim 2019 (1910 hizmet sürümü) haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Microsoft 365 cihaz yönetimi

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Microsoft 365 cihaz yönetiminde geliştirilmiş yönetim deneyimi<!-- 5551239 -->

Yenilenmiş ve kolaylaştırılmış bir yönetim deneyimi, artık aşağıdakiler de dahil olmak üzere [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com)Microsoft 365 cihaz yönetimi uzman çalışma alanında genel kullanıma sunulmuştur:

- **Gezinti güncelleştirildi**: özellikleri mantıksal olarak gruplandıran, Basitleştirilmiş bir 1. düzey gezinti bulacaksınız.
- **Yeni platform filtreleri**: cihazlar ve uygulamalar sayfalarında yalnızca seçili platformun ilkelerini ve uygulamalarını gösteren tek bir platform seçebilirsiniz.
- **Yeni bir giriş sayfası**: yeni giriş sayfasında hizmet durumunu, kiracınızın durumunu, Haberler, vb. hızlı bir şekilde görüntüleyin.

Bu geliştirmeler hakkında daha fazla bilgi için Microsoft Tech Community Web sitesindeki [Enterprise Mobility + Security blog gönderisine](https://go.microsoft.com/fwlink/?linkid=2109094) bakın.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Kayıtlı olmayan cihazlara mobil tehdit savunma uygulamaları ekleme<!-- 3005337 -->
Kullanıcıların şirket verilerini bir cihazın sistem durumuna göre engelleyebilen veya seçmeli olarak silebilecek bir Intune uygulama koruma ilkesi oluşturabilirsiniz. Cihazın sistem durumu, seçtiğiniz Mobile Threat Defense (MTD) çözümünüz kullanılarak belirlenir. Bu özellik günümüzde Intune 'A kayıtlı cihazlar cihaz uyumluluk ayarı olarak mevcuttur. Bu yeni özellik sayesinde, tehdit algılamayı bir mobil tehdit savunma satıcısından kayıtlı olmayan cihazlarda çalışacak şekilde genişlettik. Android 'de, bu özellik cihazda en son Şirket Portalı gerektirir. İOS 'ta, bu özellik, uygulamalar en son Intune SDK 'sını (v 12.0.15 +) tümleştirdiğinizde kullanıma sunulacaktır. İlk uygulama en son Intune SDK 'sını benimseme konusundaki yenilikler konusunu güncelleştireceğiz. Kalan uygulamalar, düzenli olarak kullanılabilir hale gelir. Daha fazla bilgi için bkz. [Intune Ile mobil tehdit savunma uygulama koruma Ilkesi oluşturma](~/protect/mtd-app-protection-policy.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Windows 10 ve üzeri cihazlar için yeni cihaz üretici yazılımı yapılandırma arabirimi profili (Genel Önizleme)<!-- 2266073  -->

Windows 10 ve üzeri sürümlerde, ayarları ve özellikleri denetlemek için bir cihaz yapılandırma profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > , platform için **Windows 10 ve üzeri sürümler** ) > **profil oluşturma** ). Bu güncelleştirmede, Intune 'un UEFı (BIOS) ayarlarını yönetmesine izin veren yeni bir cihaz üretici yazılımı yapılandırma arabirimi profil türü vardır.

Bu özellik hakkında daha fazla bilgi için, bkz. [Microsoft Intune Windows cihazlarda dfcı profillerini kullanma](../configuration/device-firmware-configuration-interface-windows.md).

Uygulama hedefi:
- Windows 10 RS5 (1809) ve desteklenen bellenim üzerinde daha yeni

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Yalnızca hazır olmayan deneyim (OOBE) tarafından sağlanan cihazlarda kayıt durumu sayfasını göstermek için değiştirin<!--3959566-->
Artık Autopilot OOBE tarafından sağlanan cihazlarda kayıt durumu sayfasını göstermeyi tercih edebilirsiniz.

Yeni geçişi görmek için **ıntune** > **cihaz kaydı** > **Windows kayıt** > **kayıt durumu sayfası** ' nı seçin > **profil** > **ayarları** oluştur > **yalnızca, kullanıma hazır deneyim (OOBE) tarafından sağlanan cihazlara yönelik sayfayı gösterin**.


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>14 Ekim 2019 haftası

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi 

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Android iş profilleri için kullanılabilir Google Play uygulama raporlaması<!-- 3041956   -->
Android kurumsal iş profili, adanmış ve tam olarak yönetilen cihazlarda kullanılabilir uygulama yüklemeleri için, uygulama yükleme durumunu ve yönetilen Google Play uygulamalarının yüklü sürümünü görüntüleyebilirsiniz. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](~/apps/app-protection-policies-monitor.md), [Android Iş profili cihazlarını Intune ile yönetme](~/enrollment/android-enterprise-overview.md) ve [uygulama türü ile yönetilen Google Play](~/apps/apps-add-android-for-work.md#managed-google-play-app-types).

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Windows 10 ve macOS için Microsoft Edge sürüm 77 ve üzeri (Genel Önizleme)<!-- 3872025, 4678761  -->
Microsoft Edge sürüm 77 ve üzeri, Windows 10 ve macOS çalıştıran bilgisayarlara dağıtmak için kullanılabilir. 

Genel Önizleme, Windows 10 için **geliştirme** ve **Beta** kanalları ve MacOS için bir **Beta** kanalı sunar. Dağıtım yalnızca Ingilizce (EN) ' dir, ancak son kullanıcılar tarayıcıdaki görüntüleme dilini **ayarlar** > **dilleri**altında değiştirebilir. Microsoft Edge, sistem bağlamında ve benzer mimarilere (x86 IŞLETIM sisteminde x86 uygulaması ve x64 IŞLETIM sisteminde x64 uygulaması) yüklenen bir Win32 uygulamasıdır. Ayrıca, tarayıcının otomatik güncelleştirmeleri varsayılan olarak **Açık** olur ve Microsoft Edge kaldırılamaz. Daha fazla bilgi için bkz. [Windows 10 Için Microsoft Edge 'i Microsoft Intune](~/apps/apps-windows-edge.md) ve [Microsoft Edge belgelerini](https://go.microsoft.com/fwlink/?linkid=2103823)ekleme.

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Uygulama koruma Kullanıcı arabirimi ve iOS uygulama sağlama Kullanıcı arabirimine güncelleştirme<!-- 4102027, 4102029   -->
Intune 'da uygulama koruma ilkeleri ve iOS uygulama sağlama profilleri oluşturma ve düzenleme için Kullanıcı arabirimi güncelleştirilmiştir. UI değişiklikleri şunları içerir:
- Bir dikey pencere içinde bir sihirbaz stili biçim kullanılarak basitleştirilmiş bir deneyim. 
- Atamaları eklemek için akış oluşturma için bir güncelleştirme.
- Yeni bir ilke oluşturmadan veya bir özellik düzenlenirken önce özellikleri görüntülerken ayarlanan tüm öğelerin özetlenen sayfası. Ayrıca, Özellikler düzenlenirken, Özet yalnızca düzenlenmekte olan özellikler kategorisinden öğe listesini gösterir.

Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](~/apps/app-protection-policies.md) ve [iOS uygulama sağlama profillerini kullanma](~/apps/app-provisioning-profile-ios.md).

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Intune destekli senaryolar<!-- 4850318, 4831296, 3610611  -->
Intune artık Intune 'da belirli bir görevi veya görev kümesini tamamlamanıza yardımcı olacak şekilde Kılavuzlu senaryolar sunmaktadır. Kılavuzlu senaryo, bir uçtan uca kullanım örneği etrafında ortalanan özelleştirilmiş bir adım (iş akışı) dizisidir. Ortak senaryolar, kuruluşunuzda yönetici, Kullanıcı veya cihazın oynadığı role göre tanımlanır. Bu iş akışları genellikle en iyi kullanıcı deneyimini ve güvenliğini sağlamak için dikkatle düzenlenmiş profiller, ayarlar, uygulamalar ve güvenlik denetimleri koleksiyonu gerektirir. Yeni Kılavuzlu senaryolar şunlardır:
- [Mobil için Microsoft Edge dağıtma](~/fundamentals/guided-scenarios-edge.md)
- [Mobile Apps Microsoft Office güvenli hale getirme](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Bulutta yönetilen modern masaüstü](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Daha fazla bilgi için bkz. [Intune Kılavuzlu senaryolara genel bakış](guided-scenarios-overview.md).

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Ek uygulama yapılandırma değişkeni kullanılabilir<!-- 4969237   -->
Bir uygulama yapılandırma ilkesi oluştururken, `AAD Device ID` Yapılandırma değişkenini yapılandırma ayarlarınızın bir parçası olarak dahil edebilirsiniz. Intune 'da, **ekle** > **uygulama yapılandırma ilkeleri** > **istemci uygulamaları** ' nı seçin. Yapılandırma **ayarları** dikey penceresini görüntülemek için yapılandırma ilkesi ayrıntılarınızı girip **yapılandırma ayarları** ' nı seçin. Daha fazla bilgi için bkz. [yönetilen Android kurumsal cihazlar Için uygulama yapılandırma ilkeleri-yapılandırma tasarımcısını kullanın](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>İlke kümeleri olarak adlandırılan yönetim nesnesi grupları oluşturma<!-- 3762880  -->
İlke kümeleri, önceden tanımlanmış, hedeflenen ve tek bir kavramsal birim olarak izlenmesi gereken yönetim varlıklarının başvuruları için bir paket oluşturmanıza olanak sağlar. İlke kümeleri varolan kavramları veya nesneleri değiştirmez. Intune 'da tek tek nesneleri atamaya devam edebilir ve bir ilke kümesinin parçası olarak tek tek nesnelere başvurabilirsiniz. Bu nedenle, bağımsız nesnelerde yapılan tüm değişiklikler Ilke kümesine yansıtılır.  Intune 'da yeni bir Ilke kümesi oluşturmak için > **Oluştur** ' u seçerek **ilke kümelerini** seçersiniz. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Windows 10 güncelleştirme halkalarını oluşturma ve düzenlemeyle ilgili Kullanıcı arabirimi güncelleştirmesi<!-- 4099089         -->
Intune için [Windows 10 güncelleştirme halkalarını oluşturma ve düzenlemeyle](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) ilgili Kullanıcı arabirimi deneyimini güncelleştirdik. Kullanıcı arabirimindeki değişiklikler şunları içerir:  
- Bir sihirbaz stili biçimi, daha önce güncelleştirme halkalarını yapılandırırken daha önce görülen dikey pencere genişlemesine ile birlikte bulunan tek bir konsol dikey penceresine yoğunlaştırılmış.   
- Gözden geçirilen iş akışı, halkanın ilk yapılandırmasını tamamlamadan önce atamaları içerir.
- Yeni bir güncelleştirme halkasını kaydetmeden ve dağıtımdan önce, yaptığınız tüm konfigürasyonları gözden geçirmek için kullanabileceğiniz bir Özet sayfası. Bir güncelleştirme halkasını düzenlenirken, Özet yalnızca düzenlediğiniz özelliklerin kategorisi içinde ayarlanan öğelerin listesini gösterir.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>İOS yazılım güncelleştirme ilkesi oluşturma ve düzenlemeyle ilgili Kullanıcı arabirimi güncelleştirmesi<!-- 4099090       --> 
Intune için iOS yazılım güncelleştirme ilkelerini [oluşturma](../protect/software-updates-ios.md#configure-the-policy) ve [düzenlemeyle](../protect/software-updates-ios.md#edit-a-policy) ilgili Kullanıcı arabirimi deneyimini güncelleştirdik.  Kullanıcı arabirimindeki değişiklikler şunları içerir:  
- Bir sihirbaz stili biçimi, daha önce güncelleştirme ilkelerini yapılandırdığınız gibi görülen dikey pencere genişlemesine ile birlikte bulunan tek bir konsol dikey penceresine dar.   
- Düzeltilen iş akışı, ilkenin ilk yapılandırmasını tamamlamadan önce atamaları içerir.
- Yeni bir ilke kaydetmeden ve dağıtımdan önce, yaptığınız tüm konfigürasyonları gözden geçirmek için kullanabileceğiniz bir Özet sayfası. Bir ilke düzenlenirken, Özet yalnızca düzenlediğiniz özelliklerin kategorisi içinde ayarlanan öğelerin listesini gösterir.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404--------"></a>Boşta yeniden başlatma ayarları Windows Update halkalardan kaldırılır<!--  4464404      -->
Daha önce duyurulduğu gibi, Intune 'un Windows 10 güncelleştirme halkaları artık [son tarihleri destekler](../protect/windows-update-settings.md) ve artık *yeniden başlatmayı*desteklemez. Intune 'da güncelleştirme halkalarını yapılandırırken veya yönetirken, ara *yeniden başlatma* ayarları artık kullanılamaz.  

Bu değişiklik, son [Windows hizmet değişiklikleri](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing) ve Windows 10 1903 veya sonraki sürümleri çalıştıran cihazlarda hizalanır, *son tarihler* , ara *yeniden başlatma*yapılandırmalarının yerini alır.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Android kurumsal iş profili cihazlarında bilinmeyen kaynaklardan uygulama yüklenmesini engelleyin<!-- 4760025   -->
Android kurumsal iş profili cihazlarında, kullanıcılar hiçbir zaman bilinmeyen kaynaklardan uygulama uygulamaları yükleyemez. Bu güncelleştirmede, yeni bir ayar vardır; **Kişisel profilde bilinmeyen kaynaklardan uygulama yüklemelerini engelleyin**. Varsayılan olarak, bu ayar kullanıcıların bilinmeyen kaynaklardan gelen uygulamaları cihazdaki kişisel profile içine dışarıdan yüklemesini engeller.

Yapılandırabileceğiniz ayarı görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi:
- Android kurumsal iş profili

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Android kurumsal cihaz sahibi cihazlarda genel HTTP proxy oluşturma<!-- 4816339   -->
Android kurumsal cihazlarda, kuruluşunuzun Web tarama standartlarını (**cihaz yapılandırma** > **profilleri** > Için bir genel http proxy 'si yapılandırabilirsiniz. Bu, > **Android Enterprise** for platform > **cihaz sahibi >** **profil türü** > **bağlantı**için cihaz kısıtlamaları). Yapılandırıldıktan sonra tüm HTTP trafiği bu proxy 'yi kullanır.

Bu özelliği yapılandırmak ve yapılandırdığınız tüm ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi:
- Android kurumsal cihaz sahibi

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>Android Cihaz Yöneticisi ve Android Enterprise 'ta Wi-Fi profillerinde otomatik olarak bağlan ayarı kaldırılır<!-- 5021055   -->
Android Cihaz Yöneticisi ve Android kurumsal cihazlarda, farklı ayarları yapılandırmak için bir Wi-Fi profili oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > **, platform Için ** > **Android Cihaz Yöneticisi** veya **Android Enterprise** > profil türü için **Wi-Fi** ). Bu güncelleştirmede, [Android tarafından destek olmadığından](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29) **Otomatik bağlan** ayarı kaldırılır. 

Bu ayarı bir Wi-Fi profilinde kullanırsanız, **Connect 'in otomatik olarak** çalışmadığını fark etmiş olabilirsiniz. Herhangi bir işlem yapmanız gerekmez, ancak bu ayarın Intune kullanıcı arabiriminde kaldırıldığını unutmayın.

Geçerli ayarları görmek için [Android Wi-Fi ayarları](../configuration/wi-fi-settings-android.md) veya [Android Enterprise Wi-Fi ayarları](../configuration/wi-fi-settings-android-enterprise.md)' na gidin.

Uygulama hedefi:
- Android Cihaz Yöneticisi 
- Android Kurumsal


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Denetimli iOS ve ıpados cihazları için yeni cihaz yapılandırma ayarları<!-- 5199328   -->
İOS ve ıpados cihazlarında, cihazlarda özellikleri ve ayarları kısıtlamak için bir profil oluşturabilirsiniz (**cihaz yapılandırma** > **profilleri** > profil **oluşturma** > **iOS/IPA> DOS** , profil türü için **cihaz kısıtlamaları** ). Bu güncelleştirmede, denetleyebilmeniz için yeni ayarlar vardır: 
- Dosyalar uygulamasındaki ağ sürücüsüne erişim  
- Dosyalar uygulamasındaki USB sürücüsüne erişim 
- Wi-Fi her zaman açık 

Bu ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama hedefi:
- iOS 13,0 ve üzeri
- ıpados 13,0 ve üzeri

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Hangi Android cihaz işletim sistemi sürümlerinin iş profili veya cihaz yöneticisi kaydıyla kaydedileceğini belirtin<!-- 4350697   -->
Intune cihaz türü kısıtlamalarını kullanarak, Android kurumsal iş profili kaydı veya Android Cihaz Yöneticisi kaydını hangi kullanıcı cihazlarının kullanacağı belirtmek için cihazın işletim sistemi sürümünü kullanabilirsiniz.  Daha fazla bilgi için bkz. [kayıt kısıtlamalarını ayarlama](../enrollment/enrollment-restrictions-set.md).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Windows cihazlarını yeniden adlandırmaya yönelik yeni kısıtlamalar<!-- 3478938  -->
Bir Windows cihazını yeniden adlandırırken yeni kuralları izlemeniz gerekir:
- 15 karakter veya daha az (63 bayttan küçük veya buna eşit olmalı, sondaki NULL dahil değildir)
- Null veya boş dize değil
- İzin verilen ASCII: harfler (a-z, A-Z), sayılar (0-9) ve tireler
- İzin verilen Unicode: karakterler > = 0x80, geçerli UTF8 olmalıdır, ıDN eşleme olmalıdır (yani Rtlıdntonameprepunıcode başarılı; bkz. RFC 3492)
- Adlar yalnızca rakam içermemelidir
- Adda boşluk yok
- İzin verilmeyen karakterler: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)

 Daha fazla bilgi için bkz. [Intune 'da cihazı yeniden adlandırma](../remote-actions/device-rename.md).

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Cihazlara ilişkin yeni Android raporuna genel bakış sayfası<!-- 4924364 -->
Cihazlara genel bakış sayfasına yeni bir rapor, her bir cihaz yönetimi çözümüne kaç tane Android cihaz kaydedildiğini gösterir. Bu grafik iş profilini, tam olarak yönetilen, adanmış ve Cihaz Yöneticisi kayıtlı cihaz sayısını gösterir. Raporu görmek için **ıntune** > **cihazlar** > **genel bakış**' ı seçin.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Cihaz güvenliği

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>MacOS için PKCS sertifikaları<!-- 1333650       -->
Artık [macOS Ile PKCS sertifikaları kullanabilirsiniz](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). MacOS için bir profil türü olarak PKCS sertifikasını seçebilir ve [özelleştirilmiş konu ve konu alternatif adı alanlarına](../protect/certficates-pfx-configure.md#subject-name-format)sahip kullanıcı ve cihaz sertifikalarını dağıtabilirsiniz.  

MacOS için PKCS sertifikası yeni bir ayarı da destekler, _tüm uygulamaların erişimine Izin verir_. Bu ayarla, ilişkili tüm uygulamaların, sertifikanın özel anahtarına erişmesini sağlayabilirsiniz.  Bu ayar hakkında daha fazla bilgi için https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdfApple belgelerine bakın.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>İOS mobil cihazlarını sertifikalarla sağlamak için türetilmiş kimlik bilgileri<!--  1736036, 1736037, 1772050, 2777333         -->  
Intune, [türetilmiş kimlik bilgilerinin](../protect/derived-credentials.md) bir kimlik doğrulama yöntemi ve iOS cihazları için S/MIME imzalama ve şifreleme için kullanımını destekler. Türetilmiş kimlik bilgileri, cihazlara sertifika dağıtmaya yönelik *ulusal standartlar ve Teknoloji Enstitüsü (NIST) 800-157* standardının bir uygulamasıdır.  

Türetilmiş kimlik bilgileri, akıllı kart gibi kişisel kimlik doğrulama (PıV) veya ortak erişim kartı (CAC) kartının kullanımına dayanır. Mobil cihazlarının türetilmiş bir kimlik bilgilerini almak için, kullanıcılar Şirket Portalı uygulamasında başlar ve kullandığınız sağlayıcıya özgü bir kayıt iş akışını takip edin.  Tüm sağlayıcılar için ortak, türetilmiş kimlik bilgisi sağlayıcısında kimlik doğrulaması yapmak için bir bilgisayarda akıllı kart kullanma gereksinimidir. Bu sağlayıcı daha sonra kullanıcının akıllı kartından derlenen cihaza bir sertifika yayınlar.  

Intune, aşağıdaki türetilmiş kimlik bilgisi sağlayıcılarını destekler:
- DıŞA purebred
- Entrust Datacard
- Intercede

VPN, Wi-Fi ve e-posta için cihaz yapılandırma profillerinin kimlik doğrulama yöntemi olarak türetilmiş kimlik bilgilerini kullanırsınız. Bunları uygulama kimlik doğrulaması ve S/MIME imzalama ve şifreleme için de kullanabilirsiniz.  

Standart hakkında daha fazla bilgi için bkz. www.nccoe.nist.gov adresindeki [TÜRETILMIŞ PIV kimlik bilgileri](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) .

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>SCEP sertifikaları için bir değişken olarak şirket içi Kullanıcı asıl adı belirtmek için Graph API kullanın<!--  5437939        -->  
[Intune Graph API](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)KULLANDıĞıNıZDA, SCEP sertifikaları Için konu alternatif adı (San) için bir değişken olarak onPremisesUserPrincipalName belirtebilirsiniz.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>23 Eylül 2019 haftası

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Önizlemede iOS Kullanıcı kaydı<!-- 4817900 -->
Apple 'ın iOS 13,1 sürümü, iOS cihazları için basit yönetimin yeni bir biçimi olan Kullanıcı kaydını içerir. Bu, kişisel cihazlar için cihaz kaydı veya otomatik cihaz kaydı (eski adıyla Aygıt Kayıt Programı) yerine kullanılabilir. Intune 'un önizlemesi, bu özellik kümesini şunları yapmanıza izin vererek destekler:

- Kullanıcı kaydını Kullanıcı gruplarına hedefleyin.
- Son kullanıcılara cihazlarını kaydettiklerinde daha hafif Kullanıcı kaydı veya daha güçlü bir cihaz kaydı arasından seçim yapma olanağı sunun.

9/24/2019 ' den başlayarak, iOS 13,1 ' nin yayımlanmasından itibaren, bu güncelleştirmeleri tüm müşterilere teslim etmek ve önümüzdeki hafta sonuna kadar tamamlanmasını beklemek için çalışıyoruz.
Uygulama hedefi:

iOS 13,1 ve üzeri

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Idos ve iOS 13,1 cihazları için Intune desteği<!--5439574-->
Intune artık Idos ve iOS 13,1 cihazlarını yönetmeyi desteklemektedir. Daha fazla bilgi için [bu blog gönderisine](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094) bakın.

<!-- ########################## -->

## <a name="week-of-september-16-2019-1909-service-release"></a>16 Eylül 2019 haftası (1909 hizmet sürümü)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Uygulama yönetimi 

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Yönetilen Google Play özel LOB uygulamaları<!-- 1464182  -->
Intune artık BT yöneticilerinin Intune konsoluna katıştırılmış bir iframe aracılığıyla özel Android LOB uygulamalarını yönetilen Google Play yayımlamasına olanak tanır.  Daha önce BT yöneticileri, çeşitli adımları gerektiren ve zaman tüketen, LOB uygulamalarını doğrudan Google Play yayımlama konsoluna yayımlamak için gereklidir. Bu yeni özellik, Intune konsolundan ayrılmak zorunda kalmadan LOB uygulamalarının en az bir adım kümesiyle kolayca yayımlanmasını sağlar.  Yöneticiler artık Google ile bir geliştirici olarak el ile Kaydolmayacak ve artık Google $25 kayıt ücretini ödemem gerekmez.  Yönetilen Google Play kullanan Android kurumsal yönetim senaryolarından herhangi biri bu özellikten yararlanabilir (iş profili, adanmış, tam olarak yönetilen ve kayıtlı olmayan cihazlar). Intune 'da, **ekle** > **Istemci uygulamaları** > **uygulamalar** ' ı seçin. Ardından, **uygulama türü** listesinden **yönetilen Google Play** ' yi seçin. Yönetilen Google Play uygulamalar hakkında daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md).

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Windows Şirket Portalı deneyimi<!-- 1473353, 3598357 -->
Windows Şirket Portalı güncelleştiriliyor. Windows Şirket Portalı içindeki uygulamalar sayfasında birden çok filtre kullanabileceksiniz. Cihaz ayrıntıları sayfası, gelişmiş bir kullanıcı deneyimiyle de güncelleştiriliyor. Bu güncelleştirmeleri tüm müşterilere teslim etmek ve önümüzdeki hafta sonuna kadar tamamlanmasını beklemek istiyoruz.

#### <a name="macos-support-for-web-apps---3174427---"></a>Web uygulamaları için macOS desteği<!-- 3174427 -->
Web 'deki bir URL 'ye kısayol eklemenize olanak sağlayan Web Apps, macOS Şirket Portalı kullanılarak Dock 'a yüklenebilir. Son kullanıcılar, macOS Şirket Portalı bir Web uygulaması için uygulama ayrıntıları sayfasından **Install** eylemine erişebilir. **Web bağlantısı** uygulama türü hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](../apps/apps-add.md) ve [Microsoft Intune Web uygulamaları ekleme](../apps/web-app.md).

#### <a name="macos-support-for-vpp-apps---3173501----"></a>VPP uygulamaları için macOS desteği<!-- 3173501  -->
Apple Business Manager kullanılarak satın alınan macOS uygulamaları, Apple VPP belirteçleri Intune 'da eşitlendiğinde konsolunda görüntülenir. Intune konsolunu kullanarak, gruplar için cihaz ve Kullanıcı tabanlı lisanslar atayabilir, iptal edebilir ve yeniden atayabilirsiniz. Microsoft Intune, şirketinizde kullanılmak üzere satın alınan VPP uygulamalarını şu şekilde yönetmenize yardımcı olur:

- Uygulama mağazasından lisans bilgilerini raporlama.
- Kaç lisans kullandığınızı izleme.
- Sahip olduğunuz uygulamanın daha fazla kopyasını yükleme zorunluluğunu ortadan kaldırır.

Intune ve VPP hakkında daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alınan uygulamaları ve kitapları yönetme](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Yönetilen Google Play iFrame desteği<!-- 2871756  -->
Intune artık yönetilen Google Play iframe aracılığıyla doğrudan Intune konsolunda Web bağlantıları ekleme ve yönetme desteği sağlar.  Bu, BT yöneticilerinin bir URL ve simge grafiği göndermesini sağlar ve ardından bu bağlantıları düzenli Android uygulamaları gibi cihazlara dağıtır. Yönetilen Google Play kullanan Android kurumsal yönetim senaryolarından herhangi biri bu özellikten yararlanabilir (iş profili, adanmış, tam olarak yönetilen ve kayıtlı olmayan cihazlar). Intune 'da, **ekle** > **Istemci uygulamaları** > **uygulamalar** ' ı seçin. Ardından, **uygulama türü** listesinden **yönetilen Google Play** ' yi seçin. Yönetilen Google Play uygulamalar hakkında daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md).

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>Android LOB uygulamalarını Zeköşeli cihazlara sessizce yüklemeyin<!-- 4252734  -->
Android iş kolu (LOB) uygulamalarını, her ikisi de LOB uygulaması indirip yüklemeniz istenmek yerine [Zeköşeli cihazlara](../configuration/android-zebra-mx-overview.md)yüklerken uygulamayı sessizce yükleyebilirsiniz. Intune 'da, **ekle** > **Istemci uygulamaları** > **uygulamalar** ' ı seçin. **Uygulama ekle** bölmesinde **İş kolu uygulaması**’nı seçin. Daha fazla bilgi için bkz. [Microsoft Intune Android iş kolu uygulaması ekleme](../apps/lob-apps-android.md).

Şu anda, LOB uygulaması indirildikten sonra kullanıcının cihazında bir **indirme başarısı** bildirimi görüntülenir. Bildirim yalnızca bildirim gölgelede **Clear All** öğesine dokunarak kapatılabilir. Bu bildirim sorunu gelecek bir sürümde düzeltilecektir ve yükleme hiçbir görsel gösterge olmadan tamamen sessiz olacaktır.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Intune uygulamaları için okuma ve yazma Graph API işlemleri<!-- 5031704  -->
Uygulamalar, Kullanıcı kimlik bilgileri olmadan uygulama kimliği 'ni kullanarak hem okuma hem de yazma işlemlerinde Intune Graph API çağırabilir. Intune için Microsoft Graph API 'sine erişme hakkında daha fazla bilgi için, bkz. [Microsoft Graph Intune Ile çalışma](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>İOS için Intune uygulama SDK 'Sı korumalı veri paylaşımı ve şifrelemesi<!-- 3586942  -->
Şifreleme uygulama koruma ilkeleri tarafından etkinleştirilmişse iOS için Intune uygulama SDK'sı, 256 bit şifreleme anahtarları kullanır. Korunan veri paylaşımına izin vermek için tüm uygulamaların bir SDK sürümü 8.1.1 olması gerekir.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>İOS için IKEv2 VPN profilleri desteği<!-- 1943438   -->
Bu güncelleştirmede, Ikev2 protokolünü kullanarak iOS Native VPN istemcisi için VPN profilleri oluşturabilirsiniz. Ikev2, > profil türü > **bağlantı türü**için Platform > **VPN** için iOS > **iOS** > **profil oluşturma** ' da **cihaz yapılandırma** **profillerinde** yeni bir bağlantı türüdür.

Bu VPN profilleri yerel VPN istemcisini yapılandırır, bu nedenle yönetilen cihazlara hiçbir VPN istemci uygulaması yüklenmeyecek veya gönderilmemiş. Bu özellik cihazların Intune 'A (MDM kaydı) kaydedilmesini gerektirir.

Yapılandırabileceğiniz geçerli VPN ayarlarını görmek için [iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md)bölümüne gidin.

Uygulama hedefi:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>İOS ve macOS ayarları için cihaz özellikleri, cihaz kısıtlamaları ve uzantı profilleri kayıt türüne göre gösteriliyor<!-- 4886161   -->

Intune 'da iOS ve macOS cihazları için Profiller oluşturun (**cihaz yapılandırma** > **profilleri** > platform > **cihaz özellikleri**, **cihaz kısıtlamaları**veya profil türü **uzantıları** ) için **iOS** veya **MacOS** > **profili oluşturun** ). 

Bu güncelleştirmede, Intune portalındaki kullanılabilir ayarlar, uygulanan kayıt türüne göre kategorilere ayrılır:

- iOS
  - Kullanıcı kaydı
  - Cihaz kaydı
  - Otomatik cihaz kaydı (denetimli)
  - Tüm kayıt türleri

- Mac OS
  - Kullanıcı onaylandı
  - Cihaz kaydı
  - Otomatik cihaz kaydı
  - Tüm kayıt türleri

Uygulama hedefi:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Denetimli iOS cihazları için bilgi noktası modunda çalışan yeni ses denetimi ayarları<!-- 4892835   -->
Intune 'da, denetimli iOS cihazlarını bir bilgi noktası olarak çalıştırmak için ilkeler oluşturabilir ve platform için IOS > **cihaz** oluşturma > profil türü **** > **bilgi noktası**) için **iOS** için iOS > **profil oluşturma** ' ya yönelik cihaz**yapılandırma** > .

Bu güncelleştirmede, denetleyebilmeniz için yeni ayarlar vardır:
- **Ses denetimi**: bilgi noktası modundayken cihazda ses denetimini mümkün.
- **Ses denetimi değişikliği**: kullanıcıların bilgi noktası modundayken cihazdaki ses denetimi ayarını değiştirmesine izin verin.

Geçerli ayarları görmek için [IOS bilgi noktası ayarları](../configuration/device-restrictions-ios.md#kiosk)' na gidin.

Uygulama hedefi:
- iOS 13,0 ve üzeri

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>İOS ve macOS cihazlarınızdaki uygulamalar ve Web siteleri için çoklu oturum açma kullanın<!-- 4893175   -->
Bu güncelleştirmede, iOS ve macOS **cihazları için yeni** çoklu oturum açma ayarları vardır (**cihaz yapılandırma** > **profilleri** > profil türü için **IOS** veya **ma> cos** > **profili oluşturma** ).

Özellikle de Kerberos kimlik doğrulaması kullanan uygulamalar ve Web siteleri için çoklu oturum açma deneyimi yapılandırmak üzere bu ayarları kullanın. Genel kimlik bilgisi çoklu oturum açma uygulaması uzantısı ve Apple 'ın yerleşik Kerberos uzantısı arasında seçim yapabilirsiniz.

Yapılandırabileceğiniz geçerli cihaz özelliklerini görmek için [iOS cihaz özelliklerine](../configuration/ios-device-features-settings.md) ve [MacOS cihaz özelliklerine](../configuration/macos-device-features-settings.md)gidin.

Uygulama hedefi:
- iOS 13,0 ve üzeri
- macOS 10,15 ve üzeri

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>MacOS 10.15 + cihazlarında etki alanlarını uygulamalarla ilişkilendirme<!-- 4898079   -->
MacOS cihazlarında, farklı özellikler yapılandırabilir ve bu özellikleri cihazlara bir ilke (**cihaz yapılandırma** > **profilleri** > profil **Oluştur** > **ma> cos** , profil türü için **cihaz özellikleri** ) bir ilke kullanarak gönderebilirsiniz. Bu güncelleştirmede, etki alanlarını uygulamalarınızla ilişkilendirebilirsiniz. Bu özellik, uygulama ile ilgili web siteleriyle kimlik bilgilerinin paylaşılmasını sağlar ve Apple 'ın çoklu oturum açma uzantısı, evrensel bağlantılar ve parola otomatik doldurma ile kullanılabilir. 

Yapılandırabileceğiniz geçerli özellikleri görmek için [Intune 'Da MacOS cihaz özelliği ayarları](../configuration/macos-device-features-settings.md)' na gidin.

Uygulama hedefi:
- macOS 10,15 ve üzeri

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>İOS denetimli cihazlarda uygulamaları gösterirken veya gizlerken iTunes App Store URL 'sindeki "iTunes" ve "Apps" kullanın<!-- 4928474   --> 
Intune 'da, denetimli iOS cihazlarınızda uygulamaları göstermek veya gizlemek için ilkeler oluşturabilirsiniz (**cihaz yapılandırma** > **profiller** > profil > **oluşturmak** için **iOS** > **cihaz kısıtlamaları** > **uygulamaları göster veya gizle**). 

`https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`gibi iTunes App Store URL 'sini girebilirsiniz. Bu güncelleştirmede hem `apps` hem de `itunes` URL 'de kullanılabilir, örneğin:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Bu ayarlar hakkında daha fazla bilgi için bkz. [uygulamaları gösterme veya gizleme](../configuration/device-restrictions-ios.md#show-or-hide-apps).

Uygulama hedefi:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Windows 10 uyumluluk ilkesi parola türü değerleri daha net ve ile eşleşiyor CSP<!-- 5138985 -->
Windows 10 cihazlarında belirli parola özellikleri gerektiren bir uyumluluk ilkesi oluşturabilirsiniz (**cihaz uyumluluk** > **ilkeleri** > platform > **sistem güvenliği**için **Windows 10 ve üzeri** ) **ilke oluşturma** > . Bu güncelleştirmede:
- **Parola türü** değerleri daha net ve [DeviceLock/alfanümerik ıdevicepasswordrequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)ile eşleşecek şekilde güncelleştirilir.
- **Parola süre sonu (gün)** ayarı 1-730 günden daha fazla değere izin verecek şekilde güncelleştirilir. 

Windows 10 uyumluluk ayarları hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri ayarları cihazları uyumlu veya uyumsuz olarak işaretleme](../protect/compliance-policy-create-windows.md). 

Uygulama hedefi:
- Windows 10 ve üzeri

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Microsoft Exchange şirket içi erişimini yapılandırmak için güncelleştirilmiş Kullanıcı arabirimi<!-- 4092920 -->  
[Microsoft Exchange şirket içi](../protect/conditional-access-exchange-create.md)erişim erişimini yapılandırdığınız konsolu güncelleştirdik. Şirket içi Exchange erişimi için tüm yapılandırmalara artık, *Şirket Içi Exchange erişim denetimini etkinleştirdiğiniz*konsolun aynı bölmesinde erişilebilir.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Android kurumsal iş profili cihazlarındaki giriş ekranına uygulama pencere öğelerinin eklenmesine izin ver veya kısıtla<!-- 1109650  --> 
Android kurumsal cihazlarda iş profilindeki (**cihaz yapılandırma** > **profiller** > **profil oluşturma** > **Android Enterprise** for platform > **iş profili yalnızca profil türü için cihaz kısıtlamalarını >** ) yapılandırabilirsiniz. Bu güncelleştirmede, kullanıcıların iş profili uygulamaları tarafından sunulan pencere öğelerini cihaz giriş ekranına eklemesine izin verebilirsiniz.

Yapılandırabileceğiniz ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md).

Uygulama hedefi:
- Android kurumsal iş profili

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Yeni kiracılar varsayılan olarak Android Cihaz Yöneticisi yönetiminden uzaklaşacaktır<!-- 4869790   -->
Android 'in Cihaz Yöneticisi özellikleri, Android Enterprise tarafından değiştirildi. Bu nedenle, bunun yerine Android Enterprise 'ı yeni kayıtlar için kullanmanızı öneririz. Gelecekteki bir güncelleştirmede, yeni kiracıların Cihaz Yöneticisi yönetimini kullanmak için Android kaydında aşağıdaki önkoşul adımlarını tamamlaması gerekir: **Intune** 'a gidin > cihaz **kaydı** > **android kaydı** , **cihaz yönetimi > ayrıcalıklarına sahip kişisel ve şirkete ait cihazlar** > **cihazları yönetmek için cihaz yöneticisini kullanın**.

Mevcut kiracılar ortamlarında hiçbir değişikliğe karşılaşmayacak.

Intune 'da Android Cihaz Yöneticisi hakkında daha fazla bilgi için bkz. [Android Cihaz Yöneticisi kaydı](https://docs.microsoft.com/intune/android-enroll-device-administrator).

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045-idmiss---"></a>Bir profille ilişkili DEP cihazlarının listesi<!-- 5012045 idmiss -->
Artık, bir profille ilişkili Apple otomatik Aygıt Kayıt Programı (DEP) cihazlarının sayfalı bir listesini görebilirsiniz. Listede, listedeki herhangi bir sayfadan arama yapabilirsiniz. Listeyi görmek için **ıntune** > **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ne gidin > bir belirteç > **profilleri** seçin > bir > **atanmış cihaz** seçin ( **izleyici**altında).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Cihaz yönetimi

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Daha fazla Android tam yönetilen desteği<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
Android tam olarak yönetilen cihazlar için aşağıdaki desteği ekledik:

- Tam olarak yönetilen Android için SCEP sertifikaları, cihaz sahibi olarak yönetilen cihazlarda sertifika kimlik doğrulaması için kullanılabilir. SCEP sertifikaları Iş profili cihazlarında zaten destekleniyor.  Cihaz sahibi için SCEP sertifikalarıyla şunları yapabilirsiniz: <!-- 5227935 -->
    - Android Enterprise 'ın YAPıLACAKLAR bölümünde SCEP profili oluşturma
    - kimlik doğrulaması için SCEP sertifikalarını Wi-Fi profili için bağlama
    - kimlik doğrulaması için SCEP sertifikalarını VPN profillerine bağlama
    - SCEP sertifikalarını kimlik doğrulaması için e-posta profillerine bağlama (AppConfig aracılığıyla)
- Sistem uygulamaları, Android kurumsal cihazlarda desteklenir. Intune 'da, **ekle** > **Istemci uygulamaları** > **uygulamalar** ' ı seçerek bir Android kurumsal sistem uygulaması ekleyin. **Uygulama türü** listesinde, **Android kurumsal sistem uygulaması**' nı seçin. Daha fazla bilgi için bkz. [Microsoft Intune Android kurumsal sistem uygulamaları ekleme](../apps/apps-ae-system.md). <!-- 4062195 -->
- **Cihaz uyumluluğu** > **Android kurumsal** > **cihaz sahibi**bölümünde, Google SafetyNET kanıtlama düzeyini ayarlayan bir uyumluluk ilkesi oluşturabilirsiniz.   <!-- 4631425 -->
- Android kurumsal tam yönetilen cihazlarda, mobil tehdit savunma sağlayıcıları desteklenir. **Cihaz uyumluluğu** > **Android kurumsal** > **cihaz sahibi**' de, kabul edilebilir tehdit düzeyi seçebilirsiniz. <!-- 4631440 --> [Intune kullanarak cihazları uyumlu veya uyumsuz olarak işaretlemek Için Android kurumsal ayarları](../protect/compliance-policy-create-android-for-work.md#device-owner) geçerli ayarları listeler.
- Android kurumsal tam olarak yönetilen cihazlarda, Microsoft başlatıcı uygulaması artık tam olarak yönetilen cihazda standartlaştırılmış bir son kullanıcı deneyimine izin vermek için uygulama yapılandırma ilkeleri aracılığıyla yapılandırılabilir. Microsoft başlatıcısı uygulaması, Android cihazınızı kişiselleştirmek için kullanılabilir. Uygulamayı bir Microsoft hesabı veya iş/okul hesabıyla birlikte kullanarak, kişiselleştirilmiş akışınızdaki takvim, belgeleriniz ve son etkinliklerinize erişebilirsiniz. <!-- 5334044 -->

Bu güncelleştirmeyle, Android kurumsal tam olarak yönetilen Intune desteğinin artık genel kullanıma sunulduğunu duyurmaktan mutluluk duyuyoruz.

Uygulama hedefi:

- Android kurumsal tam yönetilen cihazlar

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Tek bir cihaza özel bildirimler gönderme<!-- 4928910 -->
Artık tek bir cihaz seçebilir ve ardından bir uzak cihaz eylemi kullanarak [yalnızca bu cihaza özel bir bildirim gönderebilirsiniz](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>Silme ve geçiş kodu sıfırlama eylemleri, Kullanıcı kaydı kullanılarak kaydedilen iOS cihazları için kullanılamaz<!-- 4950491 -->
Kullanıcı kaydı, yeni bir Apple cihaz kaydı türüdür. Kullanıcı kaydını kullanarak cihazları kaydettiğinizde, bu tür cihazlarda silme ve geçiş kodu sıfırlama uzak eylemleri kullanılamaz.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>İOS 13 ve macOS Catalina cihazları için Intune desteği<!-- 4665317 -->
Intune artık iOS 13 ve macOS Catalina cihazlarının yönetimini desteklemektedir.
Daha fazla bilgi için bkz. [iOS 13 ve ıpados blog gönderisi Microsoft Intune desteği](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Cihaz güvenliği

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>İstemci tabanlı kurtarma parolası dönüşü için BitLocker desteği<!--  3444125 -->
Windows sürüm 1909 veya üstünü çalıştıran cihazlarda BitLocker için [istemci odaklı kurtarma parolası döndürmeyi](../protect/endpoint-protection-windows-10.md#windows-encryption) yapılandırmak için Intune Endpoint Protection ayarlarını kullanın.

Bu ayar, bir işletim sistemi sürücüsü kurtarmasından (Bootmgr veya WinRE kullanılarak) ve bir sabit veri sürücüsünde kurtarma parolası kilidi açma işleminden sonra istemci temelli kurtarma parolası yenileme işlemini başlatır. Bu ayar, kullanılan belirli kurtarma parolasını yeniler ve birimdeki diğer kullanılmayan parolalar değişmeden kalır. Daha fazla bilgi için bkz. [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)IÇIN BitLocker CSP belgeleri.

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Windows Defender virüsten koruma için yetkisiz koruma<!-- 4705448        -->
Windows Defender virüsten koruma için yetkisiz *korumayı* yönetmek üzere Intune 'u kullanın. Windows 10 Endpoint Protection için cihaz yapılandırma profillerini kullanırken, Microsoft Defender güvenlik merkezi grubunda, yetkisiz [koruma ayarını](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) bulabilirsiniz. Temper koruma kısıtlamalarını açmak için devre dışı bırakma korumasını etkinleştirmek, devre dışı bırakmak için *devre dışı* bırakmak veya cihazları güncel yapılandırmayı yerinde bırakmak için*yapılandırılmamış* *olarak ayarlamanız* gerekir.  

Daha fazla koruma hakkında daha fazla bilgi için bkz. Windows belgelerindeki [güvenlik ayarlarını önleme korumasıyla](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) değiştirme.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>Windows Defender Güvenlik Duvarı Gelişmiş ayarları artık genel kullanıma sunuldu<!--  5317392       -->  
Cihaz yapılandırma profilinin bir parçası olarak yapılandırdığınız [Endpoint Protection Için Windows Defender özel güvenlik duvarı kuralları](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices)genel önizleme aşamasındadır ve genel olarak KULLANILABILIR (GA).  Uygulamalar, ağ adresleri ve bağlantı noktalarına gelen ve giden davranışı belirtmek için bu kuralları kullanabilirsiniz. Bu kurallar, Temmuz 'da genel önizleme olarak yayımlanmıştır. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863-idmiss---"></a>Kapsam etiketleri artık kullanım ilkeleri koşullarını destekliyor<!-- 2358863 idmiss -->
Artık kullanım ilkeleri koşullarına [kapsam etiketleri](scope-tags.md) atayabilirsiniz. Bunu yapmak için **ıntune** > **cihaz kaydı** > **hüküm ve koşullar** ' a gidin > listeden bir öğe seçin > **Özellikler** > **kapsam etiketleri** > kapsam etiketi seçin.

## <a name="week-of-september-9-2019"></a>9 Eylül 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Microsoft Intune uygulama güncelleştirmeleri<!-- 4997846 -->
Android için Microsoft Intune uygulaması aşağıdaki geliştirmelerle güncelleştirilmiştir:
- En önemli eylemler için alt gezinti eklemek üzere Düzen güncelleştirildi ve geliştirildi.
- Kullanıcının profilini gösteren ek bir sayfa eklendi.
- Kullanıcı için, cihaz ayarlarını güncelleştirme ihtiyacı gibi eyleme dönüştürülebilir bildirimlerin görüntüsü eklendi.
- İOS ve Android için Şirket Portalı uygulamasına son eklenen destek ile uygulamayı hizalamak için özel anında iletme bildirimlerinin görüntüsü eklendi. Daha fazla bilgi için bkz. [Intune 'da özel bildirimler gönderme](../remote-actions/custom-notifications.md).

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>İOS cihazları için Şirket Portalı kayıt işlemi gizlilik ekranını özelleştirin<!-- 4394993 -->
Marku kullanarak, son kullanıcıların iOS kaydı sırasında göreceği Şirket Portalı gizlilik ekranını özelleştirebilirsiniz. Özellikle, kuruluşunuzun cihazı göremeyecek veya cihaz üzerinde yapaamayacak işlerin listesini özelleştirebilirsiniz. Daha fazla bilgi için bkz. [Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md#privacy-statement-customization).


## <a name="week-of-september-2-2019"></a>2 Eylül 2019 haftası

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Intune kullanıcı arabirimi güncelleştirmesi – kiracı durumu panosu<!-- 5273210  -->
Kiracı durum panosu için Kullanıcı arabirimi, Azure Kullanıcı arabirimi stilleriyle hizalanacak şekilde güncelleştirilmiştir. Daha fazla bilgi için bkz. [kiracı durumu](../tenant-status.md).

## <a name="week-of-august-26-2019"></a>26 Ağustos 2019 haftası

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Windows 10 ve üzeri için Yönetim Şablonları kullanarak Microsoft Edge ayarlarını yapılandırma<!-- 5228061 -->

Windows 10 ve daha yeni cihazlarda, Intune 'da Grup İlkesi ayarlarını yapılandırmak için yönetim şablonları oluşturabilirsiniz. Bu güncelleştirmede, Microsoft Edge sürüm 77 ve daha yeni sürümleri için uygulanan ayarları yapılandırabilirsiniz.

Yönetim Şablonları hakkında daha fazla bilgi edinmek için bkz. [Intune 'da Grup İlkesi ayarlarını yapılandırmak Için Windows 10 şablonlarını kullanma](../configuration/administrative-templates-windows.md).

Uygulama hedefi:

- Windows 10 ve üzeri (Windows RS4 +)

## <a name="week-of-august-12-2019-1908-service-release"></a>12 Ağustos 2019 (1908 hizmet sürümü) haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Cihaz kaydı kaldırılırken iOS uygulaması kaldırma davranışını denetleme<!-- 3504144   -->
Yöneticiler, cihazın bir kullanıcı veya cihaz grubu düzeyinde kaydı kaldırıldığında cihazda bir uygulamanın kaldırılıp kaldırılmadığını veya korunduğunu yönetebilir. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Iş uygulamaları için Microsoft Store kategorilere ayırın<!-- 3926922 -->
Iş uygulamaları için Microsoft Store kategorilere ayırabilirsiniz. Bunu yapmak için **ıntune** > **Istemci uygulamaları** > **uygulamalar** ' ı seçin > Iş uygulaması > **uygulama bilgileri** > **kategorisi**Microsoft Store seçin. Açılan menüden bir kategori atayın.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Microsoft Intune uygulama kullanıcıları için özelleştirilmiş bildirimler<!-- 4843354  -->
Android için Microsoft Intune uygulaması artık özel anında iletme bildirimlerinin görüntülenmesini destekler, bu da iOS ve Android için Şirket Portalı uygulamalarına son eklenen destek ile hizalanmıştır. Daha fazla bilgi için bkz. [Intune 'da özel bildirimler gönderme](../remote-actions/custom-notifications.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Çok uygulama modundaki Android kurumsal adanmış cihazlar için yeni özellikler<!-- 3755304 3041943 3041946   -->

Intune 'da, Android kurumsal adanmış cihazlarınızda (**cihaz yapılandırma** > **profiller** > **bir bilgi noktası stili deneyiminizdeki özellikleri ve ayarları kontrol edebilirsiniz. yalnızca platform > cihaz sahibi **için Intune** > ** , profil türü için **cihaz kısıtlamaları** ).

Bu güncelleştirmede aşağıdaki özellikler ekleniyor:

- **Adanmış cihazlar** **çoklu uygulama** > : **Sanal giriş düğmesi** cihaza çekerek veya ekranda kayan, böylece kullanıcıların taşıyabilmesi için görüntülenebilir.
- **Adanmış cihazlar** **çoklu uygulama** > : **Flashlight erişimi** , kullanıcıların Flashlight kullanmasına izin verir. 
- **Adanmış cihazlar** **çoklu uygulama** > : **medya birimi denetimi** , kullanıcıların bir kaydırıcı kullanarak cihazın medya birimini denetlemesine olanak tanır. 
- **Adanmış cihazlar** **çoklu uygulama** > : **ekran koruyucuyu etkinleştirme**, özel bir görüntüyü yükleme ve ekran koruyucusuna ne zaman gösterildiğini denetleme.

Geçerli ayarları görmek için [Android kurumsal cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Uygulama hedefi:

- Android kurumsal adanmış cihazlar

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Android kurumsal tam olarak yönetilen cihazlar için yeni uygulama ve yapılandırma profilleri<!-- 3574215 3574238 3574235 3574232   -->
Profilleri kullanarak, Android kurumsal cihaz sahibi (tam olarak yönetilen) cihazlarınıza VPN, e-posta ve Wi-Fi ayarlarını uygulayan ayarları yapılandırabilirsiniz. Bu güncelleştirmede şunları yapabilirsiniz:

- Outlook, Gmail ve dokuz Iş e-posta ayarlarını dağıtmak için [uygulama yapılandırma ilkelerini](../apps/app-configuration-policies-use-android.md) kullanın.
- [Güvenilen kök sertifika ayarlarını](../protect/certificates-configure.md)dağıtmak için cihaz yapılandırma profillerini kullanın.
- [VPN](../configuration/vpn-settings-android-enterprise.md) ve [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) ayarlarını dağıtmak için cihaz yapılandırma profillerini kullanın.

> [!IMPORTANT]
> Bu özellikle, kullanıcılar VPN, Wi-Fi ve e-posta profilleri için Kullanıcı adı ve parolasıyla kimlik doğrular. Sertifika tabanlı kimlik doğrulaması şu anda kullanılamıyor.

Uygulama hedefi:  
- Android kurumsal cihaz sahibi (tam olarak yönetilen)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>Kullanıcılar macOS cihazlarında oturum açtıklarında açık olan uygulamaları, dosyaları, belgeleri ve klasörleri denetleyin<!--3914202   -->
MacOS cihazlarında özellikleri etkinleştirebilir ve yapılandırabilirsiniz (**cihaz yapılandırma** > **profilleri** > **profil** > ** türü Için platform > **cihaz özellikleri** için** MacOS). 

Bu güncelleştirmede, Kullanıcı kayıtlı cihazda oturum açtığında hangi uygulamaların, dosyaların, belgelerin ve klasörlerin açık olduğunu denetleyen yeni bir oturum açma öğeleri ayarı vardır. 

Geçerli ayarları görmek için [Intune 'Da MacOS cihaz özelliği ayarları](../configuration/macos-device-features-settings.md)' na gidin.

Uygulama hedefi:  
- Mac OS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Son tarihler Windows Update halkalar için bağlı yeniden başlatma ayarlarını değiştirir<!-- 4464404        -->
Intune ['un Windows 10](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing)güncelleştirme halkaları, son [tarihleri için ayarları desteklemeye yöneliktir](../protect/windows-update-settings.md). *Son tarihler* , bir cihazın özellik ve güvenlik güncelleştirmelerini ne zaman yükleceğini belirlenir.  Windows 10 1903 veya üzerini çalıştıran cihazlarda, *son tarihleri* , ara *yeniden başlatma*yapılandırmalarının yerini alır.  Gelecekte, *son tarihleri* Windows 10 ' un önceki sürümlerinde de *bağlı yeniden başlatmanın* yerini alır.  

*Son tarihleri*yapılandırma ' ya yönelik cihaz, cihazların ara *yeniden* başlatma ayarlarını kullanmaya devam eder, ancak Intune, gelecekteki bir güncelleştirmede, ara yeniden başlatma ayarları desteğini kullanımdan kaldırır.  

Tüm Windows 10 cihazlarınız için *son tarihleri* kullanmayı planlayın. *Son tarihler* için ayarlar gerçekleştirildikten sonra, Intune yapılandırmalarınızı, ara *yeniden başlatmaya* yönelik olarak yapılandırmak üzere değiştirebilirsiniz. , Yapılandırılmadı olarak ayarlandığında, Intune bu ayarları cihazlarda yönetmeyi bırakır, ancak bu ayarın son yapılandırmasını cihazdan kaldırmaz. Bu nedenle, etkin *yeniden başlatma* için ayarlanan son yapılandırma, bu ayarlar Intune dışında bir yöntem tarafından değiştirilene kadar etkin ve cihazlarda kullanımda kalır. Daha sonra, Windows 'un cihazlar sürümü değiştiğinde ya da *son tarihleri* için Intune desteği cihazların Windows sürümüne genişlediğinde cihaz, zaten yerinde olan yeni ayarları kullanmaya başlayacaktır.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Birden çok Microsoft Intune sertifika Bağlayıcısı desteği<!--   4704642      -->
Intune artık, [PKCS işlemleri için birden çok Microsoft Intune sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md)yüklemeyi ve kullanımını desteklemektedir. Bu değişiklik, bağlayıcının yük dengelemesini ve yüksek kullanılabilirliğini destekler. Her bağlayıcı örneği, Intune 'dan gelen sertifika isteklerini işleyebilir.  Bir bağlayıcı kullanılamıyorsa, diğer bağlayıcılar istekleri işlemeye devam eder.

Birden çok bağlayıcı kullanmak için bağlayıcı yazılımının en son sürümüne yükseltmeniz gerekmez.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>İOS ve macOS cihazlarındaki özellikleri kısıtlamak için yeni ayarlar ve var olan ayarlarda yapılan değişiklikler<!-- 4867699 4867709   -->
İOS ve**ma > cos** çalıştıran cihazlarda ayarları **kısıtlamak için profiller** oluşturabilir, platform türü > **cihaz kısıtlamaları**için **ios** veya **MacOS** > **profil oluşturma** > . Bu güncelleştirme aşağıdaki özellikleri içerir:

- **Macos** > **bulut ve depolama** > **cihaz kısıtlamalarında** , kullanıcıların bir MacOS cihazında iş başlatmasını engellemek için yeni **Iletim** ayarını kullanın ve başka bir MacOS veya iOS cihazında çalışmaya devam edin.

  Geçerli ayarları görmek için, [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak üzere MacOS cihaz ayarları](../configuration/device-restrictions-macos.md)' na gidin.

- **İOS** > **cihaz kısıtlamalarında**birkaç değişiklik vardır:

  - **Yerleşik uygulamalar** > **IPhone 'umu bul (yalnızca denetimli)**: uygulamamı bul özelliğinde bu özelliği engelleyen yeni ayar. 
  - **Yerleşik uygulamalar** > **Arkadaşlarımı bul (yalnızca denetimli)**: uygulamamı bul özelliğinde bu özelliği engelleyen yeni ayar. 
  - **** **Wi-fi durumunun kablosuz > değişikliği (yalnızca denetimli)**: kullanıcıların cihazda Wi-Fi ' i açmasını veya kapatmasını engelleyen yeni ayar.
  - **Klavye ve sözlük** > **hızlı yol (yalnızca denetimli)**: QuickPath özelliğini engelleyen yeni ayar.
  - **Bulut ve depolama**: **etkinlik devamlılığı** iletime olarak yeniden **adlandırıldı.**

  Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama hedefi:  
- macOS 10,15 ve üzeri
- iOS 13 ve üzeri

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Denetlenmeyecek bazı iOS cihaz kısıtlamaları yalnızca iOS 13,0 sürümüyle denetimli olacak.<!-- 4867809   -->
Bu güncelleştirmede, bazı ayarlar iOS 13,0 sürümü ile yalnızca denetimli cihazlar için geçerlidir. Bu ayarlar yapılandırıldıysa ve iOS 13,0 sürümünden önce denetlenmeden önce cihazlara atanırsa, ayarlar hala bu denetlenmeden bu cihazlara uygulanır. Cihazlar iOS 13,0 ' e yükseltildikten sonra da hala geçerlidir. Bu kısıtlamalar, yedeklenen ve geri yüklenen denetimli cihazlarda kaldırılır.

Bu ayarlar şunlardır:

- Uygulama Mağazası, Belge Görüntüleme, Oyun
  - Uygulama mağazası
  - Açık iTunes, müzik, podcast veya News içeriği
  - Game Center arkadaş ekleme
  - Çok oyunculu oyun
- Yerleşik Uygulamalar
  - Kamera
    - FaceTime
  - Safari
    - İse
- Bulut ve Depolama
  - İCloud 'a yedekleme
  - İCloud Belge eşitlemesini engelle
  - İCloud Anahtarlık eşitlemesini engelle

Geçerli ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md).

Uygulama hedefi:  
- iOS 13,0 ve üzeri

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>MacOS Filekasası şifrelemesi için iyileştirilmiş cihaz durumu<!-- 4944983         -->
MacOS cihazlarında dosya Kasası şifrelemesi için birçok [cihaz durumu iletisini](../protect/encryption-monitor.md#device-encryption-status) güncelleştirdik.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Raporlamadaki bazı Windows Defender virüsten koruma tarama ayarları başarısız durumu gösteriyor<!-- 5119229 -->
Intune 'da Windows 10 cihazlarınızı (**cihaz yapılandırma** > **profilleri** > profil > **oluşturmak** Için Windows **10 ve üzeri** Windows **defender virüsten koruma**) profil > türü için Platform > **cihaz kısıtlamaları** için Windows Defender virüsten koruma kullanmak üzere ilke oluşturabilirsiniz. **Günlük hızlı tarama gerçekleştirme süresi** ve raporlama **gerçekleştirmek Için sistem taraması türü** , aslında başarılı bir durum olduğunda başarısız durumu gösterir. 

Bu güncelleştirmede, bu davranış düzeltilmiştir. Bu nedenle, ayarları gerçekleştirmek için **günlük hızlı tarama** ve **sistem taraması türü** , taramalar başarıyla tamamlandığında başarı durumunu gösterir ve ayarlar uygulanamadığında başarısız bir durum gösterir.

Windows Defender virüsten koruma ayarları hakkında daha fazla bilgi için bkz. [Windows 10 (ve daha yeni) cihaz ayarları Intune kullanarak özellik sağlamak veya kısıtlamak için](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="default-scope-tags---3702875----"></a>Varsayılan kapsam etiketleri<!-- 3702875  -->
Yeni bir yerleşik varsayılan kapsam etiketi artık kullanılabilir. Kapsam etiketlerini destekleyen tüm etiketli Intune nesneleri varsayılan kapsam etiketine otomatik olarak atanır. **Varsayılan** kapsam etiketi, günümüzde yönetici deneyimiyle eşliği sağlamak için mevcut tüm rol atamalarına eklenir. Yöneticinin varsayılan kapsam etiketiyle Intune nesnelerini görmesini istemiyorsanız, varsayılan kapsam etiketini rol atamasından kaldırın. Bu özellik, System Center Configuration Manager güvenlik kapsamları özelliğine benzer. Daha fazla bilgi için bkz. [Dağıtılmış BT IÇIN RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Android kayıt cihazı yöneticisi desteği<!-- 4869749   -->
Android Cihaz Yöneticisi kayıt seçeneği, Android kayıt sayfasına (**ıntune** > **cihaz kaydı** > **Android kaydı**) eklenmiştir. Android Cihaz Yöneticisi, tüm kiracılar için varsayılan olarak hala etkinleştirilecek.  Daha fazla bilgi için bkz. [Android Cihaz Yöneticisi kaydı](../enrollment/android-enroll-device-administrator.md).

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Kurulum Yardımcısı 'nda daha fazla ekran atlayın <!--4877451  -->
Aşağıdaki Kurulum Yardımcısı ekranlarını atlamak için Aygıt Kayıt Programı profilleri ayarlayabilirsiniz:
- iOS için
    - Görünüm
    - Hızlı dil
    - Tercih edilen dil
    - Cihazdan cihaza geçişe
- MacOS için
    - Ekran zamanı
    - Dokunma KIMLIĞI kurulumu

Kurulum Yardımcısı özelleştirmesi hakkında daha fazla bilgi için bkz. [iOS Için Apple kayıt profili oluşturma](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) ve [MacOS için Apple kayıt profili oluşturma ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile).

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Autopilot Device CSV yükleme işlemine bir kullanıcı sütunu ekleyin<!-- 3823054 -->
Artık Autopilot cihazlara CSV yüklemesine bir kullanıcı sütunu ekleyebilirsiniz. Bu, CSV 'yi içeri aktarırken kullanıcıları toplu olarak atayabilmenizi sağlar. Daha fazla bilgi için bkz. [Windows Autopilot kullanarak Intune 'Da Windows cihazlarını kaydetme](../enrollment/enrollment-autopilot.md).


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>Otomatik cihaz temizleme süresi limitini 30 güne kadar yapılandırma<!--4231059  -->
Otomatik cihaz temizleme süresi sınırını, son oturum açma işleminden sonra 30 gün (önceki 90 gün yerine) kadar kısa bir süre sonra ayarlayabilirsiniz. Bunu yapmak için **ıntune** > **cihazlar** ' a gidin > **Cihaz Temizleme kurallarını** > **ayarlayın** .

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Android cihaz donanımı sayfasına dahil edilen derleme numarası<!-- 4461910   -->
Her Android cihazının donanım sayfasında yeni bir giriş, cihazın işletim sistemi yapı numarasını içerir. Daha fazla bilgi için bkz. [Intune 'da cihaz ayrıntılarını görüntüleme](../remote-actions/device-inventory.md).


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>5 Ağustos 2019 haftası

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>Zeköşeli teknolojiler, Android kurumsal cihazlarda OEMConfig için desteklenen bir OEM 'dir<!-- 4843713 -->

Intune 'da, cihaz yapılandırma profilleri oluşturabilir ve OEMConfig (**cihaz yapılandırma** > **profilleri ' ni kullanarak Android enterprise cihazlarına ayarlar uygulayabilir ** > **profil türü için bkz** > **Android Enterprise** for platform > **oemconfig** ).

Bu güncelleştirmede, Zeköşeli teknolojiler, OEMConfig için desteklenen bir özgün ekipman üreticisi (OEM). OEMConfig hakkında daha fazla bilgi için bkz. [oemconfig Ile Android kurumsal cihazlarını kullanma ve yönetme](../configuration/android-oem-configuration-overview.md).

Uygulama hedefi:  
- Android kurumsal

<!-- ########################## -->

## <a name="week-of-july-22-2019-1907-service-release"></a>22 Temmuz 2019 haftası (1907 hizmet sürümü)

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Kullanıcılar ve gruplar için özelleştirilmiş bildirimler<!-- 16766574          -->
Intune ile yönettiğiniz iOS ve Android cihazlarda kullanıcılara Şirket Portalı uygulamadan özel anında iletme bildirimleri gönderin. Bu mobil anında iletme bildirimleri, ücretsiz metinle yüksek düzeyde özelleştirilebilir ve herhangi bir amaçla kullanılabilir. Bunları kuruluşunuzdaki farklı Kullanıcı gruplarına hedefleyebilirsiniz. Daha fazla bilgi için bkz. [özel bildirimler](../remote-actions/custom-notifications.md).

#### <a name="googles-device-policy-controller-app---3041950----"></a>Google 'ın cihaz Ilkesi denetleyicisi uygulaması<!-- 3041950  -->
Yönetilen giriş ekranı uygulaması artık Google 'ın Android cihaz Ilkesi uygulamasına erişim sağlar. Yönetilen giriş ekranı uygulaması, Intune 'A kayıtlı cihazlar için çok uygulama bilgi noktası modunu kullanan Android kurumsal (AE) adanmış cihazlar olarak kullanılan özel bir başlatıdır. Android cihaz Ilkesi uygulamasına erişebilir veya destek ve hata ayıklama amacıyla kullanıcılara Android cihaz Ilkesi uygulamasına rehberlik edebilirsiniz. Bu başlatma özelliği, cihazın ne zaman kaydolur ve yönetilen giriş ekranına kilitlediği sırada kullanılabilir. Bu işlevselliği kullanmak için ek yükleme gerekmez.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>İOS ve Android cihazlar için Outlook koruması ayarları<!-- 3212619 -->
Artık, cihaz kaydı olmadan basit Intune yönetici denetimlerini kullanarak iOS ve Android için Outlook için hem genel uygulama hem de veri koruma yapılandırma ayarlarını yapılandırabilirsiniz. Genel uygulama yapılandırma ayarları, yöneticilerin iOS ve Android 'e kayıtlı cihazlarda Outlook 'U yönetirken Etkinleştirebileceği ayarlar ile eşlik sağlar. Outlook ayarları hakkında daha fazla bilgi için bkz. [iOS ve Android Için Outlook dağıtımı yapılandırma ayarları](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready------"></a>Windows 10 cihaz yapılandırma profilleri oluştururken "uygulanabilirlik kuralları" nı kullanın <!-- 2549910 eeready    -->

Windows 10 cihaz yapılandırma profilleri oluşturun (**cihaz yapılandırma** > **profilleri** > platform > **uygulanabilirlik kuralları**için **Windows 10** > **profil oluşturma** ). Bu güncelleştirmede, profil yalnızca belirli bir sürüm veya belirli bir sürüm için geçerli olacak şekilde bir **uygulanabilirlik kuralı** oluşturabilirsiniz. Örneğin, bazı BitLocker ayarlarını sağlayan bir profil oluşturursunuz. Profili ekledikten sonra, profilin yalnızca Windows 10 Enterprise çalıştıran cihazlara uygulanması için bir uygulanabilirlik kuralı kullanın.

Bir uygulanabilirlik kuralı eklemek için bkz. [uygulanabilirlik kuralları](../configuration/device-profile-create.md#applicability-rules).

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>İOS ve macOS cihazları için özel profillere cihaza özgü bilgileri eklemek için belirteçleri kullanın<!-- 3330008  -->
İOS ve macOS cihazlarında özel profilleri, Intune 'da yerleşik olarak bulunmayan ayarları ve özellikleri yapılandırmak için (**cihaz yapılandırma** > **profilleri** > **profil** > ** türü için özel** platform > için **iOS** veya **MacOS** ) kullanabilirsiniz. Bu güncelleştirmede, cihaza özgü bilgileri eklemek için `.mobileconfig` dosyalarınıza belirteç ekleyebilirsiniz. Örneğin, cihazın seri numarasını göstermek için yapılandırma dosyanıza `Serial Number: {{serialnumber}}` ekleyebilirsiniz.

Özel bir profil oluşturmak için bkz. [iOS özel ayarları](../configuration/custom-settings-ios.md) veya [MacOS özel ayarları](../configuration/custom-settings-macos.md).

Uygulama hedefi:
- iOS
- Mac OS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Android Enterprise için bir OEMConfig profili oluştururken yeni yapılandırma Tasarımcısı<!-- 3712769   -->
Intune 'da, bir OEMConfig uygulaması kullanan bir cihaz yapılandırma profili oluşturabilirsiniz (cihaz yapılandırma > profilleri > > SDK için Android Enterprise > profil türü için OEMConfig). Bunu yaptığınızda bir JSON Düzenleyicisi, değiştirmeniz için bir şablon ve değerlerle açılır. 

Bu güncelleştirme; başlıklar, açıklamalar ve daha fazlası dahil olmak üzere uygulamada Embedded ayrıntıları gösteren gelişmiş bir kullanıcı deneyimine sahip bir yapılandırma Tasarımcısı içerir. JSON Düzenleyicisi hala kullanılabilir ve yapılandırma tasarımcısında yaptığınız tüm değişiklikleri gösterir.

Geçerli ayarları görmek için, bkz. [OEMConfig Ile Android kurumsal cihazlarını kullanma ve yönetme](../configuration/android-oem-configuration-overview.md).

Uygulama hedefi: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Windows Hello 'Yu yapılandırmak için güncelleştirilmiş Kullanıcı arabirimi<!-- 4089576            -->
[Intune 'U iş Için Windows Hello 'yu kullanacak şekilde yapılandırdığınız](../protect/windows-hello.md)konsolu güncelleştirdik. Tüm yapılandırma ayarları artık konsolun Windows Hello desteğini etkinleştirdiğiniz bölmesinde de mevcuttur.

#### <a name="intune-powershell-sdk---4924113---"></a>Intune PowerShell SDK 'Sı<!-- 4924113 --> 
Intune API 'SI için Microsoft Graph aracılığıyla destek sağlayan Intune PowerShell SDK, 6.1907.1.0 sürümüne güncelleştirilmiştir. SDK artık şunları desteklemektedir:
- Azure Otomasyonu ile birlikte kullanılır.
- Yalnızca uygulama kimlik doğrulama okuma işlemlerini destekler. 
- Kolay kısaltılmış adları diğer ad olarak destekler.
- PowerShell adlandırma kurallarına uyar. Özellikle, `PSCredential` parametresi (`Connect-MSGraph` cmdlet 'inde) `Credential`olarak yeniden adlandırıldı.
- `Invoke-MSGraphRequest` cmdlet 'i kullanılırken `Content-Type` üst bilgisinin değerini el ile belirtmeyi destekler.

Daha fazla bilgi için bkz. [Microsoft Intune Graph API Için POWERSHELL SDK](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune).


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Kayıt kısıtlamaları için güncelleştirmeler<!-- 2871968 -->
Yeni kiracılar için kayıt kısıtlamaları, Android kurumsal iş profillerinin varsayılan olarak izin verdiği şekilde güncelleştirilmiştir. Mevcut kiracılar hiçbir değişikliğe karşı karşılaşacaktır. Android kurumsal iş profillerini kullanmak için yine de [Intune hesabınızı yönetilen Google Play hesabınıza bağlamanız](../enrollment/connect-intune-android-enterprise.md)gerekir.

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>Apple kaydı ve kayıt kısıtlamaları için Kullanıcı Arabirimi güncelleştirmeleri<!--4089575, 4089579  -->
Aşağıdaki işlemlerin her ikisi de bir sihirbaz stili Kullanıcı arabirimi kullanır:
- Apple cihaz kaydı. Daha fazla bilgi için bkz. [Apple aygıt kayıt programı iOS cihazlarını otomatik olarak kaydetme](../enrollment/device-enrollment-program-enroll-ios.md).
- Kayıt kısıtlaması oluşturma. Daha fazla bilgi için bkz. [kayıt kısıtlamalarını ayarlama](../enrollment/enrollment-restrictions-set.md).

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509--idmiss---"></a>Android Q cihazları için kurumsal cihaz tanımlayıcılarının ön yapılandırmasını işleme<!-- 4711509  idmiss -->
Android soru-cevap (ile v10 arasındaki) içinde, Google, eski yönetilen (Cihaz Yöneticisi) Android cihazlarındaki MDM aracılarının cihaz tanımlayıcı bilgilerini toplamasını sağlayacak özelliği kaldırır.  Intune, BT yöneticilerinin bu cihazları şirkete ait olarak otomatik olarak etiketleyebilmesi için [cihaz seri numaralarının bir listesini önceden yapılandırmasını](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) sağlayan bir özelliğe sahiptir. Bu özellik cihaz yöneticisi tarafından yönetilen Android Q cihazları için çalışmaz.  Cihazın seri numarası veya ıMEı 'nin karşıya yüklenip yüklenmediğine bakılmaksızın, Intune kaydı sırasında her zaman kişisel olduğu kabul edilir.  Kayıt işleminden sonra sahipliğini el ile şirkete geçirebilirsiniz.  Bu yalnızca yeni kayıtları etkiler ve mevcut kayıtlı cihazlar etkilenmez.  İş profilleriyle yönetilen Android cihazları bu değişiklikten etkilenmez ve bugün olduğu gibi çalışmaya devam edecektir.  Buna ek olarak, cihaz yöneticisi olarak kaydedilen Android Q cihazları artık Intune konsolundaki seri numarasını veya ıMEı 'yi cihaz özellikleri olarak bildiremeyecektir.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Android kurumsal kayıtları (iş profili, adanmış cihazlar ve tam olarak yönetilen cihazlar) için simgeler değiştirilmiştir<!-- 4977730 -->
Android kurumsal kayıt profillerinin simgeleri değişmiştir. Yeni simgeleri görmek için **ıntune** > **kaydı** > **Android kaydı** > **kayıt profilleri**bölümüne bakın.


#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Windows tanılama veri koleksiyonu değişikliği<!-- 4113859 -->
Windows 10, sürüm 1903 ve üzeri sürümleri çalıştıran cihazlarda tanılama veri toplama için varsayılan değer değişmiştir. Windows 10 1903 ile başlayarak, tanılama veri toplama varsayılan olarak etkindir. Windows Tanılama verileri, Windows cihazlarından, cihaz ve Windows ile ilgili yazılımların nasıl çalıştığı hakkında önemli teknik verilere sahiptir. Daha fazla bilgi için bkz. [Kuruluşunuzda Windows tanılama verilerini yapılandırma](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization). Autopilot cihazlar, aksi durumda [System/Allowtelemetri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)ile Autopilot profilinde ayarlanmamışsa, "tam" telemetrisine de sahiptir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="improve-device-location---3855417----"></a>Cihaz konumunu iyileştirme<!-- 3855417  -->
**Cihazı bul** eylemini kullanarak bir cihazın tam koordinatlarıyla yakınlaştırma yapabilirsiniz. Kayıp iOS cihazlarını bulma hakkında daha fazla bilgi için bkz. [kayıp iOS cihazlarını bulma](../remote-actions/device-locate.md).

### <a name="device-security"></a>Cihaz güvenliği

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Windows Defender güvenlik duvarı için Gelişmiş ayarlar (Genel Önizleme)<!--  1311949     -->  
Windows 10 ' da Endpoint Protection için [cihaz yapılandırma profilinin bir parçası olarak özel güvenlik duvarı kurallarını](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) yönetmek Için Intune 'u kullanın. Kurallar, uygulamalar, ağ adresleri ve bağlantı noktaları için gelen ve giden davranışı belirtebilir. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Güvenlik temellerini yönetmek için güncelleştirilmiş Kullanıcı arabirimi<!-- 4091125     -->
Güvenlik temellerimiz için Intune konsolundaki [oluşturma ve düzenleme deneyimini](../protect/security-baselines.md#create-the-profile) güncelleştirdik. Değişiklikler şunları içerir:

Tek bir dikey pencereye daraltılmış daha basit bir sihirbaz stili biçimi. bir dikey pencere içinde. Bu yeni tasarım, BT uzmanlarının birkaç ayrı bölmeye detaya gitmeyi gerektiren dikey pencere genişlemesine.  
Artık, temelleri atamak için daha sonra dönmek zorunda kalmak yerine oluşturma ve düzenleme deneyiminin bir parçası olarak atamalar oluşturabilirsiniz. Yeni bir taban çizgisi oluşturmadan ve mevcut bir temeli düzenlediğinizde, görüntüleyebileceğiniz ayarların bir özetini ekledik. Düzenleme sırasında, Özet yalnızca düzenlenmekte olan özelliklerin bir kategorisi içinde ayarlanan öğelerin listesini gösterir.

<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>15 Temmuz 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Yönetilen giriş ekranı ve yönetilen ayarlar simgeleri<!-- 4918107 -->
Yönetilen giriş ekranı uygulaması simgesi ve **yönetilen ayarlar** simgesi güncelleştirildi. Yönetilen giriş ekranı uygulaması yalnızca Intune 'A Android kurumsal (AE) adanmış cihazlar olarak kaydedilmiş ve çok uygulama bilgi noktası modunda çalışan cihazlar tarafından kullanılır. Yönetilen giriş ekranı uygulaması hakkında daha fazla bilgi için bkz. [Android Enterprise Için Microsoft yönetilen giriş ekranı uygulamasını yapılandırma](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Android kurumsal adanmış cihazlarda Android cihaz Ilkesi<!-- 4918136 -->
Android cihaz Ilkesi uygulamasına, yönetilen giriş ekranı uygulamasının hata ayıklama ekranından erişebilirsiniz. Yönetilen giriş ekranı uygulaması yalnızca Intune 'A Android kurumsal (AE) adanmış cihazlar olarak kaydedilmiş ve çok uygulama bilgi noktası modunda çalışan cihazlar tarafından kullanılır. Daha fazla bilgi için bkz. [Android Enterprise Için Microsoft yönetilen giriş ekranı uygulamasını yapılandırma](../apps/app-configuration-managed-home-screen-app.md).

#### <a name="ios-company-portal-updates---3902931---"></a>iOS Şirket Portalı güncelleştirmeleri<!-- 3902931 -->
İOS uygulama yönetimi istemlerinde şirketinizin adı, geçerli "i.manage.microsoft.com" metninin yerini alır. Örneğin, kullanıcılar Şirket Portalı bir iOS uygulaması yüklemeye çalıştıklarında veya kullanıcılar uygulamanın yönetimine izin vereceği zaman, kullanıcılar şirket adını "i.manage.microsoft.com" yerine görür. Bu, önümüzdeki birkaç gün içinde tüm müşterilere alınacaktır.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>MacOS için dosya kasasını yönetme<!--  3858502 + 4557986 + 1210104  -->
[MacOS cihazları Için dosya Kasası anahtar şifrelemesini yönetmek](../protect/encrypt-devices.md)üzere Intune 'u kullanabilirsiniz. Cihazları şifrelemek için bir Endpoint Protection cihaz yapılandırma profili kullanırsınız.

Dosya Kasası desteğiniz şifrelenmemiş cihazları şifreleme, bir cihaz kişisel kurtarma anahtarı, kişisel şifreleme anahtarlarının otomatik veya el ile dönüşü ve şirket cihazlarınız için anahtar alımı içerir. Son kullanıcılar, şifreli cihazlarına kişisel kurtarma anahtarını almak için Şirket Portalı Web sitesini de kullanabilir.

Ayrıca, tüm cihaz şifreleme ayrıntılarınızı tek bir yerde görüntüleyebilmeniz için, şifreleme raporunu BitLocker 'a yönelik dosya tarafı bilgileri [hakkında bilgi](../protect/encryption-monitor.md) içerecek şekilde genişlettik.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>Windows Autopilot sıfırlaması cihazın birincil kullanıcısını kaldırır<!-- 4156123 -->
Bir cihazda Autopilot Reset kullanıldığında, cihazın birincil kullanıcısı kaldırılır. Sıfırlamadan sonra oturum açan bir sonraki Kullanıcı, birincil kullanıcı olarak ayarlanır. Bu özellik önümüzdeki birkaç gün içinde tüm müşterilere alınacaktır.

## <a name="week-of-july-8-2019"></a>8 Temmuz 2019 haftası

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Windows 10 Yönetim şablonlarında yeni Office, Windows ve OneDrive ayarları <!-- 3510695 -->

Intune 'da, şirket içi Grup İlkesi Yönetimi 'ni taklit eden Yönetim şablonları oluşturabilirsiniz (**cihaz yönetimi** > **profilleri** > profil **oluşturmak** için **Windows 10 ve > üzeri** > profil türü için **yönetim şablonu** ).

Bu güncelleştirme, şablonlarınıza ekleyebileceğiniz diğer Office, Windows ve OneDrive ayarlarını içerir. Bu yeni ayarlarla artık %100 bulut tabanlı 2500 ' den fazla ayarı yapılandırabilirsiniz.

Bu özellik hakkında daha fazla bilgi edinmek için bkz. [Intune 'da Grup İlkesi ayarlarını yapılandırmak Için Windows 10 şablonlarını kullanma](../configuration/administrative-templates-windows.md).

Şunlar için geçerlidir: Windows 10 ve üzeri

## <a name="week-of-july-1-2019"></a>1 Temmuz 2019 haftası 

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="aad-and-app-on-android-enterprise-devices---3574267---"></a>Android kurumsal cihazlarda AAD ve uygulama<!-- 3574267 -->
Tam olarak yönetilen Android Kurumsal cihazları eklerken, kullanıcılar yeni veya fabrika sıfırlaması cihazının ilk kurulumu sırasında artık Azure Active Directory (AAD) ile kaydolacaktır. Daha önce tam olarak yönetilen bir cihaz için, Kurulum tamamlandıktan sonra kullanıcının AAD kaydını başlatmak üzere Microsoft Intune uygulamasını el ile başlatması gerekiyordu. Artık Kullanıcı İlk kurulumdan sonra cihaz giriş sayfasına kaydolduğunda, cihazın kaydı kaydedilir ve kaydedilir.

AAD güncelleştirmelerine ek olarak, Intune uygulama koruma ilkeleri (uygulama) artık tam olarak yönetilen Android kurumsal cihazlarda desteklenmektedir. Bu işlev, geliştirdiğimiz için kullanılabilir hale gelir. Daha fazla bilgi için bkz. [Intune Ile Android Enterprise cihazlarına yönetilen Google Play uygulamaları ekleme](../apps/apps-add-android-for-work.md).

## <a name="week-of-june-24-2019-1906-service-release"></a>24 Haziran 2019 (1906 hizmet sürümü) haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Hangi tarayıcının kuruluş verilerine bağlantı yapmasına izin verileceğini yapılandırın<!-- 3145939 -->
Android ve iOS cihazlarında Intune Uygulama Koruması Ilkeleri (uygulama) artık Intune Managed Browser veya Microsoft Edge 'in ötesinde belirli bir tarayıcıya kuruluş web bağlantıları aktarmanızı sağlar.  UYGULAMA hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](../apps/app-protection-policy.md).

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Tüm uygulamalar sayfası Iş uygulamaları için çevrimiçi/çevrimdışı Microsoft Store tanımlar<!--4089647 -->
**Tüm uygulamalar** sayfası artık çevrimiçi veya çevrimdışı uygulamalar olarak Microsoft Store for Business (msfb) uygulamalarını belirlemek için etiketleme içerir. Her bir MSFB uygulaması artık **çevrimiçi** veya **çevrimdışı**için bir sonek içeriyor. Uygulama Ayrıntıları sayfası, **lisans türünü** de içerir ve **cihaz bağlamı yüklemeyi destekler** (yalnızca çevrimdışı lisanslı uygulamalar) bilgileri de vardır.

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Windows paylaşılan cihazlarında uygulama Şirket Portalı<!--4393553 -->
Kullanıcılar artık Windows paylaşılan cihazlarındaki Şirket Portalı uygulamasına erişebilir. Son kullanıcılar cihaz kutucuğunda **paylaşılan** bir etiket görür. Bu, Windows Şirket Portalı App sürümü 10.3.45609.0 ve üzeri için geçerlidir.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Yeni Şirket Portalı Web sayfasından yüklü tüm uygulamaları görüntüle<!-- 4224326 -->
Şirket Portalı Web sitesinin yeni **yüklü uygulamalar** sayfasında, bir kullanıcının cihazlarında yüklü olan tüm yönetilen uygulamalar (hem gerekli hem de kullanılabilir) listelenir. Atama türüne ek olarak, kullanıcılar uygulamanın yayımcısını, yayımlanma tarihini ve geçerli yükleme durumunu görebilirler. Kullanıcılarınız için gerekli veya kullanılabilir bir uygulama yapmadıysanız, hiçbir şirket uygulaması yüklenmediğini açıklayan bir ileti görür. Web 'deki yeni sayfayı görmek için [Şirket portalı Web sitesine](https://portal.manage.microsoft.com) gidin ve **yüklü uygulamalar**' a tıklayın.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>Yeni görünüm, uygulama kullanıcılarının cihazda yüklü olan tüm yönetilen uygulamaları görmesini sağlar<!-- 2352913 -->  
Windows için Şirket Portalı uygulaması artık bir kullanıcının cihazında yüklü olan tüm yönetilen uygulamaları (hem gerekli hem de kullanılabilir) listeler. Kullanıcılar ayrıca, denenen ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını görebilir. Kullanıcılarınız için gerekli olan veya kullanıcılarınızın kullanabildiği uygulamalar yapmadıysanız, hiçbir şirket uygulaması yüklenmediğini açıklayan bir ileti görür. Yeni görünümü görmek için Şirket Portalı gezinti bölmesine gidin ve **uygulamalar** > **yüklü uygulamalar**' ı seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>MacOS cihazlarında çekirdek uzantıları ayarlarını yapılandırma<!-- 2043024 -->
MacOS cihazlarında bir cihaz yapılandırma profili (**cihaz yapılandırma** > **profil oluşturma** > **platform** için **MacOS** seçin) oluşturabilirsiniz. Bu güncelleştirme, cihazlarınız üzerinde çekirdek uzantıları yapılandırmanıza ve kullanmanıza olanak sağlayan yeni bir ayar grubu içerir. Belirli uzantıları ekleyebilir veya belirli bir iş ortağının veya geliştiriciden tüm uzantılara izin verebilirsiniz.

Bu özellik hakkında daha fazla bilgi edinmek için bkz. [çekirdek uzantılarına genel bakış](../configuration/kernel-extensions-overview-macos.md) ve [çekirdek uzantısı ayarları](../configuration/kernel-extensions-settings-macos.md).

Uygulama hedefi: macOS 10.13.2 ve üzeri

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>Yalnızca Windows 10 cihazları için mağaza ayarındaki uygulamalar daha fazla yapılandırma seçeneği içerir<!-- 2697002 -->
Windows cihazları için bir cihaz kısıtlamaları profili oluşturduğunuzda, kullanıcıların uygulamaları yalnızca Windows App Store 'dan (**cihaz yapılandırma** > **profilleri** > profil **oluşturmak** için **Windows 10 ve > üzeri** > profil türü için **cihaz kısıtlamaları** ) yüklemesini sağlamak üzere **yalnızca mağaza** ayarından kullanabilirsiniz. Bu güncelleştirmede, daha fazla seçenek desteklemek için bu ayar genişletilir.

Yeni ayarı görmek için, [özelliklere izin vermek veya erişimi kısıtlamak üzere Windows 10 (ve daha yeni) cihaz ayarları](../configuration/device-restrictions-windows-10.md#app-store)' na gidin.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Bir cihaza, aynı kullanıcı grubuna veya aynı cihazlar grubuna birden çok Zeköşeli Mobility uzantıları cihaz profili dağıtma<!-- 4089955 -->
Intune 'da yerleşik olmayan Zeköşeli cihazlara yönelik ayarları özelleştirmek için bir cihaz yapılandırma profilinde Zeköşeli Mobility uzantıları (MX) kullanabilirsiniz. Şu anda tek bir cihaza bir profil dağıtabilirsiniz. Bu güncelleştirmede, aşağıdakileri yapmak için birden çok profil dağıtabilirsiniz:
- Aynı kullanıcı grubu
- Aynı cihazlar grubu
- Tek bir cihaz

[Microsoft Intune ' deki Zeköşeli Mobility uzantıları Ile zeköşeli cihazlarını kullanın ve yönetin](../configuration/android-zebra-mx-overview.md) ıNTUNE 'da MX 'in nasıl kullanılacağını gösterir.

Uygulama hedefi: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>İOS cihazlarındaki bazı bilgi noktası ayarları "engelle" kullanılarak ayarlanır ve "Izin ver" olarak değiştiriliyor<!-- 4404075  -->
İOS cihazlarında bir cihaz kısıtlamaları profili oluşturduğunuzda (**cihaz yapılandırma** > **profiller ** > **profil** > ** türü > bilgi noktası**için **iOS** > **cihaz kısıtlamaları** ), **otomatik kilit**, **zil**düğmesi, **ekran döndürme**, **ekran uyku düğmesi**ve **Ses düğmelerini**ayarlarsınız.

Bu güncelleştirmede değerler **blok** (özelliği engeller) ve **Yapılandırılmadı** (özelliğe izin verir). Ayarları görmek için [iOS cihaz ayarları ' na giderek özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md#kiosk).

Şunun için geçerlidir: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>İOS cihazlarında parola kimlik doğrulaması için yüz KIMLIĞI kullan<!-- 4490704 -->
İOS cihazları için bir cihaz kısıtlamaları profili oluşturduğunuzda, bir parola için parmak izi kullanabilirsiniz. Bu güncelleştirmede, parmak izi parola ayarları, yüz tanıma (**cihaz yapılandırma** > **profilleri** > profil **oluşturma** > iOS Için **iOS** > **cihaz kısıtlamaları** > **parola**) için bkz.. Sonuç olarak, aşağıdaki ayarlar değiştirilmiştir:

- **Parmak iziyle kilit açma** artık **dokunma KIMLIĞI ve yüz kimliği kilidi**.
- **Parmak izi değişikliği (yalnızca denetimli)** artık **dokunma KIMLIĞI ve yüz kimliği değişikliği (yalnızca denetimli)**.

Yüz KIMLIĞI, iOS 11,0 ve üzeri sürümlerde kullanılabilir. Ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md#password).

Şunun için geçerlidir: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>İOS cihazlarında oyun ve uygulama mağazası özelliklerinin sınırlandırılması artık derecelendirme bölgesine bağımlıdır<!-- 4593948 -->
İOS cihazlarında, Oyunlar, uygulama mağazası ve görüntüleme belgeleri (**cihaz yapılandırma** > **profilleri** > profil oluşturma > **iOS Için iOS** > **cihaz kısıtlamaları** **oluşturma** , > **Uygulama Mağazası, belge görüntüleme, oyun**) ile ilgili özelliklere izin verebilir veya bunları kısıtlayabilirsiniz. Ayrıca, Birleşik Devletler gibi derecelendirme bölgesini de seçebilirsiniz.

Bu güncelleştirmede, **uygulamalar** özelliği bir alt öğe **Derecelendirme bölgesine**taşınır ve **Derecelendirme bölgesine**bağımlıdır. Ayarları görmek için [iOS cihaz ayarları ' na giderek Intune kullanarak özelliklere izin verin veya kısıtlayın](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Şunun için geçerlidir: iOS

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Karma Azure AD katılımı için Windows Autopilot desteği<!-- 4809146-->
Mevcut cihazlar için Windows Autopilot artık karma Azure AD JOIN 'i destekliyor (mevcut Azure AD JOIN desteğine ek olarak). Windows 10 sürüm 1809 ve üzeri cihazlar için geçerlidir. Daha fazla bilgi için bkz. [var olan cihazlar Için Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Android cihazlar için güvenlik düzeltme eki düzeyine bakın<!-- 4461911 -->
Artık Android cihazlar için güvenlik düzeltme eki düzeyini görebilirsiniz. Bunu yapmak için **ıntune** > **cihazları** > **tüm cihazlar** ' ı seçin > bir cihaz > **donanımı**seçin.
Düzeltme eki düzeyi, **Işletim sistemi** bölümünde listelenir.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Kapsam etiketlerini bir güvenlik grubundaki tüm yönetilen cihazlara ata<!-- 3173810 -->
Artık kapsam etiketlerini bir güvenlik grubuna atayabilirsiniz ve güvenlik grubundaki tüm cihazlar da bu kapsam etiketleriyle ilişkilendirilecektir. Bu gruplardaki tüm cihazlara de kapsam etiketi atanır. Bu özellikle ayarlanan kapsam etiketleri, geçerli cihaz kapsamı etiketleri akışıyla ayarlanmış kapsam etiketlerinin üzerine yazar. Daha fazla bilgi için bkz. [Dağıtılmış BT IÇIN RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

### <a name="device-security"></a>Cihaz güvenliği

#### <a name="use-keyword-search-with-security-baselines------"></a>Anahtar sözcük aramasını güvenlik temel bilgileriyle kullanma<!--  -->
[Güvenlik temel profilleri](../protect/security-baselines.md#create-the-profile)oluştururken veya düzenlerken, kullanılabilir ayar gruplarını arama ölçütlerinize sahip olanlarla filtrelemek Için yeni *arama* çubuğunda anahtar sözcükler belirtebilirsiniz.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>Güvenlik temelleri özelliği artık genel kullanıma sunuldu<!-- 3785395 -->
**Güvenlik temelleri** özelliği önizleme aşamasındadır ve genel kullanıma sunuldu (GA).  Bu, özelliğin üretimde kullanıma hazırlanmasıdır. Ancak, tek başına temel şablonlar önizlemede kalabilir ve Kendi zamanlamalarında GA olarak değerlendirilir ve bu şekilde serbest bırakılır.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>MDM güvenlik temeli şablonu genel kullanıma sunuldu<!-- 3794072, 4217151,  3534649 -->
MDM güvenlik temeli şablonu önizleme dışına taşındı ve genel kullanıma sunuldu (GA). GA şablonu, **2019 Mayıs Için MDM güvenlik temeli**olarak tanımlanır.  Bu yeni bir şablondur ve önizleme sürümünden yükseltme değildir.  Yeni bir şablon olarak, [içerdiği ayarları](../protect/security-baseline-settings-mdm.md)gözden geçirmeniz ve sonra şablonu cihazınıza dağıtmak için yeni profiller oluşturmanız gerekir. Diğer güvenlik temeli şablonları önizlemede kalabilir. Kullanılabilir temellerin listesi için bkz. [kullanılabilir güvenlik temelleri](../protect/security-baselines.md#available-security-baselines).  

Yeni bir şablon olmanın yanı sıra, *2019 Mayıs şablonuna yönelik MDM güvenlik taban çizgisi* , en kısa zamanda geliştirme makaleimizde duyurduğumuz iki ayarı içerir:  
- Kilit üzerinde: uygulamaları kilitli bir ekrandan etkinleştirin  
- DeviceGuard: cihazların bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenlik (VBS) kullanın.  

*2019 Mayıs Için MDM güvenlik temeli* Ayrıca birkaç yeni ayarın eklenmesi, diğerlerinin kaldırılması ve bir ayarın varsayılan değerinin düzeltilmesi içerir. Önizlemedeki değişikliklerin ayrıntılı bir listesi için, bkz. **Yeni şablonda nelerin değiştiğini**.

#### <a name="security-baseline-versioning---3194322---"></a>Güvenlik temel sürümü oluşturma<!-- 3194322 -->
Intune desteği sürümü oluşturma için güvenlik temelleri. Bu destek sayesinde, her bir güvenlik temelinin yeni sürümleri yayınlandığından, sıfırdan yeni bir taban çizgisi yeniden oluşturup dağıtmak zorunda kalmadan, mevcut güvenlik taban çizgisi profillerinizi daha yeni temel sürümü kullanacak şekilde güncelleştirebilirsiniz. Buna ek olarak, Intune konsolunda, her bir taban çizgisi hakkındaki bilgileri, temeli kullanan bireysel profillerin sayısı, profillerinizin kaç farklı temel sürümünün kullanıldığı ve belirli bir güvenliğin en son sürümü gibi bilgileri görüntüleyebilirsiniz. taban çizgisi idi.  Daha fazla bilgi için bkz. **güvenlik temelleri**.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>Oturum açma ayarı için güvenlik anahtarlarını kullan ayarı taşındı<!-- 4501151 -->
**Oturum açma için güvenlik anahtarlarını kullan** adlı kimlik koruması için cihaz yapılandırma ayarı artık *Iş Için Windows Hello 'yu Yapılandır*alt ayarı olarak bulunmaz. Iş için Windows Hello 'Yu kullanmanıza izin vermeseniz bile, her zaman kullanılabilir olan en üst düzey bir ayardır. Daha fazla bilgi için bkz. [kimlik koruması](../protect/identity-protection-windows-settings.md).

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Atanan Grup yöneticileri için yeni izinler<!-- 4504437   -->
Intune 'un yerleşik okul yönetici rolünde, yönetilen uygulamalar için oluşturma, okuma, güncelleştirme ve silme (CRUD) izinleri artık vardır. Bu güncelleştirme, Eğitim için Intune ' de bir grup yöneticisi olarak atandıysanız, artık iOS MDM Anında İletme Sertifikası, iOS MDM sunucu belirteçlerini ve iOS VPP belirteçlerini ve [sahip olduğunuz tüm mevcut izinleri](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions)oluşturabilir, görüntüleyebilir, güncelleştirebilir ve silebilirsiniz. Bu eylemlerden herhangi birini gerçekleştirmek için, **IOS cihaz yönetimi** > **kiracı ayarları** ' na gidin.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Uygulamalar, Kullanıcı kimlik bilgileri olmadan okuma işlemlerini çağırmak için Graph API kullanabilir<!-- 4655885 -->
Uygulamalar, Kullanıcı kimlik bilgileri olmadan uygulama kimliği ile Intune Graph API okuma işlemlerini çağırabilir. Intune için Microsoft Graph API 'sine erişme hakkında daha fazla bilgi için, bkz. [Microsoft Graph Intune Ile çalışma](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0).

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Iş uygulamalarına yönelik Microsoft Store kapsam etiketleri uygulama<!-- 4392555 -->
Artık Microsoft Store for Business uygulamalarına kapsam etiketleri uygulayabilirsiniz. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](scope-tags.md).

## <a name="week-of-june-17-2019"></a>17 Haziran 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-features-in-microsoft-intune-app"></a>Microsoft Intune uygulamasındaki yeni özellikler
Android için Microsoft Intune uygulamasına (Önizleme) yeni özellikler ekledik. Tam olarak yönetilen Android cihazlarındaki kullanıcılar artık şunları yapabilir:  

* Intune Şirket Portalı veya Microsoft Intune uygulaması aracılığıyla kaydolduğu cihazları görüntüleyin ve yönetin.
* Destek için kuruluşunuzla iletişim kurun.
* Geri bildirimlerini Microsoft 'a gönderin.
* Kuruluş tarafından ayarlandıysa hüküm ve koşulları görüntüleyin.

## <a name="week-of-june-10-2019"></a>10 Haziran 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>GitHub 'da kullanılabilen Intune SDK tümleştirmesini gösteren yeni örnek uygulamalar<!-- 2653471 -->
Msıntuneappsdk GitHub hesabı, iOS (Swift), Android, Xamarin. iOS, Xamarin Forms ve Xamarin. Android için yeni örnek uygulamalar ekledi. Bu uygulamalar, mevcut belgelerimizi tamamlamak ve Intune uygulama SDK 'sını kendi mobil uygulamalarınıza tümleştirme hakkında gösteriler sağlamaktır. Ek Intune SDK rehberlik gerektiren bir uygulama geliştiricisiyseniz aşağıdaki bağlantılı örneklere bakın:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App) -aracılı kimlik doğrulaması Için Azure Active Directory kimlik doğrulama kitaplığı 'Nı (ADAL) kullanan bir yerel IOS (Swift) anlık ileti uygulaması.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App) -aracılı kimlik doğrulaması için ADAL kullanan yerel bir Android yapılacaklar listesi uygulamasıdır.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps) -aracılı kimlik doğrulaması için ADAL kullanan bir Xamarin. Android yapılacaklar listesi uygulaması, bu deponun de Xamarin. Forms uygulaması vardır.
- [Xamarin. iOS örnek uygulaması](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) -bir barekemikler Xamarin. iOS örnek uygulaması.

## <a name="week-of-may-27-2019"></a>27 Mayıs 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Android cihazlarda zararlı olabilecek uygulamalar için raporlama<!-- 4223162 -->
Intune artık Android cihazlarda zararlı olabilecek uygulamalar hakkında ek raporlama bilgileri sağlamaktadır. 

## <a name="week-of-may-20-2019"></a>20 Mayıs 2019 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="windows-company-portal-app---3316993---"></a>Windows Şirket Portalı uygulaması<!-- 3316993 -->
Windows Şirket Portalı uygulamasının artık **cihaz**etiketli yeni bir sayfası olacak. **Cihazlar** sayfasında, son kullanıcılar tüm kayıtlı cihazlarını gösterecektir. Kullanıcılar, 10.3.4291.0 ve sonraki sürümleri kullandıklarında bu değişikliği Şirket Portalı görür. Şirket Portalı yapılandırma hakkında daha fazla bilgi için bkz. [Microsoft Intune şirket portalı uygulamasını yapılandırma](../apps/company-portal-app.md).

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>Autopilot cihaz OrderID özniteliği adı Grup etiketi olarak değiştirildi <!-- 4659453 -->

Daha sezgisel hale getirmek için Autopilot cihazlarındaki **OrderID** özniteliği Name **Grup etiketi**olarak değiştirilmiştir. CSV 'yi Autopilot cihaz bilgilerini karşıya yüklemek için kullanırken, Grup etiketi ' ni, OrderID değil, sütun üst bilgisi olarak kullanmanız gerekir.  

## <a name="week-of-may-13-2019-1905-service-release"></a>13 Mayıs 2019 (1905 hizmet sürümü) haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Intune ilkeleri kimlik doğrulama yöntemini güncelleştirme ve uygulama yükleme Şirket Portalı<!-- 1927359  -->
Apple 'ın kurumsal cihaz kayıt yöntemlerinden biri aracılığıyla Kurulum Yardımcısı aracılığıyla zaten kaydedilmiş cihazlarda, Intune artık son kullanıcılar tarafından App Store 'dan el ile yüklendiğinde Şirket Portalı desteklememektedir. Bu değişiklik, yalnızca kayıt sırasında Apple Kurulum Yardımcısı ile doğrulandığında geçerlidir. Bu değişiklik, yalnızca aracılığıyla kaydedilmiş iOS cihazları etkiler:  
* Apple configurator

* Apple İşletme Yöneticisi

* Apple School Manager

* Apple aygıt kayıt programı (DEP)

Kullanıcıların uygulama Mağazası'ndan Şirket portalı uygulamasını yüklediğinizde ve onun üzerinden bu cihazları kaydetmek deneyin, bunlar bir hatayla karşılaşırsınız. Bu cihazların yalnızca Şirket Portalı, kayıt sırasında Intune tarafından otomatik olarak gönderildiği sırada kullanması beklenir. Azure portalında ıntune'da kayıt profilleri, cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız güncelleştirilecektir. DEP cihaz kullanıcılarınız Şirket portalı olmasını istiyorsanız, tercihlerinizi bir kayıt profili belirtmeniz gerekir. 

Ayrıca, iOS Şirket Portalı **cihaz ekranınızı belirler** . Bu nedenle, koşullu erişimi etkinleştirmek veya şirket uygulamalarını dağıtmak isteyen yöneticiler DEP kayıt profilini güncelleştirmemelidir. Bu gereksinim yalnızca DEP kaydının kimlik doğrulaması Kurulum Yardımcısı ile doğrulanmışsa geçerlidir. Bu durumda, Şirket Portalı cihaza göndermeniz gerekir. Bunu yapmak için **ıntune** > **cihaz kaydı** > **Apple kayıt** > **kayıt programı belirteçleri** ' ni seçin > bir belirteç > **profilleri** seçin > bir profil > **Özellikler** seçin > **Install** Şirket portalı **olarak ayarlayın**.

Şirket Portalı, zaten kayıtlı DEP cihazlarına yüklemek için Intune > Istemci uygulamalarına gitmeniz ve uygulamayı uygulama yapılandırma ilkeleriyle yönetilen bir uygulama olarak göndermeniz gerekir. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Son kullanıcıların bir uygulama koruma ilkesi kullanarak iş kolu (LOB) uygulamasını nasıl güncelleştirmelerini yapılandırma<!-- 3568384 -->
Artık son kullanıcılarınızın, iş kolu (LOB) uygulamasının güncelleştirilmiş bir sürümünü nereden alabilirim? Son kullanıcılar bu özelliği **En düşük uygulama sürümü** koşullu başlatma iletişim kutusunda görür. Bu, son kullanıcıların lob uygulamasının en düşük bir sürümüne güncelleştirilmesini ister. Bu güncelleştirme ayrıntılarını, LOB uygulama koruma ilkenizin (APP) bir parçası olarak sağlamanız gerekir. Bu özellik iOS ve Android 'de kullanılabilir. İOS 'ta, bu özellik, uygulamanın iOS için Intune SDK 'Sı ile tümleştirilebilmesi (veya sarmalama aracı kullanılarak sarmalanması) gerekir. 10.0.7 veya üzeri. Android 'de, bu özellik en son Şirket Portalı gerektirir. Bir son kullanıcının bir LOB uygulamasını nasıl güncelleştirmiş olduğunu yapılandırmak için, uygulamaya, `com.microsoft.intune.myappstore`anahtarla bir yönetilen uygulama yapılandırma ilkesi gönderilmesi gerekir. Gönderilen değer, son kullanıcının uygulamayı hangi depoya indirecek tanımlar. Uygulama Şirket Portalı aracılığıyla dağıtılırsa, değer `CompanyPortal`olmalıdır. Diğer herhangi bir mağaza için, URL 'nin tamamını girmeniz gerekir.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Intune yönetim uzantısı PowerShell betikleri<!-- 3734186  -->
PowerShell betiklerini, kullanıcının cihazdaki yönetici ayrıcalıklarıyla çalışacak şekilde yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Intune 'Da Windows 10 cihazlarında PowerShell betikleri kullanma](../apps/intune-management-extension.md) ve [Win32 uygulama yönetimi](../apps/app-management.md).

#### <a name="android-enterprise-app-management---4459905---"></a>Android kurumsal uygulama yönetimi<!-- 4459905 -->
BT yöneticilerinin Android kurumsal yönetimini yapılandırmasını ve kullanmasını kolaylaştırmak için Intune, Intune yönetici konsoluna dört ortak Android kurumsal ilgili uygulamayı otomatik olarak ekler. Dört Android kurumsal uygulama aşağıdaki uygulamalardır:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** -Android kurumsal tam olarak yönetilen senaryolar için kullanılır.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** -iki öğeli doğrulama kullanırsanız, hesaplarınızda oturum açmanıza yardımcı olur.
- **[Intune şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** -uygulama koruma ILKELERI (uygulama) ve Android kurumsal iş profili senaryoları için kullanılır.
- [Yönetilen giriş ekranı](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) -Android kurumsal adanmış/bilgi noktası senaryolarında kullanılır.

Daha önce BT yöneticilerinin, kurulum kapsamında bu uygulamaları [yönetilen Google Play deposunda](https://play.google.com/store/apps) el ile bulması ve onaylaması gerekir. Bu değişiklik, müşterilerin Android kurumsal yönetimini kullanmasını kolaylaştıran ve daha hızlı hale getirmeye yönelik daha önceden el ile yapılan adımları ortadan kaldırır.

Yöneticiler, Intune kiracılarını yönetilen Google Play ilk kez bağlandıklarında Intune uygulamaları listesine otomatik olarak eklenen bu dört uygulamayı görür. Daha fazla bilgi için bkz. [Intune hesabınızı yönetilen Google Play hesabınıza bağlama](../enrollment/connect-intune-android-enterprise.md). Kiracılarına zaten bağlı olan veya Android Enterprise kullanan kiracılar için yöneticilerin yapması gereken hiçbir şey yoktur. Bu dört uygulama, Mayıs 2019 servis dağıtımı tamamlandığında otomatik olarak 7 gün içinde görünür.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı güncelleştirildi<!-- 1533038 -->
Mevcut PFX sertifikalarının yeniden işlenmesine devam edildiği bir sorunu gideren [Microsoft Intune Için PFX Sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md#whats-new-for-connectors) için bir güncelleştirme yayımladık ve bu, bağlayıcının yeni istekleri işlemeyi durdurmasına neden oluyor.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Defender ATP için Intune güvenlik görevleri (genel önizlemede)<!-- 3208597 -->
Genel önizlemede, [Microsoft Defender Gelişmiş tehdit koruması (ATP) için güvenlik görevlerini](../protect/atp-manage-vulnerabilities.md)yönetmek üzere Intune 'u kullanabilirsiniz. Bu ATP ile tümleştirme ve uç nokta güvenlik açıklarını ve yapılandırmalarını düzeltmeye, önceliklendirmeye ve düzeltmeye yönelik risk tabanlı bir yaklaşım ekler ve hafifletme için bulma arasındaki süreyi azaltmaktadır.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671-----"></a>Windows 10 cihaz uyumluluk ilkesinde TPM yonga kümesini denetleme<!-- 3617671   -->
Birçok Windows 10 ve üzeri cihazda Güvenilir Platform Modülü (TPM) yonga kümeleri vardır. Bu güncelleştirme, cihazdaki TPM yonga sürümünü denetleyen yeni bir uyumluluk ayarı içerir.

[Windows 10 ve üzeri uyumluluk ilkesi ayarları](../protect/compliance-policy-create-windows.md#device-security) bu ayarı açıklar.

Şunlar için geçerlidir: Windows 10 ve üzeri

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Son kullanıcıların kendi kişisel etkin kullanımlarını değiştirmesini engelleyin ve iOS cihazlarında Siri sunucu günlüğünü devre dışı bırakın<!-- 4097904   -->  
İOS cihazında bir cihaz kısıtlamaları profili oluşturun (**cihaz yapılandırma** > **profiller** > profil oluşturmak için **ios** > **cihaz kısıtlamaları** ) > **profil oluşturma** ). Bu güncelleştirme, yapılandırabileceğiniz yeni ayarları içerir:

- **Yerleşik uygulamalar**: Siri komutları için sunucu tarafında günlüğe kaydetme
- **Kablosuz**: kişisel etkin noktanın Kullanıcı değişikliği (yalnızca denetimli)

Bu ayarları görmek için [iOS için yerleşik uygulama ayarları](../configuration/device-restrictions-ios.md#built-in-apps) ' na ve [iOS için kablosuz ayarlar](../configuration/device-restrictions-ios.md#wireless)' a gidin.

Uygulama hedefi: iOS 12,2 ve üzeri

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>MacOS cihazları için yeni sınıf uygulaması cihaz kısıtlama ayarları<!-- 4097905   --> 
MacOS cihazları için cihaz yapılandırma **profilleri oluşturabilirsiniz (** **cihaz yapılandırma** > **profilleri** , > Platform için **MacOS** > profil türü için **cihaz kısıtlamaları** ) > . Bu güncelleştirme, yeni sınıf uygulaması ayarlarını, ekran görüntülerini engelleme seçeneğini ve iCloud Fotoğraf kitaplığını devre dışı bırakma seçeneğini içerir.

Geçerli ayarları görmek için, [Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak üzere MacOS cihaz ayarları](../configuration/device-restrictions-macos.md)' na gidin.

Uygulama hedefi: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>App Store 'a erişmek için iOS parolası ayarı yeniden adlandırıldı<!-- 4557891  -->
**App Store 'a erişim parolası** , **tüm satın alımlarda** (**cihaz yapılandırma** > **profilleri** > profil **Oluştur** > **iOS** depolama parolası gerektirecek şekilde yeniden adlandırılır. > **Uygulama Mağazası, belge görüntüleme ve oyun**) için Platform > **cihaz kısıtlamaları**

Kullanılabilir ayarları görmek için [App Store, belge görüntüleme, oyun iOS ayarları '](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming)na gidin.

Şunun için geçerlidir: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Microsoft Defender Gelişmiş tehdit koruması temeli (Önizleme)<!--  3754134 -->
[Microsoft Defender Gelişmiş tehdit koruması](../protect/security-baseline-settings-defender-atp.md) ayarları için bir güvenlik temeli önizlemesi ekledik. Bu taban çizgisi, ortamınız [Microsoft Defender Gelişmiş tehdit koruması](../protect/advanced-threat-protection.md#prerequisites)kullanımı için önkoşulları karşılıyorsa kullanılabilir.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>Windows kayıt durumu sayfası (ESP) artık genel kullanıma sunuldu<!-- 3605348 -->
Kayıt durumu sayfası artık önizleme aşamasındadır. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Intune kullanıcı arabirimi güncelleştirmesi-Autopilot kayıt profili oluşturma<!-- 4593669 -->
Autopilot kayıt profili oluşturmaya yönelik kullanıcı arabirimi, Azure Kullanıcı arabirimi stilleriyle hizalanacak şekilde güncelleştirilmiştir. Daha fazla bilgi için bkz. [Autopilot kayıt profili oluşturma](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile). İleri hareket ettirilerek, ek Intune senaryoları bu yeni kullanıcı arabirimi stiline güncelleştirilecektir.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Tüm Windows cihazları için Autopilot sıfırlamayı etkinleştir<!-- 4225665 -->
Autopilot Reset, kayıt durumu sayfasını kullanmak üzere yapılandırılmamış olsalar dahi, tüm Windows cihazlarında çalışmaktadır. İlk cihaz kaydı sırasında cihaz için bir kayıt durumu sayfası yapılandırılmamışsa, cihaz, oturum açma işleminden sonra doğrudan masaüstüne gidecektir. Eşitlemek ve Intune ile uyumlu görünmesi sekiz saate kadar sürebilir. Daha fazla bilgi için bkz. [uzak Windows Autopilot sıfırlaması ile cihazları sıfırlama](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote).

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>Tüm cihazlar aranırken tam ıMEı biçimi gerekli değildir<!--30407680 -->
**Tüm cihazları**ararken IMEI numaralarına boşluk eklemeniz gerekmez.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Apple portalında bir cihazın silinmesi, Intune portalında yansıtılacaktır<!--2489996 -->
Bir cihaz Apple 'ın Aygıt Kayıt Programı veya Apple Business Manager portallarından silinirse, bir sonraki eşitleme sırasında cihaz otomatik olarak Intune 'dan silinir.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>Kayıt durumu sayfası artık Win32 uygulamalarını izler<!-- 2714451 -->
Bu, yalnızca Windows 10 sürüm 1903 ve üstünü çalıştıran cihazlar için geçerlidir. Daha fazla bilgi için bkz. [kayıt durumu sayfası ayarlama](../enrollment/windows-enrollment-status.md).

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Graph API kullanarak cihazları toplu olarak sıfırlayın ve temizleyin<!-- 3295288 -->
Artık Graph API kullanarak en fazla 100 cihazı toplu olarak sıfırlayabilir ve silebilirsiniz.

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>Şifreleme raporu genel önizleme dışında<!-- 4587546      -->
[BitLocker ve cihaz şifrelemesi için rapor](../protect/encryption-monitor.md) artık genel önizlemeye sunuldu ve artık genel önizlemenin bir parçası değil.

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>İOS ve Android cihazlar için Outlook imzası ve biyometrik ayarlar<!-- 4050557 -->
Artık, varsayılan imzanın iOS ve Android cihazlarda Outlook 'ta etkinleştirilip etkinleştirilmediğini belirtebilirsiniz. Ayrıca, kullanıcıların iOS üzerinde Outlook 'ta biyometrik ayarını değiştirmesine izin vermeyi de seçebilirsiniz.

## <a name="week-of-may-6-2019"></a>6 Mayıs 2019 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>İOS cihazlarına yönelik F5 erişimi için ağ Access Control (NAC) desteği<!-- 4500808 -->

F5, Intune 'da iOS üzerinde F5 erişimi için NAC işlevselliğine izin veren büyük IP 13 için bir güncelleştirme yayınladı. Bu özelliği kullanmak için:

- BÜYÜK IP 'yi 13.1.1.5 yenilemeye güncelleştirin. BÜYÜK IP 14 desteklenmez.
- NAC için büyük IP 'yi Intune ile tümleştirin. [Genel bakış: uç nokta yönetim sistemleriyle cihaz gönderme denetimleri IÇIN APM yapılandırma](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Intune 'da VPN profilindeki **ağ Access Control etkinleştir (NAC)** ayarını denetleyin.

Kullanılabilir ayarı görmek için [iOS CIHAZLARıNDA VPN ayarlarını yapılandırma](../configuration/vpn-settings-ios.md)bölümüne gidin.

Şunun için geçerlidir: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı güncelleştirildi<!-- doc-vso 1521237  -->  
[Microsoft Intune Için PFX Sertifika Bağlayıcısı](../protect/certficates-pfx-configure.md#whats-new-for-connectors) için bir güncelleştirme yayımladık ve yoklama aralığını 5 dakikadan 30 saniyeye bırakıyor.




## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
