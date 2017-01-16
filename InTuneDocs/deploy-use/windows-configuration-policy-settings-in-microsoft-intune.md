---
title: "Windows ilke ayarları | Microsoft Docs"
description: "Kayıtlı Windows 8 ve Windows 8.1 cihazlarının ayarlarını yapılandırmak için Intune Windows genel yapılandırma ilkesini (Windows 8.1 ve üstü) kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 53ac1c31cf2a2054080e43716b30c50c73961759


---

# <a name="windows-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows ilke ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Kayıtlı Windows 8, ve Windows 8.1 ve Windows RT 8.1 cihazlarının aşağıdaki ayarlarını yapılandırmak için Microsoft Intune **Windows genel yapılandırma ilkesini (Windows 8.1 ve üstü)** kullanın:

## <a name="applicability-settings"></a>Uygulanabilirlik ayarları

|Ayar adı|Ayrıntılar|
|----------------|----------------------------------|
|**Tüm yapılandırmaları Windows 10'a uygula**|Bu ilkedeki ayarların Windows 8 ve Windows 8.1 cihazlarına ek olarak Windows 10 cihazlarına da uygulanmasını etkinleştirir.|

## <a name="security-settings"></a>Güvenlik ayarları

|Ayar adı|Ayrıntılar|
|----------------|------|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (alfasayısal veya yalnızca sayısal gibi).|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir. Dört karakter kümesi vardır: küçük harfler, büyük harfler, rakamlar ve simgeler. Bununla birlikte, iOS cihazları için bu ayar, parolanın içermesi gereken simgelerin sayısını belirtir.|
|**En düşük parola uzunluğu**|Parola için gereken minimum uzunluğu (karakter cinsinden) yapılandırır.|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Burada belirtilen sayıda oturum açma denemesi başarısız olursa, cihazı temizler.|
|**Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Kilidini açmak için parola gerekmeden önce cihazın ne kadar süreyle boşta kalacağını belirtir.|
|**Parola kullanım süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|
|**Parola geçmişini anımsa**|Kullanıcının önceden kullanılmış parolaları yapılandırıp yapılandıramayacağını belirtir.|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.|
|**Resimli parolaya veya PIN’e izin ver**|Resimli parola veya PIN kullanımını etkinleştirir. Resimli parola, kullanıcının resimdeki hareketlerle oturum açmasına olanak tanır. PIN, kullanıcıların dört basamaklı bir kodla hızla oturum açmalarına olanak tanır.|

## <a name="encryption-settings"></a>Şifreleme ayarları

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Mobil cihazda şifreleme iste**<sup>1</sup>|Cihazdaki dosyaların şifrelenmesini gerektirir.|
<sup>1</sup> Windows 8.1 çalıştıran cihazlar için ek bilgiler

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](http://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft hesabı olmalıdır.

-   Şifrelemenin çalışması için cihazın, Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## <a name="malware-settings"></a>Kötü amaçlı yazılım ayarları

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Ağ güvenlik duvarı iste**|Windows Güvenlik Duvarı’nın açık olmasını gerektirir.|
|**SmartScreen’i etkinleştir**|Windows SmartScreen'in kullanılmasını gerektirir.|

## <a name="system-settings"></a>Sistem ayarları

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Otomatik güncelleştirmeleri zorunlu kıl**|Cihazlarda otomatik güncelleştirmeler ayarını açar.|
|**Otomatik güncelleştirmeleri zorunlu kıl - Otomatik olarak yüklenecek güncelleştirmelerin en düşük sınıflandırması**|Otomatik olarak yüklenecek güncelleştirmelerin sınıflandırmasını seçer:<br /><br />-   **Önemli** – Önemli olarak sınıflandırılan tüm güncelleştirmeleri yükler.<br />-   **Önerilen** – Önemli veya önerilen olarak sınıflandırılan tüm güncelleştirmeleri yükler.|
|**Kullanıcı Hesap Denetimi**|Cihazlarda Kullanıcı Hesap Denetimi’nin (UAC) kullanılmasını zorunlu tutar.|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Microsoft’a tanılama bilgileri göndermesini etkinleştirir.|


## <a name="cloud-settings--documents-and-data"></a>Bulut ayarları – belgeler ve veriler

|Ayar adı|Ayrıntılar|
|----------------|------|
|**İş Klasörleri URL**|Belgelerin cihazlar arasında eşitlenmesine izin vermek için iş klasörünün URL’sini ayarlar.|

## <a name="email-settings"></a>E-posta ayarları

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Microsoft hesabını Windows Mail uygulamasında isteğe bağlı hale getir**|Microsoft hesabı olmadan Windows Mail uygulamasına erişimi etkinleştirir.|

## <a name="application-settings---browser"></a>Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Otomatik doldurmaya izin ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.|
|**Açılır pencere engelleyicisine izin ver**|Açılır pencere engelleyicisini etkinleştirir veya devre dışı bırakır.|
|**Eklentilere izin ver**|Kullanıcıların Internet Explorer’a eklenti ekleyebilmesine olanak tanır.|
|**Etkin betik yazmaya izin ver**|Tarayıcının Active X betikleri gibi betikleri çalıştırmasına olanak tanır.|
|**Sahtekarlık uyarısına izin ver**|Olası sahte web siteleriyle ilgili uyarıları etkinleştirir veya devre dışı bırakır.|
|**Tek sözcüklük girişler için intranet sitesine izin ver**|Internet Explorer’ı Bing gibi bir web sitesine yönlendirmek için tek sözcük kullanımına olanak tanır.|
|**İntranet ağının otomatik algılanmasına izin ver**|Internet Explorer'da intranet sitelerinin güvenliği yapılandırmaya yardımcı olur.|
|**İnternet için güvenlik düzeyi**|Internet Explorer'da İnternet sitelerinin güvenlik düzeyini ayarlar.|
|**İntranet için güvenlik düzeyi**|Internet Explorer'da intranet sitelerinin güvenlik düzeyini ayarlar.|
|**Güvenilir siteler için güvenlik düzeyi**|Güvenilir siteler bölgesi için güvenlik düzeyini yapılandırır.|
|**Yasal siteler için güvenlik düzeyi**|Yasak siteler bölgesi için güvenlik düzeyini yapılandırır.|
|**Do Not Track üst bilgisi gönder**|Internet Explorer’da ziyaret edilen sitelere Do Not Track üst bilgisi gönderir.|
|**Kuruluş Modu menüsü erişimine izin ver**|Kullanıcıların Internet Explorer’dan Kuruluş Modu menü seçeneklerine erişmesine olanak tanır.<br>Bu ayarı seçerseniz, kullanıcıların Kuruluş Modu erişimine açtıkları web sitelerinin gösterildiği bir raporun URL’sini içeren **Günlük raporunun konumunu** belirtebilirsiniz.|
|**Kurumsal Mod site listesi konumu**|Etkin olduğunda Kuruluş Modu’nu kullanacak web sitelerinin listesinin bulunduğu konumu belirtir.|

## <a name="device-capabilities-settings---cellular"></a>Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Ayrıntılar|
|----------------|----|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımını etkinleştirir.|



### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO2-->


