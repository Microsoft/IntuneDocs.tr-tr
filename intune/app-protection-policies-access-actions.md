---
title: Uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme
titleSuffix: Microsoft Intune
description: Microsoft Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silmeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5ca557e-a8e1-4720-b06e-837c4f0bc3ca
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2cfd426a0ae7165a7aae60a90d104852fd834db6
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909125"
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
6. **Ayarlar** bölmesinde aşağı kaydırın, **Erişim Eylemleri** adlı düzenlenebilir bir tablo göreceksiniz.

    ![Intune uygulama koruma erişim eylemlerinin ekran görüntüsü](./media/apps-selective-wipe-access-actions01.png)

7. Bir **Ayar** seçin ve kullanıcıların şirket uygulamanızda oturum açması için karşılaması gereken bir **Değer** girin. 
8. Gereksinimlerinizi karşılamayan kullanıcılar için bir **Eylem** seçin. Bazı durumlarda tek bir ayar için birden çok eylem yapılandırılabilir. Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

>[!NOTE]
> **Cihaz modelleri** ayarını kullanmak için model tanımlayıcılarının noktalı virgülle ayrılmış bir listesini ekleyin. 

## <a name="policy-settings"></a>İlke ayarları 

Uygulama koruma ilkesi ayarları tablosunda **Ayar**, **Değer**, ve **Eylem** sütunları bulunur.

iOS’ta **Ayar** açılan menüsünü kullanarak şu ayarlar için eylemler yapılandırabilirsiniz:
-  En fazla PIN denemesi
-  Çevrimdışı kullanım süresi
-  Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar
-  En düşük işletim sistemi sürümü
-  En düşük uygulama sürümü
-  En düşük SDK sürümü
-  Cihaz modeli/modelleri

Android’de **Ayar** açılan menüsünü kullanarak şu ayarlar için eylemler yapılandırabilirsiniz:
-  En fazla PIN denemesi
-  Çevrimdışı kullanım süresi
-  Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar
-  En düşük işletim sistemi sürümü
-  En düşük uygulama sürümü
-  En düşük düzeltme eki sürümü
-  Cihaz üreticisi/üreticileri

**Erişim için PIN gerektir** ayarı **Evet** olarak ayarlıysa tablo, varsayılan olarak **Çevrimdışı yetkisiz kullanım süresi** ve **En fazla PIN denemesi** için satırları yapılandırılmış ayarlarla doldurur.
 
Bir ayarı yapılandırmak için **Ayar** sütunu altında açılan menüden ayarı seçin. Bir ayar seçildikten sonra, değerin ayarlanması gerekliyse aynı satırda **Değer** sütunu altında bulunan düzenlenebilir metin kutusu etkin hale gelir. Ayrıca **Eylem** sütunu altındaki açılan menü, ayar için geçerli koşullu başlatma eylemleri kümesi ile etkin hale gelir. 

Aşağıdaki listede yaygın eylemler verilmiştir:
-  **Erişimi engelle** – Son kullanıcının şirket uygulamasına erişmesini engelleyin.
-  **Verileri sil** – Son kullanıcının cihazından şirket verilerini silin.
-  **Uyar** – Son kullanıcıya uyarı olarak bir diyalog sağlayın.

### <a name="additional-settings-and-actions"></a>Ek ayarlar ve eylemler 

Bazı durumlarda, örneğin **En düşük işletim sistemi sürümü** ayarında, farklı sürüm numaralarına bağlı olarak ayarı uygulanabilir tüm eylemleri gerçekleştirecek şekilde yapılandırabilirsiniz. 

![Intune uygulama koruma erişim eylemleri - En düşük işletim sistemi sürümünün ekran görüntüsü](./media/apps-selective-wipe-access-actions05.png)

Bir ayar tamamen yapılandırıldıktan sonra ayara ait satır, salt okunur görünüme geçer ve her zaman düzenlenebilir. Ayrıca satırdaki **Ayar** sütununda seçilebilir bir açılan menü bulunur. Yapılandırılmış ve birden fazla eyleme izin vermeyen ayarlarda ise bu açılan menü seçimi bulunmaz.

## <a name="next-steps"></a>Sonraki adımlar

Intune uygulama koruma ilkeleri hakkında daha fazla bilgi edinmek için şu makalelere bakın:
- [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md)
- [iOS uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md)
- [Microsoft Intune’da Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md) 


