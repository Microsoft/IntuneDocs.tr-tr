---
title: Uygulama koruma ilkelerini izleme
titleSuffix: Microsoft Intune
description: Bu konuda, Intune 'da mobil uygulama yönetimi ilkelerinin uyumluluk durumunun nasıl izleneceği açıklanır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fad554ace3b7c8c279161f149bc06854dfaca93d
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731369"
---
# <a name="how-to-monitor-app-protection-policies"></a>Uygulama koruma ilkelerini izleme
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uyumluluk durumunu, [Azure Portal](https://portal.azure.com)Intune uygulama koruması bölmesinden izleyebilirsiniz. Ayrıca, MAM ilkelerinden etkilenen kullanıcılar hakkında bilgiler, MAM ilkesi uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunlar hakkında bilgi edinebilirsiniz.

MAM ilkelerinin uyumluluk durumunu izlemek için üç farklı yer vardır:
- Özet görünümü
- Ayrıntılı görünüm
- Raporlama görünümü

> [!NOTE]
> Uygulama Koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

Uygulama koruma verileri için bekletme süresi 90 gündür. MAM hizmetine son 90 gün içinde iade edilmiş tüm uygulama örnekleri, uygulama koruma durumu raporuna dahil edilir. Bir uygulama örneği, benzersiz bir Kullanıcı + App + cihazdır. 

## <a name="summary-view"></a>Özet görünümü

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükünde, Özet görünümünü görmek için **izleyici** bölümünde **Uygulama koruma durumu** ' nu seçin:

![Intune mobil uygulama yönetimi bölmesinde Özet kutucuğu](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Atanan kullanıcılar**: şirketinizde, bir iş bağlamındaki ilkeyle ilişkili olan ve korunmayan ve lisanslanmış olan atanan kullanıcıların yanı sıra korumalı ve lisanslanan bir uygulama kullanan atanan kullanıcıların toplam sayısı.
- **Bayrak eklenen kullanıcılar:** Sorun yaşayan kullanıcıların sayısı. Jailbreak uygulanmış (iOS) ve kökü belirtilmiş (Android) cihazlar **bayraklı kullanıcılar**altında raporlanır. Google SafetyNet cihaz kanıtlama denetimi tarafından işaretlenen cihazlara sahip kullanıcılar (BT Yöneticisi tarafından açıldıysa) burada raporlanır. 
- **Zararlı olabilecek uygulamalara sahip kullanıcılar**: Android cihazlarında Google Play koruma tarafından algılanan zararlı bir uygulamaya sahip olabilecek Kullanıcı sayısı. 
- **İOS Için Kullanıcı** durumu ve **Android için Kullanıcı durumu**: ilgili platform için bir iş bağlamında kendisine atanmış bir ilkeyi olan bir uygulamayı kullanmış olan kullanıcıların sayısı. Bu bilgiler, ilke tarafından yönetilen kullanıcıların sayısını ve bir iş bağlamındaki herhangi bir ilke tarafından hedeflenmediği bir uygulamayı kullanan kullanıcı sayısını gösterir. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.
- **En Iyi korunan IOS uygulamaları**: en sık kullanılan iOS uygulamalarına göre bu bilgiler, korunan ve korumasız iOS uygulamalarının sayısını gösterir.
- **En Iyi korunan Android Uygulamaları**: en sık kullanılan Android uygulamalarını temel alan bu bilgiler, korunan ve korunmayan Android uygulamalarının sayısını gösterir.
- **Kayıt olmadan en çok yapılandırılan IOS uygulamaları**: kayıtlı olmayan cihazlar için en sık kullanılan iOS uygulamalarına bağlı olarak, bu bilgiler yapılandırılmış iOS uygulamalarının sayısını gösterir.
- **Kayıt olmadan en fazla yapılandırılan Android Uygulamaları**: kayıtlı olmayan cihazlar için en sık kullanılan Android uygulamalarını temel alan bu bilgiler, yapılandırılan Android uygulamalarının sayısını gösterir.

    > [!NOTE]
    > Platform başına birden çok ilkeniz varsa, bu kullanıcılara en az bir ilke atandığında bir kullanıcı ilke tarafından yönetilmeye kabul edilir.

## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihaz işletim sistemi platformuna göre), **zararlı olabilecek uygulamalara** ve **bayraklı kullanıcılara** sahip kullanıcıları seçerek özetin ayrıntılı görünümüne ulaşabilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** bölmesinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- **Simge**: uygulama durumunun güncel olup olmadığını gösterir.
- **Uygulama adı**: uygulamanın adı.
- **Cihaz adı**: kullanıcının hesabıyla ilişkili cihazlar.
- **Cihaz türü**: cihazın çalıştığı cihazın veya işletim sisteminin türü.
- **İlkeler**: uygulamayla ilişkili ilkeler.
- **Durum**:
  - **Giriş yaptı:** İlke kullanıcıya dağıtılmış ve uygulama en az bir kez iş bağlamında kullanılmıştır.
  - **Giriş yapmadı**: İlke kullanıcıya dağıtılmış, ancak o zaman beri uygulamanın iş bağlamında kullanılmamıştır.
- **Son eşitleme**: cihaz son kez eşitlendiğinde.

>[!NOTE]
> Aradığınız kullanıcıya MAM ilkesi dağıtılmamışsa, kullanıcının herhangi bir MAM ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

Kullanıcının raporlamasını görmek için şu adımları izleyin:

1. Bir kullanıcı seçmek için **Kullanıcı durumu** Özet kutucuğunu seçin.

    ![Intune mobil uygulama yönetiminin Özet kutucuğunun ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. Açılan **Uygulama raporlama** bölmesinde bir Azure Active Directory kullanıcısını aramak için **Kullanıcı seçin** öğesini belirleyin.

    ![Uygulama raporlama bölmesinde kullanıcı seç seçeneğinin ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görebilirsiniz.

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde; hata iletisi, hata oluştuğunda erişilmiş olan uygulama, etkilenen cihaz işletim sistemi platformu ve zaman damgası gösterilir. ' SafetyNet cihaz kanıtlama ' koşullu başlatma denetimi tarafından işaretlenen cihazlara sahip kullanıcılar, burada Google tarafından raporlanan sebeplerden itibaren raporlanır.

### <a name="users-with-potentially-harmful-apps"></a>Zararlı olabilecek uygulamalara sahip kullanıcılar
Ayrıntılı görünümde Kullanıcı, uygulama paketi KIMLIĞI, uygulama MAM etkinleştirilmişse, tehdit kategorisi, e-posta, cihaz adı ve zaman damgası gösterilir. ' Uygulama üzerinde tehdit taraması gerektir ' koşullu başlatma denetimi tarafından işaretlenen cihazlara sahip kullanıcılar, burada Google tarafından bildirilen tehdit kategorisiyle birlikte raporlanır. Bu raporda Intune aracılığıyla dağıtılan uygulamalar varsa, uygulama için uygulama geliştiricisine başvurun ve/veya uygulamayı Son kullanıcılarınıza atanmış olarak kaldırın. 

## <a name="reporting-view"></a>Raporlama görünümü

Aynı raporları **Uygulama koruma durumu** dikey penceresinin üst kısmında bulabilirsiniz.

> [!NOTE]
> Intune, uygulama kayıt kimliği, Android üreticisi, model ve güvenlik düzeltme eki sürümü ve iOS modelinin yanı sıra ek cihaz raporlama alanları sağlar. Intune 'da bu alanlar, **istemci uygulamaları** > **Uygulama koruma durumu** ' nu seçip **Uygulama koruma raporu: iOS, Android '** i seçerek kullanılabilir. Ayrıca, bu parametreler cihaz üreticisi için **Izin verilenler** listesi (Android), cihaz modeli Için **izin verilenler** listesi (Android ve iOS) ve en düşük Android güvenlik düzeltme eki sürümü ayarını yapılandırmanıza yardımcı olur. 

Ek raporlar, MAM ilkesi uyumluluk durumu ile ilgili yardım almak için kullanılabilir. Bu raporları görüntülemek için **istemci uygulamaları** > **uygulama koruma durumu** > **raporları**' nı seçin. 

**Raporlar** dikey penceresi, aşağıdakiler de dahil olmak üzere Kullanıcı ve uygulamaya göre çeşitli raporlar sağlar:


- **Kullanıcı raporu**: Bu rapor, yukarıdaki [ayrıntılı görünüm](app-protection-policies-monitor.md#detailed-view) bölümünde yer aldığı **Kullanıcı durumu** raporunda bulabileceğiniz bilgilerin aynısını özetler.

- **Uygulama raporu**: platformu ve uygulamayı seçmenin yanı sıra, bu rapor, raporu oluşturmadan önce seçebileceğiniz iki farklı uygulama koruma durumu sağlar. Durumlar **korunabilir** veya **korumasız**olabilir.

  - Yönetilen MAM etkinliği için Kullanıcı durumu (**korumalı**): Bu rapor, her BIR yönetilen mam uygulamasının etkinliğini, Kullanıcı başına temelinde özetler. Her bir kullanıcı için, MAM ilkeleri tarafından hedeflenen tüm uygulamaları göstermenin yanı sıra uygulamaların durumunu, MAM ilkelerine giriş yapmış veya MAM ilkesi ile hedeflenmiş ancak henüz giriş yapmamış olarak özetler.
  - Yönetilmeyen MAM etkinliği için Kullanıcı durumu (**korumasız**): Bu rapor, Kullanıcı başına YÖNETILMEKTE olan mam özellikli uygulamaların etkinliğini ana hatlarıyla özetler. Bu, aşağıdaki nedenlere bağlı olarak gerçekleşebilir:
    - Bu uygulamalar, henüz bir MAM ilkesi tarafından hedeflenmemiş olan bir kullanıcı veya uygulama tarafından kullanılıyor olabilir.
    - Tüm uygulamalar giriş yapmış, ancak henüz MAM ilkelerini almıyor olabilir.

    ![3 uygulama ile ilgili ayrıntıların bulunduğu bir kullanıcının uygulama raporlama dikey penceresinin ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Kullanıcı yapılandırma raporu**: seçili bir kullanıcıya bağlı olarak, bu rapor kullanıcının aldığı uygulama yapılandırmaları hakkında ayrıntılar sağlar.
- **Uygulama yapılandırma raporu**: seçili platform ve uygulamanın temelini oluşturan bu rapor, hangi kullanıcıların seçili uygulama için yapılandırmaları aldığını gösteren Ayrıntılar sağlar.
- **Windows Information Protection Için uygulama öğrenme raporu**: Bu rapor, ilke sınırlarının çapraz olarak hangi uygulamaların denenmeye yönelik olduğunu gösterir.
- **Windows Information Protection Için Web sitesi öğrenimi**: Bu rapor, ilke sınırlarının çapraz bir şekilde hangi web siteleri tarafından denenmeye

## <a name="table-grouping"></a>Tablo gruplandırma

**Uygulama koruması Kullanıcı raporu** verileri görüntülenirken, verileri aşağıdaki şekilde toplayabilirsiniz:

- **Doğrulama sonucu:** Veriler, uygulama koruması durumuna (başarısız, uyarı veya başarılı olabilir) göre gruplandırılmış olarak gösterilir.
- **Uygulama adı:** Veriler, hata, uyarı veya başarılı ile uygulamalara (gerçek uygulama adı) göre gruplandırılmış olarak gösterilir.

## <a name="export-app-protection-activities-to-csv"></a>Uygulama koruması etkinliklerini CSV’ye dışarı aktarma

Tüm uygulama koruma ilkesi etkinliklerinizi tek bir *. csv* dosyasına dışarı aktarabilirsiniz. Bu işlem, kullanıcılardan raporlanan uygulama koruması durumlarının tümünü çözümlemenize yardımcı olabilir.

Uygulama koruması raporu oluşturmak için bu adımları izleyin:

1. Intune mobil uygulama yönetimi bölmesinde **Uygulama koruması raporu**’nu seçin.

    ![Uygulama koruma indirme bağlantısının ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Raporunuzu kaydetmek için **Evet** ' i seçin, ardından **farklı kaydet** ' i seçin ve raporu kaydetmek istediğiniz klasörü seçin.

    ![Raporu kaydet onay kutusunun ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Ayrıca bkz:
- [iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md)
- [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
- [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)
