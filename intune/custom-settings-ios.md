---
title: "iOS cihazları için Intune özel ayarları"
titleSuffix: Intune on Azure
description: "Bir iOS özel profilinde kullanabileceğiniz ayarları öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b169fe74063b618f947f5d3d6809e0e49a5136e3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>iOS cihazları için Microsoft Intune özel ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[Apple Configurator aracını](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) kullanarak oluşturduğunuz ayarları iOS cihazlarına atamak için Microsoft Intune iOS özel profilini kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune iOS özel profiline aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara atayabilirsiniz.

Bu özellik, diğer Intune profil türleriyle yapılandırılamayan iOS ayarlarını atamanıza olanak tanır.


1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. **Profil Oluştur** dikey penceresinde aşağıdakileri belirtin:

- **Özel yapılandırma profili adı** - Cihazda ve Intune durum bilgisinde gösterileceği haliyle ilke için bir ad girin.
- **Yapılandırma profili dosyası** - Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin.
Apple Configurator aracından dışarı aktardığınız ayarların, iOS özel ilkesini atadığınız cihazlardaki iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların nasıl çözümleneceği hakkında bilgi için, [Apple Developer](https://developer.apple.com/) web sitesinde **Yapılandırma Profili Başvurusu** ve **Mobil Cihaz Yönetim Protokolü Başvurusu** öğelerini arayın.

İçeri aktardığınız dosya, dikey pencerenin **Dosya içeriği** alanında görüntülenir.
