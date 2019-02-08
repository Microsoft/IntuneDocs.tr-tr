---
title: Kayıt için hibrit Azure AD'ye katılmış cihazlar - Windows Autopilot
titleSuffix: ''
description: Karma Azure kaydetmek için Windows Autopilot'ı kullanmayı Microsoft Intune AD alanına katılmış cihazlar.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35492b94e38d482f5ee59385453bac54f434223d
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55845338"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot-preview"></a>Dağıtma hibrit Azure AD'ye katılmış cihazlar, Intune ve Windows Autopilot (Önizleme) kullanarak
Karma Azure Active Directory (Azure AD) ayarlamak için Intune ve Windows Autopilot kullanabilirsiniz-katılmış cihazlar. Bunu yapmak için bu makaledeki adımları izleyin.

## <a name="prerequisites"></a>Önkoşullar

Başarılı bir şekilde yapılandırmak, [hibrit Azure AD'ye katılmış cihazları](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan). Mutlaka [cihaz kaydınızı doğrulayın]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) Get-MsolDevice cmdlet'ini kullanarak.

Kaydedilecek cihazlar ayrıca:
- [Ekim 2018 güncelleştirmesiyle](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/) Windows 10 çalıştırmalıdır.
- İnternet erişimine sahip olmalıdır.
- Active Directory’nize erişime sahip olmalıdır (VPN bağlantısı desteklenmez).
- Kullanıma hazır deneyimi (OOBE) geçeriz.

## <a name="set-up-windows-10-automatic-enrollment"></a>Windows 10 otomatik kaydını ayarlama

1. Oturum [Azure portalında](https://portal.azure.com) seçin sol bölmede **Azure Active Directory**.

   ![Azure portalı](./media/auto-enroll-azure-main.png)

1. **Mobility (MDM ve MAM)** seçeneğini belirleyin.

   ![Azure Active Directory bölmesi](./media/auto-enroll-mdm.png)

1. **Microsoft Intune**'u seçin.

   ![Mobility (MDM ve MAM) bölmesi](./media/auto-enroll-intune.png)

1. Intune ve Windows kullanarak Azure AD'ye katılmış cihazları dağıtmak kullanıcılar dahil bir grubun üyesi olduğundan emin olun, **MDM kullanıcı kapsamı**.

   ![Mobility (MDM ve MAM) yapılandırma bölmesi](./media/auto-enroll-scope.png)

1. Varsayılan değerleri kullanmak **kullanım koşulları MDM URL'si**, **MDM bulma URL'si**, ve **MDM uyumluluk URL'si** kutuları tıklayın ve ardından **Kaydet**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Kuruluş Birimi’nde bilgisayar hesabı sınırını artırma

Active Directory'niz için Intune bağlayıcısını şirket içi Active Directory etki alanında autopilot kaydı yapılmış bilgisayarlar oluşturur. Intune Bağlayıcısı'nı barındıran bilgisayarın etki alanı içinde bilgisayar nesneleri oluşturmak için haklarınız olmalıdır. 

Bazı etki alanlarında bilgisayarları oluşturmak için haklarına izin verilmez. Ayrıca, etki alanları tüm kullanıcı ve bilgisayar nesneleri oluşturmak için temsilci haklarına olmayan bilgisayarlar için geçerli bir yerleşik sınırı (varsayılan değer olan 10) vardır. Bu nedenle, kuruluş birimi Intune bağlayıcısını barındıran bilgisayarlar için temsilci haklarına ihtiyacınız olduğu hibrit Azure AD'ye katılmış cihazları oluşturulur.

Bilgisayarlar oluşturma hakkı verilmiş bir kuruluş birimi eşleşmesi gerekir:
- Etki alanına profilinde girilen kuruluş birimi.
- Hiçbir profili seçilmişse, bilgisayarın etki alanına etki alanınız için ad.

1. Açık **Active Directory Kullanıcıları ve Bilgisayarları (DSA.msc)**.

1. Azure karma oluşturmak için kullanacağınız kuruluş birimini sağ AD alanına katılmış bilgisayarları ve ardından **denetim temsilcisi**.

    ![Denetim Temsilcisi komutu](media/windows-autopilot-hybrid/delegate-control.png)

1. İçinde **denetim temsilcisi** seçin **sonraki** > **Ekle** > **nesne türlerini**.

1. İçinde **nesne türlerini** bölmesinde **bilgisayarlar** onay kutusunu işaretleyin ve ardından **Tamam**.

    ![Nesne türleri bölmesi](media/windows-autopilot-hybrid/object-types-computers.png)

1. İçinde **kullanıcıları, bilgisayarları veya grupları** bölmesinde, **Seçilecek nesne adlarını girin** kutusuna, bağlayıcısının yüklendiği bilgisayarın adını girin.

    ![Kullanıcıları, bilgisayarları veya grupları bölmesi](media/windows-autopilot-hybrid/enter-object-names.png)

1. Seçin **Adları Denetle** giriş doğrulamak için seçin **Tamam**ve ardından **sonraki**.

1. Seçin **temsilci atamak için özel bir görev oluşturmak** > **sonraki**.

1. Seçin **yalnızca aşağıdaki nesneleri klasöründe** onay kutusunu işaretleyin ve ardından **bilgisayar nesneleri**, **bu klasörde seçili nesneler oluşturma**, ve  **Bu klasör içinde seçilen nesneleri silmek** onay kutuları.

    ![Active Directory nesne türü bölmesi](media/windows-autopilot-hybrid/only-following-objects.png)
    
1. **İleri**’yi seçin.

1. Altında **izinleri**seçin **tam denetim** onay kutusu.  
    Bu eylem, diğer tüm seçenekler seçer.

    ![İzinler bölmesi](media/windows-autopilot-hybrid/full-control.png)

1. Seçin **sonraki**ve ardından **son**.

## <a name="install-the-intune-connector"></a>Intune Bağlayıcısını yükleme

Active Directory için Intune bağlayıcısını Windows Server 2016 çalıştıran bir bilgisayarda yüklü veya üzeri olmalıdır. Bilgisayarın ayrıca internet ve Active Directory erişimi olmalıdır. Birden fazla Active Directory etki alanını desteklemek üzere ölçek ve kullanılabilirliği artırmak için ortamınıza birden fazla bağlayıcı yükleyebilirsiniz. Diğer Intune bağlayıcılar çalışmıyor bir sunucuda bağlayıcı yüklemeniz önerilir.

1. Bir dil paketi yüklü ve açıklandığı gibi yapılandırılmış olduğundan emin olun [Intune Bağlayıcısı (Önizleme) dil gereksinimleri](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. İçinde [Intune](https://aka.ms/intuneportal)seçin **cihaz kaydı** > **Windows kayıt** > **için Active Directory (Intune Bağlayıcısı Önizleme)** > **bağlayıcı Ekle**. 
3. Bir bağlayıcı indirmek için yönergeleri izleyin.
4. İndirilen bağlayıcı Kurulumu dosyasını açın *ODJConnectorBootstrapper.exe*Bağlayıcısı'nı yüklemek için.
5. Kurulum sonunda seçin **yapılandırma**.
6. Seçin **oturum**.
7. Kullanıcı genel yönetici veya Intune Yönetici rolü kimlik bilgilerini girin.  
   Kullanıcı hesabı atanmış Intune lisansına sahip olmalıdır.
8. Git **cihaz kaydı** > **Windows kayıt** > **Active Directory (Önizleme) için Intune bağlayıcısını**ve ardından onaylayın bağlantı durumu **etkin**.

> [!NOTE]
> Bağlayıcı oturum açtıktan sonra birkaç dakika içinde görüntülenecek sürebilir [Intune](https://aka.ms/intuneportal). Yalnızca bu başarılı bir şekilde Intune hizmetiyle iletişim kurabildiğinde görünür.

### <a name="configure-web-proxy-settings"></a>Web proxy ayarlarını yapılandırma

Ağ ortamınızda bir web proxy varsa, başvurarak Active Directory için Intune bağlayıcısını düzgün çalıştığından emin olmak [iş mevcut şirket içi proxy sunucuları](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Bir cihaz grubu oluşturma
1. İçinde [Intune](https://aka.ms/intuneportal)seçin **grupları** > **yeni grup**.

1. İçinde **grubu** bölmesinde aşağıdakileri yapın:

    a. İçin **grup türü**seçin **güvenlik**.

    b. Girin bir **grup adı** ve **Grup açıklaması**.

    c. Seçin bir **üyelik türü**.

1. Seçtiyseniz **dinamik cihazları** üyelik türü için içinde **grubu** bölmesinde **dinamik cihaz üyeleri** ve daha sonra **Gelişmiş kural** kutusunda, aşağıdakilerden birini yapın:
    - Tüm Autopilot cihazları içeren bir grup oluşturmak için girin `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - Belirli bir sıraya göre Kimliğine sahip tüm Autopilot cihazları içeren bir grup oluşturmak için girin `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`.
    - Belirli bir satın alma siparişi kimliği ile tüm Autopilot cihazları içeren bir grup oluşturmak için girin `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
1. **Kaydet**’i seçin.

1. **Oluştur**’u seçin.  

## <a name="register-your-autopilot-devices"></a>Autopilot cihazlarınızı kaydetme

Autopilot cihazları kaydetmek için aşağıdaki yöntemlerden birini seçin.

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Daha önceden kaydedilmiş Autopilot cihazları kaydetme

1. **Hedeflenen cihazların tümünü Autopilot’a dönüştür** ayarı **Evet** olarak belirlenmiş bir Autopilot dağıtım profili oluşturun. 
2. Autopilot ile otomatik olarak kaydetmek istediğiniz üyeleri içeren bir gruba profil atayın.

Daha fazla bilgi için bkz. [Bir Autopilot dağıtım profili oluşturma](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Daha önceden kaydedilmemiş Autopilot cihazları kaydetme

Henüz kaydedilmemiş cihazlarınız varsa, bunları kendiniz kaydedebilirsiniz. Daha fazla bilgi için bkz. [Cihaz ekleme](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>OEM cihazlarını kaydetme

Yeni cihaz satın alırken bazı OEM’ler cihazları sizin için kaydedebilir. Daha fazla bilgi için bkz. [Windows Autopilot sayfası](http://aka.ms/WindowsAutopilot).

Autopilot cihazlarınızı olduğunda *kayıtlı*, Intune'a kaydolduktan önce üç yerde (adlarla seri numaralarına ayarlayın) görüntülenme:
- **Autopilot cihazları** Azure portalında ıntune bölmesi. Seçin **cihaz kaydı** > **Windows kayıt** > **cihazları**.
- **Azure AD cihazları** Azure portalında ıntune bölmesi. Seçin **cihazları** > **Azure AD cihazları**.
- **Azure AD tüm cihazlar** seçerek Azure portalında Azure Active Directory bölmesinde **cihazları** > **tüm cihazlar**.

Sonra Autopilot cihazlar, *kayıtlı*, dört yerde görüntülenir:
- **Autopilot cihazları** Azure portalında ıntune bölmesi. Seçin **cihaz kaydı** > **Windows kayıt** > **cihazları**.
- **Azure AD cihazları** Azure portalında ıntune bölmesi. Seçin **cihazları** > **Azure AD cihazları**.
- **Azure AD tüm cihazlar** Azure portalında Azure Active Directory bölmesinde. Seçin **cihazları** > **tüm cihazlar**.
- **Tüm cihazlar** Azure portalında ıntune bölmesi. Seçin **cihazları** > **tüm cihazlar**.

Autopilot cihazlarınızı kaydettikten sonra cihazın ana bilgisayar adlarını olur. Varsayılan olarak, ana bilgisayar adı ile başlayan. *Masaüstü -*.


## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma ve atama
Autopilot dağıtım profilleri, Autopilot cihazlarını yapılandırmak için kullanılır.

1. İçinde [Intune](https://aka.ms/intuneportal)seçin **cihaz kaydı** > **Windows kayıt** > **dağıtım profilleri**  >  **Profili oluşturma**.
1. Tür a **adı** ve isteğe bağlı olarak bir **açıklama**.
1. İçin **dağıtım modu**seçin **kullanıcı temelli**.
1. İçinde **Azure AD'ye Katıl** kutusunda **hibrit Azure AD'ye katıldı (Önizleme)**.
1. Seçin **ilk çalıştırma deneyimi (OOBE)** gerektiği gibi seçenekleri yapılandırın ve ardından **Kaydet**.
1. Profili oluşturmak için **Oluştur**'u seçin. 
1. Profil bölmesinde seçin **atamaları**.
1. Seçin **grupları seçin**.
1. İçinde **grupları seçin** bölmesinde, cihaz grubunu seçin ve ardından **seçin**.

Değiştirmek bir cihaz profili durumu için yaklaşık 15 dakika sürer *atanmamış* için *atama* ve son olarak, *atanan*.

## <a name="optional-turn-on-the-enrollment-status-page"></a>(İsteğe bağlı) Kayıt durumu sayfasını aç

1. İçinde [Intune](https://aka.ms/intuneportal)seçin **cihaz kaydı** > **Windows kayıt** > **kayıt durumu sayfası (Önizleme)**.
1. İçinde **kayıt durumu sayfası** bölmesinde **varsayılan** > **ayarları**.
1. İçinde **Göster uygulama ve profil yükleme ilerleme durumu** kutusunda **Evet**.
1. Diğer seçenekleri gerektiği şekilde yapılandırın.
1. **Kaydet**’i seçin.

## <a name="create-and-assign-a-domain-join-profile"></a>Etki Alanına Katılım profili oluşturma ve atama

1. İçinde [Intune](https://aka.ms/intuneportal)seçin **cihaz Yapılandırması** > **profilleri** > **profili oluştur**.
1. Aşağıdaki özellikleri girin:
   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin.
   - **Platform**: Seçin **Windows 10 ve üzeri**.
   - **Profil türü**: Seçin **etki alanına (Önizleme)**.
1. Seçin **ayarları**ve ardından bir **bilgisayar adı ön eki**, **etki alanı adı**ve (isteğe bağlı) **kuruluş birimi** içinde[DN biçiminde](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). 
1. Seçin **Tamam** > **oluşturma**.  
    Profil oluşturulur ve listede görüntülenir.
1. Profili atamak için [Cihaz profili atama](device-profile-assign.md#assign-a-device-profile) altındaki adımları izleyin. 

## <a name="next-steps"></a>Sonraki adımlar

Windows Autopilot’ı yapılandırdıktan sonra, bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için [Intune cihaz yönetimi nedir?](device-management.md).
