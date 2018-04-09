---
title: Microsoft Intune - Azure ile cihazları eşitleme | Microsoft Docs
description: En son ilkeleri ve eylemleri almak için Microsoft Intune ile kayıtlı veya yönetilen cihazları eşitleyin. Azure portalını kullanarak eşitleme adımlarını içerir ve yeniden denenebilecek hata kodlarını listeler.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7af71a2d5c3ad871e69424cf6afbf7c364bb888d
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Intune ile en son ilkeleri ve eylemleri almak için cihazları eşitleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihazı **Eşitle** eylemi, seçili cihazı Intune’a hemen giriş yapmaya zorlar. Bir cihaz giriş yaptığında, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır. Bu özellik, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanıza ve ilkelerin sorunlarını gidermenize yardımcı olur.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows
- Windows Phone
- iOS
- Mac OS
- Android

## <a name="sync-a-device"></a>Cihaz eşitleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin. 
3. **Intune**'da **Cihazlar** > **Tüm cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinde bir cihaz seçin, **Daha Fazla**’yı ve ardından **Eşitle**'yi seçin.
5. Onaylamak için **Evet**'i seçin.


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

- Eşitleme eyleminin durumunu görmek için **Cihaz eylemleri**’ni seçin. 
