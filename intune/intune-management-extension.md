---
title: Windows 10 cihazları için Microsoft Intune’da PowerShell betiklerini ekleme - Azure | Microsoft Docs
description: PowerShell betiklerini ekleyin, Azure Active Directory gruplarına betik ilkesi atayın, betikleri izlemek için raporları kullanın ve Microsoft Intune'da Windows 10 cihazlarına eklediğiniz betikleri silme adımlarını görün. Ayrıca, bazı yaygın sorunlar ve çözümleri bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 063a5cbbe18efc5c406c9dc7f2fa40d614b2e48a
ms.sourcegitcommit: d3b1e3fffd3e0229292768c7ef634be71e4736ae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2018
ms.locfileid: "52860971"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme

Intune Yönetim Uzantısı Windows 10 cihazlarda çalıştırmak için ıntune'da PowerShell betiklerini karşıya yüklemek için kullanın. Yönetim Uzantısı Windows 10 mobil cihaz Yönetimi (MDM) geliştirir ve modern yönetime geçiş yapmayı kolaylaştırır.

## <a name="moving-to-modern-management"></a>Modern yönetime geçiş

Son kullanıcı işlemi dijital bir dönüşüm geçiriyor. Klasik, geleneksel BT tek bir cihaz platformu, şirkete ait cihazlar, ofisten çalışan kullanıcılar ve elle gerçekleştirilen çeşitli geriye dönük BT süreçlerine odaklanır. Modern çalışma alanına kullanıcı ve işletme sahibi olan birçok platformda kullanır, kullanıcıların her yerden çalışmasına olanak sağlar ve otomatik ve öngörülü BT süreçleri sunar.

Microsoft Intune gibi MDM Hizmetleri, Windows 10 çalıştıran mobil ve Masaüstü cihazları yönetebilirsiniz. Yerleşik Windows 10 yönetim istemcisi kurumsal yönetim görevlerini çalıştırmak için Intune ile iletişim kurar. Gelişmiş cihaz yapılandırma, sorun giderme ve şu anda Windows 10 mdm'de desteklenmeyen değil eski Win32 uygulama yönetimi gibi gerekebilecek bazı görevler vardır. Bu özellikler için Intune yazılım istemcisi, Windows 10 cihazlarında çalıştırabilirsiniz. [Windows PC'leri bilgisayarlar veya mobil cihazlar olarak yönetmeyi karşılaştırma](pc-management-comparison.md) harika bir kaynaktır.

Intune yönetim uzantısı yerleşik Windows 10 MDM özelliklerini tamamlar. Windows 10 cihazlarda çalışan PowerShell betikleri oluşturabilirsiniz. Örneğin, eski bir Win32 uygulaması yükleyen, betiği Intune'a yükler, betiği bir Azure Active Directory (AD) grubuna atar ve betiği çalıştıran bir PowerShell Betiği oluşturabilirsiniz. Ardından, başlangıçtan bitişe kadar betik çalıştırma durumunu izleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Intune yönetim uzantısı şu önkoşullara sahiptir:

- Cihazları Azure AD'ye katılması gerekir ve [otomatik kaydedilmiş](windows-enroll.md#enable-windows-10-automatic-enrollment). Intune yönetim uzantısı, Azure AD'ye katılmış destekler, karma etki alanına katılmamışsa ve kayıtlı Windows cihazları comanaged. GPO ile kaydedilen cihazlar desteklenmez.
- Cihazlar Windows 10 sürüm 1607 veya üzeri çalıştırmalıdır.
- Bir PowerShell Betiği, Intune yönetim uzantısı aracısı yüklü değil veya bir Win32 uygulaması için bir kullanıcı veya cihaz güvenlik grubu olarak dağıtılır.

## <a name="create-a-powershell-script-policy"></a>PowerShell betik ilkesi oluşturma 

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **PowerShell betikleri** > **Ekle**'yi seçin.
3. PowerShell betiği için **Ad** ve **Açıklama** girin. **Betik konumu** için, PowerShell betiğine göz atın. Betik 200'den küçük olmalıdır KB (ASCII) veya boyut 100 KB (Unicode).
4. **Yapılandır**’ı seçin. Ardından betiği cihazda (**Evet**) veya sistem bağlamında (**Hayır**) kullanıcının kimlik bilgileriyle çalıştırmayı seçin. Varsayılan olarak, betik sistem bağlamında çalıştırılır. Betiğin sistem bağlamında çalıştırılması gerekli değilse **Evet**’i seçin. 
  ![PowerShell betiği ekleme bölmesi](./media/mgmt-extension-add-script.png)
5. Betiğin güvenilir bir yayımcı tarafından imzalanmış olup olmaması gerektiğini seçin (**Evet**). Varsayılan olarak, betiğin imzalanmasına yönelik bir gereksinim yoktur. 
6. **Tamam**’ı ve ardından **Oluştur**’u seçerek betiği kaydedin.

## <a name="assign-a-powershell-script-policy"></a>PowerShell betik ilkesi atama

1. **PowerShell betikleri**'nde, atanacak betiği seçin ve daha sonra **Yönet** > **Atamalar**’ı seçin.

    ![PowerShell Betiği ekleme bölmesi](./media/mgmt-extension-assignments.png)

2. Kullanılabilir Azure AD gruplarını listelemek için **Grupları Seç**’i seçin. 
3. Cihazları betiği alacak kullanıcıları içeren bir veya daha fazla grup seçin. İlkeyi seçili gruplara atamak için **seçin**.

> [!NOTE]
> - PowerShell betikleri, bilgisayar gruplarına uygulanamaz.
> - Son kullanıcılar, cihaza PowerShell betiklerini yürütmek için oturum açmanız gerekmez.
> - Azure AD güvenlik gruplarına cihaz ıntune'da PowerShell betiklerini hedefleyebilir.

Intune yönetim uzantısı istemci saatte ıntune'la denetler. İlkeyi Azure AD gruplarına atadıktan sonra, PowerShell betiği çalıştırılır ve çalıştırma sonuçları raporlanır.

## <a name="monitor-run-status-for-powershell-scripts"></a>PowerShell betikleri için çalıştırma durumunu izleme

Azure portalda kullanıcılar ve cihazlar için PowerShell betiklerinin çalıştırma durumunu izleyebilirsiniz.

**PowerShell betikleri**'nde izlenecek betiği seçin, **İzle**’yi ve ardından şu raporlardan birini seçin:

- **Cihaz durumu**
- **Kullanıcı durumu**

## <a name="troubleshoot-powershell-scripts"></a>PowerShell komut dosyaları sorunlarını giderme

İstemci makinesinde Aracısı günlükleri genellikle içinde `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Kullanabileceğiniz [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) bu günlük dosyalarını görüntülemek. 

![Aracı günlükleri ekran görüntüsü](./media/apps-win32-app-10.png)  

## <a name="delete-a-powershell-script"></a>PowerShell betiğini silme

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

#### <a name="issue-the-powershell-scripts-do-not-run"></a>Sorun: PowerShell betikleri çalıştırma

**Olası çözümlemeler**:

- Intune yönetim uzantısı indirdiğiniz onaylayın `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Betikleri, Surface hub'larında çalışmaz.
- Günlükleri iade `\ProgramData\Microsoft\IntuneManagementExtension\Logs` hataları.
- Olası izin sorunları için PowerShell betiğinin özelliklerinin mutlaka `Run this script using the logged on credentials`. Ayrıca oturum açmış olan kullanıcının komut dosyasını çalıştırmak için uygun izinlere sahip olup olmadığını denetleyin.
- Betik sorunlarını gidermek için bir örnek betiği çalıştırın. Örneğin, oluşturma `C:\Scripts` dizin ve verin herkes tam denetime sahip. Aşağıdaki betiği çalıştırın:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Başarılı olursa çýktý.txt oluşturulmalı ve "Betik çalışılan" metin içermesi gerekir.

- Betik yürütme Intune olmadan test etmek için komut dosyalarını kullanarak sistem bağlamı altında çalıştırmak [psexec aracı](https://docs.microsoft.com/sysinternals/downloads/psexec) yerel olarak:

  `psexec -i -s`

## <a name="next-steps"></a>Sonraki adımlar

[İzleyici](device-profile-monitor.md) ve [sorun giderme](device-profile-troubleshoot.md) profillerinizi.
