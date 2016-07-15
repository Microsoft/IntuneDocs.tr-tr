---
title: "Microsoft Intune'a şirketin sahip olduğu iOS cihazları kaydetme | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 48359b44bec9ac3e1c9510debc01d2cf8abf6d2b


---

# Microsoft Intune'a şirketin sahip olduğu iOS cihazları kaydetme
Microsoft Intune, Apple Cihaz Kayıt Programı (DEP) veya bir Mac bilgisayarda çalışan [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) aracı kullanarak şirketin sahip olduğu iOS cihazlarının kaydedilmesini destekler.

Şirket tarafından kaydedilen iOS cihazlarını üç yolla kaydedebilirsiniz:

-   **Kurulum Yardımcısı Kaydı** – Fabrika cihazı sıfırlar ve cihazın yeni kullanıcısı tarafından kurulum yapılması için hazırlar. Bu yöntem, yöneticinin kaydı önceden yapılandırması için iOS cihazını Apple Configurator çalıştıran bir Mac bilgisayara USB üzerinden bağlamasını gerektirir. Cihazlar daha sonra kullanıcılara gönderilir, kullanıcılar, Kurulum Yardımcısı sürecini yürüterek cihazı iş veya okul kimlik bilgileriyle yapılandırır ve kaydolma sürecini tamamlar. [Apple Configurator ve Kurulum Yardımcısı'nı kullanarak iOS cihazlarını kaydetme](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Doğrudan Kayıt** – Cihaz hazırlığı sırasında kullanılmak üzere Apple Configurator ile uyumlu bir dosya oluşturur. Kaydedilen cihaz fabrika ayarlı değildir, ancak hiçbir kullanıcı ilişkisi içermez. Bu yöntem, yöneticinin cihazı kaydetmek üzere iOS cihazını Apple Configurator çalıştıran bir Mac bilgisayara USB üzerinden bağlamasını gerektirir. [Apple Configurator Doğrudan Kayıt kullanarak iOS cihazlarını kaydetme](ios-direct-enrollment-in-microsoft-intune.md)

-   **Cihaz Kayıt Programı (DEP)** – Apple’ın Cihaz Kaydı Programı üzerinden satın alınan cihazlara “uzaktan” bir kayıt profili dağıtır. Kullanıcı cihazda Kurulum Yardımcısı’nı çalıştırdığında, cihaz Intune'da kaydedilir.  DEP ile kaydedilen cihazların kaydı kullanıcılar tarafından geri alınamaz. [Cihaz Kayıt Programı iOS cihazlarını kaydetme](ios-device-enrollment-program-in-microsoft-intune.md)




### Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


