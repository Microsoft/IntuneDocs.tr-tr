---
title: Bir macOS cihazı silme
titleSuffix: Microsoft Intune
description: Bir macOS cihazdan işletim sistemi dahil olmak üzere tüm verileri silmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6ae04abda7f026bcbc02e325274712a386147b8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="erase-all-data-from-a-macos-device"></a>Bir macOS cihazdan tüm verileri silme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir macOS cihazdan işletim sistemi dahil olmak üzere tüm verileri silebilirsiniz. Bu durumda cihaz Intune yönetiminden de kaldırılır. Son kullanıcıya herhangi bir uyarı yapılmaz.

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar** > **Tüm cihazlar**’a gidin > silmek istediğiniz cihazı seçin.
![Ekran görüntüsü](./media/device-erase/choosedevice.png)
2. **Daha fazla** > **Sil**’e tıklayın > **Kurtarma PIN’i** için 6 basamaklı bir sayı girin. Bu, cihazında işletim sistemini yeniden yükleyebilmesi için kullanıcıya vermeniz gereken PIN’dir. Bu PIN’i not ettiğinizden emin olun, silme işlemi tamamlandıktan sonra PIN’i göremezsiniz.
![Ekran görüntüsü](./media/device-erase/providepin.png)
3. **Tamam**’a tıklayarak cihazı silin.
