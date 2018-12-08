---
title: Intune’da Android cihazları kaydetme
titlesuffix: Microsoft Intune
description: Intune’da Android cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 79a1a03f74db8e44dc3ee4d6575e193ce7841e24
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53031900"
---
# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune yöneticisi olarak, aşağıdaki Android cihazları yönetebilirsiniz:
- Samsung Knox Standard cihazlar dahil olmak üzere Android cihazlar.
- [Android iş profili cihazları](#enable-enrollment-of-android-for-work-devices) ve Android bilgi noktası cihazları dahil olmak üzere Android kurumsal cihazlar.

Samsung Knox Standard çalıştıran cihazlarda Intune ile birden çok kullanıcı yönetimi gerçekleştirilebilir. Yani son kullanıcılar kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir ve kapatabilir. Cihaz kullanılsa da kullanılmasa da merkezi olarak yönetilir. Son kullanıcılar oturum açtıklarında, uygulamalara erişir ve ek olarak kendilerine uygulanan ilkeler varsa bunları alırlar. Kullanıcılar oturumu kapattığında tüm veriler silinir.

## <a name="prerequisite"></a>Önkoşul

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlayabilirsiniz.

## <a name="set-up-android-enrollment"></a>Android kaydını ayarlama

Intune, Android ve Samsung Knox Standard cihazlarının kaydına varsayılan olarak izin verir. Önkoşulu sağladıktan sonra yöneticilerin yapacağı tek şey [kullanıcılarına cihazlarını nasıl kaydedeceklerini anlatmak](/intune-user-help/enroll-your-device-in-intune-android) olacaktır.

Bir kullanıcı kaydolduktan sonra [uyumluluk ilkeleri atama](compliance-policy-create-android.md), [uygulamaları yönetme](app-management.md) ve daha fazlası dahil olmak üzere kullanıcının cihazlarını Intune’da yönetmeye başlayabilirsiniz.

Diğer kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:

- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Android cihazların veya yalnızca kişisel Android cihazların kaydedilmesini engellemek için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

## <a name="set-up-android-enterprise-enrollment"></a>Android kurumsal kaydını ayarlama

Android iş profili, kişisel uygulamaları ve verileri uygulama ve veri içeren iş profilinden ayıran Android cihazı özellik ve hizmet kümesidir. Android kurumsal cihazları, iş profili cihazları ve bilgi noktası cihazlarını içerir. 

Android kurumsal cihazların kaydını ayarlamak için önce [Android kurumsalı Intune’a bağlamanız](connect-intune-android-enterprise.md) gerekir. Bu adımı tamamladıktan sonra şunları yapabilirsiniz:

[Android iş profili kayıtlarını ayarlama](android-work-profile-enroll.md)
[Android bilgi noktası kayıtlarını ayarlama](android-kiosk-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Bir Samsung Knox cihazı kaydederken son kullanıcı deneyimi
Samsung Knox cihazları kaydederken göz önünde bulundurulması gereken birkaç nokta vardır:
-   Hiçbir ilke PIN gerektirmiyorsa bile cihazın kaydedilebilmesi için en az dört basamaklı bir PIN’i olmalıdır. Cihazın PIN’i yoksa, kullanıcıdan bir PIN oluşturması istenir.
-   Workplace Join Sertifikaları (WPJ) için kullanıcı etkileşimi yoktur.
-   Kullanıcıya Hizmet Kaydı bilgileri ve uygulamanın yapabilecekleri anlatılır.
-   Kullanıcıya Knox Kaydı bilgileri ve Knox’un yapabilecekleri anlatılır.
-   Bir Şifreleme İlkesi zorlanmışsa, kullanıcıların cihaz geçiş kodu olarak altı karakterlik karmaşık parola ayarlamaları gereklidir.
-   Şirket Kaynağı Erişimi için bir hizmet tarafından gönderilen sertifikaların yüklenmesi için başka kullanıcı istemi yoktur.
- Bazı eski Knox cihazlar, kullanıcıdan Şirket Kaynağı Erişimi için kullanılan ek sertifikalar isteyebilir.
- Bir Samsung Mini cihaz, **Sertifika Bulunamadı** veya **Cihaz Kaydedilemedi** hataları ile WPJ’yi yükleyemezse, en son Samsung Üretici Yazılımı Güncelleştirmelerini yükleyin.
