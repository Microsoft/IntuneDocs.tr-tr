---
title: "Uygulama bilgilerini ve atamalarını izleme | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Kullanıcılara veya cihazlara uygulama atadıktan sonra, atamanın durumunu izlemenize yardımcı olması için bu bilgileri kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7c39c904cd2a7bd20525d9072067c6e484b4437a
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune, yönettiğiniz uygulamanın özelliklerini ve bunların atama durumunu izleyebilmeniz için çeşitli yollar sağlar.

1. **Mobil Uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
2. Uygulama listesi dikey penceresinde bilgilerini görmek istediğiniz uygulamayı seçin. <*uygulama adı*> **Cihaz yükleme durumu** dikey penceresi görüntülenmelidir: ![Uygulama yükleme durumu dikey penceresi.](./media/monitor-apps.png)

Ardından, uygulamalarınız ve onların atamaları hakkında daha fazla bilgi edinmek için aşağıdaki işlemlerden birini yapın.

## <a name="general"></a>Genel

- **Genel bakış** - Uygulamanın temel genel bakış bilgilerini ve o uygulamaya ilişkin atamaların durum bilgilerini sağlar. **Cihaz yükleme durumu** veya **Kullanıcı yükleme durumu** dikey penceresini açıp daha ayrıntılı bilgilere ulaşmak için grafiklerden birini seçebilirsiniz.

## <a name="manage"></a>Bilgisayarlarda

- **Özellikler** - Seçilen uygulama hakkındaki bilgileri görüntülemenizi ve değiştirmenizi sağlar. Uygulama özellikleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).
- **Atamalar** - Bu uygulamaya ilişkin atamalar hakkında bilgi sağlar. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

## <a name="monitor"></a>İzle

- **Cihaz yükleme durumu** - Seçili uygulamayı atadığınız her cihazla ilgili ayrıntılı bilgileri (cihaz adı, işletim sistemi, cihazın Intune’a son iade edilme zamanı ve uygulama yüklemesinin durumu) sağlar.
- **Kullanıcı yükleme durumu** - Seçili uygulamayı atadığınız kullanıcıyla ilgili ayrıntılı bilgileri (uygulamanın kullanıcının tüm cihazlarındaki yükleme sayısı ve yükleme hatalarıyla ilgili bilgiler) sağlar.