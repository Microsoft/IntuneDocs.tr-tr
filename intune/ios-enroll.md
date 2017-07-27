---
title: "Intune’da Windows cihazları nasıl yükleyeceğinizi seçme"
titleSuffix: Intune on Azure
description: "Microsoft Intune’da Windows cihazların kaydını nasıl ayarlayacağınızı öğrenin.”"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bdbc7ca68995e23295cf099ce73dfdcaeba37c
ms.sourcegitcommit: 5eb209ae48173ddfdbbab131f12f3ac3498dcd87
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Intune’da iOS cihazları kaydetme

Intune, kullanıcılara şirket e-postası ve uygulamalarına erişim vermek amacıyla iPad ve iPhone’lar için mobil cihaz yönetimi (MDM) sağlar.

Bir Intune yöneticisi olarak, iOS cihazları için kaydı etkinleştirebilirsiniz. Kullanıcıların kişisel cihazlarını kaydetmelerine izin verebilirsiniz, bu işlem “kendi cihazını getir” (KCG) kaydı olarak bilinir. Şirkete ait cihazların kaydını da etkinleştirebilirsiniz.

## <a name="prerequisites-for-ios-enrollment"></a>iOS kaydı için önkoşullar
iOS cihazları etkinleştirmeden önce aşağıdaki adımları tamamlayın:
- [Intune’u ayarlama](setup-steps.md) - Bu adımlar, Intune altyapınızı ayarlar. Cihaz kaydı özellikle [MDM yetkilinizi ayarlamanızı](mdm-authority-set.md) gerektirir.
- [Bir Apple MDM Anında İletme sertifikası alma](apple-mdm-push-certificate-get.md) - Apple, iOS ve macOS cihazların yönetimini etkinleştirmek için bir sertifika gerektirir.

Bu önkoşullar tamamlandıktan sonra kullanıcılar, kişisel iOS cihazlarını kaydetmek için Şirket Portalı uygulamasını yükleyebilir veya yönetici, şirkete ait iOS cihazı yönetimini ayarlayabilir. Yöneticiler ayrıca, tek bir yönetim hesabından pek çok cihaz kaydedebilen [cihaz kayıt yöneticileri](device-enrollment-manager-enroll.md) de atayabilir. Intune, şirkete ait iOS cihazların kaydında aşağıdaki yöntemleri destekler:

## <a name="device-enrollment-program"></a>Cihaz Kaydı Programı
Kuruluşlar, Apple’ın Aygıt Kayıt Programı (DEP) aracılığıyla iOS cihazlar satın alabilir. DEP, cihazları yönetime kaydetmek için bir kayıt profilini “uzaktan” dağıtmanıza imkan tanır. [Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager, okullar için oluşturulmuş bir cihaz satın alma ve kayıt programıdır. DEP’te olduğu gibi cihazları yönetime kaydetmek için bir profil dağıtabilirsiniz. [Apple School Manager](apple-school-manager-set-up-ios.md) hakkında daha fazla bilgi edinin.

## <a name="apple-configurator"></a>Apple Configurator
Bir Mac bilgisayarda çalışan Apple Configurator ile iOS cihazları kaydedebilirsiniz. Cihazları hazırlamak için USB ile bağlayıp onlara bir kayıt profili yüklersiniz. Cihazları Apple Configurator ile iki şekilde kaydedebilirsiniz:
- Kurulum Yardımcısı kaydı - Cihazı fabrika ayarlarına sıfırlar, Kurulum Yardımcısı’nı çalıştırmaya hazırlar ve cihazın yeni kullanıcısı için şirketin ilkelerini yükler.
- Doğrudan kayıt - Cihazı fabrika ayarlarına sıfırlamaz ve önceden tanımlanmış bir ilkeyle kaydeder. Bu yöntem, kullanıcı benzeşimi olmayan cihazlar içindir.

[Apple Configurator kaydı](apple-configurator-setup-assistant-enroll-ios.md) hakkında daha fazla bilgi edinin.
