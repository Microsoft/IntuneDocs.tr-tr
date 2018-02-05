---
title: "Cihazları Intune ile eşitleme"
titlesuffix: Azure portal
description: "En son ilkeleri ve eylemleri almak için cihazları Intune ile eşitlemeyi öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f784143535188c6bee2082c5717b752f08c5490
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>En son ilkeleri ve eylemleri almak için cihazları Intune ile eşitleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihazı **Eşitle** eylemi, seçili cihazı Intune’a hemen giriş yapmaya zorlar. Bir cihaz giriş yaptığında, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır.  Bu eylem, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanız ve ilkelerin sorunlarını gidermenize yardımcı olur.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows
- Windows Phone
- iOS
- Mac OS
- Android

## <a name="how-to-sync-a-device"></a>Bir cihazı eşitleme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **Eşitle** uzak işlemini seçin.
7. Eylemi doğrulamak için **Evet** 'i seçin.


## <a name="retriable-error-codes"></a>Yeniden denenebilir hata kodları

Bir yönetici **Eşitle** cihaz eylemini çalıştırdığında, başarısız olan ancak yeniden denenebilir bir hata kodu veren iOS ve Android uygulamaları o cihaz için kullanılabilir. Ancak yeniden denenemez bir hata kodu vermiş uygulamalar, cihaz için kullanılabilir hale gelmeden önce yedi gün beklemek zorundadır.


| Hata Kodu  | Önerilen Açıklama                                                                                                                  | Yeniden denenebilir |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Bilinmeyen bir hata oluştu.                                                                                                             | Hayır        |
| 2016330897 | Intune bağlantınız zaman aşımına uğradı. Bağlantınızı sıfırlayın                                                                             | Evet       |
| 2016330896 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın.                                                                            | Evet       |
| 2016330895 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın.                                                                            | Evet       |
| 2016330894 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın.                                                                            | Evet       |
| 2016330893 | İnternet bağlantınız kesildi. Bağlantınızı sıfırlayın.                                                                            | Evet       |
| 2016330892 | Uluslararası dolaşım devre dışı bırakıldı.                                                                                                     | Hayır        |
| 2016330891 | Telefon görüşmesi yapılırken bu cihaz için hücresel veri bağlantısına erişilemez. Görüşmenin sonlanmasını bekleyin. | Evet       |
| 2016330890 | Bu cihaz için hücresel ağ. Bu cihazlar şu anda kullanılamıyor.                                                   | Hayır        |
| 2016330889 | Güvenli bağlantı başarısız oldu. Bağlantınızı sıfırlayın.                                                                                   | Evet       |
| 2016330888 | Sunucu güven değerlendirmesi başarısız oldu.                                                                                                | Hayır        |

## <a name="next-steps"></a>Sonraki adımlar

Eşitleme eyleminin durumunu görmek için **Cihaz Eylemleri**’ni seçin. 
