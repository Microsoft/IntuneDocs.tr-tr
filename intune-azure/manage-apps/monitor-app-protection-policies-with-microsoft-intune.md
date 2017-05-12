---
title: Uygulama koruma ilkelerini izleme
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Kaç kullanıcının ilkeyi kullandığını görün, diğer ayrıntıları öğrenmek için detaya gidin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 382d549e485b8ccad27ccacf7d9359a92c75fe4e
ms.contentlocale: tr-tr
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-monitor-app-protection-policies"></a>Uygulama koruma ilkelerini izleme
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Azure’de Intune önizlemesinde değilseniz**, bu konu başlığı altında klasik Intune konsolunda [uygulama koruma ilkelerinin nasıl oluşturulacağı](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) anlatılır.


Kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uygunluk durumunu [Azure portalı](https://portal.azure.com) üzerindeki Intune uygulama koruması dikey penceresinden izleyebilirsiniz. MAM ilkelerinden etkilenen kullanıcılar hakkında bilgileri, uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunları burada bulabilirsiniz.

Uyumluluk durumu üç farklı yerden izlenebilir:

-   Özet görünümü

-   Ayrıntılı görünüm

-   Raporlama görünümü

## <a name="summary-view"></a>Özet görünümü

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde, **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde, özet görünümü görmek için **İzle** > **Uygulama koruma kullanıcı durumu**’nu seçin:

![Intune mobil uygulama yönetimi dikey penceresinde Özet kutucuğu](../media/app-protection-user-status-summary.png)

-   **Kullanıcılar:** Şirketinizde ilkeyle ilişkilendirilmiş uygulamaları kullanan kullanıcıların toplam sayısı.

-   **İLKEYLE YÖNETİLEN**: Uygulamalardan en az birini iş bağlamında kullanmış olan kullanıcıların sayısı.

-   **İLKE YOK**: İlkeyle ilişkilendirilmiş uygulamaları kullanan ancak ilkenin hedeflediği kullanıcılar arasında yer almayan kullanıcıların sayısı. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.

- **Bayrak eklenen kullanıcılar:** Sorun yaşayan kullanıcıların sayısı. Şu anda yalnızca jailbreak uygulanmış cihazlara sahip kullanıcılar, **Bayrak eklenen kullanıcılar** kapsamında raporlanır.


## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğunu (cihazın işletim sistemi platformuna göre ve **Bayrak eklenen kullanıcılar** kutucuğunu seçerek özetin ayrıntılı görünümünü elde edebilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** dikey penceresinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- Kullanıcı hesabıyla ilişkilendirilmiş cihazlar

- Cihazda MAM ilkesine sahip uygulamalar

- Durum:

  - **Giriş yaptı:** İlke kullanıcıya dağıtılmış ve uygulama en az bir kez iş bağlamında kullanılmıştır.

  - **Giriş yapmadı**: İlke kullanıcıya dağıtılmış, ancak o zaman beri uygulamanın iş bağlamında kullanılmamıştır.

>[!NOTE]
> Aradığınız kullanıcıya MAM ilkesi dağıtılmamışsa, kullanıcının herhangi bir MAM ilkesi tarafından hedeflenmediğini bildiren bir ileti görürsünüz.

Kullanıcının raporlamasını görmek için şu adımları izleyin:

1.  Kullanıcı seçmek için **Özet** kutucuğunu işaretleyin.

    ![Ekran görüntüsü 3](../media/MAM-reporting-6.png)

2. Açılan **Uygulama raporlama** dikey penceresinde Bir Azure Active Directory kullanıcısını aramak için **Kullanıcı seç** öğesini seçin.

    ![Uygulama raporlama dikey penceresinde kullanıcı seç seçeneği](../media/MAM-reporting-2.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görürsünüz.

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde; hata iletisi, hata oluştuğunda erişilmiş olan uygulama, etkilenen cihaz işletim sistemi platformu ve zaman damgası gösterilir.

## <a name="reporting-view"></a>Raporlama görünümü

Ayrıntılı görünümde, aynı raporlara ek olarak MAM ilkesi uyumluluk durumuyla ilgili bilgi almanıza yardımcı olacak diğer raporları bulabilirsiniz:

![Ekran görüntüsü-4](../media/MAM-reporting-7.png)

-   **Uygulama koruması kullanıcı raporu:** Yukarıdaki Ayrıntılı görünüm bölümünde gösterilen **Kullanıcı durumu** raporunda bulabileceğiniz bilgileri özetler.

-   **Uygulama koruması uygulama raporu:** Yöneticilerin, raporu oluşturmadan önce seçebileceği iki farklı uygulama koruma durumu sağlar. Durumlar korumalı veya korumasız olabilir.

    -   Yönetilen MAM etkinliği için kullanıcı durumu (Korumalı): Bu rapor, yönetilen her bir MAM uygulamasının etkinliğini kullanıcı temelinde özetler.

        -   Her bir kullanıcı için, MAM ilkeleri tarafından hedeflenen tüm uygulamaları göstermenin yanı sıra uygulamaların durumunu, MAM ilkelerine giriş yapmış veya MAM ilkesi ile hedeflenmiş ancak henüz giriş yapmamış olarak özetler.
<br></br>
    -   Yönetilmeyen MAM etkinliği için kullanıcı durumu (Korumasız): Bu rapor, MAM’in etkinleştirildiği yönetilmeyen uygulamaların etkinliğini kullanıcı temelinde özetler. Bu, aşağıdaki nedenlere bağlı olarak gerçekleşebilir:

        -   Bu uygulamalar, henüz bir MAM ilkesi tarafından hedeflenmemiş olan bir kullanıcı veya uygulama tarafından kullanılıyor olabilir.

        -   Tüm uygulamalar giriş yapmış, ancak henüz MAM ilkelerini almıyor olabilir.

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

## <a name="see-also"></a>Ayrıca bkz.
[iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-android-apps.md)
* [iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-ios-apps.md)

