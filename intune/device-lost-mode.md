---
title: "Microsoft Intune - Azure ile iOS kayıp modunu etkinleştirme | Microsoft Docs"
description: "Microsoft Intune kullanarak kayıp veya çalınan bir iOS cihazın kilit ekranında görüntülenen iletisini özelleştirmek için Kayıp modunu açın veya başlatın. Ve Kayıp modu eylemini kullanılırken güvenlik ve gizlilik bilgileri hakkındaki ayrıntıları alın."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47d6314dfaed546e5b4cff7f93a5540ba512bde9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Intune ile iOS cihazlarda kayıp modunu etkinleştirme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Kayıp modu** cihaz eylemi, kayıp veya çalınan iOS cihazlarında kayıp modunu etkinleştirmenize yardımcı olur. Bu mod, cihazın kilit ekranında görüntülenecek iletiyi ve telefon numarasını girmenize olanak tanır. Kayıp modu kullanmak için cihazın denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

## <a name="supported-platforms"></a>Desteklenen platformlar

- iOS 9.3 ve üzeri

Bu özellik aşağıdakilerde **desteklenmez**: 
- Windows
- Windows Phone
- Mac OS
- Android

## <a name="enable-lost-mode"></a>Kayıp modunu etkinleştirme

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm Cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir iOS cihazını seçin, **...Daha Fazla**’yı ve sonra **Kayıp modu** uzak eylemini seçin.
5. **Kayıp modu**’nda, bu özelliği etkinleştirin. Ardından, görüntülenecek iletiyi ve ilgili kişi telefon numarasını girin.
6. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

Kayıp modunu etkinleştirdiğinizde cihazın tüm kullanımı engellenir. Siz kayıp modunu devre dışı bırakmadıkça son kullanıcı cihaza erişemez. Kayıp modu etkin durumdayken, cihazı bulmak için [Cihazı bul](device-locate.md) eylemini kullanın.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Intune'a gönderilir ve Azure portalında görüntülenir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kilit ekranında görüntülenecek iletide, kaybolan cihazın iade edilmesi için belirli ayrıntıları eklediğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar

Kayıp modunu etkinleştirme durumunu görmek için **Cihazlar**’ı açın ve **Cihaz eylemleri**’ni seçin.