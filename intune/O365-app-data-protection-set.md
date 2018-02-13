---
title: "Intune'da Office 365 uygulamalarında temel veri yönetimini ayarlama"
titlesuffix: Azure portal
description: "Office 365 uygulamalarını yönetme sihirbazını destekleyen belgeler.\""
keywords: 
author: lindavr
ms.author: lindavr
manager: dougeby
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 852612ac-f146-4372-a900-3f6fdebd05ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ayesham
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d1a4513b8ef6e1f42ad84558de8a57399bb8c1b
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="how-your-users-will-experience-basic-protection-on-managed-office-365-apps"></a>Kullanıcılarınızın yönetilen Office 365 uygulamalarındaki temel koruma deneyimi

**Office 365 uygulamalarını yönet** sihirbazı, her cihaz platformu için bir uygulama koruma ilkesi oluşturur.

Sihirbaz aşağıdaki ilkeleri açar:

**iOS**
* Uygulama verilerini şifreleme

**Android**
* Uygulama verilerini şifreleme
* Erişim için basit PIN gerektir

Bu ilkeler, gerektiğinde Office uygulamalarından iş verilerini temizleyebilmenize olanak tanıyarak Office 365 uygulamalarını yönetebileceğinizden emin olmanızı sağlar. Ayrıca, Office 365 uygulamalarında iş verilerinizin şifrelendiğinden ve verileri görüntülemek için PIN girilmesi gerektiğinden emin olarak, cihazın kaybolması veya çalınması durumunda temel korumayı da güvence altına alır.


Bu makalede, Intune tarafından yönetilen bir uygulamada kullanıcının deneyimini göstermek üzere örnek olarak OneDrive İş kullanılmıştır.


>[!NOTE]
>Kişisel bir cihazda, uygulama genellikle son kullanıcı tarafından indirilir. Cihaz bir mobil cihaz yönetimi (MDM) çözümü tarafından yönetiliyorsa uygulamayı cihaza dağıtabilirsiniz.

## <a name="user-experience-on-an-ios-device"></a>iOS cihazında kullanıcı deneyimi

1. Oturum açma sayfasını açmak için OneDrive İş uygulamasını başlatın.  <br/> ![iOS için OneDrive oturum açma ekranının resmi](./media/onedrive-ios-sign-in.png)
2. İş hesabı kullanıcı adınızı yazın. İş kimlik bilgilerinizi girmeniz için Office 365 kimlik doğrulaması sayfasına yönlendirilirsiniz. <br/> ![Office 365 oturum açma sayfasının resmi](./media/o365-sign-in-ios.png)
3. Kimlik bilgileriniz Azure Active Directory tarafından başarıyla doğrulandıktan sonra uygulama koruma ilkeleri uygulanır ve OneDrive İş uygulamasını yeniden başlatmanız istenir.  <br/>![iOS için yeniden başlatma isteminin resmi](./media/ios-restart-prompt.png)    
  > [!NOTE]
  > Yeniden başlatma gerekli iletisi yalnızca, Intune’da kayıtlı olmayan cihazlarda görüntülenir.


4. OneDrive İş uygulamasını yeniden başlatın. Uygulama, uygulama koruma ilkeleri açık olarak başlatılır ve cihaz için bir PIN ayarlamanız istenir (henüz cihaz için bir PIN yapılandırmadıysanız). <br/> ![PIN oluşturma isteminin resmi](./media/pin-prompt-ios.png)    
  > [!NOTE]
  > Kullanıcılarınızın çoğu bu bilgi istemini görmez. Yalnızca iOS cihazlarında PIN’i etkinleştirmemiş olan kullanıcılar bu bilgi istemini görür.


5. PIN’i ayarlayıp onayladıktan sonra, OneDrive İş uygulamasına dönün. BT yöneticinizin artık OneDrive’daki iş verilerinizi koruduğuna ilişkin tek seferlik bir bildirim görürsünüz. <br/> ![BT yöneticinizden gelen tek seferlik bildirimin resmi](./media/one-time-notice.png)
6. OneDrive İş’teki dosyalarınıza erişmek için bu bildirimi tıklayarak geçin. <br/> ![iOS cihazındaki OneDrive dosyalarının resmi](./media/onedrive-files-ios.png) <br/>

>[!NOTE]
>Dağıtılan bir ilkeyi değiştirirseniz, değişiklikler uygulamayı bir sonraki açışınızda uygulanır.


## <a name="user-experience-on-an-android-device"></a>Android cihazında kullanıcı deneyimi

1. Oturum açma sayfasını açmak için OneDrive İş uygulamasını başlatın.  <br/> ![OneDrive uygulaması hoş geldiniz ekranının resmi](./media/onedrive-android-welcome.png)
2. İş hesabı kullanıcı adınızı yazın. İş kimlik bilgilerinizi girmeniz için Office 365 kimlik doğrulaması sayfasına yönlendirilirsiniz. <br/> ![Android’de O365 oturum açma işleminin resmi](./media/o365-sign-in-android.png)
3. Kimlik bilgileriniz Azure AD Active Directory tarafından başarıyla doğrulandıktan sonra, Şirket Portalı uygulaması cihaza henüz yüklenmediyse, uygulamayı yükleme yönergelerini içeren bir ileti görürsünüz. Devam etmek için **Mağazaya git**’e dokunun. <br/> ![Şirket Portalı uygulamasını alma iletisinin resmi](./media/get-company-portal-android.png) <br/>Şirket Portalı uygulaması telefonunuza zaten yüklenmişse, OneDrive İş uygulaması otomatik olarak başlatılır ve son nota atlayabilirsiniz.    
  > [!IMPORTANT]
  > Android’de, Office uygulamalarının bir uygulama koruma ilkesi tarafından yönetilmesini ayarladıktan sonra, son kullanıcının aslında e-postaları veya belgeleri okumak için Şirket Portalı uygulamasını açması veya bu uygulamada oturum açması gerekmese bile, iş e-postalarına ve belgelerine erişmek için bu uygulamayı yüklemesi **gerekir**.

4. Şu anda Şirket Portalı uygulamasını indirip yükleyebileceğiniz Google Play mağazasındasınız. Uygulama, verilerinizi güvende tutmaya ve korumaya yardımcı olur. <br/> ![Google Play mağazasındaki uygulamanın resmi](./media/google-play-get-app-android.png)
5. Uygulama yüklemesini tamamladıktan sonra koşulları kabul etmek için **Kabul Et**’i seçin. OneDrive İş uygulaması otomatik olarak başlatılır.


>[!NOTE]
>OneDrive İş uygulamasını bir sonraki açışınızda, BT’niz gerektiriyorsa bir PIN ayarlamanız istenebilir. PIN’i ayarlayıp onayladıktan sonra, OneDrive İş’i açmaya devam edebilirsiniz.

![PIN isteminin resmi](./media/pin-prompt-android.png)


<!--- Original steps: 6. The next time you open OneDrive for Business, you may be asked to set a PIN, if your IT requires one to use the OneDrive for Business app. ART 7. After you set and confirm the PIN, you can continue on to OneDrive for Business. -->

## <a name="what-policies-does-this-wizard-set"></a>Bu sihirbaz hangi ilkeleri ayarlar?
|     |       | |
|----|--------|-|
|**Ad**|Office 365 uygulamalarını yönetme| |
| **Açıklama**|Office 365 uygulamalarını yönetme sihirbazı tarafından oluşturuldu| |
| |  | |
| **Ayar Adı** |**iOS ilke değeri** | **Android ilke değeri** |
|iTunes ve iCloud yedeklemelerini engelle| Hayır | Yok |
|Android yedeklemelerini engelle |Yok | Hayır|
|Uygulamanın diğer uygulamalara veri aktarmasına izin ver | Tüm uygulamalar | Tüm uygulamalar|
|Uygulamanın diğer uygulamalardan veri almasına izin ver| Tüm uygulamalar | Tüm uygulamalar|
|“Farklı kaydet”’i Engelle | Hayır | Hayır|
|Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtla | Herhangi bir uygulama | Herhangi bir uygulama |
|Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın | Hayır| Hayır|
|Uygulama verilerini şifreleme | Cihaz kilitliyken | Evet|
|Kişilerin eşitlenmesini devre dışı bırak | Hayır| Hayır|
|Yazdırmayı devre dışı bırak | Hayır | Hayır|
|Erişim için PIN gerektir | Hayır | Evet|
|PIN sıfırlanmadan önce deneme sayısı | Yok |5|
|Basit PIN’e izin ver | Yok |Evet|
|PIN uzunluğu | Yok | 4|
|PIN yerine parmak izine izin ver | Yok | Evet |
|Erişim için kurumsal kimlik bilgileri gerektir | Hayır | Hayır|
|Yönetilen cihazların, jailbreak uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelle | Hayır | Hayır|
|Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika) - Zaman aşımı | 30 | 30|
|Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika) - Çevrimdışı tanınan süre | 720 |720|
|Uygulama verileri temizlenmeden önce geçen çevrimdışı süre (gün cinsinden) | 90 | 90|
|Ekran yakalamayı engelle (yalnızca Android cihazlar) | Yok | Hayır |

### <a name="why-is-an-app-pin-policy-only-configured-for-android-devices"></a>Uygulama PIN ilkesi neden yalnızca Android cihazlar için yapılandırılır?
Şifreleme iOS ile Android’de ayrı çalışır.

iOS’ta bir Intune uygulama koruma ilkesiyle ilişkilendirilmiş uygulamalarda veriler, kullanılmadıkları sırada işletim sistemi tarafından sağlanan cihaz düzeyinde şifreleme ile şifrelenir. Dolayısıyla, uygulama şifreleme ilkesini açtığınızda otomatik olarak kullanıcının bir PIN belirlemesini ve iş verilerine erişmek için bunu girmesini zorunlu tutmuş olursunuz. Cihazında henüz bir cihaz PIN’i yapılandırmamış olan kullanıcıların cihaz PIN’i oluşturması istenir.

Android’de bir Intune uygulama koruma ilkesiyle ilişkilendirilmiş olan uygulamalarda veriler, dosya G/Ç görevleri sırasında eş zamanlı olarak şifrelenir. Cihaz depolamasındaki içerik her zaman şifrelenir. MDM ile yönetilmeyen cihazlarda, uygulama koruma ilkesi cihaz PIN’i gereksinimini zorunlu tutamaz. Kullanıcıların iş verilerine erişmek için PIN kullanmasının gerekli olduğundan emin olmak için, cihaz uygulama PIN ilkesini etkinleştirir.

Kuruluşunuzun gereksinimlerine uygun olması için bu ilke ayarlarını istediğiniz zaman düzenleyebilirsiniz.

### <a name="how-can-i-view-and-edit-the-policies-created-by-the-wizard"></a>Sihirbaz tarafından oluşturulan ilkeleri nasıl görüntüleyebilir ve düzenleyebilirim?
Bu ilkeleri veya Intune Azure portalında oluşturduğunuz herhangi bir ilkeyi görmek veya güncelleştirmek için, panodan **Uygulamaları yönet** > **Uygulama Koruma İlkeleri**'ni seçin. İlke listesi sağ tarafta açılır. Ayarlarını görmek ve düzenlemek için görüntülemek istediğiniz ilkeyi seçin. <br/>
![İlkeleri görüntülemek için kullanıcı arabirimi yolunun görüntüsü](./media/image-for-faq.png)

## <a name="next-steps"></a>Sonraki adımlar
[Uygulama koruma ilkeleri](app-protection-policy.md) hakkında daha fazla bilgi edinin.
