---
title: Power BI ile Veri Ambarına bağlanma
titlesuffix: Microsoft Intune
description: Microsoft Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemenizi mümkün kılan bir dosyayı Microsoft Power BI ile kullanmak üzere indirebilirsiniz.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ac71716ed09e39817743ebe4301c08a898e8f41f
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Power BI ile Veri Ambarına bağlanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Power BI yükleme

En yeni Power BI Desktop sürümünü yükleyin. Power BI Desktop’ı şu adresten indirebilirsiniz: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

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

1.  Azure portalında oturum açın ve **İzleme + Yönetim** > **Intune**’u seçin. Ayrıca **Intune** için kaynak araması da yapabilirsiniz.  
2.  **Microsoft Intune Veri Ambarı API’si (Önizleme)** dikey penceresini açın.
3. Raporlama dikey penceresinden özel akış URL’sini alın, örneğin `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4. **Power BI Desktop**’ı açın.
5. **Giriş** > **Veri Al**’ı seçin. **OData akışı**’nı seçin.
6. **Temel**’i seçin.
7. URL kutusuna **OData URL’sini** yazın veya yapıştırın.
8. **Tamam**’ı seçin.
9. Power BI Desktop istemcisinden Azure AD’de kiracınızın kimliğini doğrulamadıysanız, kimlik bilgilerinizi girin. Verilerinize erişim kazanmak için OAuth 2.0 kullanarak Azure Active Directory’de (Azure AD) yetkilendirilmeniz gerekir.  
    1.  **Kuruluş hesabını** seçin.  
    2.  Kullanıcı adınızı ve parolanızı yazın.  
    3.  **Oturum aç**’ı seçin.  
    4.  **Bağlan**’ı seçin.  
10. **Yükle**’yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

Geçen hafta içerisinde günde kaç cihazın kaydedildiği gibi ortamınızla ilgili sorulara yanıt bulabilirsiniz. Azure’da bulunan dikey pencereden alınan Intune Veri Ambarı Power BI dosyasını kullanarak Intune kiracını ve istemci popülasyonunuz hakkında öngörü edinebilirsiniz. Ancak Intune, verileri genişletmek veya yeniden kullanmak için ilave birkaç yol daha sunar. Power BI ve Intune Veri Ambarı API’si ile yapabileceğiniz daha pek çok şey vardır, örneğin:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Kiracı verileriniz, verilerinizden öngörü almanıza yardımcı olacak şekilde düzenlenir. Verilerin nasıl düzenlendiği hakkında daha fazla bilgi için bkz. [Veri Ambarı Veri Modeli](reports-ref-data-model.md).
 -  Verilere ayrıca RESTful arabiriminden erişebilir ve verileri kendi uygulamanıza ekleyebilirsiniz. Daha fazla bilgi için bkz. [Bir REST istemcisi ile Veri Ambarı API’sinden veri alma](reports-proc-data-rest.md).
