---
title: "Intune ile Windows 10 sürüm yükseltmelerini yapılandırma"
titlesuffix: Azure portal
description: "Intune’u, yönettiğiniz Windows 10 cihazlarını farklı bir sürüme yükseltmek için kullanmayı öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8581aea9db4c04efda5fe9f3281be95330bcd2e2
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 sürüm yükseltmelerini yapılandırma
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows 10 sürüm yükseltme profilinin nasıl yapılandırılacağını öğrenmek için bu makaledeki bilgileri kullanın. Bu profil Windows 10 sürümünü çalıştıran cihazları farklı bir sürüme otomatik olarak yükseltmenizi sağlar. 

## <a name="before-you-start"></a>Başlamadan önce
Cihazları en son sürüme yükseltmeye başlamadan önce şunlardan birine sahip olmanız gerekir:

- İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için Çoklu Etkinleştirme Anahtarı (MAK) veya Anahtar Yönetimi Sunucusu (KMS) ya da gerekli lisans bilgilerini içeren bir Microsoft lisans dosyası kullanabilirsiniz (Windows 10 Mobile ve Windows 10 Holographic sürümleri için).
- İlkeyi atadığınız Windows 10 cihazlar Microsoft Intune’a kayıtlı olmalıdır. Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlar ile sürüm yükseltme ilkesini kullanamazsınız.

## <a name="supported-upgrade-paths-for-the-windows-10-edition-upgrade-profile"></a>Windows 10 sürümü yükseltme profili için desteklenen yükseltme yolları
Aşağıdaki listeler, Windows 10 sürümü yükseltme profili için desteklenen yükseltme yollarını sağlar. Yükseltme hedefi olan Windows 10 sürümü kalın yazıyla gösterilir ve ardından yükseltme yapabileceğiniz desteklenen kaynak sürümleri listesi yer alır:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N sürümü**    
- Windows 10 Pro N sürümü
- Windows 10 Pro Education N sürümü
- Windows 10 Cloud N sürümü
- Windows 10 Enterprise N sürümü
- Windows 10 Core N sürümü
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N sürümü**
- Windows 10 Pro N sürümü
- Windows 10 Cloud N sürümü
- Windows 10 Core N sürümü
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N sürümü**
- Windows 10 Cloud N sürümü
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N sürümü**
- Windows 10 Pro N sürümü
- Windows 10 Cloud N sürümü
- Windows 10 Core N sürümü

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile

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
1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, sürüm yükseltme profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinde **Sürüm yükseltme**’yi seçin.
7. **Sürüm Yükseltme** dikey penceresinde aşağıdaki ayarları yapılandırın:
    - **Yükseltilecek sürüm** - Açılan listede, hedeflenen cihazları yükseltmek istediğiniz Windows 10 Masaüstü, Windows 10 Holographic veya Windows 10 Mobile sürümünü seçin.
    - **Ürün Anahtarı** - Microsoft’tan aldığınız ve tüm hedeflenen Windows 10 Masaüstü cihazlarını yükseltmek için kullanılabilen ürün anahtarını belirtin.<br>.Ürün anahtarı içeren bir ilke oluşturduğunuzda, ürün anahtarını daha sonra düzenleyemezsiniz. Bunun nedeni, anahtarın güvenlik nedeniyle engellenmesidir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girmeniz gerekir.
    - **Lisans Dosyası** - Microsoft’tan aldığınız ve hedeflenen cihazları yükseltmek istediğiniz Windows Holographic veya Windows 10 Mobile sürümünün lisans bilgilerini içeren lisans dosyasını belirlemek için **Gözat**’ı seçin.
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).

>[!NOTE]
>İlke atamasını daha sonra kaldırırsanız cihazdaki Windows sürümü geri alınmaz ve normal bir şekilde çalışmaya devam eder.

