---
title: Microsoft Intune-Azure 'da Windows 10 için teslim iyileştirme ayarları | Microsoft Docs
description: Intune ile yönettiğiniz Windows 10 cihazlarının teslim iyileştirmesi kullanma şeklini yapılandırın. Intune 'da, güncelleştirmeleri Internet 'ten yüklemek için bir cihaz yapılandırma profili oluşturun. Ayrıca bkz. var olan güncelleştirme halkalarını teslim iyileştirme profiliyle değiştirme.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 9fb4aab6b02c6ad6a5d2f18ca9d15beafc12d58a
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78369952"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Microsoft Intune teslim iyileştirme ayarları

Intune ile, bu cihazlar uygulamaları ve güncelleştirmeleri indirdiğinizde bant genişliği tüketimini azaltmak için Windows 10 cihazlarınız için teslim Iyileştirme ayarlarını kullanın. Cihaz yapılandırma profillerinizin bir parçası olarak teslim iyileştirmesini yapılandırın.  

Bu makalede, teslim iyileştirme ayarlarının cihaz yapılandırma profilinin bir parçası olarak nasıl yapılandırılacağı açıklanır. Bir profil oluşturduktan sonra, bu profili Windows 10 cihazlarınıza atar veya dağıtabilirsiniz. 

Intune 'un desteklediği teslim iyileştirme ayarlarının listesini görüntülemek için, bkz. [Intune Için teslim iyileştirme ayarları](../delivery-optimization-settings.md).  

Windows 10 ' da teslim Iyileştirmesi hakkında bilgi edinmek için Windows belgelerindeki [teslim iyileştirme güncelleştirmeleri](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) bölümüne bakın.  

## <a name="create-the-profile"></a>Profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üstünü**seçin.
    - **Profil türü**: **teslim iyileştirmesi**' nı seçin.

4. **Yapılandırma** > **Ayarlar** ' ı seçin ve güncelleştirmelerin ve uygulamaların nasıl indirilmek istediğinizi tanımlayın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [Intune Için teslim iyileştirme ayarları](../delivery-optimization-settings.md).

5. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin.

Profil oluşturulur ve listede gösterilir. Sonra, [profili atayın](device-profile-assign.md) ve ardından [durumunu izleyin](device-profile-monitor.md).

<!-- ## Move existing update rings to delivery optimization

**Delivery optimization** settings replace **Software updates – Windows 10 Update Rings**. Your existing update rings can be easily changed to use the **Delivery optimization** settings. To maintain the same settings when you create a delivery optimization profile, use the same *Delivery optimization download mode* and then set the same settings as you already use. However, you can choose to reconfigure delivery optimization settings to take advantage of the full range of addition settings that the Delivery Optimization profile can manage. 
-->

## <a name="remove-delivery-optimization-from-windows-10-update-rings"></a>Windows 10 güncelleştirme halkalarından teslim Iyileştirmeyi kaldır

Teslim Iyileştirme daha önce yazılım güncelleştirme halkalarının bir parçası olarak yapılandırılmıştır. Dağıtım Iyileştirme ayarları, Şubat 2019 ' den itibaren cihazlara yazılım güncelleştirme teslimini etkileyen ek ayarlar içeren bir teslim Iyileştirme cihaz yapılandırma profilinin bir parçası olarak yapılandırılır. Henüz yapmadıysanız, dağıtım iyileştirme ayarını güncelleştirme halkalarından *Yapılandırılmadı*olarak ayarlayarak kaldırın ve daha fazla kullanılabilir seçenek aralığını yönetmek Için bir teslim iyileştirme profili kullanın.

1. Teslim Iyileştirme cihaz yapılandırma profili oluşturma:

    1. Microsoft Endpoint Manager Yönetim Merkezi 'nde, **cihaz** > **yapılandırma profilleri** > **Profil oluştur**' u seçin.
    2. Aşağıdaki özellikleri girin:

        - **Ad**: Yeni profil için açıklayıcı bir ad girin.
        - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
        - **Platform**: **Windows 10 ve üstünü**seçin.
        - **Profil türü**: **teslim iyileştirmesi**' nı seçin.
        - **Ayarlar**: **teslim iyileştirme indirme modu**için, cihazlarınıza uyguladığınız ayarları değiştirmek istemediğiniz takdirde, var olan yazılım güncelleştirme halkası tarafından kullanılan modu seçin. Seçenekleriniz şunlardır:
            - **Yapılandırılmadı**
            - **Yalnızca HTTP, eşleme yok**
            - **Aynı NAT 'nin arkasında eşleme ile HTTP karıştırılmış**
            - **Özel bir Grup genelinde eşleme ile HTTP karıştırılmış**
            - **Internet eşlemesi ile HTTP karıştırılmış**
            - **Eşleme olmadan basit indirme modu**
            - **Atlama modu**
    3. Yönetmek isteyebileceğiniz diğer ayarları yapılandırın.

2. Bu yeni profili, var olan yazılım güncelleştirme halkası ile aynı cihazlara ve kullanıcılara atayın. [Profil atama](device-profile-assign.md) adımları listeler.

3. Mevcut yazılım halkasını yapılandırmayı geri al:
    1. Microsoft Endpoint Manager Yönetim Merkezi 'nde Windows 10 güncelleştirme halkaları > **yazılım güncelleştirmeleri** ' ne gidin.
    2. Listeden güncelleştirme halkasını seçin.
    3. Ayarlar ' da **teslim iyileştirme indirme modunu** **Yapılandırılmadı**olarak ayarlayın.
    4. Değişikliklerinizi >  **Tamam** ' a tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atayın](device-profile-assign.md) ve durumunu [izleyin](device-profile-monitor.md) .  
Intune için [teslim iyileştirme ayarlarını](../delivery-optimization-settings.md) görüntüleyin.
