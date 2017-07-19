---
title: "Intune’da iOS cihazlarının nasıl kaydedileceğini belirleme"
titleSuffix: Intune on Azure
description: "Microsoft Intune’da iOS cihazlarının kaydının nasıl ayarlandığını öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>iOS ve macOS cihazlarının nasıl kaydedileceğini belirleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, bir BT yöneticisinin Intune'da iOS cihaz kaydını etkinleştirmek için kullanabileceği yöntemleri açıklar.

iOS cihazlarını hangi yöntemle kaydedeceğinize karar verirken aşağıdaki bilgilerden yararlanın. KCG dışında aşağıdaki yöntemlerin tümü, şirkete ait cihazların kaydına yöneliktir.

**Ön koşul:** [Apple Anında İletilen Bildirim hizmeti sertifikası](apple-mdm-push-certificate-get.md) gerekir.

## <a name="user-owned-ios-devices-byod"></a>Kullanıcıya ait iOS cihazları (KCG)

Kullanıcılar kendi kişisel, KCG (kendi cihazını getir) cihazlarını kaydetmek istediklerinde, App Store’dan iOS için Şirket Portalı uygulamasını indirip uygulamadaki kayıt yönergelerini izleyebilirler. Kaydedildikten sonra, kullanıcılar şirket ağına bağlanabilir, etki alanına veya Azure Active Directory’ye katılabilir ve şirket kaynaklarına erişim sağlayabilir. KCG'yi etkinleştirmek için tek gereksinim bir [Apple Anında İletilen Bildirim hizmeti sertifikasıdır](apple-mdm-push-certificate-get.md). Kişisel iOS cihazlarının kaydedilmesini de engelleyebilirsiniz. Yönergeler için bkz. [Cihaz türü kısıtlamaları ayarlama](enrollment-restrictions-set.md).

## <a name="user-owned-macos-devices-byod"></a>Kullanıcıya ait macOS cihazları (KCG)

macOS cihaz kaydını etkinleştirebilirsiniz. macOS kaydını etkinleştirmek için tek gereksinim bir [Apple Anında İletilen Bildirim hizmeti sertifikasıdır](apple-mdm-push-certificate-get.md). Daha fazla bilgi için bkz. [macOS cihazları kaydetme](./macos-enroll.md)

## <a name="enrollment-program-with-apple"></a>Apple ile kayıt programı
Apple, cihaz kaydı ve yönetim altyapısı içeren cihaz satın alma programları sunar. Bu programlardan biri aracılığıyla satın alınan cihazlar, Intune yönetimi için cihaz seri numaraları atanarak toplu olarak "kablosuz" şekilde kaydedilebilir.

- **Cihaz Kayıt Programı (DEM)** - Apple’ın kuruluşlar ve işletmeler için cihaz kayıt programı. Daha fazla bilgi için, bkz. [Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme](device-enrollment-program-enroll-ios.md).
- **Apple School Manager** - Apple’ın okullar için cihaz kayıt programı. Daha fazla bilgi için bkz. [Apple School Manager ile iOS cihaz kaydını etkinleştirme](apple-school-manager-set-up-ios.md)

## <a name="apple-configurator"></a>Apple Configurator

iOS cihazlarını bir Kurumsal Kayıt profilini dışarı aktarıp ardından söz konusu mobil cihazları Apple Configurator çalıştıran bir Mac bilgisayara bağlayarak kaydedebilirsiniz. Apple Configurator iki kayıt biçimini destekler:

- **Kurulum Yardımcısı kaydı**: Cihazı fabrika ayarlarına sıfırlar ve yeni kullanıcı tarafından kurulum yapılmaya hazırlar. Bu yöntem yöneticinin, kaydı önceden yapılandırmak için iOS cihazını USB üzerinden Apple Configurator çalıştıran bir Mac bilgisayara bağlamasını gerektirir. Cihazlar daha sonra kullanıcılara dağıtılır, kullanıcılar da cihaz ilk açıldığında Kurulum Yardımcısı’nı çalıştırır. Bu işlem cihazı kullanıcıların iş veya okul kimlik bilgileriyle yapılandırır ve kayıt işlemini tamamlar. Daha fazla bilgi için bkz. [Apple Configurator ve Kurulum Yardımcısı ile iOS cihazları kaydetme](apple-configurator-setup-assistant-enroll-ios.md).

- **Doğrudan kayıt**: Cihaz hazırlama sırasında kullanılmak üzere Apple Configurator ile uyumlu bir dosya oluşturur. Kaydedilen cihaz fabrika ayarlarına sıfırlanmaz ve hiçbir kullanıcıyla ilişkili değildir. Cihazları kaydetmek için, yöneticinin iOS cihazını USB üzerinden Apple Configurator çalıştıran Mac bilgisayarına bağlaması gerekir. Daha fazla bilgi için bkz. [Apple Configurator Doğrudan Kurulum kullanarak iOS cihazlarını kaydetme](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Aygıt Kayıt Programı’nı (DEP) kullanma

Bu seçenek, DEP aracılığıyla satın alınan cihazlara bir “havadan” kaydolma profili dağıtır. Kullanıcı, cihaz ilk çalıştığında Kurulum Yardımcısı’nı çalıştırdığında, cihaz Intune'a kaydedilir. Daha fazla bilgi için, bkz. [Cihaz Kayıt Programı’nı kullanarak iOS cihazlarını kaydetme](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Cihaz kayıt yöneticisini (DEM) kullanma
Cihaz kayıt yöneticisi, en çok 1.000 cihazı kaydedebilen ve yönetebilen genel bir kullanıcı hesabıdır. DEM ile yönetilen cihazlarda kullanıcı benzeşimi olmaz, bu nedenle cihazın asla bir sahibi yoktur. Bir Intune kullanıcısına bu yetenekleri kazandırmak için ona DEM izinleri verirsiniz. DEM kullanıcısının kaydettiği her cihaz bir Intune lisansı kullanır. Daha fazla bilgi için bkz. [Cihaz kayıt yöneticisini kullanarak cihazları kaydetme](device-enrollment-manager-enroll.md).
