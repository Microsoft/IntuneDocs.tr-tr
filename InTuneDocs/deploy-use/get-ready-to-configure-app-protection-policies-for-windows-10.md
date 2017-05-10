---
title: "Windows 10 için uygulama koruma ilkeleri yapılandırmaya hazırlanma | Microsoft Docs"
description: "Azure AD’de mobil uygulama yönetimi (MAM) sağlayıcısı kurma"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 86a59771fc57971a626f71083e81cd4b7d858cfa
ms.lasthandoff: 04/25/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Windows 10 için uygulama koruma ilkeleri yapılandırmaya hazırlanma

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Bir Windows 10 uygulama koruma ilkesi oluşturmadan önce, Azure AD’de MAM sağlayıcıyı kurarak Windows 10 için mobil uygulama yönetimini (MAM) etkinleştirmeniz gerekir. Bu yapılandırma, Intune ile yeni bir Windows Bilgi Koruması (WIP) ilkesi oluştururken kayıt durumunu tanımlamanızı sağlar.

> [!NOTE]
> Kayıt durumu MAM ya da mobil cihaz yönetimi (MDM) olabilir.

## <a name="to-configure-the-mam-provider"></a>MAM sağlayıcısını yapılandırmak için

1.  [Azure Portal](https://portal.azure.com/)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  Sol menüden **Azure Active Directory**’yi seçin.

    ![MAM sağlayıcı yapılandırması](../media/AppManagement/mam-provider-sc-1.png)

3.  **Azure AD** dikey penceresi açıldığında, **Mobility (MDM ve MAM)** seçeneğini işaretleyin, ardından **Microsoft Intune**’a tıklayın.

    ![Mobility MDM ve MAM](../media/AppManagement/mam-provider-sc-1.png)

4.  Yapılandırma dikey penceresi açıldığında, önce **Varsayılan MAM URL'lerini geri yükle**’yi seçin, sonra şunları yapılandırın:

    a.  MAM kullanıcı kapsamı: MAM’yi Windows 10 cihazları kullanan belirli bir kullanıcı grubundaki veya tüm kullanıcılardaki kurumsal verileri korumak için kullanabilirsiniz.

    b.  MAM kullanım koşulları URL’si: MAM hizmetinin kullanım koşulları uç noktasının URL'si. Son kullanıcılara MAM hizmetinin koşullarını görüntülemek için kullanılır.

    c.  MAM bulma URL'si: Uygulama koruma ilkeleri uygulamaları gerektiğinde cihazların aradığı URL’dir.

    d.  MDM uyumluluğu URL’si:

5.  Bu ayarları yapılandırdıktan sonra **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

[WIP uygulama koruma ilkesi oluşturma](https://docs.microsoft.com/intune/deploy-use/create-windows-information-protection-policy-with-intune)
