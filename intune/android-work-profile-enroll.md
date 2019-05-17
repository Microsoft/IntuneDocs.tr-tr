---
title: Android Kurumsal iş profili cihazlarını Intune’a kaydetme
titleSuffix: Microsoft Intune
description: Android Kurumsal iş profili cihazlarını Intune’a nasıl kaydedeceğinizi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a86eaece208d1c8ea1737acde74c74ef633eea0
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59901140"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Android Kurumsal iş profili cihazların kaydını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, iş bilgileriyle kişisel bilgilerin ayrı olmasını sağlamak için Android Kurumsal iş profili cihazlarına uygulamalar ve ayarlar dağıtmanıza yardımcı olur. Android Kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Android Kurumsal iş profili yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. [Intune kiracı hesabınızı Android Kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
2. Android Kurumsal iş profili kayıt ayarlarını belirtin. Android Kurumsal iş profilleri, [yalnızca belirli Android cihazlarda desteklenmektedir](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Android Kurumsal iş profilini destekleyen tüm cihazlar geleneksel Android yönetimini de destekler. Intune, Android Kurumsal iş profilini destekleyen cihazların [Kayıt Kısıtlamaları](enrollment-restrictions-set.md) içerisinde nasıl yönetileceğini belirtmenize olanak sağlar.
    - **Engelle (varsayılan ayar)**:  Android Kurumsal iş profilini destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar, geleneksel Android cihaz olarak kaydedilir.
    - **İzin ver**: Android Kurumsal iş profilini destekleyen tüm cihazlar, Android Kurumsal iş profili cihazları olarak kaydedilir. Android Kurumsal iş profilini desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.
3. [Kullanıcılarınıza cihazlarını nasıl kaydedeceklerini anlatın](/intune-user-help/create-a-work-profile-and-enroll-your-device-in-intune-android).  


Android Kurumsal iş profillerini kullanarak cihaz kaydetmek istiyorsanız ancak bu cihazlar zaten normal Android cihazlar olarak kayıtlıysa, cihazları kaldırıp yeniden kaydetmeniz gerekir.

Android Kurumsal iş profili cihazlarını bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabı kullanarak kaydediyorsanız, hesap başına en fazla 10 cihaz kaydedebilirsiniz.

Daha fazla bilgi için bkz. [Intune’un Google’a gönderdiği veriler](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Yönetilen Google Play Store'da Şirket Portalı uygulamasını onaylama

Kullanıcıların her zaman en güncel Şirket Portalı uygulamasına sahip olduklarından emin olmak için Yönetilen Google Play mağazasında Android için Şirket Portalı uygulamasını onaylamanız gerekir. Bunu onaylayarak tüm kullanıcıların otomatik güncelleştirmeler almasını sağlarsınız. Onaylamazsanız, Şirket Portalı zamanla güncelliğini yitirir ve Microsoft'un kullanıma sunduğu önemli hata düzeltmelerini veya yeni özellikleri alamaz.

Intune Şirket Portalı'nı onaylamak için aşağıdaki adımları izleyin:

1.  [Yönetilen Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal)’da Şirket Portalı uygulamasına göz atın.
2.  Yönetilen Google Play mağazasında, Android Kurumsal bağlamasını yapılandırırken kullandığınız Google hesabıyla oturum açın.
3.  **Onayla**’ya tıkladığınızda yeni bir iletişim kutusu açılır.
4.  Bu iletişim kutusunda izinleri gözden geçirin ve ardından **Onayla**'ya tıklayın. Şirket Portalı uygulamasının cihazdaki iş profilini yönetmesine olanak tanımak için bu izinlerin verilmesi gerekir.
5.  **Uygulama yeni izinler istediğinde onaylı durumda tut** öğesini seçin ve **Kaydet**'e tıklayın.

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Android Kurumsal iş profilleri için sonraki adımlar
- [Android Kurumsal iş profili uygulamalarını dağıtma](apps-add-android-for-work.md)
- [Android Kurumsal iş profili yapılandırma ilkeleri ekleme](device-profiles.md)
