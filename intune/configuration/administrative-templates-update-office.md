---
title: Microsoft Intune-Azure 'da Yönetim şablonlarını kullanarak Office 365 güncelleştirme | Microsoft Docs
description: Office 365 uygulamalarını en son sürüme güncelleştirmek için Microsoft Intune Yönetim şablonlarını kullanın ve Office 'in güncelleştirmeleri ne sıklıkta denetleyeceğini seçin. Office Update 'e yönelik bir Intune ilkesi uygulandığında güncelleştirilecek cihaz kayıt defteri anahtarlarına bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dcd1948899ec4023a65c62f7106298b065b46883
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206933"
---
# <a name="use-update-channel-and-target-version-settings-to-update-office-365-with-microsoft-intune-administrative-templates"></a>Microsoft Intune Yönetim Şablonları ile Office 365 güncelleştirmek için kanalı güncelleştirme ve hedef sürüm ayarlarını kullanın

Intune 'da, [Grup İlkesi ayarlarını yapılandırmak Için Windows 10 şablonlarını](administrative-templates-windows.md)kullanabilirsiniz. Bu makalede, Office 365 ' i Intune 'da yönetim şablonu kullanarak güncelleştirme konusu gösterilmektedir. Ayrıca, ilkelerinizin başarıyla uygulandığını onaylama konusunda rehberlik sağlar. Bu bilgiler, sorun gidermede de yardımcı olur.

Bu senaryoda, cihazlarınızda Office 365 ' u güncelleştiren bir yönetim şablonu oluşturacaksınız.

Yönetim Şablonları hakkında daha fazla bilgi için bkz. [Windows 10 şablonları Grup İlkesi ayarlarını yapılandırmak için](administrative-templates-windows.md).

Uygulama hedefi:

- Windows 10 ve üzeri
- Office 365

## <a name="prerequisites"></a>Önkoşullar

Office uygulamalarınız için [Office365 ProPlus otomatik güncelleştirmelerini](https://docs.microsoft.com/deployoffice/configure-update-settings-for-office-365-proplus) etkinleştirdiğinizden emin olun. Bunu Grup İlkesi veya Intune Office 2016 ADMX şablonu kullanarak yapabilirsiniz:

![Intune yönetim şablonunda, Office için otomatik güncelleştirmeleri etkinleştir ayarını ayarlayın](./media/administrative-templates-update-office/admx-enable-automatic-updates.png)

## <a name="set-the-update-channel-in-the-intune-administrative-template"></a>Intune yönetim şablonunda güncelleştirme kanalını ayarlama

1. [Intune yönetim şablonunuzda](administrative-templates-windows.md#create-a-template), **kanalı Güncelleştir** ayarına gidin ve istediğiniz kanalı girin. Örneğin `Semi-Annual Channel`seçin:

    ![Intune yönetim şablonunda, Office için güncelleştirme kanalı ayarını ayarlayın](./media/administrative-templates-update-office/admx-enable-update-channel-setting.png)

    > [!NOTE]
    > Daha sık güncelleştirmeniz önerilir. Yarı yıllık yalnızca örnek olarak kullanılır.

2. İlkeyi Windows 10 cihazlarınıza [atadığınızdan](device-profile-assign.md) emin olun. İlkenizi daha erken test etmek için ilkeyi de eşitleyebilirsiniz:

    - [Intune 'da ilkeyi eşitleme](../remote-actions/device-sync.md)
    - [Cihazdaki ilkeyi el ile eşitleme](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows#sync-from-settings-app)

## <a name="check-the-intune-registry-keys"></a>Intune kayıt defteri anahtarlarını denetleme

İlkeyi atadıktan sonra cihaz eşitlendikten sonra, ilkenin uygulandığını doğrulayabilirsiniz:

1. Cihazda, **kayıt defteri Düzenleyicisi** uygulamasını açın.
2. Intune ilke yoluna gidin: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`.

    > [!TIP]
    > Kayıt defteri anahtarındaki `<Provider ID>` değişir. Cihazınızın sağlayıcı KIMLIĞINI bulmak için, **kayıt defteri Düzenleyicisi** uygulamasını açın ve `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\AdmxInstalled`gidin. Sağlayıcı KIMLIĞI gösterilir.

    İlke uygulandığında, aşağıdaki kayıt defteri anahtarlarını görürsünüz:

    - `L_UpdateBranch`
    - `L_UpdateTargetVersion`

    Aşağıdaki örneğe bakarak `<enabled /><data id="L_UpdateBranchID" value="Deferred" />`şuna benzer bir değer `L_UpdateBranch` görürsünüz. Bu değer, yarı yıllık kanal olarak ayarlanan anlamına gelir:

    ![Yönetim şablonu L_Updatebranch kayıt defteri anahtarı örneği](./media/administrative-templates-update-office/admx-update-branch-registry-key.png)

    > [!TIP]
    > [Office 365 ProPlus](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel) 'ı, değerleri Configuration Manager listeler ve bunların ne anlama geldiğini yönetin. Kayıt defteri değerleri, seçilen dağıtım kanalını temel alır:
    >
    >- Aylık kanal-değer = "geçerli"
    >- Aylık kanal (hedeflenen)-değer = "geçerli"
    >- Yarı yıllık kanal-değer = "geçerli"
    >- Yarı yıllık kanal (hedefli)-değer = "Firstreleaseertelenmiş"
    >- Insider hızlı-değer = "InsiderFast"

Bu noktada, Intune ilkesi cihaza başarıyla uygulandı.

## <a name="check-the-office-registry-keys"></a>Office kayıt defteri anahtarlarını denetleme

1. Cihazda, **kayıt defteri Düzenleyicisi** uygulamasını açın.
2. Office ilkesi yoluna gidin: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`.

    Aşağıdaki kayıt defteri anahtarlarını görürsünüz:

    - `UpdateChannel`: yapılandırılan ayarlara bağlı olarak değişen dinamik anahtar.
    - `CDNBaseUrl`: Office 365 cihaza yüklendiğinde ayarlanır.

3. `UpdateChannel` değerine bakın. Bu değer, Office 'in ne sıklıkla güncelleştirileceğini söyler. [Office 365 ProPlus](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel) ' ı, değerleri Configuration Manager listeler ve ne ayarlandıklarından birlikte yönetin.

    Aşağıdaki örneğe **bakarak, `UpdateChannel`**`http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60`olarak ayarlandığını görürsünüz:

    ![Yönetim şablonu Office UpdateChannel kayıt defteri anahtarı örneği](./media/administrative-templates-update-office/admx-update-channel-office-registry-key.png)

    Bu örnek, kısmen **yıllık**değil, hala **aylık**olarak ayarlandığı için ilkenin henüz uygulanmadığı anlamına gelir.

Bu kayıt defteri anahtarı, **Görev Zamanlayıcı** > **Office otomatik güncelleştirmeleri 2,0** çalıştırıldığında veya bir Kullanıcı cihazda oturum açtığında güncelleştirilir. Onaylamak için **Office otomatik güncelleştirmeler 2,0** görev > **tetikleyicilerini**açın. Tetikleyicilere bağlı olarak, `UpdateChannel` kayıt defteri anahtarı güncelleştirildikten önce en az bir gün ve daha fazlasını gerçekleştirebilir.

## <a name="force-office-automatic-updates-to-run"></a>Office otomatik güncelleştirmelerini çalıştırmaya zorla

İlkenizi test etmek için, cihazdaki ilke ayarlarını zorlayabilirsiniz. Aşağıdaki adımlar kayıt defterini güncelleştirir. Her zaman, kayıt defteri güncelleştirilirken dikkatli olun.

1. Kayıt defteri anahtarını temizleyin:

    1. <`Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Updates`> adresine gidin.
    2. `UpdateDetectionLastRunTime` anahtarı çift seçin, **tamam**> değer verilerini silin.

2. Office otomatik güncelleştirmeler görevini çalıştırın:

    1. Cihazda **Görev Zamanlayıcı** uygulamasını açın.
    2. **Görev Zamanlayıcı kitaplığı** > **Microsoft** > **Office**' i genişletin.
    3. **Office otomatik güncelleştirmeler 2,0** > **Çalıştır**' ı seçin:

        ![Görev zamanlamasını açın ve Office otomatik güncelleştirmelerini çalıştırın](./media/administrative-templates-update-office/admx-task-scheduler-office-automatic-updates.png)

        Görevin bitmesini bekleyin, bu işlem birkaç dakika sürebilir.

3. **Kayıt defteri Düzenleyicisi** uygulamasında `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`' a gidin. `UpdateChannel` değerini denetleyin.

    İlkede ayarlanan değerle birlikte güncelleştirilmeleri gerekir. Örneğimizde, değer `http://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114`olarak ayarlanmalıdır.

Bu noktada, Office güncelleştirme kanalı cihazda başarıyla değiştirilmiştir. Durumu denetlemek için, bu güncelleştirmeyi alan bir kullanıcı için bir Office 365 uygulaması açabilirsiniz.

## <a name="force-the-office-synchronization-to-update-account-information"></a>Hesap bilgilerini güncelleştirmek için Office eşitlemesini zorla  

Daha fazlasını yapmak istiyorsanız, Office 'i en son sürüm güncelleştirmesini almaya zorlayabilirsiniz. Aşağıdaki adımlar yalnızca bir onay olarak yapılmalıdır ya da cihazların en son sürüm güncelleştirmesini bu kanaldan hızlıca alması gerekiyorsa. Aksi takdirde, Office 'in işini yapmasına ve otomatik olarak güncelleştirmesine izin verin.

### <a name="step-1-force-the-office-version-to-update"></a>1. Adım: Office sürümünü güncelleştirmek için zorlayın

1. Office sürümünün tercih ettiğiniz güncelleştirme kanalını desteklediğini onaylayın. [Office 365 ProPlus Için güncelleştirme geçmişi](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date) , farklı güncelleştirme kanallarını destekleyen yapı numaralarını listeler.

2. [Intune yönetim şablonunuzda](administrative-templates-windows.md#create-a-template), **hedef sürüm** ayarına gidin ve istediğiniz sürümü girin.

    **Hedef sürüm** ayarınız aşağıdaki ayara benzer şekilde görünür:

    ![Intune yönetim şablonunda, Office için hedef sürüm ayarını ayarlayın](./media/administrative-templates-update-office/admx-enable-target-version-setting.png)

> [!IMPORTANT]
>
> - İlkeyi atadığınızdan emin olun.
> - Var olan bir ilkeyi değiştirirseniz, değişiklikleriniz tüm atanan kullanıcıları etkiler.
> - Bu özelliği test ediyorsanız, bir test ilkesi oluşturmanız ve ilkeyi bir Kullanıcı test grubuna atamanız önerilir.

### <a name="step-2-check-the-office-version"></a>2. Adım: Office sürümünü denetleme

İlkeyi tüm kullanıcılara dağıtmadan önce ilkenizi test etmek için bu adımları kullanmayı göz önünde bulundurun.

1. **Kayıt defteri Düzenleyicisi** uygulamasında `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates` gidin.

2. `L_UpdateTargetVersion` değerine bakın. İlke uygulandıktan sonra değer, `<enabled /><data id="L_UpdateTargetVersionID" value="16.0.10730.20344" />`gibi girdiğiniz sürüme ayarlanır.

    Bu noktada, Intune ilkesi cihaza başarıyla uygulandı.

3. Ardından, Office 'i güncelleştirmeye zorlayabilirsiniz. Excel gibi bir Office uygulaması açın. Şimdi güncelleştirmeyi seçin (muhtemelen **Hesap** menüsünde).

    Güncelleştirme birkaç dakika sürer. Office 'in girdiğiniz sürümü almaya çalışıyor olduğunu doğrulayabilirsiniz:

      1. Cihazda `C:\Program Files (x86)\Microsoft Office\Updates\Detection\Version`' a gidin.
      2. `VersionDescriptor.xml` dosyasını açın ve `<Version>` bölümüne gidin. Kullanılabilir sürüm, Intune ilkesinde girdiğiniz sürümle aynı olmalıdır, örneğin:

          ![Sürüm tanımlayıcısı Office XML dosyasındaki sürüm bölümünü denetleyin](./media/administrative-templates-update-office/office-version-descriptor-xml-example.png)

4. Güncelleştirme yüklendikten sonra Office uygulaması yeni sürümü (örneğin, **Hesap** menüsünde) göstermelidir

## <a name="next-steps"></a>Sonraki adımlar

[Office 365 istemcileri için kanal değerlerini güncelleştirme](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel)

[Office 365 ProPlus için Office bulut ilkesi hizmetine genel bakış](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service)

[Microsoft Intune 'de Grup İlkesi ayarlarını (ADMX şablonları) yapılandırmak için Windows 10 şablonlarını kullanın](administrative-templates-windows.md)
