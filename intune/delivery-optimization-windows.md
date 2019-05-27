---
title: Microsoft Intune - Azure'da Windows 10 için dağıtım iyileştirme ayarlarını | Microsoft Docs
description: Intune ile yönettiğiniz Windows 10 cihazlarına teslim iyileştirme kullanımını yapılandırın. Intune, internet'ten güncelleştirmeleri yüklemek için bir cihaz yapılandırma profili oluşturma. Ayrıca var olan güncelleştirme halkaları teslim iyileştirme profiliyle nasıl değiştirileceğini bakın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: d927c886bbb3f82c18d5873a86fc427d00d96337
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66042629"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Microsoft Intune Delivery optimization ayarları

Intune ile cihazları, uygulamaları ve güncelleştirmeleri indirdiklerinde, bant genişliği tüketimini azaltmak için Windows 10 cihazlar için dağıtım iyileştirme ayarlarını kullanabilirsiniz. Teslim iyileştirme, cihaz yapılandırma profillerinin bir parçası olarak yapılandırılır.  

Bu makalede, bir cihaz yapılandırma profilinin bir parçası olarak teslim iyileştirme ayarlarını yapılandırmak açıklar. Bir profil oluşturduktan sonra daha sonra atayın veya bu profil Windows 10 cihazlarınıza dağıtın. 

Intune'un desteklediği delivery optimization ayarları listesi için bkz. [Delivery optimization ayarları ıntune](delivery-optimization-settings.md).  

Windows 10 teslim iyileştirme hakkında bilgi edinmek için bkz. [teslim iyileştirme güncelleştirmeleri](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) Windows belgelerinde.  


> [!NOTE]
> **Yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları** değiştirilir **teslim iyileştirme** ayarları. Kullanmak için var olan güncelleştirme halkaları değiştirilebilir **teslim iyileştirme** ayarları. [Var olan güncelleştirme halkaları için teslim iyileştirme taşıma](#move-existing-update-rings-to-delivery-optimization) (Bu makaledeki) 
## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin > **Intune**’u filtreleyin > **Intune**’u seçin.

2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.

3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Platformu seçin:  

        - **Windows 10 ve üzeri**

    - **Profil türü**: Seçin **teslim iyileştirme**.
    - **Ayarları**: Güncelleştirmeleri ve uygulamaları indirmek için istediğiniz tanımlayan ayarlarını yapılandırın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [Delivery optimization ayarları ıntune](delivery-optimization-settings.md).

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin.

Profil oluşturulur ve listede görüntülenir. Ardından, [profili atama](device-profile-assign.md) ardından [atamanın durumunu izlemenize](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Var olan güncelleştirme halkaları için teslim iyileştirme Taşı

**Teslim iyileştirme** ayarlarını değiştir **yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları**. Mevcut uygulamanızı güncelleştirme halkaları kullanmak için kolayca değiştirilebilir **teslim iyileştirme** ayarları. Teslim iyileştirme profili oluşturduğunuzda, aynı ayarları korumak için aynı kullanın *teslim iyileştirme indirme modu* ve ardından aynı ayarları zaten kullanın. Ancak, teslim iyileştirme profilini de yönetebilirsiniz toplama ayarları çeşitli avantajlarından yararlanmak için teslim iyileştirme ayarlarını yapılandırmak seçebilirsiniz.

1. Teslim iyileştirme yapılandırma profili oluşturun:

    1. Intune'da seçin **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**.
    2. Aşağıdaki özellikleri girin:

        - **Ad**: Yeni profil için açıklayıcı bir ad girin.
        - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
        - **Platform**: Seçin **Windows 10 ve üzeri**.
        - **Profil türü**: Seçin **teslim iyileştirme**.
        - **Ayarları**: İçin **teslim iyileştirme indirme modu**, cihazlarınıza uygulama ayarlarını değiştirmek istediğiniz sürece varolan yazılım güncelleştirme kademesi tarafından kullanılan aynı modunu seçin. Seçenekleriniz şunlardır:
            - **Yapılandırılmadı**
            - **Yalnızca HTTP, eşleme yok**
            - **Aynı NAT arkasında eşleme ile karışık HTTP**
            - **Özel bir grup üzerinde eşleme ile karışık HTTP**
            - **Internet eşlemesi ile karışık HTTP**
            - **Eşlemesiz basit indirme modu**
            - **Atlama modu**
    3. Yönetmek istediğiniz ek ayarları yapılandırın.
1. Bu yeni profili aynı cihazları ve kullanıcıları, mevcut yazılım güncelleştirme kademesi atayın. [Profil atama](device-profile-assign.md) adımları listelenir.

3. Mevcut yazılım halka yapılandırmasını Kaldır:
    1. Intune'da Git **yazılım güncelleştirmelerini** > Windows 10 güncelleştirme halkaları.
    2. Listede, güncelleştirme kademesi seçin.
    3. Ayarları'nda **teslim iyileştirme indirme modu** için **yapılandırılmadı**.
    4. **Tamam** > **Kaydet** yaptığınız değişiklikleri.

## <a name="next-steps"></a>Sonraki adımlar

[Profil atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md) durumu.  
Görünüm [delivery optimization ayarları](delivery-optimization-settings.md) ıntune.
