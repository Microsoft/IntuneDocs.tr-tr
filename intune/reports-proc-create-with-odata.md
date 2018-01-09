---
title: "Power BI ile OData akışından bir rapor oluşturma | Microsoft Docs"
description: "Power BI Desktop kullanarak Intune Veri Ambarı API’sinden etkileşimli bir filtre ile ağaç harita görselleştirmesi oluşturun."
keywords: "Intune Veri Ambarı"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 436114837d515d3a03f253c9c8c6e195bff0af41
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>OData akışına Power BI ile bir rapor oluşturma

Bu eğitimde, Power BI Desktop kullanarak etkileşimli bir filtre ile ağaç harita görselleştirmesi oluşturacaksınız. Örneğin malı işlerden sorumlu genel müdürünüz, şirkete ait cihazlarla kişisel cihazların genel dağılımını öğrenmek isteyebilir. Bu ağaç harita, toplam cihaz türü sayısı hakkında bilgi sağlar. Kaç tane iOS, Android ve Windows cihazın şirkete ait veya kişisel cihaz olduğunu gözden geçirebilirsiniz.

### <a name="overview-of-creating-the-chart"></a>Grafiği oluşturmaya genel bakış

Bu grafiği oluşturmak için şunları yapmanız gerekir:
1. Hala yüklemediyseniz Power BI Desktop yükleyin.
2. Intune Veri Ambarı ver modeline bağlanın ve model için geçerli verileri alın.
3. Veri modeli ilişkileri oluşturun veya yönetin.
4. **Cihazlar** tablosundaki verilerle grafiği oluşturun.
5. Etkileşimli bir filtre oluşturun.
6. Tamamlanan grafiği görüntüleyin.

### <a name="a-note-about-tables-and-entities"></a>Tablolar ve varlıklar hakkında bir not

Power BI’da tablolar ile çalışırsınız. Tabloların veri alanları bulunur. Her bir veri alanına ait bir veri türü vardır. Alanlar yalnızca uygun veri türüne ait verileri barındırabilir. Veri türleri numara, metin, tarih vb. şeklindedir. Power BI’daki tablolar, modeli yüklediğinizde kiracınızda bulunan geçmiş verilerle dolar. Bazı veriler zamanla değişse de, veri modeli güncelleştirilmediği sürece tablo yapısı değişmez.

_Varlık_ ve _tablo_ terimlerinin kullanımı aklınızı karıştırabilir. Veri modeline OData akışından erişilebilir. OData evreninde tablo olarak bilinen öğelere Power BI’da varlık adı verilir. Her iki terim de aslında aynı olup verilerinizi taşıyan şeye verilen addır.

## <a name="install-power-bi-desktop"></a>Power BI Desktop’ı yükleme

En yeni Power BI Desktop sürümünü yükleyin. Power BI Desktop’ı şu adresten indirebilirsiniz: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Kiracınız için Intune Veri Ambarı OData akışına bağlanma

> [!Note]  
> Intune’da **Raporlar** izniniz olmalıdır. Daha fazla bilgi için bkz. [Yetkilendirme](reports-api-url.md).

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Intune Veri Ambarı** dikey penceresini açın.
4. Özel akış URL’sini kopyalayın. Örneğin: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Power BI Desktop’ı açın.
6. **Veri Al** > **OData akışı**’nı seçin.
7. Özel akış URL’sini **OData akışı** penceresindeki URL kutusuna yapıştırın.
8. **Temel**’i seçin.

    ![OData akışı](media/reports-create-01-odatafeed.png)

9. **Tamam**’ı seçin.
10. **Kuruluş hesabı**’nı seçin ve Intune kimlik bilgilerinizle oturum açın. 

    ![Kuruluş hesabı kimlik bilgileri](media/reports-create-02-org-account.png)

11. **Bağlan**’ı seçin. Gezgin açılacak ve size Intune Veri Ambarı’ndaki tabloların listesini gösterecektir. 

    ![Gezgin](media/reports-create-02-loadentities.png)

12. **cihazlar** ve **ownerTypes** tablolarını seçin.  **Yükle**’yi seçin. Power BI modele veri yükler.

## <a name="create-a-relationship"></a>Bir ilişki oluşturma 

Çözümlemek için birden fazla tabloyu içeri aktarabilirsiniz, yani yalnızca bir tablodaki verileri değil, farklı tablolardaki ilişkili verileri alabilirsiniz.  Power BI’ın sizin için ilişkileri arayan ve oluşturan **otomatik algılama** özelliği mevcuttur. Veri Ambarı’ndaki tablolar, Power BI’ın otomatik algılama özelliğiyle birlikte çalışabilecek şekilde derlenmiştir. Ancak Power BI ilişkileri otomatik olarak bulamasa bile bunları yönetebilirsiniz.

![İlişkileri yönetme](media/reports-create-03-managerelationships.png)

1. **İlişkileri Yönet**’i seçin.
2. Power BI ilişkileri henüz algılamadıysa **Otomatik algıla...** seçeneğine tıklayın.  
İlişki, Kaynak ve Hedef sütunlarında görüntülenir. Bu örnekte **cihazlar** tablosundaki **ownerTypeKey** veri alanı, **ownerTypes** tablosundaki **ownerTypeKey** veri alanına bağlantı sağlar. Bu ilişkiyi kullanarak cihaz türü kodunun düz adını **cihazlar** tablosunda arayabilirsiniz.

## <a name="create-a-treemap-visualization"></a>Ağaç haritası görselleştirmesi oluşturma

Bir ağaç haritası, hiyerarşik verileri kutu içinde kutu olarak gösterir. Hiyerarşinin her bir dalında kutular bulunur. Bu kutular ise alt dalları gösteren daha küçük kutular barındırır. Intune verilerinizin ağaç haritasını oluşturmak için Power BI Desktop kullanabilirsiniz.

![Görselleştirmeler > ağaç haritası](media/reports-create-03-treemap.png)

1. Grafik türü seçin. **Ağaç haritası**’nı seçin.
2. Veri modelinde **cihazlar** tablosunu bulun.
3. **Cihazlar** tablosunu genişletin ve **Alanlar** panelindeki **üretici** veri alanını seçin.
4. **Üretici** veri alanını, rapor tuvalindeki Ağaç Haritasına sürükleyin.
5. **Cihazlar** tablosundaki **deviceKey** veri alanını **Görselleştirmeler** panelindeki **Değerler** bölümüne sürükleyin ve **Veri alanını buraya sürükleyin** adlı kutuya bırakın.  
Artık kuruluşunuzdaki cihaz üreticisi dağılımını gösteren bir görseliniz var.

![Verilerle ağaç haritası](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Bir filtre ekleme

Uygulamanızı kullanarak ilave sorular yanıtlayabilmek için ağaç haritanıza bir filtre ekleyebilirsiniz. 

1. Rapor tuvalini seçin ve daha sonra **Görselleştirmeler** altında bulunan **Dilimleyici simgesine** ( ![Verilerle ağaç haritası](media/reports-create-slicer.png) ) tıklayarak filtre ekleyin.
2. **ownerTypes** tablosunu bulun ve **ownerTypeName** veri alanını **Görselleştirmeler** panelindeki **Filtreler**’in altına sürükleyin.  
   Cihazlar tablosu altında **OwnerTypeKey** adlı bir veri alanı vardır. Bu veri alanı, cihazın şirkete ait veya kişisel olmasıyla ilgili bir kod barındırır. Bu filtrede kolay adlar kullanmayı tercih edeceğiniz için **ownerTypes** tablosunu bulun ve **ownerTypeName**’i sürükleyin. Bu, veri modelinin tablolar arasındaki ilişkiyi nasıl desteklediğine bir örnekti.

![Filtreyle ağaç haritası](media/reports-create-08_ownertype.png)

Artık dağılımın nasıl değiştiğini görmek için şirkete ait ve kişisel cihazlar arasında geçiş yapmak üzere kullanılacak bir filtreniz var.

1. **Şirket**’e tıklayarak şirkete ait cihaz dağılımını görüntüleyin.
2. **Kişisel**’e tıklayarak kişisel cihazları görüntüleyin.

## <a name="next-steps"></a>Sonraki adımlar

 - Power BI Desktop’ta [ilişki oluşturma ve yönetme](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) hakkında Power BI belgelerinden daha fazla bilgi edinin.
 - [Intune Veri Ambarı](https://docs.microsoft.com/intune/reports-ref-data-model)’na başvurun.