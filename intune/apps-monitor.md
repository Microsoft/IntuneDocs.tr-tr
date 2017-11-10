---
title: "Uygulama bilgilerini ve atamaları izleme"
titlesuffix: Azure portal
description: "Kullanıcılara veya cihazlara uygulama atadıktan sonra, atamanın durumunu izlemenize yardımcı olması için bu bilgileri kullanın.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune, yönettiğiniz uygulamanın özelliklerini ve bunların atama durumunu izleyebilmeniz için çeşitli yollar sağlar.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Mobil uygulamalar** iş yükünde **Yönet** grubunda **Uygulamalar**’ı seçin.
     
    ![Uygulama yükleme durumu dikey penceresi.](./media/monitor-apps.png)
5. Uygulama listesi dikey penceresinde bir uygulama seçin. <*uygulama adı*> **Cihaz yükleme durumu** dikey penceresi görüntülenir.

Cihaz yükleme durumu raporu aşağıdaki sütunları içerir:

1.  **Cihaz Adı** Cihaz türünün adı.
2.  **Kullanıcı Adı** Kullanıcı adı.
3.   **Platform** Cihazda yüklü işletim sistemi.
4.  **Sürüm** Uygulamanın sürüm numarası.
5.   **Durum** Uygulamalar için olası durumlar şunlardır: **Yüklü**, **Yüklü Değil**, **Yükleme Bekleniyor** ve **Hata**.
6. **Durum Ayrıntıları** Cihazdaki uygulama durumunun okunabilir bir açıklaması.
7. **Son İade** Cihazın Intune’a son iade edilme zamanı.

Ardından, uygulamalarınız ve onların atamaları hakkında daha fazla bilgi edinmek için aşağıdaki işlemlerden birini yapın.

## <a name="general"></a>Genel

- **Genel bakış** - Uygulamanın temel genel bakış bilgilerini ve o uygulamaya ilişkin atamaların durum bilgilerini sağlar. **Cihaz yükleme durumu** veya **Kullanıcı yükleme durumu** dikey penceresini açıp daha ayrıntılı bilgilere ulaşmak için grafiklerden birini seçebilirsiniz.

## <a name="manage"></a>Bilgisayarlarda

- **Özellikler** - Seçilen uygulama hakkındaki bilgileri görüntülemenizi ve değiştirmenizi sağlar. Uygulama özellikleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).
- **Atamalar** - Bu uygulamaya ilişkin atamalar hakkında bilgi sağlar. Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

## <a name="monitor"></a>İzle

- **Cihaz yükleme durumu** - Seçili uygulamayı atadığınız her cihazla ilgili ayrıntılı bilgileri (cihaz adı, işletim sistemi, cihazın Intune’a son iade edilme zamanı ve uygulama yüklemesinin durumu) sağlar.
- **Kullanıcı yükleme durumu** - Seçili uygulamayı atadığınız kullanıcıyla ilgili ayrıntılı bilgileri (kullanıcının tüm cihazlarındaki uygulama yüklenme sayısıyla ilgili bilgiler dahil olmak üzere) ve yükleme hatalarıyla ilgili bilgileri sağlar.