---
title: Uygulama koruma ilkelerini kullanan veri koruma çerçevesi
titleSuffix: Microsoft Intune
description: Uygulama koruma Ilkelerinin (uygulama), cihazın kayıtlı olup olmamasına bakılmaksızın bir kuruluşun verilerinin güvenli veya yönetilen bir uygulamada yer aldığından emin olun.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: smithre4
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 075f4bdd52bfa72e2eaed051c765d77d7b80e6fd
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856262"
---
# <a name="data-protection-framework-using-app-protection-policies"></a>Uygulama koruma ilkelerini kullanan veri koruma çerçevesi 

Daha fazla kuruluş, iş veya okul verilerine erişmek için mobil cihaz stratejileri uyguladıkça, veri sızıntılarına karşı koruma, Paramount hale gelir. Veri sızıntılarına karşı koruma için Intune 'un mobil uygulama yönetimi çözümü, uygulama koruma Ilkelerdir (uygulama). UYGULAMA, cihazın kayıtlı olup olmamasına bakılmaksızın bir kuruluşun verilerinin güvenli kalmasını veya yönetilen bir uygulamada yer aldığından emin olmanızı sağlayan kurallardır. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerine genel bakış](~/apps/app-protection-policy.md). 

Uygulama koruma Ilkeleri yapılandırılırken çeşitli ayar ve seçenek sayısı, kuruluşların korumayı belirli ihtiyaçlarına göre uyarlamalarını sağlar. Bu esneklik nedeniyle, bir bütün senaryoyu uygulamak için ilke ayarlarının kullanılması gerektiği açık olmayabilir. Kuruluşların, istemci uç noktası sağlamlaştırma endeavors ' i önceliklendirmesine yardımcı olmak için Microsoft, [Windows 10 ' da güvenlik yapılandırmalarına](https://aka.ms/secconframework)yönelik yeni bir taksonomi sunmuştur ve Intune, mobil uygulama YÖNETIMI için uygulama veri koruma çerçevesi için benzer bir taksonomiyi kullanıyordur  

UYGULAMA veri koruma yapılandırma çerçevesi üç ayrı yapılandırma senaryosunda düzenlenmiştir: 

- 1\. düzey kurumsal temel veri koruması – Microsoft bu yapılandırmayı bir kurumsal cihazın en düşük veri koruma yapılandırması olarak önerir. 

- 2\. düzey kurumsal gelişmiş veri koruma – Microsoft, kullanıcıların hassas veya gizli bilgilere erişebileceği cihazlar için bu yapılandırmayı önerir. Bu yapılandırma, iş veya okul verilerine erişen mobil kullanıcıların çoğu için geçerlidir. Bazı denetimler Kullanıcı deneyimini etkileyebilir. 

- Düzey 3 Kurumsal yüksek veri koruma – Microsoft bu yapılandırmayı daha büyük veya daha fazla gelişmiş güvenlik ekibine sahip bir kuruluş tarafından çalıştırılan veya benzersiz derecede yüksek riskli olan belirli kullanıcılar veya gruplar (tek bir örnek, bir kuruluş gibi) için önerir. hırsızlık, kendi stok fiyatlarını doğrudan ve ciddi bir şekilde etkileyen verileri işleyen kullanıcıları tanımladı. Bir kuruluş, iyi ifade edilen ve Gelişmiş reklam işlemleri tarafından hedeflenmek için bu yapılandırmaya amaçlayın olmalıdır. 

## <a name="app-data-protection-framework-deployment-methodology"></a>UYGULAMA veri koruma çerçevesi dağıtım yöntemi 

Yeni yazılımların, özelliklerin veya ayarların herhangi bir dağıtımında olduğu gibi, Microsoft, uygulama veri koruma çerçevesini dağıtmadan önce doğrulamayı test etmek için bir halka metodolojiye yatırım yapmanızı önerir. Dağıtım halkalarının tanımlanması genellikle tek seferlik bir olaydır (veya en az seyrek olabilir), ancak sıralamanın hala doğru olduğundan emin olmak için bu grupları yeniden ziyaret etmelidir. 

Microsoft, uygulama veri koruma çerçevesi için aşağıdaki dağıtım halkası yaklaşımını önerir: 

| Dağıtım halkası  | Kiracı  | Değerlendirme takımları  | Çıkış  | 'Ndeki  |
|--------------------|------------------------|-------------------------------------------------------------------|----------------------------------------------------------|----------------------------------------|
| Kalite güvencesi  | Ön üretim kiracısı  | Mobil yetenek sahipleri, güvenlik, risk değerlendirmesi, gizlilik, UX  | İşlevsel senaryo doğrulaması, taslak belgeler  | 0-30 gün  |
| Önizleme  | Üretim kiracısı  | Mobil yetenek sahipleri, UX  | Son Kullanıcı senaryosu doğrulaması, kullanıcıya yönelik belgeler  | 7-14 gün, kalite sonrası güvence  |
| Üretim  | Üretim kiracısı  | Mobil yetenek sahipleri, BT yardım masası  | Yok  | 7 gün-birkaç hafta, önizleme sonrası  |

Yukarıdaki tabloda gösterildiği gibi, ilke ayarlarının etkilerini anlamak için uygulama koruma Ilkelerine yapılan tüm değişikliklerin önce üretim öncesi bir ortamda gerçekleştirilmesi gerekir. Test tamamlandıktan sonra değişiklikler üretime taşınabilir ve üretim kullanıcılarının, genellikle BT departmanının ve diğer ilgili grupların bir alt kümesine uygulanabilir. Son olarak, dağıtım mobil kullanıcı topluluğunun geri kalanına tamamlanabilir. Üretime dağıtım, değişikliğe ilişkin etkinin ölçeğine bağlı olarak daha uzun sürebilir. Kullanıcı etkisi yoksa, değişiklik hızlı bir şekilde kullanıma sunulmalıdır, ancak değişiklik Kullanıcı etkisinden sonuçlanırsa, kullanıcıların, değişiklikleri Kullanıcı popülasyonu ile iletişimine gerek duyabileceği için, dağıtım daha yavaş ilerlemelidir. 

Bir UYGULAMADAKI değişiklikleri test ederken, [Teslimat zamanlamasıyla](~/apps/app-protection-policy-delivery.md)haberdar olun. Belirli bir kullanıcı için uygulama tesliminin durumu izlenebilir. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](~/apps/app-protection-policies-monitor.md). 

Her bir uygulama için ayrı uygulama ayarları, uç ve ilgili URL 'YI kullanarak cihazlarda doğrulanabilir *: ıntunehelp*. Daha fazla bilgi için bkz. [Microsoft Edge 'i Microsoft Intune kullanarak](~/apps/manage-microsoft-edge.md#use-microsoft-edge-on-ios-to-access-managed-app-logs) [istemci uygulama koruma günlüklerini gözden geçirme](~/apps/app-protection-policy-settings-log.md) ve Web erişimini yönetme. 

## <a name="app-data-protection-framework-settings"></a>UYGULAMA veri koruma çerçevesi ayarları 

Geçerli uygulamalar için aşağıdaki uygulama koruma Ilkesi ayarlarının etkinleştirilmesi ve tüm mobil kullanıcılara atanması gerekir. Her ilke ayarı hakkında daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](~/apps/app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkesi ayarları](~/apps/app-protection-policy-settings-android.md). 

Microsoft, kullanım senaryolarını gözden geçirmeyi ve kategorilere ayırmak ve daha sonra bu düzeyin yönetim kılavuzunu kullanarak kullanıcıları yapılandırmak için önerilir. Her çerçevede olduğu gibi, veri koruma, tehdit ortamını değerlendirmeli, risk uygulama ve kullanışlılık etkisi olması gerektiği için ilgili düzeyin içindeki ayarların kuruluşun ihtiyaçlarına göre ayarlanması gerekebilir.  

### <a name="apps-to-include-in-the-app-protection-policies"></a>Uygulama koruma Ilkelerine dahil edilecek uygulamalar  

Her uygulama koruma Ilkesi için aşağıdaki temel Microsoft uygulamaları eklenmelidir: 

- Kenarını 
- Excel 
- Ofis 
- OneDrive 
- OneNote 
- Outlook 
- PowerPoint 
- Microsoft Teams 
- Microsoft To-Do
- Word 
- Microsoft SharePoint 

İlkeler, iş ihtiyacını temel alan diğer Microsoft uygulamalarını, kuruluş içinde kullanılan Intune SDK 'sını tümleştirmiş olan diğer üçüncü taraf genel uygulamaları ve [ıNTUNE SDK](~/developer/app-sdk.md) ile tümleştirilmiş (veya sarmalanmış olan) iş kolu uygulamalarını içermelidir. 

### <a name="level-1-enterprise-basic-data-protection"></a>Düzey 1 Kurumsal temel veri koruma 

Düzey 1, bir kurumsal mobil cihaz için en düşük veri koruma yapılandırmadır. Bu yapılandırma, iş veya okul verilerine erişmek, iş veya okul hesabı verilerini şifrelemek ve okul veya iş verilerini seçmeli olarak silme yeteneği sağlamak için bir PIN 'ı isteyerek, temel Exchange Online cihaz erişim ilkeleri gereksinimini değiştirir. Ancak, Exchange Online cihaz erişim ilkelerinin aksine, aşağıdaki uygulama koruma Ilkesi ayarları ilkede seçilen tüm uygulamalar için geçerlidir. böylece, veri erişiminin mobil mesajlaşma senaryolarından daha fazla korunması sağlanır. 

Düzey 1 ' deki ilkeler, Microsoft Endpoint Manager 'da uygulama koruma Ilkesi oluştururken kullanıcılara etkisini en aza indirerek ve varsayılan veri koruma ve erişim gereksinimleri ayarlarını yansıtarak makul bir veri erişim düzeyini zorlar.  

#### <a name="data-protection"></a>Veri koruma 

| Ayar | Ayar açıklaması |             Değer  |             Platfveyam        |
|-----------------|--------------------------------------------------------|-----------------------|----------------------------------------|
| Veri Aktarımı |             Kuruluş verilerini buraya Yedekle...  |             İzin ver  |             iOS/ıpados, Android        |
| Veri Aktarımı |       Diğer uygulamalara kuruluş verileri gönderme  |             Tüm uygulamalar  |             iOS/ıpados, Android        |
| Veri Aktarımı |       Diğer uygulamalardan veri al  |             Tüm uygulamalar  |             iOS/ıpados, Android        |
| Veri Aktarımı |       Uygulamalar arasında kesme, kopyalama ve yapıştırmayı kısıtla  |             Herhangi bir uygulama  |             iOS/ıpados, Android        |
| Veri Aktarımı |       Üçüncü taraf klavyeler  |             İzin ver  |             iOS/iPadOS        |
| Veri Aktarımı |       Onaylanan klavyeler  |             Gerekli değildir  |             Android        |
| Veri Aktarımı |       Ekran yakalama ve Google Yardımcısı  |             İzin ver  |             Android        |
| Şifreleme |             Kuruluş verilerini şifreleme  |             Gerekli  |             iOS/ıpados, Android        |
| Şifreleme |       Kayıtlı cihazlarda kuruluş verilerini şifreleme  |             Gerekli  |             Android        |
| İşlevi  |             Uygulamayı yerel kişiler uygulamasıyla Eşitle  |             İzin ver  |             iOS/ıpados, Android        |
| İşlevi  |       Kuruluş verilerini yazdırma  |             İzin ver  |             iOS/ıpados, Android        |
| İşlevi  |       Diğer uygulamalarla Web içeriği aktarımını kısıtla  |             Herhangi bir uygulama  |             iOS/ıpados, Android        |
| İşlevi  |       Kuruluş verileri bildirimleri  |             İzin ver  |             iOS/ıpados, Android        |

#### <a name="access-requirements"></a>Erişim gereksinimleri 

| Ayar  | Değer  | Platfveyam  | Notlar  |
|----------------------------------------------------------------|---------------|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Erişim için SABITLE  | Gerekli  | iOS/ıpados, Android  |   |
| PIN türü  | Sayısal  | iOS/ıpados, Android  |   |
| Basit PIN  | İzin ver  | iOS/ıpados, Android  |   |
| Minimum PIN uzunluğunu seçin  | 4  | iOS/ıpados, Android  |   |
| Erişim için PIN yerine biyometrik  | İzin ver  | iOS/ıpados, Android  |   |
| Erişim için PIN yerine biyometrik öğesini geçersiz kıl  | Gerekli  | iOS/ıpados, Android  |   |
| Zaman aşımı (etkinlik dakikası)  | 720  | iOS/ıpados, Android  |   |
| Erişim için PIN yerine yüz KIMLIĞI  | İzin ver  | iOS/iPadOS  |   |
| Gün sayısından sonra PIN sıfırlama  | Hayır  | iOS/ıpados, Android  |   |
| Cihaz PIN 'ı ayarlandığında uygulama PIN 'ı  | Gerekli  | iOS/ıpados, Android  | Cihaz Intune 'A kaydedildiyse, Yöneticiler cihaz uyumluluk ilkesi aracılığıyla güçlü bir cihaz PIN 'ı zorlarsa bunu "gerekli değil" olarak ayarlamayı düşünebilirler.  |
| Erişim için iş veya okul hesabı kimlik bilgileri  | Gerekli değildir  | iOS/ıpados, Android  |   |
| Daha sonra erişim gereksinimlerini yeniden denetle (dakika dışı)  | 30  | iOS/ıpados, Android  |   |

#### <a name="conditional-launch"></a>Koşullu başlatma 

| Ayar | Ayar açıklaması |          Değer/eylem  |          Platfveyam        | Notlar |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Uygulama koşulları |       En fazla PIN denemesi  |          5/PIN 'ı Sıfırla  |          iOS/ıpados, Android  |                  |
| Uygulama koşulları |       Çevrimdışı yetkisiz kullanım süresi  |          720/erişimi engelle (dakika)  |          iOS/ıpados, Android  |                  |
| Uygulama koşulları |       Çevrimdışı yetkisiz kullanım süresi  |          90/silme verisi (gün)  |          iOS/ıpados, Android  |                  |
| Cihaz koşulları  |       Jailbreak uygulanmış/kökü belirtilmiş cihazlar  |        Yok/erişimi engelle  |          iOS/ıpados, Android  |                  |
| Cihaz koşulları  |       SafetyNet cihaz kanıtlama  |          Temel bütünlük ve sertifikalı cihazlar/erişimi engelle  |          Android  |          <p>Bu ayar, Son Kullanıcı cihazlarında Google 'ın SafetyNet kanıtlamasını yapılandırır. Temel bütünlük, cihazın bütünlüğünü doğrular. Köklü cihazlar, Öykünücüler, sanal cihazlar ve değişiklik işaretlerine sahip cihazlar temel bütünlüğü başarısız oluyor. </p><p> Temel bütünlük ve sertifikalı cihazlar, Google 'ın hizmetleriyle cihazın uyumluluğunu doğrular. Yalnızca Google tarafından sertifikalı değiştirilmemiş cihazlar bu denetimi geçirebilir.</p>  |
| Cihaz koşulları  |       Uygulamalarda tehdit taraması iste  |        Yok/erişimi engelle  |          Android  |          Bu ayar, Son Kullanıcı cihazlarında Google 'ın uygulama taramasını doğrulama özelliğinin açık olmasını sağlar. Yapılandırıldıysa, son kullanıcının Android cihazında Google 'ın uygulama taramasını açana kadar erişim engellenir.        |

#### <a name="level-2-enterprise-enhanced-data-protection"></a>Düzey 2 kurumsal gelişmiş veri koruma 

Düzey 2, kullanıcıların daha hassas bilgilere erişen cihazlarda bir standart olarak önerilen veri koruma yapılandırması ' dır. Bu cihazlar, günümüzde kuruluşlarda doğal bir hedeftir. Bu öneriler, büyük ölçüde yüksek düzeyde güvenlik uygulayıcıları olan büyük bir personeli varsaymaz ve bu nedenle kurumsal kuruluşların çoğu tarafından erişilebilmelidir. Bu yapılandırma, veri aktarımı senaryolarını kısıtlayarak ve en düşük işletim sistemi sürümü gerektirerek, düzey 1 ' deki yapılandırmanın üzerine genişletilir. 

Düzey 2 ' de zorlanan ilke ayarları, 1. düzey için önerilen tüm ilke ayarlarını içerir ve daha fazla denetim ve düzey 1 ' den daha karmaşık bir yapılandırma uygulamak için yalnızca aşağıdaki ilke ayarlarını ekler veya günceller. Bu ayarlar, kullanıcılar veya uygulamalar için biraz daha yüksek bir etkiye sahip olsa da, kullanıcıların mobil cihazlarda hassas bilgilere erişimi olan riskler konusunda daha fazla bilgi sahibi olan bir veri koruma düzeyi daha fazla yorum uygular. 

#### <a name="data-protection"></a>Veri koruma 

| Ayar | Ayar açıklaması |             Değer  |             Platfveyam        | Notlar |
|---------------|----------------------------------------------------------|-----------------------------------------------|---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Veri Aktarımı |       Kuruluş verilerini buraya Yedekle...  |          Engelle  |          iOS/ıpados, Android  |                  |
| Veri Aktarımı |       Diğer uygulamalara kuruluş verileri gönderme  |          İlke ile yönetilen uygulamalar  |          iOS/ıpados, Android  |          <p>İOS/ıpados ile, Yöneticiler bu değeri "Ilkeyle yönetilen uygulamalar", "işletim sistemi paylaşımı ile Ilke ile yönetilen uygulamalar" veya "açık/paylaşım filtresi ile Ilke ile yönetilen uygulamalar" olarak yapılandırabilir. </p><p>Cihaz Intune 'a kaydedildiğinde, işletim sistemi paylaşımıyla ilke ile yönetilen uygulamalar de kullanılabilir. Bu ayar, diğer ilkeyle yönetilen uygulamalara veri aktarımına ve Intune tarafından yönetilen diğer uygulamalara dosya aktarımlarını sağlar. </p><p>Açık/paylaşılan filtreleme ile ilke ile yönetilen uygulamalar, işletim sistemi açma/paylaşma iletişim kutularını yalnızca ilkeyle yönetilen uygulamaları görüntüleyecek şekilde filtreler. </p><p> Daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](~/apps/app-protection-policy-settings-ios.md).</p> |
| Veri Aktarımı |       Kuruluş verilerinin kopyalarını Kaydet  |          Engelle  |          iOS/ıpados, Android  |                  |
| Veri Aktarımı |       Kullanıcıların seçili hizmetlere kopya kaydetmesine izin ver  |          OneDrive Iş, SharePoint Online |          iOS/ıpados, Android  |                  |
| Veri Aktarımı |       Uygulamalar arasında kesme, kopyalama ve yapıştırmayı kısıtla  |          Yapıştırma seçeneğiyle ilke ile yönetilen uygulamalar  |          iOS/ıpados, Android  |                  |
| Veri Aktarımı |       Ekran yakalama ve Google Yardımcısı  |          Engelle  |          Android  |                  |
| İşlevi |       Diğer uygulamalarla Web içeriği aktarımını kısıtla  |          Microsoft Edge  |          iOS/ıpados, Android  |                  |
| İşlevi |       Kuruluş verileri bildirimleri  |          Kuruluş verilerini engelle  |          iOS/ıpados, Android  |          Bu ayarı destekleyen uygulamaların listesi için bkz. [iOS uygulama koruma ilkesi ayarları](~/apps/app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkesi ayarları](~/apps/app-protection-policy-settings-android.md).       |


#### <a name="conditional-launch"></a>Koşullu başlatma

| Ayar | Ayar açıklaması |          Değer/eylem  |          Platfveyam        | Notlar |
|--------------------|----------------------------|-----------------------------------------------------------|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cihaz koşulları  |       En düşük işletim sistemi sürümü  |          *Biçim: Ana. ikincil. derleme <br>örneği: 12.4.4* /Block erişimi |          iOS/iPadOS        | Microsoft, en düşük iOS ana sürümünün Microsoft uygulamaları için desteklenen iOS sürümleriyle eşleşecek şekilde yapılandırılmasını önerir.   Microsoft uygulamaları, N 'nin geçerli iOS ana yayın sürümü olduğu bir N-1 yaklaşımını destekler. Küçük ve derleme sürüm değerleri için Microsoft, cihazların ilgili güvenlik güncelleştirmeleriyle güncel olmasını önerir. Apple 'ın en son önerileri için bkz. [Apple güvenlik güncelleştirmeleri](https://support.apple.com/en-us/HT201222) |
| Cihaz koşulları  |       En düşük işletim sistemi sürümü  |          *Biçim: Ana. ikincil<br> örnek: 8,0* /erişimi engelle   |          Android        | Microsoft, en düşük Android ana sürümünün Microsoft uygulamaları için desteklenen Android sürümleriyle eşleşecek şekilde yapılandırılmasını önerir. Android kurumsal gereksinimleri olan OEM 'Ler ve cihazlar, geçerli sevkiyat sürümü + bir mektup yükseltmesi desteklemelidir.   Android, bilgi çalışanları için Android 8,0 ve üstünü öneriyor.   Android 'in en son önerileri için bkz. [Android Enterprise önerilen gereksinimleri](https://www.android.com/enterprise/recommended/requirements/) |
| Cihaz koşulları  |       Min Patch sürümü  |          *Biçim: yyyy-aa-gg <br> örnek: 2020-01-01* /erişimi engelle  |          Android        | Android cihazlar aylık güvenlik düzeltme ekleri alabilir, ancak yayın OEM 'Lere ve/veya taşıyıcılar 'e bağımlıdır. Kuruluşlar, bu ayarı uygulamadan önce dağıtılmış Android cihazlarının güvenlik güncelleştirmelerini aldığından emin olmalıdır. En son düzeltme eki sürümleri için [Android güvenlik bültenlerini](https://source.android.com/security/bulletin/) inceleyin.  |

#### <a name="level-3-enterprise-high-data-protection"></a>Düzey 3 Kurumsal yüksek veri koruma 

Düzey 3, büyük ve karmaşık güvenlik kuruluşları olan kuruluşlar için standart olarak önerilen veri koruma yapılandırması ya da reklam işlemleri tarafından benzersiz bir şekilde hedeflenen belirli kullanıcılar ve gruplar için önerilir. Bu tür kuruluşlar genellikle iyi ve karmaşık reklam ve Gelişmiş reklam işlemleri tarafından hedeflenir ve bu nedenle açıklanan ek kısıtlamaları ve denetimleri bu şekilde ele almıştır. Bu yapılandırma, ek veri aktarımı senaryolarını kısıtlayarak, PIN yapılandırmasının karmaşıklığını artırarak ve mobil tehdit algılama 'yı ekleyerek düzey 2 ' deki yapılandırmayı genişletir.  

Düzey 3 ' te zorlanan ilke ayarları, düzey 2 ve 1 için önerilen tüm ilke ayarlarını içerir ve yalnızca katı veri koruma yapılandırması ve denetimleri uygulamak için aşağıdaki ilke ayarlarını ekler veya günceller. Bu ilke ayarları, kullanıcılara veya uygulamalara yönelik potansiyel olarak önemli bir etkiye sahip olabilir ve hedeflenen kuruluşların riskleri sayesinde güvenlik yorumlarının bir düzeyini zorunlu tutacaktır.  

#### <a name="data-protection"></a>Veri koruma

| Ayar | Ayar açıklaması |             Değer  |             Platfveyam        | Notlar |
|---------------|---------------------------------------|----------------------------------------|--------------------------------------|---------------------------------------------------------------------------------------------------------|
| Veri aktarımı |       Diğer uygulamalardan veri al  |          İlke ile yönetilen uygulamalar  |          iOS/ıpados, Android         |  |
| Veri aktarımı |       Üçüncü taraf klavyeler  |          Engelle  |          iOS/iPadOS        | İOS 'ta bu, tüm üçüncü taraf klavyelerin uygulama içinde çalışmasını engeller.  |
| Veri aktarımı |       Onaylanan klavyeler  |          Gerekli  |          Android        | Android ile, dağıtılan Android cihazlarınıza göre kullanılabilmesi için klavyeler seçili olmalıdır.  |
| Veri aktarımı |       Onaylanacak klavyeleri seçin  |          *Klavye ekle/kaldır*  |          Android        | Android ile, dağıtılan Android cihazlarınıza göre kullanılabilmesi için klavyeler seçili olmalıdır.  |
| İşlevi |       Kuruluş verilerini yazdırma  |          Engelle  |          iOS/ıpados, Android         |  |

#### <a name="access-requirements"></a>Erişim gereksinimleri

|       Ayar  |          Değer  |          Platfveyam  |
|-----------------------------------------------------------|--------------------|---------------------------------|
|       Basit PIN  |          Engelle  |          iOS/ıpados, Android  |
|       Minimum PIN uzunluğunu seçin  |          6  |          iOS/ıpados, Android  |
|       Gün sayısından sonra PIN sıfırlama  |          Evet  |          iOS/ıpados, Android  |
|       Gün sayısı  |          365  |          iOS/ıpados, Android  |

#### <a name="conditional-launch"></a>Koşullu başlatma

| Ayar | Ayar açıklaması |          Değer/eylem  |          Platfveyam        | Notlar |
|----------------------------|--------------------------------------|-------------------|---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Cihaz koşulları  |          Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar  |        N/A/silme verisi  |          iOS/ıpados, Android        |  |
|       Cihaz koşulları  |          İzin verilen en fazla tehdit düzeyi  |          Güvenli/blok erişimi  |          iOS/ıpados, Android        | <p>Kayıtlı olmayan cihazlar, mobil tehdit savunması kullanılarak tehditler için incelenebilir. Daha fazla bilgi için bkz. [kayıtlı olmayan cihazlar Için mobil tehdit savunması](https://aka.ms/mtdmamdocs).      </p><p>     Cihaz kaydedildiyse bu ayar, kayıtlı cihazlar için Mobile Threat Defense 'in dağıtılmasıyla ilgili olarak atlanabilir. Daha fazla bilgi için bkz. [Kayıtlı cihazlar Için mobil tehdit savunması](~/protect/mtd-device-compliance-policy-create.md).</p> |

## <a name="next-steps"></a>Sonraki adımlar

Yöneticiler, örnek [Intune uygulama koruması Ilkesi Configuration Framework JSON şablonlarını](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) [Intune 'un PowerShell betikleri](https://github.com/microsoftgraph/powershell-intune-samples)ile içe aktararak test ve üretim kullanımı için, yukarıdaki yapılandırma düzeylerini, test ve üretim kullanımına yönelik olarak birleştirebilirler.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
- [Microsoft Intune ile kullanılabilir Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md)
- [Microsoft Intune ile kullanılabilir iOS/ıpados uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md)
- Salesforce mobil uygulaması gibi üçüncü taraf uygulamalar, Intune ile özel şekillerde çalışarak şirket verilerini korur. Doğrudan Salesforce uygulamasının Intune ile nasıl çalıştığını (MDM uygulama yapılandırma ayarları dahil) öğrenmek için bkz. [Salesforce Uygulaması ve Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
