---
title: Android iş profili cihazlarını Intune’a kaydetme
titlesuffix: Microsoft Intune
description: Android iş profili cihazlarını Intune’a nasıl kaydedeceğinizi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 095985bad8f7e35a953383fcce8296716723b8bc
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909074"
---
# <a name="set-up-enrollment-of-android-work-profile-devices"></a>Android iş profili cihazların kaydını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, iş bilgileriyle kişisel bilgilerin ayrı olmasını sağlamak için Android iş profili cihazlarına uygulamalar ve ayarlar dağıtmanıza yardımcı olur. Android kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Android iş profili yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. [Intune kiracı hesabınızı Android kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
2. Android iş profili kayıt ayarlarını belirtin. Android iş profilleri, [yalnızca belirli Android cihazlarda desteklenmektedir](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Android iş profili destekleyen tüm cihazlar geleneksel Android yönetimini de destekler. Intune, Android iş profilini destekleyen cihazların [Kayıt Kısıtlamaları](enrollment-restrictions-set.md) içerisinde nasıl yönetileceğini belirtmenize olanak sağlar.
    - **Engelle (varsayılan ayar)**: Android iş profili destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar, geleneksel Android cihaz olarak kaydedilir.
    - **İzin ver**: Android iş profili destekleyen tüm cihazlar, Android iş profili cihazları olarak kaydedilir. Android iş profilini desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.
3. [Kullanıcılarınıza cihazlarını nasıl kaydedeceklerini anlatın](/intune-user-help/enroll-your-device-in-intune-android.md).


Android iş profiline cihaz kaydetmek istiyorsanız ancak bu cihazlar zaten normal Android cihazlar olarak kayıtlıysa, cihazları kaldırıp yeniden kaydetmeniz gerekir.

Android iş profili cihazlarını bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabı kullanarak kaydediyorsanız, hesap başına en fazla 10 cihaz kaydedebilirsiniz.

Daha fazla bilgi için bkz. [Intune’un Google’a gönderdiği veriler](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Yönetilen Google Play Store'da Şirket Portalı uygulamasını onaylama

Kullanıcıların her zaman en güncel Şirket Portalı uygulamasına sahip olduklarından emin olmak için yönetilen Google Play mağazasında Android için Şirket Portalı uygulamasını onaylamanız gerekir. Bunu onaylayarak tüm kullanıcıların otomatik güncelleştirmeler almasını sağlarsınız. Onaylamazsanız, Şirket Portalı zamanla güncelliğini yitirir ve Microsoft'un kullanıma sunduğu önemli hata düzeltmelerini veya yeni özellikleri alamaz.

Intune Şirket Portalı'nı onaylamak için aşağıdaki adımları izleyin:

1.  [Yönetilen Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal)’da Şirket Portalı uygulamasına göz atın.
2.  Yönetilen Google Play mağazasında, Android kurumsal bağlamasını yapılandırırken kullandığınız Google hesabıyla oturum açın.
3.  **Onayla**’ya tıkladığınızda yeni bir iletişim kutusu açılır.
4.  Bu iletişim kutusunda izinleri gözden geçirin ve ardından **Onayla**'ya tıklayın. Şirket Portalı uygulamasının cihazdaki iş profilini yönetmesine olanak tanımak için bu izinlerin verilmesi gerekir.
5.  **Uygulama yeni izinler istediğinde onaylı durumda tut** öğesini seçin ve **Kaydet**'e tıklayın.

## <a name="next-steps-for-android-work-profiles"></a>Android iş profilleri için sonraki adımlar
- [Android iş profili uygulamalarını dağıtma](store-apps-android.md)
- [Android iş profili yapılandırma ilkeleri ekleme](device-profiles.md)