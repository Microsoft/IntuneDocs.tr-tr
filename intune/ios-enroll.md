---
title: Intune’da iOS cihazları kaydetme
titleSuffix: Microsoft Intune
description: Microsoft Intune’da iOS cihazlarının kaydını ayarlayın.
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
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bc14561aa2932327d69f920885fa17538bdf245c
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045552"
---
# <a name="enroll-ios-devices-in-intune"></a>Intune’da iOS cihazları kaydetme

Intune, kullanıcılara şirket e-postası ve uygulamalarına erişim vermek amacıyla iPad ve iPhone’lar için mobil cihaz yönetimi (MDM) sağlar.

Bir Intune yöneticisi olarak, iOS cihazları için kaydı etkinleştirebilirsiniz. Kullanıcıların kişisel cihazlarını kaydetmelerine izin verebilirsiniz, bu işlem “kendi cihazını getir” (KCG) kaydı olarak bilinir. Şirkete ait cihazların kaydını da etkinleştirebilirsiniz.

## <a name="prerequisites-for-ios-enrollment"></a>iOS kaydı için önkoşullar
iOS cihazları etkinleştirmeden önce aşağıdaki adımları tamamlayın:
- [Intune’u ayarlama](setup-steps.md) - Bu adımlar, Intune altyapınızı ayarlar. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](mdm-authority-set.md) gerektirir.
- [Bir Apple MDM Anında İletme sertifikası alma](apple-mdm-push-certificate-get.md) - Apple, iOS ve macOS cihazların yönetimini etkinleştirmek için bir sertifika gerektirir.

## <a name="user-owned-ios-devices-byod"></a>Kullanıcıya ait iOS cihazları (KCG)

Kullanıcıların kendi cihazlarını Intune yönetimine kaydetmesine izin verebilirsiniz. Bu, “kendi cihazını getir” veya KCG olarak bilinir. Siz önkoşulları tamamlayıp kullanıcılara lisans atadıktan sonra kullanıcılar, App Store’dan Intune Şirket Portalı’nı indirip uygulamadaki kayıt yönergelerini izleyebilir.

## <a name="company-owned-ios-devices"></a>Şirkete ait iOS cihazlar
Kullanıcılarına cihaz sağlayan kuruluşlar için Intune, aşağıdaki iOS şirkete ait cihaz kayıt yöntemlerini destekler:

- Apple’ın Aygıt Kayıt Programı (DEP)
- Apple School Manager
- Apple Configurator Kurulum Yardımcısı kaydı
- Apple Configurator ile doğrudan kayıt

Şirkete ait iOS cihazları bir [cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) hesabıyla da kaydedebilirsiniz.

## <a name="device-enrollment-program"></a>Cihaz Kaydı Programı
Kuruluşlar, Apple’ın Aygıt Kayıt Programı (DEP) aracılığıyla iOS cihazlar satın alabilir. DEP, cihazları yönetime kaydetmek için bir kayıt profilini “uzaktan” dağıtmanıza imkan tanır. [Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager, okullar için oluşturulmuş bir cihaz satın alma ve kayıt programıdır. DEP’te olduğu gibi cihazları yönetime kaydetmek için bir profil dağıtabilirsiniz. [Apple School Manager](apple-school-manager-set-up-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-configurator"></a>Apple Configurator
Bir Mac bilgisayarda çalışan Apple Configurator ile iOS cihazları kaydedebilirsiniz. Cihazları hazırlamak için USB ile bağlayıp onlara bir kayıt profili yüklersiniz. Cihazları Apple Configurator ile iki şekilde kaydedebilirsiniz:
- Kurulum Yardımcısı kaydı - Cihazı siler, Kurulum Yardımcısı’nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükler.
- Doğrudan kayıt - Cihazı silmez ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, kullanıcı benzeşimi olmayan cihazlar içindir.

[Apple Configurator kaydı](apple-configurator-setup-assistant-enroll-ios.md) hakkında daha fazla bilgi edinin.

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>DEP veya Apple Configurator ile kaydedilmiş cihazlarda Şirket Portalı’nı kullanma

Kullanıcı benzeşimi ile yapılandırılmış cihazlar, uygulama indirmek ve cihaz yönetmek için Şirket Portalı’nı yükleyip çalıştırabilir. Kullanıcılar, cihazlarını aldıktan sonra Kurulum Yardımcısı’nı tamamlamak ve Şirket Portalı uygulamasını yüklemek için bir dizi ek adımı tamamlamalıdır.

Aşağıdakileri desteklemek için kullanıcı benzeşimi gereklidir:
  - Mobil uygulama yönetimi (MAM) uygulamaları
  - E-postasına ve şirket verilerine koşullu erişim
  - Şirket Portalı uygulaması

**Kullanıcıların kullanıcı benzeşimi olan şirkete ait iOS cihazları kaydetmesi**
1. Kullanıcılar cihazlarını açtığında, kendilerinden Kurulum Yardımcısı’nı tamamlamaları istenir. 
2. Kurulum tamamlandıktan sonra kullanıcılardan bir Apple kimliği istenir. Cihazın Şirket Portalı’nı yüklemesine izin vermek için bir Apple kimliği sağlanmalıdır. 
3. iOS cihazı, Şirket Portalı’nı App Store’dan otomatik olarak yükler.
4. Kullanıcılar, Şirket Portalı uygulamasını başlatıp Intune abonelikleriyle ilişkili kimlik bilgilerini (benzersiz kişisel ad veya UPN gibi) kullanarak oturum açmalıdır. 
5. Oturum açtıktan sonra kayıt tamamlanır. Kullanıcılar artık bu cihazı tüm özellikleriyle kullanabilir.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Kullanıcı benzeşimi olmayan şirkete ait yönetilen cihazlar hakkında

Hiçbir kullanıcı benzeşimi olmadan yapılandırılmış cihazlar, Şirket Portalı’nı desteklemez ve uygulamayı yüklememelidir. Şirket Portalı, kurumsal kimlik bilgileri olan ve kişiselleştirilmiş şirket kaynaklarına (e-posta gibi) erişmesi gereken kullanıcılar için tasarlanmıştır. Kullanıcı benzeşimi olmadan kaydedilmiş cihazlarda adanmış kullanıcı oturumu kullanılmamalıdır. Bilgi noktası, satış noktası (POS) veya paylaşılan yardımcı cihazlar, kullanıcı benzeşimi olmadan kaydedilen cihazların tipik kullanım örnekleridir.

Kullanıcı benzeşimi gerekiyorsa, cihazın kaydolma profilinde cihaz kaydedilmeden önce **Kullanıcı Benzeşimi**’nin seçildiğinden emin olun. Bir cihazdaki benzeşim durumunu değiştirmek için cihazı kullanımdan kaldırıp tekrar kaydetmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Intune iOS cihaz kaydı sorunlarını giderme](https://support.microsoft.com/help/4039809)
