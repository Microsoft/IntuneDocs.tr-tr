---
title: Microsoft Intune Windows güncelleştirmelerini güncelleştirme uyumluluğu raporları kullanın. | Microsoft Docs
description: OMS güncelleştirme uyumluluğu, Intune ile Windows dağıttığınız güncelleştirmeleri için rapor verileri görüntülemek için kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa549e90e9c0066ae10772728f097b5951284959
ms.sourcegitcommit: e262b0ad8df610e25eb9421b9ebc2673bcf1020e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2019
ms.locfileid: "55986960"
---
# <a name="intune-compliance-reports-for-updates"></a>Güncelleştirmeler için Intune uyumluluk raporları
Windows update, Windows 10 cihazlara dağıtmak için Intune kullandığınızda, Intune veya ücretsiz bir çözümü kullanarak güncelleştirme uyumluluğunu ayrıntılarını görüntüleme adlı *güncelleştirme uyumluluğu*, Microsoft Operations Management Suite (OMS) bir parçası olduğu.

## <a name="use-intune"></a>Intune kullanın
Bir ilke raporu, yapılandırdığınız Windows 10 güncelleştirme halkaları için dağıtım durumunu gözden geçirmek için: 
1. [Azure Portal](https://portal.azure.com/) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Yazılım güncelleştirmeleri** > **Genel bakış**’ı seçin. Atadığınız tüm güncelleştirme halkalarının durumu hakkında genel bilgileri görebilirsiniz.
4. Aşağıdaki raporlardan birini açın:  

   **Tüm dağıtım halkaları için**:
   1. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları**’nda
   2. **İzle** bölümünde **Uygulama başına halka dağıtım durumu**’nu seçin.  

   **Belirli dağıtım halkaları için**:  

   1. **Yazılım güncelleştirmeleri** > **Windows 10 Güncelleştirme Halkaları**’nda gözden geçirmek istediğiniz dağıtım kademesini seçin.  
   2. **İzle** bölümünde, güncelleştirme halkası hakkında ayrıntılı bilgileri görüntülemek için aşağıdaki raporlardan birini seçin:  
      - **Cihaz durumu**  
      - **Kullanıcı durumu**  

## <a name="use-update-compliance"></a>Güncelleştirme uyumluluğu kullanın
Windows 10 güncelleştirme dağıtımlarını kullanarak izleyebileceğiniz [güncelleştirme uyumluluğu](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor), bir Windows analiz çözümüdür. Güncelleştirme uyumluluğu Azure Portalı aracılığıyla sunulur ve ücretsiz karşılayan cihazlar için kullanılabilir, [önkoşulları](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites).  

Bu çözümü kullandığınızda, ticari kimliği tüm Intune dağıttığınız yönetilen Windows 10 cihazlar için güncelleştirme uyumluluğunu raporlamak istediğiniz.  

Intune konsolunda kullanarak ticari kimliği yapılandırmak için bir özel ilke OMA-URI ayarlarını kullanın Ayrıntılı bilgi için bkz. [Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

Ticari kimliği yapılandırmaya ilişkin OMA-URI (büyük/küçük harfe duyarlı) yolu: *./Vendor/MSFT/DMClient/Provider/MS DM Server/Commercialıd*  

Örneğin, **OMA-URI Ayarı Ekle veya Düzenle** bölümünde aşağıdaki değerleri kullanabilirsiniz:
- **Ayar adı**: Windows Analytics ticari kimliği
- **Ayar açıklaması**: Ticari kimliği için Windows Analytics çözümleri yapılandırma
- **OMA-URI** (büyük/küçük harfe duyarlı): *./Vendor/MSFT/DMClient/Provider/MS DM Server/Commercialıd*
- **Veri türü**: Dize
- **Değer**: \<OMS çalışma alanınızdaki Windows Telemetri sekmesinde gösterilen GUID'yi kullanın >
 
> [!NOTE]  
> MS DM Sunucusu hakkında daha fazla bilgi için bkz. [DMClient yapılandırma hizmet sağlayıcısı (CSP)]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Sonraki adımlar
[Intune'da yazılım güncelleştirmelerini yönetme](windows-update-for-business-configure.md)
