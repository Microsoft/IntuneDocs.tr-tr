---
title: Windows Autopilot kullanarak cihazları kaydetme
titleSuffix: Microsoft Intune
description: Windows Autopilot kullanarak Windows 10 cihazlarını kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2ebca165c067afbc3d830e5f75ac9f8e29effb2
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237223"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Windows Autopilot kullanarak Windows cihazlarını Intune 'A kaydetme  
Windows Autopilot, cihazların Intune 'A kaydedilmesini basitleştirir. Özelleştirilmiş işletim sistemi görüntülerinin oluşturulması ve saklanması zaman alan bir işlemdir. Ayrıca, bu özel işletim sistemi görüntülerini Son kullanıcılarınıza vermeden önce kullanıma hazırlamak üzere yeni cihazlara uygulamak için zaman harcamanız gerekebilir. Microsoft Intune ve Autopilot ile, aygıtlara özel işletim sistemi görüntüleri oluşturma, bakımını yapma ve uygulama gereksinimi olmadan yeni cihazlara Son kullanıcılarınıza izin verebilirsiniz. Autopilot cihazlarını yönetmek için Intune kullandığınızda ilkeleri, profilleri, uygulamaları ve daha fazlasını kaydolduktan sonra yönetebilirsiniz. Avantajlar, senaryolar ve önkoşullara genel bakış için bkz. [Windows Autopilot 'e genel bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

Dört tür Autopilot dağıtımı vardır:
- Kiosks, dijital imza veya paylaşılan bir cihaz için [kendi kendine dağıtım modu](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying)
- [Teknik İnceleme](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) , iş ORTAKLARıNıN veya BT personelinin,[mevcut cihazlara yönelik](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) olarak Windows 10 ' un en son sürümünü kolayca dağıtmanıza olanak sağlayan bir Windows 10 PC 'nin ön sağlamasını sağlar
- Geleneksel kullanıcılar için [Kullanıcı odaklı mod](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) . 


## <a name="prerequisites"></a>Prerequisites
- [Intune aboneliği](../fundamentals/licenses.md)
- [Windows otomatik kaydı etkin](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium aboneliği](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Intune 'da Içeri aktarma için CSV alma

Daha fazla bilgi için bkz. PowerShell cmdlet 'ini anlama.

- [Get-Windowsautopilotınfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Cihaz Ekle

Windows Autopilot cihazlarını, bilgilerine sahip bir CSV dosyasını içeri aktararak ekleyebilirsiniz.

1. [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Windows kaydı** > **içeri aktarma**@no__t**cihazları**' nı seçin.

    ![Windows Autopilot cihazlarının ekran görüntüsü](./media/enrollment-autopilot/autopilot-import-device.png)

2. **Windows Autopilot cihazları Ekle**altında, eklemek istediğiniz cihazları LISTELEYEREK bir CSV dosyasına gidin. CSV dosyası seri numaralarını, Windows ürün kimliklerini, donanım karmalarını, isteğe bağlı Grup etiketlerini ve isteğe bağlı olarak atanmış kullanıcıyı listelemelidir. Listede en fazla 500 satır olabilir. Aşağıda gösterilen üst bilgi ve satır biçimini kullanın:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Windows Autopilot cihazları ekleme ekran görüntüsü](./media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > Bir kullanıcı atamak için CSV yükleme kullandığınızda, geçerli UPN 'ler atadığınızdan emin olun. Geçersiz bir UPN (yanlış Kullanıcı adı) atarsanız, geçersiz atamayı kaldırana kadar cihazınız erişilemez durumda olabilir. CSV yükleme sırasında, **Atanan Kullanıcı** sütununda gerçekleştirdiğimiz tek doğrulama, etki alanı adının geçerli olduğunu denetliyoruz. Mevcut veya doğru bir Kullanıcı atadığınızdan emin olmak için tek tek UPN doğrulaması gerçekleştiremedik.

3. Cihaz bilgilerini içeri aktarmaya başlamak için **Içeri aktar** ' ı seçin. İçeri aktarma işlemi birkaç dakika sürebilir.

4. İçeri aktarma işlemi tamamlandıktan sonra, **cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **cihazları** > **eşitleme**' yi seçin. Eşitlemenin devam ettiğini gösteren bir ileti görüntülenir. Kaç cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakika sürebilir.

5. Yeni cihazları görmek için görünümü yenileyin.

## <a name="create-an-autopilot-device-group"></a>Autopilot cihaz grubu oluşturma

1. [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **gruplar** > **Yeni Grup**' u seçin.
2. **Grup** dikey penceresinde:
    1. **Grup türü**için **güvenlik**' i seçin.
    2. Bir **Grup adı** ve **Grup açıklaması**yazın.
    3. **Üyelik türü**için **atanan** ya da **dinamik cihaz**' ı seçin.
3. Önceki adımda **üyelik türü** için **atandı** ' ı seçtiyseniz, **Grup** dikey penceresinde **Üyeler** ' i seçin ve gruba Autopilot cihazları ekleyin.
    Henüz kayıtlı olmayan Autopilot cihazları, adın cihazın seri numarasına eşit olduğu cihazlardır.
4. Yukarıdaki **üyelik türü** Için **dinamik cihazlar** ' ı seçtiyseniz, **Grup** dikey penceresinde **dinamik cihaz üyeleri** ' ni seçin ve **Gelişmiş kural** kutusuna aşağıdaki koddan birini yazın. Yalnızca Autopilot cihazları tarafından sahip olan öznitelikleri hedeflerse, yalnızca Autopilot cihazları bu kurallar tarafından toplanır.
    - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız şunu yazın: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Intune 'un Grup etiketi alanı, Azure AD cihazlarındaki OrderID özniteliğiyle eşlenir. Belirli bir grup etiketine sahip tüm Autopilot cihazlarınızı (Azure AD cihaz OrderID) içeren bir grup oluşturmak istiyorsanız, şunu yazmanız gerekir: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Belirli bir satın alma siparişi KIMLIĞINE sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız şunu yazın: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    **Gelişmiş kural** kodu ekledikten sonra **Kaydet**' i seçin.
5. **Oluştur**' a tıklayın.  

## <a name="create-an-autopilot-deployment-profile"></a>Autopilot dağıtım profili oluşturma
Autopilot dağıtım profilleri, Autopilot cihazlarını yapılandırmak için kullanılır.
1. [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **Windows kaydı** > **dağıtım profilleri** > **Profil oluştur**' u seçin.
2. **Temel bilgiler** sayfasında, bir **ad** ve isteğe bağlı bir **Açıklama**yazın.

    ![Temel bilgiler sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-basics.png)

3. Atanan gruplardaki tüm cihazların otomatik olarak Autopilot ' e dönüştürülmesini istiyorsanız, **tüm hedeflenen cihazları Autopilot** ' ye Dönüştür ' i **Evet**olarak ayarlayın. Atanan gruplardaki şirkete ait olmayan tüm Autopilot cihazları Autopilot dağıtım hizmetine kaydolacaktır. Kişiye ait cihazlar Autopilot 'e dönüştürülmeyecektir. Kaydın işlenmesine 48 saat izin verin. Cihazın kaydı kaldırılırken ve sıfırlandığında, Autopilot onu kaydeder. Bir cihaz bu şekilde kaydedildikten sonra, bu seçeneği devre dışı bırakmak veya profil atamasını kaldırmak, cihazı Autopilot dağıtım hizmetinden kaldırmaz. Bunun yerine [cihazı doğrudan kaldırmanız](enrollment-autopilot.md#delete-autopilot-devices)gerekir.
4. **İleri ' yi**seçin.
5. **Kullanıma hazır deneyim (OOBE)** sayfasında, **dağıtım modu**için şu iki seçenekten birini seçin:
    - **Kullanıcı odaklı**: bu profile sahip cihazlar, cihazı kaydeden Kullanıcı ile ilişkilendirilir. Cihazı kaydetmek için Kullanıcı kimlik bilgileri gereklidir.
    - **Kendi kendine dağıtım (Önizleme)** : (Windows 10, sürüm 1809 veya üzeri gerektirir) bu profile sahip cihazlar, cihazı kaydeden Kullanıcı ile ilişkili değildir. Cihazı kaydetmek için Kullanıcı kimlik bilgileri gerekli değildir. Bir cihaza ilişkili kullanıcı olmadığında, Kullanıcı tabanlı uyumluluk ilkeleri buna uygulanmaz. Kendi kendine Dağıtım modunu kullanırken, yalnızca cihazı hedefleyen uyumluluk ilkeleri uygulanır.

    ![OOBE sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-outofbox.png)

6. **Azure AD 'ye katıl** kutusunda **Azure AD 'ye katılmış**' i seçin.
7. Aşağıdaki seçenekleri yapılandırın:
    - **Son Kullanıcı Lisans Sözleşmesi (EULA)** : (Windows 10, sürüm 1709 veya ÜZERI) EULA 'yı kullanıcılara göstermek istiyorsanız seçin.
    - **Gizlilik ayarları**: kullanıcılara gizlilik ayarlarını göstermek istiyorsanız seçin.
    >[!IMPORTANT]
    >Tanılama verileri ayarının varsayılan değeri Windows sürümleri arasında farklılık gösterir. Windows 10, sürüm 1903 çalıştıran cihazlarda, hazır olmayan deneyim sırasında varsayılan değer Full olarak ayarlanır. Daha fazla bilgi için bkz. [Windows Tanılama verileri](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) <br>
    
    - **Hesap değiştirme seçeneklerini gizle (Windows 10, sürüm 1809 veya üzeri gerektirir)** : hesabı Değiştir seçeneklerinin şirket oturum açma ve etki alanı hata sayfalarında görüntülenmesini engellemek için **Gizle** ' yi seçin. Bu seçenek [, Azure Active Directory ' de şirket markasının yapılandırılmasını](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding)gerektirir.
    - **Kullanıcı hesabı türü**: kullanıcının hesap türünü (**yönetici** veya **Standart** Kullanıcı) seçin. Yerel yönetici grubuna ekleyerek cihazın yerel yönetici olmasını sağlayan kullanıcıya izin veririz. Kullanıcının cihazda varsayılan yönetici olarak etkinleştirilmedik.
    - **Beyaz Glove OOBE 'ye Izin ver** (Windows 10, sürüm 1903 veya üstünü gerektirir; [ek fiziksel gereksinimler](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): beyaz eldiven desteğe izin vermek için **Evet** ' i seçin.
    - **Cihaz adı şablonu uygulama** (Windows 10, sürüm 1809 veya üzeri ve Azure AD JOIN türü gerektirir): kayıt sırasında bir cihaz adlandırırken kullanılacak bir şablon oluşturmak için **Evet** ' i seçin. Adlar 15 karakter veya daha az olmalı ve harflerden, sayılardan ve kısa çizgilerden oluşabilir. Adlar tüm sayılar olamaz. Donanıma özgü bir seri numarası eklemek için [% SERIAL% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanın. Ya da [% S_SAYI_ÜRET: x% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanarak rastgele bir sayı dizesi ekleyin, burada x eklenecek basamak sayısına eşittir. Bir [etki alanı ekleme profilinde](windows-autopilot-hybrid.md#create-and-assign-a-domain-join-profile)karma cihazlara yönelik bir ön çözüm sağlayabilirsiniz. 
    - **Dil (bölge)** \*: cihaz için kullanılacak dili seçin. Bu seçenek yalnızca **dağıtım modu**Için **kendi kendine dağıtımı** ' nı seçerseniz kullanılabilir.
    - **Klavyeyi otomatik olarak yapılandır**\*: bir **Dil (bölge)** seçiliyse, klavye seçimi sayfasını atlamak için **Evet** ' i seçin. Bu seçenek yalnızca **dağıtım modu**Için **kendi kendine dağıtımı** ' nı seçerseniz kullanılabilir.
8. **İleri ' yi**seçin.
9. **Kapsam etiketleri** sayfasında isteğe bağlı olarak, bu profile uygulamak istediğiniz kapsam etiketlerini ekleyin. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](../fundamentals/scope-tags.md).
10. **İleri ' yi**seçin.
11. **Atamalar** sayfasında, **ata**için **Seçili gruplar** ' ı seçin.

    ![Atamalar sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-assignments.png)

12. **Dahil edilecek grupları seç**' i seçin ve bu profile eklemek istediğiniz grupları seçin.
13. Herhangi bir grubu dışlamak istiyorsanız, **hariç tutulacak grupları seçin**' i seçin ve dışlamak istediğiniz grupları seçin.
14. **İleri ' yi**seçin.
15. Profili oluşturmak için **gözden geçir + oluştur** sayfasında **Oluştur** ' u seçin.

    ![Inceleme sayfasının ekran görüntüsü](./media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Intune, atanan gruplardaki yeni cihazları düzenli olarak kontrol eder ve ardından bu cihazlara profil atama işlemini başlatır. Bu işlemin tamamlanması birkaç dakika sürebilir. Bir cihaz dağıtılmadan önce, bu işlemin tamamlandığından emin olun.  "Atanmamış" iken "atama" ve son olarak "atandı" olarak bir profil durumu değişikliğini görmeniz gereken **cihaz kaydı** > **Windows kaydı**@no__t **-3 cihaz** ' ın altına bakabilirsiniz.

## <a name="edit-an-autopilot-deployment-profile"></a>Autopilot dağıtım profilini düzenleme
Bir Autopilot dağıtım profili oluşturduktan sonra, dağıtım profilinin belirli kısımlarını düzenleyebilirsiniz.   

1. [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı**' nı seçin.
2. **Windows kaydı**altında, **Windows Autopilot** bölümünde **dağıtım profilleri**' ni seçin.
3. Düzenlemek istediğiniz profili seçin.
4. Dağıtım profilinin adını veya açıklamasını değiştirmek için soldaki **Özellikler** ' e tıklayın. Değişiklik yaptıktan sonra **Kaydet** ' e tıklayın.
5. OOBE ayarlarında değişiklik yapmak için **Ayarlar** ' a tıklayın. Değişiklik yaptıktan sonra **Kaydet** ' e tıklayın.

> [!NOTE]
> Profilde yapılan değişiklikler, bu profile atanmış cihazlara uygulanır. Ancak, güncelleştirilmiş profil, cihaz sıfırlanıp yeniden kaydedilinceye kadar zaten Intune 'a kayıtlı olan bir cihaza uygulanmaz.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows Autopilot atanmamış cihazlar için uyarılar  <!-- 163236 -->  

Uyarılar, kaç Autopilot program aygıtının Autopilot dağıtım profiline sahip olduğunu gösterir. Profil oluşturmak ve bunları atanmamış cihazlara atamak için uyarıdaki bilgileri kullanın. Uyarıya tıkladığınızda, Windows Autopilot cihazlarının tam listesini ve bunlarla ilgili ayrıntılı bilgileri görürsünüz.

Atanmamış cihazlara yönelik uyarıları görmek için [Azure Portal Intune](https://aka.ms/intuneportal)'Da, **cihaz kaydı** > **genel bakış** > **atanmamış cihaz**' ı seçin.  

## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Belirli bir Autopilot cihazına Kullanıcı atama

Bir kullanıcıyı belirli bir Autopilot cihazına atayabilirsiniz. Bu atama, Windows kurulumu sırasında [Şirket markalı](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) oturum açma sayfasında bir kullanıcıyı Azure Active Directory ön doldurur. Ayrıca, özel bir karşılama adı ayarlamanıza olanak sağlar. Windows oturumunu önceden doldurmaz veya değiştirmez. Yalnızca lisanslı Intune kullanıcıları bu şekilde atanabilir.

Önkoşullar: Azure Active Directory Şirket Portalı yapılandırılmış ve Windows 10, sürüm 1809 veya sonraki bir sürümü.

1. [Azure Portal Intune](https://aka.ms/intuneportal)' da, **cihaz kaydı** > **Windows kaydı** > **cihazları** ' nı seçin > Cihaz > **Kullanıcı ata**' yı seçin.

    ![Kullanıcı ata 'nın ekran görüntüsü](./media/enrollment-autopilot/assign-user.png)

2. Intune 'u kullanmak için lisanslı bir Azure kullanıcısı seçin ve **Seç**' i seçin.

    ![Select User 'ın ekran görüntüsü](./media/enrollment-autopilot/select-user.png)

3. **Kullanıcı kolay adı** kutusuna bir kolay ad yazın veya varsayılanı kabul edin. Bu dize, Kullanıcı Windows kurulumu sırasında oturum açtığında görüntülenen kolay addır.

    ![Kolay ad ekran görüntüsü](./media/enrollment-autopilot/friendly-name.png)

4. **Tamam ' ı**seçin.


## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını Sil

Intune 'a kayıtlı olmayan Windows Autopilot cihazlarını silebilirsiniz:

- **Cihaz kaydı** > **Windows kaydı** > **cihazındaki**cihazları Windows Autopilot 'den silin. Silmek istediğiniz cihazları seçin ve **Sil**' i seçin. Windows Autopilot cihaz silme işleminin tamamlanması birkaç dakika sürebilir.

Bir cihazı kiracınızdan tamamen kaldırmak, Intune cihazını, Azure Active Directory cihazını ve Windows Autopilot cihaz kayıtlarını silmenizi gerektirir. Bu işlem, Intune 'dan yapılabilir:

1. Cihazlar Intune 'A kaydedildiyse, önce [bunları Intune tüm cihazlar dikey penceresinden silmelisiniz](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Cihazlarda Azure Active Directory cihazlarındaki cihazları **silme @no__t-** 1**Azure AD cihazlarıdır**.

3. **Cihaz kaydı** > **Windows kaydı** > **cihazındaki**cihazları Windows Autopilot 'den silin. Silmek istediğiniz cihazları seçin ve **Sil**' i seçin. Windows Autopilot cihaz silme işleminin tamamlanması birkaç dakika sürebilir.

## <a name="using-autopilot-in-other-portals"></a>Diğer portallarda Autopilot kullanma
Mobil cihaz yönetimi ile ilgilenmiyorsanız, Autopilot 'i diğer portallarda kullanabilirsiniz. Diğer portalların kullanılması bir seçenektir, ancak Autopilot dağıtımlarını yönetmek için Intune 'U kullanmanızı öneririz. Intune ve başka bir portal kullandığınızda Intune şunları yapamaz:  

- Intune 'da oluşturulan, ancak başka bir portalda düzenlenen profillerde yapılan değişiklikleri görüntüle
- Başka bir portalda oluşturulan profilleri eşitler
- Başka bir portalda yapılan profil atamalarındaki değişiklikleri görüntüleme
- Başka bir portalda yapılan profil atamalarını eşitler
- Başka bir portalda cihaz listesinde yapılan değişiklikleri görüntüle

## <a name="windows-autopilot-for-existing-devices"></a>Mevcut cihazlar için Windows Autopilot

Configuration Manager aracılığıyla [mevcut cihazlarda Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanarak Windows cihazlarını BIR ilişkilendirici kimliğiyle gruplandırabilirsiniz. İlişkilendirici KIMLIĞI, Autopilot yapılandırma dosyasının bir parametresidir. [Azure AD cihaz özniteliği KayıtAdı](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) "OfflineAutopilotprofile-\<ILIŞKILENDIRICI kimliği @ no__t-2" olarak ayarlanır. Bu, Azure AD dinamik gruplarının, kayıt KIMLIĞI tabanlı olarak Kayıtlıproprofilename özniteliği kullanılarak oluşturulmasına olanak sağlar.

>[!WARNING] 
> İlişkilendirici KIMLIĞI Intune 'da önceden listelenmediğinden, cihaz istedikleri herhangi bir ilişkilendirici KIMLIĞINI rapor edebilir. Kullanıcı, bir Autopilot veya Apple DEP profili adıyla eşleşen bir ilişkilendirici KIMLIĞI oluşturursa, cihaz, KayıtAdı özniteliğini temel alarak herhangi bir dinamik Azure AD cihaz grubuna eklenir. Bu çakışmayı önlemek için:
> - Her zaman, *Tüm* KayıtAdı değeri ile eşleşen dinamik grup kuralları oluşturun
> - "OfflineAutopilotprofile-" ile başlayan Autopilot veya Apple DEP profillerinin hiçbir şekilde adı yoktur.

## <a name="next-steps"></a>Sonraki adımlar
Kayıtlı Windows 10 cihazları için Windows Autopilot yapılandırdıktan sonra, bu cihazları yönetmeyi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](../remote-actions/device-management.md)
