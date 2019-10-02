---
title: Microsoft Intune - Azure ile iOS kayıp modunu etkinleştirme | Microsoft Docs
description: Microsoft Intune kullanarak kayıp veya çalınan bir iOS cihazının kilit ekranında gösterilen iletiyi özelleştirmek için kayıp modunu açın veya başlatın. Kayıp modu eylemini kullanırken güvenlik ve gizlilik bilgileri hakkındaki ayrıntıları alın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ac83160e6604b7a679e03bb244e1dd5081a5fc5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732649"
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>Intune ile iOS cihazlarda kayıp modunu etkinleştirme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

**Kayıp modu** cihaz eylemi, kayıp veya çalınan iOS cihazlarında kayıp modunu etkinleştirmenize yardımcı olur. Bu mod, cihazın kilit ekranında gösterilecek iletiyi ve telefon numarasını girmenize olanak tanır. Kayıp modu kullanmak için cihazın denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

## <a name="supported-platforms"></a>Desteklenen platformlar

- iOS 9.3 ve üzeri

Bu özellik aşağıdakilerde desteklenmez: 
- Windows
- Windows Phone
- Mac OS
- Android

## <a name="enable-lost-mode"></a>Kayıp modunu etkinleştirme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Cihazlar**’ı ve ardından **Tüm Cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir iOS cihazı seçin ve sonra da **...Diğer** öğesini seçin. Ardından **Kayıp modu** uzak eylemini seçin.
5. **Kayıp modu**’nda, bu özelliği etkinleştirin. Ardından, gösterilecek iletiyi ve ilgili kişi telefon numarasını girin.
6. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

Kayıp modunu etkinleştirdiğinizde cihazın tüm kullanımı engellenir. Siz kayıp modunu devre dışı bırakmadıkça son kullanıcı cihaza erişemez. Kayıp modu etkin durumdayken, cihazı bulmak için [Cihazı bul](device-locate.md) eylemini kullanın.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Intune'a gönderilir ve Azure portalında gösterilir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kilit ekranında gösterilecek iletide, kaybolan cihazın iade edilmesi için belirli ayrıntıları eklediğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar

Kayıp modunu etkinleştirme durumunu görmek için **Cihazlar**’ı açın ve **Cihaz eylemleri**’ni seçin.
