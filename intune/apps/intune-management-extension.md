---
title: Microsoft Intune-Azure 'da Windows 10 cihazlarına PowerShell betikleri ekleme | Microsoft Docs
description: PowerShell betikleri oluşturup çalıştırın, betik ilkesini Azure Active Directory gruplara atayın, betikleri izlemek için raporları kullanın ve Microsoft Intune Windows 10 cihazlarına eklediğiniz betikleri silme adımlarını görün. Ayrıca bkz. bazı yaygın sorunlar ve çözümleri.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8af7a756d95051be52a5380467cb4f9be2533b3
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78369364"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Intune 'da Windows 10 cihazlarında PowerShell betikleri kullanma

Windows 10 cihazlarında çalıştırmak için Intune 'da PowerShell betiklerini karşıya yüklemek üzere Microsoft Intune Management uzantısını kullanın. Yönetim uzantısı Windows 10 mobil cihaz yönetimini (MDM) geliştirir ve modern yönetime taşımayı kolaylaştırır.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri

## <a name="move-to-modern-management"></a>Modern yönetime taşı

Son kullanıcı işlemi dijital bir dönüşüm geçiriyor. Klasik, geleneksel BT tek bir cihaz platformuna, işe ait cihazlara, Office 'ten çalışan kullanıcılara ve farklı el ile, BT süreçlerine odaklanır. Modern çalışma alanı, Kullanıcı ve işletmeye ait olan birçok platformu kullanır, kullanıcıların her yerden çalışmasına olanak sağlar ve otomatik ve proaktif BT süreçlerini sağlar.

Microsoft Intune gibi MDM Hizmetleri, Windows 10 çalıştıran mobil ve masaüstü cihazlarını yönetebilir. Yerleşik Windows 10 yönetim istemcisi, kurumsal yönetim görevlerini çalıştırmak için Intune ile iletişim kurar. Gelişmiş cihaz yapılandırması ve sorun giderme gibi bazı görevler de gerekebilir. Win32 uygulama yönetimi için Windows 10 cihazlarınızda [Win32 uygulama yönetimi](app-management.md) özelliğini kullanabilirsiniz.

Intune yönetim uzantısı, yerleşik Windows 10 MDM özelliklerini tamamlar. Windows 10 cihazlarında çalıştırmak için PowerShell betikleri oluşturabilirsiniz. Örneğin, gelişmiş cihaz yapılandırması yapan bir PowerShell betiği oluşturun. Ardından, betiği Intune 'a yükleyin, betiği bir Azure Active Directory (AD) grubuna atayın ve betiği çalıştırın. Sonra, başlangıçtan sona kadar betiğin çalışma durumunu izleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Intune yönetim uzantısında aşağıdaki Önkoşullar bulunur. Önkoşullar karşılandıktan sonra, Kullanıcı veya cihaza bir PowerShell betiği veya Win32 uygulaması atandığında Intune yönetim uzantısı otomatik olarak yüklenir.

- Windows 10 sürüm 1607 veya üstünü çalıştıran cihazlar. Cihaz [toplu otomatik kayıt](../enrollment/windows-bulk-enroll.md)kullanılarak kaydedildiyse, cihazların Windows 10 sürüm 1703 veya üstünü çalıştırması gerekir. S modu, mağaza dışı uygulamaların çalıştırılmasına izin vermediğinden, Intune yönetim uzantısı Windows 10 ' da desteklenmez. 
  
- Azure Active Directory (AD) 'ye katılmış cihazlar, şunlar dahil:  
  
  - Karma Azure AD 'ye katılmış: Azure Active Directory (AD) ve ayrıca şirket içi Active Directory (AD) ile birleştirilmiş cihazlar. Kılavuz için bkz. [karma Azure Active Directory JOIN Uygulamanızı planlayın](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) .

- Intune 'a kayıtlı cihazlar, şunlar dahil:

  - Bir Grup ilkesine (GPO) kayıtlı cihazlar. Kılavuza yönelik [Grup İlkesi kullanarak Windows 10 cihazını otomatik olarak kaydetme](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) konusuna bakın.
  
  - Intune 'a el ile kaydedilen cihazlar şu durumlarda yapılır:
  
    - Azure AD 'de [Intune 'A otomatik kayıt](../enrollment/quickstart-setup-auto-enrollment.md) etkinleştirilir. Son Kullanıcı, yerel bir kullanıcı hesabı kullanarak cihazda oturum açar, cihazı Azure AD 'ye el ile birleştirir ve sonra Azure AD hesabını kullanarak cihazda oturum açar.
    
    VEYA  
    
    - Kullanıcı, Azure AD hesabını kullanarak cihazda oturum açar ve ardından Intune 'da kaydolur.

  - Configuration Manager ve Intune kullanan ortak yönetilen cihazlar. **Uygulamalar** Iş yükünün **pilot Intune** veya **Intune**olarak ayarlandığından emin olun. Rehberlik için aşağıdaki makalelere bakın: 
  
    - [Ortak yönetim nedir?](https://docs.microsoft.com/configmgr/comanage/overview) 
    - [İstemci uygulamaları iş yükü](https://docs.microsoft.com/configmgr/comanage/workloads#client-apps)
    - [Configuration Manager iş yüklerini Intune 'a değiştirme](https://docs.microsoft.com/configmgr/comanage/how-to-switch-workloads)
  
> [!TIP]
> Cihazların Azure AD 'ye [katılmış](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) olduğundan emin olun. Yalnızca Azure AD 'de [kayıtlı](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) olan cihazlar betiklerinizi almaz.

## <a name="create-a-script-policy-and-assign-it"></a>Betik ilkesi oluşturma ve atama

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Ekle** > **PowerShell betikleri** > **cihazları** seçin.

    ![Microsoft Intune PowerShell betikleri ekleme ve kullanma](./media/intune-management-extension/mgmt-extension-add-script.png)

3. **Temel bilgiler**bölümünde aşağıdaki özellikleri girin ve **İleri**' yi seçin:
    - **Ad**: PowerShell betiği için bir ad girin. 
    - **Açıklama**: PowerShell betiği için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
4. **Betik ayarları**' nda aşağıdaki özellikleri girin ve **İleri**' yi seçin:
    - **Betik konumu**: PowerShell betiğine gidin. Komut dosyası 200 KB 'tan (ASCII) az olmalıdır.
    - **Bu betiği oturum açmış olan kimlik bilgilerini kullanarak Çalıştır**: betiği, kullanıcının cihazdaki kimlik bilgileriyle çalıştırmak için **Evet** ' i seçin. Betiği sistem bağlamında çalıştırmak için **Hayır** (varsayılan) seçeneğini belirleyin. Birçok yönetici **Evet**' i seçer. Komut dosyasının sistem bağlamında çalışması gerekiyorsa, **Hayır**' ı seçin.
    - **Betik Imzasını zorla denetimi**: betiğin güvenilir bir yayımcı tarafından Imzalanması gerekiyorsa **Evet** ' i seçin. Betiğin imzalanması için bir gereksinim yoksa **Hayır** (varsayılan) seçeneğini belirleyin. 
    - **Betiği 64-bit PowerShell konağında Çalıştır**: betiği, 64 bit istemci mimarisinde 64 bit POWERSHELL (PS) konağında çalıştırmak için **Evet** ' i seçin. **Hayır** (varsayılan) seçeneğini belirleyin, betiği 32 bitlik bir PowerShell ana bilgisayarında çalıştırır.

      **Evet** veya **Hayır**olarak ayarlandığında, yeni ve mevcut ilke davranışı için aşağıdaki tabloyu kullanın:

      | Betiği 64-bit PS konağında Çalıştır | İstemci mimarisi | Yeni PS betiği | Mevcut ilke PS betiği |
      | --- | --- | --- | --- | 
      | Hayır | 32 bit:  | 32-bit PS Konağı destekleniyor | Yalnızca 32 bit ve 64 bit mimarilerinde çalışan 32-bit PS ana bilgisayarında çalışır. |
      | Evet | 64 bit | 64-bit mimariler için 64-bit PS konağında betiği çalıştırır. 32 bit üzerinde çalıştırıldığında, betik bir 32 bit PS konağında çalışır. | Betiği 32 bit PS ana bilgisayarında çalıştırır. Bu ayar 64 bit olarak değişirse, betik bir 64 bit PS konağında açılır (çalışmaz) ve sonuçları raporlar. 32 bit üzerinde çalıştırıldığında, betik 32-bit PS ana bilgisayarında çalışır. |

5. **Kapsam etiketlerini**seçin. Kapsam etiketleri isteğe bağlıdır. [Dağıtım için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketlerini kullanma](../fundamentals/scope-tags.md) daha fazla bilgi içerir.

    Kapsam etiketi eklemek için:

    1. **Kapsam etiketlerini Seç** ' i seçin > listeden var olan bir kapsam etiketi seçin > **seçin**.

    2. İşiniz bittiğinde **İleri**' yi seçin.

6. **Atamaları** seçin > **Eklenecek grupları**seçin. Mevcut bir Azure AD grupları listesi gösteriliyor.

    1. Cihazları betiği alan kullanıcıları içeren bir veya daha fazla grup seçin. **Seçin** öğesini belirleyin. Seçtiğiniz gruplar listede gösterilir ve ilkenize gönderilir.

        > [!NOTE]
        > Intune 'daki PowerShell betikleri Azure AD cihaz güvenlik gruplarını veya Azure AD Kullanıcı güvenlik gruplarını hedefleyebilir.

    2. **İleri**'yi seçin.

        ![Microsoft Intune PowerShell betiğini atama veya cihaz gruplarına dağıtma](./media/intune-management-extension/mgmt-extension-assignments.png)

7. **İnceleme + Ekle**' de, yapılandırdığınız ayarların bir özeti gösterilir. Betiği kaydetmek için **Ekle** ' yi seçin. **Ekle**' yi seçtiğinizde, ilke seçtiğiniz gruplara dağıtılır.

## <a name="important-considerations"></a>Önemli noktalar

- Betikler Kullanıcı bağlamı olarak ayarlandığında ve son kullanıcının yönetici hakları varsa, varsayılan olarak, PowerShell betiği yönetici ayrıcalığıyla çalışır.

- PowerShell betiklerini yürütmek için son kullanıcıların cihazda oturum açması gerekmez.

- Intune yönetim uzantısı istemcisi her saatte bir kez ve her yeni komut dosyası veya değişiklik için her yeniden başlatmanın ardından Intune 'u denetler. İlkeyi Azure AD gruplarına atadıktan sonra, PowerShell betiği çalıştırılır ve çalıştırma sonuçları raporlanır. Betik yürütüldükten sonra, betikte veya ilkede bir değişiklik olmadıkça yeniden yürütülmez.

## <a name="monitor-run-status"></a>Çalışma durumunu izle

Azure portalda kullanıcılar ve cihazlar için PowerShell betiklerinin çalıştırma durumunu izleyebilirsiniz.

**PowerShell betikleri**'nde izlenecek betiği seçin, **İzle**’yi ve ardından şu raporlardan birini seçin:

- **Cihaz durumu**
- **Kullanıcı durumu**

## <a name="intune-management-extension-logs"></a>Intune yönetim uzantısı günlükleri

İstemci makinesindeki Aracı günlükleri genellikle `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Bu günlük dosyalarını görüntülemek için [CMTrace. exe](https://docs.microsoft.com/configmgr/core/support/cmtrace) ' yi kullanabilirsiniz.

![Microsoft Intune ekran görüntüsü veya örnek CMTrace Aracısı günlükleri](./media/apps-win32-app-management/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Betiği silme

**PowerShell betikleri**'nde, betiği sağ tıklayın ve **Sil**'i seçin.

## <a name="common-issues-and-resolutions"></a>Yaygın sorunlar ve çözümleri

### <a name="issue-intune-management-extension-doesnt-download"></a>Sorun: Intune yönetim uzantısı indirmiyor

**Olası çözümler**:

- Cihaz Azure AD 'ye katılmadı. Cihazların [önkoşulları](#prerequisites) karşıladığından emin olun (Bu makalede). 
- Kullanıcı veya cihazın ait olduğu gruplara atanmış bir PowerShell komut dosyası veya Win32 uygulaması yok.
- İnternet erişimi olmadığından, Windows anında Iletme Bildirim Hizmetleri (WNS) ve benzeri bir erişim olmadığından cihaz Intune hizmetini iade edemiyor.
- Cihaz, S modunda. Intune yönetim uzantısı, S modunda çalışan cihazlarda desteklenmez. 

Cihazın otomatik olarak kayıtlı olup olmadığını görmek için şunları yapabilirsiniz:

  1. **İş veya okula erişim** > **Ayarlar** > **hesaplar** ' a gidin.
  2. Birleşik hesap > **bilgilerini**seçin.
  3. **Gelişmiş tanılama raporu**altında **rapor oluştur**' u seçin.
  4. `MDMDiagReport` bir Web tarayıcısında açın.
  5. **Mdmdevicewithaad** özelliğini arayın. Özellik varsa, cihaz otomatik olarak kaydedilir. Bu özellik yoksa, cihaz otomatik olarak kayıtlı değildir.

[Windows 10 otomatik kaydını etkinleştir](../enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) ayarı, Intune 'da otomatik kayıt yapılandırma adımlarını içerir.

### <a name="issue-powershell-scripts-do-not-run"></a>Sorun: PowerShell betikleri çalışmıyor

**Olası çözümler**:

- PowerShell betikleri, her oturum açma sırasında çalışmaz. Şunları çalıştırırlar:

  - Betik bir cihaza atandığında
  - Betiği değiştirir, yükleyin ve betiği bir kullanıcıya veya cihaza atayın
  
    > [!TIP]
    > **Microsoft Intune Yönetimi Uzantısı** , Hizmetler uygulamasında (Services. msc) listelenen diğer tüm hizmetlerde olduğu gibi, cihazda çalışan bir hizmettir. Bir cihaz yeniden başlatıldıktan sonra, bu hizmet de yeniden başlatılabilir ve Intune hizmeti ile atanmış PowerShell betiklerini denetleyebilir. **Microsoft Intune yönetim uzantısı** hizmeti el ile olarak ayarlandıysa, cihaz yeniden başlatıldıktan sonra hizmet yeniden başlatılamayabilir.

- Cihazların [Azure AD 'ye katılmış](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)olduğundan emin olun. Yalnızca çalışma alanınıza veya kuruluşunuza (Azure AD 'ye[kayıtlı](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) ) katılmış olan cihazlar betikleri almaz.
- Intune yönetim uzantısı istemcisi, Intune 'da betikteki veya ilkedeki değişiklikler için saatte bir kez kontrol eder.
- Intune yönetim uzantısının `%ProgramFiles(x86)%\Microsoft Intune Management Extension`için yüklendiğini onaylayın.
- Betikler, Surface Hub 'Larda veya Windows 10 ' da S modunda çalışmaz.
- Tüm hatalar için günlükleri gözden geçirin. Bkz. [Intune yönetim uzantısı günlükleri](#intune-management-extension-logs) (Bu makalede).
- Olası izin sorunları için, PowerShell betiğinin özelliklerinin `Run this script using the logged on credentials`olarak ayarlandığından emin olun. Ayrıca, oturum açan kullanıcının betiği çalıştırmak için uygun izinlere sahip olup olmadığını denetleyin.

- Betik sorunlarını yalıtmak için şunları yapabilirsiniz:

  - Cihazlarınızda PowerShell yürütme yapılandırmasını gözden geçirin. Rehberlik için [PowerShell yürütme ilkesine](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) bakın.
  - Intune yönetim uzantısını kullanarak bir örnek komut dosyası çalıştırın. Örneğin, `C:\Scripts` dizini oluşturun ve herkese tam denetim verin. Şu betiği çalıştırın:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Başarılı olursa output. txt oluşturulmalıdır ve "betiği çalıştı" metnini içermelidir.

  - Betik yürütmeyi Intune olmadan test etmek için, [PsExec aracını](https://docs.microsoft.com/sysinternals/downloads/psexec) yerel olarak kullanarak sistem hesabındaki betikleri çalıştırın:

    `psexec -i -s`  
    
  - Betik başarılı olduğunu bildirirse ancak gerçekten başarılı olmadıysa, virüsten koruma hizmetiniz korumalı alana alma Me Texecutor olabilir. Aşağıdaki komut, Intune 'da her zaman bir hata bildirir. Test olarak, bu betiği kullanabilirsiniz:
  
    ```powershell
    Write-Error -Message "Forced Fail" -Category OperationStopped
    mkdir "c:\temp" 
    echo "Forced Fail" | out-file c:\temp\Fail.txt
    ```

    Betik bir başarı bildirirse, hata çıktısını onaylamak için `AgentExecutor.log` bakın. Betik yürütülüyorsa, uzunluk > 2 olmalıdır.

  - . Error ve. Output dosyalarını yakalamak için aşağıdaki kod parçacığı, komut dosyasını PSx86 (`C:\Windows\SysWOW64\WindowsPowerShell\v1.0`) olarak çalışır. Gözden geçirmeniz için günlükleri tutar. Betik yürütüldükten sonra Intune yönetim uzantısının günlükleri temizleyeceğini unutmayın:
  
    ```powershell
    $scriptPath = read-host "Enter the path to the script file to execute"
    $logFolder = read-host "Enter the path to a folder to output the logs to"
    $outputPath = $logFolder+"\output.output"
    $errorPath =  $logFolder+"\error.error"
    $timeoutPath =  $logFolder+"\timeout.timeout"
    $timeoutVal = 60000 
    $PSFolder = "C:\Windows\SysWOW64\WindowsPowerShell\v1.0"
    $AgentExec = "C:\Program Files (x86)\Microsoft Intune Management Extension\agentexecutor.exe"
    &$AgentExec -powershell  $scriptPath $outputPath $errorPath $timeoutPath $timeoutVal $PSFolder 0 0
    ```

## <a name="next-steps"></a>Sonraki adımlar

Profillerinizi [izleyin](../device-profile-monitor.md) ve [sorun giderin](../device-profile-troubleshoot.md) .
