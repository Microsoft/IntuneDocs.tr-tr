---
title: Microsoft Intune - Azure ile kayıp iOS cihazlarını bulma | Microsoft Docs
description: Microsoft Intune'un cihazı bulma özelliğini kullanarak kayıp veya çalınmış iOS cihazlarını bulabilirsiniz. Cihazı bulma eylemini kullanılırken güvenlik ve gizlilik bilgileri hakkındaki ayrıntıları alabilirsiniz.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dc5d9f47a8d950c6c5de9f362bd618d1724055f4
ms.sourcegitcommit: 3e3e2af98dd92f7ba710f393841cfdb3dbcc4867
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912160"
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Kaybolan veya çalınan iOS cihazlarının yerini Intune ile bulma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Kayıp veya çalınan bir iOS cihazının konumunu bir haritada görüntülemek için **Cihazı bul** eylemini kullanın. Cihazın denetimli modda olması gerekir. Bu eylemi kullanmadan önce cihazın [kayıp modunda](device-lost-mode.md) olduğundan emin olun.

## <a name="supported-platforms"></a>Desteklenen platformlar

- iOS 9.3 ve üzeri

Bu özellik aşağıdaki sistemlerde desteklenmez: 
- Windows
- Windows Phone
- Mac OS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Kaybolan veya çalınan bir cihazın yerini bulma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir iOS cihazı seçin ve sonra da **...Diğer** öğesini seçin. Ardından **Cihazı bul** uzak eylemini seçin.
5. Cihaz bulunduktan sonra, konumu **Cihazı bul** kısmında gösterilir.
    ![Azure'da Intune kullanarak Cihazı bulma eyleminin ekran görüntüsü](./media/locate-device.png)

>[!NOTE]
>Gizlilik nedeniyle haritayı en fazla 300 metre yarıçaplık bir mesafeye kadar yakınlaştırabilirsiniz.

## <a name="activate-lost-mode-sound-alert-on-an-ios-device"></a>iOS cihazında kayıp modu ses uyarısını etkinleştirme

Birisi iOS 9.3 veya üzeri bir cihazını kaybettiyse, kullanıcının bulabilmesi için cihazda bir uyarı sesi çalınmasını uzaktan tetikleyebilirsiniz. Cihazın [kayıp modunda](device-lost-mode.md) olması gerekir.

[Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihazlar** > **Tüm cihazlar** > bir iOS cihazı seçin > **Genel Bakış** > **Daha Fazla** > **Kayıp modu sesi çal (yalnızca denetimli)** öğesini seçin.

Kullanıcı cihazda sesi devre dışı bırakana veya cihaz kayıp modundan çıkarılana kadar ses çalmaya devam eder.


## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Graph API kullanılarak alınabilir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kayıp modunu yapılandırdığınızda, kilit ekranında gösterilen iletiyi özelleştirebilirsiniz. Bu iletiye, cihazı bulan kişiye yardımcı olmak üzere, kayıp cihazı iade etmesi için belirli ayrıntıları eklediğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar

Cihazı bulma eylemini etkinleştirme durumunu görmek için **Cihazlar**’ı açın ve **Cihaz eylemleri**’ni seçin.
