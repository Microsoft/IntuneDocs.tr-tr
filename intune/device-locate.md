---
title: "Microsoft Intune - Azure ile kayıp iOS cihazlarını bulma | Microsoft Docs"
description: "Microsoft Intune'da Cihazı Bul özelliğini kullanarak kayıp veya çalınan iOS cihazlarını bulun veya yerini tespit edin; Cihazı Bul eylemini kullanırken güvenlik ve gizlilik bilgileri hakkında ayrıntılı bilgi edinin."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Kaybolan veya çalınan iOS cihazlarının yerini Intune ile bulma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kayıp veya çalınan bir iOS cihazının konumunu bir haritada görüntülemek için **Cihazı Bul** eylemini kullanın. Cihazın aygıt kayıt programı (DEP) aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir. Bu eylemi kullanmadan önce cihazın [kayıp modunda](device-lost-mode.md) olduğundan emin olun.

## <a name="supported-platforms"></a>Desteklenen platformlar

- iOS 9.3 ve üzeri

Bu özellik aşağıdaki sistemlerde **desteklenmez**: 
- Windows
- Windows Phone
- Mac OS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Kaybolan veya çalınan bir cihazın yerini bulma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm Cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir iOS cihazını seçin, **...Daha Fazla**’yı ve sonra **Cihazı bul** uzak eylemini seçin.
5. Cihaz bulunduktan sonra, konumu **Cihazı bul** kısmında görüntülenir.
    ![Azure'da Intune kullanarak cihaz bulma](./media/locate-device.png)

>[!NOTE]
>Gizlilik nedeniyle haritayı belirli bir oranda yakınlaştırabilirsiniz.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Intune'a gönderilir ve Azure portalında görüntülenir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kayıp modunu yapılandırdığınızda, kilit ekranında görüntülenen bir iletiyi özelleştirebilirsiniz. Bu iletiye, cihazı bulan kişiye yardımcı olmak üzere, kayıp cihazı iade etmesi için belirli ayrıntıları eklediğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar

Cihazı Bul etkinleştirme durumunu görmek için **Cihazlar**’ı açın ve **Cihaz eylemleri**’ni seçin.
