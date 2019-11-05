---
title: Uygulama koruma ilkesini kullanarak verileri silme koşullu başlatma eylemleri
titleSuffix: Microsoft Intune
description: Microsoft Intune 'de uygulama koruma ilkesi koşullu başlatma eylemlerini kullanarak verileri seçmeli olarak temizlemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 882c542d6a1d981b9924bb33eee40f03b41689f7
ms.sourcegitcommit: 4bf23327af734a9811d555fbd566c31239e2acd6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999483"
---
# <a name="selectively-wipe-data-using-app-protection-policy-conditional-launch-actions-in-intune"></a>Intune 'da uygulama koruma ilkesi koşullu başlatma eylemlerini kullanarak verileri seçmeli olarak silme

Intune uygulama koruma ilkelerini kullanarak son kullanıcıların şirket uygulaması veya hesabına erişmelerini engellemek için ayarlar yapılandırabilirsiniz. Bu ayarlar, verileri yeniden konumlandırmayı hedefler ve jailbreak uygulanmış cihazlar veya en düşük işletim sistemi sürümleri gibi öğeler için kuruluşunuz tarafından ayarlanmış gereksinimlere erişir.
 
Bu ayarları kullanarak, uyumsuzluk durumunda son kullanıcının cihazından şirketinizin kurumsal verilerini silmeyi açıkça seçebilirsiniz. Bazı ayarlarda birden fazla eylem yapılandırabilirsiniz; örneğin belirtilen farklı değerlere bağlı olarak erişimi engellemek ve veri silmek gibi.

## <a name="create-an-app-protection-policy-using-conditional-launch-actions"></a>Koşullu başlatma eylemlerini kullanarak bir uygulama koruma ilkesi oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin.
4. **İlke ekle**’ye tıklayın (Mevcut bir ilkeyi de düzenleyebilirsiniz). 
5. İlke için yapılandırmaya uygun ayarların bir listesini görmek üzere **Gerekli ayarları yapılandır**’a tıklayın. 
6. Ayarlar bölmesinde aşağı kaydırarak, düzenlenebilir tabloyla **koşullu başlatma** başlıklı bir bölüm görürsünüz.

    ![Intune uygulama koruma erişim eylemlerinin ekran görüntüsü](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions01.png)

7. Bir **Ayar** seçin ve kullanıcıların şirket uygulamanızda oturum açması için karşılaması gereken bir **Değer** girin. 
8. Gereksinimlerinizi karşılamayan kullanıcılar için bir **Eylem** seçin. Bazı durumlarda tek bir ayar için birden çok eylem yapılandırılabilir. Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

>[!NOTE]
> **Cihaz modellerini veya cihaz üreticisini** kullanmak için, cihaz modeli tanımlayıcılarının (iOS) veya cihaz üreticilerinin (Android) noktalı virgülle ayrılmış bir listesini girin. Birden çok değer listesinde boşluklardan kaçının. Bu değerler büyük/küçük harfe duyarlı değildir. 

## <a name="policy-settings"></a>İlke ayarları 

Uygulama koruma ilkesi ayarları tablosunda **Ayar**, **Değer**, ve **Eylem** sütunları bulunur.

### <a name="ios-policy-settings"></a>iOS ilke ayarları
iOS’ta **Ayar** açılan menüsünü kullanarak şu ayarlar için eylemler yapılandırabilirsiniz:
- En fazla PIN denemesi
- Çevrimdışı kullanım süresi
- Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar
- En düşük işletim sistemi sürümü
- En düşük uygulama sürümü
- En düşük SDK sürümü
- Cihaz modeli/modelleri
- İzin verilen en fazla cihaz tehdit düzeyi

**Cihaz modelleri** ayarını kullanmak için iOS model tanımlayıcılarının noktalı virgülle ayrılmış bir listesini ekleyin. [HockeyApp'in destek belgelerindeki](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types) Device Type sütunu altında bir iOS model tanımlayıcısı bulabilirsiniz.<br>
Örnek giriş: *iPhone5,2;iPhone5,3*

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri'nde belirtilen cihaz modeli dizelerinin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Eşleştirme tamamen cihazın bildirdiklerine bağlıdır. BT yöneticisi olarak, çeşitli cihaz üreticileri ve modelleri temelinde ve küçük bir kullanıcı grubunu hedefleyerek bu ayarı test etmenizi ve beklenen davranışın gerçekleştiğinden emin olmanızı öneririz. Varsayılan değer **Yapılandırılmadı**'dır.<br>
Aşağıdaki eylemlerden birini ayarlayın: 
- Belirtilenlere izin ver (Belirtilmeyenleri engelle)
- Belirtilenlere izin ver (Belirtilmeyenleri sil)

**BT yöneticisi aynı Intune kullanıcısı için aynı uygulamaları hedefleyen ilkeler arasında farklı bir iOS model tanımlayıcısı listesi girerse ne olur?**<br>
Yapılandırılan değerler için iki uygulama koruma ilkesi arasında çakışmalar ortaya çıktığında, Intune normalde en kısıtlayıcı yaklaşımı benimser. Dolayısıyla, sonuçta hedeflenen Intune kullanıcısının açtığı hedef uygulamaya gönderilen ilke, aynı uygulama/kullanıcı bileşimini hedefleyen *İlke A* ile *İlke B*'de listelenen iOS model tanımlayıcılarının kesişimi olabilir. Örneğin, *İlke A* "iPhone5,2;iPhone5,3" öğelerini belirtirken *İlke B* "iPhone5,3" öğelerini belirtiyor olabilir. Sonuçta hem *İlke A* hem de *İlke B* ile hedeflenen Intune kullanıcısının ilkesi "iPhone5,3" olacaktır. 

### <a name="android-policy-settings"></a>Android ilkesi ayarları

Android’de **Ayar** açılan menüsünü kullanarak şu ayarlar için eylemler yapılandırabilirsiniz:
- En fazla PIN denemesi
- Çevrimdışı kullanım süresi
- Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar
- En düşük işletim sistemi sürümü
- En düşük uygulama sürümü
- En düşük düzeltme eki sürümü
- Cihaz üreticisi/üreticileri
- SafetyNet cihaz kanıtlama
- Uygulamalarda tehdit taraması iste
- Min Şirket Portalı sürümü
- İzin verilen en fazla cihaz tehdit düzeyi

**Min Şirket portalı sürümünü**kullanarak, bir son kullanıcı cihazında zorlanan Şirket portalı için belirli bir en düşük tanımlı sürümü belirtebilirsiniz. Bu koşullu başlatma ayarı, her bir değer karşılanmazsa **erişimi engellemek**, **verileri silmek**ve olası eylemler olarak **uyarmak** için değerler ayarlamanıza olanak sağlar. Bu değer için olası biçimler *[ana] düzenine uyar. [ İkincil]* , *[birincil]. [ İkincil]. [Derleme]* veya *[birincil]. [ İkincil]. [Derleme]. [Düzeltme]* . Bazı son kullanıcılar, bir uygulama için bu şekilde zorlanan bir güncelleştirme tercih edemeyebilir, bu ayar yapılandırılırken ' warn ' seçeneği ideal olabilir. Google Play Store, uygulama güncelleştirmeleri için yalnızca Delta baytlarını göndermenin iyi bir işini yapar, ancak bu, kullanıcının güncelleştirme sırasında veriler üzerinde olmaları durumunda kullanmak istememe büyük miktarda veri olabilir. Güncelleştirme zorlamak ve böylece güncelleştirilmiş bir uygulamanın indirilmesi, güncelleştirme sırasında beklenmeyen veri ücretlerine neden olabilir. Yapılandırılmışsa **Min Şirket Portalı sürüm** ayarı, Şirket Portalı sürüm 5.0.4560.0 ve gelecekteki tüm şirket portalı sürümlerini alan son kullanıcıları etkileyecektir. Bu ayarın, bu özelliğin yayımlandığı sürümden daha eski bir Şirket Portalı sürümünü kullanan kullanıcılar üzerinde hiçbir etkisi olmayacaktır. En son Şirket Portalı sürümünde olabilecekleri için, cihazlarından uygulama otomatik güncelleştirmelerini kullanan son kullanıcılar bu özellikten hiçbir iletişim kutusu görmeyecektir. Bu ayar yalnızca kayıtlı ve kayıtlı olmayan cihazlar için uygulama korumasıyla Android 'dir.

**Cihaz üreticileri** ayarını kullanmak için Android üreticilerinin noktalı virgülle ayrılmış bir listesini ekleyin. Cihazın Android üreticisini, cihaz ayarlarının altında bulabilirsiniz.<br>
Örnek giriş: *Üretici A;Üretici B* 

>[!NOTE]
> Intune kullanan cihazlardan bildirilen ve giriş olarak kullanılabilen bazı yaygın üreticiler şunlardır: Asus;Blackberry;Bq;Gionee;Google;Hmd global;Htc;Huawei;Infinix;Kyocera;Lemobile;Lenovo;Lge;Motorola;Oneplus;Oppo;Samsung;Sharp;Sony;Tecno;Vivo;Vodafone;Xiaomi;Zte;Zuk

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri'nde belirtilen cihaz modeli dizelerinin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Eşleştirme tamamen cihazın bildirdiklerine bağlıdır. BT yöneticisi olarak, çeşitli cihaz üreticileri ve modelleri temelinde ve küçük bir kullanıcı grubunu hedefleyerek bu ayarı test etmenizi ve beklenen davranışın gerçekleştiğinden emin olmanızı öneririz. Varsayılan değer **Yapılandırılmadı**'dır.<br>
Aşağıdaki eylemlerden birini ayarlayın: 
- Belirtilenlere izin ver (Belirtilmeyenleri engelle)
- Belirtilenlere izin ver (Belirtilmeyenleri engelle)

**BT yöneticisi aynı Intune kullanıcısı için aynı uygulamaları hedefleyen ilkeler arasında farklı bir Android üreticileri listesi girerse ne olur?**<br>
Yapılandırılan değerler için iki uygulama koruma ilkesi arasında çakışmalar ortaya çıktığında, Intune normalde en kısıtlayıcı yaklaşımı benimser. Dolayısıyla, sonuçta hedeflenen Intune kullanıcısının açtığı hedef uygulamaya gönderilen ilke, aynı uygulama/kullanıcı bileşimini hedefleyen *İlke A* ile *İlke B*'de listelenen Android üreticilerinin kesişimi olabilir. Örneğin, *İlke A* "Google;Samsung" öğelerini belirtirken; *İlke B* "Google" öğesini belirtir. Intune kullanıcısının hem *İlke A* hem de *İlke B* ile hedeflenen sonuç ilkesi "Google" olacaktır. 

### <a name="additional-settings-and-actions"></a>Ek ayarlar ve eylemler 

**Erişim için PIN gerektir** ayarı **Evet** olarak ayarlıysa tablo, varsayılan olarak **Çevrimdışı yetkisiz kullanım süresi** ve **En fazla PIN denemesi** için satırları yapılandırılmış ayarlarla doldurur.
 
Bir ayarı yapılandırmak için **Ayar** sütunu altında açılan menüden ayarı seçin. Bir ayar seçildikten sonra, değerin ayarlanması gerekliyse aynı satırda **Değer** sütunu altında bulunan düzenlenebilir metin kutusu etkin hale gelir. Ayrıca **Eylem** sütunu altındaki açılan menü, ayar için geçerli koşullu başlatma eylemleri kümesi ile etkin hale gelir. 

Aşağıdaki listede yaygın eylemler verilmiştir:
- **Erişimi engelle** – Son kullanıcının şirket uygulamasına erişmesini engelleyin.
- **Verileri sil** – Son kullanıcının cihazından şirket verilerini silin.
- **Uyar** – Son kullanıcıya uyarı olarak bir diyalog sağlayın.

Bazı durumlarda, örneğin **En düşük işletim sistemi sürümü** ayarında, farklı sürüm numaralarına bağlı olarak ayarı uygulanabilir tüm eylemleri gerçekleştirecek şekilde yapılandırabilirsiniz. 

![Uygulama koruma erişim eylemlerinin ekran görüntüsü-en düşük işletim sistemi sürümü](./media/app-protection-policies-access-actions/apps-selective-wipe-access-actions05.png)

Bir ayar tamamen yapılandırıldıktan sonra ayara ait satır, salt okunur görünüme geçer ve her zaman düzenlenebilir. Ayrıca satırdaki **Ayar** sütununda seçilebilir bir açılan menü bulunur. Yapılandırılmış ve birden fazla eyleme izin vermeyen ayarlarda ise bu açılan menü seçimi bulunmaz.

## <a name="next-steps"></a>Sonraki adımlar

Intune uygulama koruma ilkeleri hakkında daha fazla bilgi edinmek için şu makalelere bakın:
- [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md)
- [iOS uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md)
- [Microsoft Intune’da Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md) 