---
title: Bir macOS cihazı silme
titleSuffix: Microsoft Intune
description: Bir macOS cihazdan işletim sistemi dahil olmak üzere tüm verileri silmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d4203f559fc9c5f66a9b9317040c0123aecb1940
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237010"
---
# <a name="erase-all-data-from-a-macos-device"></a>Bir macOS cihazdan tüm verileri silme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir macOS cihazdan işletim sistemi dahil olmak üzere tüm verileri silebilirsiniz. Bu durumda cihaz Intune yönetiminden de kaldırılır. Son kullanıcıya herhangi bir uyarı yapılmaz.

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar** > **Tüm cihazlar**’a gidin > silmek istediğiniz cihazı seçin.
![Ekran görüntüsü](./media/device-erase/choosedevice.png)
2. **Daha fazla** > **Sil**’e tıklayın > **Kurtarma PIN’i** için 6 basamaklı bir sayı girin. Bu, cihazında işletim sistemini yeniden yükleyebilmesi için kullanıcıya vermeniz gereken PIN’dir. Bu PIN’i not ettiğinizden emin olun, silme işlemi tamamlandıktan sonra PIN’i göremezsiniz.
![Ekran görüntüsü](./media/device-erase/providepin.png)
3. **Tamam**’a tıklayarak cihazı silin.
