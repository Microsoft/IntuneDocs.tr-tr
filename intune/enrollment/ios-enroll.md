---
title: Intune 'da iOS/ıpados cihazlarını kaydetme
titleSuffix: Microsoft Intune
description: Microsoft Intune 'de iOS/ıpados cihazlarının kaydını ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d5aeb17084ea0bb76429b1fa15c9de5855220ab
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415288"
---
# <a name="enroll-iosipados-devices-in-intune"></a>Intune 'da iOS/ıpados cihazlarını kaydetme

Intune, kullanıcıların şirket e-postasına, verilerine ve uygulamalarına güvenli bir şekilde erişmesini sağlamak için, IPads ve IPhone 'ın mobil cihaz yönetimi (MDM) sağlar.

Bir Intune Yöneticisi olarak iOS/ıpados ve ıpados cihazlarının kaydını şirket kaynaklarına erişecek şekilde ayarlayabilirsiniz. Kullanıcıların, "kendi cihazını getir" (BYOD) kaydı olarak bilinen, kişisel cihazları kaydetmelerini sağlayabilirsiniz. Ayrıca, şirkete ait cihazların kaydını da ayarlayabilirsiniz.

## <a name="prerequisites-for-iosipados-enrollment"></a>İOS/ıpados kaydı önkoşulları

İOS/ıpados cihazlarını etkinleştirebilmeniz için aşağıdaki adımları izleyin:

- [Cihazınızın Apple cihaz kaydına uygun olduğundan emin olun](https://support.apple.com/en-us/HT204142#eligibility).
- [Intune’u ayarlama](../fundamentals/setup-steps.md) - Bu adımlar, Intune altyapınızı ayarlar. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](../fundamentals/mdm-authority-set.md) gerektirir.
- [Apple MDM anında iletme sertifikası alma](apple-mdm-push-certificate-get.md) -Apple, ıoios/ıpados ve MacOS cihazlarının yönetimini etkinleştirmek için bir sertifika gerektirir.

## <a name="user-owned-iosipados-and-ipados-devices-byod"></a>Kullanıcıya ait iOS/ıpados ve ıpados cihazları (KCG)

Kullanıcıların kendi cihazlarını Intune yönetimine kaydetmesine izin verebilirsiniz. Bu, “kendi cihazını getir” veya KCG olarak bilinir. Kullanıcıları kaydetmek için üç seçenek vardır:
- Uygulama koruma Ilkeleri size yalnızca uygulama düzeyinde yönetim sağlayan en hafif KCG deneyimini sağlar. Bununla birlikte, cihazı 6 basamaklı bir karmaşık PIN ile de korumak istiyorsanız, bu ilkeleri kullanıcı kaydıyla birlikte kullanabilirsiniz.
- Cihaz kaydı, tipik KCG kaydı olarak düşünebilir. Yöneticilere çok çeşitli yönetim seçenekleri sağlar.
- Kullanıcı kaydı, yöneticilere cihaz yönetimi seçeneklerinin bir alt kümesini sağlayan daha kolay bir kayıt işlemidir. Bu özellik şu anda önizleme sürümündedir. 

Önkoşulları ve atanan kullanıcı lisanslarını tamamladıktan sonra, kullanıcılar Intune Şirket Portalı uygulamayı App Store 'dan indirebilir ve uygulamadaki kayıt talimatlarını takip edebilir. İOS/ıpados cihazlarında Şirket Portalı gizlilik bildirimini [Gizlilik bildirimi özelleştirmesi](../apps/company-portal-app.md#privacy-statement-customization)bölümünde açıklandığı gibi özelleştirebilirsiniz.

## <a name="company-owned-iosipados-devices"></a>Şirkete ait iOS/ıpados cihazları

Intune, kullanıcıları için cihaz satın alan kuruluşlar için aşağıdaki iOS/ıpados şirkete ait cihaz kayıt yöntemlerini destekler:

- Apple’ın Aygıt Kayıt Programı (DEP)
- Apple School Manager
- Apple Configurator Kurulum Yardımcısı kaydı
- Apple Configurator ile doğrudan kayıt

Ayrıca, şirkete ait iOS/ıpados cihazlarını bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabıyla kaydedebilirsiniz.

## <a name="device-enrollment-program"></a>Cihaz Kaydı Programı

Kuruluşlar, Apple 'ın Aygıt Kayıt Programı (DEP) aracılığıyla iOS/ıpados cihazları satın alabilir. DEP, cihazları yönetime kaydetmek için bir kayıt profilini “uzaktan” dağıtmanıza imkan tanır. Daha fazla bilgi için bkz. [aygıt kayıt programı](device-enrollment-program-enroll-ios.md).

## <a name="user-enrollment"></a>Kullanıcı kaydı
Kullanıcı kaydı, yöneticilere diğer kayıt yöntemleriyle karşılaştırıldığında yönetim seçeneklerinin bir alt kümesini sağlar. Daha fazla bilgi için, bkz. [Kullanıcı kaydı desteklenen eylemler, parolalar ve diğer seçenekler](ios-user-enrollment-supported-actions.md) ve [IOS/ıpados ve ıpados Kullanıcı kaydını ayarlama](ios-user-enrollment.md).

## <a name="apple-school-manager"></a>Apple School Manager

Apple School Manager, okullar için oluşturulmuş bir cihaz satın alma ve kayıt programıdır. DEP’te olduğu gibi cihazları yönetime kaydetmek için bir profil dağıtabilirsiniz. [Apple School Manager](apple-school-manager-set-up-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-configurator"></a>Apple Configurator

Bir Mac bilgisayarda çalışan Apple Configurator ile iOS/ıpados cihazlarını kaydedebilirsiniz. Cihazları hazırlamak için USB ile bağlayıp onlara bir kayıt profili yüklersiniz. Cihazları Apple Configurator ile iki şekilde kaydedebilirsiniz:

- Kurulum Yardımcısı kaydı - Cihazı siler, Kurulum Yardımcısı’nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükler.
- Doğrudan kayıt - Cihazı silmez ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, kullanıcı benzeşimi olmayan cihazlar içindir.

[Apple Configurator kaydı](apple-configurator-enroll-ios.md) hakkında daha fazla bilgi edinin.

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>DEP veya Apple Configurator ile kaydedilmiş cihazlarda Şirket Portalı’nı kullanma

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için bir dizi ek adımı tamamlamalıdır.

Aşağıdakileri desteklemek için kullanıcı benzeşimi gereklidir:

- Mobil uygulama yönetimi (MAM) uygulamaları
- E-posta ve şirket verilerine koşullu erişim
- Şirket Portalı uygulaması

### <a name="how-users-enroll-corporate-owned-iosipados-devices-with-user-affinity"></a>Kullanıcıların, Kullanıcı benzeşimi olan şirkete ait iOS/ıpados cihazlarını nasıl kaydetmeleri

1. Kullanıcılar cihazlarını açtığında, kendilerinden Kurulum Yardımcısı’nı tamamlamaları istenir.
2. Kurulum tamamlandıktan sonra kullanıcılardan bir Apple kimliği istenir. Cihazın Şirket Portalı’nı yüklemesine izin vermek için bir Apple kimliği sağlanmalıdır.
3. İOS/ıpados cihazı Şirket Portalı uygulamasını App Store 'dan otomatik olarak yüklenir.
4. Kullanıcılar, Şirket Portalı uygulamasını başlatıp Intune abonelikleriyle ilişkili kimlik bilgilerini (benzersiz kişisel ad veya UPN gibi) kullanarak oturum açmalıdır.
5. Oturum açtıktan sonra kayıt tamamlanır. Kullanıcılar artık bu cihazı tüm özellikleriyle kullanabilir.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Kullanıcı benzeşimi olmayan şirkete ait yönetilen cihazlar hakkında

Hiçbir kullanıcı benzeşimi olmadan yapılandırılmış cihazlar, Şirket Portalı’nı desteklemez ve uygulamayı yüklememelidir. Şirket Portalı, kurumsal kimlik bilgileri olan ve kişiselleştirilmiş şirket kaynaklarına (e-posta gibi) erişmesi gereken kullanıcılar için tasarlanmıştır. Kullanıcı benzeşimi olmadan kaydedilmiş cihazlarda adanmış kullanıcı oturumu kullanılmamalıdır. Bilgi noktası, satış noktası (POS) veya paylaşılan yardımcı cihazlar, kullanıcı benzeşimi olmadan kaydedilen cihazların tipik kullanım örnekleridir.

Kullanıcı benzeşimi gerekiyorsa, cihazın kaydolma profilinde cihaz kaydedilmeden önce **Kullanıcı Benzeşimi**’nin seçildiğinden emin olun. Bir cihazdaki benzeşim durumunu değiştirmek için cihazı kullanımdan kaldırıp tekrar kaydetmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Intune iOS/ıpados cihaz kaydı sorunlarını giderme](https://support.microsoft.com/help/4039809)
