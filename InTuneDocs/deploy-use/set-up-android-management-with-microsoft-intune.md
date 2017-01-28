---
title: "Android yönetimini kurma | Microsoft Docs"
description: "Microsoft Intune ile Android ve KNOX Standard cihazlar için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ddc03985ab8a4959a1d2c9a47e77f042ab9310
ms.openlocfilehash: 6b74c09c37970429d3eaa571db655854d592a2fe


---

# <a name="set-up-android-device-management"></a>Android cihaz yönetimini ayarlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bir Intune yöneticisi olarak Samsung Knox Standard cihazlar da dahil olmak üzere Android cihazlarının yönetimini Şirket Portalı’ndan etkinleştirebilirsiniz. Kullanıcılar, cihazlarını Google Play’den edinilebilecek Şirket Portalı uygulamasını kullanarak kaydedebilir.

1.  **Intune’u ayarlama**<br>
    Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](prerequisites-for-enrollment.md#step-2-set-mdm-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2.  **Android kaydı etkinleştirildi**<br>
    Android mobil cihaz kaydının etkinleştirilmesi için Intune konsolunda gerekli olan ek yapılandırma yoktur.

3.  **Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın.**

    Son kullanıcı kayıt talimatları için bkz. [Android cihazınızı Intune'a kaydetme](../enduser/enroll-your-device-in-intune-android.md). Kayıt işlemi kullanıcıları neler bekleyebilecekleri ve BT yöneticilerinin görebileceği ve göremeyeceği cihaz içeriği hakkında bilgilendirir.

    Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:
  - [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](what-to-tell-your-end-users-about-using-microsoft-intune.md)
  - [Android cihazlar için son kullanıcı kılavuzu](../enduser/using-your-android-device-with-intune.md)

Çin’de Google Play Mağazası olmaması nedeniyle, Android cihazların Şirket Portalı’nı Çin’deki uygulama marketlerinden edinmeleri gerekir. Android için Şirket Portalı uygulaması aşağıdaki mağazalardan yüklenebilir:
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

Android için Şirket Portalı uygulaması Microsoft Intune hizmetiyle iletişim kurmak için Google Play Hizmetleri’ni kullanır. Google Play Hizmetleri henüz Çin'de kullanılamadığından, aşağıdaki görevlerin tamamlanması 8 saate kadar sürebilir. 

|Intune Yönetici Konsolu| Android için Intune Şirket Portalı uygulaması |Intune Şirket Portalı Web Sitesi|   
|---|---|---|
|Tam temizleme| Uzak bir cihazı kaldırma| Cihaz kaldırma (yerel ve uzak)|
|Seçmeli temizleme| Cihaz sıfırlama| Cihaz sıfırlama|
|Yeni veya güncelleştirilmiş uygulamaların dağıtımı| Kullanılabilir iş kolu uygulamalarını yükleme| Cihaz geçiş kodu sıfırlama|
|Uzaktan kilitleme|||
|Geçiş kodu sıfırlama|||

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)



<!--HONumber=Jan17_HO1-->


