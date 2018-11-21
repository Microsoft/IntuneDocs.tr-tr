---
title: iOS ve macOS cihazları için Intune AirPrint ayarları
titlesuffix: Microsoft Intune
description: iOS ve macOS cihazlarını AirPrint uyumlu yazıcılara otomatik olarak bağlamaya yardımcı olmak için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 850c61868cc5404d1645482a6998856e465b4070
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186299"
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>iOS ve macOS cihazları için AirPrint ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

iOS veya macOS cihazlarını ağınızdaki AirPrint uyumlu yazıcılara otomatik olarak bağlamak için bu ayarları kullanın. Devam etmek için yazıcılarınızın IP adresi ve kaynak yolu gerekir.

## <a name="find-airprint-printer-information"></a>AirPrint yazıcı bilgilerini bulma

iOS cihazı kullanıcılarının bilinen AirPrint yazıcılarına yazdırabilmesi için AirPrint bilgilerini AirPrint yüküne eklemek üzere bu yordamı kullanın.

1. AirPrint yazıcıları ile aynı yerel ağa (alt ağ) bağlı bir Mac cihazında Terminali açın (**/Applications/Utilities** bölümünden)
2. Terminale **ippfind** yazın ve ENTER tuşuna basın.
3. Komut tarafından döndürülen herhangi bir yazıcı bilgisini not edin, örneğin: **ipp://myprinter.local.:631/ipp/port1**. Bilginin ilk kısmı yazıcınızın adı, son kısmı ise kaynak yoludur.
4. Terminale **myprinter.local ping** yazın ve ENTER tuşuna basın.
5. Komut tarafından döndürülen IP adresini not edin, örneğin: **PING myprinter.local (10.50.25.21)**.
6. Son olarak, IP adresini ve kaynak yolunu AirPrint yükü ayarlarında kullanın. Örnek bir IP adresi **10.50.25.21**, örnek bir kaynak yolu ise **/ipp/port1** olabilir.

## <a name="configure-an-airprint-profile"></a>AirPrint profilini yapılandırma

1. [Azure Portalı’nda Intune](https://portal.azure.com)’dan, cihaz yapılandırma alanındaki [**Cihaz özellikleri**’ne gidin](device-features-configure.md). 
1. **Cihaz özellikleri** bölmesinde **AirPrint**’i seçin.
2. **AirPrint** bölmesinde bir AirPrint hedefi eklemek için **IP adresini** ve **kaynak yolunu** girip **Ekle**’ye tıklayın.
3. Gereksinim duyduğunuz kadar hedef eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.

Yazıcıların bir listesini virgülle ayrılmış değerler (.csv) dosyasından içeri veya dışarı aktarabilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).