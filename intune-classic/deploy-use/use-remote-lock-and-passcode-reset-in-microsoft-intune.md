---
title: "Uzaktan kilitleme ve geçiş kodu sıfırlama | Microsoft Docs"
description: "Intune uzaktan kilitleme ve geçiş kodu sıfırlama özellikleri sunar."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f0a477c9eb1ed0580314e79135e377809eaab197
ms.openlocfilehash: 9b0ae19b211373548061e2c2979620739a0bf0a0
ms.lasthandoff: 04/17/2017

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Uzak kilitleme ve parola sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune hem uzaktan kilitleme hem de geçiş kodu sıfırlama özelliklerini sağlar.

## <a name="lock-a-device-remotely"></a>Cihazı uzaktan kilitleme
Bir kullanıcı cihazını kaybederse, cihazı uzaktan kilitleyebilirsiniz. Uzaktan kilitlemeyi kullanmaya başlamadan önce cihazın zaten ayarlanmış bir PIN veya geçiş kodu olmalıdır.

Aşağıdaki tabloda, farklı mobil platformlarda uzaktan kilitleme işleminin nasıl çalıştığı listelenmiştir.

|Platform|Uzaktan kilitleme|
|------------|---------------|
|Mac OS|Desteklenmez|
|iOS|Desteklenir|
|Android|Desteklenir|
|Android for Work|Desteklenir|
|Windows 10 (mobil)|Desteklenir|
|Windows 10 (masaüstü)|Desteklenmez|
|Windows Phone 8 ve Windows Phone 8.1|Desteklenir|
|Windows RT 8.1 ve Windows RT|Cihazın geçerli kullanıcısı, cihazı kaydeden kullanıcı ile aynıysa desteklenir.|
|Windows 8.1|Cihazın geçerli kullanıcısı, cihazı kaydeden kullanıcı ile aynıysa desteklenir.|

Intune yazılım istemcisine kaydolmuş Windows bilgisayarları için uzaktan kilitleme desteklenmez.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Bir mobil cihazı Intune konsolu üzerinden uzaktan kilitleme

1.  [Intune yönetici konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Mobil Cihazlar** öğelerini seçin.

2.  Intune’a kayıtlı cihazlar için **Doğrudan Yönetilen Tüm Cihazlar**’ı veya **Exchange ActiveSync Tarafından Yönetilen Tüm Cihazlar**’ı seçin.

    > [!TIP]
    > Kullanıcıya göre ilerleyerek de bir cihaza gidebilirsiniz. **Tüm Kullanıcılar**’ı seçin. Kullanıcı özellikleri sayfasından **Cihazlar**’ı seçin ve ardından kilitlemek istediğiniz mobil cihazın adını seçin.

3.  Listede, kilitlemek istediğiniz cihazı veya cihazları seçin. Görev çubuğunda **Uzak Görevler**’i ve ardından **Uzaktan Kilitleme**’yi seçin.

## <a name="reset-the-passcode-on-a-device"></a>Cihazdaki geçiş kodunu sıfırlama
Bir kullanıcı geçiş kodunu unutursa, cihazdan geçiş kodunu kaldırarak veya cihazda yeni bir geçici geçiş kodu zorlayarak yardımcı olabilirsiniz. Aşağıdaki tabloda, farklı mobil platformlarda parola sıfırlama işleminin nasıl çalıştığı listelenmiştir.

|Platform|Geçiş kodu sıfırlama|
|------------|------------------|
|Mac OS|Desteklenmez|
|iOS|Bir cihazdan parolayı temizlemek için desteklenir. Yeni bir geçici parola oluşturmaz.|
|Android|Android 7.0'den önceki sürümlerde desteklenir. Geçici bir geçiş kodu oluşturur.|
|Android for Work|Desteklenmez|
|Windows 10 mobile|Azure AD’ye katılan Windows 10 Creator sürümü ve üzerini çalıştıran mobil cihazlarda desteklenir.|
|Windows Phone 8 ve Windows Phone 8.1|Desteklenir|
|Windows RT 8.1|Desteklenmez|
|Windows 8.1|Desteklenmez|
|Windows 10 masaüstü|Desteklenmez|

Intune yazılım istemcisine kaydolmuş Windows bilgisayarları için geçiş kodu sıfırlaması desteklenmez.

### <a name="reset-a-passcode"></a>Geçiş kodu sıfırlama

1.  [Intune yönetici konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Mobil Cihazlar** öğelerini seçin.

2.  Intune’a kayıtlı cihazlar için **Doğrudan Yönetilen Tüm Cihazlar**’ı veya **Exchange ActiveSync Tarafından Yönetilen Tüm Cihazlar**’ı seçin.

    > [!TIP]
    > Kullanıcıya göre ilerleyerek de bir cihaza gidebilirsiniz. **Tüm Kullanıcılar**’a tıklayın. Kullanıcının özellikler sayfasında **Cihazlar**’a tıklayın ve ardından silmek istediğiniz mobil cihazın adına tıklayın.

3.  Listede, kilitlemek istediğiniz cihazı veya cihazları seçin. Görev çubuğunda **Uzak Görevler**’i ve ardından **Geçiş Kodu Sıfırlama**’yı seçin.


### <a name="see-also"></a>Ayrıca bkz.
[Cihazları kullanımdan kaldırma](retire-devices-from-microsoft-intune-management.md) ve [Cihaz Veri Yönetimi için Windows Seçmeli Silme](http://technet.microsoft.com/library/dn486874.aspx)

