---
title: "Windows 10 cihazlarını Intune ile sıfırlama"
titleSuffix: Intune on Azure
description: "Intune çalıştıran Windows 10 bilgisayarlarını sıfırlamak için Fresh Start kullanma hakkında bilgi edinin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44633f244536a0033dd51fc06e1dba09c0490500
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Windows 10 cihazlarını Intune ile sıfırlamak için Fresh Start kullanma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Fresh Start** cihaz eylemi, Creators Update çalıştıran bir Windows 10 bilgisayarında yüklü tüm uygulamaları kaldırır, sonra bilgisayarı en son Windows sürümüne otomatik olarak güncelleştirir.
Bu eylem genellikle yeni bir PC ile gelen önceden yüklü (OEM) uygulamaların kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz. Bu durumda uygulamalar ve ayarlar kaldırılır, ancak kullanıcıların Giriş klasörünün içeriği korunur.

## <a name="how-to-use-fresh-start"></a>Yeni Başlangıç nasıl kullanılır?

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir Windows 10 masaüstü cihazını seçin, sonra **Fresh Start** uzak cihaz eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.

