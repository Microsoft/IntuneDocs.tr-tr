---
title: Uygulama koruma ilkelerini izleme
titleSuffix: Microsoft Intune
description: Bu konu, ıntune mobil uygulama yönetimi ilkelerinin uyumluluk durumunu izlemek açıklar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cee1cbc05164a418148ecea8d93f6c8c45c73e01
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394545"
---
# <a name="how-to-monitor-app-protection-policies"></a>Uygulama koruma ilkelerini izleme
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune uygulama koruma bölmesinde kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uygunluk durumunu izleyebilirsiniz [Azure portalında](https://portal.azure.com). Ayrıca, MAM ilkeleri, MAM ilke uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunları tarafından etkilenen kullanıcılar hakkında bilgi bulabilirsiniz.

MAM ilkelerinin uyumluluk durumunu izlemek için üç farklı yerden izlenebilir vardır:
-   Özet görünümü
-   Ayrıntılı görünüm
-   Raporlama görünümü

> [!NOTE]
> Uygulama Koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

## <a name="summary-view"></a>Özet görünümü

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. İçinde **istemci uygulamaları** iş yükünü seçin **uygulama koruma durumu** gelen **İzleyici** bölümünde Özet görünümü görmek için:

![Intune mobil uygulama yönetimi bölmesinde Özet kutucuğu](./media/app-protection-user-status-summary.png)

- **Atanan kullanıcılar**: Şirketinizde iş bağlamında bir ilkeyle ilişkili korumalı ve lisanslı, korunmasız ve lisanssız atanan kullanıcılar yanı sıra bir uygulama kullanan atanmış kullanıcıların toplam sayısı.
- **Bayrak eklenen kullanıcılar**: Sorun yaşayan kullanıcıların sayısı. Jailbreak uygulanmış cihazlar kapsamında raporlanır **riskli oldukları belirlenen kullanıcılar**.
- **İOS için kullanıcı durumu** ve **Android için kullanıcı durumu**: İlgili platformuna yönelik iş bağlamında atanmış bir ilkeye sahip bir uygulama kullanmış olan kullanıcıların sayısı. Bu bilgileri, iş bağlamında hiçbir ilke tarafından hedeflenmeyen bir uygulamayı kullanan kullanıcıların sayısını yanı sıra, ilke tarafından yönetilen kullanıcı sayısını gösterir. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.
- **Popüler korunan iOS uygulamaları**: Bu bilgiler, en çok kullanılan iOS uygulamalarına bağlı olarak, korumalı ve korumasız iOS uygulamaları sayısını gösterir.
- **Üst korunan Android uygulamaları**: Bu bilgiler, en çok kullanılan Android uygulaması bağlı olarak, korumalı ve korumasız Android uygulamaları sayısını gösterir.
- **Yapılandırılan iOS uygulamaları kayıt olmadan top**: Bu bilgiler, kayıtlı olmayan cihazlar için en sık kullanılan iOS uygulamaları bağlı olarak, yapılandırılan iOS uygulamaları sayısını gösterir.
- **Üst yapılandırılan Android uygulamaları kayıtsız**: Bu bilgiler, kayıtlı olmayan cihazlar için en çok kullanılan Android uygulamalarını bağlı olarak, yapılandırılan Android uygulamaları sayısını gösterir.

    > [!NOTE]
    > Platform başına birden çok ilkeniz varsa, bir kullanıcı en az bir sahip olduğunda, ilke ile yönetildiği kabul edilir ilke kendisine atanır.

## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihazın işletim sistemi platformuna göre ve **Bayrak eklenen kullanıcılar** kutucuğunu seçerek özetin ayrıntılı görünümünü elde edebilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** bölmesinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- **Simge**: Uygulama durumunu güncel olup olmadığını gösterir.
- **Uygulama adı**: Uygulama adı.
- **Cihaz adı**: Kullanıcı hesabıyla ilişkilendirilmiş cihazlar.
- **Cihaz türü**: Cihaz veya işletim sistemi türü, cihaz çalışıyor.
- **İlkeleri**: Uygulama ile ilişkili ilkeleri.
- **Durum**:
  - **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında en az bir kez kullanıldı.
  - **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmamış.
- **Son eşitleme**: Ne zaman bir cihaz son eşitlendi.

>[!NOTE]
> Aradığınız kullanıcıya MAM ilkesi dağıtılmamışsa, kullanıcının herhangi bir MAM ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

Kullanıcının raporlamasını görmek için şu adımları izleyin:

1.  Kullanıcı seçmek için Seç **kullanıcı durumu** Özet kutucuğu.

    ![Intune mobil uygulama yönetimi Özet kutucuğu ekran görüntüsü](./media/MAM-reporting-6.png)

2. Açılan **Uygulama raporlama** bölmesinde bir Azure Active Directory kullanıcısını aramak için **Kullanıcı seçin** öğesini belirleyin.

    ![Uygulama raporlama bölmesinde seçili kullanıcı seçeneğinin ekran görüntüsü](./media/MAM-reporting-2.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görebilirsiniz.

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde; hata iletisi, hata oluştuğunda erişilmiş olan uygulama, etkilenen cihaz işletim sistemi platformu ve zaman damgası gösterilir.

## <a name="reporting-view"></a>Raporlama görünümü

Aynı raporlar üst kısmında bulabilirsiniz **uygulama koruma durumu** dikey penceresi.

> [!NOTE]
> Intune, ek cihaz alanları, uygulama kayıt kimliği, Android üreticisi, modeli ve güvenlik düzeltme eki sürümü yanı sıra iOS model dahil olmak üzere raporlama sağlar. Intune, bu alanlar seçerek kullanılabilir **istemci uygulamaları** > **uygulama koruma durumu** seçip **uygulama koruma raporu: iOS, Android**. Bu parametreleri yapılandırma Ayrıca, yardımcı olacak **izin ver** cihaz üreticisi (Android) için liste **izin** cihaz modeli (Android ve iOS) ve en düşük Android güvenlik düzeltme eki için listesi Sürüm ayarı. 

MAM İlkesi uyumluluk durumuyla ilgili yardımcı olacak ek raporlar kullanılabilir. Bu raporları görüntülemek için seçin **istemci uygulamaları** > **uygulama koruma durumu** > **raporları**. 

**Raporları** dikey pencere, kullanıcı ve uygulama, aşağıdakiler dahil olmak üzere dayanan çeşitli raporlar sağlar:


- **Kullanıcı raporu**: Bu rapor bulabileceğiniz bilgileri özetler **kullanıcı durumu** altında rapor [ayrıntılı görünümü](app-protection-policies-monitor.md#detailed-view) yukarıdaki bölümde.

- **Uygulama raporu**: Bu rapor, uygulama ve platform seçmenin yanı sıra, raporu oluşturmadan önce seçebileceğiniz iki farklı uygulama koruma durumu sağlar. Durumlar olabilir **korumalı** veya **korumasız**.

    -   Yönetilen MAM etkinliği için kullanıcı durumu (**korumalı**): Bu rapor, kullanıcı başına temelinde her yönetilen MAM uygulamasının etkinliğini özetler. Her bir kullanıcı için, MAM ilkeleri tarafından hedeflenen tüm uygulamaları göstermenin yanı sıra uygulamaların durumunu, MAM ilkelerine giriş yapmış veya MAM ilkesi ile hedeflenmiş ancak henüz giriş yapmamış olarak özetler.
    -   Yönetilmeyen MAM etkinliği için kullanıcı durumu (**korumasız**): Bu rapor, MAM özellikli uygulamalar, kullanıcı başına esasına göre şu anda yönetilmeyen etkinliğini özetler. Bu, aşağıdaki nedenlere bağlı olarak gerçekleşebilir:
        -   Bu uygulamalar, henüz bir MAM ilkesi tarafından hedeflenmemiş olan bir kullanıcı veya uygulama tarafından kullanılıyor olabilir.
        -   Tüm uygulamalar giriş yapmış, ancak henüz MAM ilkelerini almıyor olabilir.

        ![Bir kullanıcının uygulama raporlama dikey penceresinin ekran görüntüsü ayrıntıları 3 için uygulamalar](./media/MAM-reporting-4.png)

- **Kullanıcı yapılandırma raporu**: Bu rapor, seçilen bir kullanıcıya bağlı, kullanıcının aldığı herhangi bir uygulama yapılandırmaları hakkında ayrıntılar sağlar.
- **Uygulama yapılandırma raporu**: Temel seçili platform ve uygulama bu raporu hangi kullanıcıların seçilen uygulamaya ilişkin yapılandırmaları almış ayrıntılarını sağlar.
- **Uygulama öğrenme raporu Windows Information Protection için**: Bu rapor, hangi uygulamaların İlkesi sınırları çalıştığınız gösterir.
- **Web sitesi için Windows bilgi koruması öğrenme**: Bu rapor, hangi Web sitelerini İlkesi sınırları çalıştığınız gösterir.

## <a name="table-grouping"></a>Tablo gruplandırma

Bir kez **uygulama koruması kullanıcı raporu** veri görüntüleniyorsa, aşağıdaki verileri toplayabilirsiniz:

- **Doğrulama sonucu:** Veri başarısız, uyarı veya başarılı olabilir. uygulama koruma durumu tarafından gruplandırılmış olarak gösterilir.
- **Uygulama adı:** Veri başarısız, uyarı veya başarılı olan uygulamalara (asıl uygulama adı) göre gruplandırılmış olarak gösterilir.

## <a name="export-app-protection-activities-to-csv"></a>Uygulama koruması etkinliklerini CSV’ye dışarı aktarma

Tüm uygulama koruma İlkesi etkinliklerinizi tek bir verme *.csv* dosya. Bu işlem, kullanıcılardan raporlanan uygulama koruması durumlarının tümünü çözümlemenize yardımcı olabilir.

Uygulama koruması raporu oluşturmak için bu adımları izleyin:

1. Intune mobil uygulama yönetimi bölmesinde **Uygulama koruması raporu**’nu seçin.

    ![Uygulama koruma indirme bağlantısının ekran görüntüsü](./media/app-protection-report-csv-2.png)

2. Seçin **Evet** raporunuzu kaydetmek için ardından **Kaydet** ve raporu kaydetmek istediğiniz klasörü seçin.

    ![Raporu kaydet onay kutusunun ekran görüntüsü](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Ayrıca bkz.
- [iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md)
- [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
- [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)
