---
title: "Android için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune on Azure
description: "Android cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44d80e1c72b58eccd4e69b1d561c7d651f39b3c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Android ve Samsung KNOX Standard cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihazları kuruluşunuzda yapılandırmak için bu ayarları bir Android cihaz kısıtlama ilkesiyle birlikte kullanın.

## <a name="general"></a>Genel

|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Kamera**|Cihaz kamerasının kullanılmasına izin verir.|Evet|Evet|
|**Kopyala ve yapıştır**|Cihazda kopyalama ve yapıştırma işlevine izin verir.|Hayır|Evet|
|**Uygulamalar arasında pano paylaşımı**|Uygulamalar arasında kopyalama ve yapıştırma için panonun kullanılmasına izin verir.|Hayır|Evet|
|**Tanılama veri gönderimi**|Kullanıcının cihazdan tanılama verileri göndermesini durdurur.|Hayır|Evet|
|**Fabrika sıfırlaması**|Kullanıcının cihazda fabrika sıfırlaması gerçekleştirmesine izin verir.|Hayır|Evet|
|**Coğrafi Konum**|Cihazın konum bilgilerini kullanmasına izin verir (yalnızca Samsung KNOX Standard).|Hayır|Evet|
|**Kapatma**|Kullanıcının cihazı kapatmasına izin verir.<br>Devre dışı bırakılırsa **Cihaz silinmeden önceki oturum açma hatası sayısı** ayarlanamaz.|Hayır|Evet|
|**Ekran yakalama**|Kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.|Hayır|Evet|
|**Sesli yardım**|Cihazda sesli yardım yazılımının kullanımına izin verir.|Hayır|Evet|
|**YouTube**|Cihazda YouTube uygulamasının kullanılmasına izin verir.|Hayır|Evet|
|**Paylaşılan cihazlar**|Yönetilen bir Samsung KNOX Standard cihazını paylaşılan olarak yapılandırın. Bu modda, son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da yönetilmeye devam eder.<br>Oturum açan kullanıcılar kendilerine atanan uygulamalara ilkelere otomatik olarak erişir. Kullanıcılar oturumu kapattığında tüm veriler silinir.|Hayır|Evet|

## <a name="password"></a>Parola

|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Parola**|Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.|Evet|Evet|
|**En düşük parola uzunluğu**|Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (4 ile 16 karakter arasında).|Evet|Evet|
|**Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**|Cihaz otomatik olarak kilitlenmeden önce işlem yapılmayan dakika sayısını belirtir.|Evet|Evet|
|**Cihaz silinmeden önceki oturum açma hatası sayısı**|Cihaz silinmeden önce başarısız oturum açma sayısını belirtir.|Evet|Evet|
|**Parola kullanım süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Gerekli parola türü**|Gereken parola karmaşıklık düzeyini ve biyometrik cihaz kullanılıp kullanılamayacağını belirtir. Aşağıdakilerden birini seçin:<br><br>    -     **Cihaz varsayılanı**<br>-     **Düşük güvenlik biyometriği**<br>    -     **En az sayısal**<br>    -     **Sayısal karmaşık** - ('1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez)<sup>1</sup><br>    -     **En az alfabetik**<br>    -     **En az alfasayısal**<br>    -     **En az simgeler ile alfasayısal**|Evet|Evet|
|**Önceki parolaların yeniden kullanılmasını engelleme**|Son kullanıcının daha önce kullanmış olduğu bir parolayı oluşturmasını engeller.|Evet|Evet|
|**Parmak izi ile kilit açma**|Desteklenen cihazların kilidini açmak için parmak izi kullanımına izin verir.|Hayır|Evet|
|**Akıllı Kilitleme ve diğer güven aracıları**|Uyumlu Android cihazlarda Akıllı Kilit özelliğini denetlemenize olanak tanır (Samsung KNOX Standard 5.0 ve üstü). Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin, cihaz belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda bu kullanılabilir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.|Evet (5.0 ve üzeri)|Evet|
|**Şifreleme**|Cihazdaki dosyaların şifrelenmesini gerektirir.|Evet|Evet|

<sup>1</sup> Bu ayarı cihazlara atamadan önce, Şirket Portalı uygulamasının bu cihazlarda en son sürüme güncelleştirilmiş olduğundan emin olun.

**Sayısal karmaşık** ayarını yapılandırıp, bunu Android 5.0 öncesi bir sürümü çalıştıran cihaza atarsanız aşağıdaki davranış uygulanır.
- Şirket Portalı uygulaması 1704 öncesi bir sürümü çalıştırıyorsa cihaza PIN ilkesi uygulanmaz ve Intune portalında bir hata görüntülenir.
- Şirket Portalı uygulaması 1704 veya üzeri bir sürüm çalıştırıyorsa yalnızca basit bir PIN uygulanabilir. Android 5.0 öncesi sürümlerde bu ayar desteklenmez. Intune portalında herhangi bir hata görüntülenmez.


## <a name="google-play-store"></a>Google Play Store

|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Google Play mağazası**|Kullanıcının cihazda Google Play mağazasına erişmesine izin verir|Hayır|Evet|

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
|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Web tarayıcısı**|Cihazın varsayılan web tarayıcısının kullanılıp kullanılamayacağını belirtir.|Hayır|Evet|
|**Otomatik doldurma**|Kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.|Hayır|Evet|
|**Çerezler**|Cihazın web tarayıcısının tanımlama bilgileri kullanmasına izin verir.|Hayır|Evet|
|**Javascript**|Cihazın web tarayıcısının Java betiklerini çalıştırmasına izin verir.|Hayır|Evet|
|**Açılır pencereler**|Web tarayıcısında açılır pencere engelleyicisinin kullanılmasına izin verir.|Hayır|Evet|

## <a name="cloud-and-storage"></a>Bulut ve Depolama
|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Google yedeklemesi**|Google yedeklemesi kullanmaya izin verir.|Hayır|Evet|
|**Google hesabı otomatik eşitlemesi**|Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.|Hayır|Evet|
|**Çıkarılabilir depolama birimi**|Cihazda SD kartı gibi çıkarılabilir depolama birimi kullanılmasına izin verir.|Hayır|Evet|
|**Depolama kartlarında şifreleme**|Cihaz depolama kartını şifrelemenin gerekip gerekmediğini belirtir.|Hayır|Evet|

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı
|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Veri dolaşımı**|Cihaz, cep telefonu şebekesindeyken veri dolaşımına izin verir).|Hayır|Evet|
|**SMS/MMS iletileri**|Cihazda SMS ve MMS mesajlaşması kullanımına izin verir.|Hayır|Evet|
|**Sesli arama**|Cihazda sesli arama özelliğinin kullanımını etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Ses dolaşımı**|Cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.|Hayır|Evet|
|**Bluetooth**|Cihazda Bluetooth özelliğinin kullanımına izin verir.|Hayır|Evet|
|**NFC**|Desteklenen cihazlarda yakın alan iletişimi kullanan işlemlere izin verir.|Hayır|Evet|
|**Wi-Fi**|Cihazın Wi-Fi özelliklerinin kullanımına izin verir.|Hayır|Evet|
|**Wi-Fi İnternet paylaşımı**|Cihazda Wi-Fi internet paylaşımı kullanımına izin verir.|Hayır|Evet|

## <a name="kiosk"></a>Bilgi noktası
|||||
|-|-|-|-|
|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|**Yönetilen uygulama seçin**|Cihaz bilgi noktası modunda olduğunda çalıştırılabilen bir veya daha fazla uygulama eklemek için aşağıdaki seçeneklerden birini belirleyin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez.<br><br>- **Paket adına göre uygulama ekleme**<br>- **URL’ye göre uygulama ekleme**<br>- **Yönetilen uygulamalar ekleme**|Hayır|Evet|
|**Ekran uyku düğmesi**|Cihazın açma/kapatma düğmesini etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Ses düğmeleri**|Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
