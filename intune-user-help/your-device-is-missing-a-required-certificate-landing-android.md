---
title: Cihazınızda gerekli bir sertifika eksik | Microsoft Docs
titlesuffix: Microsoft Intune
description: Cihazınızda şirketinizin destek birimi tarafından gerekli bir sertifika eksik.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc86a53dd790059297430fd6b08f1a699aafbc84
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850667"
---
# <a name="your-device-is-missing-a-required-certificate"></a>Cihazınızda gerekli bir sertifika eksik

## <a name="whats-a-certificate"></a>Sertifika nedir?

[Şifreleme](https://technet.microsoft.com/library/cc962030.aspx), bilgiler için güvenlik sağlama bilimidir. Geleneksel olarak şifreleme, [iletişimin gizli tutulduğundan emin olmak için](https://technet.microsoft.com/library/cc962019.aspx) kodlanmış iletileri geçirmek üzere kullanılır. Kendi simplist formunda şifreleme değiştirir veya kodlanmış bir iletiyi okunamaz, anlaşılmaz veya gizli iletisine için harflerin kendisini veya sırasını değiştirir. Yalnızca bir kod çözme anahtarına, yani _sertifikaya_ sahip kişiler, kodlanmış iletiyi özgün, okunabilir biçimine geri dönüştürebilir. Android cihazınız, Intune’daki sertifikaları kullanarak cihazınız ile e-posta ve belgeler gibi kurumsal kaynaklarınız arasındaki iletişimlerin bir uçtan diğerine geçiş yolculuğunda güvende tutulmasını sağlar.

## <a name="fixing-certificate-issues"></a>Sertifika sorunlarını giderme

Android cihazınız Intune’a kayıtlı değilse ve şirketinizin destek birimi tarafından gerekli kılınan bir sertifika cihazınızda bulunmuyorsa, Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Denemeniz gereken ilk adım, [genellikle cihazınıza önceden yüklenmiş olarak gelen bir sertifikanın eksik olup olmadığını kontrol etmektir](your-device-is-missing-a-preinstalled-certificate-android.md).

Sertifika sorunlarını çözme işe yaramazsa, şirketinizin destek birimi [ek güvenlik için ikinci bir sertifika yüklemek ihtiyaç duyduğunuz](your-device-is-missing-an-IT-required-certificate-android.md).

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
