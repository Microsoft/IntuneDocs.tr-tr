---
title: Windows Autopilot kullanarak cihaz kaydetme
titleSuffix: Microsoft Intune
description: Windows Autopilot kullanarak Windows 10 cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 5fa3079c994a2e0ea2d587185e12c52085133f9c
ms.sourcegitcommit: 814d1d473de2de2e735efab826b1091de2b093f5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51025194"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Windows Autopilot'ı kullanarak Windows cihazları kaydetme  
Windows Autopilot cihaz kaydını basitleştirir. Özelleştirilmiş işletim sistemi görüntülerinin derlenmesi ve bakımı çok zaman alan bir işlemdir. Ayrıca bu özel işletim sistemi görüntülerini, yeni cihazları son kullanıcılarınıza vermeden önce kullanıma hazırlamak amacıyla cihazlara uygulamak için de zaman harcayabilirsiniz. Microsoft Intune ve Autopilot ile cihazlarda özel işletim sistemi görüntüleri oluşturmanıza, bu görüntüleri cihazlara uygulamanıza ve bunların bakımını yapmanıza gerek kalmadan son kullanıcılarınıza yeni cihazlar verebilirsiniz. Autopilot cihazlarını yönetmek için Intune kullandığınızda, kaydolduktan sonra ilkeleri, profilleri, uygulamaları ve diğer nesneleri yönetebilirsiniz. Faydalara, senaryolara ve önkoşullara genel bir bakış için bkz. [Windows Autopilot’a genel bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Önkoşullar
- [Windows otomatik kayıt etkin olmalıdır](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium aboneliği olmalıdır](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Intune’da içeri aktarma için CSV dosyasını alma

PowerShell cmdlet’ini nasıl kullanacağınızı anlamak için bu cmdlet’e göz atın.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo/1.3/Content/Get-WindowsAutoPilotInfo.ps1)

## <a name="add-devices"></a>Cihazları ekleme

Bilgilerini içeren CSV dosyasını içeri aktararak Windows Autopilot cihazlarını ekleyebilirsiniz.

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > **İçeri Aktar**’ı seçin.

    ![Windows Autopilot cihazlarının ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device.png)

2. **Windows Autopilot cihazları ekle** altında, eklemek istediğiniz cihazları listeleyen bir CSV dosyasına gözatın. Dosya; seri numaraları, Windows ürün kimlikleri, donanım karmaları ve cihazların isteğe bağlı sipariş kimliklerini listelemelidir.

    ![Windows Autopilot cihazları ekleme ekran görüntüsü](media/enrollment-autopilot/autopilot-import-device2.png)

3. Cihaz bilgilerini içeri aktarmayı başlatmak için **İçeri Aktar**'ı seçin. İçeri aktarma birkaç dakika sürebilir.

4. İçeri aktarma tamamlandıktan sonra **Cihaz kaydı** > **Windows kaydı** > **Windows Autopilot** > **Cihazlar** > **Eşitle**’yi seçin. Eşitlemenin sürdüğüne dair bir ileti görüntülenir. Kaç tane cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.

5. Yeni cihazları görmek için görüntüyü yenileyin.

## <a name="create-an-autopilot-device-group"></a>Bir Autopilot cihaz grubu oluşturma

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da **Gruplar** > **Yeni grup**’u seçin.
2. **Gruplar** dikey penceresinde:
    1. **Grup türü** olarak **Güvenlik**’i seçin.
    2. Bir **Grup adı** ve **Grup açıklaması** girin.
    3. **Üyelik türü** olarak **Atanan** veya **Dinamik Cihaz**’ı seçin.
3. Önceki adımda **Üyelik türü** olarak **Atanan**'ı seçtiyseniz, **Gruplar** dikey penceresinde **Üyeler**'i seçin ve gruba Autopilot cihazları ekleyin.
    Henüz kaydedilmemiş Autopilot cihazları, adın cihaz seri numarası olduğu cihazlardır.
4. Yukarıda **Üyelik türü** olarak **Dinamik Cihazlar**’ı seçtiyseniz **Gruplar** dikey penceresinde **Dinamik cihaz üyeleri**’ni seçin ve **Gelişmiş kural** kutusuna aşağıdaki kodlardan birini yazın.
    - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")` yazın
    - Belirli bir sipariş kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") ` yazın
    - Belirli bir Satın Alma Sipariş Kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` yazın
    
    **Gelişmiş kural** kodunu ekledikten sonra **Kaydet**’i seçin.
5. **Oluştur**’u seçin.  

## <a name="create-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma
Autopilot dağıtım profilleri, Autopilot cihazlarını yapılandırmak için kullanılır.
1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri** > **Profil Oluştur**’u seçin.
2. Bir **Ad** ve isteğe bağlı olarak bir **Açıklama** girin.
3. Atanan gruplardaki tüm cihazların otomatik olarak Autopilot'a dönüştürülmesini istiyorsanız **Hedeflenen tüm cihazları Autopilot'a dönüştür** seçeneğini **Evet** olarak ayarlayın. Atanan gruplardaki Autopilot olmayan tüm cihazlar Autopilot dağıtım hizmeti ile kaydedilir. Kaydın işlenmesi için 48 saat kadar bekleyin. Kaydı kaldırılıp sıfırlandığında Autopilot cihazı kaydeder. Bir cihaz bu şekilde kaydedildikten sonra bu seçeneğin devre dışı bırakılması veya profil atamasının kaldırılması cihazı Autopilot dağıtım hizmetinden kaldırmaz. Bunun yerine [cihazı doğrudan kaldırmanız](enrollment-autopilot.md#delete-autopilot-devices) gerekir.
4. **Dağıtım modu** için şu iki seçenekten birini belirtin:
    - **Kullanıcı temelli**: Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkilidir. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekir.
    - **Kendi kendine dağıtım (önizleme)**: (en son [Windows 10 Insider Önizleme Derlemesini](https://docs.microsoft.com/windows-insider/at-work-pro/) gerektirir) Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkili değildir. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekmez.
5. **Azure AD’ye farklı katıl** kutusunda **Azure AD katılımlı**’yı seçin.
6. **İlk kez çalıştırma deneyimi (OOBE)** öğesini seçin, aşağıdaki seçenekleri yapılandırın ve **Kaydet**’e tıklayın:
    - **Dil (Bölge)***: Cihazda kullanılacak dili seçin. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
    - **Klavyeyi otomatik olarak yapılandır***: Bir **Dil (Bölge)** seçildiyse, klavye seçimi sayfasını atlamak için **Evet** olarak ayarlayın. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
    - **Son kullanıcı lisans sözleşmesi (EULA)**: (Windows 10, sürüm 1709 veya sonrası) EULA'yı kullanıcılara göstermek istiyorsanız seçin.
    - **Gizlilik ayarları**: Gizlilik ayarlarını kullanıcılara göstermek istiyorsanız seçin.
    - **Hesap değiştirme seçeneklerini gizle (yalnızca Windows Insider)**: Şirket oturum açma ve etki alanı hatası sayfalarında hesap değiştirme seçeneklerinin görüntülenmesini engellemek için **Gizle** olarak ayarlayın. Bu seçenek, [Azure Active Directory’de şirket markasının yapılandırılmasını](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) gerektirir.
    - **Kullanıcı hesap türü**: Kullanıcı hesap türü **Yönetici** ya da **Standart** olarak seçin.
    - **Bilgisayar adı şablonunu uygula (yalnızca Windows Insider)**: Kaydetme sırasında cihazı adlandırırken kullanılacak bir şablon oluşturmak için **Evet** olarak ayarlayın. Adlar en çok 15 karakter olmalıdır; harf, rakam ve tire içerebilir. Ancak tamamen sayıdan oluşamaz. Donanıma özgü seri numarası eklemek için [%SERIAL% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanın. Veya x değerinin eklenecek basamak sayısına karşılık geldiği [%RAND:x% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanarak rastgele bir sayı dizesi ekleyin. 

6. Profili oluşturmak için **Oluştur**’a tıklayın. Autopilot dağıtım profili artık cihazlara atanmak üzere hazırdır.

*Hem **Dil (Bölge)** hem de **Klavyeyi otomatik olarak yapılandır** seçenekleri, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir (en son [Windows 10 Insider Önizleme Derlemesini](https://docs.microsoft.com/windows-insider/at-work-pro/) gerektirir).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Autopilot dağıtım profilini bir cihaz grubuna atama

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri**’ni ve daha sonra bir profili seçin.
2. Profile ait dikey pencerede **Atamalar**’ı seçin. 
3. **Grupları seçin**’e tıklayın, daha sonra **Grupları seçin** dikey penceresinde uygulamayı atamak istediğiniz grubu/grupları seçin ve **Seçin**’e tıklayın.

## <a name="edit-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profilini düzenleme
Bir Autopilot dağıtım profili oluşturduktan sonra bu profilin bazı kısımlarını düzenleyebilirsiniz.   

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı**’nı seçin.
2. **Windows kaydı** altındaki **Windows Autopilot** bölümünde **Dağıtım Profilleri**’ni seçin.
3. Düzenlemek istediğiniz profili seçin.
4. Solda bulunan **Özellikler**’e tıklayarak dağıtım profilinin adını veya açıklamasını değiştirin. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.
5. OOBE ayarlarında değişiklik yapmak için **Ayarlar**’a tıklayın. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.

> [!NOTE]
> Profilde yapılan değişiklikler, bu profile atanmış cihazlara uygulanır. Ancak güncelleştirilmiş profil, Intune’a önceden kaydedilmiş cihazlarda cihaz sıfırlanıp yeniden kaydedilene kadar uygulanmaz.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Windows Autopilot’ta atanmamış cihazlar için uyarılar  <!-- 163236 -->  

Uyarılar kaç Autopilot programı cihazının Autopilot dağıtım profili olmadığını gösterir. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows Autopilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz.


Atanmamış cihazlar için uyarı görmek istiyorsanız [Azure portalında Intune’da](https://aka.ms/intuneportal) **Cihaz kaydı** > **Genel bakış** > **Atanmamış cihazlar**’ı seçin.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Belirli bir Autopilot cihazına kullanıcı atama

Belirli bir Autopilot cihazına kullanıcı atayabilirsiniz. Bu atama, Windows kurulumu sırasında [şirket markalı](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) oturum açma sayfasında Azure Active Directory’den bir kullanıcıyı önceden doldurur. Ayrıca özel bir karşılama adı ayarlamanıza imkan verir. Windows oturum açmayı önceden doldurmaz ve değiştirmez. Yalnızca lisanslı Intune kullanıcıları bu yolla atanabilir.

Önkoşullar: Yapılandırılmış Azure Active Directory Şirket Portalı ve en son [Windows 10 Insider Önizleme Derlemesi](https://docs.microsoft.com/windows-insider/at-work-pro/).

1. [Azure portalında Intune’da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar** > cihazı seçin **Kullanıcı ata**’yı seçin.

    ![Kullanıcı ata ekran görüntüsü](media/enrollment-autopilot/assign-user.png)

2. Intune’u kullanmak için Azure lisanslı bir kullanıcıyı seçin ve **Seç**’e tıklayın.

    ![Kullanıcı seç ekran görüntüsü](media/enrollment-autopilot/select-user.png)

3. **Kolay Ad** kutusuna kolay bir ad girin veya varsayılanı kabul edin. Bu dize, kullanıcı Windows kurulumu sırasında oturum açtığında görüntülenen kolay addır.

    ![Kolay ad ekran görüntüsü](media/enrollment-autopilot/friendly-name.png)

4. **Tamam**’ı seçin.


## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

Kayıtlı olmayan Windows Autopilot cihazları silebilirsiniz.

1. Cihazlar Intune’a kayıtlıysa önce bunları [Azure Active Directory portalından silmeniz](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal) gerekir.

2. [Azure portalında Intune'da](https://aka.ms/intuneportal), **Cihaz kaydı** > **Windows kaydı** > **Cihazlar**'ı seçin.

3. **Windows Autopilot cihazları** bölümünde silmek istediğiniz cihazları, sonra da **Sil**’i seçin.

4. **Evet**'i seçerek silme işlemini onaylayın. Silme işlemi birkaç dakika sürebilir.

## <a name="using-autopilot-in-other-portals"></a>Autopilot'ı diğer portallarda kullanma
Mobil cihaz yönetimi ile ilgilenmiyorsanız, Autopilot'ı diğer portallarda kullanabilirsiniz. Diğer portalları kullanmak bir seçenek olsa da Autopilot dağıtımlarınızı yönetmek için yalnızca Intune kullanmanızı öneririz. Intune'u ve başka bir portalı kullandığınızda Intune şunları yapamaz:  

- Intune’da oluşturulup başka bir portalda düzenlenmiş profillerdeki değişiklikleri görüntüleme
- Başka bir portalda oluşturulmuş profilleri eşitleme
- Başka bir portalda profil atamalarında yapılmış değişiklikleri görüntüleme
- Başka bir portalda yapılmış profil atamalarını eşitleme
- Başka bir portal üzerinden cihaz listesine yapılmış değişiklikleri görüntüleme

## <a name="windows-autopilot-for-existing-devices"></a>Mevcut cihazlar için Windows Autopilot

Configuration Manager aracılığıyla [mevcut cihazlar için Autopilot](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) kullanarak kaydederken Windows cihazlarını, ilişkilendirici kimliğine göre gruplayabilirsiniz. İlişkilendirici kimliği, Autopilot yapılandırma dosyasının bir parametresidir. [Azure Active Directory cihaz özniteliği enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects), otomatik olarak “OfflineAutopilotprofile-\<correlator ID\>” şeklinde ayarlanır. Bu, enrollmentprofileName özniteliği kullanılarak elde edilen ilişkilendirici kimliğine göre rastgele Azure Active Directory dinamik grupları oluşturulmasını sağlar.

>[!WARNING] 
> İlişkilendirici kimliği Intune’da önceden listelenmediğinden, cihaz herhangi bir ilişkilendirici kimliğini raporlayabilir. Kullanıcı, bir Autopilot veya Apple DEP profil adıyla eşleşen bir ilişkilendirici kimliği oluşturursa cihaz, enrollmentProfileName özniteliğine bağlı olarak herhangi bir dinamik Azure Active Directory cihaz grubuna eklenir. Bu çakışmayı önlemek için:
> - Her zaman enrollmentProfileName değerinin *tamamıyla* eşleşen dinamik grup kuralları oluşturun
> - Autopilot ve Apple DEP profillerini hiçbir zaman “OfflineAutopilotprofile-” ile başlayarak adlandırmayın.

## <a name="next-steps"></a>Sonraki adımlar
Windows Autopilot'ı kayıtlı Windows 10 cihazları için yapılandırdıktan sonra bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](https://docs.microsoft.com/intune/device-management)
