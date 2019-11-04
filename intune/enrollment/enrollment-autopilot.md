---
title: Windows Autopilot kullanarak cihaz kaydetme
titleSuffix: Microsoft Intune
description: Windows Autopilot kullanarak Windows 10 cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e2f654d9e505afba00a1a9090febe4c06ca77ff
ms.sourcegitcommit: d2d18eef64bcf16eec1a48fcb67f1362537c0245
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73445337"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Windows Autopilot kullanarak Windows cihazlarını Intune 'A kaydetme  
Windows Autopilot, cihazların Intune 'A kaydedilmesini basitleştirir. Özelleştirilmiş işletim sistemi görüntülerinin derlenmesi ve bakımı çok zaman alan bir işlemdir. Ayrıca bu özel işletim sistemi görüntülerini, yeni cihazları son kullanıcılarınıza vermeden önce kullanıma hazırlamak amacıyla cihazlara uygulamak için de zaman harcayabilirsiniz. Microsoft Intune ve Autopilot ile cihazlarda özel işletim sistemi görüntüleri oluşturmanıza, bu görüntüleri cihazlara uygulamanıza ve bunların bakımını yapmanıza gerek kalmadan son kullanıcılarınıza yeni cihazlar verebilirsiniz. Autopilot cihazlarını yönetmek için Intune kullandığınızda, kaydolduktan sonra ilkeleri, profilleri, uygulamaları ve diğer nesneleri yönetebilirsiniz. Faydalara, senaryolara ve önkoşullara genel bir bakış için bkz. [Windows Autopilot’a genel bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

Dört tür Autopilot dağıtımı vardır:
- Kiosks, dijital imza veya paylaşılan bir cihaz için [kendi kendine dağıtım modu](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying)
- [Teknik İnceleme](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) , iş ORTAKLARıNıN veya BT personelinin,[mevcut cihazlara yönelik](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) olarak Windows 10 ' un en son sürümünü kolayca dağıtmanıza olanak sağlayan bir Windows 10 PC 'nin ön sağlamasını sağlar
- Geleneksel kullanıcılar için [Kullanıcı odaklı mod](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) . 


## <a name="prerequisites"></a>Önkoşullar
- [Intune aboneliği](../fundamentals/licenses.md)
- [Windows otomatik kayıt etkin olmalıdır](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium aboneliği](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Intune 'da Içeri aktarma için CSV alma

Daha fazla bilgi için bkz. PowerShell cmdlet 'ini anlama.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Cihazları ekleme

Bilgilerini içeren CSV dosyasını içeri aktararak Windows Autopilot cihazlarını ekleyebilirsiniz.

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > **İçeri Aktar**’ı seçin.

    ![Windows Autopilot cihazlarının ekran görüntüsü](./media/enrollment-autopilot/autopilot-import-device.png)

2. **Windows Autopilot cihazları ekle** altında, eklemek istediğiniz cihazları listeleyen bir CSV dosyasına gözatın. CSV dosyası seri numaralarını, Windows ürün kimliklerini, donanım karmalarını, isteğe bağlı Grup etiketlerini ve isteğe bağlı olarak atanmış kullanıcıyı listelemelidir. Listede en fazla 500 satır olabilir. Aşağıda gösterilen üst bilgi ve satır biçimini kullanın:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Windows Autopilot cihazları ekleme ekran görüntüsü](./media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > Bir kullanıcı atamak için CSV yükleme kullandığınızda, geçerli UPN 'ler atadığınızdan emin olun. Geçersiz bir UPN (yanlış Kullanıcı adı) atarsanız, geçersiz atamayı kaldırana kadar cihazınız erişilemez durumda olabilir. CSV yükleme sırasında, **Atanan Kullanıcı** sütununda gerçekleştirdiğimiz tek doğrulama, etki alanı adının geçerli olduğunu denetliyoruz. Mevcut veya doğru bir Kullanıcı atadığınızdan emin olmak için tek tek UPN doğrulaması gerçekleştiremedik.

3. Cihaz bilgilerini içeri aktarmayı başlatmak için **İçeri Aktar**'ı seçin. İçeri aktarma birkaç dakika sürebilir.

4. İçeri aktarma işlemi tamamlandıktan sonra, **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları** > **eşitleme**' yi seçin. Eşitlemenin devam ettiğini gösteren bir ileti görüntülenir. Kaç tane cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.

5. Yeni cihazları görmek için görüntüyü yenileyin.

## <a name="create-an-autopilot-device-group"></a>Bir Autopilot cihaz grubu oluşturma

1. [Azure portalında Intune](https://aka.ms/intuneportal)'da **Gruplar** > **Yeni grup**'u seçin.
2. **Gruplar** dikey penceresinde:
    1. **Grup türü** olarak **Güvenlik**’i seçin.
    2. Bir **Grup adı** ve **Grup açıklaması** girin.
    3. **Üyelik türü** olarak **Atanan** veya **Dinamik Cihaz**’ı seçin.
3. Önceki adımda **Üyelik türü** olarak **Atanan**'ı seçtiyseniz, **Gruplar** dikey penceresinde **Üyeler**'i seçin ve gruba Autopilot cihazları ekleyin.
    Henüz kaydedilmemiş Autopilot cihazları, adın cihaz seri numarası olduğu cihazlardır.
4. Yukarıda **Üyelik türü** olarak **Dinamik Cihazlar**’ı seçtiyseniz **Gruplar** dikey penceresinde **Dinamik cihaz üyeleri**’ni seçin ve **Gelişmiş kural** kutusuna aşağıdaki kodlardan birini yazın. Yalnızca Autopilot cihazları tarafından sahip olan öznitelikleri hedeflerse, yalnızca Autopilot cihazları bu kurallar tarafından toplanır. Autopilot olmayan öznitelikleri temel alan bir grup oluşturmak, grupta yer alan cihazların gerçekten Autopilot 'e kaydolduğundan emin olmaz.
    - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız şunu yazın: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Intune 'un Grup etiketi alanı, Azure AD cihazlarındaki OrderID özniteliğiyle eşlenir. Belirli bir grup etiketi (Azure AD cihaz OrderID) ile tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız, şunu yazmanız gerekir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Belirli bir Satın Alma Sipariş Kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` yazın
    
    **Gelişmiş kural** kodunu ekledikten sonra **Kaydet**’i seçin.
5. **Oluştur**’u seçin.  

## <a name="create-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma
Autopilot dağıtım profilleri, Autopilot cihazlarını yapılandırmak için kullanılır. Her kiracı için en fazla 350 profil oluşturabilirsiniz.
1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri** > **Profil Oluştur**’u seçin.
2. **Temel bilgiler** sayfasında, bir **ad** ve isteğe bağlı bir **Açıklama**yazın.

    ![Temel bilgiler sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-basics.png)

3. Atanan gruplardaki tüm cihazların otomatik olarak Autopilot'a dönüştürülmesini istiyorsanız **Hedeflenen tüm cihazları Autopilot'a dönüştür** seçeneğini **Evet** olarak ayarlayın. Atanan gruplardaki şirkete ait olmayan tüm Autopilot cihazları Autopilot dağıtım hizmetine kaydolacaktır. Kişiye ait cihazlar Autopilot 'e dönüştürülmeyecektir. Kaydın işlenmesi için 48 saat kadar bekleyin. Kaydı kaldırılıp sıfırlandığında Autopilot cihazı kaydeder. Bir cihaz bu şekilde kaydedildikten sonra bu seçeneğin devre dışı bırakılması veya profil atamasının kaldırılması cihazı Autopilot dağıtım hizmetinden kaldırmaz. Bunun yerine [cihazı doğrudan kaldırmanız](enrollment-autopilot.md#delete-autopilot-devices) gerekir.
4. **İleri**'yi seçin.
5. **Kullanıma hazır deneyim (OOBE)** sayfasında, **dağıtım modu**için şu iki seçenekten birini seçin:
    - **Kullanıcı temelli**: Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkilidir. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekir.
    - **Kendi kendine dağıtım (Önizleme)** : (Windows 10, sürüm 1809 veya üzeri gerektirir) bu profile sahip cihazlar, cihazı kaydeden Kullanıcı ile ilişkili değildir. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekmez. Bir cihaza ilişkili kullanıcı olmadığında, Kullanıcı tabanlı uyumluluk ilkeleri buna uygulanmaz. Kendi kendine Dağıtım modunu kullanırken, yalnızca cihazı hedefleyen uyumluluk ilkeleri uygulanır.

    ![OOBE sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-outofbox.png)

6. **Azure AD’ye farklı katıl** kutusunda **Azure AD katılımlı**’yı seçin.
7. Aşağıdaki seçenekleri yapılandırın:
    - **Son kullanıcı lisans sözleşmesi (EULA)** : (Windows 10, sürüm 1709 veya sonrası) EULA'yı kullanıcılara göstermek istiyorsanız seçin.
    - **Gizlilik ayarları**: Gizlilik ayarlarını kullanıcılara göstermek istiyorsanız seçin.
    >[!IMPORTANT]
    >Tanılama verileri ayarının varsayılan değeri Windows sürümleri arasında farklılık gösterir. Windows 10, sürüm 1903 çalıştıran cihazlarda, hazır olmayan deneyim sırasında varsayılan değer Full olarak ayarlanır. Daha fazla bilgi için bkz. [Windows Tanılama verileri](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) <br>
    
    - **Hesap değiştirme seçeneklerini gizle (Windows 10, sürüm 1809 veya üzeri gerektirir)** : hesabı Değiştir seçeneklerinin şirket oturum açma ve etki alanı hata sayfalarında görüntülenmesini engellemek için **Gizle** ' yi seçin. Bu seçenek, [Azure Active Directory’de şirket markasının yapılandırılmasını](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) gerektirir.
    - **Kullanıcı hesap türü**: Kullanıcı hesap türü **Yönetici** ya da **Standart** olarak seçin. Yerel yönetici grubuna ekleyerek cihazın yerel yönetici olmasını sağlayan kullanıcıya izin veririz. Kullanıcının cihazda varsayılan yönetici olarak etkinleştirilmedik.
    - **Beyaz Glove OOBE 'ye Izin ver** (Windows 10, sürüm 1903 veya üstünü gerektirir; [ek fiziksel gereksinimler](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): beyaz eldiven desteğe izin vermek için **Evet** ' i seçin.
    - **Cihaz adı şablonu uygulama** (Windows 10, sürüm 1809 veya üzeri ve Azure AD JOIN türü gerektirir): kayıt sırasında bir cihaz adlandırırken kullanılacak bir şablon oluşturmak için **Evet** ' i seçin. Adlar en çok 15 karakter olmalıdır; harf, rakam ve tire içerebilir. Ancak tamamen sayıdan oluşamaz. Donanıma özgü seri numarası eklemek için [%SERIAL% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanın. Veya x değerinin eklenecek basamak sayısına karşılık geldiği [%RAND:x% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanarak rastgele bir sayı dizesi ekleyin. Bir [etki alanı ekleme profilinde](windows-autopilot-hybrid.md#create-and-assign-a-domain-join-profile)karma cihazlara yönelik bir ön çözüm sağlayabilirsiniz. 
    - **Dil (Bölge)** \*: Cihazda kullanılacak dili seçin. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
    - **Klavyeyi otomatik olarak yapılandır**\*: bir **Dil (bölge)** seçiliyse, klavye seçimi sayfasını atlamak için **Evet** ' i seçin. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
8. **İleri**'yi seçin.
9. **Kapsam etiketleri** sayfasında isteğe bağlı olarak, bu profile uygulamak istediğiniz kapsam etiketlerini ekleyin. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](../fundamentals/scope-tags.md).
10. **İleri**'yi seçin.
11. **Atamalar** sayfasında, **ata**için **Seçili gruplar** ' ı seçin.

    ![Atamalar sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-assignments.png)

12. **Dahil edilecek grupları seç**' i seçin ve bu profile eklemek istediğiniz grupları seçin.
13. Herhangi bir grubu dışlamak istiyorsanız, **hariç tutulacak grupları seçin**' i seçin ve dışlamak istediğiniz grupları seçin.
14. **İleri**'yi seçin.
15. Profili oluşturmak için **gözden geçir + oluştur** sayfasında **Oluştur** ' u seçin.

    ![Inceleme sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Intune, atanan gruplardaki yeni cihazları düzenli olarak kontrol eder ve ardından bu cihazlara profil atama işlemini başlatır. Bu işlemin tamamlanması birkaç dakika sürebilir. Bir cihaz dağıtılmadan önce, bu işlemin tamamlandığından emin olun.  Profil durumunun "atanmamış" iken "atama" ve son olarak "atandı" olarak değiştirilmesini görmeniz gereken **cihaz kaydı**  > **Windows kayıt**  > **cihazları** ' na bakabilirsiniz.

## <a name="edit-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profilini düzenleme
Bir Autopilot dağıtım profili oluşturduktan sonra bu profilin bazı kısımlarını düzenleyebilirsiniz.   

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı**’nı seçin.
2. **Windows kaydı** altındaki **Windows Autopilot** bölümünde **Dağıtım Profilleri**’ni seçin.
3. Düzenlemek istediğiniz profili seçin.
4. Solda bulunan **Özellikler**’e tıklayarak dağıtım profilinin adını veya açıklamasını değiştirin. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.
5. OOBE ayarlarında değişiklik yapmak için **Ayarlar**’a tıklayın. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.

> [!NOTE]
> Profilde yapılan değişiklikler, bu profile atanmış cihazlara uygulanır. Ancak güncelleştirilmiş profil, Intune’a önceden kaydedilmiş cihazlarda cihaz sıfırlanıp yeniden kaydedilene kadar uygulanmaz.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows Autopilot atanmamış cihazlar için uyarılar  <!-- 163236 -->  

Uyarılar kaç Autopilot programı cihazının Autopilot dağıtım profili olmadığını gösterir. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows Autopilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz.

Atanmamış cihazlar için uyarı görmek istiyorsanız [Azure portalında Intune’da](https://aka.ms/intuneportal) **Cihaz kaydı** > **Genel bakış** > **Atanmamış cihazlar**’ı seçin.  

## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Belirli bir Autopilot cihazına kullanıcı atama

Belirli bir Autopilot cihazına kullanıcı atayabilirsiniz. Bu atama, Windows kurulumu sırasında [şirket markalı](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) oturum açma sayfasında Azure Active Directory’den bir kullanıcıyı önceden doldurur. Ayrıca özel bir karşılama adı ayarlamanıza imkan verir. Windows oturum açmayı önceden doldurmaz ve değiştirmez. Yalnızca lisanslı Intune kullanıcıları bu yolla atanabilir.

Önkoşullar: Azure Active Directory Şirket Portalı yapılandırılmış ve Windows 10, sürüm 1809 veya sonraki bir sürümü.

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > cihazı seçin **Kullanıcı ata**’yı seçin.

    ![Kullanıcı ata ekran görüntüsü](./media/enrollment-autopilot/assign-user.png)

2. Intune’u kullanmak için Azure lisanslı bir kullanıcıyı seçin ve **Seç**’e tıklayın.

    ![Kullanıcı seç ekran görüntüsü](./media/enrollment-autopilot/select-user.png)

3. **Kolay Ad** kutusuna kolay bir ad girin veya varsayılanı kabul edin. Bu dize, kullanıcı Windows kurulumu sırasında oturum açtığında görüntülenen kolay addır.

    ![Kolay ad ekran görüntüsü](./media/enrollment-autopilot/friendly-name.png)

4. **Tamam**’ı seçin.

## <a name="autopilot-deployments-report"></a>Autopilot dağıtımları raporu
Windows Autopilot aracılığıyla dağıtılan her bir cihazda ayrıntıları görebilirsiniz.
Raporu görmek için **Intune** 'a gidin ve **izleyici**altında **Autopilot dağıtımlar**' ı seçin.
Veriler dağıtımdan sonra 30 gün boyunca kullanılabilir.


## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Intune 'a kayıtlı olmayan Windows Autopilot cihazlarını silebilirsiniz:

- **Cihaz kaydı** > **Windows kaydı** > **cihazındaki**cihazları Windows Autopilot 'den silin. Silmek istediğiniz cihazları seçin ve **Sil**' i seçin. Windows Autopilot cihaz silme işleminin tamamlanması birkaç dakika sürebilir.

Bir cihazı kiracınızdan tamamen kaldırmak, Intune cihazını, Azure Active Directory cihazını ve Windows Autopilot cihaz kayıtlarını silmenizi gerektirir. Bu işlem, Intune 'dan yapılabilir:

1. Cihazlar Intune 'A kaydedildiyse, önce [bunları Intune tüm cihazlar dikey penceresinden silmelisiniz](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Cihazlarda Azure Active Directory cihazlarda cihazları**Azure AD cihazları** ** >  silin** .

3. **Cihaz kaydı** > **Windows kaydı** > **cihazındaki**cihazları Windows Autopilot 'den silin. Silmek istediğiniz cihazları seçin ve **Sil**' i seçin. Windows Autopilot cihaz silme işleminin tamamlanması birkaç dakika sürebilir.

## <a name="using-autopilot-in-other-portals"></a>Autopilot'ı diğer portallarda kullanma
Mobil cihaz yönetimi ile ilgilenmiyorsanız, Autopilot'ı diğer portallarda kullanabilirsiniz. Diğer portalları kullanmak bir seçenek olsa da Autopilot dağıtımlarınızı yönetmek için yalnızca Intune kullanmanızı öneririz. Intune'u ve başka bir portalı kullandığınızda Intune şunları yapamaz:  

- Intune’da oluşturulup başka bir portalda düzenlenmiş profillerdeki değişiklikleri görüntüleme
- Başka bir portalda oluşturulmuş profilleri eşitleme
- Başka bir portalda profil atamalarında yapılmış değişiklikleri görüntüleme
- Başka bir portalda yapılmış profil atamalarını eşitleme
- Başka bir portal üzerinden cihaz listesine yapılmış değişiklikleri görüntüleme

## <a name="windows-autopilot-for-existing-devices"></a>Mevcut cihazlar için Windows Autopilot

Configuration Manager aracılığıyla [mevcut cihazlar için Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanarak kaydederken Windows cihazlarını, ilişkilendirici kimliğine göre gruplayabilirsiniz. İlişkilendirici kimliği, Autopilot yapılandırma dosyasının bir parametresidir. [Azure Active Directory cihaz özniteliği enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices), otomatik olarak “OfflineAutopilotprofile-\<correlator ID\>” şeklinde ayarlanır. Bu, enrollmentprofileName özniteliği kullanılarak elde edilen ilişkilendirici kimliğine göre rastgele Azure Active Directory dinamik grupları oluşturulmasını sağlar.

>[!WARNING] 
> İlişkilendirici kimliği Intune’da önceden listelenmediğinden, cihaz herhangi bir ilişkilendirici kimliğini raporlayabilir. Kullanıcı, bir Autopilot veya Apple DEP profil adıyla eşleşen bir ilişkilendirici kimliği oluşturursa cihaz, enrollmentProfileName özniteliğine bağlı olarak herhangi bir dinamik Azure Active Directory cihaz grubuna eklenir. Bu çakışmayı önlemek için:
> - Her zaman enrollmentProfileName değerinin *tamamıyla* eşleşen dinamik grup kuralları oluşturun
> - Autopilot ve Apple DEP profillerini hiçbir zaman “OfflineAutopilotprofile-” ile başlayarak adlandırmayın.

## <a name="next-steps"></a>Sonraki adımlar
Windows Autopilot'ı kayıtlı Windows 10 cihazları için yapılandırdıktan sonra bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](../remote-actions/device-management.md)
