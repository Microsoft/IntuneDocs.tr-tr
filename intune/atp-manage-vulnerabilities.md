---
title: Microsoft Defender ATP - Azure tarafından bulunan güvenlik açıklarını düzeltin için Intune'u kullanmayı | Microsoft Docs
description: Güvenlik görevlerden, tehdit ve güvenlik açığı yönetimi, Intune konsolu içinde bölümü, Microsoft Defender Gelişmiş tehdit Koruması (ATP) gelen yönetme konusuna bakın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 987e3171c4e5c5ba3f15097837e2c018ddc7a4b6
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66049209"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Microsoft tarafından Defender ATP güvenlik açıkları düzeltmek için Intune kullanın  

Microsoft Defender Gelişmiş tehdit Koruması (ATP ile) Intune tümleştirdiğinizde, ATPs tehdit ve güvenlik açığı Yönetimi (TVM) yararlanmak ve uç nokta zayıflık TVM tarafından tanımlanan düzeltme için Intune kullanın. Bu tümleştirme, bulma ve düzeltme yanıt süresi, ortamınız genelinde iyileştirebilir güvenlik açıklarını önceliklendirilmesi risk tabanlı bir yaklaşım getirir.  

[Tehdit ve güvenlik açığı Yönetimi](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) parçasıdır [Microsoft Defender Gelişmiş tehdit koruması](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).  

## <a name="how-integration-works"></a>Tümleştirme nasıl çalışır?  

Microsoft Defender Gelişmiş tehdit koruması için Intune bağlandıktan sonra ATP tehdit ve Güvenlik Açığı Ayrıntıları yönetilen cihazlardan alır.  

Windows Defender Güvenlik Merkezi konsolunda ATP güvenlik yöneticileri uç noktası güvenlik açıkları hakkındaki verileri gözden geçirin. Yöneticileri, tek tıklamayla ardından savunmasız cihazlar için düzeltme bayrak güvenlik görevlerini oluşturmak için kullanın. Güvenlik görevlerini, Intune yöneticilerinin raporları nereye görüntüleyebilir Intune konsoluna hemen geçirilir. Güvenlik görevi güvenlik açığı, öncelik, durumu ve güvenlik açığı düzeltmek için atılması gereken adımları türünü tanımlar. Intune Yöneticisi, kabul etme veya reddetme görevi seçer.  

Bir görev kabul edildiğinde, Intune Yöneticisi sonra güvenlik açığı ancak Intune, güvenlik görevinin bir parçası sağlanan yönergeleri kullanarak düzeltmek için çalışır.  

Düzeltme için ortak eylemler şunlardır:  
- **Blok** çalıştırılan uygulamanın  
- **Dağıtma** bir işletim sistemi güvenlik açıklarını hafifletecek güncelleştirilecek.  
- **Değiştirme** bir kayıt defteri değeri.  
- **Devre dışı** veya **etkinleştirme** güvenlik açığı etkilemek için bir yapılandırma.  
- **Dikkat etmeniz gereken** tehdit admin sağlamak için uygun bir öneri olmayan olduğunda uyarır.  

Bir örnek iş akışı:  
- Microsoft Defender ATP içinde Contoso Media Player v4 adlı bir uygulama için bir güvenlik açığı bulunan ve bir yönetici uygulamayı güncelleştirmek için bir güvenlik görevi oluşturur. Contoso Media player, Intune ile dağıtılan bir yönetilmeyen bir uygulamadır.  

  Bu güvenlik görevi bekleme durumu ile Intune konsolunda görünür:  
  ![Intune konsolunda güvenlik Görevler listesini görüntüleyin](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- Intune yöneticisi görevinin ayrıntılarını görüntülemek için güvenlik görevi seçer.  Yönetici ardından seçer **kabul**, hangi güncelleştirmelerin olması için ATP'yi ve Intune durum *kabul edilen*.  
  ![Kabul etme veya reddetme bir güvenlik görevi](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- Yönetici daha sonra sağlanan kılavuzuna göre görev düzeltir.  Kılavuz, gereken düzeltme türüne bağlı olarak değişir. Kullanılabilir olduğunda, Intune'da yapılandırmaları için ilgili bölmeleri açın bağlantıları düzeltme kılavuz içerir. 

  Bu örnekte media player, yönetilen bir uygulama olmadığı için Intune yalnızca metin yönergeleri sağlar. Uygulama yönetilmişse Intune güncelleştirilmiş bir sürümü karşıdan yüklemek için yönergeler sağlar ve uygulama dağıtımının dağıtıma güncelleştirilmiş dosyaları eklenebilir böylece açmak için bir bağlantı sağlayın. 

- Düzeltme tamamlandıktan sonra Intune Yöneticisi güvenlik görevi açılır ve seçer **görev tamamlanamıyor**.  Intune ve burada güvenlik yöneticilerini düzenlenen durumu güvenlik açığı doğrulamak ATP, düzeltme durumu güncelleştirilir.  

## <a name="prerequisites"></a>Önkoşullar  

**Abonelikleri**:  
- Microsoft Intune  
- Microsoft Defender Gelişmiş tehdit Koruması ([ücretsiz deneme için kaydolun](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink).)  

**ATP'yi Intune yapılandırmaları**:  
- Hizmet bağlantı Microsoft Defender ATP ile yapılandırın.  
- Profil türü olan bir cihaz uyumluluk ilkesini dağıtma **Microsoft Defender ATP (Windows 10 Masaüstü)** ATP tarafından değerlendirilen riski olan cihazlar.
  ATP ile çalışmak için Intune'u ayarlama hakkında daha fazla bilgi için bkz: [ıntune'da koşullu erişim ile Microsoft Defender ATP için uyumluluğu zorlama](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).  

## <a name="work-with-security-tasks"></a>Güvenlik görevler ile çalışma  

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) gidin **cihaz güvenliği** > **güvenlik görevlerini**.  
2. Bu güvenlik görev ek ayrıntıları görüntüler. bir kaynak penceresi açmak için listeden bir görevi'ni seçin.  
3. Güvenlik Görev Kaynak penceresi görüntülerken, ek bağlantılar seçebilirsiniz:  
   - YÖNETİLEN uygulamalar - görünüm savunmasızdır uygulama. Güvenlik Açığı birden fazla uygulama için geçerli olduğu durumlarda, uygulamaların filtrelenmiş bir listesini görürsünüz.  
   - CİHAZLAR - listesini görüntüleme *savunmasız cihazlar*, öğesinden, aracılığıyla, cihazdaki güvenlik açığı için daha fazla ayrıntı içeren bir giriş bağlantı oluşturabilirsiniz.  
   - İstek sahibi - bu güvenlik görevi gönderen yönetici e-posta göndermek için bağlantısını kullanın.  
   - NOTLARI - güvenlik görevi açarken istek sahibi tarafından gönderilen özel iletilerini okuma.  
4. Seçin **kabul** veya **Reddet** planlı eyleminizi ATP'ye bildirim göndermek için. Kabul edin veya görevi reddetme ATP'ye gönderilen notları gönderebilirsiniz.  

5. Bir görev kabul sonra (kapattıysanız) güvenlik görevi yeniden açın ve güvenlik açığı düzeltmek için Düzeltme ayrıntıları izleyin.  Tarafından ATP güvenlik görev ayrıntılarında sağlanan yönergeleri dahil güvenlik bağlı olarak değişir.  

   Bunu yapmak, mümkün olduğunda, Intune konsolunda açık olan ilgili yapılandırma nesneleri bağlantıları düzeltme yönergeleri içerir.  

6. Düzeltme adımları tamamladıktan sonra güvenlik görevi'ni açın ve seçin **görev tamamlanamıyor**.  Bu eylem, hem Intune hem de ATP güvenlik görev durumunu güncelleştirir.  

Düzeltme başarılı olduktan sonra düzeltilen cihazlardan yeni bilgilere dayanarak ATP içinde riskini Etkilenme puanı bırakabilirsiniz. 

## <a name="next-steps"></a>Sonraki Adımlar
Intune hakkında daha fazla bilgi edinin ve [Microsoft Defender ATP](https://docs.microsoft.com/intune/advanced-threat-protection)  
Intune gözden [mobil tehdit savunması](https://docs.microsoft.com/intune/mobile-threat-defense)  
Gözden geçirme [tehdit ve güvenlik açığı Yönetimi Panosu](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) Microsoft Defender ATP içinde
