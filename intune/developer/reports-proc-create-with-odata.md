---
title: OData akışından Power BI ile bir Intune raporu oluşturma
titleSuffix: Microsoft Intune
description: Power BI Desktop kullanarak Intune Veri Ambarı API’sinden etkileşimli bir filtre ile ağaç harita görselleştirmesi oluşturun.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 18815fb671e853bc0463fed750d40b80ccb285fb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74784281"
---
# <a name="create-an-intune-report-from-the-odata-feed-with-power-bi"></a>OData akışından Power BI ile bir Intune raporu oluşturma

Bu makalede, kullanıcıların etkileşimli bir filtre Power BI Desktop kullanarak Intune verilerinizin ağaç Haritası görselleştirmesinin nasıl oluşturulacağı açıklanmaktadır. Örneğin, CFO, cihazların genel dağıtımının şirkete ait cihazlar ve kişisel cihazlar arasında nasıl Karşılaştırıldığı hakkında bilgi alabilir. Bu ağaç harita, toplam cihaz türü sayısı hakkında bilgi sağlar. Kaç tane iOS, Android ve Windows cihazın şirkete ait veya kişisel cihaz olduğunu gözden geçirebilirsiniz.

## <a name="overview-of-creating-the-chart"></a>Grafiği oluşturmaya genel bakış

Bu grafiği oluşturmak için şunları yapmanız gerekir:
1. Hala yüklemediyseniz Power BI Desktop yükleyin.
2. Intune Veri Ambarı ver modeline bağlanın ve model için geçerli verileri alın.
3. Veri modeli ilişkileri oluşturun veya yönetin.
4. **Cihazlar** tablosundaki verilerle grafiği oluşturun.
5. Etkileşimli bir filtre oluşturun.
6. Tamamlanan grafiği görüntüleyin.

### <a name="a-note-about-tables-and-entities"></a>Tablolar ve varlıklar hakkında bir not

Power BI’da tablolar ile çalışırsınız. Tabloların veri alanları bulunur. Her bir veri alanına ait bir veri türü vardır. Alanlar yalnızca uygun veri türüne ait verileri barındırabilir. Veri türleri numara, metin, tarih vb. şeklindedir. Power BI’daki tablolar, modeli yüklediğinizde kiracınızda bulunan geçmiş verilerle dolar. Bazı veriler zamanla değişse de, veri modeli güncelleştirilmediği sürece tablo yapısı değişmez.

*Varlık* ve *tablo* terimlerinin kullanımı aklınızı karıştırabilir. Veri modeline bir OData (açık veri Protokolü) akışı aracılığıyla erişilebilir. OData evreninde tablo olarak bilinen öğelere Power BI’da varlık adı verilir. Her iki terim de aslında aynı olup verilerinizi taşıyan şeye verilen addır. OData hakkında daha fazla bilgi için bkz. [OData 'e genel bakış](/odata/overview).

## <a name="install-power-bi-desktop"></a>Power BI Desktop’ı yükleme

En yeni Power BI Desktop sürümünü yükleyin. Power BI Desktop’ı şu adresten indirebilirsiniz: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Kiracınız için Intune Veri Ambarı OData akışına bağlanma

> [!Note]  
> Intune’da **Raporlar** izniniz olmalıdır. Daha fazla bilgi için bkz. [Yetkilendirme](../reports-api-url.md).

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Microsoft Intune-genel bakış** dikey penceresinin sağ tarafındaki **diğer görevler** altında bulunan veri ambarı bağlantısını seçerek **Intune veri ambarı** bölmesini açın.
3. Özel akış URL’sini kopyalayın. Örneğin: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
4. Power BI Desktop’ı açın.
5. Menü çubuğundan **dosya** > **veri al** > **OData akışı**' nı seçin.
6. Önceki adımdan kopyaladığınız özel akış URL 'sini **OData akış** penceresindeki URL kutusuna yapıştırın.
7. **Temel**’i seçin.

    ![Kiracınız için Intune veri ambarı için OData akışı](./media/reports-proc-create-with-odata/reports-create-01-odatafeed.png)

8. **Tamam**’ı seçin.
9. **Kuruluş hesabı**’nı seçin ve Intune kimlik bilgilerinizle oturum açın.

    ![Kuruluş hesabı kimlik bilgileri](./media/reports-proc-create-with-odata/reports-create-02-org-account.png)

10. **Bağlan**’ı seçin. Gezgin açılacak ve size Intune Veri Ambarı’ndaki tabloların listesini gösterecektir.

    ![Gezgin 'in ekran görüntüsü-veri ambarı tablolarının listesi](./media/reports-proc-create-with-odata/reports-create-02-loadentities.png)

11. **cihazlar** ve **ownerTypes** tablolarını seçin.  **Yükle**’yi seçin. Power BI modele veri yükler.

## <a name="create-a-relationship"></a>Bir ilişki oluşturma

Çözümlemek için birden fazla tabloyu içeri aktarabilirsiniz, yani yalnızca bir tablodaki verileri değil, farklı tablolardaki ilişkili verileri alabilirsiniz. Power BI, sizin için ilişkileri bulmayı ve oluşturmayı deneyen **Otomatik Algıla** adlı bir özelliğe sahiptir. Veri ambarındaki tablolar, Power BI Otomatik Algıla özelliği ile çalışacak şekilde oluşturulmuştur. Ancak Power BI ilişkileri otomatik olarak bulamazsa, ilişkileri yine de yönetmeye devam edebilirsiniz.

![Tablolar arasında ilgili verilerin ilişkilerini yönetme](./media/reports-proc-create-with-odata/reports-create-03-managerelationships.png)

1. **İlişkileri Yönet**’i seçin.
2. Power BI zaten ilişki algılamıyorsa **otomatik algıla...** seçeneğini belirleyin.

İlişki, Kaynak ve Hedef sütunlarında görüntülenir. Bu örnekte **cihazlar** tablosundaki **ownerTypeKey** veri alanı, **ownerTypes** tablosundaki **ownerTypeKey** veri alanına bağlantı sağlar. **Cihazlar** tablosundaki cihaz türü kodunun düz adını aramak için ilişkiyi kullanırsınız.

## <a name="create-a-treemap-visualization"></a>Ağaç haritası görselleştirmesi oluşturma

Ağaç Haritası grafiği, hiyerarşik verileri kutular içindeki kutular olarak gösterir. Hiyerarşinin her bir dalında kutular bulunur. Bu kutular ise alt dalları gösteren daha küçük kutular barındırır. Intune kiracı verilerinizin bir ağaç haritasını oluşturmak için Power BI Masaüstü 'nü kullanarak, cihaz üreticisi türlerinin göreli miktarları gösterilmektedir.

![Power BI ağaç Haritası görselleştirmeleri](./media/reports-proc-create-with-odata/reports-create-03-treemap.png)

1. **Görsel öğeler** bölmesinde, **ağaç Haritası**' nı bulup seçin. **Treemap** grafiği rapor tuvaline eklenecektir.
2. **Alanlar** bölmesinde `devices` tablosunu bulun.
3. `devices` tablosunu genişletin ve `manufacturer` veri alanını seçin.
4. `manufacturer` veri alanını rapor tuvaline sürükleyin ve **treemap** grafiğine bırakın.
5. `deviceKey` veri alanını `devices` tablosundan **görsel öğeler** bölmesine sürükleyin ve **veri alanı Ekle**etiketli kutudaki **değerler** bölümünün altına bırakın.  

Artık kuruluşunuzdaki cihaz üreticileri dağılımını gösteren bir görseliniz var.

![Verilerle ağaç Haritası-cihazların üreticilerinin dağılımı](./media/reports-proc-create-with-odata/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Bir filtre ekleme

Uygulamanızı kullanarak ilave sorular yanıtlayabilmek için ağaç haritanıza bir filtre ekleyebilirsiniz.

1. Bir filtre eklemek için, rapor tuvali ' ni seçin ve ardından **görsel öğeler**altında **dilimleyici simgesini** (veri modeliyle![treemap ve desteklenen ilişkiler](./media/reports-proc-create-with-odata/reports-create-slicer.png)) seçin. Boş **dilimleyici** görselleştirmesi tuvalde görünür.
2. **Alanlar** bölmesinde `ownerTypes` tablosunu bulun.
3. `ownerTypes` tablosunu genişletin ve `ownerTypeName` veri alanını seçin.
4. `onwerTypeName` veri alanını `ownerTypes` tablosundan **Filtreler** bölmesine sürükleyin ve **Bu sayfadaki filtreler** altında **veri alanları Ekle**etiketli kutuda bu sayfaya bırakın.  

   `OwnerTypes` tablosu altında, bir cihazın şirkete ait veya kişisel olup olmadığı gibi bir veri içeren `OwnerTypeKey`adlı bir veri alanı bulunur. Bu filtrede kolay adlar göstermek istediğinizden bu yana `ownerTypes` tablosunu bulun ve **ownerTypeName** öğesini dilimleyiciye sürükleyin. Bu örnek, veri modelinin tablolar arasındaki ilişkiyi nasıl desteklediğini gösterir.

![Filter ile treemap-tablolar arasındaki ilişkileri destekler](./media/reports-proc-create-with-odata/reports-create-08_ownertype.png)

Artık şirkete ait ve kişisel cihazlar arasında geçiş yapmak üzere kullanılacak bir filtreniz var. Dağılımın nasıl değiştiğini görmek için bu filtreyi kullanın.

1. Şirkete ait cihaz dağıtımına sahip olduğunu görmek için Dilimleyicinin içindeki **Şirket** ' ı seçin.
2. Kişisel cihazları görmek için Dilimleyicinin içinden **Kişisel** ' i seçin.

## <a name="next-steps"></a>Sonraki adımlar

- Power BI Desktop’ta [ilişki oluşturma ve yönetme](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) hakkında Power BI belgelerinden daha fazla bilgi edinin.
- [Intune Veri Ambarı](reports-ref-data-model.md)’na başvurun.
