---
title: "Windows Phone 8.1 çalıştıran cihazlar için Microsoft Intune özel ayarları"
titleSuffix: 
description: "Windows Phone 8.1 özel profilinde kullanabileceğiniz ayarlar hakkında bilgi edinin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f45b2dd9cab0ccfd912d1f1348d90264bf8906b8
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Windows Phone 8.1 çalıştıran cihazlar için Microsoft Intune özel cihaz ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows Phone 8.1 cihazlardaki özellikleri denetlemek amacıyla kullanılabilen OMA-URI ayarlarını atamak için Microsoft Intune Windows Phone 8.1 **Özel** profilini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, diğer Intune ilkeleriyle ile yapılandırılamayan ayarları atamanıza olanak sağlamak için tasarlanmıştır.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Windows Phone 8.1 cihazları için özel ilke ayarları

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. **Özel OMA-URI Ayarları** bölmesinde **Ekle**'yi seçerek bir veya birden çok OMA-URI ayarı ekleyin.
3. **Satır Ekle** bölmesinde, her ayar için aşağıdaki değerleri yapılandırın:
    - **Ad** - Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama** - Ayara genel bir bakış sağlayan ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama belirtin.
    - **OMA-URI** - Ayar sağlamak istediğiniz OMA-URI’yi belirtin.
    - **Veri türü** - Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize**, **Dize (XML)**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta**, **Boole** veya **Base64** seçeneklerinden birini belirleyin.
    - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz değeri veya dosyayı girin.

4. Bitirdiğinizde **Tamam**’a tıklayın, ardından gereken diğer ayarları eklemeye devam edin.
