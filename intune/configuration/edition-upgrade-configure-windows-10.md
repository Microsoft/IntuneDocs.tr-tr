---
title: Windows 10 cihazlarında yükseltme veya kullanma modu-Microsoft Intune-Azure | Microsoft Docs
description: Windows 10 cihazlarını farklı bir sürüme yükseltmek veya S moduna geçmek için Microsoft Intune kullanın. Yöneticiler, Windows 10 Professional 'ı Windows 10 Enterprise 'a yükseltmek için bir cihaz yapılandırma profili kullanabilir ve S modundan geçiş yapabilir. Windows 10 Pro, N sürümü, eğitim, bulut, kurumsal, Core, Holographic ve mobil için desteklenen yükseltme yollarına bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 13fca4de8e36b1bdeb9026985e2eabd21e56e924
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206950"
---
# <a name="upgrade-windows-10-editions-or-switch-out-of-s-mode-on-devices-using-microsoft-intune"></a>Microsoft Intune kullanarak cihazlarda Windows 10 sürümlerini yükseltme veya S modunu değiştirme



Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, Windows 10 cihazlarınızı yükseltmek isteyebilirsiniz. Örneğin, Windows 10 Professional cihazlarınızı Windows 10 Enterprise 'a yükseltmek istiyorsunuz. Ya da cihazın S modundan geçiş istediğini tercih edersiniz.

[Windows 10 S modu](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) (başka bir Microsoft Web sitesini açar) güvenlik ve performans için tasarlanmıştır. Intune 'U, S modunu değiştirmek için kullanabilirsiniz. S modundan çıkma geri alınamaz. Bir kez çıktıktan sonra Windows 10 S moduna geri dönemezsiniz.

S modu hakkında [sık sorulan bazı sorulara](https://support.microsoft.com/help/4020089/windows-10-in-s-mode-faq) bakın.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri
- S modu için Windows 10 1809 veya üzeri
- Windows 10 Holographic for Business

Bu özellikler Intune 'da kullanılabilir ve yönetici tarafından yapılandırılabilir. Intune, kuruluşunuzun ihtiyaçlarına göre bu ayarları oluşturmak ve özelleştirmek için "yapılandırma profillerini" kullanır. Bu özellikleri bir profile ekledikten sonra, daha sonra, kuruluşunuzdaki Windows 10 cihazlarına profili gönderebilir veya dağıtabilirsiniz. Profil dağıttığınızda, Intune cihazları veya anahtarları S modundan otomatik olarak yükseltir.

Bu makalede, desteklenen yükseltme yolları listelenmekte ve cihaz yapılandırma profilinin nasıl oluşturulacağı gösterilir. [Windows 10](edition-upgrade-windows-settings.md)' un tüm kullanılabilir yükseltme ve mod ayarlarını da görebilirsiniz.

> [!NOTE]
> İlke atamasını daha sonra kaldırırsanız, cihazdaki Windows sürümü geri döndürülemez. Cihaz normal olarak çalışmaya devam eder.

## <a name="prerequisites"></a>Önkoşullar

Cihazları yükseltmeden önce, aşağıdaki önkoşullara sahip olduğunuzdan emin olun:

- Yükseltilen Windows sürümünü ilkeyle hedeflenen tüm cihazlara yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). Çoklu Etkinleştirme Anahtarları (MAK) veya Anahtar Yönetimi Sunucusu (KMS) anahtarlarından herhangi birini kullanabilirsiniz.
- Windows 10 Mobile ve Windows 10 holographic sürümleri için bir Microsoft lisans dosyası kullanabilirsiniz. Lisans dosyası, ilkeyle hedeflediğiniz tüm cihazlara güncelleştirilmiş sürümü yüklemek için lisans bilgilerini içerir.
- İlkeyi atadığınız Windows 10 cihazları Microsoft Intune’a kaydedilir. Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlar ile sürüm yükseltme ilkesini kullanamazsınız.

## <a name="supported-upgrade-paths"></a>Desteklenen yükseltme yolları

Aşağıdaki tabloda, Windows 10 sürümü yükseltme profili için desteklenen yükseltme yolları listelenmiştir.

| Kaynak yükseltme sürümü | Hedef yükseltme sürümü |
|---|---|
| Windows 10 Pro | Windows 10 eğitimi <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Windows 10 Pro N sürümü | Windows 10 Education N sürümü <br/>Windows 10 Enterprise N sürümü <br/>Windows 10 Pro Education N sürümü | 
| Windows 10 Pro Education | Windows 10 eğitimi | 
| Windows 10 Pro Education N sürümü | Windows 10 Education N sürümü |
| Windows 10 Cloud | Windows 10 eğitimi <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Windows 10 Cloud N sürümü | Windows 10 Education N sürümü <br/>Windows 10 Enterprise N sürümü <br/>Windows 10 Pro N sürümü <br/>Windows 10 Pro Education N sürümü | 
| Windows 10 Enterprise | Windows 10 eğitimi | 
| Windows 10 Enterprise N sürümü | Windows 10 Education N sürümü | 
| Windows 10 Core | Windows 10 eğitimi <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Windows 10 Core N sürümü | Windows 10 Education N sürümü <br/>Windows 10 Enterprise N sürümü <br/>Windows 10 Pro Education N sürümü | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)  (X) = not supported    
![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Pro N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Pro Education|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Pro Education N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Cloud|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Cloud N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Enterprise|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Enterprise N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Core|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Core N|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Mobile|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|
|Holographic|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![unsupported](./media/edition-upgrade-configure-windows-10/x_blk.png)|![supported](./media/edition-upgrade-configure-windows-10/check_grn.png) -->

## <a name="create-the-profile"></a>Profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin. Örneğin, `Windows 10 edition upgrade profile` veya `Windows 10 switch off S mode`gibi bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üstünü**seçin.
    - **Profil türü**: **sürüm yükseltme**' yi seçin.
    - **Ayarlar**: yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yapacaklarınız için, bkz.:

        - [Windows 10 yükseltme ve S modu](edition-upgrade-windows-settings.md)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

Profil oluşturulur ve listede gösterilir. [Profili atayıp](device-profile-assign.md) [durumunu izlemeyi](device-profile-monitor.md)unutmayın.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak için hazırlanın. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Windows 10](edition-upgrade-windows-settings.md) ve [Windows holographic for Business](holographic-upgrade.md) cihazlarına yönelik yükseltme ve S modu ayarlarını görüntüleyin.
