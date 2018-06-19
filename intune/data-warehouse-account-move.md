---
title: Intune Veri Ambarı hesabı verilerinizi taşıma
titlesuffix: Microsoft Intune
description: Hesabınızı taşırken Intune Veri Ambarı verilerinizi yedeklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ee3ccbf9-82fc-4fbf-9d3d-8f05e431d090
ms.reviewer: aanavath
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: f1b2af2723ddb4c89f7f3d6409ced12f7a16883a
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223671"
---
# <a name="move-your-intune-data-warehouse-account-data"></a>Intune Veri Ambarı hesabı verilerinizi taşıma 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
1. Azure portalında **Microsoft Intune** -> **Mobil Uygulamalar** -> **Uygulama koruma durumu**’na gidin.
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
    - Kayıt durumu için bkz. 
    - Bu haftanın en sık görülen kayıt hataları için 
    - Kayıt durumu için bu [kayıt durumu sorgusunu](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentFailureTrends()/content) kopyalayın ve [Graph Gezgini](https://developer.microsoft.com/graph/graph-explorer)’ne yapıştırın.
    - Bu haftanın en sık görülen kayıt hataları için bu [kayıt hataları sorgusunu](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentTopFailures(period=null)/content) kopyalayın ve [Graph Gezgini](https://developer.microsoft.com/graph/graph-explorer)’ne yapıştırın.

    > [!NOTE]
    > Cihaz kayıt verilerine erişmek için geçerli bir kimlik doğrulaması belirteciniz olmalıdır. 

## <a name="after-a-data-warehouse-account-move"></a>Bir Veri Ambarı taşıması sonrasında

Veri Ambarı hesabı taşındıktan sonra, Intune’da Veri Ambarı’nın sıfırlandığını ve verilerinizin yeni konumda depolandığını görürsünüz. Grafikleri ve dışarı aktarma seçenekleri sıfırlanır ve tıkladığınızda grafiklerin neden sıfırlandığını açıklayan makaleye giden bir bildirim alırsınız.  

## <a name="data-warehouse-move-example"></a>Veri Ambarı taşıma örneği 

X müşterisi, hesap taşımasının 1.06.2018 tarihinde başlamasını ister. Bu isteğe yanıt olarak müşteri, önceki Veri Ambarı verilerini yedeklemek istemesi halinde gerekli adımları ayrıntılı olarak açıklayan belgeleri bulacağı bir bağlantı alır. 1.06.2018 tarihinde Veri Ambarı ve ambarın desteklediği grafikler sıfırlanır ve yeni veri merkezinde veri depolamaya başlar. 

## <a name="next-steps"></a>Sonraki adımlar

 - [Intune’daki haftalık yenilikleri](whats-new.md) öğrenin. Yaklaşan değişiklikler, hizmet hakkında önemli bildirimler ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.
 - [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)’nu okuyun.
