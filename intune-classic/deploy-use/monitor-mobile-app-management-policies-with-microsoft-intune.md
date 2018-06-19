---
title: Microsoft Intune ile MAM ilkelerini izleme
description: Kaç kullanıcının ilkeyi kullandığını görün, diğer ayrıntıları öğrenmek için detaya gidin.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de26b7614578b275802ca048ed17bfa5969f0387
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31021533"
---
# <a name="monitor-app-protection-policies-with-microsoft-intune"></a>Microsoft Intune ile uygulama koruma ilkelerini izleme
Kullanıcılara uyguladığınız mobil uygulama koruma ilkelerinin uyumluluk durumunu izleyebilirsiniz. Uygulama koruma ilkelerinden etkilenen kullanıcılar hakkında bilgiler, ilkelerin uyumluluk durumunu ve kullanıcılarınızın karşılaşmış olabileceği sorunları bulabilirsiniz.

Uyumluluk durumu üç farklı yerden izlenebilir:

-   Özet görünümü

-   Ayrıntılı görünüm

-   Raporlama görünümü

## <a name="summary-view"></a>Özet görünümü

Özet görünümü açmak için aşağıdaki üç adımı izleyin:

1. [Azure portalına](https://portal.azure.com) gidin ve kimlik bilgilerinizi girin.
2. **Diğer Hizmetler**’i seçin ve filtre metin kutusuna **Intune** yazın.
3. **Intune Uygulama Koruması**’nı seçin.

**Intune mobil uygulama yönetimi** dikey penceresinde, uyumluluk durumunun özetini görebilirsiniz:

![Intune mobil uygulama yönetimi dikey penceresinde Özet kutucuğu](../media/mam-azure-portal-user-status-summary.png)

-   **Kullanıcılar**: Şirketinizde, iş bağlamında bir ilkeyle ilişkili uygulama kullanan kullanıcıların toplam sayısı.

-   **İLKEYLE YÖNETİLEN**: Kendisine iş bağlamında bir ilke atanmış bir uygulama kullanan kullanıcı sayısı.

-   **İLKE YOK**: İş bağlamında hiçbir ilke tarafından hedeflenmeyen bir uygulamayı kullanan kullanıcı sayısı. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.
    > [!NOTE]
    > Platform başına birden çok ilkeniz varsa bir kullanıcıya atanmış en az bir ilke olduğunda bu kullanıcının ilke ile yönetildiği kabul edilir.

- **Bayrak eklenen kullanıcılar:** Sorun yaşayan kullanıcıların sayısı. Şu anda yalnızca jailbreak uygulanmış cihazlara sahip kullanıcılar, **Bayrak eklenen kullanıcılar** kapsamında raporlanır.


## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihazın işletim sistemi platformuna göre ve **Bayrak eklenen kullanıcılar** kutucuğunu seçerek özetin ayrıntılı görünümünü elde edebilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** dikey penceresinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- Kullanıcı hesabıyla ilişkilendirilmiş cihazlar

- Cihazdaki uygulama koruma ilkesine sahip uygulamalar

- Durum:

  - **Giriş yaptı:** İlke kullanıcıya dağıtılmış ve uygulama en az bir kez iş bağlamında kullanılmıştır.

  - **Giriş yapmadı**: İlke kullanıcıya dağıtılmış, ancak o zaman beri uygulamanın iş bağlamında kullanılmamıştır.

>[!NOTE]
> Aradığınız kullanıcıya uygulama koruma ilkesi dağıtılmamışsa, kullanıcının herhangi bir uygulama koruma ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

Kullanıcının raporlamasını görmek için şu adımları izleyin:

1.  Kullanıcı seçmek için **Özet** kutucuğunu işaretleyin.

    ![Ekran görüntüsü 3](../media/MAM-reporting-6.png)

2. Açılan **Uygulama raporlama** dikey penceresinde Bir Azure Active Directory kullanıcısını aramak için **Kullanıcı seç** öğesini seçin.

    ![Uygulama raporlama dikey penceresinde kullanıcı seç seçeneği](../media/MAM-reporting-2.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görürsünüz.

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde; hata iletisi, hata oluştuğunda erişilmiş olan uygulama, etkilenen cihaz işletim sistemi platformu ve zaman damgası gösterilir.

## <a name="reporting-view"></a>Raporlama görünümü

Ayrıntılı görünümdeki raporların aynılarına ek olarak uygulama koruma ilkesi uyumluluk durumuyla ilgili bilgi almanıza yardımcı olacak ek raporlar bulabilirsiniz:

![Ekran görüntüsü-4](../media/MAM-reporting-7.png)

-   **Uygulama koruması kullanıcı raporu:** Yukarıdaki Ayrıntılı görünüm bölümünde gösterilen **Kullanıcı durumu** raporunda bulabileceğiniz bilgileri özetler.

-   **Uygulama koruması uygulama raporu:** Yöneticilerin, raporu oluşturmadan önce seçebileceği iki farklı uygulama koruma durumu sağlar. Durumlar korumalı veya korumasız olabilir.

    -   Yönetilen MAM etkinliği için kullanıcı durumu (Korumalı): Bu rapor, yönetilen her bir MAM uygulamasının etkinliğini kullanıcı temelinde özetler.

        -   Her bir kullanıcı için, uygulama koruma ilkeleri tarafından hedeflenen tüm uygulamaları göstermenin yanı sıra uygulamaların durumunu, uygulama koruma ilkeleriyle giriş yapılmış veya uygulama koruma ilkesi ile hedeflenmiş ancak henüz giriş yapılmamış olarak özetler.
<br></br>
    -   Yönetilmeyen MAM etkinliği için kullanıcı durumu (Korumasız): Bu rapor, MAM’in etkinleştirildiği yönetilmeyen uygulamaların etkinliğini kullanıcı temelinde özetler. Bu, aşağıdaki nedenlere bağlı olarak gerçekleşebilir:

        -   Bu uygulamalar, henüz bir uygulama koruma ilkesi tarafından hedeflenmemiş olan bir kullanıcı veya uygulama tarafından kullanılıyor olabilir.

        -   Tüm uygulamalara giriş yapılmış, ancak bunlar herhangi bir uygulama koruma ilkesi almıyor olabilirler.

![Ekran görüntüsü-2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Tablo gruplandırma

**Uygulama koruması kullanıcı raporu** verileri gösterilince, verileri aşağıdakilere göre toplayabilirsiniz:

- **Doğrulama sonucu:** Veriler, uygulama koruması durumuna (başarısız, uyarı veya başarılı olabilir) göre gruplandırılmış olarak gösterilir.
- **Uygulama adı:** Veriler, uygulamalara (asıl uygulama adı) göre başarısız, hata veya başarılı olarak gruplandırılmış olarak gösterilir.

## <a name="export-app-protection-activities-to-csv"></a>Uygulama koruması etkinliklerini CSV’ye dışarı aktarma

Uygulama koruma ilkesi etkinliklerinizin tümünü tek bir .csv dosyasına dışarı aktarabilirsiniz. Bu işlem, kullanıcılardan raporlanan uygulama koruması durumlarının tümünü çözümlemenize yardımcı olabilir.

Uygulama koruması raporu oluşturmak için bu adımları izleyin:

1. Intune mobil uygulama yönetimi dikey penceresinde Uygulama koruması raporunu seçin.

    ![Ekran görüntüsü-6](../media/app-protection-report-csv-2.png)

2. Raporunuzu kaydetmek için Evet’i seçin, ardından Farklı Kaydet’i seçin ve raporun kaydedilmesini istediğiniz klasörü belirtin.

    ![Ekran görüntüsü-7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Ayrıca bkz:
[iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](/intune/end-user-mam-apps-android)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](/intune/end-user-mam-apps-ios)
