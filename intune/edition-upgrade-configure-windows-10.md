---
title: Yükseltme veya Windows 10 cihazlarda - Microsoft Intune - S modunu kullanmak Azure | Microsoft Docs
description: Windows 10 cihazlarını farklı bir sürüme yükseltmek için Microsoft Intune kullanın veya S modunu etkinleştirin. Yöneticiler, Windows 10 Professional, Windows 10 Enterprise için yükseltme ve etkinleştirme veya S modundan geçiş için bir cihaz yapılandırma profili kullanabilirsiniz. Windows 10 Pro N sürümü, eğitim, bulut, Enterprise, Core, Holographic ve Mobile için desteklenen yükseltme yolları bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26a8718247142ef2ed3f509dc185207b1e99e82f
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233330"
---
# <a name="upgrade-windows-10-editions-or-enable-s-mode-on-devices-using-microsoft-intune"></a>Windows 10 sürümlerine yükseltmek veya Intune kullanarak cihazlarda S modunu etkinleştir

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, Windows 10 cihazlarını yükseltmek isteyebilirsiniz. Örneğin, Windows 10 Enterprise için Windows 10 Professional cihazları yükseltmek istediğiniz. Veya, S mobil cihazları yalnızca Microsoft Store uygulamaları çalıştırma için etkinleştirmek istediğiniz.

[Windows 10 S modu](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) güvenlik ve performans için tasarlanmıştır. Yalnızca Microsoft Store uygulamalarını çalıştırıyorlarsa cihazlarınızı güvenli tutmaya yardımcı olması için S modunu kullanabilirsiniz. Cihazlarınızı Microsoft Store içinde kullanılamayan uygulamaları kullanıyorsanız, S modundan geçiş yapın. S modundan çıkma geri alınamaz. Bir kez çıktıktan sonra Windows 10 S moduna geri dönemezsiniz.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri
- Windows 10 1809 veya üzeri S modu
- Windows 10 Holographic for Business

Bu özellikler, Intune'da bulunan ve yönetici tarafından yapılandırılabilir. Intune kullanır "yapılandırma profillerini" oluşturabilir ve kuruluşunuzun ihtiyaçları için bu ayarları özelleştirebilirsiniz. Bu özellikler bir profilde ekledikten sonra daha sonra anında iletme veya kuruluşunuzda Windows 10 cihazlarına profil dağıtmak. Profili dağıttığınızda, otomatik olarak Intune cihazları yükseltir veya S modunu etkinleştirir.

Bu makalede, desteklenen yükseltme yolları listelenir ve cihaz yapılandırma profili oluşturma işlemi gösterilmektedir. Tüm kullanılabilir yükseltme ve S modu ayarları için Ayrıca bkz [Windows 10](edition-upgrade-windows-settings.md).

> [!NOTE]
> İlke atamasını daha sonra kaldırırsanız cihazdaki Windows sürümü geri alınır. Cihaz, normal şekilde çalışmaya devam eder.

## <a name="prerequisites"></a>Önkoşullar

Cihazları yükseltmeden önce aşağıdaki önkoşulların karşılandığından emin olun:

- Yükseltilen Windows sürümünü ilkeyle hedeflenen tüm cihazlara yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). Çoklu Etkinleştirme Anahtarları (MAK) veya Anahtar Yönetimi Sunucusu (KMS) anahtarlarından herhangi birini kullanabilirsiniz.
- Windows 10 Mobile ve Windows 10 Holographic sürümleri için bir Microsoft lisans dosyası kullanabilirsiniz. Lisans dosyası güncelleştirilmiş sürüm tüm cihazlara Windows'un ilkeyle hedeflediğiniz yüklemek için gerekli lisans bilgilerini içerir.
- İlkeyi atadığınız Windows 10 cihazları Microsoft Intune’a kaydedilir. Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlar ile sürüm yükseltme ilkesini kullanamazsınız.

## <a name="supported-upgrade-paths"></a>Desteklenen yükseltme yolları

Aşağıdaki tabloda, Windows 10 sürümü yükseltme profili için desteklenen yükseltme yolları listelenmiştir.

| Kaynak yükseltme sürümü | Hedef yükseltme sürümü |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Windows 10 Pro N sürümü | Windows 10 Education N sürümü <br/>Windows 10 Enterprise N sürümü <br/>Windows 10 Pro Education N sürümü | 
| Windows 10 Pro Education | Windows 10 Education | 
| Windows 10 Pro Education N sürümü | Windows 10 Education N sürümü |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Windows 10 Cloud N sürümü | Windows 10 Education N sürümü <br/>Windows 10 Enterprise N sürümü <br/>Windows 10 Pro N sürümü <br/>Windows 10 Pro Education N sürümü | 
| Windows 10 Enterprise | Windows 10 Education | 
| Windows 10 Enterprise N sürümü | Windows 10 Education N sürümü | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Windows 10 Core N sürümü | Windows 10 Education N sürümü <br/>Windows 10 Enterprise N sürümü <br/>Windows 10 Pro Education N sürümü | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin. Örneğin, aşağıdaki gibi girin `Windows 10 edition upgrade profile` veya `Windows 10 switch off S mode`.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Platformu seçin:  

        - **Windows 10 ve üzeri**

    - **Profil türü**: Seçin **sürüm yükseltme**.
    - **Ayarları**: Yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yaptıkları için bkz:

        - [Windows 10 yükseltme ve S modu](edition-upgrade-windows-settings.md)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. 

Profil oluşturulur ve listede gösterilen. Mutlaka [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak üzere hazırdır. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

Yükseltme ve S modu ayarları için görüntüleme [Windows 10](edition-upgrade-windows-settings.md) ve [Windows Holographic for Business](holographic-upgrade.md) cihazlar.
