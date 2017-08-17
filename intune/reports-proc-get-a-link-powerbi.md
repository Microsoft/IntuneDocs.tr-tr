---
title: "Power BI ile Veri Ambarına bağlanma | Microsoft Docs"
description: "Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemenizi mümkün kılan bir dosyayı Microsoft Power BI ile kullanmak üzere indirebilirsiniz."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b70bf3410e20dd792c0fcff050292ddea714d63e
ms.sourcegitcommit: 99ffed621855357de427d6fdf7b70d4e543197e9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Power BI ile Veri Ambarına bağlanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemenizi mümkün kılan bir dosyayı Microsoft Power BI ile kullanmak üzere indirebilirsiniz. Veri Ambarı Power BI dosyası (pbix) kiracınız için bağlantı ayarlarını ve aşağıdaki rapor ve grafik örneklerini barındırır:  

  -  Cihazlar
  -  Kayıt
  -  Uygulama koruma ilkesi
  -  Uyumluluk ilkesi
  -  Cihaz yapılandırma profilleri
  -  Yazılım güncelleştirmeleri
  -  Cihaz envanter günlükleri

Ayrıca kayıt, uyumluluk, cihaz yapılandırma profili ve yazılım güncelleştirmeleri için vurgulanan eğilimler de vardır. Örnek grafikler ve raporlar, tuvale kullanıcı dostu filtreler uygular. Gelişmiş filtreler kullanmak için Power BI Desktop’taki **Filtre** panosuna bakın. 

Aşağıdaki adımlar, Power BI dosyasını nasıl indireceğinizi ve OData bağlantısını Power BI ile nasıl kullanacağınızı gösterir.

## <a name="install-power-bi"></a>Power BI yükleme

En yeni Power BI Desktop sürümünü yükleyin. Power BI Desktop’ı şu adresten indirebilirsiniz: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) 

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Power BI dosyasını (pbix) kullanarak verileri ve raporları yükleme

Power BI dosyası (pbix), kiracınızın bağlantısı bilgisini ve Veri Ambarı veri modeline bağlı olarak önceden oluşturulmuş bir raporlar kümesini barındırır. Dosyayı Power BI Desktop’ta açın ve Azure AD’de oturum açın. Rapor, Intune kiracınızdan verileri yükler.

> [!Important]  
> Her Power BI dosyası (pbix) kiracı konumuna bağlı olarak farklı olabilir. Birden çok Intune kiracısı yönetiyorsanız, bu kiracı için oturum açık durumdayken Azure portalından indirilen dosyayı kullandığınızdan emin olun.  

1.  Azure portalında oturum açın ve **İzleme + Yönetim** > **Intune**’u seçin. Ayrıca **Intune** için kaynak araması da yapabilirsiniz.  
2.  **Microsoft Intune Veri Ambarı API’si (Önizleme)** dikey penceresini açın.
3.  **Power BI dosyasını indir**’e tıklayın. (pbix) uzantılı dosya, belirttiğiniz konuma indirme yapar.
4.  Dosyayı Power BI ile açın. *Intune Veri Ambarı Raporları* yüklenir ancak kiracı verilerinizi alması birkaç saniye sürebilir.
5.  Kiracı verilerinizi yüklemek için **Yenile**’ye tıklayın ve raporları gözden geçirin.
6.  Power BI’da Azure Active Directory kimlik bilgilerinizle kimlik doğrulamadıysanız, Power BI sizden kimlik bilgilerinizi sağlamanızı ister. Kimlik bilgilerinizi seçerken kimlik doğrulama yöntemi olarak **Kuruluş hesabı**’nı seçin.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Power BI’da OData bağlantısını kullanarak verileri yükleme

Azure AD’de istemci kimliği doğrulandığı zaman OData URL’si, Veri Ambarı API’sinde rapor istemcinizin veri modelini açığa çıkaran RESTful uç noktasına bağlanır. Bağlantı kurmak ve kendi raporlarınızı oluşturmak üzere Power BI Desktop’ı kullanmak için bu yönergeleri izleyin. Kullanabilecekleriniz yalnızca Power BI Desktop ile sınırlı değil. İstemcinin OAUTH2.0 kimlik doğrulama ve OData v4.0 standardı destekliyor olması kaydıyla OData ile URL ile en sevdiğiniz analiz aracını kullanabilirsiniz.

1.  Raporlama dikey penceresinden **OData URL’sini** alın, örneğin `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
2.  **Power BI Desktop**’ı açın.
3.  **Giriş** > **Veri Al**’ı seçin. **OData akışı**’nı seçin.
4.  **Temel**’i seçin.
5.  URL kutusuna **OData URL’sini** yazın veya yapıştırın.
6.  **Tamam**’a tıklayın.
7.  Power BI Desktop istemcisinden Azure AD’de kiracınızın kimliğini doğrulamadıysanız, kimlik bilgilerinizi girin.  
    a.  **Kuruluş hesabını** seçin.  
    b.  Kullanıcı adınızı ve parolanızı yazın.  
    c.  **Oturum Aç**’a tıklayın.  
    d.  **Bağlan**'a tıklayın.  
8.  **Yükle**’ye tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

Geçen hafta içerisinde günde kaç cihazın kaydedildiği gibi ortamınızla ilgili sorulara yanıt bulabilirsiniz. Azure’da bulunan dikey pencereden alınan Intune Veri Ambarı Power BI dosyasını kullanarak Intune kiracını ve istemci popülasyonunuz hakkında öngörü edinebilirsiniz. Ancak Intune, verileri genişletmek veya yeniden kullanmak için ilave birkaç yol daha sunar. Power BI ve Intune Veri Ambarı API’si ile yapabileceğiniz daha pek çok şey vardır, örneğin:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Kiracı verileriniz, verilerinizden öngörü almanıza yardımcı olacak şekilde düzenlenir. Verilerin nasıl düzenlendiği hakkında daha fazla bilgi için bkz. [Veri Ambarı Veri Modeli](reports-ref-data-model.md). 
<!-- -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md). -->