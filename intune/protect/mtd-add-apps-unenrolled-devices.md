---
title: Kayıtlı olmayan cihazlara mobil tehdit savunma uygulamaları ekleme
titleSuffix: Microsoft Intune
description: Cihaz kullanıcılarına kayıtlı olmayan cihazlara mobil tehdit savunma uygulamaları ekleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/24/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: a0d1574599b9e514d4bb0289b88ad3c55cc24d15
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782238"
---
# <a name="add-mobile-threat-defense-apps-to-unenrolled-devices"></a>Kayıtlı olmayan cihazlara mobil tehdit savunma uygulamaları ekleme

Varsayılan olarak, Mobile Threat Defense ile Intune uygulama koruma ilkeleri kullanıldığında, Intune, ilgili hizmetlerle bağlantıları etkinleştirmek için tüm gerekli uygulamaları yükleyip oturum açmak üzere cihazındaki son kullanıcıya kılavuzluk etmek üzere çalışır.

Son kullanıcılar, mobil cihazlarında bir tehdit tanımlandığında ve tehditleri düzeltmeye yönelik rehberlik almak için cihazlarını ve mobil tehdit savunması 'nı (Android ve iOS) kaydetmek için Microsoft Authenticator (iOS) gerekir.

İsteğe bağlı olarak, Microsoft Authenticator ve Mobile Threat Defense (MTD) uygulamalarını da eklemek ve dağıtmak için Intune 'U kullanabilirsiniz.

> [!NOTE]
> Bu makale, uygulama koruma ilkelerini destekleyen tüm Mobile Threat Defense iş ortakları için geçerlidir:
>
> - Daha iyi mobil (Android, iOS/ıpados)
> - Zyium (Android, iOS/ıpados)
> - Lookout for Work (Android, iOS/ıpados)
>
> Kayıtlı olmayan cihazlar için, Intune ile kullandığınız iOS uygulaması için mobil tehdit savunması 'nı ayarlayan **bir iOS uygulama yapılandırma ilkesine ihtiyacınız yoktur** . Bu, Intune 'a kayıtlı cihazlara kıyasla önemli bir farktır.

## <a name="configure-microsoft-authenticator-for-ios-via-intune-optional"></a>İOS için Microsoft Authenticator Intune aracılığıyla yapılandırma (isteğe bağlı)

Intune uygulama koruma ilkelerini Mobile Threat Defense ile birlikte kullanırken Intune, son kullanıcının cihazlarını Microsoft Authenticator (iOS) ile yüklemesine, oturum açmasını ve kaydolmasıyla ilgili rehberlik edecektir.

Ancak, uygulamayı Intune Şirket Portalı aracılığıyla son kullanıcılar için kullanılabilir hale getirmek istemeniz gerekir. [Microsoft Intune iOS Mağazası uygulamaları ekleme](../apps/store-apps-ios.md)yönergelerine bakın. **Uygulama bilgilerini Yapılandır** bölümünü tamamlarken bu [Microsoft Authenticator-iOS Uygulama Mağazası URL 'sini](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) kullanın. Son adım olarak [Intune ile gruplara uygulama atamayı](../apps/apps-deploy.md) unutmayın.

> [!NOTE]
> iOS cihazlarında, Azure AD'nin kullanıcıların kimlikleri denetleyebilmesi için [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) olması gerekir. Intune Şirket Portalı, kullanıcıların kimliklerinin Azure AD tarafından denetlenmesi için Android cihazlarda aracı olarak kullanılır.

## <a name="making-mobile-threat-defense-apps-available-via-intune-optional"></a>Mobil tehdit savunması uygulamalarını Intune aracılığıyla kullanılabilir hale getirme (isteğe bağlı)

Intune uygulama koruma ilkelerini Mobile Threat Defense ile birlikte kullanırken Intune, son kullanıcıya gerekli mobil tehdit savunma istemci uygulamasını yükleyip oturum açmaya kılavuzluk eder.

Ancak, uygulamayı Intune Şirket Portalı aracılığıyla son kullanıcılar için kullanılabilir hale getirmek istemeniz gerekir, [Azure Portal](https://portal.azure.com/)aşağıdaki adımları izleyebilirsiniz. Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

- [Intune’a uygulama ekleme](../apps/apps-add.md).
- [Intune ile uygulama atama](../apps/apps-deploy.md).

### <a name="making-lookout-for-work-available-to-end-users"></a>Lookout for Work son kullanıcılara kullanılabilir hale getirme

- **Android**  
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **Uygulama bilgilerini Yapılandır** bölümünü tamamlarken bu [Lookout for Work Play Store URL 'sini](https://play.google.com/store/apps/details?id=com.lookout.enterprise) kullanın.

- **iOS**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **Uygulama bilgilerini Yapılandır** bölümünü tamamlarken bu [Lookout for Work-iOS Uygulama Mağazası URL 'sini](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) kullanın.

<!-- ### Making Symantec Endpoint Protection Mobile available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). When completing the **Configure app information** section, use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure). For **Minimum operating system**, select **Android 4.0 (Ice Cream Sandwich)**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [SEP Mobile - App Store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) when completing the **Configure app information** section.

### Making Check Point SandBlast Mobile available to end users
- **Android**  
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) when completing the **Configure app information** section. 

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile - App Store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) when completing the **Configure app information** section. -->

### <a name="making-zimperium-available-to-end-users"></a>Son kullanıcılar için Zkusuri kullanılabilir hale getirme

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **Uygulama bilgilerini Yapılandır** bölümünü tamamlarken bu [zlaium-Play Store URL 'sini](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) kullanın.
- **iOS**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **Uygulama bilgilerini Yapılandır** bölümünü tamamlarken bu [zlaium-App Store URL 'sini](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) kullanın.

<!-- ### Making Pradeo available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Pradeo - Play Store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Pradeo - App Store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) when completing the **Configure app information** section. -->

### <a name="making-better-mobile-available-to-end-users"></a>Son kullanıcılar için daha Iyi mobil kullanıma hazır hale getirme

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **Uygulama bilgilerini Yapılandır** bölümünü tamamlarken bu [etkin Shield-Play Store URL 'sini](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) kullanın.

<!-- - **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) when completing the **Configure app information** section. -->

<!-- ### Making Sophos available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Sophos - Play Store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) when completing the **Configure app information** section.

### Making Wandera available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Wandera Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.wandera.android) when completing the **Configure app information** section. For **Minimum operating system**, select **Android 5.0**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Wandera Mobile - - App Store URL](https://itunes.apple.com/app/wandera/id605469330) when completing the **Configure app information** section. -->

## <a name="next-steps"></a>Sonraki adımlar

- [Kayıtlı olmayan cihazlar için Intune 'da Mobile Threat Defense bağlayıcısını etkinleştirme](~/protect/mtd-enable-unenrolled-devices.md)