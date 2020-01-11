---
title: Android kurumsal tam olarak yönetilen cihazlar için Intune kaydını kurma
titleSuffix: Microsoft Intune
description: Android kurumsal tam yönetilen cihazları Intune 'a kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d8397dea1dca97122aac6716ee3d51295b913538
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885933"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices"></a>Android kurumsal tam olarak yönetilen cihazların Intune kaydını ayarlama 

Android kurumsal tam olarak yönetilen cihazlar, tek bir kullanıcıyla ilişkili ve özel olarak çalışan ve kişisel kullanım için kullanılan, şirkete ait cihazlardır. Yöneticiler cihazı tümüyle yönetebilir ve ilke denetimlerini iş profilleri için kullanılamaz hale uygulayabilir, örneğin:
- Yalnızca yönetilen Google Play uygulama yüklemeye izin verin.
- Yönetilen uygulamaların kaldırılmasını engelleyin.
- Kullanıcıların cihazların fabrika ayarlarına sıfırlamasını ve bu şekilde devam etmelerini önleyin.

Intune, Android kurumsal tam olarak yönetilen cihazlar dahil olmak üzere Android kurumsal cihazlara uygulama ve ayarlar dağıtmanıza yardımcı olur. Android Kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Teknik gereksinimler

Android kurumsal tam olarak yönetilen cihazları yönetmek için tek başına Intune kiracısına sahip olmanız gerekir. Tam olarak yönetilen cihaz yönetimi eski Silverlight Yönetim konsolunda kullanılamıyor.

Cihazların, Android kurumsal tam olarak yönetilen bir cihaz olarak yönetilmesi için bu gereksinimleri karşılaması gerekir:

- Android OS sürüm 6,0 ve üzeri.
- Cihazların Google Mobile Services (GMS) bağlantısı olan bir Android derlemesi çalıştırması gerekir. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

Yukarıdaki gereksinimler karşılanıyorsa cihaz üreticisi/OEM üzerinde bir kısıtlama yoktur.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Android kurumsal tam yönetilen cihaz yönetimini ayarlama

Android kurumsal tam olarak yönetilen cihaz yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. Mobil cihazları yönetmeye hazırlanmak için [mobil cihaz yönetimi (MDM) yetkilisini **Microsoft Intune**olarak ayarlamanız](../fundamentals/mdm-authority-set.md)gerekir. Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune kiracı hesabınızı Android Kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
3. [Şirkete ait Kullanıcı cihazlarını etkinleştir](#enable-corporate-owned-user-devices)
4. [Tam olarak yönetilen cihazları kaydedin](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Şirkete ait Kullanıcı cihazlarını etkinleştir

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) ' nde oturum açın ve **cihazlar** > **Android** > Android **kaydı**  > **şirkete ait, tam olarak yönetilen Kullanıcı cihazları**' nı seçin.
2. **Kullanıcıların şirkete ait Kullanıcı cihazlarını kaydetmesine Izin ver**altında **Evet**' i seçin.

> [!NOTE]
> *Bir cihazın uyumlu denetim olarak işaretlenmesini gerektir* ve **tüm bulut uygulamaları**, **Android** ve **TARAYıCıLAR** Için geçerli olmasını gerektiren bir Azure AD koşullu erişim ilkeniz varsa, bu ilkeden **Microsoft Intune** bulut uygulamasını dışmalısınız. Bunun nedeni, Android Kurulum işlemlerinin kaydolma sırasında kullanıcılarınızın kimliğini doğrulamak için bir Chrome sekmesi kullanmamasıdır. Daha fazla bilgi için bkz. [Azure AD koşullu erişim belgeleri](https://docs.microsoft.com/azure/active-directory/conditional-access/).

Bu ayar **Evet**olarak ayarlandığında, Intune kiracınız için bir kayıt belirteci (rastgele bir dize) ve QR kodu sağlar. Bu tek kayıt belirteci tüm kullanıcılarınız için geçerlidir ve sona ermez. Cihazın Android işletim sistemine ve sürümüne bağlı olarak, cihazı kaydetmek için belirteci veya QR kodunu kullanabilirsiniz.

## <a name="enroll-the-fully-managed-devices"></a>Tam olarak yönetilen cihazları kaydetme
Artık [tam olarak yönetilen cihazlarınızı](android-dedicated-devices-fully-managed-enroll.md)kaydedebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
- [Android kurumsal tam yönetilen cihaz yapılandırma ilkeleri ekleme](../configuration/device-restrictions-android-for-work.md#device-owner-only)
- [Android kurumsal tam olarak yönetilen cihazlar için uygulama yapılandırma ilkelerini yapılandırma](../apps/app-configuration-policies-use-android.md)

