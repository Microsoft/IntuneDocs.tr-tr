---
title: Microsoft Intune ile MAM ilkelerini izleme | Microsoft Docs
description: "Kaç kullanıcının ilkeyi kullandığını görün, diğer ayrıntıları öğrenmek için detaya gidin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: e60d707833ee276971000411e50564f39b41b207


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Microsoft Intune ile mobil uygulama yönetimi ilkelerini izleme
Kullanıcılara uyguladığınız mobil uygulama yönetimi (MAM) ilkelerinin uygunluk durumunu [Azure portalı](https://portal.azure.com) üzerindeki Intune uygulama koruması dikey penceresinden izleyebilirsiniz. MAM ilkelerinden etkilenen kullanıcılar hakkında bilgileri, uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunları burada bulabilirsiniz.

Uyumluluk durumu üç farklı yerden izlenebilir:

-   Özet görünümü

-   Ayrıntılı görünüm

-   Raporlama görünümü

## <a name="summary-view"></a>Özet görünümü

Özet görünümü açmak için aşağıdaki üç adımı izleyin:

1. [Azure portalı](https://portal.azure.com)’na gidin ve kimlik bilgilerinizi girin.
2. **Diğer Hizmetler**’i seçin ve "Intune" yazın.
3. **Intune Uygulama Koruması**’nı seçin.

**Intune mobil uygulama yönetimi** dikey penceresinde, uyumluluk durumunun özetini görebilirsiniz:

![Intune mobil uygulama yönetimi dikey penceresinde Özet kutucuğu](../media/mam-azure-portal-user-status-summary.png)

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

    ![Ekran görüntüsü-1](../media/MAM-reporting-1.png)

    -   Yönetilen MAM etkinliği için kullanıcı durumu (Korumalı): Bu rapor, yönetilen her bir MAM uygulamasının etkinliğini kullanıcı temelinde özetler.

        -   Her bir kullanıcı için, MAM ilkeleri tarafından hedeflenen tüm uygulamaları göstermenin yanı sıra uygulamaların durumunu, MAM ilkelerine giriş yapmış veya MAM ilkesi ile hedeflenmiş ancak henüz giriş yapmamış olarak özetler.
<br></br>
    -   Yönetilmeyen MAM etkinliği için kullanıcı durumu (Korumasız): Bu rapor, MAM’in etkinleştirildiği yönetilmeyen uygulamaların etkinliğini kullanıcı temelinde özetler. Bu, aşağıdaki nedenlere bağlı olarak gerçekleşebilir:

        -   Bu uygulamalar, henüz bir MAM ilkesi tarafından hedeflenmemiş olan bir kullanıcı veya uygulama tarafından kullanılıyor olabilir.

        -   Tüm uygulamalar giriş yapmış, ancak henüz MAM ilkelerini almıyor olabilir.

![Ekran görüntüsü-2](../media/MAM-reporting-4.png)

## <a name="see-also"></a>Ayrıca bkz.
[iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


