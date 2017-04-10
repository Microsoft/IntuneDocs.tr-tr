---
title: "Microsoft Intune Önizlemesinde bilinen sorunlar"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Önizlemedeki bilinen sorunlar hakkında sağlanan bilgileri okuyun"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Microsoft Intune önizlemesinde bilinen sorunlar


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Intune önizlemesindeki tüm bilinen sorunlar hakkında bilgi edinmek için bu konuyu kullanın.

Burada listelenmeyen bir hatayı bildirmek istiyorsanız, [bir destek isteği açın](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Intune’a yeni bir özellik eklenmesini istiyorsanız, [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) sitemizde bir rapor doldurabilirsiniz.

## <a name="administration-and-accounts"></a>Yönetim ve hesaplar

- Genel Yöneticiler (Kiracı Yöneticileri olarak da bilinir) ayrı bir Intune veya Enterprise Mobility Suite (EMS) lisansı olmadan günlük yönetim görevlerine devam edebilir. Ancak, Genel Yöneticiler kendi cihazlarını veya bir şirket cihazını kaydetme gibi amaçlarla hizmeti kullanmak ya da Intune Şirket Portalı’nı kullanmak isterse diğer tüm kullanıcılar gibi bir Intune veya EMS lisansına ihtiyaç duyacaklardır.

## <a name="apple-enrollment-profile-migration"></a>Apple kayıt profili geçişi
- Intune, önümüzdeki birkaç ay içinde Apple Aygıt Kayıt Programı ve Apple Configurator kayıtlarınızı yeni Azure Portal aracılığıyla yönetmenize olanak sağlayacaktır. Apple Aygıt Kayıt Programı belirtecini siler ve güncelleştirilmiş bir belirteci karşıya yüklemezseniz özgün belirteç, Intune hesabınızı geçirme sürecinin bir parçası olarak yeni Azure Portal’a geri yüklenir. Bu belirteci kaldırmak ve DEP kaydını önlemek için belirteci Azure Portal’da silmeniz yeterlidir. 

