---
title: Rapor şifreleme ve BitLocker anahtarlarını Microsoft Intune | Microsoft Intune
description: Bir raporu, cihaz şifreleme durumunu görüntülemek ve Intune portalındaki BitLocker kurtarma anahtarlarını erişebilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 820800deea491c363834a9cafaf077c0992467f6
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394656"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>BitLocker'ı ve cihaz şifreleme izleyin  
Intune, Windows 10 cihazlarınızın şifreleme durumunu belirlemek için merkezi bir konum sağlayan ve BitLocker için önemli bilgiler, Azure Active Directory (Azure AD) bulunan cihazlardan erişim yardımcı olur.  

- [Şifreleme raporu (genel önizlemede)](#encryption-report) cihaz şifreleme durumu ve hazırlık hakkında ayrıntılar sağlar. Rapor ayrıntıları korumak istediğiniz cihazların başarılı şifreleme engelleyen sorunları belirlemenize yardımcı olabilir.  
- [BitLocker'ı ayrıntılarına bakın (genel Önizleme aşamasında)](#bitlocker-recovery-keys) cihazlarınızdan Intune portalındaki anahtarı kimliği ve kurtarma anahtarlarını ister.  

## <a name="encryption-report-in-public-preview"></a>Şifreleme rapora (genel Önizleme)
Windows 10 cihazlarınızın şifreleme durumu hakkındaki ayrıntıları görüntülemek için şifreleme rapor (Pubic Önizleme aşamasında) kullanabilirsiniz.  

Rapora ulaşmak için oturum açın [Intune](https://aka.ms/intuneportal) gidin **cihaz Yapılandırması**ve ardından altındaki *İzleyici*seçin **şifreleme raporu (Önizleme)**.  

### <a name="prerequisites"></a>Önkoşullar:
Şifreleme raporda görünmesi için bir cihaz 1607 veya üzeri sürümü Windows çalıştırmanız gerekir.  

### <a name="report-details"></a>Rapor ayrıntıları
Rapor görüntüler **cihaz adı** her hakkında üst düzey ayrıntılar ve Windows 10 cihazları için:  
- **İşletim sistemi sürümü** – sürümü, Windows.  
- **TPM sürümü** – cihazın Güvenilir Platform Modülü (TPM) yongası sürümü.  
- **Şifreleme hazırlık** BitLocker şifrelemesi desteklemek için cihazları Hazırlık Değerlendirmesi bir. Bir cihaz bir şifreleme durumunu olabilir *şifreli* kendi şifreleme hazırlık olsa bile *hazır değil*, TPM eksik olduğundan.  
- **Şifreleme durumu** – işletim sistemi sürücüsünü şifrelenmiş olsun.  


### <a name="device-encryption-status"></a>Cihaz şifreleme durumu
Bir cihaz seçtiğinizde, Intune görüntüler **cihaz şifreleme durumu** bölmesi.

Bu bölme aşağıdaki ayrıntıları sağlar:  
- **Cihaz adı** – görüntülemekte olduğunuz cihazın adı.  
- **Şifreleme hazırlık** - BitLocker şifrelemesi desteklemek için cihazları Hazırlık Değerlendirmesi bir. Bir cihaz bir şifreleme durumunu olabilir *şifreli* kendi şifreleme hazırlık olsa bile *hazır değil*, TPM eksik olduğundan.  
- **Şifreleme durumu** - işletim sistemi sürücüsünü şifrelenmiş olsun.  
- **Profilleri** – listesini *cihaz Yapılandırması* profilleri bu cihaza uygulanır ve aşağıdaki profil türü ve ayarları içerir:  
    - Profil türü = *uç nokta koruması*  
    - Ayarlar > Windows şifreleme > cihazlar şifreleme = *gerekli*  

  Bu liste bağımsız ilkeleri gözden geçirme için profil durumu özeti sorunlar olduğunu gösteren bulma kullanımda olabilir.  

- **Profil durumu özeti** – bu cihaza uygulama profilleri bir özeti. Özet, tüm geçerli profillerinde en az tercih edilen koşulunu temsil eder. Örneğin, bir profil hatayla sonuçlanırsa, profil durumu özeti görüntülenir *hata*.  
- **Durum ayrıntıları** – Gelişmiş cihazın şifreleme durumu hakkında ayrıntılar. 
  > [!NOTE]  
  > Intune yalnızca gösterir *durumu ayrıntıları* çalıştıran cihazlar için *Windows 10 Nisan 2019 Update* veya üzeri.
  
  Bu alan, algılanabilir her bir ilgili hata bilgilerini görüntüler. Bir cihaz şifreleme hazır olmamasının anlamak için bu bilgileri kullanabilirsiniz.  

  Intune bildirebilirsiniz durumu ayrıntıları örnekleri şunlardır:  

   - BitLocker'ı ilke BitLocker Sürücü Şifrelemesi işletim sistemi birimi şifrelemesi başlatmak için sihirbazını başlatmak için kullanıcı onayı gerektirir, ancak kullanıcı izin vermedi.  
   - İşletim sistemi birimi şifrelemesi yöntemi BitLocker İlkesi eşleşmiyor.  
   - Bir TPM koruyucusu, işletim sistemi birimi korumak BitLocker'ı ilke gerektirir, ancak bir TPM kullanılmaz.  
   - BitLocker İlkesi, işletim sistemi birimi için bir salt TPM koruyucusu gerektirir, ancak TPM koruması kullanılmaz.  
   - BitLocker'ı ilke TPM + PIN koruma için işletim sistemi birimi gerektirir, ancak bir TPM + PIN koruyucusu kullanılmaz.  
   - BitLocker'ı İlkesi, TPM + başlatma gerektiriyor anahtar koruma için işletim sistemi birimi, ancak bir TPM + başlangıç anahtar koruyucusu kullanılmaz.  
   - İşletim sistemi birimi, ancak bir TPM + PIN için BitLocker'ı İlkesi TPM + PIN + başlangıç anahtar koruması gerektiriyor + başlangıç anahtar koruyucusu kullanılmaz.  
   - İşletim sistemi birimi korumasız kalır.  
   - Kurtarma anahtarı yedekleme başarısız oldu.  
   - Bir sabit sürücü korumasız kalır.  
   - Şifreleme yöntemi sabit sürücünün BitLocker İlkesi eşleşmiyor.  
   - Sürücüleri şifrelemek için BitLocker'ı İlkesi yönetici olarak oturum açmak kullanıcının gerektiriyor veya cihazı Azure AD'ye katılır, AllowStandardUserEncryption ilke 1 olarak ayarlanmış olması gerekir.  
   - Windows Kurtarma Ortamı'nı (WinRE) yapılandırılmamış.  
   - BitLocker'ın, TPM kullanılamıyor ya da mevcut değilse, onu kullanılamaz kayıt defterinde yapıldı veya işletim sistemi çıkarılabilir bir sürücüde olduğundan.  
   - TPM'nin BitLocker için hazır değil.  
   - Kurtarma anahtarı yedekleme için gerekli olan ağ kullanılabilir değil.  

## <a name="bitlocker-recovery-keys-in-public-preview"></a>BitLocker kurtarma anahtarları (genel Önizleme)
BitLocker anahtarı kimliği ve kurtarma anahtarlarını, Windows 10 cihazları için gelen Intune portalından görüntüleyebileceğiniz şekilde genel önizleme olarak için BitLocker'ı Azure AD'ye dikey pencere erişim Intune sağlar.  Erişilebilir olması için cihazı Azure AD'ye kalacakları anahtarlarını olmalıdır. 
1. Oturum [Intune](https://aka.ms/intuneportal)Git **cihazları** altındaki *Yönet*seçin **tüm cihazlar**.
2. Bir cihaz seçin listeden ve altında *İzleyici*seçin **kurtarma anahtarlarını – Önizleme**.  
  
Aşağıdaki bilgiler, anahtarları, Azure AD'de kullanılabilir olduğunda kullanılabilir:
- BitLocker anahtar kimliği
- BitLocker kurtarma anahtarı
- Sürücü türü  

Azure AD'de anahtarları değil, Intune görüntüler *Hayır BitLocker anahtarı bulunamadı, bu cihaz için*.  

Bilgi için BitLocker'ı kullanarak elde [BitLocker'ı yapılandırma hizmet sağlayıcısı](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). BitLocker CSP, Windows 10 sürüm 1703 ve üzeri ve Windows 10 Pro sürüm 1809 ve üzeri için desteklenir. 

## <a name="next-steps"></a>Sonraki adımlar
Oluşturma bir [cihaz uyumluluğu](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) BitLocker ve şifreleme yapılandırmak Windows 10 cihazlar için ilke.