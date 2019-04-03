---
title: Power BI ile Veri Ambarına bağlanma
titleSuffix: Microsoft Intune
description: Microsoft Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemenizi mümkün kılan bir dosyayı Microsoft Power BI ile kullanmak üzere indirebilirsiniz.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 259d700d04547a801b0ebc37242dacf536ad61d3
ms.sourcegitcommit: 79baf89e4a7a7b1cecb8ccf5cb976736ae6a7286
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58871387"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Power BI ile Veri Ambarına bağlanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Power BI uyumluluğu uygulama, Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemenizi için kullanabilirsiniz. Ayrıca, Kiracı verilerinizi Power bı'da OData bağlantısını kullanarak yükleyebilirsiniz. Aşağıdaki örnek raporları ve ilgili grafikler görüntüleyebilmek Intune kiracınız için bağlantı ayarlarını sağlar:  

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

En son sürümünü yükleyin [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). Daha fazla bilgi için [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Power BI Intune uyumluluk veri ambarı uygulaması'nı kullanarak rapor ve veri yükleme

Power BI [Intune uyumluluk veri ambarı uygulaması](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) kiracınızın ve önceden oluşturulmuş raporları veri ambarı veri modelini temel alan bir dizi ilgili bilgileri içerir.

1.  Gidin [Intune uyumluluk veri ambarı uygulaması](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) yükleme işlemini başlatın.
2.  Güvenilen kaynaklardan gelen Power BI uygulamasını yüklemek için sorulduğunda **yükleme**.
3.  Tıklayarak **Intune uyumluluk veri ambarı uygulaması** Döşe.
4.  Tıklayın **verilere** düğmesi. 
    **Intune uyumluluk veri ambarı uygulaması Bağlan** iletişim kutusu görüntülenir.
5.  Tıklayın **oturum** düğmesi.
6.  Intune veri ambarı'na sahip bir kiracı için erişimi olan bir kullanıcı hesabıyla oturum açın, görüntülemek istediğiniz bildirir. 
7.  Tıklayın **raporları** sekmesine ve ardından tıklayın **uyumluluk V1.0** rapor.
8.  Daha sonra bu raporlara geri gitmek kolaylaştırmak için yanındaki Yıldıza tıklayın **uyumluluk V1.0** rapor. Bu raporu Power BI sık kullanılanlarınızı ekler.

Alternatif olarak, Intune Portalı'ndan uygulama yükleyebilirsiniz:

1.  Azure portalında oturum açın ve **İzleme + Yönetim** > **Intune**’u seçin. Intune için kaynakları arama da yapabilirsiniz.
2.  Açık **Intune veri ambarı ayarlama** dikey penceresi.
3.  Seçin **Al Power BI uygulaması** erişmek ve tarayıcıdaki kiracınız için önceden oluşturulmuş Power BI raporlarını paylaşma.
4.  Adım 2-yukarıdaki 8 izleyin.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Power BI’da OData bağlantısını kullanarak verileri yükleme

Azure AD’de istemci kimliği doğrulandığı zaman OData URL’si, Veri Ambarı API’sinde rapor istemcinizin veri modelini açığa çıkaran RESTful uç noktasına bağlanır. Bağlantı kurmak ve kendi raporlarınızı oluşturmak üzere Power BI Desktop’ı kullanmak için bu yönergeleri izleyin. Kullanabilecekleriniz yalnızca Power BI Desktop ile sınırlı değil. İstemcinin OAUTH2.0 kimlik doğrulama ve OData v4.0 standardı destekliyor olması kaydıyla OData ile URL ile en sevdiğiniz analiz aracını kullanabilirsiniz.

1.  Azure portalında oturum açın ve **İzleme + Yönetim** > **Intune**’u seçin. Ayrıca **Intune** için kaynak araması da yapabilirsiniz.  
2.  Açık **Intune veri ambarı ayarlama** dikey penceresi.
3. Raporlama dikey penceresinden özel akış URL’sini alın, örneğin `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
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

Geçen hafta içerisinde günde kaç cihazın kaydedildiği gibi ortamınızla ilgili sorulara yanıt bulabilirsiniz. Dikey pencerede Azure hizmetinden alınan Intune veri ambarı Power BI raporlarını kullanarak, Intune kiracını ve istemci popülasyon öngörü elde edebilirsiniz. Ancak Intune, verileri genişletmek veya yeniden kullanmak için ilave birkaç yol daha sunar. Power BI ve Intune veri ambarı API'si ek işlevler, örneğin sağlar:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Kiracı verileriniz, verilerinizden öngörü almanıza yardımcı olacak şekilde düzenlenir. Verilerin nasıl düzenlendiği hakkında daha fazla bilgi için bkz. [Veri Ambarı Veri Modeli](reports-ref-data-model.md).
 -  Verilere ayrıca RESTful arabiriminden erişebilir ve verileri kendi uygulamanıza ekleyebilirsiniz. Daha fazla bilgi için bkz. [Bir REST istemcisi ile Veri Ambarı API’sinden veri alma](reports-proc-data-rest.md).
