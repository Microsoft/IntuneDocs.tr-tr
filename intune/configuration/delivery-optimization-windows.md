---
title: Microsoft Intune-Azure 'da Windows 10 için teslim iyileştirme ayarları | Microsoft Docs
description: Intune ile yönettiğiniz Windows 10 cihazlarının teslim iyileştirmesi kullanma şeklini yapılandırın. Intune 'da, güncelleştirmeleri Internet 'ten yüklemek için bir cihaz yapılandırma profili oluşturun. Ayrıca bkz. var olan güncelleştirme halkalarını teslim iyileştirme profiliyle değiştirme.
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
ms.openlocfilehash: 4357a3235386d9fd17c1df23004e9bc8ddeb28ca
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730849"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Microsoft Intune teslim iyileştirme ayarları

Intune ile, bu cihazlar uygulamaları ve güncelleştirmeleri indirdiğinizde bant genişliği tüketimini azaltmak için Windows 10 cihazlarınız için teslim iyileştirme ayarlarını kullanabilirsiniz. Teslim iyileştirme, cihaz yapılandırma profillerinizin bir parçası olarak yapılandırılır.  

Bu makalede, teslim iyileştirme ayarlarının cihaz yapılandırma profilinin bir parçası olarak nasıl yapılandırılacağı açıklanır. Bir profil oluşturduktan sonra, bu profili Windows 10 cihazlarınıza atar veya dağıtabilirsiniz. 

Intune 'un desteklediği teslim iyileştirme ayarlarının listesi için bkz. [Intune Için teslim iyileştirme ayarları](../delivery-optimization-settings.md).  

Windows 10 ' da teslim Iyileştirmesi hakkında bilgi edinmek için Windows belgelerindeki [teslim iyileştirme güncelleştirmeleri](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) bölümüne bakın.  


> [!NOTE]
> **Yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları** **teslim iyileştirme** ayarları ile değiştirilmiştir. Mevcut güncelleştirme halkalarınız **teslim iyileştirme** ayarlarını kullanacak şekilde değiştirilebilir. [Mevcut güncelleştirme halkalarını teslim Iyileştirmeye taşıyın](#move-existing-update-rings-to-delivery-optimization) (Bu makalede) 
## <a name="create-the-profile"></a>Profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.

2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.

3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: platformu seçin:  

        - **Windows 10 ve üzeri**

    - **Profil türü**: **teslim iyileştirmesi**' nı seçin.
    - **Ayarlar**: güncelleştirmelerin ve uygulamaların nasıl indirilmek istediğinizi tanımlayan ayarları yapılandırın. Kullanılabilir ayarlar hakkında daha fazla bilgi için bkz. [Intune Için teslim iyileştirme ayarları](../delivery-optimization-settings.md).

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin.

Profil oluşturulur ve listede gösterilir. Sonra, [profili atayın](device-profile-assign.md) ve ardından [durumunu izleyin](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Mevcut güncelleştirme halkalarını teslim iyileştirmeye taşıyın

**Teslim iyileştirme** ayarları, **yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkalarını**değiştirir. Mevcut güncelleştirme halkalarınız, **teslim iyileştirme** ayarlarını kullanmak üzere kolayca değiştirilebilir. Teslim iyileştirme profili oluştururken aynı ayarları sürdürmek için, aynı *teslim iyileştirme indirme modunu* kullanın ve ardından, zaten kullandığınız ayarları ayarlayın. Bununla birlikte, teslim iyileştirme profilinin yönetebileceği tam kapsamlı ayarların avantajlarından yararlanmak için teslim iyileştirme ayarlarını yeniden yapılandırmayı tercih edebilirsiniz.

1. Teslim iyileştirme yapılandırma profili oluşturma:

    1. Intune 'da **cihaz yapılandırma** > **profiller** > **Profil oluştur**' u seçin.
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
1. Bu yeni profili, var olan yazılım güncelleştirme halkası ile aynı cihazlara ve kullanıcılara atayın. [Profil atama](device-profile-assign.md) adımları listeler.

3. Mevcut yazılım halkasını yapılandırmayı geri al:
    1. Intune 'da Windows 10 güncelleştirme halkalarını > **yazılım güncelleştirmeleri** ' ne gidin.
    2. Listeden güncelleştirme halkasını seçin.
    3. Ayarlar ' da **teslim iyileştirme indirme modunu** **Yapılandırılmadı**olarak ayarlayın.
    4. **Tamam** >  değişikliklerinizi**kaydedin** .

## <a name="next-steps"></a>Sonraki adımlar

[Profili atayın](device-profile-assign.md) ve durumunu [izleyin](device-profile-monitor.md) .  
Intune için [teslim iyileştirme ayarlarını](../delivery-optimization-settings.md) görüntüleyin.
