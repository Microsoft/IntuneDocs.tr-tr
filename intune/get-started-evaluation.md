---
title: "Intune’u kullanmaya başlama"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="what-is-microsoft-intune"></a>Microsoft Intune nedir?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Azure portalında Microsoft Intune](./media/generic-intune-azure.png)

Microsoft Intune, Azure'un en yeni hizmetlerinden biridir. Kuruluşunuzun mobil cihazları, bilgisayarları ve [düzenli olarak güncelleştirilen](whats-new.md) uygulamalarını yönetmeniz için bazı araçlar sunar. Modern Azure konsolunun yanı sıra Intune, Klasik konsolu kullanmanıza da imkan verir. Klasik konsol, Intune’un ilk sürümüdür ve hala [Intune yazılım istemcisiyle Windows bilgisayarları yönetmek](/intune-classic/deploy-use/pc-management-comparison.md) için buraya gitmeniz gerekir. Silverlight olarak derlenen Klasik portal, çok az sayıda görev için kullanılır. Mobil cihaz ve uygulama yönetimi dahil olmak üzere diğer her şey Azure portalından gerçekleştirilir. Bu başlangıç kılavuzu, Azure portalında Intune’u başarıyla kullanmanız için gereken temel görevler konusunda size yol gösterir.

![Yardım ve destek dikey penceresi, Intune sol kenar çubuğundaki eylemler listenin en altında yer alır.](./media/intune-azure-help-support-closeup.png)

## <a name="what-does-intune-in-the-azure-portal-provide"></a>Azure portalında Intune ne işe yarar?

Azure portalında Intune size şunları sağlar:

* Tüm [Enterprise Mobility + Security (EMS) bileşenleriniz](https://docs.microsoft.com/enterprise-mobility-security) için tümleştirilmiş bir konsol
* [Modern web tarayıcılarını](supported-devices-browsers.md) destekleyen web standartlarında derlenmiş HTML tabanlı bir konsol
* Tüm Azure uygulamalarınızda uyumluluk sağlamak için [Azure Active Directory grupları](groups-get-started.md)
* [Microsoft Grafik API’si](intune-graph-apis.md) aracılığıyla otomasyon

## <a name="prerequisites"></a>Önkoşullar

Başlamadan önce etkin birer Intune yönetici ve kiracı hesabınızın olması gerekir. Bu hesaplara [buradan](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) kaydolabilirsiniz. Mevcut aboneler bu etkinlikleri de etkin kiracınızda tamamlayabilir. Yalnızca sınama cihazlarında çalıştığınızdan emin olun!

Ayrıca kılavuzdaki tüm görevleri tamamlamak için kuruluşunuzun genel yöneticisi olduğunuzdan emin olmalısınız.
