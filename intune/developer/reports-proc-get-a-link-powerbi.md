---
title: Power BI ile veri ambarına bağlanma
titleSuffix: Microsoft Intune
description: Microsoft Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemenize olanak sağlayan Microsoft Power BI ile kullanmak üzere bir dosyayı indirebilirsiniz.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e8fadb625073af2a70d605d3ceabb9ba97906ae
ms.sourcegitcommit: 46322ca7a92971e18dc0b230f436b9ca892b90c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72008326"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Power BI ile veri ambarına bağlanma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune kiracınız için etkileşimli ve dinamik olarak oluşturulmuş raporlar yüklemek üzere Power BI uyumluluk uygulamasını kullanabilirsiniz. Ayrıca, OData bağlantısını kullanarak kiracı verilerinizi Power BI yükleyebilirsiniz. Intune, ile ilgili aşağıdaki örnek raporları ve grafikleri görüntüleyebilmeniz için kiracınıza bağlantı ayarları sağlar:  

- Cihazlarınız
- Kaydolmak
- Uygulama koruma ilkesi
- Uyumluluk ilkesi
- Cihaz yapılandırma profilleri
- Yazılım güncelleştirmeleri
- Cihaz envanter günlükleri

Ayrıca, kayıt, uyumluluk, cihaz yapılandırma profili ve yazılım güncelleştirmeleri için vurgulanan eğilimler vardır. Örnek grafikler ve raporlar, tuvale Kullanıcı dostu filtreler uygular. Gelişmiş filtreleri kullanmak için Power BI Desktop **filtre** bölmesine göz atın.

Aşağıdaki adımlarda Power BI dosyasının nasıl indirileceği ve OData bağlantısının Power BI nasıl kullanılacağı gösterilmektedir.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Power BI yüklensin

En son [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi)sürümünü yükler. Daha fazla bilgi için bkz. [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Power BI Intune uyumluluk verileri ambarı uygulamasını kullanarak verileri ve raporları yükleme

Power BI [Intune uyumluluk (veri ambarı)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) uygulaması, kiracınız için bilgiler ve veri ambarı veri modelini temel alan bir dizi önceden oluşturulmuş rapor içerir.

1. Yükleme işlemini başlatmak için [Intune uyumluluk (veri ambarı)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) uygulamasının **appsource** sayfasına gidin.
2. **Şimdi al** düğmesine tıklayın ve ardından **devam**' a tıklayın.
3. Power BI uygulamasını yüklemek isteyip istemediğiniz sorulduğunda, **yüklensin**' e tıklayın.
4. Yükleme tamamlandıktan sonra, **Intune uyumluluk (veri ambarı) uygulama kutucuğuna** tıklayın.
5. **Bağlan** düğmesine tıklayın. **Intune uyumluluğuna Bağlan (veri ambarı)** iletişim kutusu görüntülenir.
6. **Oturum aç** düğmesine tıklayın.
7. Görüntülemek istediğiniz raporlara sahip olan kiracı için Intune veri ambarına erişimi olan bir kullanıcı hesabıyla oturum açın.
8. Dahil edilen panoyu görüntülemek için **panolar** sekmesine tıklayın ve ardından **uyumluluk genel bakış** panosuna tıklayın.
9. Tüm kullanılabilir raporları görüntülemek için, **raporlar** sekmesine tıklayın ve ardından **Uyumluluk v 1.0** raporuna tıklayın. Alttaki sekmelere tıklayarak rapor sayfalarına göz atabilirsiniz.
10. Daha sonra bu raporlara geri gitmeyi kolaylaştırmak için, **Uyumluluk v 1.0** raporunun yanındaki yıldıza tıklayın. Bu, raporu Power BI sık kullanılanlarınıza ekler.

Alternatif olarak, uygulamayı Intune portalından yükleyebilirsiniz:

1. Azure portal oturum açın ve **İzleme ve Yönetim** > **Intune**' ı seçin. Ayrıca, Intune için kaynakları arayabilirsiniz.
2. **Intune veri ambarını ayarla** dikey penceresini açın.
3. Tarayıcıda kiracınızın önceden oluşturulmuş Power BI raporlarına erişmek ve bunları paylaşmak için **Power BI uygulaması al** ' ı seçin.
4. Yukarıdaki 2-10 adımlarını izleyin.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>OData bağlantısını kullanarak Power BI verileri yükleme

Azure AD 'de kimliği doğrulanmış bir istemci ile OData URL 'SI, veri ambarını raporlama istemcinize sunan veri ambarı API 'sindeki yeniden bağlantı noktasına bağlanır. Kendi raporlarınızı bağlamak ve oluşturmak için Power BI Desktop kullanmak için bu yönergeleri izleyin. Power BI Desktop sınırlı değildir ancak istemci, OAUTH 2.0 kimlik doğrulamasını ve OData v 4.0 standardını desteklediği için OData URL 'SI ile en sevdiğiniz analitik aracı kullanabilirsiniz.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. Genel Bakış dikey penceresinin sağ tarafındaki **diğer görevler** bölümünde **Intune veri ambarını ayarla** ' ya tıklayın. **Intune veri ambarı** dikey penceresi görüntülenir.
3. Raporlama dikey penceresinden özel akış URL 'sini alın, örneğin:<br>
    `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
4. **Power BI Desktop**açın.
5. **Dosya** > **veri al**' ı seçin. **OData akışı**' nı seçin.
6. **Temel**öğesini seçin.
7. **OData URL** 'sini URL kutusuna yazın veya yapıştırın.
8. **Tamam ' ı**seçin.
9. Power BI masaüstü istemcisinden kiracınız için Azure AD 'de kimlik doğrulaması yapmadıysanız, kimlik bilgilerinizi yazın. Verilerinize erişim kazanmak için, OAuth 2,0 kullanarak Azure Active Directory (Azure AD) ile yetkilendirmelisiniz.  
    1. **Kuruluş hesabı**' nı seçin.  
    2. Kullanıcı adınızı ve parolanızı yazın.  
    3. **Oturum aç '** ı seçin.  
    4. **Bağlan**' ı seçin.  
10. **Yükle**' yi seçin.

## <a name="next-steps"></a>Sonraki adımlar

Ortamınız ile ilgili soruların yanıtlarını, son hafta içinde güne göre kaydedilen cihazların sayısı gibi bulabilirsiniz. Azure 'daki dikey pencereden alınan Intune veri ambarı Power BI raporlarını kullanarak Intune kiracınız ve istemci popülasyonu hakkında öngörüler elde edebilirsiniz. Ancak, Intune verileri uzatmak veya yeniden kullanmak için bir dizi ek yol sağlar. Power BI ve Intune veri ambarı API 'SI, ek işlevsellik sağlar, örneğin:

<!-- - You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
- Kiracınızın verileri, verilerinize ilişkin Öngörüler almanıza yardımcı olacak şekilde düzenlenmiştir. Verilerin nasıl düzenlendiği hakkında daha fazla bilgi için bkz. [veri ambarı veri modeli](reports-ref-data-model.md).
- Ayrıca, bir yeniden oluşturma arabiriminden verilere erişebilir ve verileri kendi uygulamanıza ekleyebilirsiniz. Daha fazla bilgi için bkz. [BIR Rest istemcisi Ile veri AMBARı API 'sinden veri edinme](../reports-proc-data-rest.md).
