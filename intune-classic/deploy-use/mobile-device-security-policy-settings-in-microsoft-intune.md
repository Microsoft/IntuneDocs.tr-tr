---
title: "Mobil cihaz güvenlik ilkesi ayarları"
description: "Kuruluşunuzdaki yönetilen cihazlara dağıtabileceğiniz çeşitli ayarları yapılandırmak için Intune’u kullanın."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fa86e50ebf7e65be0ce8ace65e2cb0bc7e38658e
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="mobile-device-security-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da mobil cihaz güvenliği ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

> [!IMPORTANT]
> Microsoft Intune artık her cihaz platformu için ayrı yapılandırma ilkeleri sağlamaktadır. Bu ilkeler, kullanabileceğiniz en güncel ayarları içerir. Mobil cihaz güvenliği ilkesini kullanmaya devam edebilirsiniz ve var olan dağıtımlar çalışmaya devam eder. Ancak, mobil cihaz güvenliği ilkesi yakında kaldırılacağı için, yeni yapılandırma ilkelerine geçişi en kısa sürede planlamanız gerekir.

Kuruluşunuzdaki yönetilen cihazlara dağıtabileceğiniz çeşitli ayarları yapılandırmak için Intune mobil cihaz güvenliği ilkelerini kullanabilirsiniz. Bu ayarlar, cihazlarınızın işlevsellik ve güvenliğini denetlemek için kullanılır.

Aşağıdaki cihaz türleri için mobil cihaz güvenlik ilkeleri oluşturabilir ve dağıtabilirsiniz:

-   Windows RT 8.1 ve kayıtlı Windows 8.1 cihazlar

-   Windows RT

-   Windows Phone 8 ve Windows Phone 8.1

-   iOS

-   Android ve Samsung KNOX Standard

> [!NOTE]
> Bazı ayarlar bazı cihazlar için geçerli değildir. Yapılandırabileceğiniz ayarların tam listesi için aşağıdaki tabloya bakın.
> Microsoft Intune, Ekim 2016'dan itibaren Windows 8 Şirket Portalı uygulamaları için desteği kaldıracaktır. Microsoft Intune, ayrıca Windows Phone 8 ve WinRT platformları için desteği kaldıracaktır. Bu nedenle bundan sonra herhangi bir Windows Phone 8 veya WinRT cihazını kaydetmeniz veya güncelleştirmeniz mümkün olmayacaktır. Daha önce kaydedilen Windows Phone 8, WinRT ve Windows 8 cihazlarını yönetmeye devam edebilirsiniz. Windows 8 ve Windows Phone 8 cihazlarını Windows 8.1’e ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara bir kesinti olmadan uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.

## <a name="security-settings"></a>Güvenlik ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Mobil cihazların kilidini açmak için bir parola iste**|Hayır|Hayır|Evet|Evet|Evet|
|**Gerekli parola türü**<br /><br />Bu ayar, gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|Evet|Evet|Evet|Evet|Hayır|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**<br /><br />Dört karakter kümesi vardır: küçük harfler, büyük harfler, rakamlar ve simgeler. Bu ayar parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir. Bununla birlikte, iOS cihazları için bu ayar, parolanın içermesi gereken simge karakterlerinin sayısını belirtir.|Evet|Evet|Evet|Evet|Hayır|
|**En düşük parola uzunluğu**|Evet|Evet|Evet|Evet|Evet|
|**Basit parolalara izin ver**<br /><br />Basit parolalar '0000' ve '1234' şeklindedir.|Hayır|Hayır|Evet|Evet|Hayır|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Evet|Evet|Evet|Evet|Evet|
|**Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı**<sup>1</sup>|Evet|Evet|Evet|Evet|Evet|
|**Parola kullanım süresi (gün)**|Evet|Evet|Evet|Evet|Evet|
|**Parola geçmişini anımsa**|Evet|Evet|Evet|Evet|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Evet|Evet|Evet|Evet|Evet|
|**Parola kalitesi**|Hayır|Hayır|Hayır|Hayır|Evet|
|**Resimli parolaya veya PIN’e izin ver**|Evet|Evet|Hayır|Hayır|Hayır|
|**Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Parmak izi ile kilit açmaya izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
<sup>1</sup> iOS cihazlarda **Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı** ve **Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı** ayarlarını sırayla uygulayarak yapılandırın. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran 5 dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için 5 dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki 5 dakikanın sonunda cihaz kilitlenir.

Windows RT çalıştıran cihazlara bir parola uzunluğu ilkesi dağıttığınızda, kullanıcılar geçerli parolaları ilke gereksinimlerine uysa bile parolalarını sıfırlamaya zorlanır.

## <a name="encryption-settings"></a>Şifreleme ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Mobil cihazda şifreleme iste**<sup>1</sup><br /><br />Windows Phone 8 cihazları için bunu **Evet**olarak ayarlamanız gerekir.<br /><br />iOS cihazlarda şifrelemeyi etkinleştirmek için **Mobil cihazların kilidini açmak için parola iste**ayarını etkinleştirin.|Evet|Hayır|Evet|Hayır|Evet|
|**Depolama kartlarında şifreleme iste**<br /><br />Bu ayar, Exchange ActiveSync tarafından yönetilen cihazlar için de geçerlidir.|yok|yok|yok <br />Uygulamalar ve ilişkili veriler otomatik olarak şifrelenir.|yok|Evet|
<sup>1</sup>Windows 8.1 çalıştıran cihazlar için ek bilgiler:

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](http://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft hesabı olmalıdır.

-   Şifrelemenin çalışması için cihazın, Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## <a name="malware-settings"></a>Kötü amaçlı yazılım ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Ağ güvenlik duvarı iste**|Evet|Hayır|Hayır|Hayır|Hayır|
|**SmartScreen’i etkinleştir**|Evet|Hayır|Hayır|Hayır|Hayır|

## <a name="system-settings"></a>Sistem ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Otomatik güncelleştirmeleri zorunlu kıl**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Otomatik güncelleştirmeleri zorunlu kıl - Otomatik olarak yüklenecek güncelleştirmelerin en düşük sınıflandırması**<br /><br />Otomatik olarak yüklenecek güncelleştirmelerin sınıflandırmasını seçin:<br /><br />- **Önemli**. Önemli olarak sınıflandırılan tüm güncelleştirmeleri yükler.<br /><br />- **Önerilen**. Önemli veya önerilen olarak sınıflandırılan tüm güncelleştirmeleri yükler.|Evet|Hayır|Hayır|Hayır|Hayır|
|**Ekran yakalamaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Kilit ekranında denetim merkezine izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Kilit ekranında bildirim görünümüne izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Kilit ekranında bugün görünümüne izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Kullanıcı Hesap Denetimi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Tanılama verilerinin gönderimine izin ver**|Evet|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Güvenilmeyen TLS sertifikalarına izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Kilitliyken kişisel cüzdan yazılımına izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Fabrika sıfırlamasına izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|


## <a name="cloud-settings--documents-and-data"></a>Bulut ayarları – belgeler ve veriler

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**iCloud'a yedeklemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**iCloud'a belge eşitlemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**iCloud'a Fotoğraf Yayını’nı eşitlemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Şifreli yedekleme iste**|Hayır|Hayır|Hayır|Evet|Hayır|
|**İş Klasörleri URL**<br /><br />Bu ayar, belgelerin cihazlar arasında eşitlenmesine izin vermek için iş klasörünün URL’sini ayarlar.|Evet|Hayır|Hayır|Hayır|Hayır|
|**Google yedeklemesine izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|

## <a name="cloud-settings--accounts-and-synchronization"></a>Bulut ayarları – hesaplar ve eşitleme

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Microsoft hesabına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|
|**Google hesabı otomatik eşitlemesine izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|

## <a name="email-settings"></a>E-posta ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Kullanıcıların e-posta eklerini indirmesine izin ver**<sup>1</sup>|yok|yok|yok|yok|yok|
|**E-posta eşitleme süresi** <br /><br />Bu ayar, Exchange ActiveSync tarafından yönetilen cihazlar için de geçerlidir.|yok|yok|yok|yok|yok|
|**Bu ayarları tam olarak desteklemeyen mobil cihazların Exchange ile eşitleme yapmasına izin verin (Exchange ActiveSync)** <br /><br />Bu ayar, Exchange ActiveSync tarafından yönetilen cihazlar için de geçerlidir.|yok|yok|yok|yok|yok|
|**Microsoft hesabını Windows Mail uygulamasında isteğe bağlı hale getir**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Özel e-posta hesaplarına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|

## <a name="application-settings---browser"></a>Uygulama ayarları - tarayıcı

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Web tarayıcısına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Otomatik doldurmaya izin ver**|Evet|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Açılır pencere engelleyicisine izin ver**|Evet|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Tanımlama bilgilerine izin ver**|Hayır|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Eklentilere izin ver**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Etkin betik yazmaya izin ver**|Evet|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Sahtekarlık uyarısına izin ver**|Evet|Hayır|Hayır|Evet|Hayır|
|**Tek sözcüklük girişler için intranet sitesine izin ver**<br /><br />(Bu ayar Internet Explorer’ı bir web sitesine yönlendirmek için ‘Bing’ gibi tek bir sözcüğün kullanılmasına izin verir.)|Evet|Hayır|Hayır|Hayır|Hayır|
|**İntranet ağının otomatik algılanmasına izin ver**|Evet|Hayır|Hayır|Hayır|Hayır|
|**İnternet için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**İntranet için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Güvenilir siteler için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Yasal siteler için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Do Not Track üst bilgisi gönder**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Kuruluş Modu menüsü erişimine izin ver**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Kurumsal Mod site listesi konumu**|Evet|Hayır|Hayır|Hayır|Hayır|

## <a name="application-settings---apps"></a>Uygulama ayarları - uygulamalar

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Uygulama depolamaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Uygulama mağazasına erişim için parola iste**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Uygulama içi satın almalara izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Diğer yönetilmeyen uygulamalardaki yönetilen belgelere izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Diğer yönetilen uygulamalardaki yönetilmeyen belgelere izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Görüntülü konferansa izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Medya mağazasında yetişkinlere yönelik içeriğe izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Uygulama yüklemesine izin ver**|Hayır|Hayır|Hayır|iOS 6 ve üzeri|Hayır|

## <a name="application-settings---gaming"></a>Uygulama ayarları - oyun

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Game Center arkadaşlarına izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Çok oyunculu oyunlara izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|

## <a name="device-capabilities-settings---hardware"></a>Cihaz özellikleri ayarları - donanım

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Kameraya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet|
|**Çıkarılabilir depolamaya izin ver**|Hayır|Hayır|Evet|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**Wi-Fi bağlantısına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**Wi-Fi İnternet paylaşımına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|
|**Wi-Fi etkin noktası raporlamasına izin ver**<br /><br />Bu ayar, yakındaki bağlantıların keşfedilmesine yardımcı olmak için Wi-Fi bağlantıları hakkında bilgi gönderir.|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|
|**Coğrafi konuma izin ver**<br /><br />Bu ayar, cihazın konum bilgilerini kullanmasına izin verir.|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**NFC'ye izin ver**<br /><br />Bu ayar, yakın alan iletişimi kullanan işlemlere izin verir.|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**Bluetooth'a izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**Kapatmaya izin ver**<br>Bu ayar devre dışı bırakılırsa, Samsung KNOX Standard cihazları için **Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatalarının sayısı** ayarı çalışmaz.|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|

## <a name="device-capabilities-settings---cellular"></a>Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Ses dolaşımına izin ver**|Hayır|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Veri dolaşımına izin ver**|Evet|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Dolaşım sırasında otomatik eşitlemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**SMS/MMS iletilerine izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|

## <a name="device-capabilities-settings---features"></a>Cihaz özellikleri ayarları - özellikler

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android ve Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Sesli yardıma izin ver**|Hayır|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Cihaz kilitliyken sesli yardıma izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Sesli aramaya izin ver**|Hayır|Hayır|Hayır|Evet|Evet (Yalnızca Samsung KNOX Standard)|
|**Kopyalama ve yapıştırmaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**Uygulamalar arasında pano paylaşımına izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|
|**YouTube'a izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (Yalnızca Samsung KNOX Standard)|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
