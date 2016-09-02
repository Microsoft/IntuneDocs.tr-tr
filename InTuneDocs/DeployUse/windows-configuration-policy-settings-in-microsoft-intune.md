---
title: "Windows ilke ayarları | Microsoft Intune"
description: "Kayıtlı Windows 8 ve Windows 8.1 cihazlarının ayarlarını yapılandırmak için Intune Windows genel yapılandırma ilkesini (Windows 8.1 ve üstü) kullanın."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7fdfe64a18fe359ee4b3b4507ef4108ad65ab573
ms.openlocfilehash: 3102e4637c61bbae002fb30947acd1f82204ac93


---

# Microsoft Intune’da Windows ilke ayarları
Kayıtlı Windows 8.1 ve Windows 8 cihazlarının aşağıdaki ayarlarını yapılandırmak için Microsoft Intune **Windows genel yapılandırma ilkesini (Windows 8.1 ve üstü)** kullanın:

## Uygulanabilirlik ayarları

|Ayar adı|Ayrıntılar|
|----------------|----------------------------------|
|**Tüm yapılandırmaları Windows 10'a uygula**|Bu ilkedeki ayarların Windows 8 ve Windows 8.1 cihazlarına ek olarak Windows 10 cihazlarına da uygulanmasını etkinleştirir.|

## Güvenlik ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (alfasayısal veya yalnızca sayısal gibi).|Evet|Evet|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir. Dört karakter kümesi vardır: küçük harfler, büyük harfler, rakamlar ve simgeler. Bununla birlikte, iOS cihazları için bu ayar, parolanın içermesi gereken simgelerin sayısını belirtir.|Evet|Evet|
|**Minimum parola uzunluğu**<sup>1</sup>|Parola için gereken minimum uzunluğu (karakter cinsinden) yapılandırır.|Evet|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Burada belirtilen sayıda oturum açma denemesi başarısız olursa, cihazı temizler.|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Kilidini açmak için parola gerekmeden önce cihazın ne kadar süreyle boşta kalacağını belirtir.| Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Kullanıcının önceden kullanılmış parolaları yapılandırıp yapılandıramayacağını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların yeniden kullanılmasını önle**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.|Evet|Evet|
|**Resimli parolaya veya PIN’e izin ver**|Resimli parola veya PIN kullanımını etkinleştirir. Resimli parola, kullanıcının resimdeki hareketlerle oturum açmasına olanak tanır. PIN, kullanıcıların dört basamaklı bir kodla hızla oturum açmalarına olanak tanır.|Evet|Evet|
<sup>1</sup> Windows RT çalıştıran cihazlara bir parola uzunluğu ilkesi dağıttığınızda, kullanıcılar geçerli parolaları ilke gereksinimlerine uysa bile parolalarını sıfırlamaya zorlanır.

## Şifreleme ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Mobil cihazda şifreleme iste**<sup>1</sup>|Cihazdaki dosyaların şifrelenmesini gerektirir.<br>Windows Phone 8 cihazları için bunu **Evet**olarak ayarlamanız gerekir.|Evet|Hayır|
<sup>1</sup> Windows 8.1 çalıştıran cihazlar için ek bilgiler

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](http://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft hesabı olmalıdır.

-   Şifrelemenin çalışması için cihazın, Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## Kötü amaçlı yazılım ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Ağ güvenlik duvarı iste**|Windows Güvenlik Duvarı’nın açık olmasını gerektirir.|Evet|Hayır|
|**SmartScreen’i etkinleştir**|Windows SmartScreen'in kullanılmasını gerektirir.|Evet|Hayır|

## Sistem ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Otomatik güncelleştirmeleri zorunlu kıl**|Cihazlarda otomatik güncelleştirmeler ayarını açar.|Evet|Hayır|
|**Otomatik güncelleştirmeleri zorunlu kıl - Otomatik olarak yüklenecek güncelleştirmelerin minimum sınıflandırması**|Otomatik olarak yüklenecek güncelleştirmelerin sınıflandırmasını seçer:<br /><br />-   **Önemli** – Önemli olarak sınıflandırılan tüm güncelleştirmeleri yükler.<br />-   **Önerilen** – Önemli veya önerilen olarak sınıflandırılan tüm güncelleştirmeleri yükler.|Evet|Hayır|
|**Kullanıcı Hesap Denetimi**|Cihazlarda Kullanıcı Hesap Denetimi’nin (UAC) kullanılmasını zorunlu tutar.|Evet|Hayır|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Microsoft’a tanılama bilgileri göndermesini etkinleştirir.|Evet|Hayır|


## Bulut ayarları – belgeler ve veriler

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**İş Klasörleri URL**|Belgelerin cihazlar arasında eşitlenmesine izin vermek için iş klasörünün URL’sini ayarlar.|Evet|Hayır|

## E-posta ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Microsoft hesabını Windows Mail uygulamasında isteğe bağlı hale getir**|Microsoft hesabı olmadan Windows Mail uygulamasına erişimi etkinleştirir.|Evet|Hayır|

## Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Otomatik doldurmaya izin ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.|Evet|Hayır|
|**Açılır pencere engelleyicisine izin ver**|Açılır pencere engelleyicisini etkinleştirir veya devre dışı bırakır.|Evet|Hayır|
|**Eklentilere izin ver**|Kullanıcıların Internet Explorer’a eklenti ekleyebilmesine olanak tanır.|Evet|Hayır|
|**Etkin betik yazmaya izin ver**|Tarayıcının Active X betikleri gibi betikleri çalıştırmasına olanak tanır.|Evet|Hayır|
|**Sahtekarlık uyarısına izin ver**|Olası sahte web siteleriyle ilgili uyarıları etkinleştirir veya devre dışı bırakır.|Evet|Hayır|
|**Tek sözcüklük girişler için intranet sitesine izin ver**|Internet Explorer’ı Bing gibi bir web sitesine yönlendirmek için tek sözcük kullanımına olanak tanır.|Evet|Hayır|
|**Intranet ağının otomatik algılanmasına izin ver**|Internet Explorer'da intranet sitelerinin güvenliği yapılandırmaya yardımcı olur.|Evet|Hayır|
|**İnternet için güvenlik düzeyi**|Internet Explorer'da İnternet sitelerinin güvenlik düzeyini ayarlar.|Evet|Hayır|
|**Intranet için güvenlik düzeyi**|Internet Explorer'da intranet sitelerinin güvenlik düzeyini ayarlar.|Evet|Hayır|
|**Güvenilir siteler için güvenlik düzeyi**|Güvenilir siteler bölgesi için güvenlik düzeyini yapılandırır.|Evet|Hayır|
|**Yasal siteler için güvenlik düzeyi**|Yasak siteler bölgesi için güvenlik düzeyini yapılandırır.|Evet|Hayır|
|**Do Not Track üst bilgisi gönder**|Internet Explorer’da ziyaret edilen sitelere Do Not Track üst bilgisi gönderir.|Evet|Hayır|
|**Kuruluş Modu menüsüne erişime izin ver**|Kullanıcıların Internet Explorer’dan Kuruluş Modu menü seçeneklerine erişmesine olanak tanır.<br>Bu ayarı seçerseniz, kullanıcıların Kuruluş Modu erişimine açtıkları web sitelerinin gösterildiği bir raporun URL’sini içeren **Günlük raporunun konumunu** belirtebilirsiniz.|Evet|Hayır|
|**Kurumsal Mod site listesi konumu**|Etkin olduğunda Kuruluş Modu’nu kullanacak web sitelerinin listesinin bulunduğu konumu belirtir.|Evet|Hayır|

## Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımını etkinleştirir.|Evet|Hayır|



### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


