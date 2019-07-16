---
title: Microsoft Intune 'de şifreleme raporu ve BitLocker anahtarları
titleSuffix: Microsoft Intune
description: Cihaz şifreleme durumunuz hakkında bir rapor görüntüleyin ve Microsoft Intune portalı içinden BitLocker Kurtarma anahtarlarına erişin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b4c7e4b2d35eb2662ca74660e2133dcd2c89f0a1
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883363"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>BitLocker ve cihaz şifrelemesini izleme  
Intune, Windows 10 cihazlarınızın şifreleme durumunu tanımlamak için merkezi bir konum sağlar ve Azure Active Directory (Azure AD) içinde bulunan cihazlarınızdan BitLocker için önemli bilgilere erişmenize yardımcı olur.  

- [Şifreleme raporu](#encryption-report) , bir cihazın şifreleme durumu ve hazırlığı hakkında ayrıntılı bilgi sağlar. Rapor ayrıntıları, korumak istediğiniz cihazların başarıyla şifrelenmesini önleyen sorunları belirlemenize yardımcı olabilir.  
- Intune portalı içinden cihazlarınızın anahtar KIMLIĞI ve kurtarma anahtarları gibi [BitLocker ayrıntılarını görüntüleyin](#bitlocker-recovery-keys) .  

## <a name="encryption-report"></a>Şifreleme raporu
Windows 10 cihazlarınızın şifreleme durumuyla ilgili ayrıntıları görüntülemek için şifreleme raporunu kullanabilirsiniz.  

Raporu bulmak için [Intune](https://aka.ms/intuneportal) 'Da oturum açın ve **cihaz yapılandırması**' na gidin ve ardından *izleyici*' nin altında **şifreleme raporu**' nu seçin.  

### <a name="prerequisites"></a>Önkoşullar:
Şifreleme raporunda görünmesi için bir cihazın Windows 1607 veya sonraki bir sürümü çalıştırması gerekir.  

### <a name="report-details"></a>Rapor ayrıntıları
Rapor, Windows 10 cihazlarınızın **cihaz adını** ve aşağıdakiler dahil olmak üzere her biri ile ilgili üst düzey ayrıntıları görüntüler:  
- **Işletim sistemi sürümü** – Windows sürümü.  
- **TPM sürümü** : cihazdaki GÜVENILIR Platform Modülü (TPM) yongasının sürümü.  
- **Şifreleme hazırlığı** – cihazların değerlendirilmesi BitLocker şifrelemesini desteklemeye hazır. Cihazlar şu şekilde tanımlanabilir:
  - **Hazırlanıyor**: Cihaz, cihazın TPM olmasını gerektiren ve aşağıdaki Windows 10 sürümü ve SKU gereksinimlerini karşılayan MDM ilkesi kullanılarak şifrelenebilir:
    - Sürüm 1703 veya üzeri, Iş, kurumsal, eğitim
    - Pro 'nun sürüm 1809 veya üzeri  
  
    Daha fazla bilgi için Windows belgelerindeki [BitLocker yapılandırma hizmeti sağlayıcısına (CSP)](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) bakın.  

  - **Hazırlanma**: Cihazın tam şifreleme özellikleri yoktur, ancak yine de şifrelemeyi destekler. Örneğin, cihaz bir kullanıcı tarafından el ile veya bir TMP olmadan şifrelemeye izin vermek üzere ayarlanabilir grup ilkesi aracılığıyla şifrelenmiş olabilir.
  - **Uygulanamaz**: Bu cihazı sınıflandırmak için yeterli bilgi yok.  

- **Şifreleme durumu** – işletim sistemi sürücüsünün şifrelenip şifrelenmediği. 


### <a name="device-encryption-status"></a>Cihaz şifreleme durumu
Bir cihaz seçtiğinizde, Intune **Cihaz şifreleme durumu** bölmesini görüntüler.

Bu bölme aşağıdaki ayrıntıları sağlar:  
- **Cihaz adı** – görüntülemekte olduğunuz cihazın adı.  
- **Şifreleme hazırlığı** -cihazların değerlendirilmesi BitLocker şifrelemesini desteklemeye hazır. TPM olmadığı için, şifreleme hazırlığı *hazır*olmasa bile bir cihazın şifreleme durumu *şifrelenmiş* olabilir. (Daha fazla bilgi için önceki bölümde bulunan şifreleme hazırlığı bölümüne bakın.)
- **Şifreleme durumu** -işletim sistemi sürücüsünün şifreli olup olmadığı. Intune 'un bir cihaz şifreleme durumu veya bu durumdaki bir değişiklik üzerinde raporlamaya başlaması 24 saate kadar sürebilir.  
- **Profiller** : Bu cihaza uygulanan ve aşağıdaki profil türü ve ayarlarını içeren *cihaz yapılandırma* profillerinin bir listesidir:  
  - Profil türü = *Endpoint Protection*  
  - Ayarlar > Windows şifrelemesi > şifreleme cihazları = *gerekli*  

  Bu liste, gözden geçirme için ayrı ilkelerin bulunmasında kullanılabilir ve profil durumu Özeti sorunları belirtir.  

- **Profil durumu Özeti** : Bu cihaza uygulanan profillerin Özeti. Özet, tüm geçerli profillerde en düşük durumu temsil eder. Örneğin, bir profil hata ile sonuçlanırsa, profil durumu özeti *hata*görüntüler.  
- **Durum ayrıntıları** – cihazın şifreleme durumu hakkında gelişmiş ayrıntılar. 
  > [!NOTE]  
  > Intune yalnızca *Windows 10 nisan 2019 güncelleştirme* veya üstünü çalıştıran cihazların *durum ayrıntılarını* gösterir.
  
  Bu alan, algılanabildiği her bir hata için bilgileri görüntüler. Bu bilgileri, bir cihazın neden şifreleme için hazırlanamadığına ilişkin bir neden olduğunu anlamak için kullanabilirsiniz.  

  Intune 'un rapor verebir durum ayrıntıları aşağıda verilmiştir:  

  - BitLocker ilkesi için Kullanıcı onayı 'Nın, işletim sistemi biriminin şifrelemesini başlatmak üzere BitLocker Sürücü Şifrelemesi Sihirbazı 'Nı başlatması gerekir, ancak Kullanıcı onay vermedi.  
  - İşletim sistemi biriminin şifreleme yöntemi BitLocker ilkesiyle eşleşmiyor.  
  - BitLocker, işletim sistemi birimini korumak için bir TPM koruyucusu gerektirir, ancak TPM kullanılmaz.  
  - BitLocker ilkesi, işletim sistemi birimi için salt TPM koruyucusu gerektirir, ancak TPM koruması kullanılmaz.  
  - BitLocker ilkesi, işletim sistemi birimi için TPM + PIN koruması gerektirir, ancak TPM + PIN koruyucusu kullanılmaz.  
  - BitLocker ilkesi, işletim sistemi birimi için TPM + başlangıç anahtarı koruması gerektirir, ancak TPM + başlangıç anahtarı koruyucusu kullanılmaz.  
  - BitLocker ilkesi, işletim sistemi birimi için TPM + PIN + başlangıç anahtarı koruması gerektirir, ancak TPM + PIN + başlangıç anahtarı koruyucusu kullanılmaz.  
  - İşletim sistemi birimi korumasız.  
  - Kurtarma anahtarı yedeklemesi başarısız oldu.  
  - Sabit bir sürücü korumasız.  
  - Sabit sürücünün şifreleme yöntemi BitLocker ilkesiyle eşleşmiyor.  
  - Sürücüleri şifrelemek için BitLocker ilkesi kullanıcının yönetici olarak oturum açmasını ya da cihazın Azure AD 'ye katılmasını gerektiriyorsa, AllowStandardUserEncryption ilkesinin 1 olarak ayarlanması gerekir.  
  - Windows kurtarma ortamı (WinRE) yapılandırılmadı.  
  - TPM, mevcut olmadığı, kayıt defterinde kullanılamaz hale getirilen ya da işletim sistemi çıkarılabilir bir sürücüde olan BitLocker için kullanılamaz.  
  - TPM BitLocker için yok.  
  - Ağ kullanılabilir değil, kurtarma anahtarı yedeklemesi için gereklidir.  

## <a name="bitlocker-recovery-keys"></a>BitLocker kurtarma anahtarları
Intune, Windows 10 cihazlarınızın BitLocker anahtar kimliklerini ve kurtarma anahtarlarını Intune portalından görüntüleyebilmeniz için BitLocker için Azure AD dikey penceresine erişim sağlar.  Erişilebilir olması için cihazın, Azure AD 'ye yönelik anahtarları olması gerekir. 
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihazlar** ' a gidin ve ardından *Yönet*' in altında **tüm cihazlar**' ı seçin.
2. Listeden bir cihaz seçin ve ardından *izleyici*altında **kurtarma anahtarları**' nı seçin.  
  
Azure AD 'de anahtarlar kullanılabilir olduğunda aşağıdaki bilgiler kullanılabilir:
- BitLocker anahtar KIMLIĞI
- BitLocker kurtarma anahtarı
- Sürücü türü  

Anahtarlar Azure AD 'de olmadığında, Intune *Bu cihaz Için hiçbir BitLocker anahtarı bulunamadığını*gösterir.  

BitLocker için bilgi, [BitLocker yapılandırma hizmeti sağlayıcısı](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP) kullanılarak elde edilir. BitLocker CSP, Windows 10 sürüm 1703 ve üzeri sürümlerde ve Windows 10 Pro sürüm 1809 ve üzeri sürümlerde desteklenir. 

## <a name="next-steps"></a>Sonraki adımlar
BitLocker ve şifrelemeyi yapılandırmak için Windows 10 cihazları için bir [cihaz uyumluluk](compliance-policy-create-windows.md) ilkesi oluşturun.
