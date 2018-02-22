---
title: "Windows Holographic’i Windows Holographic for Business’a yükseltme"
titleSuffix: Azure portal
description: "Windows Holographic çalıştıran cihazları nasıl Windows Holographic for Business’a yükselteceğinizi öğrenin"
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c467d2d4e02785bfac48afe2b39c50300eb4be40
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Windows Holographic çalıştıran cihazları Windows Holographic for Business’a yükseltme


Microsoft Intune ile Windows Holographic çalıştıran cihazları yönetmek için cihazları Windows Holographic’ten Windows Holographic for Business’a yükseltmek üzere bir Sürüm Yükseltme profili oluşturmanız gerekir. Microsoft HoloLens için ise yükseltme için gereken lisansı almak üzere Commercial Suite satın alabilirsiniz. Daha fazla bilgi için bkz. [Windows Holographic for Business özelliklerini etkinleştirme](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise).

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Sürüm Yükseltme cihaz yapılandırma profili ayarlamak için

1. [Azure portalında](https://portal.azure.com) yönetici hesabınızla oturum açın.


2.  **Cihaz yapılandırması**, **Profiller** ve ardından **+ Profil oluştur**’a tıklayın.

    ![Profil oluşturma](media/Holographic-create-profile.png)

3.  **Profil oluştur** dikey penceresinde profil için bir ad girin, platform için **Windows 10 ve üzeri**’ni seçin ve profil türü için **Sürüm yükseltme**’yi seçin. **Ayarları Yapılandırma**’ya tıklayın.

5. **Sürüm Yükseltme** dikey penceresindeki **Yükseltilecek sürüm** için **Windows 10 Holographic for Business**’ı seçin. **Lisans Dosyası**’nda size sağlanan XML lisans dosyasına göz atın ve bunu seçin.

    ![XML dosya adı girin](media/Holographic-edition-upgrade.png)
 
5.  **Tamam**’a tıklayın ve daha sonra profili oluşturmak için **Oluştur**’a tıklayın.


## <a name="deploy-the-edition-upgrade-policy"></a>Sürüm Yükseltme ilkesini dağıtın

Bundan sonra Sürüm Yükseltme profilini seçili gruplara veya cihazlara atayacaksınız.

1. Önceki adımlarda oluşturduğunuz profilde **Atamalar**’a tıklayın.

2. **Atamalar** dikey penceresinde, ilkeye dahil etmek veya ilkeden dışlamak istediğiniz kullanıcı gruplarını ve cihazları seçin.

![Grupları dahil edin ve dışlayın](media/Holographic-groups.PNG)

Bu kullanıcı veya grupları Intune’a kaydedildiğinde, Sürüm Yükseltme profili uygulanır. 

## <a name="next-steps"></a>Sonraki adımlar

Gruplar hakkında daha fazla bilgi için bkz. [Gruplar ile çalışmaya başlama](get-started-groups.md).


