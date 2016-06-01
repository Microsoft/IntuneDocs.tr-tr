---
# required metadata

title: Microsoft Intune’da Windows ilke ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Windows ilke ayarları
Kayıtlı Windows 8 ve Windows 8.1 cihazlarının ayarlarını yapılandırmak için Microsoft Intune **Windows genel yapılandırma ilkesini** kullanın:

## Güvenlik ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|Evet|Evet|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Küçük harfler, büyük harfler, rakamlar ve semboller şeklinde dört karakter kümesi vardır. Bu ayar parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir. Öte yandan iOS cihazları için bu ayar, parolanın içermesi gereken sembol karakterlerinin sayısını belirtir.|Evet|Evet|
|**Minimum parola uzunluğu**<sup>1</sup>|Cihazlarda parola için gereken minimum uzunluğu (karakter cinsinden) yapılandırır.|Evet|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu sayıda oturum açma girişimi başarısız olursa cihaz silinir.|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Kilidini açmak için parola gerekmeden önce cihazın ne kadar süreyle boşta kalacağını seçin.| Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Parolanın değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Kullanıcının önceden kullanılmış parolaları yapılandırıp yapılandıramayacağını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.|Evet|Evet|
|**Resimli parolaya veya PIN’e izin ver**|Cihazda resimli parola veya PIN kullanımına izin verir. Resimli parola, resimdeki hareketlerle oturum açmasına olanak tanır. PIN, kullanıcıların 4 basamaklı bir kod kullanarak hızla oturum açmalarına olanak tanır.|Evet|Evet|
<sup>1</sup> Windows RT çalıştıran cihazlara bir parola uzunluğu ilkesi dağıtmayı ayarladığınızda, kullanıcılar geçerli parolaları ilke gereksinimlerine uysa bile parolalarını sıfırlamaya zorlanır.

## Şifreleme ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Mobil cihazda şifreleme iste**<sup>1</sup>|Cihazdaki dosyaların şifrelenmesini gerektirir.<br>Windows Phone 8 cihazları için bunu **Evet** olarak ayarlamanız gerekir..|Evet|Hayır|
<sup>1</sup> Windows 8.1 çalıştıran cihazlar için ek bilgiler

-   Windows 8.1 çalıştıran cihazlarda şifrelemeyi zorlamak için her bir cihaza [Windows için Aralık 2014 MDM istemci güncelleştirmesi](http://support.microsoft.com/kb/3013816) ’ni yüklemeniz gerekir.

-   Windows 8.1 cihazları için bu ayarı etkinleştirirseniz, cihazın tüm kullanıcılarının bir Microsoft Hesabının olması gerekir.

-   Şifrelemenin çalışması için cihazın, Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) donanım sertifika gereksinimlerini karşılaması gerekir.

-   Bir cihazda şifrelemeyi zorunlu tuttuğunuzda kurtarma anahtarına yalnızca kullanıcıların OneDrive hesabından eriştikleri Microsoft Hesabından erişilebilir. Bu anahtarı bir kullanıcı adına kurtaramazsınız.

## Kötü amaçlı yazılım ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Ağ güvenlik duvarı iste**|Windows Güvenlik Duvarı’nın açık olmasını gerektirir.|Evet|Hayır|
|**SmartScreen’i etkinleştir**|Cihazlarda Windows Smartscreen'in kullanılmasını gerektirir.|Evet|Hayır|

## Sistem ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Otomatik güncelleştirmeleri zorunlu kıl**|Cihazlarda otomatik güncelleştirmeler ayarını açın.|Evet|Hayır|
|**Otomatik güncelleştirmeleri zorunlu kıl - Otomatik olarak yüklenecek güncelleştirmelerin minimum sınıflandırması**|Otomatik olarak yüklenecek güncelleştirmelerin sınıflandırmasını seçin:<br /><br />-   **Önemli** – Önemli olarak sınıflandırılan tüm güncelleştirmeleri yükler.<br />-   **Önerilen** – Önemli veya önerilen olarak sınıflandırılan tüm güncelleştirmeleri yükler.|Evet|Hayır|
|**Kullanıcı Hesap Denetimi**|Cihazlarda Kullanıcı Hesap Denetimi’nin (UAC) kullanılmasını zorunlu tutun.|Evet|Hayır|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Microsoft’a tanılama bilgileri göndermesine izin verin.|Evet|Hayır|


## Bulut ayarları – belgeler ve veriler

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**İş Klasörleri URL**|Belgelerin cihazlar arasında eşitlenmesine izin vermek için iş klasörünün URL’sini ayarlar.|Evet|Hayır|

## E-posta ayarları

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Microsoft hesabını Windows Mail uygulamasında isteğe bağlı hale getir**|Microsoft hesabı olmadan Windows Mail uygulamasına erişime izin verir.|Evet|Hayır|

## Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Otomatik doldurmaya izin ver**|Kullanıcı tarayıcıdaki otomatik tamamlama ayarlarını değiştirebilir.|Evet|Hayır|
|**Açılır pencere engelleyicisine izin ver**|Açılır pencere engelleyicisini etkinleştirir veya devre dışı bırakır.|Evet|Hayır|
|**Eklentilere izin ver**|Kullanıcı Internet Explorer’a eklenti ekleyebilir.|Evet|Hayır|
|**Etkin betik yazmaya izin ver**|Tarayıcı Active X betikleri gibi betikleri çalıştırabilir.|Evet|Hayır|
|**Sahtekarlık uyarısına izin ver**|Olası sahte web siteleri için uyarıları etkinleştirir veya devre dışı bırakır.|Evet|Hayır|
|**Tek sözcüklük girişler için intranet sitesine izin ver**|Internet Explorer’ı Bing gibi bir web sitesine yönlendirmek için tek sözcük kullanımına izin verir.|Evet|Hayır|
|**Intranet ağının otomatik algılanmasına izin ver**|Internet Explorer'da intranet sitelerinin güvenliği yapılandırmaya yardımcı olur.|Evet|Hayır|
|**İnternet için güvenlik düzeyi**|Internet Explorer'da İnternet sitelerinin güvenlik düzeyini ayarlayın.|Evet|Hayır|
|**Intranet için güvenlik düzeyi**|Internet Explorer'da intranet sitelerinin güvenlik düzeyini ayarlayın.|Evet|Hayır|
|**Güvenilir siteler için güvenlik düzeyi**|Güvenilir siteler bölgesi için güvenlik düzeyini yapılandırın.|Evet|Hayır|
|**Yasal siteler için güvenlik düzeyi**|Engellenen siteler bölgesi için güvenlik düzeyini yapılandırın.|Evet|Hayır|
|**Do Not Track üst bilgisi gönder**|Internet Explorer’da, ziyaret edilen sitelere Do Not Track üst bilgisi gönderin.|Evet|Hayır|
|**Kuruluş Modu menüsüne erişime izin ver**|Kullanıcıların Internet Explorer’dan Kuruluş Modu menü seçeneklerine erişmesine olanak tanır.<br>Seçilirse, kullanıcıların Kuruluş Modu erişimine açtıkları web sitelerinin gösterildiği bir raporun URL’sini içeren **Günlük raporunun konumunu** belirtebilirsiniz.|Evet|Hayır|
|**Kurumsal Mod site listesi konumu**|Etkin olduğunda Kuruluş Modu’nu kullanacak web sitelerinin listesinin bulunduğu konumu belirtin.|Evet|Hayır|

## Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Ayrıntılar|Windows 8.1 ve Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verin.|Evet|Hayır|



### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


