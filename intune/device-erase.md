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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 64f8b31c4fab5b247ae466df52a0b965f1be813b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179975"
---
# <a name="erase-all-data-from-a-macos-device"></a>Bir macOS cihazdan tüm verileri silme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir macOS cihazdan işletim sistemi dahil olmak üzere tüm verileri silebilirsiniz. Bu durumda cihaz Intune yönetiminden de kaldırılır. Son kullanıcıya herhangi bir uyarı yapılmaz.

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar** > **Tüm cihazlar**’a gidin > silmek istediğiniz cihazı seçin.
![Ekran görüntüsü](./media/device-erase/choosedevice.png)
2. **Daha fazla** > **Sil**’e tıklayın > **Kurtarma PIN’i** için 6 basamaklı bir sayı girin. Bu, cihazında işletim sistemini yeniden yükleyebilmesi için kullanıcıya vermeniz gereken PIN’dir. Bu PIN’i not ettiğinizden emin olun, silme işlemi tamamlandıktan sonra PIN’i göremezsiniz.
![Ekran görüntüsü](./media/device-erase/providepin.png)
3. **Tamam**’a tıklayarak cihazı silin.
