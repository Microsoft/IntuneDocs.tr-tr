---
title: Windows 10 cihazlarına Microsoft Intune - Azure PowerShell betiklerini ekleyin | Microsoft Docs
description: Oluşturma ve PowerShell betikleri çalıştırma, Azure Active Directory gruplarına betik ilkesi atama, komut dosyalarını izlemek için raporları kullanma ve Windows 10 cihazlarda Microsoft Intune eklediğiniz betikleri silmek için adımlara bakın. Ayrıca, bazı yaygın sorunlar ve çözümleri bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/21/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 469327261b8f617be0851b52d389965c5eff9b59
ms.sourcegitcommit: 464cf677e3746eaba46836dedfb94572a75032f9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58330411"
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

Intune yönetim uzantısı şu önkoşullara sahiptir:

- Cihazlar alanına veya Azure AD ile Azure AD için kayıtlı ve Intune için yapılandırılmış [otomatik kayıt](quickstart-setup-auto-enrollment.md). Intune yönetim uzantısı, Azure AD'ye katılmış destekler, hibrit Azure AD etki alanına katılmamışsa ve kayıtlı Windows cihazları birlikte yönetilir.
- Cihazlar Windows 10 sürüm 1607 veya üzeri çalıştırmalıdır.
- Bir PowerShell Betiği, Intune yönetim uzantısı aracısı yüklü değil veya bir Win32 uygulaması için bir kullanıcı veya cihaz güvenlik grubu olarak dağıtılır.

## <a name="create-a-script-policy"></a>Bir betik ilkesi oluşturma 

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **PowerShell betikleri** > **Ekle**'yi seçin.
3. Aşağıdaki özellikleri girin:
    - **Ad**: PowerShell komut dosyası için bir ad girin. 
    - **Açıklama**: PowerShell Betiği için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir. 
    - **Betik konumu**: PowerShell komut dosyasına göz atın. Betik 200 KB'den düşük (ASCII) olmalıdır.
4. Seçin **yapılandırma**ve aşağıdaki özellikleri girin:
    - **Oturum açmış kimlik bilgilerini kullanarak bu betiği çalıştırın**: Seçin **Evet** betiği cihazda kullanıcının kimlik bilgileriyle çalıştırmak için. Seçin **Hayır** betik sistem bağlamında çalışacak şekilde (varsayılan). Betiğin sistem bağlamında çalıştırılması gerekli değilse **Evet**’i seçin.
    - **Betik imzası denetimini zorla**: Seçin **Evet** durumunda betiğin güvenilir bir yayımcı tarafından imzalanmalıdır. Seçin **Hayır** imzalanması için komut dosyası için bir gereksinim değilse (varsayılan). 
    - **Ana bilgisayarda 64 bit PowerShell komut dosyasını çalıştırmak**: Seçin **Evet** betiği bir 64 bit PowerShell (PS) ana bilgisayar 64 bit istemci mimarisi çalıştırmak için. Seçin **Hayır** (varsayılan), bir 32-bit PowerShell ana bilgisayar betiği çalıştırır.

      Ayarlarken **Evet** veya **Hayır**için aşağıdaki tabloyu yeni kullanın ve mevcut ilke davranışı:

      | Ana bilgisayarda 64-bit PS betiği çalıştırın | İstemci mimarisi | Yeni PS betiği | Var olan bir ilkeyi PS betiği |
      | --- | --- | --- | --- | 
      | Hayır | 32 bit  | desteklenen 32-bit PS konak | 32 bit ve 64-bit mimarilerde düşünülerek yalnızca 32-bit PS konak, çalıştırır. |
      | Evet | 64 bit | 64-bit PS 64-bit mimarilere konağını betiği çalıştırır. 32-bit üzerinde çalışan, bir 32-bit PS ana komut dosyasını çalıştırır. | Komut dosyası, 32-bit PS ana bilgisayarda çalışır. Bu ayar, 64-bit (değil Çalıştır) betiği açılır bir 64-bit PS konak ve raporlarda sonuçları değişirse. 32-bit üzerinde çalışan, 32-bit PS ana komut dosyasını çalıştırır. |

    ![Ekleme ve Intune PowerShell betiklerini kullanma](./media/mgmt-extension-add-script.png)
5. Seçin **Tamam** > **Oluştur** betiği kaydedilemiyor.

## <a name="assign-the-policy"></a>İlke atama

1. **PowerShell betikleri**'nde, atanacak betiği seçin ve daha sonra **Yönet** > **Atamalar**’ı seçin.

    ![Atayın veya PowerShell Betiği Microsoft Intune cihaz grubuna dağıtın](./media/mgmt-extension-assignments.png)

2. Kullanılabilir Azure AD gruplarını listelemek için **Grupları Seç**’i seçin. 
3. Cihazları betiği alacak kullanıcıları içeren bir veya daha fazla grup seçin. İlkeyi seçili gruplara atamak için **seçin**.

> [!NOTE]
> - Son kullanıcılar, cihaza PowerShell betiklerini yürütmek için oturum açmanız gerekmez.
> - Azure AD güvenlik gruplarına cihaz ıntune'da PowerShell betiklerini hedefleyebilir.
> - Azure AD güvenlik gruplarını için ıntune'da PowerShell betiklerini hedefleyebilir.

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

PowerShell betikleri, her oturum açmada çalıştırmayın. Bunlar yalnızca yeniden başlatma sonrasında çalıştırma veya **Microsoft Intune Yönetim Uzantısı** hizmeti yeniden başlatılır. Intune yönetim uzantısı istemci denetimi betiğinde herhangi bir değişiklik veya ıntune ilkesi için saat başına bir kez.

#### <a name="issue-intune-management-extension-doesnt-download"></a>Sorun: Intune yönetim uzantısı indirilmedi

**Olası çözümlemeler**:

- Cihazları Azure AD'ye otomatik olarak kayıtlı olduğundan emin olun. , Cihazda doğrulamak için: 

  1. Git **ayarları** > **hesapları** > **işe veya okula erişim**.
  2. Birleştirilmiş bir hesap seçin > **bilgisi**.
  3. Altında **Gelişmiş tanılama raporu**seçin **rapor oluştur**.
  4. Açık `MDMDiagReport` bir web tarayıcısı ve Git **kayıtlı yapılandırma kaynaklarını** bölümü.
  5. Aranacak **MDMDeviceWithAAD** özelliği. Bu özellik yoksa, Cihazınızı otomatik kayıtlı değil.

    [Windows 10 otomatik kaydı etkinleştirme](windows-enroll.md#enable-windows-10-automatic-enrollment) adımlarını içerir.

#### <a name="issue-powershell-scripts-do-not-run"></a>Sorun: PowerShell betikleri çalıştırma

**Olası çözümlemeler**:

- Intune yönetim uzantısı indirdiğiniz onaylayın `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Betikleri, Surface hub'larında çalışmaz.
- Günlükleri iade `\ProgramData\Microsoft\IntuneManagementExtension\Logs` hataları.
- Olası izin sorunları için PowerShell betiğinin özelliklerinin mutlaka `Run this script using the logged on credentials`. Ayrıca oturum açmış olan kullanıcının komut dosyasını çalıştırmak için uygun izinlere sahip olup olmadığını denetleyin.
- Betik sorunlarını gidermek için bir örnek betiği çalıştırın. Örneğin, oluşturma `C:\Scripts` dizin ve verin herkes tam denetime sahip. Şu betiği çalıştırın:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Başarılı olursa çýktý.txt oluşturulmalı ve "Betik çalışılan" metin içermesi gerekir.

- Betik yürütme Intune olmadan test etmek için komut dosyalarını kullanarak sistem bağlamı altında çalıştırmak [psexec aracı](https://docs.microsoft.com/sysinternals/downloads/psexec) yerel olarak:

  `psexec -i -s`

## <a name="next-steps"></a>Sonraki adımlar

[İzleyici](device-profile-monitor.md) ve [sorun giderme](device-profile-troubleshoot.md) profillerinizi.
