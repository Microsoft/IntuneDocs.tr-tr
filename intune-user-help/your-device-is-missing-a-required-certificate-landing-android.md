---
title: "Cihazınızda gerekli bir sertifika eksik | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7c454584df4f0eb6b3a9dfe10ee7b887bcdee2ca
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="your-device-is-missing-a-required-certificate"></a>Cihazınızda gerekli bir sertifika eksik

## <a name="whats-a-certificate"></a>Sertifika nedir?

[Şifreleme](https://technet.microsoft.com/library/cc962030.aspx), bilgiler için güvenlik sağlama bilimidir. Geleneksel olarak şifreleme, [iletişimin gizli tutulduğundan emin olmak için](https://technet.microsoft.com/library/cc962019.aspx) kodlanmış iletileri geçirmek üzere kullanılır. En basit şekliyle şifreleme, kodlanmış bir iletiyi okunamaz, anlaşılmaz veya gizli bir iletiye dönüştürmek için harflerin kendisini veya sırasını değiştirir. Yalnızca bir kod çözme anahtarına, yani _sertifikaya_ sahip kişiler, kodlanmış iletiyi özgün, okunabilir biçimine geri dönüştürebilir. Android cihazınız, Intune’daki sertifikaları kullanarak cihazınız ile e-posta ve belgeler gibi kurumsal kaynaklarınız arasındaki iletişimlerin bir uçtan diğerine geçiş yolculuğunda güvende tutulmasını sağlar.

## <a name="fixing-certificate-issues"></a>Sertifika sorunlarını giderme

Android cihazınız Intune’a kayıtlı değilse ve şirketinizin destek birimi tarafından gerekli kılınan bir sertifika cihazınızda bulunmuyorsa, Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Denemeniz gereken ilk adım, [genellikle cihazınıza önceden yüklenmiş olarak gelen bir sertifikanın eksik olup olmadığını kontrol etmektir](your-device-is-missing-a-preinstalled-certificate-android.md).

Bu işe yaramazsa, şirketinizin destek birimi [ek güvenlik için ikinci bir sertifika yüklemenizi gerekli kılabilir](your-device-is-missing-an-IT-required-certificate-android.md).

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın.
