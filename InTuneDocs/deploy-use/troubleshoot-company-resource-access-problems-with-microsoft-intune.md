---
title: "Şirket kaynak erişimi sorunlarını giderme | Microsoft Docs"
description: "Bu konu başlığı altındaki hata ve durum kodları, kaynak erişimi sorunlarını gidermenize yardımcı olur."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40622ced-6029-4abf-873e-b51d2b51934c
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: dd1ada2bf6505552e7dbf8b185c929fa4e40104c


---

# <a name="troubleshoot-company-resource-access-problems-with-microsoft-intune"></a>Microsoft Intune ile şirket kaynak erişimi sorunlarını giderme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune eylemi bir hata kodu döndürdüğünde sorunları gidermenize yardımcı olması için bu konu başlığı altında verilen hata ve durum kodlarını kullanın.

Bu bilgiler sorununuzu çözmezse, yardım almanın diğer yollarını öğrenmek için bkz. [Microsoft Intune için destek alma](../troubleshoot/how-to-get-support-for-microsoft-intune.md).

## <a name="status-codes-for-mdm-managed-windows-devices"></a>MDM ile yönetilen Windows cihazları için durum kodları

|Durum kodu|Hata iletisi|Yapılması gereken|
|---------------|-----------------|--------------|
|10 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Yükleme devam ediyor||
|20 (APP_CI_ENFORCEMENT_IN_PROGRESS_WAITING_CONTENT)|İçerik bekleniyor||
|30 (APP_CI_ENFORCEMENT_ERROR_RETRIEVING_CONTENT)|İçerik alınıyor|Olası Neden: İş durumu 30, bir uygulamanın kullanıcı tarafından indirmesinin başarısız olduğunu belirtir.<br /><br />Bunun olası nedenleri şunlar olabilir:<br /><br />İndirme devam ederken cihazın İnternet bağlantısı kesilmiştir.<br /><br />Kayıt sırasındaki cihaza verilen sertifikanın süresi sona ermiştir.<br /><br />Sorun Giderme:<br /><br />Cihaz sertifikası süresinin dolmadığını onaylamak için cihazda Denetim Masası’ndan Şirket Uygulamaları uygulamasını başlatın; süresi dolmuşsa cihazı yeniden kaydetmeniz gerekir.<br /><br />Cihazın İnternet’e bağlı olduğunu onaylayın ve uygulamayı yeniden istemeyi deneyin.|
|40 (APP_CI_ENFORCEMENT_IN_PROGRESS_CONTENT_DOWNLOADED)|İçerik indirme tamamlandı||
|50 (APP_CI_ENFORCEMENT_IN_PROGRESS_INSTALLING)|Yükleme devam ediyor||
|60 (APP_CI_ENFORCEMENT_ERROR_INSTALLING)|Yükleme Hatası oluştu|Uygulama yüklemesi, indirmeden sonra başarısız oldu.<br /><br />Uygulamanın imzalandığı kod imzalama sertifikası cihazda yok.<br /><br />Uygulamanın bağlı olduğu bir çerçeve bağımlılığı, cihazda yüklü olarak bulunmadı.<br /><br /><br />İş çerçevesi bağımlılığının eksik olması nedeniyle yükleme hatası olması durumunda yöneticinin uygulama paketiyle birlikte iş çerçevesini paketleyerek uygulamayı yeniden yayımlaması gerekir.<br /><br />İndirilen uygulama paketi geçerli bir paket değildir, bozulmuş olabilir veya cihazdaki işletim sistemi sürümüyle uyumlu olmayabilir.|
|70 (APP_CI_ENFORCEMENT_SUCCEEDED)|Yükleme Başarısı||
|80 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Kaldırma devam ediyor||
|90 (APP_CI_ENFORCEMENT_ERROR)|Kaldırma Hatası oluştu||
|100 (APP_CI_ENFORCEMENT_SUCCEEDED)|Kaldırma Başarılı||
|110 (APP_CI_ENFORCEMENT_ERROR)|İçerik karması uyuşmazlığı||
|120 (APP_CI_ENFORCEMENT_ERROR)|SLK / yan yükleme etkin değil||
|130 (APP_CI_ENFORCEMENT_ERROR)|MSADP lisans yüklemesi başarısız oldu||
|Durum yok (APP_CI_ENFORCEMENT_UNKNOWN)|yok|Şu anda durum bilinmiyor.|

## <a name="company-resource-access-common-errors"></a>Şirket kaynağına erişim (genel hatalar)

|Durum kodu|Onaltılık hata kodu|Hata iletisi|
|---------------|--------------------------|-----------------|
|-2016281101|0x87D1FDF3|MDM CRP isteği bulunamadı|
|-2016281102|0x87D1FDF2|NDES URL'si bulunamadı|
|-2016281103|0x87D1FDF1|MDM CRP sertifika bilgisi bulunamadı|
|-2016281104|0x87D1FDF0|MDM CI sertifika bilgisi bulunamadı|
|-2016281105|0x87D1FDEF|Kural değerlendirilemedi|
|-2016281106|0x87D1FDEE|Çakışma çözümlemesinde kaybedildiğinden uygulanamaz|
|-2016281107|0x87D1FDED|Desteklenmeyen ayar bulma kaynağı|
|-2016281108|0x87D1FDEC|Başvurulan ayar, CI'da bulunamadı|
|-2016281109|0x87D1FDEB|Veri türü dönüştürmesi başarısız oldu|
|-2016281110|0x87D1FDEA|CIM ayarı için geçersiz parametre|
|-2016281111|0x87D1FDE9|Bu cihaz için uygulanamaz|
|-2016281112|0x87D1FDE8|Düzeltme işlemi başarısız oldu|
|-2016330905|0x87D13B67|Uygulama durumu bilinmiyor|
|-2016330906|0x87D13B66|Uygulama yönetiliyor, ancak kullanıcı tarafından kaldırıldı|
|-2016330907|0x87D13B65|Cihaz, kullanım kodunu kullanıyor|
|-2016330908|0x87D13B64|Uygulama yüklemesi başarısız oldu|
|-2016330909|0x87D13B63|Kullanıcı, uygulamayı güncelleştirme teklifini reddetti|
|-2016330910|0x87D13B62|Kullanıcı, uygulamayı yükleme teklifini reddetti|
|-2016330911|0x87D13B61|Kullanıcı, yönetilen uygulama yüklemesi gerçekleşmeden önce uygulamayı yükledi|
|-2016330912|0x87D13B60|Uygulama yüklenmek üzere zamanlandı, ancak işlemi tamamlamak için bir kullanım kodu gerekiyor|
|-2016341109|0x87D1138B|iOS cihazı bir hata döndürdü|
|-2016341110|0x87D1138A|iOS cihazı yanlış biçim nedeniyle komutu reddetti|
|-2016341111|0x87D11389|iOS cihazı, beklenmeyen bir Boşta durumu döndürdü|
|-2016341112|0x87D11388|iOS cihazı şu anda meşgul|

## <a name="errors-returned-by-ios-devices"></a>iOS cihazları tarafından döndürülen hatalar

|Durum kodu|Onaltılık hata kodu|Hata iletisi|
|---------------|--------------------------|-----------------|
|-2016299111|0x87D1B799|İç hata|
|-2016299112|0x87D1B798|İç hata|
|-2016300111|0x87D1B3B1|36001:(iç hata)|
|-2016300112|0x87D1B3B0|36000:Hücresel şebeke zaten yapılandırılmış|
|-2016301110|0x87D1AFCA|35002:Tek bir yükte birden çok yazı tipi|
|-2016301111|0x87D1AFC9|35001:Yazı tipi yüklemesi başarısız oldu|
|-2016301112|0x87D1AFC8|35000:Geçersiz yazı tipi verileri|
|-2016302109|0x87D1ABE3|34003:Kerberos asıl adı geçersiz|
|-2016302110|0x87D1ABE2|34002:Kerberos asıl adı eksik|
|-2016302111|0x87D1ABE1|34001:Geçersiz URL eşleşme deseni|
|-2016302112|0x87D1ABE0|34000:Geçersiz uygulama tanımlayıcısı eşleşme deseni|
|-2016304112|0x87D1A410|32000:Çok sayıda uygulama|
|-2016305111|0x87D1A029|31001:Ayarlar uygulanamıyor|
|-2016305112|0x87D1A028|31000:Kimlik bilgileri uygulanamıyor|
|-2016306111|0x87D19C41|30001:Zaman aşımına uğradı|
|-2016306112|0x87D19C40|30000:Kimlik doğrulaması başarısız oldu|
|-2016307109|0x87D1985B|29003:Bozuk sertifika verisi|
|-2016307110|0x87D1985A|29002:|
|-2016307111|0x87D19859|29001:|
|-2016307112|0x87D19858|29000:Cihaz denetlenmiyor|
|-2016308110|0x87D19472|28002:Duvar kağıdı ayarlanamıyor|
|-2016308111|0x87D19471|28001:Bozuk duvar kağıdı resmi|
|-2016308112|0x87D19470|28000:Bilinmeyen öğe|
|-2016310111|0x87D18CA1|26001:Dosya düzeyinde şifreleme desteklenmiyor|
|-2016310112|0x87D18CA0|26000:Blok düzeyinde şifreleme desteklenmiyor|
|-2016311110|0x87D188BA|25002:Kaldırılamıyor.|
|-2016311111|0x87D188B9|25001:Yüklenemiyor|
|-2016311112|0x87D188B8|25000:Bozuk profil|
|-2016312109|0x87D184D3|24003:Bozuk final profili|
|-2016312110|0x87D184D2|24002:Bozuk kimlik yükü|
|-2016312111|0x87D184D1|24001:Öznitelik sözlüğü imzalanamıyor|
|-2016312112|0x87D184D0|24000:Öznitelik sözlüğü oluşturulamıyor|
|-2016313110|0x87D180EA|23002:Geçersiz sunucu sertifikası|
|-2016313111|0x87D180E9|23001:Bozuk sunucu yanıtı|
|-2016313112|0x87D180E8|23000:Bozuk kimlik|
|-2016314099|0x87D17D0D|22013:Geçersiz PKI İşlemi yanıtı|
|-2016314100|0x87D17D0C|22012:CA Sertifikası depolanamıyor|
|-2016314101|0x87D17D0B|22011:CSR oluşturulamıyor|
|-2016314102|0x87D17D0A|22010:Geçici kimlik depolanamıyor|
|-2016314103|0x87D17D09|22009:Geçici kimlik oluşturulamıyor|
|-2016314104|0x87D17D08|22008:Kimlik oluşturulamıyor|
|-2016314105|0x87D17D07|22007:Geçersiz imzalı sertifika|
|-2016314106|0x87D17D06|22006:Yetersiz CACaps|
|-2016314107|0x87D17D05|22005:Ağ hatası|
|-2016314108|0x87D17D04|22004:Desteklenmeyen sertifika yapılandırması|
|-2016314109|0x87D17D03|22003:Geçersiz RAResponse|
|-2016314110|0x87D17D02|22002:Geçersiz CAResponse|
|-2016314111|0x87D17D01|22001:Anahtar çifti oluşturulamıyor|
|-2016314112|0x87D17D00|22000:Geçersiz anahtar kullanımı|
|-2016315105|0x87D1791F|21007:Hesap doğrulanamıyor|
|-2016315106|0x87D1791E|21006:Sertifika şifresi çözülemiyor|
|-2016315107|0x87D1791D|21005: Hesap benzersiz değil (E-posta Profili cihazda zaten var)|
|-2016315108|0x87D1791C|21004:Hesap oluşturulamıyor|
|-2016315109|0x87D1791B|21003:Ana bilgisayar adı yok|
|-2016315110|0x87D1791A|21002:Sunucudaki şifreleme ilkesine uymuyor|
|-2016315111|0x87D17919|21001:Sunucudaki ilkeye uymuyor|
|-2016315112|0x87D17918|21000:Sunucudan ilke alınamıyor|
|-2016316110|0x87D17532|20002:Hesap benzersiz değil|
|-2016316111|0x87D17531|20001:Ana bilgisayar adı yok|
|-2016316112|0x87D17530|20000:Hesap oluşturulamıyor|
|-2016317110|0x87D1714A|19002:Hesap benzersiz değil|
|-2016317111|0x87D17149|19001:Ana bilgisayar adı yok|
|-2016317112|0x87D17148|19000:Hesap oluşturulamıyor|
|-2016318110|0x87D16D62|18002:Geçersiz kimlik bilgileri|
|-2016318111|0x87D16D61|18001:Ana bilgisayara ulaşılamıyor|
|-2016318112|0x87D16D60|18000:Bilinmeyen hata|
|-2016319110|0x87D1697A|17002:Hesap benzersiz değil|
|-2016319111|0x87D16979|17001:Ana bilgisayar adı yok|
|-2016319112|0x87D16978|17000:Hesap oluşturulamıyor|
|-2016320110|0x87D16592|16002:Hesap benzersiz değil|
|-2016320111|0x87D16591|16001:Ana bilgisayar adı yok|
|-2016320112|0x87D16590|16000:Abonelik oluşturulamıyor|
|-2016321109|0x87D161AB|15003:Geçersiz sertifika|
|-2016321110|0x87D161AA|15002:Ağ yapılandırması kilitlenemiyor|
|-2016321111|0x87D161A9|15001:VPN kaldırılamıyor|
|-2016321112|0x87D161A8|15000:VPN yüklenemiyor|
|-2016322110|0x87D15DC2|14002:Bulut yapılandırması zaten var|
|-2016322111|0x87D15DC1|14001:Cihaz kilitli|
|-2016322112|0x87D15DC0|14000:Geçersiz alan|
|-2016323107|0x87D159DD|13005:Proxy ayarlanamıyor|
|-2016323108|0x87D159DC|13004:EAP ayarlanamıyor|
|-2016323109|0x87D159DB|13003:WiFi yapılandırması oluşturulamıyor|
|-2016323110|0x87D159DA|13002:Parola gerekli|
|-2016323111|0x87D159D9|13001:Kullanıcı adı gerekli|
|-2016323112|0x87D159D8|13000:Yüklenemiyor|
|-2016324070|0x87D1561A|12042:Bilinmeyen yerel ayar kodu|
|-2016324071|0x87D15619|12041:Bilinmeyen dil kodu|
|-2016324072|0x87D15618|12040:iTunes store oturum açması gerekli|
|-2016324073|0x87D15617|12039:(kullanılmıyor)|
|-2016324074|0x87D15616|12038:Uygulama yönetilmiyor|
|-2016324075|0x87D15615|12037:Geçersiz kullanım kodu|
|-2016324076|0x87D15614|12036:Geçerli durumda uygulama kaldırılamıyor|
|-2016324077|0x87D15613|12035:Uygulama satın alınamıyor|
|-2016324078|0x87D15612|12034:URL, HTTPS değil|
|-2016324079|0x87D15611|12033:Geçersiz bildirim|
|-2016324080|0x87D15610|12032:Bildirimde çok fazla uygulama var|
|-2016324081|0x87D1560F|12031:Uygulama yüklemesi devre dışı|
|-2016324082|0x87D1560E|12030:Geçersiz URL|
|-2016324083|0x87D1560D|12029:Uygulama yönetilmiyor|
|-2016324084|0x87D1560C|12028:Kullanım için beklenmiyor|
|-2016324085|0x87D1560B|12027:Bir uygulama değil|
|-2016324086|0x87D1560A|12026:Uygulama zaten kuyruğa alınmış|
|-2016324087|0x87D15609|12025:Uygulama zaten yüklenmiş|
|-2016324088|0x87D15608|12024:Uygulama bildirimi doğrulanamadı|
|-2016324089|0x87D15607|12023:Uygulama kimliği doğrulanamadı|
|-2016324090|0x87D15606|12022:Geçersiz konu|
|-2016324091|0x87D15605|12021:Geçersiz istek türü|
|-2016324092|0x87D15604|12020:Sunucu tarafından yetkilendirilmemiş|
|-2016324093|0x87D15603|12019:Gizli emanet kopyalanamıyor|
|-2016324094|0x87D15602|12018:Emanet anahtar çantası verileri kopyalanamıyor|
|-2016324095|0x87D15601|12017:Emanet anahtar çantası oluşturulamıyor|
|-2016324096|0x87D15600|12016:Kimlik eksik|
|-2016324097|0x87D155FF|12015:İletim belirteci alınamıyor|
|-2016324098|0x87D155FE|12014:Sağlama profili yönetilmiyor|
|-2016324099|0x87D155FD|12013:Profil yönetilmiyor|
|-2016324100|0x87D155FC|12012:MDM değiştirme uyumsuzluğu|
|-2016324101|0x87D155FB|12011:Geçersiz MDM yapılandırması|
|-2016324102|0x87D155FA|12010:İç tutarsızlık hatası|
|-2016324103|0x87D155F9|12009:Geçersiz değiştirme profili|
|-2016324104|0x87D155F8|12008:Yanlış biçimli istek|
|-2016324105|0x87D155F7|12007:Yetkilendirilmemiş|
|-2016324106|0x87D155F6|12006:Yeniden yönlendirme reddedildi|
|-2016324107|0x87D155F5|12005:Sertifika bulunamıyor|
|-2016324108|0x87D155F4|12004:Geçersiz iletme sertifikası|
|-2016324109|0x87D155F3|12003:Geçersiz sınama yanıtı|
|-2016324110|0x87D155F2|12002:İade edilemiyor|
|-2016324111|0x87D155F1|12001:Birden çok MDM örneği|
|-2016324112|0x87D155F0|12000:Geçersiz erişim hakları|
|-2016325111|0x87D15209|11001:Özel APN zaten yüklü|
|-2016325112|0x87D15208|11000:VPN yüklenemiyor|
|-2016326111|0x87D14E21|10001:Geçersiz imzalayan|
|-2016326112|0x87D14E20|10000:Varsayılanlar yüklenemiyor|
|-2016327106|0x87D14A3E|9006:Sertifika kimlik değil|
|-2016327107|0x87D14A3D|9005:Sertifika hatalı oluşturulmuş|
|-2016327108|0x87D14A3C|9004:Kök sertifika depolanamıyor|
|-2016327109|0x87D14A3B|9003:WAPI verileri depolanamıyor|
|-2016327110|0x87D14A3A|9002:Sertifika depolanamıyor|
|-2016327111|0x87D14A39|9001:Bir yükte çok fazla sertifika var|
|-2016327112|0x87D14A38|9000:Geçersiz parola|
|-2016328112|0x87D14650|8000:Web Klibi yüklenemiyor|
|-2016329105|0x87D1426F|7007:SMTP hesabı yanlış yapılandırılmış|
|-2016329106|0x87D1426E|7006:POP hesabı yanlış yapılandırılmış|
|-2016329107|0x87D1426D|7005:IMAP hesabı yanlış yapılandırılmış|
|-2016329108|0x87D1426C|7004:SMIME sertifikası bozuk|
|-2016329109|0x87D1426B|7003:SMIME sertifikası bulunamadı|
|-2016329110|0x87D1426A|7002:Doğrulama sırasında bilinmeyen hata oluştu|
|-2016329111|0x87D14269|7001:Geçersiz kimlik bilgileri|
|-2016329112|0x87D14268|7000:Ana bilgisayara ulaşılamıyor|
|-2016330110|0x87D13E82|6002:Sorgu oluşturulamıyor|
|-2016330111|0x87D13E81|6001:Boş dize|
|-2016330112|0x87D13E80|6000:Anahtar zinciri sistem hatası|
|-2016331097|0x87D13AA7|5015:Yetkisiz kullanım süresi ayarlanamıyor|
|-2016331098|0x87D13AA6|5014:Geçiş kodu ayarlanamıyor|
|-2016331099|0x87D13AA5|5013:Geçiş kodu temizlenemiyor|
|-2016331100|0x87D13AA4|5012:(kullanılmıyor)|
|-2016331101||5011:Yanlış geçiş kodu|
|-2016331102||5010:Cihaz kilitli|
|-2016331103|0x87D13AA4|5009:(kullanılmıyor)|
|-2016331104|0x87D13AA0|5008:Geçiş kodu çok yeni|
|-2016331105|0x87D13A9F|5007:Geçiş kodunun süresi doldu|
|-2016331106|0x87D13AA3|5006:Geçiş kodu için alfasayısal karakterler gerekiyor|
|-2016331107|0x87D13A9D|5005:Geçiş kodu için sayı gerekiyor|
|-2016331108|0x87D13A9C|5004:Geçiş kodu, artan azalan karakterler içeriyor|
|-2016331109|0x87D13A9B|5003:Geçiş kodu tekrar eden karakterler içeriyor|
|-2016331110|0x87D13A9A|5002:Karmaşık karakter sayısı çok az|
|-2016331111|0x87D13A99|5001:Benzersiz karakter sayısı çok az|
|-2016331112|0x87D13A98|5000:Geçiş kodu çok kısa|
|-2016332093|0x87D136C3|4019:Birden Çok Uygulama Kilidi yükü|
|-2016332094|0x87D136C2|4018:Birden çok APN veya Hücresel Şebeke yükü|
|-2016332095|0x87D136C1|4017:Birden çok genel HTTPProxy yükü|
|-2016332096|0x87D136C0|4016:(İç hata)|
|-2016332097|0x87D136BF|4015:Değiştirme profili bir MDM yükü içermiyor|
|-2016332098|0x87D136BE|4014:Kullanılabilir cihaz kimliği yok|
|-2016332099|0x87D136BD|4013:Güncelleştirme başarısız oldu|
|-2016332100|0x87D136BC|4012:Profil güncelleştirilemiyor|
|-2016332101|0x87D136BB|4011:Son profil bir yapılandırma profili değil|
|-2016332102|0x87D136BA|4010:Güncelleştirilen profil aynı tanımlayıcıya sahip değil|
|-2016332103|0x87D136B9|4009:Cihaz kilitli|
|-2016332104|0x87D136B8|4008:Uyuşmayan sertifikalar|
|-2016332105|0x87D136B7|4007:Tanınmayan dosya biçimi|
|-2016332106|0x87D136B6|4006:Profil kaldırma tarihi geçmişte|
|-2016332107|0x87D136B5|4005:Geçiş kodu uyumlu değil|
|-2016332108|0x87D136B4|4004:Kullanıcı yüklemeyi iptal etti|
|-2016332109|0x87D136B3|4003:Profil, yükleme için kuyruğa alınmamış|
|-2016332110|0x87D136B2|4002:Yinelenen UUID|
|-2016332111|0x87D136B1|4001:Yükleme hatası|
|-2016332112|0x87D136B0|4000:Profil ayrıştırılamıyor|
|-2016333111|0x87D132C9|3001:Tutarsız değer karşılaştırma algısı (iç hata)|
|-2016333112|0x87D132C8|3000:Tutarsız kısıtlama algısı (iç hata)|
|-2016334108|0x87D12EE4|2004:Desteklenmeyen alan değeri|
|-2016334109|0x87D12EE3|2003:Alanda bozuk veri türü|
|-2016334110|0x87D12EE2|2002:Zorunlu alan eksik|
|-2016334111|0x87D12EE1|2001:Desteklenmeyen yük sürümü|
|-2016334112|0x87D12EE0|2000:Yanlış Biçimli Yük|
|-2016335102|0x87D12B02|1010:Desteklenmeyen alan değeri|
|-2016335103|0x87D12B01|1009:Profil yükleme hatası|
|-2016335104|0x87D12B00|1008:Benzersiz olmayan yük tanımlayıcıları|
|-2016335105|0x87D12AFF|1007:Benzersiz olmayan UUID'ler|
|-2016335106|0x87D12AFE|1006:Şifresi çözülemiyor|
|-2016335107|0x87D12AFD|1005:Boş profil|
|-2016335108|0x87D12AFC|1004:Bozuk imza|
|-2016335109|0x87D12AFB|1003:Alanda bozuk veri türü|
|-2016335110|0x87D12AFA|1002:Zorunlu alan eksik|
|-2016335111|0x87D12AF9|1001:Desteklenmeyen profil sürümü|
|-2016335112|0x87D12AF8|1000:Yanlış biçimli profil|

## <a name="oma-response-codes"></a>OMA yanıt kodları

|Durum kodu|Onaltılık hata kodu|Hata iletisi|
|---------------|--------------------------|-----------------|
|-2016344008|0x87D10838|(1404): Sertifika erişimi reddedildi|
|-2016344009|0x87D10837|(1403): Sertifika bulunamadı|
|-2016344010|0x87D10836|DCMO(1402): İşlem başarısız oldu|
|-2016344011|0x87D10835|DCMO(1401): Kullanıcı, sorulduğunda işlemi reddetmeyi seçti|
|-2016344012|0x87D10834|DCMO(1400): İstemci hatası|
|-2016344108|0x87D107D4|DCMO(1204): Cihaz Yeteneği devre dışı bırakıldı, Kullanıcının yeniden etkinleştirmesine izin verildi|
|-2016344109|0x87D107D3|DCMO(1203): Cihaz Yeteneği devre dışı bırakıldı, Kullanıcının yeniden etkinleştirilmesine izin verilmiyor|
|-2016344110|0x87D107D2|DCMO(1202): Etkinleştirme işlemi başarıyla gerçekleştirildi, ancak Cihaz Yeteneği şu anda ayrılmış|
|-2016344111|0xF3FB4D95|DCMO(1201): Etkinleştirme işlemi başarıyla gerçekleştirildi ve Cihaz Yeteneği şu anda eklenmiş|
|-2016344112|0x87D107D0|DCMO(1200): İşlem başarıyla gerçekleştirildi|
|-2016345595|0x87D10205|Syncml(517): Atomik bir komuta verilen yanıt tek iletiye sığmayacak kadar büyük.|
|-2016345596|0x87D10204|Syncml(516): Komut, Atomik öğe içindeydi ve Atomik başarısız oldu. Bu komut başarıyla geri alınmadı.|
|-2016345598|0x87D10202|Syncml(514): İşlem, komut işlenmeden önce zaten iptal edilmiş olduğundan, SyncML komutu başarıyla tamamlanamadı.|
|-2016345599|0x87D10201|Syncml(513): Alıcı, istek SyncML İletisinde kullanılan SyncML Eşitleme Protokolü'nün belirtilen sürümünü desteklemiyor veya desteklemeyi reddediyor.|
|-2016345600|0x87D10200|Syncml (512): Eşitleme oturumu sırasında bir uygulama hatası oluştu.|
|-2016345601|0x87D101FF|Syncml(511): İstek işlenirken sunucuda ciddi bir hata oluştu.|
|-2016345602|0x87D101FE|Syncml(510): İstek işlenirken bir hata oluştu. Hata, alıcı veri deposundaki bir hatayla ilgilidir.|
|-2016345603|0x87D101FD|Syncml(509): Daha sonra kullanılmak üzere ayrılmış.|
|-2016345604|0x87D101FC|Syncml(508): İstemcinin sunucuyla geçerli eşitleme durumunun yenilenmesini gerektiren bir hata oluştu.|
|-2016345605|0x87D101FB|Syncml(507): Hata, bir Atomik öğe türü içindeki tüm SyncML komutlarının başarısız olmasına neden oldu.|
|-2016345606|0x87D101FA|Syncml(506): İstek işlenirken bir uygulama hatası oluştu.|
|-2016345607|0x87D101F9|Syncml(505): Alıcı, istek SyncML İletisinde kullanılan SyncML DTD'nin belirtilen sürümünü desteklemiyor veya desteklemeyi reddediyor.|
|-2016345608|=0x87D101F8|Syncml(504): Bir ağ geçidi veya proxy olarak görev yapan alıcı, URI (örneğin HTTP, FTP, LDAP) veya isteği tamamlamaya çalışırken erişmesi gereken başka bir ikincil alıcı (örneğin DNS) tarafından belirtilen yukarı akış alıcıdan zamanında yanıt almadı.|
|-2016345609|0x87D101F7|Syncml(503): Alıcı, alıcının geçici olarak aşırı yüklenmesi veya bakımda olması nedeniyle isteği şu anda işleyemiyor.|
|-2016345610|0x87D101F6|Syncml(502): Bir ağ geçidi veya proxy olarak görev yapan alıcı, isteği gerçekleştirmeye çalışırken eriştiği yukarı akış alıcısından geçersiz bir yanıt aldı.|
|-2016345611|0x87D101F5|Syncml(501): Alıcı, isteği gerçekleştirmek için gerekli olan komutu desteklemiyor.|
|-2016345612|0x87D101F4|Syncml(500): Alıcı, karşılaştığı beklenmedik durum nedeniyle isteği gerçekleştiremedi|
|-2016345684|0x87D101AC|Syncml(428): Taşıma başarısız oldu|
|-2016345685|0x87D101AB|Syncml(427): Üst öğe, alt öğeler içerdiğinden silinemiyor.|
|-2016345686|0x87D101AA|Syncml(426): Kısmi öğe kabul edilmedi.|
|-2016345687|0x87D101A9|Syncml(425): Gönderenin alıcı üzerinde yeterli erişim denetimi izinleri (ACL) olmadığından istenen komut başarısız oldu.|
|-2016345688|0x87D101A8|Syncml(424): Öbekli nesne alındı, ancak alınan nesnenin boyutu, ilk öbekte bildirilen boyutla eşleşmedi.|
|-2016345689|0x87D101A7|Syncml(423): "Geçici Olarak Silinmiş" öğe daha önce sunucuda "Kalıcı Olarak Silinmiş" olduğundan istenen komut başarısız oldu.|
|-2016345690|0x87D101A6|Syncml(422): LocURI'deki CGI betiği yanlış biçimde oluşturulduğundan istenen komut sunucuda başarısız oldu.|
|-2016345691|0x87D101A5|Syncml(421): Belirtilen arama dilbilgisi bilinmediğinden istenen komut sunucuda başarısız oldu.|
|-2016345692|0x87D101A4|Syncml(420): Alıcı, kalan eşitleme verileri için yeterli depolama alanına sahip değil.|
|-2016345693|0x87D101A3|Syncml(419): İstemci isteğinin oluşturduğu çakışma, sunucu komutunun üstün gelmesiyle çözümlendi.|
|-2016345694|0x87D101A2|Syncml(418): Hedef zaten var olduğundan istenen Koy veya Ekle komutu başarısız oldu.|
|-2016345695|0x87D101A1|Syncml(417): İstek şu anda başarısız oldu, isteği başlatanın isteği daha sonra tekrar denemesi gerekiyor.|
|-2016345696|0x87D101A0|Syncml(416): İstekte belirtilen bayt boyutu çok büyük olduğundan istek başarısız oldu.|
|-2016345697|0x87D1019F|Syncml(415): Desteklenmeyen medya türü veya biçimi.|
|-2016345698|0x87D1019E|Syncml(414): Hedef URI, alıcının işleyemeyeceği ya da işlemek istemediği kadar uzun olduğundan istenen komut başarısız oldu.|
|-2016345699|0x87D1019D|Syncml(413): İstenen öğe, alıcının işleyemeyeceği ya da işlemek istemediği kadar büyük olduğundan alıcı istenen komutu gerçekleştirmeyi reddediyor.|
|-2016345700|0x87D1019C|Syncml(412): İstenen komut eksik veya hatalı oluşturulmuş olduğundan alıcıda başarısız oldu.|
|-2016345701|0x87D1019B|Syncml(411): İstenen komutla beraber Meta öğesi türünde bayt boyutu veya uzunluk bilgileri eklenmelidir.|
|-2016345702|0x87D1019A|Syncml(410): İstenen hedef artık alıcıda mevcut değil ve iletme URI'sı bilinmiyor.|
|-2016345703|0x87D10199|Syncml(409): Veriye ait istemci ve sunucu sürümleri arasındaki bir güncelleme çakışması nedeniyle istenen başarısız oldu.|
|-2016345704|0x87D10198|Syncml(408): Beklenen bir ileti gereken süre içinde alınmadı.|
|-2016345705|0x87D10197|Syncml(407): İstek sahibinin doğru kimlik bilgileri sağlaması gerektiğinden istenen komut başarısız oldu.|
|-2016345706|0x87D10196|Syncml(406): İstekte yer alan isteğe bağlı özellik desteklenmediğinden istenen komut başarısız oldu.|
|-2016345707|0x87D10195|Syncml(405): İstenen komuta hedefte izin verilmiyor.|
|-2016345708|0x87D10194|Syncml(404): İstenen hedef bulunamadı.|
|-2016345709|0x87D10193|Syncml(403): İstenen komut başarısız oldu, ancak alıcı istenen komutu anladı.|
|-2016345710|0x87D10192|Syncml(402): Doğru ödeme gerektiğinden istenen komut başarısız oldu.|
|-2016345711|0x87D10191|Syncml(401): İstek sahibinin doğru kimlik bilgilerini sağlaması gerektiğinden istenen komut başarısız oldu.|
|-2016345712|0x87D10190|Syncml(400): Komuttaki yanlış oluşturulmuş söz dizimi nedeniyle istenen komut gerçekleştirilemedi.|
|-2016345807|0x87D10131|Syncml(305): İstenen hedefe, belirtilen proxy URI'sı ile erişilmesi gerekiyor.|
|-2016345808|0x87D10130|Syncml(304):İstenen SyncML komutu, hedefte yürütülmedi.|
|-2016345809|0x87D1012F|Syncml(303): İstenen hedef başka bir URI'da bulunabilir.|
|-2016345810|0x87D1012E|Syncml(302): İstenen hedef, geçici olarak başka bir URI'ya taşındı.|
|-2016345811|0x87D1012D|Syncml(301): İstenen hedef, yeni bir URI'ya sahip.|
|-2016345812|0x87D1012C|Syncml(300): İstenen hedef, istenen birden çok alternatif istenen hedeften biri.|
|-2016345896|0x87D100D8|Syncml(216): Komut, Atomik öğenin içindeydi ve Atomik başarısız oldu. Bu komut başarıyla geri alındı.|
|-2016345897|0x87D100D7|Syncml(215): Kullanıcı etkileşimi ve kullanıcının seçimi kabul etmemeyi seçmesi nedeniyle bir komut yürütülmedi.|
|-2016345898|0x87D100D6|Syncml(214): İşlem iptal edildi. SyncML komutu başarıyla tamamlandı, ancak oturum içinde başka komut işlenmeyecek.|
|-2016345899|0x87D100D5|Syncml(213): Öbeklenmiş öğe kabul edildi ve arabelleğe alındı.|
|-2016345900|0x87D100D4|Syncml(212): Kimlik doğrulaması kabul edildi. Eşitleme oturumunun kalanı için başka bir kimlik doğrulaması gerekmiyor. Bu yanıt kodu yalnızca kimlik bilgilerinin sağlandığı bir isteğe verilen yanıtta kullanılabilir.|
|-2016345901|0x87D100D3|Syncml(211): Öğe silinmedi. İstenen öğe bulunamadı. Daha önce silinmiş olabilir.|
|-2016345902|0x87D100D2|Syncml(210): Arşiv olmadan silme. Yanıt, istenen verilerin başarıyla silindiğini, ancak bu İSTEĞE BAĞLI özellik uygulama tarafından desteklenmediğinden silinmeden önce arşivlenmediğini belirtiyor.|
|-2016345903|0x87D100D1|Çakışma, yineleme ile çözümlendi. Yanıt, isteğin bir güncelleştirme çakışması oluşturduğunu gösteriyor; bu güncelleştirme çakışması, sunucu veritabanında oluşturulmakta olan istemci verilerinin çoğaltılmasıyla çözümlendi. Yanıt, Durum Öğesinde yinelemenin her iki hedef URI’sini içeriyor. Ayrıca iki yönlü bir eşitleme olması durumunda, yinelenen veri tanımıyla Ekle komutu döndürüldü.|
|-2016345904|0x87D100D0|Çakışma, istemci komutunun uygulanmasıyla çözümlendi. Yanıt, istemci komutunun  uygulanmasıyla çözümlenen bir güncelleştirme çakışması olduğunu belirtiyor.|
|-2016345905|0x87D100CF|Çakışma, birleştirme ile çözümlendi. Yanıt, isteğin, verilerin istemci ve sunucu örneklerinin birleştirilmesiyle çözümlenen bir çakışma oluşturduğunu belirtiyor. Yanıt, Durum Öğesinde hem Hedef hem de Kaynak URL’lerini içeriyor. Ayrıca Değiştir komutu, birleştirilmiş verilerle döndürülür.|
|-2016345906|0x87D100CE|Yanıt, komutun yalnızca bir parçasının tamamlandığını belirtiyor. Komutun geri kalanı daha sonra tamamlanabiliyorsa, tamamlandığında başka bir uygun tamamlama isteği durum kodu OLUŞTURULMALIDIR.|
|-2016345907|0x87D100CD|Kaynak, içeriğini GÜNCELLEŞTİRMELİDİR. Talebi gönderene, güncel sürümü edinmek için içeriğinin eşitlenmesi GEREKTİĞİ bildiriliyor.|
|-2016345908|0x87D100CC|İstek başarıyla tamamlandı ancak hiçbir veri döndürülmüyor. Yanıt kodu aynı zamanda, hedefte içerik olmadığında bir Get’e yanıt olarak da döndürülür.|
|-2016345909|0x87D100CB|Yetkili olmayan yanıt. Hedeflenenden farklı bir varlık isteğe yanıt veriyor. Yanıt yalnızca istek yetkili hedeften 200 yanıt kodu ile sonuçlanacaksa döndürülür.|
|-2016345910|0x87D100CA|İşleme için kabul edildi. Bir uygulamanın uzaktan yürütmesini çalıştırma veya kullanıcı ya da uygulamaya bildirme isteği başarıyla gerçekleştirildi.|
|-2016345911|0x87D100C9|İstenen öğe eklendi.|
|-2016345912|0x87D100C8|SyncML komutu başarıyla tamamlandı.|
|-2016346011|0x87D10065|Belirtilen SyncML komutu yürütülüyor, ancak henüz tamamlanmadı.|

### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](../troubleshoot/how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Dec16_HO2-->


