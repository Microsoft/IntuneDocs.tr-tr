---
title: Bilgisayar istemci yazılımını yükleme
description: Windows bilgisayarlarınızın Microsoft Intune istemci yazılımıyla yönetilmesini sağlamanıza yardımcı olması için bu kılavuzu kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
ms.date: 07/13/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 48079adfd8ff2f635ebf63370da62f7e428dcb40
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238515"
---
# <a name="install-the-intune-software-client-on-windows-pcs"></a>Windows bilgisayarlara Intune yazılım istemcisini yükleme

[!INCLUDE [classic-portal](includes/classic-portal.md)]

> [!NOTE]
> Aşağıda açıklandığı gibi Windows bilgisayarlarını [mobil cihaz yönetimi (MDM) ile mobil cihazlar olarak](windows-enroll.md) ya da Intune yazılım istemcisi ile bilgisayarlar olarak yönetmek için Microsoft Intune’u kullanabilirsiniz. Ancak Microsoft, müşterilerin mümkün olan her durumda [MDM yönetim çözümünü kullanmasını](windows-enroll.md) önerir. Daha fazla bilgi için [Windows PC'leri bilgisayarlar veya mobil cihazlar olarak yönetmeyi karşılaştırma](pc-management-comparison.md) 


Windows bilgisayarlar Intune istemci yazılımı yüklenerek kaydedilebilir. Intune istemci yazılımı aşağıdaki yöntemler kullanılarak yüklenebilir:

- BT yöneticisi şu yöntemlerden birini kullanabilir: el ile yükleme, Grup İlkesi veya bir disk görüntüsüne dahil edilmiş yükleme

- Son kullanıcılar, istemci yazılımını el ile yükleyebilir

Intune istemci yazılımı, bilgisayarı Intune yönetimine kaydetmek için gerekli en düşük yazılımı içerir. Bilgisayar kaydedildikten sonra Intune istemci yazılımı, bilgisayar yönetimi için gereken tam istemci yazılımını indirir.

Bu indirmeler, ağın bant genişliğine olan etkiyi azaltır ve bilgisayarın Intune’a ilk kaydı için gerekli olan zamanı en aza indirir. Ayrıca ikinci indirme işlemi bittikten sonra istemcinin mevcut en yeni yazılıma sahip olmasını sağlar.

Intune lisanslarından biri, Intune istemci yazılımını en fazla beş bilgisayara yüklemenize olanak tanır.

## <a name="download-the-intune-client-software"></a>Intune istemci yazılımını indirme

Intune istemci yazılımının kullanıcılar tarafından yüklendiği yöntemlerin dışındaki tüm yöntemler, sonrasında yazılımın son kullanıcılara dağıtılması için BT yöneticilerinin öncelikle yazılımı indirmesini gerektirir.

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Yönetici** &gt; **İstemci Yazılımı İndirme**’ye tıklayın.

   ![Intune bilgisayar istemcisini indirme](./media/https://docs.microsoft.com/intune/media/install-the-windows-pc-client/pc-sa-client-download.png)

2. **İstemci Yazılımı İndirme** sayfasında, **İstemci Yazılımını İndir**'e tıklayın. Ardından yazılımı içeren **Microsoft_Intune_Setup.zip** paketini ağınızda güvenli bir yere kaydedin.

   Intune istemci yazılımı yükleme paketi, hesabınızla ilgili benzersiz bilgileri içerir. Bu bilgilere ekli bir sertifika aracılığıyla erişilebilir. Yetkisiz kullanıcılar yükleme paketine erişirse paketin ekli sertifikası tarafından temsil edilen hesaba bilgisayar kaydedip şirketin kaynaklarına erişim elde edebilir.

3. Yükleme paketinin içeriğini ağınızda güvenli bir konuma ayıklayın.

    > [!IMPORTANT]
    > Ayıklanan **ACCOUNTCERT** dosyasını yeniden adlandırmayın veya kaldırmayın, aksi takdirde istemci yazılımının yüklenmesi başarısız olur.

## <a name="deploy-the-client-software-manually"></a>İstemci yazılımını el ile dağıtma

İstemci yazılımının yükleneceği bilgisayarlarda, istemci yazılımı yükleme dosyalarının bulunduğu klasöre gidin. Ardından, istemci yazılımını yüklemek için **Microsoft_Intune_Setup.exe**'yi çalıştırın.

> [!NOTE]
> İstemci bilgisayarın görev çubuğundaki simgenin üzerine geldiğinizde yükleme durumu görüntülenir.

## <a name="deploy-the-client-software-by-using-group-policy"></a>İstemci yazılımını Grup İlkesi kullanarak dağıtma

1.  **Microsoft_Intune_Setup.exe** ve **MicrosoftIntune.accountcert** dosyalarını içeren klasörde, 32 bit ve 64 bit bilgisayarlar için Windows Installer tabanlı yükleme programlarını ayıklamak için aşağıdaki komutu çalıştırın:

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** ve **MicrosoftIntune.accountcert** dosyalarını, istemci yazılımının yükleneceği tüm bilgisayarlar tarafından erişilebilen bir ağ konumuna kopyalayın.

    > [!IMPORTANT]
    > Dosyaları ayırmayın veya yeniden adlandırmayın, aksi takdirde yazılım yüklemesi başarısız olur.

3.  Yazılımı ağınızdaki bilgisayarlara dağıtmak için Grup İlkesi'ni kullanın.

    Otomatik olarak yazılım dağıtmak için Grup İlkesi'ni kullanma hakkında daha fazla bilgi için, bkz. [Yeni Başlayanlar için Grup İlkesi](https://technet.microsoft.com/library/hh147307.aspx).

## <a name="deploy-the-client-software-as-part-of-an-image"></a>İstemci yazılımını bir görüntünün parçası olarak dağıtma
Aşağıdaki yordamı örnek alarak Intune istemci yazılımını bilgisayarlara bir işletim sistemi görüntüsünün parçası olarak dağıtabilirsiniz:

1.  **Microsoft_Intune_Setup.exe** ve **MicrosoftIntune.accountcert** istemci yükleme dosyalarını, referans bilgisayarındaki **%Systemdrive%\Temp\Microsoft_Intune_Setup** klasörüne kopyalayın.

2.  **SetupComplete.cmd** betiğine aşağıdaki komutu ekleyerek **WindowsIntuneEnrollPending** kayıt defteri girişini oluşturun:

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  /PrepareEnroll komut satırı bağımsız değişkeniyle kayıt paketini çalıştırmak için **setupcomplete.cmd**’ye aşağıdaki komutu ekleyin:

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > **SetupComplete.cmd** betiği, bir kullanıcı oturum açmadan önce Windows Kurulumu’nun sistemde değişiklik yapmasını sağlar. **/PrepareEnroll** komut satırı bağımsız değişkeni, Windows Kurulumu tamamlandıktan sonra, hedeflenen bir bilgisayarı Intune hizmetine otomatik olarak kaydolmaya hazırlar.

4.  **SetupComplete.cmd**'yi başvuru bilgisayarındaki **%Windir%\Setup\Scripts** klasörüne koyun.

5.  Başvuru bilgisayarının bir görüntüsünü yakalayın ve bu görüntüyü hedef bilgisayarlara dağıtın.

    Windows Kur tamamlandıktan sonra hedef bilgisayar yeniden başlatıldığında, **WindowsIntuneEnrollPending** kayıt defteri anahtarı oluşturulur. Kayıt paketi, bilgisayarın kayıtlı olup olmadığını denetler. Bilgisayar kayıtlıysa, başka eyleme gerek yoktur. Bilgisayar kayıtlı değilse, kayıt paketi bir Microsoft Intune Otomatik Kayıt Görevi oluşturur.

    Otomatik kayıt görevi bir sonraki zamanlanan saatte çalıştığında, **WindowsIntuneEnrollPending** kayıt defteri değerinin var olup olmadığını denetler ve hedeflenen bilgisayarı Intune’a kaydetmeye çalışır. Kayıt herhangi bir nedenden dolayı başarısız olursa, görev bir daha çalıştığında kayıt yeniden denenir. Yeniden deneme işlemleri bir ay devam eder.

    Intune Otomatik Kayıt Görevi, **WindowsIntuneEnrollPending** kayıt defteri değeri ve hesap sertifikası, kayıt başarılı olduğunda veya bir ay sonra (hangisi önce geliyorsa) hedeflenen bilgisayardan silinir.

## <a name="instruct-users-to-self-enroll"></a>Kullanıcıdan kendi kendine kaydolmasını isteme

Kullanıcılar, Intune istemci yazılımını [Şirket Portalı web sitesine](https://portal.manage.microsoft.com) giderek yükler. Kullanıcıların web portalında gördüğü bilgiler, hesabınızın MDM Yetkilisine ve kullanıcının bilgisayarının işletim sistemi platformuna/sürümüne bağlı olarak değişiklik gösterir.

Kullanıcılara bir Intune lisansı atanmamışsa veya kuruluşun MDM Yetkilisi, Intune olarak ayarlanmamışsa, kullanıcılara kaydolmaya yönelik herhangi bir seçenek gösterilmez.

Kullanıcılar bir Intune lisansı atanmışsa ve kuruluşun MDM yetkilisi, Intune için ayarlanmış ise:

- Windows 7 veya Windows 8 bilgisayarı kullanıcılarına, yalnızca indirip kuruluşlarına özel bilgisayar istemci yazılımını yükleyerek Intune'a kaydolma seçeneği gösterilir.

- Windows 10 veya Windows 8.1 bilgisayarı kullanıcılarına iki kayıt seçeneği gösterilir:

  -  **Bilgisayarı mobil cihaz olarak kaydetme**: Kullanıcıların **Bul nasıl kaydolacağınızı** düğmesine tıklayın ve Bilgisayarlarını mobil bir cihaz olarak kaydetme yönergelerine alınır. MDM kaydı varsayılan ve tercih edilen kayıt seçeneği olduğundan bu düğme göze çarpacak bir şekilde görüntülenir. Ancak MDM seçeneği, yalnızca istemci yazılımı yüklemeyi kapsayan bu makale için kapsam dışıdır.
  - **Bilgisayar Intune istemci yazılımını kullanarak kaydetme**: Kullanıcılarınıza söylemeniz gerekir **indirmek için buraya tıklayın** istemci yazılımı yüklemesi boyunca götüren bir bağlantı,.

Aşağıdaki tabloda seçenekler özetlenmektedir.

  ![Her platformun varsayılan kayıt seçenekleri](./media/install-the-windows-pc-client/default-enrollment-options-table.png)

Aşağıdaki ekran görüntüleri, kullanıcıların yazılım istemcisini kullanarak cihazlarını kaydederken karşılaştıkları ekranları göstermektedir.

Kullanıcılardan, önce cihazlarını tanımlamaları veya kaydetmeleri istenir.

  ![cihazı tanımlayın veya kaydedin](./media/install-the-windows-pc-client/identify-device-or-enroll.png)

Kullanıcılarınızın bilgisayar istemci yazılımını yükleyebilmesi için, kendilerine **İndirmek için buraya tıklayın** bağlantısını seçmelerini söylemeniz gerekir. Bu bağlantı, kullanıcılara bilgisayar istemci yazılımını indirme olanağı sağlar ve yükleme süreci boyunca yol gösterir. **Nasıl kaydolacağınızı öğrenin** düğmesi, kullanıcıları MDM kaydı kullanılarak nasıl kaydolunacağını açıklayan belgelere yönlendirir. Söz konusu yöntem, bu makaledeki yazılım istemcisi yönergeleri için kapsam dışıdır.

  ![İndirmek için buraya tıklayın bağlantısını seçin](./media/install-the-windows-pc-client/enroll-your-windows-device.png)

Kullanıcılar, bağlantıya tıkladıklarında bir **Yazılımı İndir** düğmesi görürler. Bilgisayar istemci yazılımını yüklemeyi başlatmak için bu düğmeyi seçmeleri gerekir.

  ![Yazılımı İndir düğmesini seçin](./media/install-the-windows-pc-client/download-pc-client-software.png)

Kullanıcılardan kurumsal kimlik bilgileriyle oturum açmaları istenir.

  ![Kimlik bilgilerinizle oturum açın](./media/install-the-windows-pc-client/sign-in-to-intune.png)

Kullanıcılar, yüklemeye ait Karşılama sayfasına yönlendirilir.

  ![Bilgisayar istemci yüklemesine ait karşılama sayfası](./media/install-the-windows-pc-client/welcome-to-pc-agent-install-wizard.png)

Kullanıcıların **İleri**’yi seçmesiyle yükleme başlatılır.

  ![Bilgisayar istemci yüklemesine ait karşılama sayfası](./media/install-the-windows-pc-client/welcome-to-pc-agent-install-wizard.png)

Kullanıcılar, yükleme tamamlandığında **Son**’u seçer.

  ![Bilgisayar istemci yüklemesini sonlandırın](./media/install-the-windows-pc-client/completed-the-setup-wizard.png)

Kullanıcılar, Intune bilgisayar istemci yazılımını kullanarak kaydolduktan sonra bilgisayarlarını mobil bir cihaz olarak yeniden kaydetmeye çalışırsa aşağıdaki hata ekranıyla karşılaşır.

  ![Bilgisayar zaten kayıtlı olduğunda gösterilen ekran](./media/install-the-windows-pc-client/page-shown-if-pc-already-enrolled.png)

## <a name="monitor-and-validate-successful-client-deployment"></a>Başarılı istemci dağıtımını izleme ve doğrulama
Başarılı istemci dağıtımını izlemenize ve doğrulamanıza yardımcı olması için aşağıdaki yordamlardan birini kullanın.

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a>Microsoft Intune yönetici konsolundan istemci yazılımının yüklendiğini doğrulamak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Bilgisayarlar**’a tıklayın.

2.  Listede Intune ile iletişim kuran bilgisayarları bulun veya **Cihaz ara** kutusuna bilgisayar adını (veya adının bir parçasını) yazarak belirli bir yönetilen bilgisayar arayın.

3.  Konsolun alt bölmesinden bilgisayarın durumunu inceleyin. Hataları giderin.

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a>Tüm kayıtlı bilgisayarları görüntülemek üzere bir bilgisayar envanteri raporu oluşturmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Raporlar** &gt; **Bilgisayar Envanteri Raporları**’na tıklayın.

2.  **Yeni Rapor Oluştur** sayfasında, (filtre uygulamak istemiyorsanız) tüm alanlardaki varsayılan değerleri bırakın ve **Raporu Görüntüle**'ye tıklayın.

3.  **Bilgisayar Envanteri Raporu** sayfası, Intune’a başarılı bir şekilde kaydedilen tüm bilgisayarların görüntülendiği yeni bir pencerede açılır.

    > [!TIP]
    > Raporu herhangi bir sütunun içeriğine göre sıralamak için sütun başlığına tıklayın.

## <a name="uninstall-the-windows-client-software"></a>Windows istemci yazılımını kaldırma

Windows istemci yazılımı kaydı iki yolla silinebilir:

- Intune yönetici konsolundan (önerilen yöntem)
- İstemci üzerindeki bir komut isteminden

### <a name="unenroll-by-using-the-intune-admin-console"></a>Intune yönetim konsolunu kullanarak kayıt silme

Intune yönetim konsolunu kullanarak yazılım istemci kaydı silmek için **Gruplar** > **Tüm Bilgisayarlar** > **Cihazlar**’a gidin. İstemciye sağ tıklayın ve **Devre Dışı Bırak/Temizle**’yi seçin.

### <a name="unenroll-by-using-a-command-prompt-on-the-client"></a>İstemci üzerindeki bir komut isteminden kayıt silme

Yükseltilmiş bir komut istemi kullanarak aşağıdaki komutlardan birini çalıştırın.

**Yöntem 1**:

    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune

**Yöntem 2** Bu aracıların tümünün her Windows SKU’sunda yüklü olduğunu unutmayın:

    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall
    wmic product where name="Microsoft Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall
    wmic product where name="Microsoft Policy Platform" call uninstall
    wmic product where name="Microsoft Security Client" call uninstall
    wmic product where name="Microsoft Online Management Client" call uninstall
    wmic product where name="Microsoft Online Management Client Service" call uninstall
    wmic product where name="Microsoft Easy Assist v2" call uninstall
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Microsoft Intune Center" call uninstall
    wmic product where name="Microsoft Online Management Update Manager" call uninstall
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall
    wmic product where name="Microsoft Intune" call uninstall
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall
    wmic product where name="Windows Intune Notification Service" call uninstall
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall
    wmic product where name="Windows Online Management Policy Agent" call uninstall
    wmic product where name="Windows Policy Platform" call uninstall
    wmic product where name="Windows Security Client" call uninstall
    wmic product where name="Windows Online Management Client" call uninstall
    wmic product where name="Windows Online Management Client Service" call uninstall
    wmic product where name="Windows Easy Assist v2" call uninstall
    wmic product where name="Windows Intune Monitoring Agent" call uninstall
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall
    wmic product where name="Windows Firewall Configuration Provider" call uninstall
    wmic product where name="Windows Intune Center" call uninstall
    wmic product where name="Windows Online Management Update Manager" call uninstall
    wmic product where name="Windows Online Management Agent Installer" call uninstall
    wmic product where name="Windows Intune" call uninstall

> [!TIP]
> İstemci kaydı silindiğinde, etkilenen istemci için sunucu tarafında eski bir kayıt kalır. Kayıt silme işlemi zaman uyumsuzdur ve kaldırılacak dokuz aracı olduğundan tamamlanması 30 dakikaya kadar sürebilir.

### <a name="check-the-unenrollment-status"></a>Kayıt silinme durumunu denetleme

"%ProgramFiles%\Microsoft\OnlineManagement" yolunu denetleyin ve solda sadece aşağıdaki dizinlerin gösterildiğinden emin olun:

- AgentInstaller
- Logs
- Güncelleştirmeler
- Common

### <a name="remove-the-onlinemanagement-folder"></a>OnlineManagement klasörünü kaldırma

Kayıt silme işlemi OnlineManagement klasörünü kaldırmaz. Kaldırma sonrasında 30 dakika bekleyin ve ardından bu komutu çalıştırın. Çok erken çalıştırırsanız, kaldırma işlemi bilinmeyen bir durumda kalabilir. Klasörü kaldırmak için yükseltilmiş bir komut istemi başlatın ve çalıştırın:

    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".

### <a name="next-steps"></a>Sonraki adımlar
[Intune yazılım istemcisi ile genel Windows bilgisayar yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
