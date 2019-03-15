---
title: Android kurumsal iş profili cihazları ıntune'a kaydetme
titlesuffix: Microsoft Intune
description: Intune'da Android kurumsal iş profili cihazları kaydetmeyi öğrenin.
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
ms.openlocfilehash: 554bf209b71d03a95245d656f19a029af6e67a52
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394953"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Android kurumsal iş profili cihazların kaydını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, iş ve kişisel bilgilerin ayrı olduğundan emin olmak için Android kurumsal iş profili cihazları için uygulama ve ayarları dağıtmanıza yardımcı olur. Belirli Android Enterprise hakkında bilgi için [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Android kurumsal iş profilinin yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. [Android Enterprise hesabınızı Intune Kiracı hesabınızı bağlayın](connect-intune-android-enterprise.md).
2. Android kurumsal iş profili kayıt ayarlarını belirtin. Android kurumsal iş profilleri olan [yalnızca belirli Android cihazlarda desteklenen](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Android Enterprise çalışma profillerini destekleyen tüm cihazlar geleneksel Android yönetimini de destekler. Intune, Android Enterprise çalışma profillerini destekleyen cihazlar içinden nasıl yönetileceğinizi belirtmenize olanak tanır [kayıt kısıtlamaları](enrollment-restrictions-set.md).
    - **Engelle (varsayılan ayar)**:  Android Enterprise çalışma profillerini destekleyen cihazlar da dahil olmak üzere tüm Android cihazlar geleneksel Android cihaz olarak kaydedilir.
    - **İzin**: Android iş profilleri Android Kurumsal kaydedilen Kurumsal destekleyen tüm cihazlar profili cihazları çalışır. Android kurumsal iş profilleri desteklemeyen herhangi bir Android cihaz, geleneksel Android cihaz olarak kaydedilir.
3. [Kullanıcılarınıza cihazlarını nasıl kaydedeceklerini anlatın](/intune-user-help/enroll-your-device-in-intune-android).


Android kurumsal iş profilleri kullanarak cihazları kaydetme istediğiniz, ancak bu cihazlar zaten normal Android cihazlar olarak kaydedilen cihazları ilk kaydını ve yeniden kaydetmeniz gerekir.

Kullanarak Android kurumsal iş profili cihazları kaydetmenin, bir [cihaz kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabı, hesap başına kayıtlı 10 cihaz sınırı yoktur.

Daha fazla bilgi için bkz. [Intune’un Google’a gönderdiği veriler](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Yönetilen Google Play Store'da Şirket portalı uygulamasını onaylama

Kullanıcıların her zaman erişim için Şirket portalı uygulamasının en güncel sürümüne sahip olmasını sağlamak için yönetilen Google Play Store'da, Android için Şirket portalı uygulamasını onaylamanız gerekir. Bunu onaylayarak tüm kullanıcıların otomatik güncelleştirmeler almasını sağlarsınız. Onaylamazsanız, Şirket Portalı zamanla güncelliğini yitirir ve Microsoft'un kullanıma sunduğu önemli hata düzeltmelerini veya yeni özellikleri alamaz.

Intune Şirket Portalı'nı onaylamak için aşağıdaki adımları izleyin:

1.  Şirket portalı uygulamasına göz atın [yönetilen Google Play store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Yönetilen Google Play store Android Kurumsal yapılandırmak için kullandığınız aynı Google hesabı ile oturum açın.
3.  **Onayla**’ya tıkladığınızda yeni bir iletişim kutusu açılır.
4.  Bu iletişim kutusunda izinleri gözden geçirin ve ardından **Onayla**'ya tıklayın. Şirket Portalı uygulamasının cihazdaki iş profilini yönetmesine olanak tanımak için bu izinlerin verilmesi gerekir.
5.  **Uygulama yeni izinler istediğinde onaylı durumda tut** öğesini seçin ve **Kaydet**'e tıklayın.

## <a name="next-steps-for-android-enterprise-work-profiles"></a>İş profilleri Android Enterprise için sonraki adımlar
- [Android kurumsal iş profili uygulamaları dağıtma](apps-add-android-for-work.md)
- [Android kurumsal iş profili yapılandırma ilkeleri ekleme](device-profiles.md)
