---
title: iOS çalıştıran cihazlar için Microsoft Intune özel ayarları
titleSuffix: ''
description: Microsoft Intune’da bir iOS özel profilinde kullanabileceğiniz ayarları öğrenin.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3c92b8816dd6c5afd96cb8853b6d251ff5befaf4
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>iOS çalıştıran cihazlar için Microsoft Intune özel cihaz ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[Apple Configurator aracını](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) kullanarak oluşturduğunuz ayarları iOS cihazlarına atamak için Microsoft Intune iOS özel profilini kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune iOS özel profiline aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara atayabilirsiniz.

Bu özellik, diğer Intune profil türleriyle yapılandırılamayan iOS ayarlarını atamanıza olanak tanır.


1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. **Özel Yapılandırma Profili** bölmesinde aşağıdaki ayarların her birini yapılandırın:

- **Özel yapılandırma profili adı** - Cihazda ve Intune durum bilgisinde gösterildiği haliyle ilke için bir ad girin.
- **Yapılandırma profili dosyası** - Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin.
Apple Configurator aracından dışarı aktardığınız ayarların, iOS özel ilkesini atadığınız cihazlardaki iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların nasıl çözümleneceği hakkında bilgi için, [Apple Developer](https://developer.apple.com/) web sitesinde **Yapılandırma Profili Başvurusu** ve **Mobil Cihaz Yönetim Protokolü Başvurusu** öğelerini arayın.

İçeri aktardığınız dosya, bölmenin **Dosya içeriği** alanında görüntülenir.
