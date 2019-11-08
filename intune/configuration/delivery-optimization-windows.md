---
title: Microsoft Intune-Azure 'da Windows 10 için teslim iyileştirme ayarları | Microsoft Docs
description: Intune ile yönettiğiniz Windows 10 cihazlarının teslim iyileştirmesi kullanma şeklini yapılandırın. Intune 'da, güncelleştirmeleri Internet 'ten yüklemek için bir cihaz yapılandırma profili oluşturun. Ayrıca bkz. var olan güncelleştirme halkalarını teslim iyileştirme profiliyle değiştirme.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 908319c588fe2a1bf55a376d3f02a03db780a3ad
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755407"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Microsoft Intune teslim iyileştirme ayarları

Intune ile, bu cihazlar uygulamaları ve güncelleştirmeleri indirdiğinizde bant genişliği tüketimini azaltmak için Windows 10 cihazlarınız için teslim iyileştirme ayarlarını kullanabilirsiniz. Teslim iyileştirme, cihaz yapılandırma profillerinizin bir parçası olarak yapılandırılır.  

Bu makalede, teslim iyileştirme ayarlarının cihaz yapılandırma profilinin bir parçası olarak nasıl yapılandırılacağı açıklanır. Bir profil oluşturduktan sonra, bu profili Windows 10 cihazlarınıza atar veya dağıtabilirsiniz. 

Intune 'un desteklediği teslim iyileştirme ayarlarının listesi için bkz. [Intune Için teslim iyileştirme ayarları](../delivery-optimization-settings.md).  

Windows 10 ' da teslim Iyileştirmesi hakkında bilgi edinmek için Windows belgelerindeki [teslim iyileştirme güncelleştirmeleri](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) bölümüne bakın.  

> [!NOTE]
> **Yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları** **teslim iyileştirme** ayarları ile değiştirilmiştir. Mevcut güncelleştirme halkalarınız **teslim iyileştirme** ayarlarını kullanacak şekilde değiştirilebilir. [Mevcut güncelleştirme halkalarını teslim Iyileştirmeye taşıyın](#move-existing-update-rings-to-delivery-optimization) (Bu makalede)

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

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Mevcut güncelleştirme halkalarını teslim iyileştirmeye taşıyın

**Teslim iyileştirme** ayarları, **yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkalarını**değiştirir. Mevcut güncelleştirme halkalarınız, **teslim iyileştirme** ayarlarını kullanmak üzere kolayca değiştirilebilir. Teslim iyileştirme profili oluştururken aynı ayarları sürdürmek için, aynı *teslim iyileştirme indirme modunu* kullanın ve ardından, zaten kullandığınız ayarları ayarlayın. Bununla birlikte, teslim iyileştirme profilinin yönetebileceği tam kapsamlı ayarların avantajlarından yararlanmak için teslim iyileştirme ayarlarını yeniden yapılandırmayı tercih edebilirsiniz.

1. Teslim iyileştirme yapılandırma profili oluşturma:

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
    4. **Tamam** >  değişikliklerinizi**kaydedin** .

## <a name="next-steps"></a>Sonraki adımlar

[Profili atayın](device-profile-assign.md) ve durumunu [izleyin](device-profile-monitor.md) .  
Intune için [teslim iyileştirme ayarlarını](../delivery-optimization-settings.md) görüntüleyin.
