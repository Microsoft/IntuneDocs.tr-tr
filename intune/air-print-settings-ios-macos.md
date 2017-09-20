---
title: "iOS ve macOS cihazları için Intune AirPrint ayarları"
titlesuffix: Azure portal
description: "iOS ve macOS cihazlarını AirPrint uyumlu yazıcılara otomatik olarak bağlamaya yardımcı olmak için Intune’u nasıl kullanabileceğinizi öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bf8e076ff5ff4266f36d0a86697558b309a7fc36
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2017
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>iOS ve macOS cihazları için AirPrint ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

1. **Cihaz özellikleri** dikey penceresinde **AirPrint**'i seçin.
2. **AirPrint** dikey penceresinde bir AirPrint hedefi eklemek için **IP adresini** ve **kaynak yolunu** girip **Ekle**’ye tıklayın.
3. Gereksinim duyduğunuz kadar hedef eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.

Yazıcıların bir listesini virgülle ayrılmış değerler (.csv) dosyasından içeri veya dışarı aktarabilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).