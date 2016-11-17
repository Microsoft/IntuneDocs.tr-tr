---
title: "Uzaktan kilitleme ve geçiş kodu sıfırlama | Microsoft Intune"
description: "Intune uzaktan kilitleme ve geçiş kodu sıfırlama özellikleri sunar."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: b32ef59aa33205e5687d951d50dfd605a6b071f2

---
# Uzak kilitleme ve parola sıfırlama özellikleriyle cihazlarınızın korunmasına yardımcı olma
Microsoft Intune hem uzaktan kilitleme hem de geçiş kodu sıfırlama özelliklerini sağlar.

## Cihazı uzaktan kilitleme
Bir kullanıcı cihazını kaybederse, cihazı uzaktan kilitleyebilirsiniz. Aşağıdaki tabloda, farklı mobil platformlarda uzaktan kilitleme işleminin nasıl çalıştığı listelenmiştir.

|Platform|Uzaktan kilitleme|
|------------|---------------|
|iOS|Desteklenir|
|Android|Desteklenir|
|Windows 10 ve Windows 10 Mobile|Desteklenir|
|Windows Phone 8 ve Windows Phone 8.1|Desteklenir|
|Windows RT 8.1 ve Windows RT|Cihazın geçerli kullanıcısı, cihazı kaydeden kullanıcı ile aynıysa desteklenir.|
|Windows 8.1|Cihazın geçerli kullanıcısı, cihazı kaydeden kullanıcı ile aynıysa desteklenir.|

Intune yazılım istemcisine kaydolmuş Windows bilgisayarları için uzaktan kilitleme desteklenmez.

### Bir mobil cihazı Intune konsolu üzerinden uzaktan kilitleme

1.  [Intune yönetici konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Mobil Cihazlar** öğelerini seçin.

2.  Intune’a kayıtlı cihazlar için **Doğrudan Yönetilen Tüm Cihazlar**’ı veya **Exchange ActiveSync Tarafından Yönetilen Tüm Cihazlar**’ı seçin.

    > [!TIP]
    > Kullanıcıya göre ilerleyerek de bir cihaza gidebilirsiniz. **Tüm Kullanıcılar**’ı seçin. Kullanıcı özellikleri sayfasından **Cihazlar**’ı seçin ve ardından kilitlemek istediğiniz mobil cihazın adını seçin.

3.  Listede, kilitlemek istediğiniz cihazı veya cihazları seçin. Görev çubuğunda **Uzak Görevler**’i ve ardından **Uzaktan Kilitleme**’yi seçin.

## Cihazdaki geçiş kodunu sıfırlama
Bir kullanıcı geçiş kodunu unutursa, cihazdan geçiş kodunu kaldırarak veya cihazda yeni bir geçici geçiş kodu zorlayarak yardımcı olabilirsiniz. Aşağıdaki tabloda, farklı mobil platformlarda parola sıfırlama işleminin nasıl çalıştığı listelenmiştir.

|Platform|Geçiş kodu sıfırlama|
|------------|------------------|
|iOS|Bir cihazdan parolayı temizlemek için desteklenir. Yeni bir geçici parola oluşturmaz.|
|Android|Desteklenen. Geçici bir geçiş kodu oluşturur.|
|Windows 10 Mobile|Desteklenir|
|Windows Phone 8 ve Windows Phone 8.1|Desteklenir|
|Windows RT 8.1 ve Windows RT|Desteklenmez|
|Windows 8.1|Desteklenmez|

Intune yazılım istemcisine kaydolmuş Windows bilgisayarları için geçiş kodu sıfırlaması desteklenmez.

### Geçiş kodu sıfırlama

1.  [Intune yönetici konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Mobil Cihazlar** öğelerini seçin.

2.  Intune’a kayıtlı cihazlar için **Doğrudan Yönetilen Tüm Cihazlar**’ı veya **Exchange ActiveSync Tarafından Yönetilen Tüm Cihazlar**’ı seçin.

    > [!TIP]
    > Kullanıcıya göre ilerleyerek de bir cihaza gidebilirsiniz. **Tüm Kullanıcılar**’a tıklayın. Kullanıcının özellikler sayfasında **Cihazlar**’a tıklayın ve ardından silmek istediğiniz mobil cihazın adına tıklayın.

3.  Listede, kilitlemek istediğiniz cihazı veya cihazları seçin. Görev çubuğunda **Uzak Görevler**’i ve ardından **Geçiş Kodu Sıfırlama**’yı seçin.


### Ayrıca bkz.
[Cihazları kullanımdan kaldırma](retire-devices-from-microsoft-intune-management.md) ve [Cihaz Veri Yönetimi için Windows Seçmeli Silme](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Oct16_HO4-->


