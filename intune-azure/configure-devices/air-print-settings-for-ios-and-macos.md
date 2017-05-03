---
title: "iOS ve macOS cihazları için Intune AirPrint ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS ve macOS cihazlarını AirPrint uyumlu yazıcılara otomatik olarak bağlamaya yardımcı olmak için Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: a0f60cad9a5e679c83572375c3dd83bc7aeebd93
ms.lasthandoff: 04/19/2017


---

# <a name="airprint-settings-for-ios-and-macos-devices"></a>iOS ve macOS cihazları için AirPrint ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

iOS veya macOS cihazlarını ağınızdaki AirPrint uyumlu yazıcılara otomatik olarak bağlamak için bu ayarları kullanın. Devam etmek için yazıcılarınızın IP adresine ve kaynak yoluna ihtiyacınız olacaktır.

## <a name="find-airprint-printer-information"></a>AirPrint yazıcı bilgilerini bulma

iOS cihazı kullanıcılarının bilinen AirPrint yazıcılarına yazdırabilmesi için AirPrint bilgilerini AirPrint yüküne eklemek üzere bu yordamı kullanın.

1. Airprint yazıcıları ile aynı yerel ağa (alt ağ) bağlı bir Mac cihazında Terminali açın (**/Applications/Utilities** bölümünden)
2. Terminale **ippfind** yazın ve ENTER tuşuna basın.
3. Komut tarafından döndürülen herhangi bir yazıcı bilgisini not edin, örneğin: **ipp://myprinter.local.:631/ipp/port1**. Bilginin ilk kısmı yazıcınızın adı, son kısmı ise kaynak yoludur.
4. Terminale **myprinter.local ping** yazın ve ENTER tuşuna basın.
5. Komut tarafından döndürülen IP adresini not edin, örneğin: **PING myprinter.local (10.50.25.21)**.
6. Son olarak, IP adresini ve kaynak yolunu AirPrint yükü ayarlarında kullanın. Örnek bir IP adresi **10.50.25.21**, örnek bir kaynak yolu ise **/ipp/port1** olabilir.

## <a name="configure-an-airprint-profile"></a>AirPrint profilini yapılandırma

1. **Cihaz özellikleri** dikey penceresinde **AirPrint**’i seçin.
2. **AirPrint** dikey penceresinde bir AirPrint hedefi eklemek için **IP adresini** ve **kaynak yolunu** girip **Ekle**’ye tıklayın.
3. Gereksinim duyduğunuz kadar hedef eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.

Yazıcıların bir listesini virgülle ayrılmış değerler (.csv) dosyasından içeri veya dışarı aktarabilirsiniz.

