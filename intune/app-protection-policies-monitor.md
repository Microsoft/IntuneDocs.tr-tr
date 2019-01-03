---
title: Uygulama koruma ilkelerini izleme
titleSuffix: Microsoft Intune
description: Intune'da mobil uygulama yönetimi ilkelerinin uyumluluk durumunu izleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c0603b3cfd2b8fbe1d26e782118fb07526849cfa
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816849"
---
# <a name="how-to-monitor-app-protection-policies"></a>Uygulama koruma ilkelerini izleme
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uygunluk durumunu [Azure portalı](https://portal.azure.com) üzerindeki Intune uygulama koruması bölmesinden izleyin. MAM ilkelerinden etkilenen kullanıcılar hakkında bilgileri, uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunları burada bulabilirsiniz.

Uyumluluk durumu üç farklı yerden izlenebilir:

-   Özet görünümü

-   Ayrıntılı görünüm

-   Raporlama görünümü

> [!NOTE]
> Uygulama Koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

## <a name="summary-view"></a>Özet görünümü

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükünde özet görünümü görmek için **İzle** > **Uygulama koruma durumu**’nu seçin:

![Intune mobil uygulama yönetimi bölmesinde Özet kutucuğu](./media/app-protection-user-status-summary.png)

-   **Kullanıcılar**: Şirketinizin, iş bağlamında bir ilkeyle ilişkili olan bir uygulama kullanan kullanıcıların toplam sayısı.

-   **İLKE TARAFINDAN YÖNETİLEN**: Bir iş bağlamında atanmış bir ilkeye sahip bir uygulama kullanmış olan kullanıcıların sayısı.

-   **İLKE YOK**: İş bağlamında hiçbir ilke tarafından hedeflenmeyen bir uygulamayı kullanan kullanıcıların sayısı. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.
    > [!NOTE]
    > Platform başına birden çok ilkeniz varsa bir kullanıcıya atanmış en az bir ilke olduğunda bu kullanıcının ilke ile yönetildiği kabul edilir.

- **Bayrak eklenen kullanıcılar**: Sorun yaşayan kullanıcıların sayısı. Şu anda yalnızca jailbreak uygulanmış cihazlara sahip kullanıcılar, **Bayrak eklenen kullanıcılar** kapsamında raporlanır.


## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihazın işletim sistemi platformuna göre ve **Bayrak eklenen kullanıcılar** kutucuğunu seçerek özetin ayrıntılı görünümünü elde edebilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** bölmesinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- Kullanıcı hesabıyla ilişkilendirilmiş cihazlar

- Cihazda MAM ilkesine sahip uygulamalar

- Durum:

  - **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında en az bir kez kullanıldı.

  - **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmamış.

>[!NOTE]
> Aradığınız kullanıcıya MAM ilkesi dağıtılmamışsa, kullanıcının herhangi bir MAM ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

Kullanıcının raporlamasını görmek için şu adımları izleyin:

1.  Kullanıcı seçmek için **Özet** kutucuğunu işaretleyin.

    ![Intune mobil uygulama yönetimi Özet kutucuğu ekran görüntüsü](./media/MAM-reporting-6.png)

2. Açılan **Uygulama raporlama** bölmesinde bir Azure Active Directory kullanıcısını aramak için **Kullanıcı seçin** öğesini belirleyin.

    ![Uygulama raporlama bölmesinde seçili kullanıcı seçeneğinin ekran görüntüsü](./media/MAM-reporting-2.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görebilirsiniz.

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde; hata iletisi, hata oluştuğunda erişilmiş olan uygulama, etkilenen cihaz işletim sistemi platformu ve zaman damgası gösterilir.

## <a name="reporting-view"></a>Raporlama görünümü

Ayrıntılı görünümde, aynı raporlara ek olarak MAM ilkesi uyumluluk durumuyla ilgili bilgi almanıza yardımcı olacak diğer raporları bulabilirsiniz:

![Ayarlar bölmesinde kullanılabilir 2 raporun vurgulandığı ekran görüntüsü](./media/MAM-reporting-7.png)

-   **Uygulama Koruması kullanıcı raporu:** Bulabileceğiniz bilgileri özetler **kullanıcı durumu** yukarıdaki ayrıntılı görünüm bölümünde rapor.

-   **Uygulama koruması uygulama raporu:** Bu, yöneticilerin, raporu oluşturmadan önce seçebileceği iki farklı uygulama koruma durumu sağlar. Durumlar korumalı veya korumasız olabilir.

    -   Yönetilen MAM etkinliği (korumalı) için kullanıcı durumu: Bu rapor, kullanıcı başına temelinde her yönetilen MAM uygulamasının etkinliğini özetler.

        -   Her bir kullanıcı için, MAM ilkeleri tarafından hedeflenen tüm uygulamaları göstermenin yanı sıra uygulamaların durumunu, MAM ilkelerine giriş yapmış veya MAM ilkesi ile hedeflenmiş ancak henüz giriş yapmamış olarak özetler.
<br></br>
    -   Yönetilmeyen MAM etkinliği (korumasız) için kullanıcı durumu: Bu rapor, MAM özellikli uygulamalar, kullanıcı başına esasına göre şu anda yönetilmeyen etkinliğini özetler. Bu, aşağıdaki nedenlere bağlı olarak gerçekleşebilir:

        -   Bu uygulamalar, henüz bir MAM ilkesi tarafından hedeflenmemiş olan bir kullanıcı veya uygulama tarafından kullanılıyor olabilir.

        -   Tüm uygulamalar giriş yapmış, ancak henüz MAM ilkelerini almıyor olabilir.

![Bir kullanıcının uygulama raporlama dikey penceresinin ekran görüntüsü ayrıntıları 3 için uygulamalar](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Tablo gruplandırma

**Uygulama koruması kullanıcı raporu** verileri gösterilince, verileri aşağıdakilere göre toplayabilirsiniz:

- **Doğrulama sonucu:** Veri başarısız, uyarı veya başarılı olabilir. uygulama koruma durumu tarafından gruplandırılmış olarak gösterilir.
- **Uygulama adı:** Veri başarısız, uyarı veya başarılı olan uygulamalara (asıl uygulama adı) göre gruplandırılmış olarak gösterilir.

## <a name="export-app-protection-activities-to-csv"></a>Uygulama koruması etkinliklerini CSV’ye dışarı aktarma

Uygulama koruma ilkesi etkinliklerinizin tümünü tek bir .csv dosyasına dışarı aktarabilirsiniz. Bu işlem, kullanıcılardan raporlanan uygulama koruması durumlarının tümünü çözümlemenize yardımcı olabilir.

Uygulama koruması raporu oluşturmak için bu adımları izleyin:

1. Intune mobil uygulama yönetimi bölmesinde **Uygulama koruması raporu**’nu seçin.

    ![Uygulama koruma indirme bağlantısının ekran görüntüsü](./media/app-protection-report-csv-2.png)

2. Raporunuzu kaydetmek için Evet’i seçin, ardından Farklı Kaydet’i seçin ve raporun kaydedilmesini istediğiniz klasörü belirtin.

    ![Raporu kaydet onay kutusunun ekran görüntüsü](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Ayrıca bkz.
[iOS uygulamaları arasında veri aktarımını yönetme](data-transfer-between-apps-manage-ios.md)

* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-ios.md)
