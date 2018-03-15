---
title: "Windows 10 cihazlarını Intune ile sıfırlama"
titlesuffix: Azure portal
description: "Intune çalıştıran Windows 10 bilgisayarlarını sıfırlamak için Fresh Start kullanma hakkında bilgi edinin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c45d3e47c90ca7739b3aa6eee1bf31d787a82264
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Windows 10 cihazlarını Intune ile sıfırlamak için Fresh Start kullanma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Fresh Start** cihaz eylemi, Creators Update çalıştıran bir Windows 10 bilgisayarında yüklü tüm uygulamaları kaldırır, sonra bilgisayarı en son Windows sürümüne otomatik olarak güncelleştirir.
Bu eylem genellikle yeni bir PC ile gelen önceden yüklü OEM uygulamalarının kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz. Bu durumda uygulamalar ve ayarlar kaldırılır, ancak kullanıcıların Giriş klasörünün içeriği korunur.

## <a name="how-to-use-fresh-start"></a>Yeni Başlangıç nasıl kullanılır?

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde, **Cihazlar**’ı seçin.
4. **Cihazlar** bölmesinde, **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden bir Windows 10 masaüstü cihazını seçin, sonra **Fresh Start** uzak cihaz eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar** bölmesinde, **Cihaz eylemleri**'ni seçin.

