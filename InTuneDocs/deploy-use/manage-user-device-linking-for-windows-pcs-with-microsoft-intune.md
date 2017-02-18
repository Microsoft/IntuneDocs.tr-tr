---
title: "Windows bilgisayarlar için kullanıcı-cihaz bağlamayı yönetme | Microsoft Docs"
description: "Bir kullanıcı Intune tarafından yönetilen bir Windows bilgisayara nasıl bağlanır?"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 10dd2caa9ce1b96424f55e373e904a778390eb15
ms.openlocfilehash: 3a20dc18a72518ba9e01552cd1283170972b4bbb


---

# <a name="manage-user-device-linking-for-windows-pcs"></a>Windows bilgisayarlar için kullanıcı-cihaz bağlamayı yönetme
Bu konudaki bilgiler, yalnızca Intune yazılım istemcisini kullanarak bilgisayar olarak yönettiğiniz Windows masaüstü cihazlar için geçerlidir. 

Bir kullanıcı için yazılım dağıtmadan önce kullanıcıyı bir bilgisayara bağlamanız gerekir. Bir kullanıcıyı birden çok bilgisayara bağlayabilirsiniz, ancak her bilgisayara yalnızca bir kullanıcı bağlanabilir. Kullanıcılar şirket portalını kullanarak Intune kaydını yaptıkları bilgisayarlara otomatik olarak bağlanır.

Bir kullanıcıyı bir bilgisayara bağlamak için:

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya bir kullanıcıya bağlamak istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2.  Kullanıcıya bağlamak istediğiniz bilgisayarı seçin ve ardından **Kullanıcı Bağla**'yı seçin.

    **Kullanıcı Bağla** iletişim kutusu mevcut kullanıcıların görünen adı, kullanıcı kimliği ve her kullanıcının bağlı olduğu bilgisayar sayısını içeren bir liste görüntüler. Bir kullanıcı seçili bilgisayara zaten bağlıysa kullanıcının adı ve kullanıcı kimliği **Geçerli kullanıcı**altında gösterilir. Bilgisayar hiçbir kullanıcıya bağlanmamışsa **Geçerli Kullanıcı** altında **Kullanıcı Yok**görüntülenir.

3.  Aşağıdakilerden birini yapın:

    -   Bilgisayarın bağlı olduğu bir kullanıcı varsa bilgisayarı bu kullanıcıya bağlı olarak bırakmak için **İptal**'i seçin.

    -   Geçerli kullanıcının (varsa) bağlantısını kaldırmak için **Bağlantıyı Kaldır** &gt; **Tamam**'ı seçin.

    -   Bilgisayarı yeni bir kullanıcıya bağlamak için **Tüm kullanıcılar** listesinde bir kullanıcı seçin. Kullanıcı verilerinin doğru olduğundan emin olun ve ardından **Tamam**'ı seçin.

> [!TIP]
> Son kullanıcıların bilgisayarlara bağlanma yeteneğini kısıtlamak istiyorsanız **Microsoft Intune Aracı Ayarları** ilkesinde **Kullanıcıların bilgisayarlara bağlanma yeteneğini kısıtla** seçeneğini etkinleştirin.

### <a name="see-also"></a>Ayrıca bkz.

[Intune yazılım istemcisi ile genel Windows bilgisayar yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Dec16_HO3-->


