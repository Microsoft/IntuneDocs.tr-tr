---
title: Kılavuzlu senaryolara genel bakış
titleSuffix: Microsoft Intune
description: Microsoft 365 cihaz yönetimi portalında kullanılabilen Intune destekli senaryolar hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b833e5265387637a35bfcdf79f4ae5f37558de61
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839128"
---
# <a name="intune-guided-scenarios-overview"></a>Intune destekli senaryolara genel bakış 

Kılavuzlu senaryo, bir uçtan uca kullanım örneği etrafında ortalanan özelleştirilmiş bir adım serisidir. Yaygın senaryolar, bir yönetici, Kullanıcı veya cihazın kuruluşunuzda oynadığı role dayalıdır. Bu roller genellikle en iyi kullanıcı deneyimini ve güvenliğini sağlamak için dikkatle düzenlenmiş profiller, ayarlar, uygulamalar ve güvenlik denetimleri koleksiyonu gerektirir.    

Belirli bir Intune senaryosunu uygulamak için gereken tüm adımlar ve kaynaklarla ilgili bilgi sahibi değilseniz, Kılavuzlu senaryolar başlangıç noktası olarak kullanılabilir. Kılavuzlu senaryo ilkeleri, uygulamaları, atamaları ve diğer yönetim yapılandırmasını otomatik olarak birleştirir. Ayrıca, Kılavuzlu senaryolar belirtilen senaryo için uygulanabilir veya seyrek olmayan bazı seçenekleri kasıtlı olarak atlayabilir. 

Kılavuzlu senaryolar, Intune 'un normal iş akışlarından farklı bir yönetim alanı değildir. Bu iş akışları, Intune 'un profiller, uygulamalar ve ilkeler için mevcut iş akışlarıyla birlikte kullanılmak üzere tasarlanmıştır. Kılavuzlu bir senaryoyu tamamladıktan sonra, senaryonun gelecekteki tüm yönetimi, ilkeler, uygulamalar ve profiller için mevcut menülerde gerçekleşmelidir. Kılavuzlu senaryo "Kılavuzlu senaryo" kaynak türünü kaydetmez veya kaynaklarda yapılan gelecekteki değişiklikleri izler. Kılavuzlu senaryo tarafından oluşturulan her kaynak ilgili iş yükünde görüntülenir. Kılavuzlu senaryoda atlanan bu seçenekler bile dahil olmak üzere tüm seçenekler, varolan menülerde düzenlenmeye sunulacaktır.  

## <a name="types-of-guided-scenarios"></a>Kılavuzlu senaryo türleri 

Basitlik sağlamak için, tüm Kılavuzlu senaryolar kapsam etiketleri, dışlama grupları ve sanal Grup atamaları gibi karmaşık kapsam özelliklerini atlayın. Bir Kılavuzlu senaryo tarafından oluşturulan tüm kaynaklar, senaryoyu tamamlayan yöneticinin her kapsam etiketini miras alır. Belirli senaryolar, yaygın olarak ilgili senaryoları kapsayan ortak ayar için bir özelleştirme düzeyi sunar. Bu senaryolar, Grup atamasını yalnızca gruplara dahil etmek için destekler. Diğer Kılavuzlu senaryolar için, tüm senaryo hiçbir özelleştirme teklifi sunarak tutarlı bir deneyim sağlar ve tüm atamaları alacak şekilde otomatik olarak yeni bir grup oluşturur. Kılavuzlu senaryo tamamlandıktan sonra, varolan ilke, uygulama ve profil iş yükleri aracılığıyla doğrudan daha gelişmiş atamalar kullanabilirsiniz.  

Aşağıdaki senaryolar Kılavuzlu: 
- Mobil için Microsoft Edge dağıtma 
- Bulut tarafından yönetilen bir BILGISAYAR deneyin
- Mobil için güvenli Microsoft Office 

## <a name="guided-scenario-functionality"></a>Kılavuzlu senaryo işlevselliği 

Kılavuzlu senaryolar belirli işlevleri sunar. Aşağıdaki ayrıntılar, kılavuzlu bir senaryoyu izleyerek yapabileceklerinizi ve yapamadıklarınızı açıklamaya yardımcı olur.

### <a name="launching"></a>Başlatma  

Tüm Kılavuzlu senaryolar **[cihaz yönetim portalından](https://devicemanagement.microsoft.com)**  > , **sorun giderme +** **destekli senaryolar** > destek aracılığıyla kullanılabilir. 

Kılavuzlu senaryo, senaryonun amacını ve kurulumu tamamlaması gereken önkoşulları açıklayan bir giriş ile başlar. Bu noktada, senaryoyu tamamlamaya yönelik tüm gerekli ayrıcalıklara sahip olduğunuzu doğrulamak için yönetici izinleriniz denetlenir.  

Tüm önkoşul denetimleri başarılı olduktan sonra senaryo özelleştirme için uygun ayarları sunar. Kılavuzlu senaryolar yalnızca en az sayıda ayar için giriş gerektirmek ve gerekli veya özel koşullara bağlı olarak sık görülen veya Gelişmiş ayarları gizleyecek şekilde hedeflenir. Her Kılavuzlu senaryo, ek ayrıntılar sağlayan belgelere bağlanır. 

Tüm zorunlu ayarlar girildikten sonra, Kılavuzlu senaryo girilen ayarların ve senaryonun gerektirdiği kaynakların bir özetini sunar. Bu noktada, açıkça belirtilmediği takdirde hiçbir şey kaydedilmez.

Sonraki adım, senaryoyu dağıtmaktır. Bir senaryonun dağıtımı, gerekli tüm kaynakları ve seçili ayarları oluşturur ve kaydeder. Dağıtımı tamamlaması için gereken süre senaryoya göre farklılık gösterir. Dağıtım tamamlandıktan sonra, Kılavuzlu senaryo her bir kaynağın yönetim görünümü, kaynağın normal iş yükü ve belgelerinin bağlantılarıyla oluşturulan kaynakların bir listesini sunar. 

> [!IMPORTANT]
> Kılavuzlu senaryonun sonunda sunulan liste kaydedilmez ve yalnızca Kılavuzlu senaryo açıkken görüntülenebilir.  
Senaryo dağıtımı sırasında bir hata oluşursa, tüm değişiklikler geri alınacaktır. 

### <a name="editing"></a>Düzenleme 

Kılavuzlu senaryolar mevcut kaynakları düzenlemek için kullanılamaz. Oluşturulduktan sonra tüm kaynaklar, gruplar ve atamalar mevcut iş yükleri kullanılarak düzenlenmelidir.

### <a name="monitoring"></a>İzleme 

Kılavuzlu senaryolar, ilk oluşturma işleminden ayrı olarak mevcut kaynakları izlemek için kullanılamaz. Oluşturulduktan sonra tüm kaynakların, grupların ve atamaların mevcut iş yükleri kullanılarak izlenmesi gerekir. 

### <a name="retiring"></a>Bırakarak 

Kılavuzlu senaryolar, ilk dağıtımda hata sırasında otomatik temizliğin dışında, mevcut kaynakları devre dışı bırakmak için kullanılamaz. Oluşturulduktan sonra tüm kaynakların, grupların ve atamaların mevcut iş yükleri kullanılarak Kullanımdan kaldırılmış olması gerekir. 

### <a name="updating"></a>Güncelleniyor

Teknoloji geliştikçe, Intune zaman zaman, kullanıcının deneyimini, güvenliğini veya senaryonun diğer yönlerini geliştirmek üzere kılavuzlu bir senaryoyu güncelleştirebilir. Bu güncelleştirme, yalnızca Kılavuzlu senaryo tarafından yapılan yeni dağıtımları etkiler. Intune, daha önce Kılavuzlu senaryo tarafından oluşturulan mevcut kaynakları, yeni en iyi yöntemler veya önerilere uyacak şekilde güncelleştirmez.  

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Intune hızlı bir şekilde çalıştırmak için, Intune destekli senaryolar aracılığıyla ilerleyin. Intune 'u yeni kullanmaya çalışıyorsanız, [ücretsiz deneme hızlı](free-trial-sign-up.md)başlangıcı ' nı izleyerek Intune kiracınızı ayarlayın.
