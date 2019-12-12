---
title: Microsoft Intune Windows güncelleştirmeleri için Güncelleştirme Uyumluluğu raporlarını kullanın
titleSuffix: Microsoft Intune
description: Intune ile dağıttığınız Windows güncelleştirmelerinin rapor verilerini görüntülemek için OMS Güncelleştirme Uyumluluğu kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0de98a0820e15a09c2b3724b216359580327259e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74465715"
---
# <a name="intune-compliance-reports-for-updates"></a>Güncelleştirmeler için Intune uyumluluk raporları

Windows 10 cihazlarına Windows Update dağıtmak için Intune 'u kullandığınızda, Intune 'U kullanarak güncelleştirme uyumluluğu hakkındaki ayrıntıları veya Microsoft Operations Management Suite (OMS) bir parçası olan *güncelleştirme uyumluluğu*adlı ücretsiz bir çözümü görüntüleyin.

## <a name="use-intune"></a>Intune 'U kullanma

Yapılandırdığınız Windows 10 güncelleştirme halkaları için dağıtım durumundaki bir ilke raporunu gözden geçirmek için:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Yazılım güncelleştirme durumu** >  > **cihazlar** ' **ı** seçin. Atadığınız tüm güncelleştirme halkalarının durumu hakkında genel bilgileri görebilirsiniz.

3. Ek ayrıntıları görüntülemek için **izleyici**' yi seçin. Ardından **yazılım güncelleştirmeleri**' nin altında, **güncelleştirme halkası dağıtım durumu** ' nu seçin ve gözden geçirilecek dağıtım halkasını seçin.

   **İzle** bölümünde, güncelleştirme halkası hakkında ayrıntılı bilgileri görüntülemek için aşağıdaki raporlardan birini seçin:

   - **Cihaz durumu**-bu işlem cihaz yapılandırma durumunu gösterir, Ayrıntılar için bkz. [deviceConfigurationDeviceStatus güncelleştirme]( https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationdevicestatus-update?view=graph-rest-1.0).

   - **Kullanıcı durumu**-bu işlem Kullanıcı adı, durum ve son rapor tarihini gösterir, Ayrıntılar için bkz. [Deviceconfigurationuserdurumlarının listesi](https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationuserstatus-list?view=graph-rest-1.0).

   - **Son Kullanıcı güncelleştirme durumu**-bu işlem Windows cihaz güncelleştirme durumunu gösterir, Ayrıntılar için bkz. [windowsupdatestate](https://docs.microsoft.com/graph/api/resources/intune-shared-windowsupdatestate?view=graph-rest-beta).

## <a name="use-update-compliance"></a>Güncelleştirme Uyumluluğu kullan

Windows 10 Update piyasaya çıkarma 'i Windows Analytics çözümünü [güncelleştirme uyumluluğu](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor)kullanarak izleyebilirsiniz. Güncelleştirme Uyumluluğu Azure portal sunulur ve [önkoşullarını](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites)karşılayan cihazlarda ücretsiz olarak kullanılabilir.  

Bu çözümü kullandığınızda, güncelleştirme uyumluluğunu raporlamak istediğiniz Intune ile yönetilen Windows 10 cihazlarınızdan birine ticari bir KIMLIK dağıtırsınız.  

Intune 'da, ticari KIMLIĞI yapılandırmak için özel bir ilkenin OMA-URI ayarlarını kullanırsınız. [Microsoft Intune 'Da Windows 10 cihazları Için Intune ilke ayarları](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)bölümüne bakın.  

Ticari KIMLIĞI yapılandırmaya yönelik OMA-URI (büyük/küçük harfe duyarlı) yolu: *./Vendor/MSFT/DMClient/Provider/MS DM Server/Commercial Cıalıd*  

Örneğin, **OMA-URI Ayarı Ekle veya Düzenle** bölümünde aşağıdaki değerleri kullanabilirsiniz:

- **Ayar Adı**: Windows Analytics Ticari Kimliği
- **Ayar Açıklaması**: Windows Analytics çözümleri için ticari kimliği yapılandırma
- **OMA-URI** (büyük/küçük harfe duyarlı): *./Vendor/MSFT/DMClient/Provider/MS DM Server/ticari IDID*
- **Veri Türü:** Dize
- **Değer**: \<OMS çalışma alanınızdaki Windows telemetri SEKMESINDE gösterilen GUID 'yi kullanın >

> [!NOTE]
> MS DM Sunucusu hakkında daha fazla bilgi için bkz. [DMClient yapılandırma hizmet sağlayıcısı (CSP)]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="next-steps"></a>Sonraki adımlar

[Intune 'da yazılım güncelleştirmelerini yönetme](windows-update-for-business-configure.md)
