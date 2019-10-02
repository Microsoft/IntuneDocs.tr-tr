---
title: Microsoft Intune Windows güncelleştirmeleri için Güncelleştirme Uyumluluğu raporlarını kullanın
titleSuffix: Microsoft Intune
description: Intune ile dağıttığınız Windows güncelleştirmelerinin rapor verilerini görüntülemek için OMS Güncelleştirme Uyumluluğu kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 09f3cafc16d8a08885731aa244a089367c6c0933
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732473"
---
# <a name="intune-compliance-reports-for-updates"></a>Güncelleştirmeler için Intune uyumluluk raporları
Windows 10 cihazlarına Windows Update dağıtmak için Intune 'u kullandığınızda, Intune 'U kullanarak güncelleştirme uyumluluğu hakkındaki ayrıntıları veya Microsoft Operations Management Suite (OMS) bir parçası olan *güncelleştirme uyumluluğu*adlı ücretsiz bir çözümü görüntüleyin.

## <a name="use-intune"></a>Intune 'U kullanma
Yapılandırdığınız Windows 10 güncelleştirme halkaları için dağıtım durumundaki bir ilke raporunu gözden geçirmek için: 
1. [Azure portalı](https://portal.azure.com/)’nda oturum açın.
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

## <a name="use-update-compliance"></a>Güncelleştirme Uyumluluğu kullan
Windows 10 Update piyasaya çıkarma 'i Windows Analytics çözümünü [güncelleştirme uyumluluğu](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor)kullanarak izleyebilirsiniz. Güncelleştirme Uyumluluğu Azure portal sunulur ve [önkoşullarını](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites)karşılayan cihazlarda ücretsiz olarak kullanılabilir.  

Bu çözümü kullandığınızda, güncelleştirme uyumluluğunu raporlamak istediğiniz Intune ile yönetilen Windows 10 cihazlarınızdan birine ticari bir KIMLIK dağıtırsınız.  

Intune konsolunda, ticari KIMLIĞI yapılandırmak için özel bir ilkenin OMA-URI ayarlarını kullanırsınız. Ayrıntılı bilgi için bkz. [Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

Ticari KIMLIĞI yapılandırmaya yönelik OMA-URI (büyük/küçük harfe duyarlı) yolu: *./Vendor/MSFT/DMClient/Provider/MS DM Server/Commercial Cıalıd*  

Örneğin, **OMA-URI Ayarı Ekle veya Düzenle** bölümünde aşağıdaki değerleri kullanabilirsiniz:
- **Ayar Adı**: Windows Analytics Ticari Kimliği
- **Ayar Açıklaması**: Windows Analytics çözümleri için ticari kimliği yapılandırma
- **OMA-URI** (büyük/küçük harfe duyarlı): *./Vendor/MSFT/DMClient/Provider/MS DM Server/ticari IDID*
- **Veri Türü:** Dize
- **Değer**: \<oms çalışma alanınızdaki Windows telemetri SEKMESINDE gösterilen GUID 'yi kullanın >
 
> [!NOTE]  
> MS DM Sunucusu hakkında daha fazla bilgi için bkz. [DMClient yapılandırma hizmet sağlayıcısı (CSP)]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Sonraki adımlar
[Intune 'da yazılım güncelleştirmelerini yönetme](windows-update-for-business-configure.md)

