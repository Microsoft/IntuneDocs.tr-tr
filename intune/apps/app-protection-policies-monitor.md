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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0b4ab3369f241c9f33d4e0bddfd0dcf98c8ab915
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830590"
---
# <a name="how-to-monitor-app-protection-policies"></a>Uygulama koruma ilkelerini izleme
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uyumluluk durumunu, [Azure Portal](https://portal.azure.com)Intune uygulama koruması bölmesinden izleyebilirsiniz. Ayrıca, MAM ilkelerinden etkilenen kullanıcılar hakkında bilgiler, MAM ilkesi uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunlar hakkında bilgi edinebilirsiniz.

Uygulama koruma ilkelerini izlemek için üç farklı yer vardır:
- Özet görünümü
- Ayrıntılı görünüm
- Raporlama görünümü

> [!NOTE]
> Uygulama koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

Uygulama koruma verileri için bekletme süresi 90 gündür. MAM hizmetine son 90 gün içinde iade edilmiş tüm uygulama örnekleri, uygulama koruma durumu raporuna dahil edilir. Bir uygulama örneği, benzersiz bir Kullanıcı + App + cihazdır. 

## <a name="summary-view"></a>Özet görünümü

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **istemci uygulamaları**' nı seçin.
4. **İstemci uygulamaları** iş yükünde, Özet görünümünü görmek için **izleyici** bölümünde **Uygulama koruma durumu** ' nu seçin:

![Intune mobil uygulama yönetimi bölmesindeki Özet kutucuğu](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Atanan kullanıcılar**: şirketinizde, bir iş bağlamındaki ilkeyle ilişkili olan ve korunmayan ve lisanslanmış olan atanan kullanıcıların yanı sıra korumalı ve lisanslanan bir uygulama kullanan atanan kullanıcıların toplam sayısı.
- **Bayraklı kullanıcılar**: sorun yaşayan Kullanıcı sayısı. Jailbreak uygulanmış (iOS) ve kökü belirtilmiş (Android) cihazlar **bayraklı kullanıcılar**altında raporlanır. Google SafetyNet cihaz kanıtlama denetimi tarafından işaretlenen cihazlara sahip kullanıcılar (BT Yöneticisi tarafından açıldıysa) burada raporlanır. 
- **Zararlı olabilecek uygulamalara sahip kullanıcılar**: Android cihazlarında Google Play koruma tarafından algılanan zararlı bir uygulamaya sahip olabilecek Kullanıcı sayısı. 
- **İOS Için Kullanıcı** durumu ve **Android için Kullanıcı durumu**: ilgili platform için bir iş bağlamında kendisine atanmış bir ilkeyi olan bir uygulamayı kullanmış olan kullanıcıların sayısı. Bu bilgiler, ilke tarafından yönetilen kullanıcıların sayısını ve bir iş bağlamındaki herhangi bir ilke tarafından hedeflenmediği bir uygulamayı kullanan kullanıcı sayısını gösterir. Bu kullanıcıları ilkeye eklemeyi göz önünde bulundurmanız gerekebilir.
- **En Iyi korunan IOS uygulamaları**: en sık kullanılan iOS uygulamalarına göre bu bilgiler, korunan ve korumasız iOS uygulamalarının sayısını gösterir.
- **En Iyi korunan Android Uygulamaları**: en sık kullanılan Android uygulamalarını temel alan bu bilgiler, korunan ve korunmayan Android uygulamalarının sayısını gösterir.
- **Kayıt olmadan en çok yapılandırılan IOS uygulamaları**: kayıtlı olmayan cihazlar için en sık kullanılan iOS uygulamalarına bağlı olarak, bu bilgiler yapılandırılmış iOS uygulamalarının sayısını gösterir.
- **Kayıt olmadan en fazla yapılandırılan Android Uygulamaları**: kayıtlı olmayan cihazlar için en sık kullanılan Android uygulamalarını temel alan bu bilgiler, yapılandırılan Android uygulamalarının sayısını gösterir.

    > [!NOTE]
    > Platform başına birden çok ilkeniz varsa, bu kullanıcılara en az bir ilke atandığında bir kullanıcı ilke tarafından yönetilmeye kabul edilir.

## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihaz işletim sistemi platformuna göre), **zararlı olabilecek uygulamalara** ve **bayraklı kullanıcılara** sahip kullanıcıları seçerek özetin ayrıntılı görünümüne ulaşabilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir Kullanıcı arayabilir ve bu kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** bölmesinde seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- **Simge**: uygulama durumunun güncel olup olmadığını gösterir.
- **Uygulama adı**: uygulamanın adı.
- **Cihaz adı**: kullanıcının hesabıyla ilişkili cihazlar.
- **Cihaz türü**: cihazın çalıştığı cihazın veya işletim sisteminin türü.
- **İlkeler**: uygulamayla ilişkili ilkeler.
- **Durum**:
  - **Iade edildi**: ilke kullanıcıya dağıtıldı ve uygulama en az bir kez iş bağlamında kullanıldı.
  - **Iade edilmedi**: ilke kullanıcıya dağıtıldı, ancak uygulama bu tarihten sonra iş bağlamında kullanılmadı.
- **Son eşitleme**: uygulama Intune ile son kez eşitlendiğinde. 

>[!NOTE]
> ' Last Sync ' sütunu hem konsol içi Kullanıcı durumu raporunda hem de uygulama koruma Ilkesi [verilebilir. csv raporunda](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities-to-csv)aynı değeri temsil eder. Fark, 2 raporlardaki değer arasında eşitleme sırasında küçük bir gecikmede yapılır. 
>
> ' Son eşitleme ' içinde başvurulan süre, Intune 'un en son "uygulama örneğini" gördük. Uygulama örneği, uygulama + Kullanıcı + cihazının benzersiz bir birleşimidir. Bir son kullanıcı uygulamayı başlattığında, son ne zaman iade edilene bağlı olarak, bu başlatma sırasında Intune Uygulama Koruması hizmetiyle konuşabilir veya konuşmayabilir. Bu belge [, uygulama koruma ilkesi iade etme zaman aşımı sürelerini](https://docs.microsoft.com/en-us/intune/app-protection-policy-delivery)açıklığa kavuşturmasına yardımcı olur. Bu nedenle, Son Kullanıcı bu uygulamayı son iade aralığında (genellikle etkin kullanım için 30 dakika) kullanmamışsa ve uygulamayı başladıklarında:
>
> - Uygulama koruma Ilkesi verilebilir. csv raporu, en yeni zamanı 1 dakika (olağan; en az) ila 30 dakika (en fazla, Intune raporlama tarafından kullanılan SQL toplaması tarafından sağlanmış olan maksimum SLA) olacaktır.
> - Kullanıcı durumu raporu en yeni zamana anında sahip olur.
>
> Örneğin, 12:00 PM 'de korumalı bir uygulama başlatan hedeflenen ve lisanslı bir son kullanıcıyı göz önünde bulundurun:
> - Bu bir oturum açma ilk kez oturum açarsa, son kullanıcının Intune 'da uygulama örneği kaydı olmadığı anlamına gelen (etkin olmayan) önce oturum açtığı anlamına gelir. Oturum açtıklarında, yeni bir uygulama örneği kaydı alırlar ve bağlantı sorunu olmadan hemen bekleyen iade edilir; sonraki iadelerde yukarıda listelenen aynı zaman gecikmeleri vardır. Bu nedenle, son eşitleme süresi Kullanıcı durumu raporunda 12:00 PM olarak, 12:01 PM (12:30 veya 12. en kötü durum) uygulama koruma Ilkesi raporunu olarak rapor edecektir. 
> - Uygulamayı yeni başlatmadıklarında, bildirilen ' son eşitleme ' saati, en son ne zaman iade ettikleri zamana bağlıdır.


Bir kullanıcıya ilişkin raporlamayı görmek için şu adımları izleyin:

1. Bir kullanıcı seçmek için **Kullanıcı durumu** Özet kutucuğunu seçin.

    ![Intune mobil uygulama yönetiminin Özet kutucuğunun ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. Açılan **uygulama raporlama** bölmesinde, Azure Active Directory Kullanıcı aramak Için **Kullanıcı Seç** ' i seçin.

    ![Uygulama raporlama bölmesinde kullanıcı seç seçeneğinin ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Listeden kullanıcıyı seçin. Bu kullanıcının uyumluluk durumunun ayrıntılarını görebilirsiniz.

>[!NOTE]
> Aradığınız kullanıcılara MAM ilkesi dağıtılmamışsa, kullanıcının herhangi bir MAM ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

### <a name="flagged-users"></a>Bayrak eklenmiş kullanıcılar
Ayrıntılı görünümde hata iletisi, hata oluştuğu zaman erişilen uygulama, cihaz işletim sistemi platformu etkilendi ve zaman damgası gösterilir. ' SafetyNet cihaz kanıtlama ' koşullu başlatma denetimi tarafından işaretlenen cihazlara sahip kullanıcılar, burada Google tarafından raporlanan sebeplerden itibaren raporlanır.

### <a name="users-with-potentially-harmful-apps"></a>Zararlı olabilecek uygulamalara sahip kullanıcılar
Ayrıntılı görünümde Kullanıcı, uygulama paketi KIMLIĞI, uygulama MAM etkinleştirilmişse, tehdit kategorisi, e-posta, cihaz adı ve zaman damgası gösterilir. "Uygulamalarda tehdit taraması gerektir" adlı cihazlara sahip olan kullanıcılar, burada Google tarafından bildirilen tehdit kategorisiyle birlikte raporlanır. Bu raporda Intune aracılığıyla dağıtılan uygulamalar varsa, uygulama için uygulama geliştiricisine başvurun ve/veya uygulamayı Son kullanıcılarınıza atanmış olarak kaldırın. 

## <a name="reporting-view"></a>Raporlama görünümü

Aynı raporları **Uygulama koruma durumu** dikey penceresinin üst kısmında bulabilirsiniz.

> [!NOTE]
> Intune, uygulama kayıt kimliği, Android üreticisi, model ve güvenlik düzeltme eki sürümü ve iOS modelinin yanı sıra ek cihaz raporlama alanları sağlar. Intune 'da bu alanlar, **istemci uygulamaları** > **Uygulama koruma durumu** ' nu seçip **Uygulama koruma raporu: iOS, Android '** i seçerek kullanılabilir. Ayrıca, bu parametreler cihaz üreticisi için **Izin verilenler** listesi (Android), cihaz modeli Için **izin verilenler** listesi (Android ve iOS) ve en düşük Android güvenlik düzeltme eki sürümü ayarını yapılandırmanıza yardımcı olur. 

Ek raporlar, MAM ilkesi uyumluluk durumu ile ilgili yardım almak için kullanılabilir. Bu raporları görüntülemek için **istemci uygulamaları** > **uygulama koruma durumu** > **raporları**' nı seçin. 

**Raporlar** dikey penceresi, aşağıdakiler de dahil olmak üzere Kullanıcı ve uygulamaya göre çeşitli raporlar sağlar:


- **Kullanıcı raporu**: Bu rapor, yukarıdaki [ayrıntılı görünüm](app-protection-policies-monitor.md#detailed-view) bölümünde yer aldığı **Kullanıcı durumu** raporunda bulabileceğiniz bilgilerin aynısını özetler.

- **Uygulama raporu**: platformu ve uygulamayı seçmenin yanı sıra, bu rapor, raporu oluşturmadan önce seçebileceğiniz iki farklı uygulama koruma durumu sağlar. Durumlar **korunabilir** veya **korumasız**olabilir.

  - Yönetilen MAM etkinliği için Kullanıcı durumu (**korumalı**): Bu rapor, her BIR yönetilen mam uygulamasının etkinliğini, Kullanıcı başına temelinde özetler. Her Kullanıcı için MAM ilkeleri tarafından hedeflenen tüm uygulamaları gösterir ve her bir uygulamanın durumunu MAM ilkeleriyle birlikte iade edildi olarak veya bir MAM ilkesiyle hedeflenmiş, ancak uygulama hiçbir şekilde iade edilmedi olarak gösterir.
  - Yönetilmeyen MAM etkinliği için Kullanıcı durumu (**korumasız**): Bu rapor, Kullanıcı başına YÖNETILMEKTE olan mam özellikli uygulamaların etkinliğini ana hatlarıyla özetler. Bu durum aşağıdaki nedenlerden dolayı gerçekleşebilir:
    - Bu uygulamalar, şu anda bir MAM ilkesi tarafından hedeflenilmemiş bir kullanıcı veya uygulama tarafından kullanılıyor.
    - Tüm uygulamalar iade edilir, ancak herhangi bir MAM ilkesi almaz.

    ![3 uygulama ile ilgili ayrıntıların bulunduğu bir kullanıcının uygulama raporlama dikey penceresinin ekran görüntüsü](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Kullanıcı yapılandırma raporu**: seçili bir kullanıcıya bağlı olarak, bu rapor kullanıcının aldığı uygulama yapılandırmaları hakkında ayrıntılar sağlar.
- **Uygulama yapılandırma raporu**: seçili platform ve uygulamanın temelini oluşturan bu rapor, hangi kullanıcıların seçili uygulama için yapılandırmaları aldığını gösteren Ayrıntılar sağlar.
- **Windows Information Protection Için uygulama öğrenme raporu**: Bu rapor, ilke sınırlarının çapraz olarak hangi uygulamaların denenmeye yönelik olduğunu gösterir.
- **Windows Information Protection Için Web sitesi öğrenimi**: Bu rapor, ilke sınırlarının çapraz bir şekilde hangi web siteleri tarafından denenmeye

## <a name="table-grouping"></a>Tablo gruplandırma

**Uygulama koruması Kullanıcı raporu** verileri görüntülenirken, verileri aşağıdaki şekilde toplayabilirsiniz:

- **Doğrulama sonucu:** Veriler, hata, uyarı veya başarılı olabilecek uygulama koruma durumuna göre gruplandırılmış olarak gösterilir.
- **Uygulama adı:** Veriler, hata, uyarı veya başarılı ile uygulamalara (gerçek uygulama adı) göre gruplandırılmış olarak gösterilir.

## <a name="export-app-protection-activities-to-csv"></a>Uygulama koruma etkinliklerini CSV 'ye aktar

Tüm uygulama koruma ilkesi etkinliklerinizi tek bir *. csv* dosyasına dışarı aktarabilirsiniz. Bu, kullanıcılardan raporlanan tüm uygulama koruma durumlarını çözümlemek için yararlı olabilir.

Uygulama koruma raporunu oluşturmak için aşağıdaki adımları izleyin:

1. Intune mobil uygulama yönetimi bölmesinde **Uygulama koruma raporu**' nu seçin.

    ![Uygulama koruma indirme bağlantısının ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Raporunuzu kaydetmek için **Evet** ' i seçin, ardından **farklı kaydet** ' i seçin ve raporu kaydetmek istediğiniz klasörü seçin.

    ![Raporu Kaydet onay kutusunun ekran görüntüsü](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Ayrıca bkz.
- [İOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md)
- [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-android.md)
- [İOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](../fundamentals/end-user-mam-apps-ios.md)
