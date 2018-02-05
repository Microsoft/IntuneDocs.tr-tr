---
title: "Kayıp iOS cihazlarını Intune ile bulma"
titlesuffix: Azure portal
description: "Kaybolan veya çalınan iOS cihazlarının yerini Intune ile bulmayı öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90b1321c0df49f446bfdeccbacdfd5642396dacd
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Kaybolan veya çalınan iOS cihazlarının yerini Intune ile bulma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazı Bul** cihaz eylemi, kayıp veya çalınan bir iOS cihazının konumunu bir haritada görüntüler. Cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir. Bu eylemi kullanabilmek için önce cihazın [kayıp moduna](/intune-azure/manage-devices/lost-mode.md) geçirilmiş olması gerekir.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzeri (Kayıp modunda), denetimli ve şirkete ait için desteklenir
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Kaybolan veya çalınan bir cihazın yerini bulma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir iOS cihazını seçin, sonra **Cihazı Bul** uzak eylemini seçin.
6. Cihaz bulunduktan sonra konumu **Cihazı bul** dikey penceresinde görüntülenir.
    ![Cihazı bul dikey penceresi](./media/locate-device.png)

>[!NOTE]
>Gizlilik nedeniyle haritayı belirli bir oranda yakınlaştırabilirsiniz.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Intune'a gönderilir ve Azure portalında görüntülenir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kayıp modunu yapılandırdığınızda, kilitleme ekranında girdiğiniz iletinin, bulan kişinin cihazı iade etmesine yardımcı olan bilgiler içermesini öneririz.


## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.