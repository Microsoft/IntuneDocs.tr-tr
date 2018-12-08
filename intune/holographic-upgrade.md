---
title: Windows Holographic’i Windows Holographic for Business’a yükseltme
titleSuffix: Microsoft Intune
description: Windows Holographic çalıştıran cihazları nasıl Windows Holographic for Business’a yükselteceğinizi öğrenin
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: da506156a7345b447ecc8e34a8d3ccdcc8e1a732
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53031611"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Windows Holographic çalıştıran cihazları Windows Holographic for Business’a yükseltme


Microsoft Intune ile Windows Holographic çalıştıran cihazları yönetmek için cihazları Windows Holographic’ten Windows Holographic for Business’a yükseltmeniz gerekir. Yükseltmeyi yapmak için bir Sürüm Yükseltme profili oluşturabilirsiniz. Microsoft HoloLens için ise yükseltme için gereken lisansı almak üzere Commercial Suite satın alabilirsiniz. Daha fazla bilgi için bkz. [Windows Holographic for Business özelliklerini etkinleştirme](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Sürüm Yükseltme cihaz yapılandırma profili ayarlamak için

1. [Azure portalında](https://portal.azure.com) yönetici hesabınızla oturum açın.


2.  **Cihaz yapılandırması**, **Profiller** ve ardından **+ Profil oluştur**’a tıklayın.

    ![Profil Oluştur](media/Holographic-create-profile.png)

3.  **Profil oluştur** bölmesinde profil için bir ad girin, platform için **Windows 10 ve üzeri**’ni seçin ve profil türü için **Sürüm yükseltme**’yi seçin. **Ayarları Yapılandırma**’ya tıklayın.

5. **Sürüm Yükseltme** bölmesinde **Yükseltilecek sürüm** için **Windows 10 Holographic for Business**’ı seçin. **Lisans Dosyası**’nda size sağlanan XML lisans dosyasına göz atın ve bunu seçin.

    ![XML dosya adı girin](media/Holographic-edition-upgrade.png)
 
5.  **Tamam**’a tıklayın ve daha sonra profili oluşturmak için **Oluştur**’a tıklayın.


## <a name="deploy-the-edition-upgrade-policy"></a>Sürüm Yükseltme ilkesini dağıtın

Bundan sonra Sürüm Yükseltme profilini seçili gruplara veya cihazlara atayacaksınız.

1. Önceki adımlarda oluşturduğunuz profilde **Atamalar**’a tıklayın.

2. **Atamalar** bölmesinde, ilkeye dahil etmek veya ilkeden dışlamak istediğiniz kullanıcı gruplarını ve cihazları seçin.

![Grupları dahil edin ve dışlayın](media/Holographic-groups.PNG)

Bu kullanıcı veya grupları Intune’a kaydedildiğinde, Sürüm Yükseltme profili uygulanır. 

## <a name="next-steps"></a>Sonraki adımlar

Gruplar hakkında daha fazla bilgi için bkz. [Gruplar ile çalışmaya başlama](get-started-groups.md).


