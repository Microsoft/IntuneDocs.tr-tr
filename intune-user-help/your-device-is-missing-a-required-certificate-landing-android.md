---
title: "Cihazınızda gerekli bir sertifika eksik | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 910fe2bc4e616c3b60d351efaffe173f58c04bc6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="your-device-is-missing-a-required-certificate"></a>Cihazınızda gerekli bir sertifika eksik

## <a name="whats-a-certificate"></a>Sertifika nedir?

[Şifreleme](https://technet.microsoft.com/library/cc962030.aspx), bilgiler için güvenlik sağlama bilimidir. Geleneksel olarak şifreleme, [iletişimin gizli tutulduğundan emin olmak için](https://technet.microsoft.com/library/cc962019.aspx) kodlanmış iletileri geçirmek üzere kullanılır. En basit şekliyle şifreleme, kodlanmış bir iletiyi okunamaz, anlaşılmaz veya gizli bir iletiye dönüştürmek için harflerin kendisini veya sırasını değiştirir. Yalnızca bir kod çözme anahtarına, yani _sertifikaya_ sahip kişiler, kodlanmış iletiyi özgün, okunabilir biçimine geri dönüştürebilir. Android cihazınız, Intune’daki sertifikaları kullanarak cihazınız ile e-posta ve belgeler gibi kurumsal kaynaklarınız arasındaki iletişimlerin bir uçtan diğerine geçiş yolculuğunda güvende tutulmasını sağlar.

## <a name="fixing-certificate-issues"></a>Sertifika sorunlarını giderme

Android cihazınız Intune’a kayıtlı değilse ve BT yöneticiniz tarafından gerekli kılınan bir sertifika cihazınızda bulunmuyorsa, Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Denemeniz gereken ilk adım, [genellikle cihazınıza önceden yüklenmiş olarak gelen bir sertifikanın eksik olup olmadığını kontrol etmektir](your-device-is-missing-a-preinstalled-certificate-android.md).

Bu işe yaramazsa, BT yöneticiniz [ek güvenlik için ikinci bir sertifika yüklemenizi gerekli kılabilir](your-device-is-missing-an-IT-required-certificate-android.md).

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.
