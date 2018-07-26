---
title: Uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme
titleSuffix: Microsoft Intune
description: Microsoft Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silmeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f422b5619115b44b8d39c2d735f2163c22167f
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138705"
---
# <a name="selectively-wipe-data-using-app-protection-policy-access-actions-in-intune"></a>Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme

Intune uygulama koruma ilkelerini kullanarak son kullanıcıların şirket uygulaması veya hesabına erişmelerini engellemek için ayarlar yapılandırabilirsiniz. Bu ayarlar, verileri yeniden konumlandırmayı hedefler ve jailbreak uygulanmış cihazlar veya en düşük işletim sistemi sürümleri gibi öğeler için kuruluşunuz tarafından ayarlanmış gereksinimlere erişir.
 
Bu ayarları kullanarak, uyumsuzluk durumunda son kullanıcının cihazından şirketinizin kurumsal verilerini silmeyi açıkça seçebilirsiniz. Bazı ayarlarda birden fazla eylem yapılandırabilirsiniz; örneğin belirtilen farklı değerlere bağlı olarak erişimi engellemek ve veri silmek gibi.

## <a name="create-an-app-protection-policy-using-access-actions"></a>Erişim eylemlerini kullanarak uygulama koruma ilkesi oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar** > **Uygulama koruma ilkeleri**’ni seçin.
4. **İlke ekle**’ye tıklayın (Mevcut bir ilkeyi de düzenleyebilirsiniz). 
5. İlke için yapılandırmaya uygun ayarların bir listesini görmek üzere **Gerekli ayarları yapılandır**’a tıklayın. 
6. Ayarlar bölmesinde ekranı aşağı kaydırın, **Erişim Eylemleri** adlı düzenlenebilir bir tablo göreceksiniz.

    ![Intune uygulama koruma erişim eylemlerinin ekran görüntüsü](./media/apps-selective-wipe-access-actions01.png)

7. Bir **Ayar** seçin ve kullanıcıların şirket uygulamanızda oturum açması için karşılaması gereken bir **Değer** girin. 
8. Gereksinimlerinizi karşılamayan kullanıcılar için bir **Eylem** seçin. Bazı durumlarda tek bir ayar için birden çok eylem yapılandırılabilir. Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

>[!NOTE]
> **Cihaz modelleri** ayarını kullanmak için model tanımlayıcılarının noktalı virgülle ayrılmış bir listesini ekleyin. 

## <a name="policy-settings"></a>İlke ayarları 

Uygulama koruma ilkesi ayarları tablosunda **Ayar**, **Değer**, ve **Eylem** sütunları bulunur.

### <a name="ios-policy-settings"></a>iOS ilke ayarları
iOS’ta **Ayar** açılan menüsünü kullanarak şu ayarlar için eylemler yapılandırabilirsiniz:
-  En fazla PIN denemesi
-  Çevrimdışı kullanım süresi
-  Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar
-  En düşük işletim sistemi sürümü
-  En düşük uygulama sürümü
-  En düşük SDK sürümü
-  Cihaz modeli/modelleri

**Cihaz modelleri** ayarını kullanmak için iOS model tanımlayıcılarının noktalı virgülle ayrılmış bir listesini ekleyin. [HockeyApp'in destek belgelerindeki](https://support.hockeyapp.net/kb/client-integration-ios-mac-os-x-tvos/ios-device-types) Device Type sütunu altında bir iOS model tanımlayıcısı bulabilirsiniz.<br>
Örnek giriş: *iPhone5,2; iPhone5,3*

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri'nde belirtilen cihaz modeli dizelerinin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Eşleştirme tamamen cihazın bildirdiklerine bağlıdır. BT yöneticisi olarak, çeşitli cihaz üreticileri ve modelleri temelinde ve küçük bir kullanıcı grubunu hedefleyerek bu ayarı test etmenizi ve beklenen davranışın gerçekleştiğinden emin olmanızı öneririz. Varsayılan değer **Yapılandırılmadı**'dır.<br>
Aşağıdaki eylemlerden birini ayarlayın: 
- Belirtilenlere izin ver (Belirtilmeyenleri engelle)
- Belirtilenlere izin ver (Belirtilmeyenleri sil)

**BT yöneticisi aynı Intune kullanıcısı için aynı uygulamaları hedefleyen ilkeler arasında farklı bir iOS model tanımlayıcısı listesi girerse ne olur?**<br>
Yapılandırılan değerler için iki uygulama koruma ilkesi arasında çakışmalar ortaya çıktığında, Intune normalde en kısıtlayıcı yaklaşımı benimser. Dolayısıyla, sonuçta hedeflenen Intune kullanıcısının açtığı hedef uygulamaya gönderilen ilke, aynı uygulama/kullanıcı bileşimini hedefleyen *İlke A* ile *İlke B*'de listelenen iOS model tanımlayıcılarının kesişimi olabilir. Örneğin, *İlke A* "iPhone5,2; iPhone5,3" öğelerini belirtirken *İlke B* "iPhone5,3" öğelerini belirtiyor olabilir. Sonuçta hem *İlke A* hem de *İlke B* ile hedeflenen Intune kullanıcısının ilkesi "iPhone5,3" olacaktır. 

### <a name="android-policy-settings"></a>Android ilkesi ayarları

Android’de **Ayar** açılan menüsünü kullanarak şu ayarlar için eylemler yapılandırabilirsiniz:
-  En fazla PIN denemesi
-  Çevrimdışı kullanım süresi
-  Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar
-  En düşük işletim sistemi sürümü
-  En düşük uygulama sürümü
-  En düşük düzeltme eki sürümü
-  Cihaz üreticisi/üreticileri

**Cihaz üreticileri** ayarını kullanmak için Android üreticilerinin noktalı virgülle ayrılmış bir listesini ekleyin. Cihazın Android üreticisini, cihaz ayarlarının altında bulabilirsiniz.<br>
Örnek giriş: *Üretici A; Üretici B; Google* 

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri'nde belirtilen cihaz modeli dizelerinin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Eşleştirme tamamen cihazın bildirdiklerine bağlıdır. BT yöneticisi olarak, çeşitli cihaz üreticileri ve modelleri temelinde ve küçük bir kullanıcı grubunu hedefleyerek bu ayarı test etmenizi ve beklenen davranışın gerçekleştiğinden emin olmanızı öneririz. Varsayılan değer **Yapılandırılmadı**'dır.<br>
Aşağıdaki eylemlerden birini ayarlayın: 
- Belirtilenlere izin ver (Belirtilmeyenleri engelle)
- Belirtilenlere izin ver (Belirtilmeyenleri engelle)

**BT yöneticisi aynı Intune kullanıcısı için aynı uygulamaları hedefleyen ilkeler arasında farklı bir Android üreticileri listesi girerse ne olur?**<br>
Yapılandırılan değerler için iki uygulama koruma ilkesi arasında çakışmalar ortaya çıktığında, Intune normalde en kısıtlayıcı yaklaşımı benimser. Dolayısıyla, sonuçta hedeflenen Intune kullanıcısının açtığı hedef uygulamaya gönderilen ilke, aynı uygulama/kullanıcı bileşimini hedefleyen *İlke A* ile *İlke B*'de listelenen Android üreticilerinin kesişimi olabilir. Örneğin, *İlke A* "Google, Samsung" öğelerini belirtirken; *İlke B* "Google" öğesini belirtir. Intune kullanıcısının hem *İlke A* hem de *İlke B* ile hedeflenen sonuç ilkesi "Google" olacaktır. 

### <a name="additional-settings-and-actions"></a>Ek ayarlar ve eylemler 

**Erişim için PIN gerektir** ayarı **Evet** olarak ayarlıysa tablo, varsayılan olarak **Çevrimdışı yetkisiz kullanım süresi** ve **En fazla PIN denemesi** için satırları yapılandırılmış ayarlarla doldurur.
 
Bir ayarı yapılandırmak için **Ayar** sütunu altında açılan menüden ayarı seçin. Bir ayar seçildikten sonra, değerin ayarlanması gerekliyse aynı satırda **Değer** sütunu altında bulunan düzenlenebilir metin kutusu etkin hale gelir. Ayrıca **Eylem** sütunu altındaki açılan menü, ayar için geçerli koşullu başlatma eylemleri kümesi ile etkin hale gelir. 

Aşağıdaki listede yaygın eylemler verilmiştir:
-  **Erişimi engelle** – Son kullanıcının şirket uygulamasına erişmesini engelleyin.
-  **Verileri sil** – Son kullanıcının cihazından şirket verilerini silin.
-  **Uyar** – Son kullanıcıya uyarı olarak bir diyalog sağlayın.

Bazı durumlarda, örneğin **En düşük işletim sistemi sürümü** ayarında, farklı sürüm numaralarına bağlı olarak ayarı uygulanabilir tüm eylemleri gerçekleştirecek şekilde yapılandırabilirsiniz. 

![Intune uygulama koruma erişim eylemleri - En düşük işletim sistemi sürümünün ekran görüntüsü](./media/apps-selective-wipe-access-actions05.png)

Bir ayar tamamen yapılandırıldıktan sonra ayara ait satır, salt okunur görünüme geçer ve her zaman düzenlenebilir. Ayrıca satırdaki **Ayar** sütununda seçilebilir bir açılan menü bulunur. Yapılandırılmış ve birden fazla eyleme izin vermeyen ayarlarda ise bu açılan menü seçimi bulunmaz.

## <a name="next-steps"></a>Sonraki adımlar

Intune uygulama koruma ilkeleri hakkında daha fazla bilgi edinmek için şu makalelere bakın:
- [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md)
- [iOS uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md)
- [Microsoft Intune’da Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md) 


