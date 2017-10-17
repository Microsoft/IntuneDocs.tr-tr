---
title: "Exchange ActiveSync ilkesi ayarları"
description: "Exchange ActiveSync tarafından yönetilen cihazlardaki özellikleri ve işlevleri denetlemenize olanak sağlayan ayarları yapılandırmak için, Intune Exchange ActiveSync ilkesini kullanın."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1dd762af4295c788202150799ef60b748fe7de21
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="exchange-activesync-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Exchange ActiveSync ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Exchange ActiveSync tarafından yönetilen cihazlardaki özellikleri ve işlevleri denetleyen ayarları yapılandırmak için Microsoft Intune **Exchange ActiveSync** ilkesini kullanın.


## <a name="password-settings"></a>Parola ayarları

|Ayar adı|Ayrıntılar
|----------------|---|
|**Mobil cihazların kilidini açmak için bir parola iste**|Cihazların parola kullanılarak kilitlenip kilitlenmeyeceğini belirtir.<br>(Windows RT çalıştıran cihazlara uygulanamaz).|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|
|**En düşük parola uzunluğu**|Cihaz parolasında bulunması gereken en az karakter sayısını belirtir.|
|**Basit parolalara izin ver**|‘0000’ ve ‘1234’ gibi basit parolalar kullanıp kullanamayacağınızı belirtir.|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Cihaz temizlenmeden önce bir kullanıcının kaç kez hatalı parola girebileceğini belirtir.|
|**Parola kullanım süresi (gün)**|Cihaz parolasının kaç gün sonra değiştirilmesi gerektiğini belirtir.
|**Parola geçmişini anımsa**|Önceden kullanılmış parolaların kullanımına izin verilip verilmeyeceğini belirtir.|
|**Parola geçmişini anımsa** – **Önceki parolaların yeniden kullanılmasını önle**|Daha önce kullanılan kaç parolanın yeniden kullanılamayacağını belirtir.|
|**Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Ekran kilitlenmeden önce cihazın boşta beklemesi gereken süreyi belirtir.

## <a name="encryption-settings"></a>Şifreleme ayarları

|Ayar adı|Ayrıntılar|
|----------------|---|
|**Mobil cihazda şifreleme iste**<sup>1</sup>|Desteklendiği durumlarda bir cihazdaki verilerin şifrelenmesini zorunlu kılar.<br><br>Windows Phone 8 cihazları için bunu **Evet**olarak ayarlamanız gerekir.<br /><br />iOS cihazlarda şifrelemeyi etkinleştirmek için **Mobil cihazların kilidini açmak için parola iste** ayarını etkinleştirin.|
|**Depolama kartlarında şifreleme iste**|SD kartı gibi dış depolama alanlarında depolanan verilerin şifrelenmesini zorunlu kılar (desteklenen cihazlarda).
<sup>1</sup> Windows 8.1 çalıştıran cihazlar için ek bilgiler

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorunlu kılmak istiyorsanız [Windows için Aralık 2014 MDM istemci güncelleştirmesi](https://support.microsoft.com/kb/3013816)’ni her bir cihaza yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft hesabı olmalıdır.

-   Şifrelemenin Windows 8.1 cihazlarda çalışmasını istiyorsanız cihazın Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Bir Windows 8.1 cihazda şifrelemeyi zorunlu kılarsanız kurtarma anahtarına yalnızca kullanıcının OneDrive hesabına erişmek için gerekli olan Microsoft Hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## <a name="email-settings"></a>E-posta ayarları

|Ayar adı|Ayrıntılar
|----------------|---|
|**Kullanıcıların e-posta eklerini indirmesine izin ver**|E-posta eklerinin cihaza indirilip indirilmeyeceğini belirtir.|
|**E-posta eşitleme süresi**|Alınan e-postaların cihazla kaç gün boyunca eşitleneceğini belirtir.
|**Exchange ActiveSync ayarlarını tam olarak desteklemeyen mobil cihazların Exchange ile eşitleme yapmasına izin ver**|Bir veya birden çok Exchange ActiveSync ayarını desteklemeyen cihazlarda Exchange erişimine izin verilip verilmeyeceğini belirtir.

## <a name="browser-settings"></a>Tarayıcı ayarları

|Ayar adı|Ayrıntılar
|----------------|---|
|**Web tarayıcısına izin ver**|Cihazda web tarayıcısının kullanılıp kullanılamayacağını belirtir.<br>(Windows RT veya Windows Phone’da kullanılamaz).

## <a name="hardware-settings"></a>Donanım ayarları

|Ayar adı|Ayrıntılar
|----------------|---|
|**Kameraya izin ver**|Cihazdaki kameranın kullanılıp kullanılamayacağını belirtir.<br>(Windows RT veya Windows Phone’da kullanılamaz).



### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
