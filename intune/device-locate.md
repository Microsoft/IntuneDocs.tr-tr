---
title: "Kayıp iOS cihazlarını Intune ile bulma"
titleSuffix: Intune on Azure
description: "Kaybolan veya çalınan iOS cihazlarının yerini Intune ile bulmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 80aa0e5afd1f8862b181d455ff6b545e462f90c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Kaybolan veya çalınan iOS cihazlarının yerini Intune ile bulma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazı Bul** cihaz eylemi, kayıp veya çalınan bir iOS cihazının konumunu bir haritada görüntüler. Cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir. Bu eylemi kullanabilmek için önce cihazın [kayıp moduna](/intune-azure/manage-devices/lost-mode.md) geçirilmiş olması gerekir.

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
