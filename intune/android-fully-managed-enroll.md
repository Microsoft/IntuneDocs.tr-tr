---
title: Android için Intune kayıt Kurulumu tam olarak yönetilen cihazlar
titlesuffix: Microsoft Intune
description: Kaydetmeyi öğrenin tam olarak yönetilen Android cihazları ıntune'a.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a730dbb702286f71534623b2c08da6b388c3e499
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835852"
---
# <a name="set-up-intune-enrollment-of-android-fully-managed-devices-preview"></a>Intune'u ayarlama Android kayıt tam (Önizleme) ile yönetilen cihazlar

Tam olarak yönetilen Android cihazları, bir tek kullanıcı ve iş için özel olarak kullanılan ve değil kişisel kullanım ile ilişkili ve şirkete ait cihazlardır. Yöneticiler, cihazın tamamını yönetmenize ve ilke denetimleri gibi iş profilleri, kullanılamayan uygulamak:
- yalnızca yönetilen Google Play mağazasından uygulama yüklemesine izin ver
- yönetilen uygulamaları kaldırmasını engelleyin
- Kullanıcıların cihazları fabrika ayarlarına engellemek ve benzeri.

Intune uygulamaları dağıtmanıza yardımcı olur ve tam olarak Android dahil olmak üzere Android kuruluş cihazlarının, ayarlar yönetilen cihazlar. Android kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Teknik gereksinimler

Bir Intune olmalıdır Android tam olarak yönetmek için tek başına Kiracı yönetilen cihazlar. Tam olarak yönetilen devcie Yönetim (SCCM bağlı) ya da karma modda ya da eski Silverlight yönetim konsolunda kullanılamaz.

Cihaz bir Android cihazı tam olarak yönetilen olarak yönetilecek şu gereksinimleri karşılamanız gerekir:

- Android işletim sistemi sürüm 5.1 ve üzeri.
- Bir derleme Google Mobile Services'ı (GMS) bağlantısı olan Android cihazları çalıştırmanız gerekir. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

Yukarıdaki gereksinimleri karşılandığında cihaz üreticisi/OEM konusunda bir kısıtlama yoktur.

## <a name="set-up-android-fully-managed-device-management"></a>Ayarlanan Android cihaz Yönetimi tam olarak yönetilen

Ayarlamak için Android tam cihaz Yönetimi yönetilen, aşağıdaki adımları izleyin:

1. Mobil cihazları yönetmek hazırlamak için şunları yapmanız gerekir [mobil cihaz Yönetimi (MDM) yetkilisini ayarlamak **Intune**](mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune kiracı hesabınızı Android kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
3. [Kullanıcı şirkete ait cihazları etkinleştirme](#enable-corporate-owned-user-devices)
4. [Tam olarak yönetilen cihazları kaydetme](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Şirket ait kullanıcı cihazları etkinleştirme

1. Git [Intune portalı](https://portal.azure.com) ve **cihaz kaydı** > **Android kaydını** > **şirkete, tam olarak yönetilen kullanıcı cihazları (Önizleme)**.
2. Altında **kullanıcı şirkete ait cihazları kaydetmesine izin vermek**, seçin **Evet**.

Bu ayar ayarlandığında **Evet**, size bir kayıt belirteci (rastgele bir dize) ve bir QR kodu ile Intune kiracınız için sağlar. Bu tek kayıt belirtecini tüm kullanıcılar için geçerlidir ve süresi olmaz. Android işletim sistemi ve sürümü cihazın bağlı olarak, bilgi noktası cihazı kaydetmek için belirteç veya QR kodunu kullanabilirsiniz.

## <a name="enroll-the-fully-managed-devices"></a>Tam olarak yönetilen cihazları kaydetme
Artık [tam olarak yönetilen cihazları kaydetme](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Bu önizleme özelliği için Değerlendirmeler
Android çözüm kümesi tam olarak yönetilen için bu genel Önizleme özellikleri çekirdek kümesini içerir. Geçerli iletişim kanallarınızın ekibine birini kullanarak önizleme özelliklerini kullanma deneyiminizle ilgili görüşlerinizi almak istiyoruz (gibi [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Bu önizleme, tam olarak yönetilen Android cihazlar için aşağıdaki özellikleri destekler:
- NFC, belirteç girişi, QR kodunu ve sıfır dokunma kullanarak cihaz kaydetme
- Kullanıcı grupları için cihaz yapılandırması
- Uygulama dağıtımı ve kullanıcı grupları için yapılandırma


Bu önizleme özelliklerini kullanırken aşağıdakileri göz önünde bulundurun:
- Önizlemedeki özellikler için önerilen olmayan görev açısından kritik veya üretim dağıtımları. 
- Önizleme özellikleri Intune üretim standartlarına uygulanır. Ancak, Intune özelliklerinin tamamı Android kullanılabilir tam olarak yönetilen kullanıcı cihazları. Önizleme özellikleri, Intune konsolunda "(Önizleme)" net bir şekilde etiketlenir. 
- Önizleme özellikleri, tam olarak normal bir Intune destek kanalları desteklenir.
- Android tam olarak kaydedilmesi yönetilen cihazlar kullanarak Samsung Knox mobil kayıt önizlemede desteklenmiyor. 
- Yönetilen cihazlara Intune Şirket portalı uygulaması Android üzerinde tam olarak desteklenmez kullanın. 
- Koşullu erişim, uygulama koruma ilkeleri ve dağıtım önizlemede desteklenmeyen sertifika gibi Intune özellikleri. 
- Herhangi bir profili veya uygulama cihaz grubu hedefleme önizlemede desteklenmiyor. Yalnızca kullanıcı grubu hedefleme desteklenir. 
- E-posta, WiFi veya VPN yapılandırmak için birinci sınıf kullanıcı Arabirimi yoktur. Desteklenen uygulama yapılandırma ayarlarını yapılandırmak için uygulama yapılandırma ilkelerini kullanın.

## <a name="next-steps"></a>Sonraki adımlar
- [Android cihaz yapılandırma ilkelerinin tam olarak yönetilen Ekle](device-restrictions-android-for-work.md#device-owner-only)
- [Tam olarak yönetilen Android cihazlar için uygulama yapılandırma ilkelerini yapılandırma](app-configuration-policies-use-android.md)

