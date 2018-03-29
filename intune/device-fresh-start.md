---
title: Microsoft Intune - Azure ile Windows 10 cihazlarını sıfırlama | Microsoft Docs
description: Microsoft Intune kullanarak Windows 10 bilgisayarlarındaki uygulamaları silmek veya kaldırmak için Yeni Başlangıç'ı kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 902ffbcd8f12ba6deb215a54ce378fae94d20426
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Windows 10 cihazlarını Intune ile sıfırlamak için Fresh Start kullanma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Yeni Başlangıç** cihaz eylemi, Creators Update çalıştıran Windows 10 bilgisayarına yüklenmiş tüm uygulamaları kaldırır. Ardından bilgisayarı otomatik olarak en son Windows sürümüne güncelleştirir.

Bu eylem, genellikle yeni bir bilgisayara önceden yüklenmiş (OEM) uygulamaları kaldırmaya yardımcı olur. Kullanıcının Giriş klasörünün içeriğini saklamak ve yalnızca uygulamaları ve ayarları kaldırmak için `if user data is retained` ayarını kullanın.

> [!IMPORTANT]
> Yeni Başlangıç, cihazın Intune kaydını siler ancak cihaz Azure Active Directory'ye bağlı kalmayı sürdürür.

## <a name="use-fresh-start"></a>Yeni Başlangıç kullanma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir Windows 10 masaüstü cihazını seçin, sonra **Yeni Başlangıç**’ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

Bu eylemin durumunu görmek için **Cihaz eylemleri** (**Microsoft Intune** > **Cihazlar**) seçimi yapın.