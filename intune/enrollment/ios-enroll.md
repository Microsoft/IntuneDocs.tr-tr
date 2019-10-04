---
title: İOS cihazlarını Intune 'A kaydetme
titleSuffix: Microsoft Intune
description: Microsoft Intune 'de iOS cihazlarının kaydını ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c4f3424c0d9712affbbf8ba3929e825b62ce5864
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940313"
---
# <a name="enroll-ios-devices-in-intune"></a>İOS cihazlarını Intune 'A kaydetme

Intune, kullanıcıların şirket e-postasına, verilerine ve uygulamalarına güvenli bir şekilde erişmesini sağlamak için, IPads ve IPhone 'ın mobil cihaz yönetimi (MDM) sağlar.

Bir Intune Yöneticisi olarak iOS ve ıpados cihazlarının kaydını şirket kaynaklarına erişecek şekilde ayarlayabilirsiniz. Kullanıcıların, "kendi cihazını getir" (BYOD) kaydı olarak bilinen, kişisel cihazları kaydetmelerini sağlayabilirsiniz. Ayrıca, şirkete ait cihazların kaydını da ayarlayabilirsiniz.

## <a name="prerequisites-for-ios-enrollment"></a>İOS kaydı için Önkoşullar

İOS cihazlarını etkinleştirebilmeniz için aşağıdaki adımları izleyin:

- [Cihazınızın Apple cihaz kaydına uygun olduğundan emin olun](https://support.apple.com/en-us/HT204142#eligibility).
- [Intune 'U ayarlama](../fundamentals/setup-steps.md) -Bu adımlar, Intune altyapınızı ayarlar. Özellikle, cihaz kaydı, [MDM yetkilinizi ayarlamanızı](../fundamentals/mdm-authority-set.md)gerektirir.
- [Apple MDM anında iletme sertifikası alın](apple-mdm-push-certificate-get.md) -Apple, IOS ve MacOS cihazlarının yönetimini etkinleştirmek için bir sertifika gerektirir.

## <a name="user-owned-ios-and-ipados-devices-byod"></a>Kullanıcıya ait iOS ve ıpados cihazları (KCG)

Kullanıcıların kendi kişisel cihazlarını Intune yönetimine kaydetmelerini sağlayabilirsiniz, "kendi cihazını getir" veya KCG olarak bilirsiniz. Kullanıcıları kaydetmek için üç seçenek vardır:
- Uygulama koruma Ilkeleri size yalnızca uygulama düzeyinde yönetim sağlayan en hafif KCG deneyimini sağlar. Bununla birlikte, cihazı 6 basamaklı bir karmaşık PIN ile de korumak istiyorsanız, bu ilkeleri kullanıcı kaydıyla birlikte kullanabilirsiniz.
- Cihaz kaydı, tipik KCG kaydı olarak düşünebilir. Yöneticilere çok çeşitli yönetim seçenekleri sağlar.
- Kullanıcı kaydı, yöneticilere cihaz yönetimi seçeneklerinin bir alt kümesini sağlayan daha kolay bir kayıt işlemidir. Bu özellik şu anda önizleme aşamasındadır. 

Önkoşulları ve atanan kullanıcı lisanslarını tamamladıktan sonra, kullanıcılar Intune Şirket Portalı uygulamayı App Store 'dan indirebilir ve uygulamadaki kayıt talimatlarını takip edebilir. [Gizlilik bildirimi özelleştirmesi](../apps/company-portal-app.md#privacy-statement-customization)bölümünde açıklandığı gibi iOS cihazlarında Şirket portalı gizlilik bildirimini özelleştirebilirsiniz.

## <a name="company-owned-ios-devices"></a>Şirkete ait iOS cihazları

Intune, kullanıcıları için cihaz satın alan kuruluşlar için aşağıdaki iOS şirkete ait cihaz kayıt yöntemlerini destekler:

- Apple 'ın Aygıt Kayıt Programı (DEP)
- Apple Okul Yöneticisi
- Apple Configurator Kurulum Yardımcısı kaydı
- Apple Configurator doğrudan kaydı

Ayrıca, şirkete ait iOS cihazlarını bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabıyla kaydedebilirsiniz.

## <a name="device-enrollment-program"></a>Aygıt Kayıt Programı

Kuruluşlar, Apple Aygıt Kayıt Programı (DEP) aracılığıyla iOS cihazları satın alabilir. DEP, cihazları yönetime getirmek için bir kayıt profilini "hava üzerinden" dağıtmanızı sağlar. Daha fazla bilgi için bkz. [aygıt kayıt programı](device-enrollment-program-enroll-ios.md).

## <a name="user-enrollment"></a>Kullanıcı kaydı
Kullanıcı kaydı, yöneticilere diğer kayıt yöntemleriyle karşılaştırıldığında yönetim seçeneklerinin bir alt kümesini sağlar. Daha fazla bilgi için, bkz. [Kullanıcı kaydı desteklenen eylemler, parolalar ve diğer seçenekler](ios-user-enrollment-supported-actions.md) ve [IOS ve ıpados Kullanıcı kaydını ayarlama](ios-user-enrollment.md).

## <a name="apple-school-manager"></a>Apple Okul Yöneticisi

Apple Okul Yöneticisi, okullara yönelik bir cihaz satın alma ve kayıt programıdır. DEP gibi, cihazları yönetime kaydetmek için bir profil dağıtabilirsiniz. [Apple Okul Yöneticisi](apple-school-manager-set-up-ios.md)hakkında daha fazla bilgi edinin.

## <a name="apple-configurator"></a>Apple Configurator

Bir Mac bilgisayarda çalışan Apple Configurator ile iOS cihazlarını kaydedebilirsiniz. Cihazları hazırlamak için, USB ile bağlantı kurabilir ve bir kayıt profili yüklersiniz. Cihazları Apple Configurator ile iki şekilde kaydedebilirsiniz:

- Kurulum Yardımcısı kaydı-cihazı temizler, Kurulum Yardımcısı 'Nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükleyecek.
- Doğrudan kayıt-cihazı siler ve önceden tanımlanmış bir ilkeyle cihazı kaydeder. Bu yöntem, Kullanıcı benzeşimi olmayan cihazlar içindir.

[Apple Configurator kaydı](apple-configurator-enroll-ios.md)hakkında daha fazla bilgi edinin.

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>DEP ile kaydedilen veya Apple Configurator ile kaydedilen cihazlarda Şirket Portalı kullanın

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihazları yönetmek için Şirket Portalı uygulamasını yükleyip çalıştırabilir. Kullanıcılar cihazlarını aldıktan sonra, Kurulum Yardımcısını tamamlayıp Şirket Portalı uygulamasını yüklemek için bir dizi ek adımı tamamlamalıdır.

Aşağıdakileri desteklemek için Kullanıcı benzeşimi gereklidir:

- Mobil uygulama yönetimi (MAM) uygulamaları
- E-posta ve şirket verilerine koşullu erişim
- Şirket Portalı uygulaması

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Kullanıcıların, Kullanıcı benzeşimi olan şirkete ait iOS cihazlarını nasıl kaydetmeleri

1. Kullanıcılar cihazlarını açtığında Kurulum Yardımcısı 'nı tamamlamaları istenir.
2. Kurulumu tamamladıktan sonra kullanıcılardan bir Apple KIMLIĞI istenir. Cihazın Şirket Portalı yüklemesine izin vermek için bir Apple KIMLIĞI sağlamaları gerekir.
3. İOS cihazı Şirket Portalı uygulamasını App Store 'dan otomatik olarak kurar.
4. Kullanıcılar Şirket Portalı uygulamasını başlatmalı ve Intune 'daki abonelikle ilişkili kimlik bilgilerini (benzersiz kişisel ad veya UPN gibi) kullanarak oturum açabilirler.
5. Oturum açtıktan sonra kayıt tamamlanmıştır. Kullanıcılar artık bu cihazı tam yetenek kümesiyle kullanabilir.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Kullanıcı benzeşimi olmayan şirkete ait yönetilen cihazlar hakkında

Kullanıcı benzeşimi olmadan yapılandırılan cihazlar Şirket Portalı desteklemez ve uygulamanın yüklü olmaması gerekir. Şirket Portalı, kurumsal kimlik bilgileri olan ve kişiselleştirilmiş şirket kaynaklarına (e-posta gibi) erişim gerektiren kullanıcılar için tasarlanmıştır. Kullanıcı benzeşimi olmadan kaydedilen cihazların adanmış bir Kullanıcı oturum açması amaçlanmamıştır. Bilgi noktası, satış noktası (POS) veya paylaşılan yardımcı cihazlar, Kullanıcı benzeşimi olmadan kaydedilen cihazlar için tipik kullanım durumlarıdır.

Kullanıcı benzeşimi gerekiyorsa, cihaz kaydedilmeden önce cihazın kayıt profilinde **Kullanıcı benzeşimi** ' nin seçili olduğundan emin olun. Bir cihazda benzeşim durumunu değiştirmek için cihazı kullanımdan kaldırmak ve yeniden kaydetmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Intune 'de iOS cihaz kaydı sorunlarını giderme](https://support.microsoft.com/help/4039809)
