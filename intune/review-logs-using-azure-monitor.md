---
title: Azure izleyici 'de Microsoft Intune-Azure kullanarak denetim günlüklerini yönlendirme | Microsoft Docs
description: Azure depolama hesabı, Olay Hub 'ları veya Log Analytics 'e Microsoft Intune denetim günlükleri ve işletimsel Günlükler göndermek için tanılama ayarlarını kullanın. Verileri ne kadar süreyle saklamak istediğinizi seçin ve farklı boyuttaki kiracılar için bazı tahmini maliyetleri görüntüleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d95b37d18fa609f1c4e98d4fad5cfa600333b90a
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68354529"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Intune 'da günlük verilerini depolama, Olay Hub 'ları veya Log Analytics 'e gönderme (Önizleme)

Microsoft Intune, ortamınız hakkında bilgi sağlayan yerleşik günlükleri içerir. **Denetim günlükleri** , Intune 'da gerçekleşen farklı olay veya görevlerle ilgili ayrıntıları gösterir. **Işletimsel Günlükler (Önizleme)** , aynı zamanda (veya başarısız), uyumlu olmayan cihazların ayrıntılarını ve kaydolmasını sağlayan kullanıcılar ve cihazlar hakkındaki ayrıntıları gösterir.

Bu Günlükler, depolama hesapları, Olay Hub 'ları ve Log Analytics de dahil olmak üzere Azure Izleyici hizmetlerine de gönderilebilir. Özellikle şunları yapabilirsiniz:

* Verileri korumak için Intune günlüklerini bir Azure depolama hesabına arşivleyin veya bir süre için arşivleme yapın.
* Intune 'U, splunk ve QRadar gibi popüler güvenlik bilgilerini ve olay yönetimi (SıEM) araçlarını kullanarak analiz için bir Azure Olay Hub 'ına kaydeder.
* Intune günlüklerini bir olay hub 'ına aktararak kendi özel günlük çözümlerinizle tümleştirin.
* Bağlantılı verilerde zengin görselleştirmeleri, izlemeyi ve uyarı vermeyi etkinleştirmek için Intune günlüklerini Log Analytics gönderin.

Bu özellikler, Intune 'da **Tanılama ayarlarının** bir parçasıdır.

Bu makalede, farklı hizmetlere günlük verileri göndermek, örnek ve maliyet tahminleri sağlamak ve bazı yaygın soruların cevapları için **Tanılama ayarlarının** nasıl kullanılacağı gösterilmektedir.

## <a name="prerequisites"></a>Önkoşullar

Bu özelliği kullanmak için şunlar gerekir:

* Bir Azure aboneliği: Azure aboneliğiniz yoksa, [ücretsiz deneme için kaydolabilirsiniz](https://azure.microsoft.com/free/).
* Azure 'da bir Microsoft Intune ortamı (kiracı)
* Intune kiracısı için **genel yönetici** veya **Intune Hizmet Yöneticisi** olan bir kullanıcı.

Denetim günlüğü verilerini yönlendirmek istediğiniz yere bağlı olarak, aşağıdaki hizmetlerden birine ihtiyacınız vardır:

* *ListKeys* izinleri olan bir [Azure depolama hesabı](https://docs.microsoft.com/azure/storage/common/storage-account-overview) . BLOB depolama hesabı değil, genel bir depolama hesabı kullanmanızı öneririz. Depolama fiyatlandırma bilgileri için bkz. [Azure Storage Fiyatlandırma hesaplayıcısı](https://azure.microsoft.com/pricing/calculator/?service=storage). 
* Üçüncü taraf çözümlerle tümleştirilecek bir [Azure Olay Hub 'ı ad alanı](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) .
* Log Analytics Günlükler göndermek için bir [Azure Log Analytics çalışma alanı](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) .

## <a name="send-logs-to-azure-monitor"></a>Günlükleri Azure izleyici 'ye gönderme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **İzleme**altında **Tanılama ayarları**' nı seçin. İlk kez açtığınızda açın:

    ![Azure Izleyici 'ye Günlükler göndermek için Intune 'da tanılama ayarlarını etkinleştirin](media/diagnostics-settings-turn-on.png)

3. Aşağıdaki özellikleri girin:

    - **Ad**: Tanılama ayarları için bir ad girin. Bu ayar, girdiğiniz tüm özellikleri içerir. Örneğin, şunu girin: `Route audit logs to storage account`.
    - **Bir depolama hesabına Arşivle**: Günlük verilerini bir Azure depolama hesabına kaydeder. Verileri kaydetmek veya arşivlemek istiyorsanız bu seçeneği kullanın.

        1. **Yapılandır**> Bu seçeneği belirleyin. 
        2. Listeden var olan bir depolama hesabını seçin > **Tamam ' ı**seçin.

    - **Bir olay hub 'ına akış**: Günlükleri bir Azure Olay Hub 'ına akıp. Günlük verilerinizde, splunk ve QRadar gibi SıEM araçlarını kullanarak analitik istiyorsanız bu seçeneği belirleyin.

        1. **Yapılandır**> Bu seçeneği belirleyin. 
        2. Listeden var olan bir olay hub 'ı ad alanını ve ilkeyi seçin > **Tamam**' ı seçin.

    - **Log Analytics gönder**: Verileri Azure Log Analytics 'e gönderir. Günlükleriniz için görselleştirmeler, izleme ve uyarı kullanmak istiyorsanız bu seçeneği belirleyin.

        1. **Yapılandır**> Bu seçeneği belirleyin. 
        2. Yeni bir çalışma alanı oluşturun ve çalışma alanı ayrıntılarını girin. Ya da listeden var olan bir çalışma alanını seçin > **Tamam**' ı seçin.

            [Azure Log Analytics çalışma alanı](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) , bu ayarlar hakkında daha fazla ayrıntı sağlar.

    - Günlük > **auditlogs**: [Intune denetim günlüklerini](monitor-audit-logs.md) depolama hesabınıza, Olay Hub 'ına veya Log Analytics 'e göndermek için bu seçeneği belirleyin. Denetim günlükleri, Intune 'da kimin ve ne zaman yaptığına ilişkin bir değişiklik üreten her görevin geçmişini gösterir.

      Bir depolama hesabı kullanmayı seçerseniz, verileri (bekletme) kaç gün tutmak istediğinizi de girin. Verileri süresiz olarak tutmak için, **bekletme (gün)** değerini `0` (sıfır) olarak ayarlayın.

    - Günlük > **operationallogs**: İşletimsel Günlükler (Önizleme), Intune 'a kaydolduğunu kullanıcıların ve cihazların başarısını veya başarısızlığını ve uyumlu olmayan cihazların ayrıntılarını gösterir. Kayıt günlüklerini depolama hesabınıza, Olay Hub 'ınıza veya Log Analytics 'e göndermek için bu seçeneği belirleyin.

      Bir depolama hesabı kullanmayı seçerseniz, verileri (bekletme) kaç gün tutmak istediğinizi de girin. Verileri süresiz olarak tutmak için, **bekletme (gün)** değerini `0` (sıfır) olarak ayarlayın.

      > [!NOTE]
      > İşletimsel Günlükler önizlemededir. İşletimsel günlüklere dahil edilen bilgiler dahil olmak üzere geri bildirim sağlamak için [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback) (yeni bir Web sitesi açar) sayfasına gidin.

    İşiniz bittiğinde, ayarlarınız aşağıdaki ayarlara benzer şekilde görünür: 

    ![Intune denetim günlüklerini bir Azure depolama hesabına gönderen örnek resim](media/diagnostics-settings-example.png)

4. Yaptığınız değişiklikleri **kaydedin**. Ayarınız listede gösterilir. Oluşturulduktan sonra Ayarları Değiştir **ayarını** > Düzenle ' yi seçerek**değiştirebilirsiniz.**

## <a name="use-audit-logs-throughout-intune"></a>Intune boyunca denetim günlüklerini kullanma

Ayrıca, kayıt, uyumluluk, yapılandırma, cihazlar, istemci uygulamaları ve daha fazlası dahil olmak üzere Intune 'un diğer bölümlerinde denetim günlüklerini dışarı aktarabilirsiniz.

Örneğin, cihaz uyumluluğunu kullanırken denetim günlüklerini dışarı aktarmak için:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz uyumluluk** > İzleyicisiDenetim > **günlüklerini**seçin:

    ![Intune verilerini Azure Izleyici depolama, Olay Hub 'ları veya analiz 'e yönlendirmek için Denetim günlüklerini seçin](media/audit-logs-under-monitor-in-compliance.png)

3. **Veri ayarlarını dışarı aktar**' ı seçin. Etkin değilse, **tanılama ayarlarını**açabilirsiniz. Günlükleri [Azure izleyici 'ye gönderme](#send-logs-to-azure-monitor) (Bu makalede) bölümünde açıklandığı gibi günlüklerin nereden gönderileceğini de seçebilirsiniz.

## <a name="cost-considerations"></a>Maliyetle ilgili konular

Zaten bir Microsoft Intune lisansınız varsa, depolama hesabını ve Olay Hub 'ını ayarlamak için bir Azure aboneliğine sahip olmanız gerekir. Azure aboneliği genellikle ücretsizdir. Ancak, arşiv için depolama hesabı ve akış için Olay Hub 'ı dahil olmak üzere Azure kaynaklarını kullanmak için ödeme yaparsınız. Veri miktarı ve maliyetler, kiracı boyutuna bağlı olarak değişiklik gösterir.

### <a name="storage-size-for-activity-logs"></a>Etkinlik günlükleri için depolama boyutu

Her denetim günlüğü olayı yaklaşık 2 KB veri depolama alanı kullanır. 100.000 kullanıcısı olan bir kiracı için günde yaklaşık 1.500.000 olay olabilir. Günde 3 GB veri depolama alanı gerekebilir. Yazma işlemleri genellikle beş dakikalık toplu işlemlerde gerçekleştiğinden ayda yaklaşık 9.000 yazma işlemi bekleyebilir.

Aşağıdaki tablolarda, kiracının boyutuna bağlı olarak maliyet tahmini gösterilmektedir. Ayrıca, en az bir yıllık veri saklama için Batı ABD bir genel amaçlı v2 depolama hesabı içerir. Günlüklerinizi istediğiniz veri hacmine yönelik bir tahmin almak için [Azure depolama Fiyatlandırma hesaplayıcısı](https://azure.microsoft.com/pricing/details/storage/blobs/)' nı kullanın.

**100.000 kullanıcısı ile denetim günlüğü**

| | |
|---|---|
|Gün başına olay| 1.500.000|
|Aylık tahmini veri hacmi| 90 GB|
|Aylık tahmini maliyet (USD)| $1,93|
|Yıllık tahmini maliyet (USD)| $23,12|

**1.000 kullanıcısı ile denetim günlüğü**

| | |
|---|---|
|Gün başına olay| 15.000|
|Aylık tahmini veri hacmi| 900 MB|
|Aylık tahmini maliyet (USD)| $0,02|
|Yıllık tahmini maliyet (USD)| $0,24|

### <a name="event-hub-messages-for-activity-logs"></a>Etkinlik günlükleri için Olay Hub 'ı iletileri

Olaylar genellikle beş dakikalık aralıklarla toplanmış ve bu zaman çerçevesi içindeki tüm olaylara sahip tek bir ileti olarak gönderilir. Olay Hub 'ındaki bir ileti en fazla 256 KB boyutunda bir ileti içerir. Zaman çerçevesi içindeki tüm iletilerin toplam boyutu o birimi aşarsa, birden çok ileti gönderilir.

Örneğin, saniye başına yaklaşık 18 olay, 100.000 'den fazla Kullanıcı büyük bir kiracısında gerçekleşir. Bu, beş dakikada bir 5.400 olayına karşılık gelir (300 saniye x 18 olay). Denetim günlükleri Olay başına yaklaşık 2 KB 'dir. Bu, 10,8 MB veri ile eşitleme yapar. Bu nedenle, 43 ileti bu beş dakikalık aralıkta Olay Hub 'ına gönderilir.

Aşağıdaki tabloda, olay verileri hacmine bağlı olarak Batı ABD bir temel olay hub 'ı için aylık tahmini maliyetler yer alır. Günlüklerinizi istediğiniz veri hacminin tahminini almak için [Event Hubs Fiyatlandırma hesaplayıcısı](https://azure.microsoft.com/pricing/details/event-hubs/)' nı kullanın.

**100.000 kullanıcısı ile denetim günlüğü**

| | |
|---|---|
|Saniye başına olay| 18|
|Beş dakikalık Aralık başına olay sayısı| 5\.400|
|Aralık başına birim| 10,8 MB|
|Aralık başına ileti| 43|
|Aylık ileti sayısı| 371.520|
|Aylık tahmini maliyet (USD)| $10,83|

**1.000 kullanıcısı ile denetim günlüğü**

| | |
|---|---|
|Saniye başına olay|0.1 |
|Beş dakikalık Aralık başına olay sayısı| 52|
|Aralık başına birim|104 KB |
|Aralık başına ileti|1\. |
|Aylık ileti sayısı|8\.640 |
|Aylık tahmini maliyet (USD)|$10,80 |

### <a name="log-analytics-cost-considerations"></a>Log Analytics maliyet konuları

Log Analytics çalışma alanını yönetme ile ilgili maliyetleri gözden geçirmek için, bkz. [Log Analytics veri birimi ve bekletme denetimi yaparak maliyeti yönetme](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage).

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

Sık sorulan soruların yanıtlarını alın ve Azure Izleyici 'de Intune günlükleriyle ilgili bilinen sorunlar hakkında bilgi edinin.

### <a name="which-logs-are-included"></a>Hangi Günlükler dahildir?

Denetim günlükleri ve işletimsel (Önizleme) günlükleri bu özellik kullanılarak yönlendirme için de kullanılabilir.

### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>Bir eylemden sonra, karşılık gelen Günlükler Olay Hub 'ında ne zaman görünür?

Günlükler genellikle olay hub 'ınızda, eylem gerçekleştirildikten sonra birkaç dakika içinde görünür. [Azure Event Hubs nedir?](https://docs.microsoft.com/azure/event-hubs/) daha fazla bilgi sağlar.

### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>Bir eylemden sonra, karşılık gelen Günlükler depolama hesabında ne zaman görünür?

Azure Storage hesaplarında, işlem çalıştıktan sonra gecikme süresi 5 ila 15 dakika olur.

### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>Bir yönetici bir tanılama ayarının bekletme süresini değiştirirse ne olur?

Yeni bekletme ilkesi, değişiklikten sonra toplanan günlüklere uygulanır. İlke değişikliği etkilenmeden önce toplanan Günlükler.

### <a name="how-much-does-it-cost-to-store-my-data"></a>Verilerimi depolama maliyeti ne kadar sürer?

Depolama maliyetleri, günlüklerinizin boyutuna ve seçtiğiniz bekletme dönemine bağlıdır. Oluşturulan günlük birimine bağlı olan kiracılar için tahmini maliyetlerin bir listesi için bkz. [etkinlik günlükleri Için depolama boyutu](#storage-size-for-activity-logs) (Bu makalede).

### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Verilerden bir olay hub 'ına ne kadar veri akışı maliyeti?

Akış maliyetleri, dakika başına aldığınız ileti sayısına bağlıdır. Maliyetlerin sayısı ve maliyet tahminleri hakkında bilgi edinmek için bkz. [etkinlik günlükleri Için Olay Hub 'ı iletileri](#event-hub-messages-for-activity-logs) (Bu makalede).

### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Nasıl yaparım? SıEM sistemim ile Intune denetim günlüklerini tümleştirsin mi?

Günlükleri SıEM sisteminize akışındaki Event Hubs Azure Izleyici 'yi kullanın. İlk olarak, [günlükleri bir olay hub 'ına akışı](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)yapın. Ardından, yapılandırılmış olay hub 'ını kullanarak [SıEM aracınızı ayarlayın](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) . 

### <a name="what-siem-tools-are-currently-supported"></a>Şu anda hangi SıEM araçları destekleniyor?

Şu anda Azure Izleyici, [splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar ve [Sumo Logic](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (yeni bir Web sitesi açar) tarafından desteklenir. Bağlayıcıların nasıl çalıştığı hakkında daha fazla bilgi için bkz. [bir dış araçla tüketim Için Azure izleme verilerini bir olay hub 'ına akış](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs).

### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Bir dış SıEM aracı kullanmadan veriye bir olay hub 'ından erişebilir miyim?

Evet. Özel uygulamanızdan günlüklere erişmek için [Event HUBS API](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph)'sini kullanabilirsiniz.

### <a name="what-data-is-stored"></a>Hangi veriler depolanır?

Intune, işlem hattı aracılığıyla gönderilen herhangi bir veriyi depolamaz. Intune, kiracı yetkilisinde verileri Azure Izleyici ardışık düzenine yönlendirir. Daha fazla bilgi için bkz. [Azure izleyiciye genel bakış](https://docs.microsoft.com/azure/azure-monitor/overview).

## <a name="next-steps"></a>Sonraki adımlar

* [Etkinlik günlüklerini bir depolama hesabına arşivleme](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Etkinlik günlüklerini bir olay hub 'ına yönlendirme](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Etkinlik günlüklerini Log Analytics ile tümleştirme](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)
