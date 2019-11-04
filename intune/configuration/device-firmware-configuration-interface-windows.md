---
title: Microsoft Intune-Azure 'da MDM ilkelerini kullanarak Windows BIOS özelliklerini güncelleştirme | Microsoft Docs
description: Microsoft Intune 'da Windows 10 cihazlarında CPU, yerleşik donanım ve önyükleme seçenekleri gibi UEFı ayarlarını yönetmek için bir cihaz üretici yazılımı yapılandırma arabirimi (DFCı) profili ekleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5afe2414db063aad53a89fd8125a68a53457ca49
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414646"
---
# <a name="use-device-firmware-configuration-interface-profiles-on-windows-devices-in-microsoft-intune-public-preview"></a>Windows cihazlarında cihaz üretici yazılımı yapılandırma arabirimi profillerini Microsoft Intune (Genel Önizleme) kullanma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

> [!Note]
> Her [aylık güncelleştirmenin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) piyasaya sürülme birkaç gün sürebilir. Bazı özellikler birkaç hafta boyunca alabilir ve tüm müşteriler tarafından hemen kullanılamayabilir.

Autopilot cihazlarını yönetmek için Intune kullandığınızda, cihaz üretici yazılımı yapılandırma arabirimini (DFCı) kullanarak, UEFı (BIOS) ayarlarını, kaydolduktan sonra yönetebilirsiniz. Avantajlar, senaryolar ve önkoşullara genel bakış için bkz. [DFCı 'Ya genel bakış](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Dfci_Feature/).

DFCı [Windows](https://docs.microsoft.com/windows/client-management/mdm/uefi-csp) 'un yönetim komutlarını ıNTUNE 'dan UEFI 'ye (Birleşik Genişletilebilir Bellenim Arabirimi) geçmesini sağlar.

Intune 'da, BIOS ayarlarını denetlemek için bu özelliği kullanın. Genellikle, bellenim kötü amaçlı saldırılara karşı daha dayanıklıdır. Son Kullanıcı denetimini BIOS üzerinde sınırlandırır ve bu durum, güvenliği aşılmış olması durumunda iyidir.

Örneğin, Windows 10 cihazlarını güvenli bir ortamda kullanın ve kamerayı devre dışı bırakmak isteyebilirsiniz. Kamerayı, bellenim katmanında devre dışı bırakarak son kullanıcının önemi yoktur. İşletim sistemini yeniden yükleme veya bilgisayarı Temizleme, kamerayı yeniden açamaz. Başka bir örnekte, kullanıcıların başka bir işletim sistemini veya aynı güvenlik özelliklerine sahip olmayan eski bir sürümünü önyüklemesine engel olmak için önyükleme seçeneklerini kilitleyin.

Daha eski bir Windows sürümünü yeniden yüklediğinizde, ayrı bir işletim sistemi yükleyin veya sabit sürücüyü biçimlendirin, DFCı yönetimini geçersiz kılamazsınız. Bu özellik, kötü amaçlı yazılımların yükseltilmiş işletim sistemi işlemlerine dahil olmak üzere işletim sistemi işlemleriyle iletişim kurmasını önleyebilir. DFCı 'nın güven zinciri ortak anahtar şifrelemeyi kullanır ve yerel UEFı (BIOS) Parola güvenliğine bağlı değildir. Bu güvenlik katmanı, yerel kullanıcıların cihazın UEFı (BIOS) menülerinden yönetilen ayarlara erişmesini engeller.

Bu özellik şu platformlarda geçerlidir:

- Desteklenen UEFı üzerinde Windows 10 RS5 (1809) ve üzeri

## <a name="before-you-begin"></a>Başlamadan önce

- Cihaz üreticisinin, üretim işlemindeki UEFı bellenimine veya yüklediğiniz bir bellenim güncelleştirmesine sahip olması gerekir. [Dfcı 'yı destekleyen üreticileri](https://microsoft.github.io/mu/dyn/mu_plus/DfciPkg/Docs/Scenarios/DfciScenarios/#oems-that-support-dfci)veya dfcı 'yi kullanmak için gereken bellenim sürümünü öğrenmek için cihaz satıcılarınızla birlikte çalışın.

- Cihaz, bir [Microsoft bulut çözümü sağlayıcısı (CSP) iş ortağı](https://partner.microsoft.com/cloud-solution-provider)tarafından Windows Autopilot veya doğrudan OEM tarafından kaydedilmiş olmalıdır. 

  Autopilot için el ile kaydedilen cihazların [bir CSV dosyasından içeri aktarılması](../enrollment/enrollment-autopilot.md#add-devices)gıbı, dfcı kullanılmasına izin verilmez. Yönetim sayesinde, DFCı yönetimi, bir OEM veya Microsoft CSP iş ortağı kaydı aracılığıyla cihazın ticari alımı için Windows Autopilot 'e yönelik dış kanıtlama gerektirir.

  Cihazınız kaydedildikten sonra, seri numarası Windows Autopilot cihazları listesinde gösterilir.

  Gereksinimler dahil Autopilot hakkında daha fazla bilgi için bkz. [Windows Autopilot kullanarak Intune 'Da Windows cihazlarını kaydetme](../enrollment/enrollment-autopilot.md).

## <a name="create-your-azure-ad-security-groups"></a>Azure AD güvenlik gruplarınızı oluşturma

Autopilot dağıtım profilleri Azure AD güvenlik gruplarına atanır. DFCı tarafından desteklenen cihazlarınızı içeren gruplar oluşturmayı unutmayın. DFCı cihazlarında çoğu kuruluş, Kullanıcı grupları yerine cihaz grupları oluşturabilir. Aşağıdaki senaryoları göz önünde bulundurun:

- İnsan kaynakları (HR) farklı Windows cihazlarına sahiptir. Güvenlik nedenleriyle, bu gruptaki herkesin cihazlarda kamerayı kullanmasını istemezsiniz. Bu senaryoda, ilke türü her ne olursa olsun, ilke HR grubundaki kullanıcılar için geçerli olacak şekilde bir HR güvenlik kullanıcıları grubu oluşturabilirsiniz.
- Üretim aşamasında 10 cihaz vardır. Tüm cihazlarda cihazların USB cihazından önyüklenmesini engellemek isteyebilirsiniz. Bu senaryoda, bir güvenlik cihazları grubu oluşturabilir ve bu 10 cihazı gruba ekleyebilirsiniz.

Intune 'da Grup oluşturma hakkında daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](../fundamentals/groups-add.md).

## <a name="create-the-profiles"></a>Profilleri oluşturma

DFCı 'yi kullanmak için aşağıdaki profilleri oluşturun ve bunları grubunuza atayın.

### <a name="create-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma

Bu profil, yeni cihazları ayarlar ve önceden yapılandırır. [Autopilot dağıtım profilinde](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) profil oluşturma adımları listelenir.

### <a name="create-an-enrollment-state-page-profile"></a>Kayıt durumu sayfası profili oluşturma

Bu profil, Windows kurulumu sırasında cihazların doğrulanıp doğrulandığından ve DFCı için etkinleştirildiğinden emin olmanızı sağlar. Tüm uygulamalar ve profiller yüklenene kadar cihaz kullanımını engellemek için bu profili kullanmanız önemle önerilir. [Kayıt durumu sayfası profili](../enrollment/windows-enrollment-status.md) , profili oluşturma adımlarını listeler.

### <a name="create-the-dfci-profile"></a>DFCı profilini oluşturma

Bu profil, yapılandırdığınız DFCı ayarlarını içerir.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: profil için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı **Windows: Windows cihazlarında dfcı ayarlarını yapılandırın**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Windows 10 ve üzeri** seçeneğini belirleyin.
    - **Profil türü**: **cihaz üretici yazılımı yapılandırma arabirimini**seçin.

4. Şu ayarları yapılandırın:

    - **Yerel kullanıcının UEFI (BIOS) ayarlarını değiştirmesine Izin ver**: seçenekleriniz:
      - **Yalnızca yapılandırılmadı**ayarı: Yerel Kullanıcı, Intune tarafından **etkinleştirmek** veya **devre dışı bırakmak** için açıkça ayarlanmış olan bu ayarlar *dışında* herhangi bir ayarı değiştirebilir.
      - **Hiçbiri**: Yerel Kullanıcı, dfcı profilinde görünmeyen ayarlar dahil olmak üzere UEFı (BIOS) ayarlarını değiştiremeyebilir.

    - **CPU ve GÇ Sanallaştırması**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu özelliğe dokunmaz ve tüm ayarları olduğu gibi bırakır.
        - **Etkin**: BIOS, platformun CPU ve GÇ sanallaştırma özelliklerini işletim sistemi tarafından kullanılmak üzere sunar. Windows sanallaştırma tabanlı güvenlik ve cihaz koruyucu teknolojilerini etkinleştirir.
        - **Devre dışı bırak**: BIOS, platform CPU & IO sanallaştırma yeteneklerini devre dışı bırakır ve bunların kullanılmasını önler.
    - **Kameralar**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu özelliğe dokunmaz ve tüm ayarları olduğu gibi bırakır.
        - **Etkin**: UEFı (BIOS) tarafından doğrudan yönetilen tüm yerleşik kameralar etkindir. USB kameraları gibi çevre birimleri etkilenmez.
        - **Devre dışı**: UEFı (BIOS) tarafından doğrudan yönetilen tüm yerleşik kamera devre dışı bırakıldı. USB kameraları gibi çevre birimleri etkilenmez.
    - **Mikrofonlar ve hoparlörler**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu özelliğe dokunmaz ve tüm ayarları olduğu gibi bırakır.
        - **Etkin**: UEFı (BIOS) tarafından doğrudan yönetilen tüm yerleşik mikrofonlar ve hoparlörler etkindir. USB cihazları gibi çevre birimleri etkilenmez.
        - **Devre dışı**: UEFı (BIOS) tarafından doğrudan yönetilen tüm yerleşik mikrofonlar ve hoparlörler devre dışı bırakılır. USB cihazları gibi çevre birimleri etkilenmez.
    - **Radyolar (Bluetooth, Wi-Fi, NFC vb.)** : seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu özelliğe dokunmaz ve tüm ayarları olduğu gibi bırakır.
        - **Etkin**: UEFı (BIOS) tarafından doğrudan yönetilen tüm yerleşik radyolar etkindir. USB cihazları gibi çevre birimleri etkilenmez.
        - **Devre dışı**: UEFı (BIOS) tarafından doğrudan yönetilen tüm yerleşik radyolar devre dışı bırakıldı. USB cihazları gibi çevre birimleri etkilenmez.

        > [!WARNING]
        > **Radyoların** ayarını devre dışı bırakırsanız, cihaz kablolu ağ bağlantısı gerektirir. Aksi takdirde, cihaz yönetilebilir olabilir.

    - **Dış medyadan (USB, SD) önyükleme**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu özelliğe dokunmaz ve tüm ayarları olduğu gibi bırakır.
        - **Etkin**: UEFı (BIOS), sabit olmayan sürücü depolamadan önyükleme yapılmasına izin verir.
        - **Devre dışı**: UEFı (BIOS), sabit olmayan sürücü depolamadan önyüklenmesine izin vermez.
    - **Ağ bağdaştırıcılarından önyükleme**: seçenekleriniz:
        - **Yapılandırılmadı**: Intune bu özelliğe dokunmaz ve tüm ayarları olduğu gibi bırakır.
        - **Etkin**: UEFı (BIOS), yerleşik ağ arabirimlerinden önyüklenmesine izin verir.
        - **Devre dışı**: UEFı (BIOS), yerleşik ağ arabirimlerinin önyüklenmesine izin vermez.

5. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin. Profil oluşturulur ve listede gösterilir.

## <a name="assign-the-profiles-and-reboot"></a>Profilleri atayın ve yeniden başlatın

Profiller oluşturulduktan sonra, [atanmak için hazırlırlar](../configuration/device-profile-assign.md). Profilleri, DFCı cihazlarınızı içeren Azure AD güvenlik gruplarına atadığınızdan emin olun.

Cihaz eşitlendikten sonraki sefer veya cihaz yeniden başlatıldığında, DFCı profil ayarları uygulanır. İlke uygulandıktan sonra, cihazı yeniden başlatın.

Cihaz Windows cihaz kurulumunu çalıştırdığında, DFCı kayıt durumu sayfası sırasında yeniden başlatmaya zorlayabilir. Kurulum tamamlandıktan sonra, cihaz yeniden başlatılarak DFCı ayarlarının etkin olduğunu doğrulayabilirsiniz. Ardından, UEFı menüsünü açmak için cihaz üreticisinin yönergelerini kullanın.

## <a name="update-existing-dfci-settings"></a>Mevcut DFCı ayarlarını Güncelleştir

Kullanımdaki cihazlarda mevcut DFCı ayarlarını değiştirmek istiyorsanız, ' yi kullanabilirsiniz. Mevcut DFCı profilinizde ayarları değiştirin ve değişikliklerinizi kaydedin. Profil zaten atanmış olduğundan, yeni DFCı ayarları şu durumlarda geçerli olur:

1. Cihaz, profil güncelleştirmelerini gözden geçirmek için Intune hizmetini iade eder. İadeler çeşitli zamanlarda gerçekleşecektir. Daha fazla bilgi için, bkz. [cihazların ilke, profil veya uygulama güncelleştirmeleri ne zaman alınacağı](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

2. Yeni ayarları zorlamak için, cihazı [Uzaktan](../remote-actions/device-restart.md) veya yerel olarak yeniden başlatın.

Ayrıca, [iade edilecek cihazlara sinyal](../remote-actions/device-sync.md)gönderebilirsiniz. Başarılı bir eşitlemeden sonra [yeniden başlatma sinyali](../remote-actions/device-restart.md).

>[!NOTE]
> DFCı profilini silme veya bir cihazı profile atanan gruptan kaldırma, DFCı ayarlarını kaldırmaz veya UEFı (BIOS) menülerini yeniden etkinleştirebilir. DFCı kullanmayı durdurmak istiyorsanız, mevcut DFCı profilinizi güncelleştirin. Adımlar hakkında daha fazla bilgi için bu makaledeki [cihazı devre dışı bırakma](#retire) bölümüne bakın.

## <a name="reuse-retire-or-recover-the-device"></a>Cihazı yeniden kullanma, devre dışı bırakma veya kurtarma

### <a name="reuse"></a>Pencereleri

Windows 'u cihaza yeniden amaçlandırın olarak sıfırlamayı planlıyorsanız, [cihazı](../remote-actions/devices-wipe.md)silin. Autopilot cihaz **kaydını kaldırmayın.**

Cihazı sildikten sonra, cihazı yeni DFCı ve Autopilot profillerini atayan gruba taşıyın. Windows kurulumu 'nu yeniden çalıştırmak için cihazı yeniden başlattığınızdan emin olun.

### <a name="retire"></a>Devre dışı bırakma

Cihazı devre dışı bırakmaya ve yönetimden yayınlamaya hazırsanız, DFCı profilini çıkış durumunda istediğiniz UEFı (BIOS) ayarlarına güncelleştirin. Genellikle tüm ayarların etkinleştirilmesini istersiniz. Örneğin:

1. DFCı profilinizi açın (**cihaz yapılandırma** > **profilleri**).
2. **Yerel kullanıcının UEFI (BIOS) ayarlarını** **yalnızca yapılandırılmadı ayarlarına**değiştirmesine izin ver ayarını değiştirin.
3. Diğer tüm ayarları **Yapılandırılmadı**olarak ayarlayın.
4. Ayarlarınızı kaydedin.

Bu adımlar cihazın UEFı (BIOS) menülerini kaldırır. Değerler profille aynı kalır (**etkin** veya **devre dışı**) ve varsayılan işletim sistemi değerlerine geri ayarlanmazlar.

Artık Cihazı temizlemeye hazırsınız. Cihaz temizlenmeden sonra, Autopilot kaydını silin. Kaydın silinmesi cihazın yeniden başlatıldığında otomatik olarak yeniden kaydedilmesini önler.

### <a name="recover"></a>Kurtarılamıyor

Bir cihazı siler ve UEFı (BIOS) menülerinin kilidini açmadan önce Autopilot kaydını silerseniz, menüler kilitli kalır. Intune, kilidini açmak için profil güncelleştirmeleri gönderemiyor.

Cihazın kilidini açmak için, UEFı (BIOS) menüsünü açın ve ağdan yönetimi yenileyin. Kurtarma menülerin kilidini açar, ancak tüm UEFı (BIOS) ayarları önceki Intune DFCı profilindeki değerlere ayarlanmış halde bırakır.

## <a name="end-user-impact"></a>Son Kullanıcı etkisi

DFCı ilkesi uygulandığında, UEFı (BIOS) menüsü parola korumalı olsa bile, yerel kullanıcılar DFCı tarafından yapılandırılan ayarları değiştiremezler. Yapılandırdığınız ayarlara bağlı olarak, son kullanıcılar donanım bileşenlerinin bulunamadığını veya tanılanalamadığına ilişkin hatalar alabilir. Devre dışı bıraktığınız seçenekleri açıklayan son kullanıcılara belge sağladığınızdan emin olun.  

## <a name="next-steps"></a>Sonraki adımlar

Profil atandıktan sonra [durumunu izleyin](../device-profile-monitor.md).
