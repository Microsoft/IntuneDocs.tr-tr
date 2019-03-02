---
title: Microsoft Intune - Azure ile cihazları eşitleme | Microsoft Docs
description: En son ilkeleri ve eylemleri almak için Microsoft Intune ile kayıtlı veya yönetilen cihazları eşitleyin. Azure portalını kullanarak eşitleme adımlarını içerir ve yeniden denenebilecek hata kodlarını listeler.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/28/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 979430ae90ed5599f8192a8707e6c53c754c0708
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230525"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Intune ile en son ilkeleri ve eylemleri almak için cihazları eşitleme


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cihazı **Eşitle** eylemi, seçili cihazı Intune’a hemen giriş yapmaya zorlar. Bir cihaz giriş yaptığında, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır. Bu özellik, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanıza ve ilkelerin sorunlarını gidermenize yardımcı olur.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows
- Windows Phone
- iOS
- Mac OS
- Android

## <a name="sync-a-device"></a>Cihaz eşitleme

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin. 
3. **Intune**'da **Cihazlar** > **Tüm cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinde bir cihaz seçin, **Daha Fazla**’yı ve ardından **Eşitle**'yi seçin.
5. Onaylamak için **Evet**'i seçin.

Eşitleme eyleminin durumunu görmek için **Cihaz** > **Cihaz eylemleri**’ni seçin.

Standart Intune İlkesi iade frekansları içinde bulabilirsiniz [yenileme döngüsü süreleri](device-profiles.md).

## <a name="retryable-error-codes"></a>Yeniden denenebilir hata kodları

Bir yönetici **Eşitle** cihaz eylemini çalıştırdığında, başarısız olan ancak yeniden denenebilir bir hata kodu veren iOS ve Android uygulamaları o cihazda yine kullanılabilir. Ancak yeniden denenemez bir hata kodu vermiş uygulamalar, cihaz için kullanılabilir hale gelmeden önce yedi gün beklemek zorundadır.


| Hata kodu  | Önerilen açıklama | Yeniden denenebilir |
|---|---|---|
| 2016330898 | Bilinmeyen bir hata oluştu. | Hayır |
| 2016330897 | Intune bağlantınız zaman aşımına uğradı. Bağlantınızı sıfırlayın. | Evet |
| 2016330896 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın. | Evet |
| 2016330895 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın. | Evet |
| 2016330894 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın. | Evet |
| 2016330893 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın. | Evet|
| 2016330892 | Uluslararası dolaşım devre dışı bırakıldı. | Hayır|
| 2016330891 | Telefon görüşmesi yapılırken bu cihaz için hücresel veri bağlantısına erişilemez. Görüşmenin sonlanmasını bekleyin. | Evet|
| 2016330890 | Bu cihaz için hücresel ağ. Bu cihazlar şu anda kullanılamıyor. | Hayır|
| 2016330889 | Güvenli bağlantı başarısız oldu. Bağlantınızı sıfırlayın. | Evet|
| 2016330888 | Sunucu güven değerlendirmesi başarısız oldu. | Hayır|

## <a name="next-steps"></a>Sonraki adımlar

Cihazın [ayrıntılarını denetleyebilirsiniz](device-inventory.md).
 
