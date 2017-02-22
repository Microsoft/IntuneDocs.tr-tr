---
title: "Android için Intune cihaz kısıtlama ayarları | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Android cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 74023866802eb4c13e7e9ff97e8048afe7d62409
ms.openlocfilehash: 40e04f1f8e7972bcd72cceae272d8295a496df7a


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-intune-azure-preview"></a>Intune Azure önizlemesinde Android ve Samsung KNOX Standard cihaz kısıtlama ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Genel
-   **Kamera** - Cihaz kamerasının kullanılmasına izin verir.
-   **Kopyala ve Yapıştır** - Cihazda kopyalama ve yapıştırma işlevlerine izin verir.
-   **Uygulamalar arasında pano paylaşımı** - Uygulamalar arasında kopyalama ve yapıştırma işlemleri için panonun kullanımına izin verir (yalnızca Samsung KNOX Standard).
-   **Tanılama verileri gönderme** - Kullanıcının cihazdan tanılama verileri göndermesini durdurur.    
-   **Fabrika sıfırlaması** - Kullanıcının cihazda fabrika sıfırlaması gerçekleştirmesine izin verir.
-   **Coğrafi konum** - Cihazın konum bilgilerini kullanmasına izin verir (yalnızca Samsung KNOX Standard).
-   **Kapatma** - Kullanıcının cihazı kapatmasına izin verir.<br>Bu ayar devre dışı bırakılırsa, Samsung KNOX Standard cihazları için **Cihaz silinmeden önceki oturum açma hatası sayısı** ayarı çalışmaz.
-   **Ekran yakalama** - Kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
-   **Sesli yardımcı** - Cihazda sesli yardım yazılımının kullanımına izin verir (yalnızca Samsung KNOX Standard).
-   **YouTube** - Cihazda YouTube uygulamasının kullanımına izin verir (yalnızca Samsung KNOX Standard).

## <a name="password"></a>Parola
-   **Parola gerekli** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
-   **En az parola uzunluğu** - Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (4 ile 16 karakter arasında).
-   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Cihaz otomatik olarak kilitlenmeden önce işlem yapılmayan dakika sayısını belirtir.
-   **Cihaz silinmeden önceki oturum açma hatası sayısı** - Cihaz silinmeden önce başarısız oturum açma sayısını belirtir.
-   **Parola geçerlilik süresi (gün)** - Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.
-   **Gerekli parola türü** - Gereken parola karmaşıklık düzeyini ve biyometrik cihaz kullanılıp kullanılamayacağını belirtir.
-   **Önceki parolaların yeniden kullanılmasını engelle** - Son kullanıcının daha önce kullanmış olduğu bir parolayı oluşturmasını durdurur.
-   **Parmak izi ile kilit açmaya izin ver** - Desteklenen cihazların kilidini açmak için parmak izi kullanımına izin verir.
-   **Akıllı Kilitleme ve diğer güven aracıları** - Uyumlu Android cihazlarda Akıllı Kilitleme özelliğini denetlemenize olanak tanır (Samsung KNOX Standard 5.0 ve üstü). Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.
-   **Şifreleme** - Cihazdaki dosyaların şifrelenmesini gerektirir.

## <a name="google-play-store"></a>Google Play Store

-   **Google Play Store** - Kullanıcının cihazda Google Play Store’a erişmesine izin verir (yalnızca Samsung KNOX Standard).

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

**Yasak uygulamalar** listesi - Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.
**Onaylı uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Uyumluluğun korunması için kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.
Kısıtlı uygulama ayarlarını içeren cihaz profilleri kullanıcı gruplarına dağıtılmalıdır.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra da tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Mağazadaki uygulamanın URL’sini belirtme

Uyumlu veya uyumsuz uygulama listesinde bir uygulama URL'si belirtmek için aşağıdaki adımları uygulayın:

[Google Play'in uygulamalar bölümünde](https://play.google.com/store/apps) kullanmak istediğiniz uygulamayı arayın.

Uygulamanın yükleme sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde gerekli URL olarak kullanabilirsiniz.

Örnek: Microsoft Office Mobile için Google Play'i arayın. Kullandığınız URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub** olacaktır.

### <a name="additional-options"></a>Ek seçenekler

Ayrıca, **İçeri Aktar**’a tıklayarak listeyi <*uygulama url’si*>, <*uygulama adı*>, <*uygulama yayımcısı*> biçimindeki bir csv dosyasından doldurabilir veya **Dışarı Aktar**’a tıklayarak kısıtlı uygulama listesinin içeriğiyle, aynı biçimde bir csv dosyası oluşturabilirsiniz.      

## <a name="browser"></a>Tarayıcı
-   **Web tarayıcısı** - Cihazın varsayılan web tarayıcısının kullanılıp kullanılamayacağını belirtir.
-   **Otomatik doldurma** - Kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.
-   **Tanımlama bilgileri** - Cihazın web tarayıcısının tanımlama bilgileri kullanmasına izin verir.
-   **Javascript** - Cihazın web tarayıcısının Java betiklerini çalıştırmasına izin verir.
-   **Açılır pencereler** - Web tarayıcısında açılır pencere engelleyicisinin kullanılmasına izin verir.

## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **Google yedekleme** - Google yedeklemesinin kullanılmasına izin verir.
-   **Google hesabı otomatik eşitlemesi** - Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.
-   **Çıkarılabilir depolama birimi** - Cihazın SD kartı gibi bir çıkarılabilir depolama birimi kullanmasına izin verir (yalnızca Samsung KNOX Standard).
-   **Depolama kartlarında şifreleme** - Cihazın depolama kartını şifrelemenin gerekip gerekmediğini belirtir.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı
-   **Veri dolaşımı** - Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir (yalnızca Samsung KNOX Standard).
-   **SMS/MMS mesajları** - Cihazda SMS ve MMS mesajlarının kullanılmasına izin verir (yalnızca (Samsung KNOX Standard).
-   **Sesli arama** - Cihazda sesli arama özelliğini etkinleştirir veya devre dışı bırakır (yalnızca Samsung KNOX Standard).
-   **Ses dolaşımı** - Cihaz hücresel ağ üzerindeyken ses dolaşımına izin verir (yalnızca Samsung KNOX Standard).
-   **Bluetooth** - Cihazda Bluetooth’un kullanımına izin verir (yalnızca Samsung KNOX Standard).
-   **NFC** - Cihaz destekliyorsa, yakın alan iletişimi kullanan işlemlere izin verir (yalnızca Samsung KNOX Standard).
-   **Wi-Fi** - Cihazın Wi-Fi özelliklerinin kullanımına izin verir (yalnızca Samsung KNOX Standard).
-   **Wi-Fi paylaşımı** - Cihazda Wi-Fi paylaşımının kullanılmasına izin verir (yalnızca Samsung KNOX Standard).

## <a name="kiosk"></a>Bilgi noktası
-   **Yönetilen uygulama seçin** - Cihaz bilgi noktası modundayken çalıştırılabilecek yönetilen uygulamaya göz atın ve seçim yapın (mağazaya bir bağlantıyla belirtilen uygulamalar henüz desteklenmemektedir). Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez.
-   **Ekran uyku düğmesi** - Ekranda uykuya geçme ve uyandırma düğmesini etkinleştirir veya devre dışı bırakır.
-   **Ses düğmeleri** - Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.



<!--HONumber=Feb17_HO1-->


