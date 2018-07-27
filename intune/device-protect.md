---
title: Cihazları Microsoft Intune ile koruma
titleSuffix: Microsoft Intune
description: Intune’un cihazlarınızı yetkisiz erişime veya diğer tehditlere karşı korumanıza yardımcı olabileceği yollardan bazılarını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.openlocfilehash: bb9606a8586e0dbdbb566def344c9c551cb09e52
ms.sourcegitcommit: a8b544975156dd45c2bf215b57ac994415b568bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39164838"
---
# <a name="protect-devices-with-microsoft-intune"></a>Cihazları Microsoft Intune ile koruma

Microsoft Intune, yönettiğiniz cihazları ve bu cihazlarda depolanan verileri korumanıza yardımcı olur.

## <a name="device-configuration"></a>Cihaz yapılandırması
Intune [yapılandırma ilkeleri](device-profiles.md), çeşitli ayar ve özellikleri denetleyerek cihazları korumanıza ve yapılandırmanıza yardımcı olur. Örneğin:
- Cihazdaki kamera veya Bluetooth gibi donanım özelliklerinin kullanımını kısıtlayabilirsiniz.
- Uyumlu ve uyumsuz uygulamaları yapılandırabilirsiniz. Uyumsuz bir uygulama yüklenirse size uyarı verilir (ve bazı platformlar yüklemeyi engelleyebilir).

## <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Kullanıcılar kilitlenen cihazlarına erişemediğinde geçiş kodlarını sıfırlama
Mobil cihazlarda şirket verilerini korumanın ilk adımı cihazı kullanmak için bir geçiş kodu istenmesi olduğundan, bazen bir [geçiş kodunu sıfırlamanız](device-passcode-reset.md) ya da geçiş kodunu kaldırarak veya uzaktan geçici geçiş kodu ayarlayarak bir çalışana kodu sıfırlaması için yardımcı olmanız gerekir. Ayrıca kaybedilirse veya çalınırsa [bir cihazı uzaktan kilitleyebilirsiniz](device-remote-lock.md).

## <a name="retire-devices-and-remove-data"></a>Cihazları devre dışı bırakma ve verileri kaldırma
Bir cihazın [Intune yönetiminden kaldırılması](devices-wipe.md) gerektiğinde (örneğin, bir kullanıcı ayrıldığında veya cihaz kaybedildiğinde ya da çalındığında), bu cihazdaki verileri kaldırmak isteyeceksinizdir. Intune, şirketinizin verilerinin güvenli kalmasını sağlamak için bir dizi yöntem sunar.

## <a name="require-devices-to-be-compliant"></a>Cihazların uyumlu olmasını zorunlu kılma
Intune’da belirttiğiniz kurallarla uyumlu olmayan cihazları değerlendirmenize (ve bazı durumlarda düzeltmenize) izin veren [cihaz uyumluluk ilkeleri](device-compliance-get-started.md) bulunur. Örneğin, şuna dair raporları alabilirsiniz:
- jailbreak uygulanmış iOS cihazlar
- şifrelenmiş veya şifrelenmemiş cihazlar
- Windows 10 cihaz sistem durumu (Sistem Durumu Kanıtlama Hizmeti tarafından belirlendiği gibi).

## <a name="protect-apps-and-the-data-they-use"></a>Uygulamaları ve kullandıkları verileri koruma
Intune, uygulamaları ve bunların verilerini korumanıza yardımcı olmak için size bir dizi özellik sunar. Örneğin, mobil uygulama yönetimi (MAM) ilkesi şunları yapabilir:
- verilerin korumalı bir uygulamadan yedeklenmesini engeller
- diğer uygulamalara kopyalama ve yapıştırmayı kısıtlar
- bir uygulamaya erişim için PIN gerektirir Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları ve verileri koruma](app-protection-policy.md)

## <a name="add-an-additional-layer-of-protection-to-devices"></a>Cihazlara ek bir koruma katmanı ekleme
[Çok faktörlü kimlik doğrulaması (MFA)](multi-factor-authentication.md), ağdaki cihazları kullananların kimliklerini doğrulamanın daha güvenli bir yoludur.  MFA ile, kullanıcıların, kimliklerini kullanıcı adı ve parolanın ötesinde, bir telefon konuşması veya kısa mesaj üzerinden doğrulaması gerekir.

## <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Windows cihazlarda İş İçin Windows Hello ayarlarını denetleme
Intune, Windows 10 için alternatif bir oturum açma yöntemi olan [İş İçin Windows Hello](windows-hello.md)’yu tümleştirmenizi sağlar ve daha sonra bu, bir parola, akıllı kart veya sanal akıllı kartı değiştirmek için Active Directory veya Azure Active Directory hesabı kullanır.

## <a name="bypass-activation-lock-on-ios-devices"></a>iOS’de Etkinleştirme Kilidini Atlama
Etkinleştirme Kilidi kullanıcıların cihazlarını korumaya yardımcı olan bir özelliktir. Bu özellik, herhangi birinin cihazı silmesi veya yeniden etkinleştirmesi için kullanıcıların Apple kimliğini veya parolasını girmesini ister. Ancak bu özellik, örneğin kullanıcının kilidi kaldırmadan şirketten ayrılması durumunda sorunlara yol açabilir. [iOS Etkinleştirme Kilidi atlama]( device-activation-lock-bypass.md), denetimli iOS cihazlarından kilidi kaldırarak bu cihazları yeniden kullanıma almanıza veya silmenize yardımcı olabilir.

## <a name="next-steps"></a>Sonraki adımlar

[Mobil tehdit savunması](mobile-threat-defense.md) hakkında daha fazla bilgi edinin

