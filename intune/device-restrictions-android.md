---
title: "Android için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune on Azure
description: "Android cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09641b5e34ab8200e7dd9d4c27f0dabf59fa62d2
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Android ve Samsung KNOX Standard cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihazları kuruluşunuzda yapılandırmak için bu ayarları bir Android cihaz kısıtlama ilkesiyle birlikte kullanın.

>[!TIP]
>İstediğiniz ayarlar mevcut değilse cihazlarınızı bir [özel profil](custom-settings-android.md) kullanarak yapılandırabilirsiniz. 

## <a name="general"></a>Genel

- **Kamera** - Cihaz kamerasının kullanılmasına izin verir.
- **Kopyala ve Yapıştır (yalnızca Samsung KNOX)** - Cihazda kopyalama ve yapıştırma işlevlerine izin verir.
- **Uygulamalar arasında pano paylaşımı (yalnızca Samsung KNOX)** - Uygulamalar arasında kopyalama ve yapıştırma işlemleri için panonun kullanımına izin verir.
- **Tanılama verileri gönderme (yalnızca Samsung KNOX)** - Kullanıcının cihazdan tanılama verileri göndermesini durdurur.
- **Fabrika sıfırlaması (yalnızca Samsung KNOX)** - Kullanıcının cihazda fabrika sıfırlaması gerçekleştirmesine izin verir.
- **Coğrafi konum (yalnızca Samsung KNOX)** - Cihazın konum bilgilerini kullanmasına izin verir.
- **Kapatma (yalnızca Samsung KNOX)** - Kullanıcının cihazı kapatmasına izin verir.<br>Devre dışı bırakılırsa **Cihaz silinmeden önceki oturum açma hatası sayısı** ayarlanamaz.
- **Ekran yakalama (yalnızca Samsung KNOX)** - Kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Sesli yardımcı (yalnızca Samsung KNOX)** - Cihazda sesli yardım yazılımının kullanımına izin verir.
- **YouTube (yalnızca Samsung KNOX)** - Cihazda YouTube uygulamasının kullanımına izin verir.
- **Paylaşılan cihazlar** - Yönetilen bir Samsung KNOX Standard cihazını paylaşılan cihaz olarak yapılandırın. Bu modda, son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da yönetilmeye devam eder.<br>Oturum açan kullanıcılar kendilerine atanan uygulamalara ilkelere otomatik olarak erişir. Kullanıcılar oturumu kapattığında tüm veriler silinir.

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
- **Parmak izi ile kilit açmaya izin ver (yalnızca Samsung KNOX)** - Desteklenen cihazların kilidini açmak için parmak izi kullanımına izin verir.
- **Akıllı Kilitleme ve diğer güven aracıları** - Uyumlu Android cihazlarda Akıllı Kilitleme özelliğini denetlemenize olanak tanır (Samsung KNOX Standard 5.0 ve üstü). Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin, cihaz belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda bu kullanılabilir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.
- **Şifreleme** - Cihazdaki dosyaların şifrelenmesini gerektirir.

<sup>1</sup> Bu ayarı cihazlara atamadan önce, Şirket Portalı uygulamasının bu cihazlarda en son sürüme güncelleştirilmiş olduğundan emin olun.

**Sayısal karmaşık** ayarını yapılandırıp, bunu Android 5.0 öncesi bir sürümü çalıştıran cihaza atarsanız aşağıdaki davranış uygulanır.
- Şirket Portalı uygulaması 1704 öncesi bir sürümü çalıştırıyorsa cihaza PIN ilkesi uygulanmaz ve Intune portalında bir hata görüntülenir.
- Şirket Portalı uygulaması 1704 veya üzeri bir sürüm çalıştırıyorsa yalnızca basit bir PIN uygulanabilir. Android 5.0 öncesi sürümlerde bu ayar desteklenmez. Intune portalında herhangi bir hata görüntülenmez.


## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (yalnızca Samsung KNOX)** - Kullanıcının cihazda Google Play Store’a erişmesine izin verir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini hem Android hem de Samsung KNOX Standard cihazları için yapılandırabilirsiniz:

**Yasak uygulamalar** listesi - Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.
**Onaylı uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Uyumluluğun korunması için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.
Kısıtlı uygulama ayarlarını içeren cihaz profilleri kullanıcı gruplarına atanmalıdır.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra da tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Mağazadaki uygulamanın URL’sini belirtme

Uyumlu veya uyumsuz uygulama listesinde bir uygulama URL'si belirtmek için aşağıdaki adımları uygulayın:

[Google Play'in uygulamalar bölümünde](https://play.google.com/store/apps) kullanmak istediğiniz uygulamayı arayın.

Uygulamanın yükleme sayfasını açın ve URL'yi panoya kopyalayın. Artık bu URL’yi uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde kullanabilirsiniz.

Örnek: Microsoft Office Mobile için Google Play'i arayın. Şu URL’yi kullanın: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Ek seçenekler

Listeyi bir csv dosyasından almak için **İçeri Aktar**’a da tıklayabilirsiniz. <*uygulama url’si*>, <*uygulama adı*>, <*uygulama yayımcısı*> biçimini kullanın veya aynı biçimdeki kısıtlı uygulama listesi içeriğini barındıran csv dosyasında **Dışarı Aktar**’a tıklayın.      

## <a name="browser"></a>Tarayıcı

- **Web tarayıcısı (yalnızca Samsung KNOX)** - Cihazın varsayılan web tarayıcısının kullanılıp kullanılamayacağını belirtir.
- **Otomatik doldurma (yalnızca Samsung KNOX)** - Kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.
- **Tanımlama bilgileri (yalnızca Samsung KNOX)** - Cihazdaki web tarayıcısının tanımlama bilgileri kullanmasına izin verir.
- **Javascript (yalnızca Samsung KNOX)** - Cihazdaki web tarayıcısının Java betiklerini çalıştırmasına izin verir.
- **Açılır pencereler (yalnızca Samsung KNOX)** - Web tarayıcısında açılır pencere engelleyicisinin kullanımına izin verir.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Google yedekleme (yalnızca Samsung KNOX)** - Google yedeklemesinin kullanımına izin verir.
- **Google hesabı otomatik eşitlemesi (yalnızca Samsung KNOX)** - Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.
- **Çıkarılabilir depolama birimi (yalnızca Samsung KNOX)** - Cihazın SD kartı gibi bir çıkarılabilir depolama birimi kullanmasına izin verir.
- **Depolama kartlarında şifreleme (yalnızca Samsung KNOX)** - Cihaz depolama kartını şifrelemenin gerekip gerekmediğini belirtir.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Veri dolaşımı (yalnızca Samsung KNOX)** - Cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **SMS/MMS mesajları (yalnızca Samsung KNOX)** - Cihazda SMS ve MMS mesajlarının kullanımına izin verir.
- **Sesli arama (yalnızca Samsung KNOX)** - Cihazda sesli arama özelliğini etkinleştirir veya devre dışı bırakır.
- **Ses dolaşımı (yalnızca Samsung KNOX)** - Cihaz hücresel ağ üzerindeyken ses dolaşımına izin verir.
- **Bluetooth (yalnızca Samsung KNOX)** - Cihazda Bluetooth’un kullanımına izin verir.
- **NFC (yalnızca Samsung KNOX)** - Desteklenen cihazlarda yakın alan iletişimi kullanan işlemlere izin verir.
- **Wi-Fi (yalnızca Samsung KNOX)** - Cihazın Wi-Fi özelliklerinin kullanımına izin verir.
- **Wi-Fi paylaşımı (yalnızca Samsung KNOX)** - Cihazda Wi-Fi paylaşımının kullanılmasına izin verir.

## <a name="kiosk"></a>Bilgi noktası

Bilgi noktası ayarları, Samsung KNOX Standard cihazlar için geçerlidir.

- **Yönetilen bir uygulama seçin** - Cihaz bilgi noktası modunda olduğunda çalışabilen bir veya daha fazla uygulama eklemek için aşağıdaki seçeneklerden birini belirleyin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez.
    - **Paket adına göre uygulama ekleme**
    - **URL’ye göre uygulama ekleme**
    - **Yönetilen uygulamalar ekleme**.
- **Ekran uyku düğmesi** - Ekranda uykuya geçme ve uyandırma düğmesini etkinleştirir veya devre dışı bırakır.
- **Ses düğmeleri** - Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.


## <a name="next-steps"></a>Sonraki adımlar

Cihaz kısıtlama profilini oluşturmak ve sonra atamak için [Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md) makalesindeki yönergeleri kullanarak devam edin.