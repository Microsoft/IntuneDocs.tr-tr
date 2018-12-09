---
title: Windows Holographic for Business için yükseltme
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
ms.openlocfilehash: 4839206db5e34a039c9e99dd74f5ab1bad328418
ms.sourcegitcommit: 5058dbfb0e224207dd4e7ca49712c6ad3434c83c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2018
ms.locfileid: "53112349"
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


