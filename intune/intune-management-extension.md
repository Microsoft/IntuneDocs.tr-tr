---
title: Windows 10 cihazlarına Microsoft Intune - Azure PowerShell betiklerini ekleyin | Microsoft Docs
description: Oluşturma ve PowerShell betikleri çalıştırma, Azure Active Directory gruplarına betik ilkesi atama, komut dosyalarını izlemek için raporları kullanma ve Windows 10 cihazlarda Microsoft Intune eklediğiniz betikleri silmek için adımlara bakın. Ayrıca, bazı yaygın sorunlar ve çözümleri bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 967398516cdc2f727aa517fed3c8cf65810a38a1
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251217"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Windows 10 cihazlarda ıntune'da PowerShell betiklerini kullanın

Microsoft Intune Yönetim Uzantısı Windows 10 cihazlarda çalıştırmak için ıntune'da PowerShell betiklerini karşıya yüklemek için kullanın. Yönetim Uzantısı Windows 10 mobil cihaz Yönetimi (MDM) geliştirir ve modern yönetime geçiş yapmayı kolaylaştırır.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri

## <a name="move-to-modern-management"></a>Modern yönetime geçiş

Son kullanıcı işlemi dijital bir dönüşüm geçiriyor. Tek bir cihaz platformu, iş şirketinize ait cihazlar, office ve farklı el ile reaktif BT işlemleri çalışan kullanıcılar Klasik, geleneksel BT odaklanılmıştır. Modern çalışma alanına kullanıcı ve işletme sahibi olan birçok platformda kullanır, kullanıcıların her yerden çalışmasına olanak sağlar ve otomatik ve öngörülü BT süreçleri sunar.

Microsoft Intune gibi MDM Hizmetleri, Windows 10 çalıştıran mobil ve Masaüstü cihazları yönetebilirsiniz. Yerleşik Windows 10 yönetim istemcisi kurumsal yönetim görevlerini çalıştırmak için Intune ile iletişim kurar. Gelişmiş cihaz yapılandırma ve sorun giderme gibi gerekebilecek bazı görevler vardır. Win32 uygulama yönetimi için kullandığınız [Win32 Uygulama Yönetimi](apps-win32-app-management.md) Windows 10 cihazlarınızda özelliği.

Intune yönetim uzantısı yerleşik Windows 10 MDM özelliklerini tamamlar. Windows 10 cihazlarda çalışan PowerShell betikleri oluşturabilirsiniz. Örneğin, Gelişmiş cihaz yapılandırmaları, betiği Intune'a yükler, betiği bir Azure Active Directory (AD) grubuna atar ve betiği çalıştıran bir PowerShell Betiği oluşturabilirsiniz. Ardından, başlangıçtan bitişe kadar betik çalıştırma durumunu izleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Intune yönetim uzantısı, aşağıdaki önkoşulları vardır. Bunlar sağlandığında, Intune yönetim uzantısı otomatik olarak bir PowerShell Betiği çalıştırılamadığında yüklü değil veya Win32 uygulaması, kullanıcı veya cihaza atanır.

- Windows 10 sürüm 1607 veya üzerini çalıştıran cihazlar. Kullanarak cihaz kaydedilirse [toplu otomatik kayıt](windows-bulk-enroll.md), 1703 veya daha sonra cihazları Windows 10 sürümü çalıştırması gerekir. Intune yönetim uzantısı olmayan mağaza uygulamaları çalıştıran S modu izin vermediğinden üzerinde Windows 10 S modunda desteklenmez. 
  
- Azure Active Directory'ye (AD) katılmış cihazlar da dahil olmak üzere:  
  
  - Hibrit Azure AD'ye katılmış: Azure Active Directory (AD) alanına katılmış ve ayrıca katılmış cihazların şirket içi Active Directory (AD). Bkz: [hibrit Azure Active Directory join sürecinizi planlamak](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) Kılavuzu.

- Intune'a kayıtlı cihazlar da dahil olmak üzere:

  - Grup İlkesi'nde (GPO) kayıtlı cihazlar. Bkz: [Grup İlkesi kullanarak otomatik olarak bir Windows 10 cihazını kaydetme](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) Kılavuzu.
  
  - El ile hangi olduğunda, Intune'a kayıtlı cihazlar:
  
    - [Intune otomatik kayıt](quickstart-setup-auto-enrollment.md) Azure AD'de etkinleştirilir. Son kullanıcı cihazda yerel bir kullanıcı hesabı kullanarak oturum açtığında, cihazın Azure AD'ye el ile birleştirir ve ardından cihaza kendi Azure AD hesabını kullanarak oturum açtığında.
    
    OR  
    
    - Kullanıcı cihazda kullanıcı Azure AD hesabı kullanarak oturum açtığında ve ardından Intune'a kaydedilir.

  - Configuration Manager ve Intune kullanan ortak yönetilen cihazlar. Bkz: [ortak yönetim nedir](https://docs.microsoft.com/sccm/comanage/overview) Kılavuzu.

> [!TIP]
> Cihazlardır mutlaka [katılmış](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) Azure AD'ye. Yalnızca cihazlar [kayıtlı](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) Azure AD'de betiklerinizi almazsınız.

## <a name="create-a-script-policy"></a>Bir betik ilkesi oluşturma 

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **PowerShell betikleri** > **Ekle**'yi seçin.
3. Aşağıdaki özellikleri girin:
    - **Ad**: PowerShell komut dosyası için bir ad girin. 
    - **Açıklama**: PowerShell Betiği için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir. 
    - **Betik konumu**: PowerShell komut dosyasına göz atın. Betik 200 KB'den düşük (ASCII) olmalıdır.
4. Seçin **yapılandırma**ve aşağıdaki özellikleri girin:
    - **Oturum açmış kimlik bilgilerini kullanarak bu betiği çalıştırın**: Seçin **Evet** betiği cihazda kullanıcının kimlik bilgileriyle çalıştırmak için. Seçin **Hayır** betik sistem bağlamında çalışacak şekilde (varsayılan). Birçok yönetici seçin **Evet**. Betik sistem bağlamında çalıştırılması gerekiyorsa, seçin **Hayır**.
    - **Betik imzası denetimini zorla**: Seçin **Evet** durumunda betiğin güvenilir bir yayımcı tarafından imzalanmalıdır. Seçin **Hayır** imzalanması için komut dosyası için bir gereksinim değilse (varsayılan). 
    - **Ana bilgisayarda 64 bit PowerShell komut dosyasını çalıştırmak**: Seçin **Evet** betiği bir 64 bit PowerShell (PS) ana bilgisayar 64 bit istemci mimarisi çalıştırmak için. Seçin **Hayır** (varsayılan), bir 32-bit PowerShell ana bilgisayar betiği çalıştırır.

      Ayarlarken **Evet** veya **Hayır**için aşağıdaki tabloyu yeni kullanın ve mevcut ilke davranışı:

      | Ana bilgisayarda 64-bit PS betiği çalıştırın | İstemci mimarisi | Yeni PS betiği | Var olan bir ilkeyi PS betiği |
      | --- | --- | --- | --- | 
      | Hayır | 32 bit  | desteklenen 32-bit PS konak | 32 bit ve 64-bit mimarilerde düşünülerek yalnızca 32-bit PS konak, çalıştırır. |
      | Evet | 64 bit | 64-bit PS 64-bit mimarilere konağını betiği çalıştırır. 32-bit üzerinde çalışan, bir 32-bit PS ana komut dosyasını çalıştırır. | Komut dosyası, 32-bit PS ana bilgisayarda çalışır. Bu ayar, 64-bit (değil Çalıştır) betiği açılır bir 64-bit PS konak ve raporlarda sonuçları değişirse. 32-bit üzerinde çalışan, 32-bit PS ana komut dosyasını çalıştırır. |

    ![Ekleme ve Intune PowerShell betiklerini kullanma](./media/mgmt-extension-add-script.png)
5. Seçin **Tamam** > **Oluştur** betiği kaydedilemiyor.

> [!NOTE]
> Betikleri kullanıcı bağlamı için ayarlanır ve son kullanıcı, varsayılan olarak yönetici haklarına sahip olduğunda, PowerShell betiğini yönetici ayrıcalığı altında çalışır.

## <a name="assign-the-policy"></a>İlke atama

1. **PowerShell betikleri**'nde, atanacak betiği seçin ve daha sonra **Yönet** > **Atamalar**’ı seçin.

    ![Atayın veya PowerShell Betiği Microsoft Intune cihaz grubuna dağıtın](./media/mgmt-extension-assignments.png)

2. Kullanılabilir Azure AD gruplarını listelemek için **Grupları Seç**’i seçin. 
3. Cihazları betiği alacak kullanıcıları içeren bir veya daha fazla grup seçin. İlkeyi seçili gruplara atamak için **seçin**.

> [!NOTE]
> - Son kullanıcılar, cihaza PowerShell betiklerini yürütmek için oturum açmanız gerekmez.
> - Azure AD cihaz güvenlik gruplarını veya Azure AD güvenlik gruplarını ıntune'da PowerShell betiklerini hedefleyebilir.

Intune yönetim uzantısı istemci saatte bir denetler ve yeni komut dosyaları veya değişiklikler için Intune ile her bir yeniden başlatma işleminden sonra. İlkeyi Azure AD gruplarına atadıktan sonra, PowerShell betiği çalıştırılır ve çalıştırma sonuçları raporlanır. Betiğini yürütür sonra olmadığı sürece betik veya ilke değişikliği yeniden yürütülmez.

## <a name="monitor-run-status"></a>Çalıştırma durumu İzleyicisi

Azure portalda kullanıcılar ve cihazlar için PowerShell betiklerinin çalıştırma durumunu izleyebilirsiniz.

**PowerShell betikleri**'nde izlenecek betiği seçin, **İzle**’yi ve ardından şu raporlardan birini seçin:

- **Cihaz durumu**
- **Kullanıcı durumu**

## <a name="troubleshoot-scripts"></a>Komut dosyaları sorunlarını giderme

İstemci makinesinde Aracısı günlükleri genellikle içinde `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Kullanabileceğiniz [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) bu günlük dosyalarını görüntülemek. 

![Ekran görüntüsünü veya örnek cmtrace aracı Intune günlüğe kaydeder.](./media/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Bir betik Sil

**PowerShell betikleri**'nde, betiği sağ tıklayın ve **Sil**'i seçin.

## <a name="common-issues-and-resolutions"></a>Genel sorunlar ve çözümleri

#### <a name="issue-intune-management-extension-doesnt-download"></a>Sorun: Intune yönetim uzantısı indirilmedi

**Olası çözümlemeler**:

- Cihaz Azure AD'ye katılmış değil. Cihazların karşıladığından emin olun [önkoşulları](#prerequisites) (Bu makaledeki). 
- PowerShell betikleri veya kullanıcıya veya cihaza ait gruplara atanan Win32 uygulamaları yoktur.
- Cihaz Intune hizmetiyle hiç internet erişimi nedeniyle Windows anında bildirim Hizmetleri (WNS) ve benzeri erişimi iade edilemez.
- Cihaz S modundadır. Intune yönetim uzantısı S modunda çalıştıran cihazlarda desteklenmez. 

Cihazın otomatik olarak kayıtlı olup olmadığını görmek için şunları yapabilirsiniz:

  1. Git **ayarları** > **hesapları** > **işe veya okula erişim**.
  2. Birleştirilmiş bir hesap seçin > **bilgisi**.
  3. Altında **Gelişmiş tanılama raporu**seçin **rapor oluştur**.
  4. Açık `MDMDiagReport` bir web tarayıcısında.
  5. Arama **MDMDeviceWithAAD** özelliği. Özellik varsa, otomatik olarak kayıtlı cihazdır. Bu özellik mevcut değilse, cihaz otomatik olarak kayıtlı değil.

[Windows 10 otomatik kaydı etkinleştirme](windows-enroll.md#enable-windows-10-automatic-enrollment) Intune otomatik kayıt yapılandırma adımlarını içerir.

#### <a name="issue-powershell-scripts-do-not-run"></a>Sorun: PowerShell betikleri çalıştırma

**Olası çözümlemeler**:

- PowerShell betikleri, her oturum açmada çalıştırmayın. Bunlar çalıştırın:

  - Bir cihaza komut atandığında
  - Komut dosyasını değiştirirseniz, karşıya yükleme ve komut dosyası için bir kullanıcı veya cihaz atama
  
    > [!TIP]
    > **Microsoft Intune Yönetim Uzantısı** cihaz çalışır (services.msc) Hizmetleri uygulamasında listelenmesini hizmet gibi bir hizmettir. Bir cihaz yeniden başlatıldıktan sonra bu hizmet de yeniden başlatın ve Intune hizmetine atanan tüm PowerShell betikleri için denetleyin. Varsa **Microsoft Intune Yönetim Uzantısı** hizmetini el ile olarak ayarlayın ve ardından cihaz yeniden başlatıldıktan sonra hizmet yeniden başlatılamayabilir.

- Cihazlardır mutlaka [Azure AD'ye katılmış](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Yalnızca, çalışma alanına veya kuruluşunuz katılmış cihazları ([kayıtlı](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) Azure AD'de) betikleri almazsınız.
- Intune yönetim uzantısı istemci betiği herhangi bir değişiklik veya ıntune ilkesi için saat başına bir kez denetler.
- Intune yönetim uzantısı indirdiğiniz onaylayın `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Betikler, Surface hub'ları veya Windows 10 S modunda çalışmıyor.
- Hatalar için günlükleri gözden geçirin. Bkz: [komut dosyaları sorunlarını giderme](#troubleshoot-scripts) (Bu makaledeki).
- Olası izin sorunları için PowerShell betiğinin özelliklerinin mutlaka `Run this script using the logged on credentials`. Ayrıca oturum açmış olan kullanıcının komut dosyasını çalıştırmak için uygun izinlere sahip olup olmadığını denetleyin.

- Betik sorunlarını gidermek için aşağıdakileri yapın:

  - Cihazlarınızda PowerShell yürütme yapılandırmasını gözden geçirin. Bkz: [PowerShell yürütme İlkesi](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) Kılavuzu.
  - Intune yönetim uzantısı kullanarak bir örnek betiği çalıştırın. Örneğin, oluşturma `C:\Scripts` dizin ve verin herkes tam denetime sahip. Şu betiği çalıştırın:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Başarılı olursa çýktý.txt oluşturulmalı ve "Betik çalışılan" metin içermesi gerekir.

  - Betik yürütme Intune olmadan test etmek için sistem hesabı kullanarak komut dosyalarını çalıştırmak [psexec aracı](https://docs.microsoft.com/sysinternals/downloads/psexec) yerel olarak:

    `psexec -i -s`

## <a name="next-steps"></a>Sonraki adımlar

[İzleyici](device-profile-monitor.md) ve [sorun giderme](device-profile-troubleshoot.md) profillerinizi.
