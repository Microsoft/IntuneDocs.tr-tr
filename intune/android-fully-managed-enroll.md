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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32a8fb7345a955629c3aa3073f02602fb057c99a
ms.sourcegitcommit: 2614d1b08b8a78cd792aebd2ca9848f391df8550
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67794262"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices-preview"></a>Android kurumsal tam olarak yönetilen cihazların Intune kaydını ayarlama (Önizleme)

Android kurumsal tam olarak yönetilen cihazlar, tek bir kullanıcıyla ilişkili ve özel olarak çalışan ve kişisel kullanım için kullanılan, şirkete ait cihazlardır. Yöneticiler cihazı tümüyle yönetebilir ve ilke denetimlerini iş profilleri için kullanılamaz hale uygulayabilir, örneğin:
- yalnızca yönetilen Google Play uygulama yüklemeye izin ver
- yönetilen uygulamaların kaldırılmasını engelleyin
- Kullanıcıların cihazların fabrika ayarlarına sıfırlamasını ve bu şekilde devam etmelerini önleyin.

Intune, Android kurumsal tam olarak yönetilen cihazlar dahil olmak üzere Android kurumsal cihazlara uygulama ve ayarlar dağıtmanıza yardımcı olur. Android Kurumsal hakkında belirli ayrıntıları öğrenmek için bkz. [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Teknik gereksinimler

Android kurumsal tam olarak yönetilen cihazları yönetmek için tek başına Intune kiracısına sahip olmanız gerekir. Tam olarak yönetilen cihaz yönetimi, karma (Configuration Manager bağlı) modunda veya eski Silverlight Yönetim konsolunda kullanılamaz.

Cihazların, Android kurumsal tam olarak yönetilen bir cihaz olarak yönetilmesi için bu gereksinimleri karşılaması gerekir:

- Android işletim sistemi sürüm 5.1 ve üzeri.
- Cihazların Google Mobile Services (GMS) bağlantısı olan bir Android derlemesi çalıştırması gerekir. Cihazlarda GMS kullanılabilir olmalı ve cihazlar GMS’ye bağlanabilmelidir.

Yukarıdaki gereksinimler karşılanıyorsa cihaz üreticisi/OEM üzerinde bir kısıtlama yoktur.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Android kurumsal tam yönetilen cihaz yönetimini ayarlama

Android kurumsal tam olarak yönetilen cihaz yönetimini ayarlamak için aşağıdaki adımları izleyin:

1. Mobil cihazları yönetmeye hazırlanmak için [mobil cihaz yönetimi (MDM) yetkilisini **Microsoft Intune**olarak ayarlamanız](mdm-authority-set.md)gerekir. Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlarsınız.
2. [Intune kiracı hesabınızı Android Kurumsal hesabınıza bağlayın](connect-intune-android-enterprise.md).
3. [Şirkete ait Kullanıcı cihazlarını etkinleştir](#enable-corporate-owned-user-devices)
4. [Tam olarak yönetilen cihazları kaydedin](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Şirkete ait Kullanıcı cihazlarını etkinleştir

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihaz kaydı** > **Android kaydı** > **şirkete ait, tam olarak yönetilen Kullanıcı cihazları (Önizleme)** seçeneğini belirleyin.
2. **Kullanıcıların şirkete ait Kullanıcı cihazlarını kaydetmesine Izin ver**altında **Evet**' i seçin.

> [!NOTE]
> *Bir cihazın uyumlu denetim olarak işaretlenmesini gerektir* ve **tüm bulut uygulamaları**, **Android** ve **TARAYıCıLAR** Için geçerli olmasını gerektiren bir Azure AD koşullu erişim ilkeniz varsa, **Microsoft Intune** hariç bırakmanız gerekir Bu ilkeden bulut uygulaması. Bunun nedeni, Android Kurulum işlemlerinin kaydolma sırasında kullanıcılarınızın kimliğini doğrulamak için bir Chrome sekmesi kullanmamasıdır. Daha fazla bilgi için bkz. [Azure AD koşullu erişim belgeleri](https://docs.microsoft.com/azure/active-directory/conditional-access/).

Bu ayar **Evet**olarak ayarlandığında, Intune kiracınız için bir kayıt belirteci (rastgele bir dize) ve QR kodu sağlar. Bu tek kayıt belirteci tüm kullanıcılarınız için geçerlidir ve sona ermez. Aygıtın Android işletim sistemi ve sürümüne bağlı olarak, bilgi noktası cihazını kaydetmek için belirteci veya QR kodunu kullanabilirsiniz.

## <a name="enroll-the-fully-managed-devices"></a>Tam olarak yönetilen cihazları kaydetme
Artık [tam olarak yönetilen cihazlarınızı](android-dedicated-devices-fully-managed-enroll.md)kaydedebilirsiniz.

## <a name="considerations-for-this-preview-feature"></a>Bu önizleme özelliğiyle ilgili konular
Bu genel önizleme, Android kurumsal tam olarak yönetilen çözüm kümesi için temel bir özellikler kümesi içerir. Geçerli iletişim kanallarınızı takıma ( [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas?category_id=210853)gibi) kullanarak Önizleme özelliklerini kullanarak deneyiminizden haberdar olmak istiyoruz.

Bu önizleme, Android kurumsal tam olarak yönetilen cihazlar için aşağıdaki özellikleri destekler:
- NFC, Token entry, QR Code ve Zero Touch kullanan cihaz kaydı
- Kullanıcı grupları için cihaz yapılandırması
- Kullanıcı grupları için uygulama dağıtımı ve yapılandırması


Bu önizleme özelliklerini kullanırken şunları göz önünde bulundurun:
- Görev açısından kritik veya üretim dağıtımları için Önizlemedeki Özellikler önerilmez. 
- Önizleme özellikleri Microsoft Intune üretim standartlarına uygulanır. Ancak, Android kurumsal tam olarak yönetilen Kullanıcı cihazlarıyla tüm Intune özellikleri kullanılamaz. Önizleme özellikleri, Intune konsolundaki "(Önizleme)" ile açıkça etiketlenir. 
- Önizleme özellikleri, normal Intune destek kanalları aracılığıyla tam olarak desteklenir.
- Samsung KNOX mobil kaydı kullanılarak Android kurumsal tam yönetilen cihazların kaydedilmesi önizlemede desteklenmez. 
- Intune Şirket Portalı uygulamasının kullanımı, Android kurumsal tam yönetilen cihazlarda desteklenmez. 
- Koşullu erişim, uygulama koruma ilkeleri ve sertifika dağıtımı gibi Intune özellikleri önizlemede desteklenmez. 
- Herhangi bir profil veya uygulamayı hedefleyen cihaz grubu, önizlemede desteklenmez. Yalnızca Kullanıcı grubu hedefleme desteklenir. 
- E-posta, WiFi veya VPN yapılandırmak için birinci sınıf Kullanıcı arabirimi yoktur. Desteklenen uygulama yapılandırma ayarlarını yapılandırmak için uygulama yapılandırma ilkelerini kullanın.

## <a name="next-steps"></a>Sonraki adımlar
- [Android kurumsal tam yönetilen cihaz yapılandırma ilkeleri ekleme](device-restrictions-android-for-work.md#device-owner-only)
- [Android kurumsal tam olarak yönetilen cihazlar için uygulama yapılandırma ilkelerini yapılandırma](app-configuration-policies-use-android.md)

