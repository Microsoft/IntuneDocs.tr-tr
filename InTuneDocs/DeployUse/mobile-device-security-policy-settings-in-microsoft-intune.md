---
title: "Mobil cihaz güvenliği ilkesi ayarları | Microsoft Intune"
description: "Kuruluşunuzdaki yönetilen cihazlara dağıtabileceğiniz çeşitli ayarları yapılandırmak için Intune’u kullanın."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 41813b383003311e68f2a7fb50d42638434649f7


---

# Microsoft Intune’da mobil cihaz güvenliği ilkesi ayarları
> [!IMPORTANT]
> Microsoft Intune’da artık her cihaz platformu için ayrı yapılandırma ilkeleri vardır ve bu ilkeler kullanabileceğiniz en güncel ayarları içerir. Mobil cihaz güvenliği ilkesini kullanmaya devam edebilirsiniz ve var olan dağıtımlar çalışmaya devam eder. Ancak, mobil cihaz güvenliği ilkesi yakında kaldırılacağından yeni yapılandırma ilkelerine geçişi en kısa sürede planlamanız gerekir.

Kuruluşunuzdaki yönetilen cihazlara dağıtabileceğiniz çeşitli ayarları yapılandırmak için Intune mobil cihaz güvenliği ilkelerini kullanın. Bu ayarlar, cihazlarınızın işlevsellik ve güvenliğini kontrol etmek için kullanılabilir.

Aşağıdaki cihaz türleri için mobil cihaz güvenlik ilkeleri oluşturabilir ve dağıtabilirsiniz:

-   Windows RT 8.1 ve kayıtlı Windows 8.1 cihazlar

-   Windows RT

-   Windows Phone 8 ve Windows Phone 8.1

-   iOS

-   Android be Samsung KNOX

> [!NOTE]
> Bazı ayarlar bazı cihazlar için geçerli değildir. Yapılandırabileceğiniz ayarların tam listesi için aşağıdaki tabloya bakın.

## Güvenlik ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Hayır|Hayır|Evet|Evet|Evet|
|**Gerekli parola türü**<br /><br />(gerekli parola türünü belirtir. Örneğin, yalnızca sayısal ya da alfasayısal gibi)|Evet|Evet|Evet|Evet|Hayır|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**<br /><br />Küçük harfler, büyük harfler, rakamlar ve semboller şeklinde dört karakter kümesi vardır. Bu ayar parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir). Ancak iOS cihazları için bu ayar, parolanın içermesi gereken sembol karakterlerinin sayısını belirtir)|Evet|Evet|Evet|Evet|Hayır|
|**Minimum parola uzunluğu**|Evet|Evet|Evet|Evet|Evet|
|**Basit parolalara izin ver**<br /><br />Basit parolalar '0000' ve '1234' şeklindedir|Hayır|Hayır|Evet|Evet|Hayır|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Evet|Evet|Evet|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**<sup>1</sup>|Evet|Evet|Evet|Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Evet|Evet|Evet|Evet|Evet|
|**Parola geçmişini anımsa**|Evet|Evet|Evet|Evet|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Evet|Evet|Evet|Evet|Evet|
|**Parola kalitesi**|Hayır|Hayır|Hayır|Hayır|Evet|
|**Resimli parolaya veya PIN’e izin ver**|Evet|Evet|Hayır|Hayır|Hayır|
|**Parola gerekmeden önce etkin olmama süresi (dakika)**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Parmak izi ile kilit açmaya izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
iOS cihazlarında **Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı** ve **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarlarını sırayla uygulayarak yapılandırın. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran 5 dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için 5 dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki 5 dakikanın sonunda cihaz kilitlenir.

Windows RT çalıştıran cihazlara bir parola uzunluğu ilkesi dağıtmayı ayarladığınızda kullanıcılar, geçerli parolaları ilke gereksinimlerine uysa bile parolalarını sıfırlamaya zorlanır.

## Şifreleme ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Mobil cihazda şifreleme iste**<sup>1</sup><br /><br />Windows Phone 8 cihazları için bunu **Evet**olarak ayarlamanız gerekir.<br /><br />iOS cihazlarda şifrelemeyi etkinleştirmek için **Mobil cihazların kilidini açmak için parola iste**ayarını etkinleştirin.|Evet|Hayır|Evet|Hayır|Evet|
|**Depolama kartlarında şifrelemeyi gerektir**<br /><br />Exchange ActiveSync tarafından yönetilen cihazlar için de geçerlidir.|yok|yok|yok (uygulamalar ve ilişkili veriler otomatik olarak şifrelenir)|yok|Evet|
Windows 8.1 çalıştıran cihazlar için ek bilgiler

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](http://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft Hesabının olması gerekir.

-   Şifrelemenin çalışması için cihazın, Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Bir cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft Hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## Kötü amaçlı yazılım ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Ağ güvenlik duvarı iste**|Evet|Hayır|Hayır|Hayır|Hayır|
|**SmartScreen’i etkinleştir**|Evet|Hayır|Hayır|Hayır|Hayır|

## Sistem ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Otomatik güncelleştirmeleri zorunlu kıl**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Otomatik güncelleştirmeleri zorunlu kıl - Otomatik olarak yüklenecek güncelleştirmelerin minimum sınıflandırması**<br /><br />Otomatik olarak yüklenecek güncelleştirmelerin sınıflandırmasını seçin:<br /><br />**Önemli** – Önemli olarak sınıflandırılan tüm güncelleştirmeleri yükler.<br /><br />**Önerilen** – Önemli veya önerilen olarak sınıflandırılan tüm güncelleştirmeleri yükler.|Evet|Hayır|Hayır|Hayır|Hayır|
|**Ekran yakalamaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (yalnızca Samsung KNOX)|
|**Kilit ekranında denetim merkezine izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Kilit ekranında bildirim görünümüne izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Kilit ekranında bugün görünümüne izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Kullanıcı Hesap Denetimi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Tanılama verilerinin gönderimine izin ver**|Evet|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (yalnızca Samsung KNOX)|
|**Güvenilmeyen TLS sertifikalarına izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Kilitliyken bireysel cüzdan yazılımına izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Fabrika sıfırlamasına izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|


## Bulut ayarları – belgeler ve veriler

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**iCloud'a yedeklemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**iCloud'a belge eşitlemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**iCloud'a Fotoğraf Akışını eşitlemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Şifreli yedekleme iste**|Hayır|Hayır|Hayır|Evet|Hayır|
|**İş Klasörleri URL**<br /><br />(belgelerin cihazlar arasında eşitlenmesine izin vermek için iş klasörünün URL’sini ayarlar)|Evet|Hayır|Hayır|Hayır|Hayır|
|**Google yedeklemesine izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|

## Bulut ayarları – hesaplar ve eşitleme

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Microsoft Hesabına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|
|**Google hesabı otomatik eşitlemesine izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|

## E-posta ayarları

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Kullanıcıların e-posta eklerini indirmesine izin ver**<sup>1</sup>|yok|yok|yok|yok|yok|
|**E-posta eşitleme dönemi** Exchange ActiveSync tarafından yönetilen cihazlar için de geçerlidir.|yok|yok|yok|yok|yok|
|**Bu ayarları tam olarak desteklemeyen mobil cihazların Exchange ile eşitleme yapmasına izin ver (Exchange ActiveSync)** Exchange ActiveSync tarafından yönetilen cihazlar için de geçerlidir.|yok|yok|yok|yok|yok|
|**Microsoft hesabını Windows Mail uygulamasında isteğe bağlı hale getir**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Özel e-posta hesaplarına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|

## Uygulama ayarları - tarayıcı

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Web tarayıcısına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (yalnızca Samsung KNOX)|
|**Otomatik doldurmaya izin ver**|Evet|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Açılır pencere engelleyicisine izin ver**|Evet|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Tanımlama bilgilerine izin ver**|Hayır|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Eklentilere izin ver**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Etkin betik yazmaya izin ver**|Evet|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Sahtekarlık uyarısına izin ver**|Evet|Hayır|Hayır|Evet|Hayır|
|**Tek kelimeli girişler için intranet sitesine izin ver**<br /><br />(Internet Explorer’ı 'Bing' gibi bir web sitesine yönlendirmek için tek bir sözcük kullanımına izin verir)|Evet|Hayır|Hayır|Hayır|Hayır|
|**Intranet ağının otomatik algılanmasına izin ver**|Evet|Hayır|Hayır|Hayır|Hayır|
|**İnternet için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Intranet için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Güvenilir siteler için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Yasal siteler için güvenlik düzeyi**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Takip Etme başlığını gönder**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Kurumsal Mod menüsüne erişime izin ver**|Evet|Hayır|Hayır|Hayır|Hayır|
|**Kurumsal Mod site listesi konumu**|Evet|Hayır|Hayır|Hayır|Hayır|

## Uygulama ayarları - uygulamalar

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Uygulama depolamaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet (yalnızca Samsung KNOX)|
|**Uygulama deposuna erişim için parola iste**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Uygulama içi satın almalara izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Diğer yönetilmeyen uygulamalardaki yönetilen belgelere izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Diğer yönetilen uygulamalardaki yönetilmeyen belgelere izin ver**|Hayır|Hayır|Hayır|iOS 7 ve üzeri|Hayır|
|**Görüntülü konferansa izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Medya mağazasında yetişkinlere yönelik içeriğe izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Uygulama yüklemesine izin ver**|Hayır|Hayır|Hayır|iOS 6 ve üzeri|Hayır|

## Uygulama ayarları - oyun

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Game Center arkadaşlarına izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Çok oyunculu oyunlara izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|

## Cihaz özellikleri ayarları - donanım

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Kameraya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Evet|Evet|
|**Çıkarılabilir depolama birimine izin ver**|Hayır|Hayır|Evet|Hayır|Evet (yalnızca Samsung KNOX)|
|**Wi-Fi'a izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (yalnızca Samsung KNOX)|
|**Wi-Fi İnternet paylaşımına izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (yalnızca Samsung KNOX)|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|
|**Wi-Fi etkin noktası bildirimine izin ver**<br /><br />(Yakındaki bağlantıların keşfedilmesine yardımcı olması için Wi-Fi bağlantıları hakkında bilgi gönder)|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Hayır|
|**Coğrafi konuma izin ver**<br /><br />(cihazın konum bilgilerini kullanmasına izin verir)|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (yalnızca Samsung KNOX)|
|**NFC'ye izin ver**<br /><br />(yakın alan iletişimi kullanan işlemlere izin verir)|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (yalnızca Samsung KNOX)|
|**Bluetooth'a izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (yalnızca Samsung KNOX)|
|**Kapatmaya izin ver**<br>Bu ayar devre dışı bırakılırsa, Samsung KNOX cihazları için **Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatalarının sayısı** ayarı çalışmaz.|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|

## Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Sesli dolaşıma izin ver**|Hayır|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Veri dolaşımına izin ver**|Evet|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Dolaşım sırasında otomatik eşitlemeye izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**SMS/MMS iletilerine izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|

## Cihaz özellikleri ayarları - özellikler

|Ayar adı|Windows 8.1 ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|iOS|Android be Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Sesli yardımcıya izin ver**|Hayır|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Cihaz kilitliyken sesli yardımcıya izin ver**|Hayır|Hayır|Hayır|Evet|Hayır|
|**Sesli aramaya izin ver**|Hayır|Hayır|Hayır|Evet|Evet (yalnızca Samsung KNOX)|
|**Kopyalama ve yapıştırmaya izin ver**|Hayır|Hayır|Yalnızca Windows Phone 8.1|Hayır|Evet (yalnızca Samsung KNOX)|
|**Uygulamalar arasında pano paylaşımına izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|
|**YouTube'a izin ver**|Hayır|Hayır|Hayır|Hayır|Evet (yalnızca Samsung KNOX)|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


