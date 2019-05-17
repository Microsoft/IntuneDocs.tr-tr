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
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59899712"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Power BI ile Veri Ambarına bağlanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Power BI Uyumluluğu uygulamasını kullanarak Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yükleyebilirsiniz. Ayrıca OData bağlantısını kullanarak kiracı verilerinizi Power BI'a yükleyebilirsiniz. Intune, kiracınızın bağlantı ayarlarını kiracınıza ileterek şunlarla ilgili örnek raporları ve grafikleri görüntülemenizi sağlar:  

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

En yeni [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi) sürümünü yükleyin. Daha fazla bilgi için bkz. [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Power BI Intune Uyumluluğu Veri Ambarı Uygulamasını kullanarak verileri ve raporları yükleme

Power BI [Intune Uyumluluğu Veri Ambarı uygulaması](https://aka.ms/intune/datawarehouseapi/getpowerbiapp), kiracınızın bağlantısı bilgisini ve Veri Ambarı veri modeline bağlı olarak önceden oluşturulmuş bir raporlar kümesini barındırır.

1.  Yükleme işlemini başlatmak için [Intune Uyumluluğu Veri Ambarı uygulaması](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) sayfasına gidin.
2.  Güvenilen kaynaklar tarafından sağlanan Power BI uygulamasını yüklemek isteyip istemediğiniz sorulduğunda **Yükle**'ye tıklayın.
3.  **Intune Uyumluluğu Veri Ambarı Uygulaması** kutucuğuna tıklayın.
4.  **Verilere bağlan** düğmesine tıklayın. 
    **Intune Uyumluluğu Veri Ambarı Uygulamasına Bağlan** iletişim kutusu görüntülenir.
5.  **Oturum aç** düğmesine tıklayın.
6.  Görüntülemek istediğiniz raporların bulunduğu kiracının Intune Veri Ambarına erişimi olan bir kullanıcı hesabıyla oturum açın. 
7.  **Raporlar** sekmesine ve ardından **Uyumluluk V1.0** raporuna tıklayın.
8.  Bu raporlara daha sonra kolayca ulaşabilmek için **Uyumluluk V1.0** raporunun yanındaki yıldıza tıklayın. Bunu yaptığınızda rapor Power BI sık kullanılanlarınıza eklenir.

Alternatif olarak, uygulamayı Intune portalından da yükleyebilirsiniz:

1.  Azure portalında oturum açın ve **İzleme + Yönetim** > **Intune**’u seçin. Ayrıca Intune için kaynak araması da yapabilirsiniz.
2.  **Intune Veri Ambarı Ayarlama** dikey penceresini açın.
3.  Kiracınız için önceden oluşturulmuş olan Power BI raporlarına tarayıcıda erişmek ve bunları paylaşmak için **Power BI Uygulamasını edinin**'i seçin.
4.  Yukarıdaki 2-8 arası adımları izleyin.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Power BI’da OData bağlantısını kullanarak verileri yükleme

Azure AD’de istemci kimliği doğrulandığı zaman OData URL’si, Veri Ambarı API’sinde rapor istemcinizin veri modelini açığa çıkaran RESTful uç noktasına bağlanır. Bağlantı kurmak ve kendi raporlarınızı oluşturmak üzere Power BI Desktop’ı kullanmak için bu yönergeleri izleyin. Kullanabilecekleriniz yalnızca Power BI Desktop ile sınırlı değil. İstemcinin OAUTH2.0 kimlik doğrulama ve OData v4.0 standardı destekliyor olması kaydıyla OData ile URL ile en sevdiğiniz analiz aracını kullanabilirsiniz.

1.  Azure portalında oturum açın ve **İzleme + Yönetim** > **Intune**’u seçin. Ayrıca **Intune** için kaynak araması da yapabilirsiniz.  
2.  **Intune Veri Ambarı Ayarlama** dikey penceresini açın.
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

Geçen hafta içerisinde günde kaç cihazın kaydedildiği gibi ortamınızla ilgili sorulara yanıt bulabilirsiniz. Azure’da bulunan dikey pencereden alınan Intune Veri Ambarı Power BI raporlarını kullanarak Intune kiracınız ve istemci popülasyonunuz hakkında içgörülere ulaşabilirsiniz. Ancak Intune, verileri genişletmek veya yeniden kullanmak için ilave birkaç yol daha sunar. Power BI ve Intune Veri Ambarı API'si ek işlevler sağlar, örneğin:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Kiracı verileriniz, verilerinizden öngörü almanıza yardımcı olacak şekilde düzenlenir. Verilerin nasıl düzenlendiği hakkında daha fazla bilgi için bkz. [Veri Ambarı Veri Modeli](reports-ref-data-model.md).
 -  Verilere ayrıca RESTful arabiriminden erişebilir ve verileri kendi uygulamanıza ekleyebilirsiniz. Daha fazla bilgi için bkz. [Bir REST istemcisi ile Veri Ambarı API’sinden veri alma](reports-proc-data-rest.md).
