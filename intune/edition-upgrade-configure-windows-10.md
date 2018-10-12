---
title: Windows 10 cihazlarında Microsoft Intune - Azure ile yükseltme veya S modunu kullanma | Microsoft Docs
description: Windows 10 cihazlarını farklı sürümlere yükseltmek için Microsoft Intune'da bir cihaz profili oluşturun. Örneğin, Windows 10 Professional sürümünden Windows 10 Enterprise sürümüne yükseltme yapabilirsiniz. Ayrıca, yapılandırma profilini kullanarak bir cihazda S modunu etkinleştirebilir veya kapatabilirsiniz. Ayrıca Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic ve Mobile için desteklenen yükseltme yollarına da bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0e4ba42559a068ebefb453aba18060803dc36e0
ms.sourcegitcommit: f3974c810e172f345853dacd7f2ca0abc11b1a5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44389634"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Windows 10 sürümünü yükseltmek ya da Intune'da S modundan geçiş yapmak için bir yapılandırma profili kullanın
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows 10 sürümünü çalıştıran cihazları farklı bir sürüme otomatik olarak yükseltmek için Intune'da bir yükseltme profili yapılandırın. Ayrıca, desteklenen yükseltme yollarına da bakın.

## <a name="before-you-begin"></a>Başlamadan önce
Cihazları en son sürüme yükseltmeden önce aşağıdaki önkoşulları sağlamanız gerekir:

- Yükseltilen Windows sürümünü ilkeyle hedeflenen tüm cihazlara yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). Çoklu Etkinleştirme Anahtarları (MAK) veya Anahtar Yönetimi Sunucusu (KMS) anahtarlarından herhangi birini kullanabilirsiniz. Windows 10 Mobile ve Windows 10 Holographic sürümlerinde, ilkeyle hedeflediğiniz tüm cihazlara Windows'un güncelleştirilmiş sürümünü yüklemek için, lisans bilgilerini içeren bir Microsoft lisans dosyası kullanabilirsiniz.
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


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

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

## <a name="upgrade-the-edition"></a>Sürümü yükseltme

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Profil için bir **Ad** ve bir **Açıklama** girin. Örneğin `Windows 10 edition upgrade` gibi şey girin
4. **Platform** olarak **Windows 10 ve üzeri**'ni seçin.
5. **Profil türü** olarak **Sürüm yükseltme**'yi seçin.
6. **Sürüm Yükseltme** özelliklerinde, aşağıdaki ayarları girin:

   - **Yükseltilecek sürüm**: Yükseltme yaptığınız Windows 10 sürümünü seçin. Bu ilke tarafından hedeflenen cihazlar seçtiğiniz sürüme yükseltilir.
   - **Ürün Anahtarı**: Microsoft'tan aldığınız ürün anahtarını girin. Ürün anahtarıyla bir ilke oluşturulduktan sonra anahtar güncelleştirilemez ve güvenlik nedeniyle gizlenir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girin.
   - **Lisans Dosyası**: **İş için Windows 10 Holographic** veya **Windows 10 Mobile sürümü**'nde, seçmek üzere **Gözat** ile Microsoft'tan aldığınız dosyaya gidin. Bu lisans dosyası, hedeflenen cihazları yükselttiğiniz sürümlerinin lisans bilgilerini içerir.

7. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Profili oluşturmak için **Oluştur**'u seçin.

## <a name="switch-out-of-s-mode"></a>S modundan çıkma

[Windows 10 S modu](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) güvenlik ve performans için tasarlanmıştır. Yalnızca Microsoft Store uygulamalarını çalıştırıyorlarsa cihazlarınızı güvenli tutmaya yardımcı olması için S modunu kullanabilirsiniz. Cihazlarınız Microsoft Store'da bulunmayan uygulamalar gerektiriyorsa, S modundan çıkın. S modundan çıkma geri alınamaz. Bir kez çıktıktan sonra Windows 10 S moduna geri dönemezsiniz.

Aşağıdaki adımlar, Windows 10 (1809 veya üzeri) cihazlarda S modunu kontrol eden bir profilin nasıl oluşturulacağını göstermektedir.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Profil için bir **Ad** ve bir **Açıklama** girin. Örneğin, `Windows 10 switch off S mode` gibi bir şey girin
4. **Platform** olarak **Windows 10 ve üzeri**'ni seçin.
5. **Profil türü** olarak **Sürüm yükseltme**'yi seçin.
6. **Mod anahtarı (yalnızca Windows)** seçeneğini belirleyip **S modundan çık** özelliğini ayarlayın. Seçenekleriniz şunlardır:

    - **Yapılandırma yok**: S modundaki bir cihaz S modunda kalır. Son kullanıcı cihazı S modundan çıkarabilir.
    - **S modunda tut**: Son kullanıcının cihazı S modundan çıkarmasını devre dışı bırakır.
    - **Çıkış**: Cihazı S modundan çıkarır.

7. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Profili oluşturmak için **Oluştur**'u seçin.

Profil oluşturulur ve profiller arasında listelenir.

## <a name="next-steps"></a>Sonraki adımlar

Gruplarınıza [bu profili atayın](device-profile-assign.md).

>[!NOTE]
>İlke atamasını daha sonra kaldırırsanız, cihazdaki Windows sürümü geri alınmaz ve normal bir şekilde çalışmaya devam eder.
