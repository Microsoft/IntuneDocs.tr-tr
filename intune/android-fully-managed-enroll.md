---
title: Kurulum Intune kaydı Android Enterprise için tam olarak yönetilen cihazlar
titleSuffix: Microsoft Intune
description: Intune'da Android kuruluş tarafından tam olarak yönetilen cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f1b1197671b54cb5374bd79b6acbeb8137c0135c
ms.sourcegitcommit: cc5d757018d05fc03ac9ea3d30f563df9bfd61ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66819881"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices-preview"></a>Intune'u ayarlama Android Kurumsal kaydını tam (Önizleme) ile yönetilen cihazlar

Kuruluş tarafından tam olarak yönetilen Android cihazları, bir tek kullanıcı ve iş için özel olarak kullanılan ve değil kişisel kullanım ile ilişkili ve şirkete ait cihazlardır. Yöneticiler, cihazın tamamını yönetmenize ve ilke denetimleri gibi iş profilleri, kullanılamayan uygulamak:
- yalnızca yönetilen Google Play uygulama yüklemesine izin ver
- yönetilen uygulamaları kaldırmasını engelleyin
- Kullanıcıların cihazları fabrika ayarlarına engellemek ve benzeri.

Intune uygulamaları dağıtmanıza yardımcı olur ve tam olarak Android Enterprise dahil olmak üzere Android kuruluş cihazlarının, ayarlar yönetilen cihazlar. Android Kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Teknik gereksinimler

Tam olarak yönetilen Android kuruluş cihazlarını yönetmek için bir Intune tek başına Kiracı olması gerekir. Karma (Configuration Manager bağlı) her iki modda veya eski Silverlight yönetim konsolunda tam olarak yönetilen bir cihaz Yönetimi kullanılamıyor.

Cihaz bir Android Kurumsal cihaz tam olarak yönetilen olarak yönetilecek şu gereksinimleri karşılamanız gerekir:

- Android işletim sistemi sürüm 5.1 ve üzeri.
- Bir derleme Google Mobile Services'ı (GMS) bağlantısı olan Android cihazları çalıştırmanız gerekir. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

Yukarıdaki gereksinimleri karşılandığında cihaz üreticisi/OEM konusunda bir kısıtlama yoktur.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Tam olarak yönetilen Android Kurumsal cihaz yönetimini ayarlama

Ayarlamak için Android Kurumsal cihaz Yönetimi yapılandırılan, aşağıdaki adımları izleyin:

1. Mobil cihazları yönetmek hazırlamak için şunları yapmanız gerekir [mobil cihaz Yönetimi (MDM) yetkilisini ayarlamak **Intune**](mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune kiracı hesabınızı Android Kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
3. [Kullanıcı şirkete ait cihazları etkinleştirme](#enable-corporate-owned-user-devices)
4. [Tam olarak yönetilen cihazları kaydetme](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Şirket ait kullanıcı cihazları etkinleştirme

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) ve **cihaz kaydı** > **Android kaydını** > **şirkete, tam olarak yönetilen Kullanıcı cihazları (Önizleme)** .
2. Altında **kullanıcı şirkete ait cihazları kaydetmesine izin vermek**, seçin **Evet**.

[!NOTE]
Kullanan tanımlı bir Azure AD koşullu erişim ilkesi varsa *bir cihazın uyumlu olarak işaretlenmesini gerektir* denetlemek ve uygulandığı **tüm bulut uygulamaları**, **Android** ve **Tarayıcılar** -hariç tutmanız gerekir **Intune** bu ilkeden bulut uygulaması. Android kurulum işlemlerini kullanan bir Chrome sekme kaydolma sırasında kullanıcıların kimliklerini doğrulamak için olmasıdır. Daha fazla bilgi için [Azure AD koşullu erişim belgelerine](https://docs.microsoft.com/azure/active-directory/conditional-access/).

Bu ayar ayarlandığında **Evet**, size bir kayıt belirteci (rastgele bir dize) ve bir QR kodu ile Intune kiracınız için sağlar. Bu tek kayıt belirtecini tüm kullanıcılar için geçerlidir ve süresi olmaz. Android işletim sistemi ve sürümü cihazın bağlı olarak, bilgi noktası cihazı kaydetmek için belirteç veya QR kodunu kullanabilirsiniz.

## <a name="enroll-the-fully-managed-devices"></a>Tam olarak yönetilen cihazları kaydetme
Artık [tam olarak yönetilen cihazları kaydetme](android-dedicated-devices-fully-managed-enroll.md).

## <a name="considerations-for-this-preview-feature"></a>Bu önizleme özelliği için Değerlendirmeler
Android Kurumsal çözüm kümesi tam olarak yönetilen için bu genel Önizleme özellikleri çekirdek kümesini içerir. Geçerli iletişim kanallarınızın ekibine birini kullanarak önizleme özelliklerini kullanma deneyiminizle ilgili görüşlerinizi almak istiyoruz (gibi [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)).

Android Kurumsal tam olarak yönetilen cihazlar için bu önizlemede aşağıdaki özellikleri destekler:
- NFC, belirteç girişi, QR kodunu ve sıfır dokunma kullanarak cihaz kaydetme
- Kullanıcı grupları için cihaz yapılandırması
- Uygulama dağıtımı ve kullanıcı grupları için yapılandırma


Bu önizleme özelliklerini kullanırken aşağıdakileri göz önünde bulundurun:
- Önizlemedeki özellikler için önerilen olmayan görev açısından kritik veya üretim dağıtımları. 
- Önizleme özellikleri Intune üretim standartlarına uygulanır. Ancak, tüm Intune özellikleri tam olarak yönetilen Android Enterprise kullanıcı cihazları ile kullanılabilir. Önizleme özellikleri, Intune konsolunda "(Önizleme)" net bir şekilde etiketlenir. 
- Önizleme özellikleri, tam olarak normal bir Intune destek kanalları desteklenir.
- Samsung Knox mobil kaydı kullanarak tam olarak yönetilen Android Enterprise cihazlarını kaydetme, Önizleme'de desteklenmez. 
- Yönetilen cihazlara Intune Şirket portalı uygulaması Android kuruluş tam olarak desteklenmez kullanın. 
- Koşullu erişim, uygulama koruma ilkeleri ve dağıtım önizlemede desteklenmeyen sertifika gibi Intune özellikleri. 
- Herhangi bir profili veya uygulama cihaz grubu hedefleme önizlemede desteklenmiyor. Yalnızca kullanıcı grubu hedefleme desteklenir. 
- E-posta, WiFi veya VPN yapılandırmak için birinci sınıf kullanıcı Arabirimi yoktur. Desteklenen uygulama yapılandırma ayarlarını yapılandırmak için uygulama yapılandırma ilkelerini kullanın.

## <a name="next-steps"></a>Sonraki adımlar
- [Android Kurumsal cihaz yapılandırma ilkelerinin tam olarak yönetilen Ekle](device-restrictions-android-for-work.md#device-owner-only)
- [Android Kurumsal tam olarak yönetilen cihazlar için uygulama yapılandırma ilkelerini yapılandırma](app-configuration-policies-use-android.md)

