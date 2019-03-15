---
title: Rota denetim günlükleri Azure İzleyici'yi kullanarak Microsoft Intune - Azure | Microsoft Docs
description: Denetim günlükleri ve işlem günlüklerini Intune Azure depolama hesabı, olay hub'ları veya log analytics'e göndermek için tanılama ayarları kullanın. Ne kadar süreyle verileri korumak ve bazı farklı boyutta kiracılar için tahmini maliyetleri görmek istediğinizi seçin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 412e5527e1a740f9b460ef8e090913a3c3270b5c
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460997"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Olay hub'ları, depolama için günlük verileri gönderin veya log analytics (Önizleme) Intune'a

Microsoft Intune ortamınız hakkında bilgi sağlayan yerleşik günlükleri içerir. **Denetim günlükleri** farklı olayları veya Intune'a gerçekleşen görevler ayrıntılarını gösterir. **İşlem günlüklerinde (Önizleme)** başarıyla diğer kullanıcılar ve cihazlar üzerinde ayrıntılarını göster (veya başarısız), uyumlu olmayan cihazlar hakkında ayrıntılı bilgi yanı sıra kaydetme.

Bu günlükleri depolama hesapları, olay hub'ları ve log analytics de dahil olmak üzere Azure İzleyici'hizmetine de gönderilir. Özellikle, şunları yapabilirsiniz:

* Intune günlükleri verileri tutmak veya bir süre için arşivlemek için bir Azure depolama hesabına arşivleme.
* Stream Intune Splunk ve QRadar gibi popüler güvenlik bilgileri ve Olay yönetimi (SIEM) araçlarını kullanarak analiz için Azure olay hub'ına kaydeder.
* Intune günlüklerini, olay hub'ına akış tarafından kendi özel günlük çözümleriyle tümleştirin.
* Log Analytics, izleme ve uyarı bağlı veriler üzerinde zengin görselleştirmeler etkinleştirmek için Intune günlükleri gönderin.

Bu özellikler parçası olan **tanılama ayarları** ıntune. 

Bu makalede nasıl kullanılacağını gösterir **tanılama ayarları** farklı hizmetler için günlük verileri göndermek için örnekler ve maliyet tahminleri sağlar ve bazı sık sorulan soruları yanıtlar.

## <a name="prerequisites"></a>Önkoşullar

Bu özelliği kullanmak için gerekir:

* Bir Azure aboneliği: Azure aboneliğiniz yoksa, şunları yapabilirsiniz [ücretsiz deneme için kaydolun](https://azure.microsoft.com/free/).
* Azure'daki Microsoft Intune ortamı (Kiracı)
* Bir kullanıcı kimin sahip bir **genel yönetici** veya **Intune Hizmet Yöneticisi** Intune kiracınız için.

Denetim günlüğü verilerini yönlendirmek istediğiniz bağlı olarak, aşağıdaki hizmetlerden biri ihtiyacınız vardır:

* Bir [Azure depolama hesabı](https://docs.microsoft.com/azure/storage/common/storage-account-overview) ile *Listkeys'i* izinleri. Genel bir depolama hesabı ve blob depolama hesabı kullanmanızı öneririz. Depolama fiyatlandırma bilgileri için bkz. [Azure depolama fiyatlandırma hesaplayıcısı](https://azure.microsoft.com/pricing/calculator/?service=storage). 
* Bir [Azure event hubs ad alanı](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) üçüncü taraf çözümleriyle tümleştirmek için.
* Bir [Azure log analytics çalışma alanı](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) günlükleri Log Analytics'e göndermek için.

## <a name="send-logs-to-azure-monitor"></a>Günlükleri göndermek için Azure İzleyici

1. İçinde [Azure portalında](https://portal.azure.com/)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. Altında **izleme**seçin **tanılama ayarları**. İlk kez açtığınızda, açın:

    ![Intune'a günlükleri göndermek için Azure İzleyici için tanılama ayarlarını açın](media/diagnostics-settings-turn-on.png)

3. Aşağıdaki özellikleri girin:

    - **Ad**: Tanılama ayarları için bir ad girin. Bu ayar, girdiğiniz tüm özellikleri içerir. Örneğin, şunu girin: `Route audit logs to storage account`.
    - **Bir depolama hesabında arşivle**: Azure depolama hesabınız için günlük verileri kaydeder. Kaydet veya verileri arşivlemek istiyorsanız bu seçeneği kullanın.

        1. Bu seçeneği seçin > **yapılandırma**. 
        2. Listeden mevcut bir depolama hesabını seçin > **Tamam**.

    - **Olay hub'ına Stream**: Akış günlüklerini Azure olay hub'ına. Gibi Splunk ve, QRadar SIEM araçlarını kullanarak verilerinizi log analytics istiyorsanız bu seçeneği belirleyin.

        1. Bu seçeneği seçin > **yapılandırma**. 
        2. Listeden bir var olan olay hub'ı ad alanını ve ilkesini seçin > **Tamam**.

    - **Log Analytics'e gönderme**: Azure log analytics'e veri gönderir. İzleme ve uyarı günlükleriniz için görselleştirmeler, kullanmak istiyorsanız bu seçeneği belirleyin.

        1. Bu seçeneği seçin > **yapılandırma**. 
        2. Yeni bir çalışma alanı oluşturun ve çalışma alanı ayrıntıları girin. Veya listeden mevcut bir çalışma alanı seçin > **Tamam**.

            [Azure log analytics çalışma alanı](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) bu ayarlar hakkında daha fazla ayrıntı sağlar.

    - **Günlük** > **AuditLogs**: Göndermek için bu seçeneği [Intune denetim günlüklerini](monitor-audit-logs.md) depolama hesabı, olay hub'ı veya log analytics. Intune'da kimin yaptığını dahil olmak üzere, değişikliği oluşturan her görev geçmişini denetim günlüklerini gösterir ve ne zaman.

      Bir depolama hesabı kullanmayı seçerseniz, ayrıca (bekletme) verilerini saklamak istediğiniz gün sayısı girin. Verileri sonsuza kadar korumak için ayarlayın **bekletme (gün)** için `0` (sıfır).

    - **Günlük** > **OperationalLogs**: İşlem günlüklerini (Önizleme), uyumlu olmayan cihazlar hakkında ayrıntılı bilgi yanı sıra Intune, başarı veya başarısızlık kullanıcı ve cihaz gösterir. Log analytics ya da depolama hesabınıza, olay hub'ı kayıt günlüklerini göndermek için bu seçeneği belirleyin.

      Bir depolama hesabı kullanmayı seçerseniz, ayrıca (bekletme) verilerini saklamak istediğiniz gün sayısı girin. Verileri sonsuza kadar korumak için ayarlayın **bekletme (gün)** için `0` (sıfır).

      > [!NOTE]
      > İşlem günlüklerinde Önizleme aşamasındadır. İşlem günlüklerine dahil bilgiler dahil olmak üzere, geribildirim sağlamak için Git [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback) (yeni bir Web sitesini açar).

    İşiniz bittiğinde aşağıdaki ayarlara ayarlarınızı benzer: 

    ![Azure depolama hesabınız için Intune denetim günlüklerini gönderen örneği görüntüsü](media/diagnostics-settings-example.png)

4. Yaptığınız değişiklikleri **kaydedin**. Ayarınız listesinde gösterilir. Oluşturulduktan sonra seçerek ayarlarını değiştirebilirsiniz **ayarını Düzenle** > **Kaydet**.

## <a name="cost-considerations"></a>Maliyetle ilgili konular

Zaten bir Microsoft Intune lisansınız varsa, depolama hesabı ve olay hub'ı ayarlamak için bir Azure aboneliği gerekir. Azure aboneliği genellikle ücretsizdir. Ancak, Azure kaynakları ödeme yapın ve olay hub'ına akış için depolama hesabı için arşiv dahil. Veri miktarına ve maliyetleri, Kiracı boyutuna bağlı olarak değişir.

### <a name="storage-size-for-activity-logs"></a>Etkinlik günlükleri için depolama boyutu

Her denetim günlüğü olayı yaklaşık 2 KB veri depolama alanı kullanır. 100.000 kullanıcı ile bir kiracı için günde yaklaşık 1,5 milyon olay olabilir. Yaklaşık 3 GB veri depolama günlük gerekebilir. Yazma işlemleri genellikle beş dakikalık toplu işler üzerinde olduğundan, yazma işlemleri ayda yaklaşık olarak 9. 000 bekleyebilirsiniz.

Aşağıdaki tablolarda, Kiracı boyutuna bağlı olarak Maliyet tahmini gösterilmektedir. Ayrıca bir genel amaçlı v2 depolama hesabı en az bir yıl süreyle veri saklama, Batı ABD bölgesinde içerir. Günlükleriniz için beklediğiniz veri birimi kestirmek için kullanmak [Azure depolama fiyatlandırma hesaplayıcısı](https://azure.microsoft.com/pricing/details/storage/blobs/).

**100.000 kullanıcı ile denetim günlüğü**

| | |
|---|---|
|Günlük olayları| 1,5 milyon|
|Tahmini aylık veri hacmi| 90 GB|
|(USD) aylık tahmini maliyet| $1.93|
|Yıl (USD) başına tahmini maliyet| $23.12|

**1.000 kullanıcılarla denetim günlüğü**

| | |
|---|---|
|Günlük olayları| 15.000|
|Tahmini aylık veri hacmi| 900 MB|
|(USD) aylık tahmini maliyet| $0.02|
|Yıl (USD) başına tahmini maliyet| $0.24|

### <a name="event-hub-messages-for-activity-logs"></a>Etkinlik günlükleri Olay hub'ı iletileri

Olaylar genellikle beş dakikalık aralıklarla toplu ve o zaman çerçevesi içindeki tüm etkinlikleri tek bir ileti olarak gönderilir. Olay hub'ında bir ileti boyut 256 KB üst sınırı vardır. Ardından zaman çerçevesi içinde tüm iletilerin toplam boyutu o birim aşarsanız, birden çok ileti gönderilir.

Örneğin, yaklaşık 18 olaylar başına ikinci genellikle büyük bir kiracı 100. 000'den fazla kullanıcı için gerçekleşir. Bu beş dakikada (300 saniye x 18 olayları) 5.400 olaylara karşılık gelmektedir. Denetim, olay başına yaklaşık 2 KB günlüklerdir. Bu, veri 10.8 MB karşılık gelmektedir. Bu nedenle, 43 iletileri bu beş dakikalık aralığında olay hub'ına gönderilir.

Aşağıdaki tablo, bir temel olay hub'ında Batı ABD, olay veri hacmine göre aylık Tahmini maliyetler içerir. Günlükleriniz için beklediğiniz veri hacmi kestirmek için kullanmak [Event Hubs fiyatlandırma hesaplayıcısını](https://azure.microsoft.com/pricing/details/event-hubs/).

**100.000 kullanıcı ile denetim günlüğü**

| | |
|---|---|
|Saniye başına olay| 18|
|Beş dakikalık aralık başına olay sayısı| 5,400|
|Aralık başına birim| 10.8 MB|
|İleti aralığı başına işleme| 43|
|İleti başına aylık| 371,520|
|(USD) aylık tahmini maliyet| $10.83|

**1.000 kullanıcılarla denetim günlüğü**

| | |
|---|---|
|Saniye başına olay|0.1 |
|Beş dakikalık aralık başına olay sayısı| 52|
|Aralık başına birim|104 KB |
|İleti aralığı başına işleme|1. |
|İleti başına aylık|8,640 |
|(USD) aylık tahmini maliyet|$10.80 |

### <a name="log-analytics-cost-considerations"></a>Log Analytics'e konuları maliyeti

Log Analytics çalışma alanı yönetmeyle ilgili maliyetleri gözden geçirmek için bkz: [veri hacmini ve saklamayı Log analytics'te kontrol ederek maliyet yönetme](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage).

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

Sık sorulan soruların yanıtlarını alın ve Azure İzleyici'de Intune günlükleri ile ilgili bilinen sorunlar hakkında bilgi edinin.

#### <a name="which-logs-are-included"></a>Hangi günlüklerin dahildir?

Denetim günlükleri ve operasyonel (Önizleme) günlükleri her ikisi de bu özelliği kullanarak yönlendirme için kullanılabilir olan.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>Bir eylem sonra ne zaman karşılık gelen günlükleri Olay hub'ı görünüyor?

Günlükler genellikle, olay hub'ında eylem gerçekleştirildikten sonra birkaç dakika içinde gösterilir. [Azure Event Hubs nedir? ](https://docs.microsoft.com/azure/event-hubs/) daha fazla bilgi sağlar.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>Bir eylem sonra ne zaman karşılık gelen günlükler depolama hesabında görünüyor?

Azure depolama hesapları için gecikme süresi, 5'ten herhangi bir eylem çalıştıktan sonra 15 dakika ile olan.

#### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>Tanılama ayarını saklama süresi yöneticinin değişmesi durumunda ne olur?

Yeni bir bekletme ilkesi değişiklikten sonra toplanan günlükleri uygulanır. İlke değişikliği etkilemeden önce toplanan günlükleri.

#### <a name="how-much-does-it-cost-to-store-my-data"></a>Bu benim verileri depolamak için nin ücreti ne kadardır?

Depolama maliyetleri, günlükleri ve seçtiğiniz Bekletme dönemi boyutuna bağlıdır. Oluşturulan günlük birimi üzerinde bağlıdır, kiracılar için tahmini maliyetleri listesi için bkz. [etkinlik günlükleri için depolama boyutu](#storage-size-for-activity-logs) (Bu makaledeki).

#### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Bunu verilerimi bir olay hub'ına akışla aktarmak nin ücreti ne kadardır?

Akış maliyetlerini dakika başına aldığınız ileti sayısını bağlıdır. Maliyetleri hesaplanan ve maliyet tahminleri iletileri sayısına göre hakkında ayrıntılı bilgi için bkz: [etkinlik günlükleri Olay hub'ı iletileri](#event-hub-messages-for-activity-logs) (Bu makaledeki).

#### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Intune denetim günlüklerini SIEM sistemimin ile nasıl tümleştirebilirim?

Azure İzleyici ile Event Hubs akış günlüklerini SIEM sisteminize için kullanın. İlk olarak, [günlükleri Olay hub'ına akış](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub). Ardından, [SIEM aracınızı ayarlayın](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) yapılandırılan olay hub'ı ile. 

#### <a name="what-siem-tools-are-currently-supported"></a>Hangi SIEM araçları şu anda destekleniyor mu?

Azure İzleyici tarafından şu anda desteklenen [Splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar, ve [Sumo mantıksal](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (yeni bir Web sitesini açar). Bağlayıcıları nasıl çalışır hakkında daha fazla bilgi için bkz. [Stream dış bir araç tarafından izleme verileri tüketim için olay hub'ına Azure](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs).

#### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Veriler bir olay hub'ından harici bir SIEM aracı kullanmadan erişebilirim?

Evet. Özel uygulamanızı günlüklerine erişmek için kullanabileceğiniz [olay hub'ları API](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph).

#### <a name="what-data-is-stored"></a>Hangi veriler depolanır?

Intune işlem hattı gönderilen tüm verileri depolar. Intune Azure İzleyici ardışık, kiracının yetkilisi veri yönlendirir. Daha fazla bilgi için [Azure İzleyiciye Genel Bakış](https://docs.microsoft.com/azure/azure-monitor/overview).

## <a name="next-steps"></a>Sonraki adımlar

* [Arşiv etkinlik günlükleri bir depolama hesabına](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Etkinlik günlükleri Olay hub'ına yönlendirme](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Etkinlik günlüklerini Log Analytics ile tümleştirme](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)
