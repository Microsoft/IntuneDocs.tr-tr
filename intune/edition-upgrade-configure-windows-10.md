---
title: Microsoft Intune - Azure ile Windows 10 cihazlarını yükseltme | Microsoft Docs
description: Windows 10 cihazlarını yeni sürümlere yükseltmek için Microsoft Intune'da bir cihaz profili oluşturun. Ayrıca Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic ve Mobile için desteklenen yükseltme yollarına da bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 994ab8e7d955d18b293e4d9e9661e0c44baaaa1f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-windows-10-edition-upgrade-profile-in-intune"></a>Intune'da Windows 10 sürüm yükseltme profilini yapılandırma
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows 10 sürümünü çalıştıran cihazları farklı bir sürüme otomatik olarak yükseltmek için Intune'da bir yükseltme profili yapılandırın. Ayrıca, desteklenen yükseltme yollarına da bakın.

## <a name="before-you-begin"></a>Başlamadan önce
Cihazları en son sürüme yükseltmeden önce aşağıdakilerden birine sahip olmanız gerekir:

- Yükseltilen Windows sürümünü ilkeyle hedeflenen tüm cihazlara yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). İlkeyle hedeflediğiniz tüm cihazlara güncelleştirilmiş Windows sürümünü yüklemek için Çoklu Etkinleştirme Anahtarı (MAK) veya Anahtar Yönetimi Sunucusu (KMS) ya da gerekli lisans bilgilerini içeren bir Microsoft lisans dosyası kullanabilirsiniz (Windows 10 Mobile ve Windows 10 Holographic sürümleri için).
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

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Cihaz kısıtlama ayarlarını içeren bir cihaz profili oluşturma
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması**’nı seçin, **Profiller**’i seçin ve ardından **Profil Oluştur**’u seçin.
4. Sürüm yükseltme profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinde **Sürüm yükseltme**’yi seçin.
7. **Sürüm Yükseltme** özelliklerinde, aşağıdaki ayarları girin:
   - **Yükseltilecek sürüm** - Açılan listede, hedeflenen cihazları yükselttiğiniz Windows 10 Masaüstü, Windows 10 Holographic veya Windows 10 Mobile sürümünü seçin.
   - **Ürün Anahtarı** - Microsoft’tan aldığınız ve tüm hedeflenen Windows 10 Masaüstü cihazlarını yükseltmek için kullanılabilen ürün anahtarını girin. 
    Ürün anahtarı içeren bir ilke oluşturduktan sonra, anahtar güncelleştirilemez ve güvenlik nedenleriyle gizlenir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girin.
   - **Lisans Dosyası** - Microsoft'tan aldığınız lisans dosyasını belirtmek için **Gözat**'ı seçin. Bu lisans dosyası hedeflenen cihazları yükselttiğiniz Windows Holographic veya Windows 10 Mobile sürümüne yönelik lisans bilgilerini içerir.
8. İşiniz bittiğinde, değişikliklerinizi kaydetmek için **Oluştur**'u seçin.

Profil oluşturulur ve profiller arasında listelenir.

## <a name="next-steps"></a>Sonraki adımlar

Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).

>[!NOTE]
>İlke atamasını daha sonra kaldırırsanız cihazdaki Windows sürümü geri alınmaz ve normal bir şekilde çalışmaya devam eder.