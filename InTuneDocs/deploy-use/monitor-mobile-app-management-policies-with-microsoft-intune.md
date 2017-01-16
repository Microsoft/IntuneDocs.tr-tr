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
ms.sourcegitcommit: 9e208608d50c9b5f7fe66743de0d3c7e741dbfbd
ms.openlocfilehash: 2a18ad7226c6fc6de0277f1f20443ea64dc8b918


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Microsoft Intune ile mobil uygulama yönetimi ilkelerini izleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bir mobil uygulama (MAM) ilkesi ayarladıktan ve kullanıcılara uyguladıktan sonra, [Azure portalında](https://portal.azure.com) uyumluluk durumunu izleyebilirsiniz. Azure portalında, ilkeden etkilenen kullanıcılar hakkında bilgiler, uyumluluk durumu ve kullanıcılarınızın karşılaşmış olabileceği sorunlar bulunur.
## <a name="summary-view"></a>Özet görünümü
**Intune mobil uygulama yönetimi** dikey penceresinde, uyumluluk durumunun özetini görebilirsiniz:


![Intune mobil uygulama yönetimi dikey penceresinde Özet kutucuğu](../media/mam-azure-portal-user-status-summary.png)

-   **Kullanıcılar:** Şirketinizde ilkeyle ilişkilendirilmiş uygulamaları kullanan kullanıcıların toplam sayısı.

-   **İLKEYLE YÖNETİLEN**: Uygulamalardan en az birini iş bağlamında kullanmış olan kullanıcıların sayısı.

-   **İLKE YOK**: İlkeyle ilişkilendirilmiş uygulamaları kullanan ancak ilkenin hedeflediği kullanıcılar arasında yer almayan kullanıcıların sayısı. Bu kullanıcıları ilkeye eklemeyi düşünebilirsiniz.

- **Bayrak eklenen kullanıcılar:** Sorun yaşayan kullanıcıların sayısı. Şu anda yalnızca jailbreak uygulanmış cihazlara sahip kullanıcılar, **Bayrak eklenen kullanıcılar** kapsamında raporlanır.


## <a name="detailed-view"></a>Ayrıntılı görünüm
**Kullanıcı durumu** kutucuğuna ve **Bayrak eklenen kullanıcılar** kutucuğunu seçerek özetin ayrıntılı görünümünü elde edebilirsiniz.

### <a name="user-status"></a>Kullanıcı durumu
Tek bir kullanıcıyı arayabilir ve o kullanıcının uyumluluk durumunu denetleyebilirsiniz. **Uygulama raporlama** dikey penceresinde, seçilen kullanıcı için aşağıdaki bilgiler görüntülenir:
- Kullanıcı hesabıyla ilişkilendirilmiş cihazlar

- Cihazda MAM ilkesine sahip uygulamalar

- Durum:

  - **Giriş yaptı:** İlke kullanıcıya dağıtılmış ve uygulama en az bir kez iş bağlamında kullanılmıştır.

  - **Giriş yapmadı**: İlke kullanıcıya dağıtılmış, ancak o zaman beri uygulamanın iş bağlamında kullanılmamıştır.

>[!NOTE]
> Aradığınız kullanıcıya MAM ilkesi dağıtılmamışsa, kullanıcının hiçbir uygulama ilkesinde hedeflenmediğini bildiren bir ileti görürsünüz.

Kullanıcının raporlamasını görmek için şu adımları izleyin:

1.  Kullanıcı seçmek için **Özet** kutucuğuna tıklayın veya **Ayarlar** dikey penceresinde **KULLANICI TARAFINDAN UYGULAMA RAPORLAMA**’yı seçin:

    ![Ayarlar dikey penceresinde Uygulama raporlama seçeneği](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. Açılan **Uygulama raporlama** dikey penceresinde Bir Azure Active Directory kullanıcısını aramak için **Kullanıcı seç** öğesini seçin.

    ![Uygulama raporlama dikey penceresinde kullanıcı seç seçeneği](../media/mam-azure-portal-app-reporting-select-user.png)

3. Listeden kullanıcı seçin. Bu kullanıcı için uyumluluk durumuna ilişkin ayrıntıları görürsünüz.

    ![Uygulama raporlama ayrıntıları](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Bayrak eklenen kullanıcılar
Ayrıntılı görünümde hata iletisi, hata oluştuğunda erişilmiş olan uygulama, cihazın platformu ve zaman damgası gösterilir.  

### <a name="see-also"></a>Ayrıca bkz.
[iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


