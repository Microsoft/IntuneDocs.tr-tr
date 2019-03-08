---
title: Veri Ambarı veri modeli
titlesuffix: Microsoft Intune
description: Microsoft Intune Veri Ambarı, sürekli değişen mobil ortamınızın geçmiş bilgilerini görüntülemenizi sağlamak için günlük olarak veri örnekleri alır.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2cbf6e1bde3f8853f2e5c6c1919089bf0dc10126
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565529"
---
# <a name="microsoft-intune-data-warehouse-data-model"></a>Microsoft Intune veri ambarı veri modeli

Intune Veri Ambarı, sürekli olarak değişen mobil cihazların bulunduğu ortamın tarihsel bir görünümünü sağlamak için verileri örnekler. Görünüm, zaman içinde ilgili varlıklardan oluşur.

## <a name="entities-entity-sets"></a>Varlıklar: Varlık kümeleri

Ambar, verileri aşağıdaki üst düzey kategorilerde kullanıma sunar:

  -  Uygulama koruma etkin uygulamalar ve kullanım
  -  Kayıtlı cihazlar, özellikler ve envanter
  -  Uygulama ve yazılım envanteri
  -  Cihaz yapılandırması ve uyumluluk ilkeleri

Bu alanlar, Intune ortamınızla ilişkili olan varlıkları içerir. Varlıklar kümeleri ile ilgili ayrıntıları aşağıdaki konularda bulabilirsiniz:

  -  [Uygulama](reports-ref-application.md)
  -  [Tarih](reports-ref-date.md)
  -  [Cihazlar](reports-ref-devices.md)
  -  [Intune Yönetim Uzantısı](reports-ref-intunemanagementextension.md)
  -  [İlke](reports-ref-policy.md)
  -  [Mobil Uygulama Yönetimi (MAM)](reports-ref-mobile-app-management.md)
  -  [Kullanıcı](reports-ref-user.md)
  -  [Geçerli Kullanıcı](reports-ref-current-user.md)
  -  [Kullanıcı Cihaz İlişkileri](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a>İlişkiler: Yıldız şeması modeli

Ambar, ilişki içindeki varlıkları, sormak istediğiniz soru türüyle alakalı ilişki içindeki varlıkları düzenler. Örneğin, şirket tarafından geliştirilen bir Android uygulamasının yükleme sayısını inceleyebilirsiniz. Veri ambarının yapısı, mobil ortamınız hakkında öngörü kazanmanızı sağlayacak şekildedir. Buna karşılık olarak Microsoft Power BI gibi analiz araçları ise Veri Ambarı veri modelini kullanarak görselleştirmeler ve dinamik panolar oluşturur.

Varlıklar ve ilişkiler bir yıldız şeması modeli kullanır. Bir yıldız şeması, gerçekleri zamana göre ilişkilendirir. Model bağlamında bir *olgu*; cihaz sayısı, uygulama sayısı veya kayıt zamanı gibi nicel bir ölçüdür. Olgu tabloları çok fazla veri depolar. Çok büyük olabilirler ve bu nedenle bilgileri genellikle 30 gün ile sınırlarlar. Bir *boyut* olgular için bağlam sağlar. Olgu, olanları ölçtüğünde, boyutlar neyin başına ne geldiğini gösterir. **Kullanıcı** tablosu gibi boyut tabloları daha küçüktür ve verileri gerçek zamanlı tablolardan daha uzun süreler için yeniden eğitebilir. 

Yıldız şeması modeli, esneklik ve veri çözümlemesi için iyileştirilmiştir. Böylece değişen mobil ortamınızı anlamanız için gereken raporları oluşturabilirsiniz.

## <a name="time-daily-snapshots"></a>Süre: Günlük anlık görüntüleri

Ambar, Intune'daki verilerden aşağı akıştadır. Intune gece yarısı UTC'de günlük anlık görüntü alır ve anlık görüntüyü ambarda saklar. Tutulan anlık görüntülerin süresi, olgu tablosundan olgu tablosuna farklılık gösterir. Bazıları yedi gün, diğerleri 30 gün ve daha uzun süreli olabilir.

## <a name="next-steps"></a>Sonraki adımlar

 - Veri ambarının kullanıcının ömrünü Intune’da nasıl izlediği hakkında daha fazla bilgi edinmek için bkz. [Intune Veri Ambarı’nda kullanıcı ömrü gösterimi](reports-ref-user-timeline.md).
 - Veri ambarları ile çalışma hakkında daha fazla bilgi edinmek için bkz. [İlk Veri Ambarı’nı Oluşturma](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse).
 - [Bir veri kümesini içeri aktararak yeni Power BI raporu oluşturma](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/) içindeki Power BI ve bir veri ambarı ile çalışma hakkında daha fazla bilgi edinmek için. 
