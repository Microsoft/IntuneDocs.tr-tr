---
title: Uygulama koruma ilkelerini izleme
titleSuffix: Microsoft Intune
description: Bu konuda, Intune 'da uygulama koruma ilkelerinin nasıl izleneceği açıklanır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9d82813f1292c99cf248c56a102503413d2cb8fb
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507446"
---
# <a name="how-to-monitor-app-protection-policies"></a>Uygulama koruma ilkelerini izleme
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uyumluluk durumunu, [Azure Portal](https://portal.azure.com)Intune uygulama koruması bölmesinden izleyebilirsiniz. Ayrıca, MAM ilkelerinden etkilenen kullanıcılar hakkında bilgiler, MAM ilkesi uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunlar hakkında bilgi edinebilirsiniz.

Uygulama koruma ilkelerini izlemek için üç farklı yer vardır:
- Özet görünümü
- Ayrıntılı görünüm
- Raporlama görünümü

> [!NOTE]
> Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

Uygulama koruma verileri için bekletme süresi 90 gündür. Son 90 gün içinde MAM hizmetine iade edilmiş tüm uygulama örnekleri, uygulama koruma durumu raporuna dahil edilir. Bir *uygulama örneği* , benzersiz bir Kullanıcı + App + cihazdır. 

## <a name="summary-view"></a>Özet görünümü

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. Özet görünümünü görmek için, **istemci uygulamaları** iş yükünde, **Izleyici**altında, **Uygulama koruma durumu**' nu seçin.

   ![Intune mobil uygulama yönetimi bölmesindeki Özet kutucuğunun ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Atanan kullanıcılar**: şirketinizde, bir iş bağlamındaki ilkeyle ilişkili olan ve korunmayan ve lisanslanmış olan atanan kullanıcıların yanı sıra korumalı ve lisanslanan bir uygulama kullanan atanan kullanıcıların toplam sayısı.
- **Bayraklı kullanıcılar**: cihazlarıyla ilgili sorun yaşayan Kullanıcı sayısı. Jailbreak uygulanmış (iOS) ve kökü belirtilmiş (Android) cihazlar **bayraklı kullanıcılar**altında raporlanır. Ayrıca, Google SafetyNet cihaz kanıtlama denetimi (BT Yöneticisi tarafından açıldıysa) tarafından işaretlenen cihazlara sahip kullanıcılar burada raporlanır. 
- **Zararlı olabilecek uygulamalara sahip kullanıcılar**: Android cihazlarında Google Play koruma tarafından algılanan zararlı bir uygulamaya sahip olabilecek Kullanıcı sayısı. 
- **İOS Için Kullanıcı** durumu ve **Android için Kullanıcı durumu**: ilgili platform için bir iş bağlamında kendisine atanmış bir ilkeyi olan bir uygulamayı kullanmış olan kullanıcıların sayısı. Bu bilgiler, ilke tarafından yönetilen kullanıcıların sayısını ve bir iş bağlamındaki herhangi bir ilke tarafından hedeflenmediği bir uygulamayı kullanan kullanıcı sayısını gösterir. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.
- **En Iyi korunan IOS uygulamaları**: en sık kullanılan iOS uygulamalarına göre bu bilgiler, korunan ve korumasız iOS uygulamalarının sayısını gösterir.
- **En Iyi korunan Android Uygulamaları**: en sık kullanılan Android uygulamalarını temel alan bu bilgiler, korunan ve korunmayan Android uygulamalarının sayısını gösterir.
- **Kayıt olmadan en çok yapılandırılan IOS uygulamaları**: kayıtlı olmayan cihazlar için en sık kullanılan iOS uygulamalarına bağlı olarak, bu bilgiler yapılandırılmış iOS uygulamalarının sayısını gösterir.
- **Kayıt olmadan en fazla yapılandırılan Android Uygulamaları**: kayıtlı olmayan cihazlar için en sık kullanılan Android uygulamalarını temel alan bu bilgiler, yapılandırılan Android uygulamalarının sayısını gösterir.

    > [!NOTE]
    > Platform başına birden çok ilkeniz varsa bir kullanıcıya atanmış en az bir ilke olduğunda bu kullanıcının ilke ile yönetildiği kabul edilir.

## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihaz işletim sistemi platformuna göre), **zararlı olabilecek uygulamalara sahip olan kullanıcıları** ve **bayraklı kullanıcıları** kutucuğunu seçerek özetin ayrıntılı görünümüne ulaşabilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** bölmesinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- **Simge**: uygulama durumunun güncel olup olmadığını gösterir.
- **Uygulama adı**: uygulamanın adı.
- **Cihaz adı**: kullanıcının hesabıyla ilişkili cihazlar.
- **Cihaz türü**: cihazın çalıştığı cihazın veya işletim sisteminin türü.
- **İlkeler**: uygulamayla ilişkili ilkeler.
- **Durum**:
  - **Giriş yaptı:** İlke kullanıcıya dağıtılmış ve uygulama en az bir kez iş bağlamında kullanılmıştır.
  - **Iade edilmedi**: ilke kullanıcıya dağıtıldı, ancak uygulama bu tarihten sonra iş bağlamında kullanılmadı.
- **Son eşitleme**: uygulama Intune ile son kez eşitlendiğinde. 

>[!NOTE]
> **Son eşitleme** sütunu, hem konsol içi Kullanıcı durumu raporunda hem de uygulama koruma ilkesi [verilebilir. csv raporunda](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities-to-csv)aynı değeri temsil eder. Bu fark, iki rapordaki değer arasındaki eşitlemede küçük bir gecikme olur. 
>
> Son eşitlemede başvurulan süre, Intune 'un uygulama örneğini son gördüğünüz. Bir Kullanıcı bir uygulamayı başlattığında, en son ne zaman iade edilene bağlı olarak bu başlatma zamanında Intune Uygulama Koruması hizmetine bildirimde bulunabilir. [Uygulama koruma ilkesi için yeniden deneme aralığı zamanlarını](https://docs.microsoft.com/en-us/intune/app-protection-policy-delivery)inceleyin. Bir Kullanıcı bu uygulamayı son iade aralığında (genellikle etkin kullanım için 30 dakika) kullanmadıysanız ve uygulamayı başlamışsa:
>
> - Uygulama koruma Ilkesi verilebilir. csv raporu, en yeni zamanı 1 dakika (minimum) ile 30 dakika (en fazla) arasında.
> - Kullanıcı durumu raporu en yeni zamana anında sahiptir.
>
> Örneğin, 12:00 PM 'de korumalı bir uygulamayı başlatan hedeflenen ve lisanslı bir kullanıcıyı göz önünde bulundurun:
> - Bu, ilk kez oturum açmışsa, bu, kullanıcının daha önce imzalandığı ve Intune ile uygulama örneği kaydı olmadığı anlamına gelir. Kullanıcı oturum açtıktan sonra, Kullanıcı yeni bir uygulama örneği kaydı alır ve hemen iade edilebilir (daha önce gelecekteki iadelerde listelenen aynı zaman gecikmeleriyle birlikte). Bu nedenle, son eşitleme zamanı, Kullanıcı durumu raporunda 12:00 PM ve uygulama koruma Ilkesi raporundaki 12:01 PM (veya en son 12:30). 
> - Kullanıcı uygulamayı yeni başlatmazysa, bildirilen son eşitleme zamanı, kullanıcının en son ne zaman iade edildiğinde değişir.


Kullanıcının raporlamasını görmek için şu adımları izleyin:

1. Bir kullanıcı seçmek için **Kullanıcı durumu** Özet kutucuğunu seçin.

    ![Intune mobil uygulama yönetiminin Özet kutucuğunun ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. **Uygulama raporlama** bölmesinde, Azure Active Directory Kullanıcı aramak Için **Kullanıcı Seç** ' i seçin.

    ![Uygulama raporlama bölmesinde kullanıcı seç seçeneğinin ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görebilirsiniz.

>[!NOTE]
> Aradığınız kullanıcıya MAM ilkesi dağıtılmamışsa, kullanıcının herhangi bir MAM ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde; hata iletisi, hata oluştuğunda erişilmiş olan uygulama, etkilenen cihaz işletim sistemi platformu ve zaman damgası gösterilir. Hata genellikle jailbreak uygulanmış (iOS) veya kökü belirtilen (Android) cihazlar içindir. Ayrıca, ' SafetyNet cihaz kanıtlama ' koşullu başlatma denetimi tarafından işaretlenen cihazlara sahip kullanıcılar, burada Google tarafından raporlanan sebeplerden itibaren raporlanır. Bir kullanıcının rapordan kaldırılması için, bir sonraki kök algılama denetiminden (veya jailbreak Check/Safbrannet Check olduktan sonra) bir pozitif sonuç bildirmeli sonra gerçekleşen cihazın durumunun değişmiş olması gerekir. Cihaz gerçekten düzeltilmişse, bayrak eklenmiş kullanıcılar raporundaki yenileme, dikey pencere yeniden yüklediğinde gerçekleşir.

### <a name="users-with-potentially-harmful-apps"></a>Zararlı olabilecek uygulamalara sahip kullanıcılar
Ayrıntılı görünüm şunları gösterir:

- Kullanıcı.
- Uygulama paketi KIMLIĞI.
- Uygulama MAM etkinse.
- Tehdit kategorisi.
- E-posta.
- Cihaz adı.
- Bir zaman damgası.

**Uygulamalarda tehdit taraması iste** koşullu başlatma denetimi tarafından işaretlenen cihazlara sahip kullanıcılar, burada Google tarafından bildirilen tehdit kategorisiyle birlikte raporlanır. Bu raporda Intune aracılığıyla dağıtılan uygulamalar varsa, uygulama için uygulama geliştiricisine başvurun veya uygulamayı Kullanıcılarınıza atamak için kaldırın. 

## <a name="reporting-view"></a>Raporlama görünümü

Aynı raporları **Uygulama koruma durumu** dikey penceresinin üst kısmında bulabilirsiniz.

> [!NOTE]
> Intune, uygulama kayıt KIMLIĞI, Android üreticisi, model ve güvenlik düzeltme eki sürümü ve iOS modelinin yanı sıra ek cihaz raporlama alanları sağlar. Intune 'da, bu alanlara, **istemci uygulamaları** > **uygulama koruma durumu** > **Uygulama koruma raporu: iOS, Android '** i seçerek erişirsiniz. Ayrıca, bu parametreler cihaz üreticisi için **Izin verilenler** listesini (Android), cihaz modeli Için **izin verilenler** listesini (Android ve iOS) ve en düşük Android güvenlik düzeltme eki sürümü ayarını yapılandırmanıza yardımcı olur. 

Ek raporlar, MAM ilkesi uyumluluk durumu ile ilgili yardım almak için kullanılabilir. Bu raporları görüntülemek için **istemci uygulamaları** > **uygulama koruma durumu** > **raporları**' nı seçin. 

**Raporlar** dikey penceresi, aşağıdakiler de dahil olmak üzere Kullanıcı ve uygulamaya göre çeşitli raporlar sağlar:

- **Kullanıcı raporu**: Bu rapor, yukarıdaki [ayrıntılı görünüm](app-protection-policies-monitor.md#detailed-view) bölümünde yer aldığı **Kullanıcı durumu** raporunda bulabileceğiniz bilgilerin aynısını özetler.

- **Uygulama raporu**: platformu ve uygulamayı seçmenin yanı sıra, bu rapor, raporu oluşturmadan önce seçebileceğiniz iki farklı uygulama koruma durumu sağlar. Durumlar **korunabilir** veya **korumasız**olabilir.

  - Yönetilen MAM etkinliği için Kullanıcı durumu (**korumalı**): Bu rapor, her BIR yönetilen mam uygulamasının etkinliğini, Kullanıcı başına temelinde özetler. Her Kullanıcı için MAM ilkeleri tarafından hedeflenen tüm uygulamaları ve her uygulamanın durumunu MAM ilkeleriyle iade edildi olarak gösterir. Rapor ayrıca, bir MAM ilkesiyle hedeflenen, ancak hiç iade edilmedi olan her uygulamanın durumunu da içerir.
  - Yönetilmeyen MAM etkinliği için Kullanıcı durumu (**korumasız**): Bu rapor, şu anda yönetilmeyen ve Kullanıcı başına TEMELINDE olan mam özellikli uygulamaların etkinliklerini özetler. Bunun nedeni şu olabilir:
    - Bu uygulamalar, şu anda bir MAM ilkesi tarafından hedeflenen bir kullanıcı veya uygulama tarafından kullanılıyor.
    - Tüm uygulamalar giriş yapmış, ancak henüz MAM ilkelerini almıyor olabilir.

    ![Üç uygulama için ayrıntıların bulunduğu bir kullanıcının uygulama raporlama dikey penceresinin ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Kullanıcı yapılandırma raporu**: seçili bir kullanıcıya bağlı olarak, bu rapor kullanıcının aldığı uygulama yapılandırmaları hakkında ayrıntılar sağlar.
- **Uygulama yapılandırma raporu**: seçili platform ve uygulamanın temelini oluşturan bu rapor, hangi kullanıcıların seçili uygulama için yapılandırmaları aldığını gösteren Ayrıntılar sağlar.
- **Windows Information Protection Için uygulama öğrenme raporu**: Bu rapor, ilke sınırlarının çapraz olarak hangi uygulamaların denenmeye yönelik olduğunu gösterir.
- **Windows Information Protection Için Web sitesi öğrenimi**: Bu rapor, ilke sınırlarının çapraz bir şekilde hangi web siteleri tarafından denenmeye

## <a name="table-grouping"></a>Tablo gruplandırma

**Uygulama koruma Kullanıcı raporu** verileri gösterildikten sonra, verileri aşağıdaki şekilde toplayabilirsiniz:

- **Doğrulama sonucu**: veriler, "hata", "uyarı" veya "başarılı" olabilen uygulama koruma durumuna göre gruplandırılır.
- **Uygulama adı**: veriler gerçek uygulama adına göre gruplandırılır. Yine, durum "hata", "uyarı" veya "başarılı" olabilir.

## <a name="export-app-protection-activities"></a>Uygulama koruma etkinliklerini dışarı aktarma

Uygulama koruma ilkesi etkinliklerinizin tümünü tek bir .csv dosyasına dışarı aktarabilirsiniz. Bu işlem, kullanıcılardan raporlanan uygulama koruması durumlarının tümünü çözümlemenize yardımcı olabilir.

Uygulama koruma raporunu oluşturmak için aşağıdaki adımları izleyin:

1. Intune mobil uygulama yönetimi bölmesinde **Uygulama koruması raporu**’nu seçin.

    ![Uygulama koruma indirme bağlantısının ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Raporunuzu kaydetmek için **Evet** ' i seçin ve ardından **farklı kaydet**' i seçin. Raporu kaydetmek istediğiniz klasörü seçin.

    ![Raporu kaydet onay kutusunun ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Ayrıca bkz:
- [iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md)
- [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
- [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)
