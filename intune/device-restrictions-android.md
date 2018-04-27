---
title: Android için Microsoft Intune cihaz kısıtlama ayarları
titlesuffix: ''
description: Android çalıştıran cihazlarda cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 619d9e86bd130a617155d262f3e09882ce26ec1e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-android-and-samsung-knox-standard-device-restriction-settings"></a>Microsoft Intune Android ve Samsung Knox Standard cihaz kısıtlama ayarları 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, Android çalıştıran cihazlar için yapılandırabileceğiniz tüm Microsoft Intune cihaz kısıtlama ayarları gösterilir.

>[!TIP]
>İstediğiniz ayarlar mevcut değilse cihazlarınızı bir [özel profil](custom-settings-android.md) kullanarak yapılandırabilirsiniz.

## <a name="general"></a>Genel

- **Kamera** - Cihaz kamerasının kullanılmasına izin verir.
- **Kopyala ve Yapıştır (yalnızca Samsung Knox)** - Cihazda kopyalama ve yapıştırma işlevlerine izin verir.
- **Uygulamalar arasında pano paylaşımı (yalnızca Samsung Knox)** - Uygulamalar arasında kopyalama ve yapıştırma işlemleri için panonun kullanımına izin verir.
- **Tanılama verileri gönderme (yalnızca Samsung Knox)** - Kullanıcının cihazdan tanılama verileri göndermesini durdurur.
- **Fabrika sıfırlaması (yalnızca Samsung Knox)** - Kullanıcının cihazda fabrika sıfırlaması gerçekleştirmesine izin verir.
- **Coğrafi konum (yalnızca Samsung Knox)** - Cihazın konum bilgilerini kullanmasına izin verir.
- **Kapatma (yalnızca Samsung Knox)** - Kullanıcının cihazı kapatmasına izin verir.<br>Devre dışı bırakılırsa **Cihaz silinmeden önceki oturum açma hatası sayısı** ayarlanamaz.
- **Ekran yakalama (yalnızca Samsung Knox)** - Kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Sesli yardımcı (yalnızca Samsung Knox)** - Cihazda sesli yardım yazılımının kullanımına izin verir.
- **YouTube (yalnızca Samsung Knox)** - Cihazda YouTube uygulamasının kullanımına izin verir.
- **Paylaşılan cihazlar (yalnızca Samsung Knox)** - Yönetilen bir Samsung Knox Standard cihazını paylaşılan cihaz olarak yapılandırın. Bu modda, son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da yönetilmeye devam eder.<br>SCEP sertifika profiliyle birlikte kullanıldığında, bu özellik son kullanıcıların, tüm kullanıcılar için aynı uygulama kümesini içeren ancak kendi SCEP kullanıcı sertifikası olan bir cihazı paylaşmalarına olanak tanır.  Kullanıcılar oturumu kapattığında tüm veriler silinir.  Bu özellik yalnızca LOB uygulamalarıyla sınırlıdır.
- **Tarih ve saat değişikliklerini engelle (Samsung Knox)** - Kullanıcının cihazda tarih ve saat ayarlarını değiştirmesini engelleyin. 

## <a name="password"></a>Parola

- **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu kılın. |Evet|Evet|
- **En az parola uzunluğu** - Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (4 ile 16 karakter arasında).
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Cihaz otomatik olarak kilitlenmeden önce işlem yapılmayan dakika sayısını belirtir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı** - Cihaz silinmeden önce başarısız oturum açma sayısını belirtir.
- **Parola süresinin sonu (gün)** - Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.
-  **Gerekli parola türü** - Gereken parola karmaşıklık düzeyini ve biyometrik cihaz kullanılıp kullanılamayacağını belirtir. Aşağıdakilerden birini seçin:
    - **Cihaz varsayılanı**
    - **Düşük güvenlik biyometriği**
    - **En az sayısal**
    - **Sayısal karmaşık** - ‘1111’ veya ‘1234’ gibi yinelenen veya ardışık numaralara izin verilmez<sup>1</sup>
    - **En az alfabetik**
    - **En az alfasayısal**
    - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle** - Son kullanıcının daha önce kullanmış olduğu bir parolayı oluşturmasını durdurur.
- **Parmak izi ile kilit açmaya izin ver (yalnızca Samsung Knox)** - Desteklenen cihazların kilidini açmak için parmak izi kullanımına izin verir.
- **Akıllı Kilitleme ve diğer güven aracıları** - Uyumlu Android cihazlarda Akıllı Kilitleme özelliğini denetlemenize olanak tanır (Samsung Knox Standard 5.0 ve üstü). Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin, cihaz belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda bu kullanılabilir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.
- **Şifreleme** - Cihazdaki dosyaların şifrelenmesini gerektirir.

<sup>1</sup> Bu ayarı cihazlara atamadan önce, Şirket Portalı uygulamasının bu cihazlarda en son sürüme güncelleştirilmiş olduğundan emin olun.

**Sayısal karmaşık** ayarını yapılandırıp, bunu Android 5.0 öncesi bir sürümü çalıştıran cihaza atarsanız aşağıdaki davranış uygulanır.
- Şirket Portalı uygulaması 1704 öncesi bir sürümü çalıştırıyorsa cihaza PIN ilkesi uygulanmaz ve Azure portalında bir hata görüntülenir.
- Şirket Portalı uygulaması 1704 veya üzeri bir sürüm çalıştırıyorsa yalnızca basit bir PIN uygulanabilir. Android 5.0 öncesi sürümlerde bu ayar desteklenmez. Azure portalında herhangi bir hata görüntülenmez.


## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (yalnızca Samsung Knox)** - Kullanıcının cihazda Google Play Store’a erişmesine izin verir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini hem Android hem de Samsung Knox Standard cihazları için yapılandırabilirsiniz:

**Yasak uygulamalar** listesi - Kullanıcılar yükleyip çalıştırdığında raporlanacak uygulamaları (Intune tarafından yönetilmeyenler) listeler.
**Onaylı uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Uyumluluğun korunması için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.
Kısıtlı uygulama ayarlarını içeren cihaz profilleri kullanıcı gruplarına atanmalıdır.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra da tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Mağazadaki uygulamanın URL’sini belirtme

Uyumlu veya uyumsuz uygulama listesinde bir uygulama URL'si belirtmek için aşağıdaki adımları uygulayın:

[Google Play'in uygulamalar bölümünde](https://play.google.com/store/apps) kullanmak istediğiniz uygulamayı arayın.

Uygulamanın yükleme sayfasını açın ve URL'yi panoya kopyalayın. Artık bu URL’yi uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde kullanabilirsiniz.

Örnek: [Google Play’in uygulamalar bölümünde](https://play.google.com/store/apps) **Microsoft Planner**’ı aratın. Şu URL’yi kullanın: **https://play.google.com/store/apps/details?id=com.microsoft.planner**.

### <a name="additional-options"></a>Ek seçenekler

Listeyi bir csv dosyasından almak için **İçeri Aktar**’a da tıklayabilirsiniz. <*uygulama url’si*>, <*uygulama adı*>, <*uygulama yayımcısı*> biçimini kullanın veya aynı biçimdeki kısıtlı uygulama listesi içeriğini barındıran csv dosyasında **Dışarı Aktar**’a tıklayın.      

## <a name="browser"></a>Tarayıcı

- **Web tarayıcısı (yalnızca Samsung Knox)** - Cihazın varsayılan web tarayıcısının kullanılıp kullanılamayacağını belirtir.
- **Otomatik doldurma (yalnızca Samsung Knox)** - Kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.
- **Tanımlama bilgileri (yalnızca Samsung Knox)** - Cihazdaki web tarayıcısının tanımlama bilgileri kullanmasına izin verir.
- **Javascript (yalnızca Samsung Knox)** - Cihazdaki web tarayıcısının Java betiklerini çalıştırmasına izin verir.
- **Açılır pencereler (yalnızca Samsung Knox)** - Web tarayıcısında açılır pencere engelleyicisinin kullanımına izin verir.

## <a name="allow-or-block-apps"></a>Uygulamalara izin verme veya uygulamaları engelleme

Bu ayarlar, yalnızca Samsung Knox Standard çalıştıran cihazlara yüklenebilen veya bu cihazlarda başlatılabilen uygulamaları belirtmek için kullanılabilir.
Ayrıca, cihaz kullanıcısından gizlenen yüklü uygulamaları da belirtebilirsiniz. Kullanıcılar bu uygulamaları çalıştıramaz.

- **Yüklenmesine izin verilen uygulamalar (yalnızca Samsung Knox Standard)**
- **Başlatılması engellenen uygulamalar (yalnızca Samsung Knox Standard)**
- **Kullanıcıdan gizlenen uygulamalar (yalnızca Samsung Knox Standard)**

Her ayar için aşağıdakilerden birini kullanarak bir uygulama listesi yapılandırın:

- **Paket adına göre uygulama ekleme** - Öncelikli olarak iş kolu uygulamaları için kullanılır. Uygulamanın ve uygulama paketinin adını girin.
- **URL’ye göre uygulama ekleme** - Uygulamanın adını ve Google Play mağazası URL’sini girin.
- **Yönetilen uygulamalar ekleme** - Intune ile yönettiğiniz uygulamalar listesinden ihtiyacınız olan uygulamayı seçin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Google yedekleme (yalnızca Samsung Knox)** - Google yedeklemesinin kullanımına izin verir.
- **Google hesabı otomatik eşitlemesi (yalnızca Samsung Knox)** - Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.
- **Çıkarılabilir depolama birimi (yalnızca Samsung Knox)** - Cihazın SD kartı gibi bir çıkarılabilir depolama birimi kullanmasına izin verir.
- **Depolama kartlarında şifreleme (yalnızca Samsung Knox)** - Cihaz depolama kartını şifrelemenin gerekip gerekmediğini belirtir.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Veri dolaşımı (yalnızca Samsung Knox)** - Cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **SMS/MMS mesajları (yalnızca Samsung Knox)** - Cihazda SMS ve MMS mesajlarının kullanımına izin verir.
- **Sesli arama (yalnızca Samsung Knox)** - Cihazda sesli arama özelliğini etkinleştirir veya devre dışı bırakır.
- **Ses dolaşımı (yalnızca Samsung Knox)** - Cihaz hücresel ağ üzerindeyken ses dolaşımına izin verir.
- **Bluetooth (yalnızca Samsung Knox)** - Cihazda Bluetooth’un kullanımına izin verir.
- **NFC (yalnızca Samsung Knox)** - Desteklenen cihazlarda yakın alan iletişimi kullanan işlemlere izin verir.
- **Wi-Fi (yalnızca Samsung Knox)** - Cihazın Wi-Fi özelliklerinin kullanımına izin verir.
- **Wi-Fi paylaşımı (yalnızca Samsung Knox)** - Cihazda Wi-Fi paylaşımının kullanılmasına izin verir.

## <a name="kiosk"></a>Bilgi noktası

Bilgi noktası ayarları yalnızca Samsung Knox Standard cihazlarda ve Intune ile yönettiğiniz uygulamalarda geçerlidir.

- **Yönetilen bir uygulama seçin** - Cihaz bilgi noktası modunda olduğunda çalışabilen bir veya daha fazla yönetilen uygulama eklemek için aşağıdaki seçeneklerden birini belirleyin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez. Önceden yüklenen tarayıcılar, cihaz bilgi noktası modundayken çalışmasına izin verilen bir uygulama olarak tanımlanamaz. Bir tarayıcı gerekliyse [Managed Browser](app-configuration-managed-browser.md) kullanabilirsiniz.
    - **Paket adına göre uygulama ekleme**
    - **URL’ye göre uygulama ekleme**
    - **Yönetilen uygulamalar ekleme**.
- **Ekran uyku düğmesi** - Ekranda uykuya geçme ve uyandırma düğmesini etkinleştirir veya devre dışı bırakır.
- **Ses düğmeleri** - Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.


## <a name="next-steps"></a>Sonraki adımlar

Cihaz kısıtlama profilini oluşturmak ve sonra atamak için [Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md) makalesindeki yönergeleri kullanarak devam edin.
