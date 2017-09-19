---
title: "Intune ile iOS kayıp modunu etkinleştirme"
titlesuffix: Azure portal
description: "Intune'u kayıp veya çalınan iOS cihazlarında kayıp modunu etkinleştirmek için kullanmayı öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f16bd212c7a23d847da0929933fbd4b497099d0
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>iOS cihazlarında kayıp modunu etkinleştirme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Kayıp modu** cihaz eylemi, kayıp veya çalınan iOS cihazlarında kayıp modunu etkinleştirmenize yardımcı olur. Bu mod, cihazın kilit ekranında görüntülenecek mesajı ve telefon numarasını belirtmenize olanak tanır.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzeri, denetimli ve şirkete ait için desteklenir
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="how-to-activate-lost-mode"></a>Kayıp modu etkinleştirme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir iOS cihazını seçin, sonra **Kayıp modu** uzak eylemini seçin.
6. **Kayıp modu** dikey penceresinde, kayıp modu etkinleştirin. Ardından, görüntülenecek iletiyi ve isteğe bağlı olarak, bir irtibat telefonu numarası girin.
7. **Tamam**’a tıklayın.

Kayıp modunu etkinleştirdiğinizde cihazın tüm kullanımını engellemiş olursunuz. Siz kayıp modunu devre dışı bırakmadıkça son kullanıcı cihaza erişemez. Kayıp modu etkin durumdayken **Cihazı bul** eylemini kullanarak cihazın nerede olduğunu bulabilirsiniz.
Kayıp modu kullanmak için cihazın denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Kayıp modu ve cihazı bul eylemleri için güvenlik ve gizlilik bilgileri
- Siz bu eylemi açana kadar Intune'a hiçbir cihaz konum bilgisi gönderilmez.
- Cihazı bul eylemini kullandığınızda, cihazın enlem ve boylam koordinatları Intune'a gönderilir ve Azure portalında görüntülenir.
- Veriler 24 saat depolandıktan sonra kaldırılır. Konum verilerini el ile kaldıramazsınız.
- Konum verileri hem depolanma hem de aktarım sırasında şifrelenir.
- Kilit ekranında girdiğiniz iletinin, bulan kişinin cihazı iade etmesine yardımcı olan bilgiler içermesini öneririz.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.

