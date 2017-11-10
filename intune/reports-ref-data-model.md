---
title: "Veri Ambarı veri modeli | Microsoft Docs"
description: "Intune Veri Ambarı, sürekli değişen mobil ortamınızın geçmiş bilgilerini görüntülemenizi sağlamak için günlük olarak veri örnekleri alır."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 37af15a36ff20b2c13b5fb1157d04a05c40d3216
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="data-warehouse-data-model"></a>Veri Ambarı veri modeli

Intune Veri Ambarı, sürekli değişen mobil ortamınızın geçmiş bilgilerini görüntülemenizi sağlamak için günlük olarak veri örnekleri alır.

Kiracınızdan alınan veriler, veri ambarına eklenir. Ambar, sormak istediğiniz türde sorulara karşılık gelen varlıklar ve ilişkiler kümesidir. Örneğin, yüklemelerde artan bir eğilim olup olmadığını değerlendirmek için şirket içinde geliştirilmiş bir Android uygulamasının geçen hafta içerisindeki günlük yüklenme miktarına göz atabilirsiniz. Veri ambarının yapısı, mobil ortamınız hakkında öngörü kazanmanızı sağlayacak şekildedir. Buna karşılık olarak Microsoft Power BI gibi analiz araçları ise Veri Ambarı veri modelini kullanarak görselleştirmeler ve dinamik panolar oluşturur.

Intune Veri Ambarı yapısı, yıldız şeması modelini kullanır. Bir yıldız şeması, olguları zaman boyutunca düzenler. Model bağlamında bir *olgu*; cihaz sayısı, uygulama sayısı veya kayıt zamanı gibi nicel bir ölçüdür. Model bağlamında bir *boyut* ise bir kategoriler kümesi ve bunların hiyerarşik ilişkisidir. Örneğin günler aylara göre, aylar yıllara göre gruplanır. Yıldız şeması modeli, esneklik ve veri çözümlemesi için iyileştirilmiştir. Böylece değişen mobil ortamınızı anlamanız için gereken raporları oluşturabilirsiniz.

Ambar, verileri aşağıdaki üst düzey kategorilerde kullanıma sunar:
  -  Uygulama koruma etkin uygulamalar ve kullanım
  -  Kayıtlı cihazlar, özellikler ve envanter
  -  Uygulama ve yazılım envanteri
  -  Cihaz yapılandırması ve uyumluluk ilkeleri

**Veri modeli varlık kümeleri**

Varlık kümeleri, veri modelinde adı olan varlık koleksiyonlarıdır. Bu kümeler, modelde toplanan verileri tanımlayan varlıkları barındırır. Her bir valık kümesi, Veri Ambarı veri modeli için bir erişim noktası sağlar. Aşağıdaki varlık kategorileri hakkında ayrıntılar bulabilirsiniz:

  -  [Uygulama](reports-ref-application.md)
  -  [Tarih](reports-ref-date.md)
  -  [Cihazlar](reports-ref-devices.md)
  -  [İlke](reports-ref-policy.md)
  -  [Mobil Uygulama Yönetimi (MAM)](reports-ref-mobile-app-management.md)
  -  [Kullanıcı](reports-ref-user.md)
  -  [Kullanıcı Cihaz İlişkileri](reports-ref-user-device.md)