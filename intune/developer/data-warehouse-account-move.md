---
title: Intune Veri Ambarı hesabı verilerinizi taşıma
titleSuffix: Microsoft Intune
description: Hesabınızı taşırken Intune Veri Ambarı verilerinizi yedeklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ee3ccbf9-82fc-4fbf-9d3d-8f05e431d090
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: bbf9944411776e5d6f47aa59116806a0a703ce4c
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813390"
---
# <a name="move-your-intune-data-warehouse-account-data"></a>Intune Veri Ambarı hesabı verilerinizi taşıma 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir hesap taşıması istediğiniz, veri merkezinizin başka bir konuma alınmasını istemiş olursunuz. Taşıma sonrası Veri Ambarınız sıfırlanır ve belirtilen taşıma başlangıç gününe bağlı olarak yeni konumda veri kaydetmeye başlar. Önceki Veri Ambarı verilerinizi yedeklemek için lütfen hesabınızı taşımadan **önce** aşağıdaki adımları tamamlayın. Çoğu Veri Ambarı tablosu, 30 gün boyunca veriler saklar. Bu nedenle bu tablolardaki herhangi bir veri boşluğu, hesabınız taşındıktan 30 gün sonra kullanılabilir olmayacaktır. Belirli tablolar için bekletme aralığı hakkında daha fazla bilgi için bkz. [Veri Ambarı veri modeli](reports-ref-data-model.md). 

## <a name="back-up-your-data-warehouse-data"></a>Veri Ambarı verilerinizi yedekleme 

Veri Ambarı verilerinizi yedeklemek için Veri Ambarı verilerinizi, Veri Ambarı API’sini kullanarak bir *.csv* dosyası olarak kaydetmeniz gerekir:  

1. Veri Ambarı API’sini ilk kez kullanıyorsanız, [Bir REST istemcisi ile Intune Veri Ambarı API’sinden veri alma](reports-proc-data-rest.md) makalesinde sağlanan tek seferlik işlemi izleyin.
2. [Intune Veri Ambarı’na PowerShell ile erişme](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/PowerShell) başlıklı PowerShell örneğini kullanarak tüm verilerinizi CSV dosyalarına indirin. 

## <a name="back-up-your-trend-charts-from-the-azure-portal"></a>Azure portalındaki eğilim grafiklerinizi yedekleme

Azure portalı görünümünüzdeki bazı eğilim grafikleri sıfırlanacaktır. **Graph**’ta şu betiği çalıştırarak bu grafikleri yedekleyebilirsiniz:   

### <a name="terms--conditions-acceptance-reports"></a>Hüküm ve Koşulların Kabulü raporları
1. Azure portalında **Microsoft Intune** -> **Cihaz Kaydı** -> **Hüküm ve Koşullar**’a gidin.
2. Her bir **Hüküm ve Koşullar** öğesi için **Kabul Raporu** ve ardından **Dışarı Aktar**’ı seçin.
3. Raporu yerel olarak kaydedin.
 
### <a name="app-protection-reports"></a>Uygulama Koruma raporları  
1. Azure portalında **Microsoft Intune** -> **İstemci Uygulamaları** -> **Uygulama koruma durumu**’na gidin.
2. Her bir raporu kaydetmek için indirme simgesine ( ⤓ ) tıklayın.

### <a name="device-configuration-charts"></a>Cihaz Yapılandırma grafikleri 
1. Azure portalında **Microsoft Intune** -> **Cihaz Yapılandırması**’na gidin.
2. Microsoft [Graph Gezgini](https://developer.microsoft.com/graph/graph-explorer)’ni kullanarak grafiklerdeki verileri indirin. 
    - Tüm cihazlardaki cihaz yapılandırma profillerinin dağıtım durumları için bkz. [Cihaz dağıtım durumu](https://graph.microsoft.com/beta/reports/deviceConfigurationDeviceActivity/content).

    - Tüm kullanıcıların cihaz yapılandırma profillerinin dağıtım durumları için bkz. [Kullanıcı dağıtım durumu](https://graph.microsoft.com/beta/reports/deviceConfigurationUserActivity/content).

    - Profil dağıtım durumu için bkz. [Dağıtım durumu sağlama](https://graph.microsoft.com/beta/deviceManagement/deviceConfigurations?$select=id,displayName,lastModifiedDateTime,deviceStatusOverview&$expand=deviceStatusOverview).
  
    > [!NOTE]
    > Cihaz yapılandırması ve dağıtım durumu bilgilerine erişmek için geçerli bir kimlik doğrulaması belirteciniz olmalıdır.

## <a name="device-enrollment-charts"></a>Cihaz Kayıt grafikleri
1. Azure portalında **Microsoft Intune** -> **Cihaz Kaydı**’na gidin.
2. Microsoft [Graph Gezgini](https://developer.microsoft.com/graph/graph-explorer)’ni kullanarak grafiklerdeki verileri indirin.
    - Kayıt durumu için bu [kayıt durumu sorgusunu](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentFailureTrends()/content) kopyalayın ve [Graph Gezgini](https://developer.microsoft.com/graph/graph-explorer)’ne yapıştırın.
    - Bu haftanın en sık görülen kayıt hataları için bu [kayıt hataları sorgusunu](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentTopFailures(period=null)/content) kopyalayın ve [Graph Gezgini](https://developer.microsoft.com/graph/graph-explorer)’ne yapıştırın.

    > [!NOTE]
    > Cihaz kayıt verilerine erişmek için geçerli bir kimlik doğrulaması belirteciniz olmalıdır. 

## <a name="after-a-data-warehouse-account-move"></a>Bir Veri Ambarı taşıması sonrasında

Veri Ambarı hesabı taşındıktan sonra, Intune’da Veri Ambarı’nın sıfırlandığını ve verilerinizin yeni konumda depolandığını görürsünüz. Grafikleri ve dışarı aktarma seçenekleri sıfırlanır ve tıkladığınızda grafiklerin neden sıfırlandığını açıklayan makaleye giden bir bildirim alırsınız.  

## <a name="data-warehouse-move-example"></a>Veri Ambarı taşıma örneği 

X müşterisi, hesap taşımasının 1.06.2018 tarihinde başlamasını ister. Bu isteğe yanıt olarak müşteri, önceki Veri Ambarı verilerini yedeklemek istemesi halinde gerekli adımları ayrıntılı olarak açıklayan belgeleri bulacağı bir bağlantı alır. 1\.06.2018 tarihinde Veri Ambarı ve ambarın desteklediği grafikler sıfırlanır ve yeni veri merkezinde veri depolamaya başlar. 

## <a name="next-steps"></a>Sonraki adımlar

- [Intune’daki haftalık yenilikleri](../fundamentals/whats-new.md) öğrenin. Yaklaşan değişiklikler, hizmet hakkında önemli bildirimler ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.
- [Microsoft Intune Blogu](https://go.microsoft.com/fwlink/?LinkID=273882)’nu okuyun.
