---
title: "Uzaktan kilitleme ve geçiş kodu sıfırlama | Microsoft Intune"
description: "Intune uzaktan kilitleme ve geçiş kodu sıfırlama özellikleri sunar."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: aae739b5ea8640449f180535a6d8f1550c7ae228
ms.openlocfilehash: 8dc7f1c7eb32828854b4e2309c915f4fd0cba9a2

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Uzak kilitleme ve parola sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma
Microsoft Intune hem uzaktan kilitleme hem de geçiş kodu sıfırlama özelliklerini sağlar.

## <a name="lock-a-device-remotely"></a>Cihazı uzaktan kilitleme
Bir kullanıcı cihazını kaybederse, cihazı uzaktan kilitleyebilirsiniz. Aşağıdaki tabloda, farklı mobil platformlarda uzaktan kilitleme işleminin nasıl çalıştığı listelenmiştir.

|Platform|Uzaktan kilitleme|
|------------|---------------|
|Mac OS|Desteklenmez|
|iOS|Desteklenir|
|Android|Desteklenir|
|Windows 10 ve Windows 10 Mobile|Desteklenir|
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
|Windows 10 Mobile|Desteklenir|
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



<!--HONumber=Nov16_HO4-->


