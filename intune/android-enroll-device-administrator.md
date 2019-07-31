---
title: Android Cihaz Yöneticisi kaydı Microsoft Intune
titleSuffix: ''
description: Cihaz yönetici kaydını kullanarak Android cihazlarını Intune 'a kaydetme.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdd3bf3bfdbc14f4324da4b5edc8d131f3f4f170
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671185"
---
# <a name="android-device-administrator-enrollment"></a>Android Cihaz Yöneticisi kaydı

Android Cihaz Yöneticisi (bazen "eski" Android yönetimi ve Android 2,2 ile kullanıma sunulan) Android cihazlarını yönetmenin bir yoludur. Ancak, geliştirilmiş yönetim işlevselliği artık [Android Enterprise](https://www.android.com/enterprise/management/) (Android 5,0 ile yayımlanmıştır) ile kullanılabilir. Modern, daha zengin ve daha güvenli cihaz yönetimine geçiş çabasında, Google yeni Android sürümlerindeki Cihaz Yöneticisi desteğini düşürdüğünde.

Bu nedenle, bu tür azaltılmış işlevselliği önlemek için aşağıda açıklanan Cihaz Yöneticisi işlemini kullanarak yeni cihazların kaydedilmesini öneririz.

Aynı nedenlerden dolayı, cihazların Android 10 ' a güncelleyecekse Cihaz Yöneticisi yönetiminden da cihazları geçirmeniz önerilir. 

Android cihaz yöneticisi desteği için Intune desteği hakkında daha fazla bilgi için [Bildirimler bölümüne](whats-new.md#decreasing-support-for-android-device-administrator)bakın.

Kullanıcıların, Android cihazlarını Cihaz Yöneticisi yönetimine kaydetmesine hala karar verirseniz, sonraki bölüme geçin.  


> [!Note]  
> Android 10 ve üzeri, karma mobil cihaz yönetiminde (Hibrit MDM;) desteklenmez. Karma MDM, 1 Eylül 2019 ' de hizmet dışına alındığından, System Center Configuration Manager konsolu ile yönetilen Intune). Karma MDM kullanmaya devam ediyorsanız, mümkün olan en kısa sürede Intune 'a geçiş yapmanız gerekir. Geçiş için yardıma ihtiyacınız varsa destek ekibiyle iletişime geçin. Daha fazla bilgi için bkz. [Karma Mobil Cihaz Yönetiminden Azure’da Intune’a geçme](https://aka.ms/hybrid_notification).

Google 'ın Android kurumsal özellikleri hakkında daha fazla bilgi için şu makalelere bakın:
- [Google 'ın cihaz yöneticisinden Android kuruluşa geçiş kılavuzu](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google 'ın Cihaz Yöneticisi API 'sini kullanımdan kaldırma planına yönelik belgeleri](https://developers.google.com/android/work/device-admin-deprecation)


## <a name="set-up-device-administrator-enrollment"></a>Cihaz yönetici kaydını ayarlama

Intune varsayılan olarak, Cihaz Yöneticisi özelliklerine sahip Android cihazların kaydına izin verir.

1. Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](mdm-authority-set.md). Bu öğeyi, mobil cihaz yönetimi için ilk olarak Intune 'u ayarlarken tek bir kez ayarlarsınız.
2. [Kullanıcılarınıza cihazlarını nasıl kaydedeceklerini anlatın](/intune-user-help/enroll-your-device-in-intune-android).  

Bir kullanıcı kaydolduktan sonra [uyumluluk ilkeleri atama](compliance-policy-create-android.md), [uygulamaları yönetme](app-management.md) ve daha fazlası dahil olmak üzere kullanıcının cihazlarını Intune’da yönetmeye başlayabilirsiniz.

Diğer kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:
- [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md)
- [Android cihazınızı Intune ile kullanma](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)


## <a name="block-device-administrator-enrollment"></a>Cihaz Yöneticisi kaydını engelle
Android Cihaz Yöneticisi cihazlarını engellemek veya yalnızca kişisel Android Cihaz Yöneticisi cihazlarının kaydını engellemek için bkz. [cihaz türü kısıtlamalarını ayarlama](enrollment-restrictions-set.md).



## <a name="next-steps"></a>Sonraki adımlar
- [Uyumluluk ilkeleri atama](compliance-policy-create-android.md)
- [Uygulamaları yönetme](app-management.md)