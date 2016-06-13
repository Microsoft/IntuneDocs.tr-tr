---
# required metadata

title: Exchange ActiveSync ilkesi ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Exchange ActiveSync ilkesi ayarları
Exchange ActiveSync tarafından yönetilen cihazlardaki özellikleri ve işlevleri denetlemenize olanak sağlayan ayarları yapılandırmak için Microsoft Intune **Exchange ActiveSync** ilkesini kullanın.


## Parola ayarları

|Ayar adı|Ayrıntılar
|----------------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Cihazların parola kullanılarak kilitlenip kilitlenmeyeceğini belirtir.<br>(Windows RT çalıştıran cihazlara uygulanamaz)|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|
|**Minimum parola uzunluğu**|Cihaz parolasında bulunması gereken minimum karakter sayısını belirtir.|
|**Basit parolalara izin ver**|Basit parolalar '0000' ve '1234' şeklindedir.|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Cihaz temizlenmeden önce doğru parolayı girmek için burada belirtilen sayıda girişimde bulunulmasına izin verir.|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının kaç gün sonra değiştirilmesi gerektiğini belirtir.
|**Parola geçmişini anımsa**|Önceden kullanılmış parolaların kullanımına izin verilip verilmeyeceğini belirtir.|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış olan parolalardan kaç tanesinin yeniden kullanılamayacağını belirtir.|
|**Parola gerekmeden önce etkin olmama süresi (dakika)**|Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.

## Şifreleme ayarları

|Ayar adı|Ayrıntılar|
|----------------|
|**Mobil cihazda şifreleme iste**<sup>1</sup>|Desteklendiği durumlarda cihazdaki verilerin şifrelenmesini zorunlu tutar.<br>Windows Phone 8 cihazları için bunu **Evet**olarak ayarlamanız gerekir.<br /><br />iOS cihazlarda şifrelemeyi etkinleştirmek için **Mobil cihazların kilidini açmak için parola iste**ayarını etkinleştirin.|
|**Depolama kartlarında şifrelemeyi gerektir**|SD kartı gibi dış depolama alanlarında depolanan verilerin şifrelenmesini zorunlu tutar (desteklenen cihazlarda).
<sup>1</sup> Windows 8.1 çalıştıran cihazlar için ek bilgiler

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](http://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft Hesabının olması gerekir.

-   Şifrelemenin çalışması için cihazın, Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Bir cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft Hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## E-posta ayarları

|Ayar adı|Ayrıntılar
|----------------|
|**Kullanıcıların e-posta eklerini indirmesine izin ver**|E-posta eklerinin cihaza indirilip indirilmeyeceğini belirtir.|
|**E-posta eşitleme dönemi**|Alınan e-postanın cihazla eşitlenmesi için gün sayısını seçin.
|**Exchange ActiveSync ayarlarını tam olarak desteklemeyen mobil cihazların Exchange ile eşitleme yapmasına izin ver**|Bir veya birden çok Exchange ActiveSync ayarını desteklemeyen cihazlarda Exchange erişimine izin verilip verilmeyeceğini belirtir.

## Tarayıcı ayarları

|Ayar adı|Ayrıntılar
|----------------|-
|**Web tarayıcısına izin ver**|Cihazda web tarayıcısının kullanılıp kullanılamayacağını belirtir.<br>(Windows RT veya Windows Phone’da kullanılamaz)

## Donanım ayarları

|Ayar adı|Ayrıntılar
|----------------|
|**Kameraya izin ver**|Cihazdaki kameranın kullanılıp kullanılamayacağını belirtir.<br>(Windows RT veya Windows Phone’da kullanılamaz)



### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO2-->


