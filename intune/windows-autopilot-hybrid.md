---
title: Karma Active Directory’ye katılmış olan cihazların Intune kaydını Windows Autopilot kullanarak ayarlama
titleSuffix: Microsoft Intune
description: Karma Active Directory’ye katılmış olan cihazları Intune’a kaydetmek için Windows Autopilot’ı kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1a10d434fbdb5d827c7ecb89d1ae2f7e43c0f951
ms.sourcegitcommit: 1e6fee4032c50ab41a5166db39fbea80a731c541
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/14/2018
ms.locfileid: "51654917"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-using-intune-and-windows-autopilot-preview"></a>Karma Azure Active Directory’ye olan katılmış cihazları Intune ve Windows Autopilot kullanarak dağıtma (Önizleme)
Karma Azure Active Directory alanına katılmış olan cihazları ayarlamak için Intune ve Windows Autopilot kullanabilirsiniz. Bunu yapmak için aşağıdaki adımları izleyin.

> [!NOTE]
> Bu özellik, gelecek birkaç gün içinde kullanıcı tabanının kullanımına sunulacaktır. Bu nedenle, bu özellik hesabınız için kullanılabilir olana kadar bu adımları uygulayamayabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- [Karma Azure Active Directory’ye katılmış olan cihazları](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) başarıyla yapılandırın.
    - [Get-MsolDevice cmdlet’ini kullanarak kaydı doğruladığınızdan]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) emin olun.

Kaydedilecek cihazlar ayrıca:
- [Ekim 2018 güncelleştirmesiyle](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/) Windows 10 çalıştırmalıdır.
- İnternet erişimine sahip olmalıdır.
- Active Directory’nize erişime sahip olmalıdır (VPN bağlantısı desteklenmez).
- İlk Kez Çalıştırma Deneyiminden (OOBE) geçmelidir.

## <a name="set-up-windows-10-automatic-enrollment"></a>Windows 10 otomatik kaydını ayarlama

1. [Azure portalında](https://portal.azure.com) oturum açın ve **Azure Active Directory**’yi seçin.

   ![Azure portalının ekran görüntüsü](./media/auto-enroll-azure-main.png)

2. **Mobility (MDM ve MAM)** seçeneğini belirleyin.

   ![Azure portalının ekran görüntüsü](./media/auto-enroll-mdm.png)

3. **Microsoft Intune**'u seçin.

   ![Azure portalının ekran görüntüsü](./media/auto-enroll-intune.png)

4. Intune ve Windows kullanarak Azure Active Directory’ye katılmış olan cihazları dağıtan kullanıcıların **MDM Kullanıcı kapsamınıza** dahil bir grubun üyeleri olduğundan emin olun.

   ![Azure portalının ekran görüntüsü](./media/auto-enroll-scope.png)

5. Aşağıdaki URL'ler için varsayılan değerleri kullanın:
    - **MDM Kullanım Koşulları URL’si**
    - **MDM Bulma URL’si**
    - **MDM Uyumluluğu URL’si**
6. **Kaydet**’i seçin.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Kuruluş Birimi’nde bilgisayar hesabı sınırını artırma

Active Directory için Intune Bağlayıcısı, Şirket İçi Active Directory etki alanında Autopilot ile kaydedilen bilgisayarlar oluşturur. Intune bağlayıcısını barındıran bilgisayar, etki alanı içinde bilgisayar nesneleri oluşturma haklarına sahip olmalıdır. 

Bazı etki alanlarında bilgisayarlara bilgisayar oluşturma hakkı verilmez. Ya da Yöneticiler etki alanı genelinde bilgisayar hesabı sınırını artırmak istemiyor olabilir. Bu gibi durumlarda haklar, Karma Azure Active Directory’ye katılmış olan cihazların oluşturulduğu kuruluş birimine devredilebilir.

Bilgisayar oluşturma hakkı verilen kuruluş birimi şunlarla eşleşmelidir:
- Etki Alanına Katılım profilinde girilen kuruluş birimi
- Hiç profil seçilmemişse etki alanınız için bilgisayarın etki alanı adı.

1. **Active Directory Kullanıcıları ve Bilgisayarları**’nı açın (DSA.msc).

2. Karma Azure AD’ye katılmış olan bilgisayarları oluşturmak için kullanacağınız kuruluş birimi > **Denetim Temsilcisi Seç**’e sağ tıklayın.

    ![Denetim temsilcisi seç ekran görüntüsü](media/windows-autopilot-hybrid/delegate-control.png)

3. **Denetim Devretme** sihirbazında **Sonraki** > **Ekle...** > **Nesne Türleri**’ni seçin.

4. **Nesne Türleri** iletişim kutusunda **Bilgisayarlar**’ı işaretleyin ve ardından **Tamam**’a tıklayın.

    ![Denetim temsilcisi seç ekran görüntüsü](media/windows-autopilot-hybrid/object-types-computers.png)

5. **Kullanıcı, Bilgisayar veya Grup Seç** iletişim kutusundaki **Seçilecek nesne adlarını girin** kutusuna Bağlayıcının yüklü olduğu bilgisayarın adını girin.

    ![Denetim temsilcisi seç ekran görüntüsü](media/windows-autopilot-hybrid/enter-object-names.png)

6. **Adları Denetle**’yi seçerek girişinizi doğrulayın ve daha sonra **Tamam** > **Sonraki** seçeneğini belirleyin.

7. **Temsilci seçmek için özel bir görev oluşturun** > **Sonraki** seçeneğini belirleyin.

8. **Yalnızca klasörün içinde bulunan aşağıdaki nesneler** seçeneğini belirleyin ve şu seçenekleri işaretleyin:
    - **Bilgisayar nesneleri**
    - **Seçili nesneleri bu klasörde oluştur**
    - **Seçili nesneleri bu klasörden sil**

    ![Denetim temsilcisi seç ekran görüntüsü](media/windows-autopilot-hybrid/only-following-objects.png)
    
9. **İleri**’yi seçin.

10. **İzinler** altında **Tam Denetim**’i işaretleyin (böylece tüm diğer seçenekler işaretlenir) > **Sonraki** > **Son**’u seçin.

    ![Denetim temsilcisi seç ekran görüntüsü](media/windows-autopilot-hybrid/full-control.png)

## <a name="install-the-intune-connector"></a>Intune Bağlayıcısını yükleme

Active Directory için Intune Bağlayıcısı, Windows Server 2016 çalıştıran ve hem Internet’e hem de Active Directory hizmetinize bağlı olan bir bilgisayara yüklenmelidir. Birden fazla Active Directory etki alanını desteklemek üzere ölçek ve kullanılabilirliği artırmak için ortamınıza birden fazla bağlayıcı yükleyebilirsiniz. Bağlayıcıyı, herhangi bir başka Intune bağlayıcısı çalıştırmayan bir sunucuya yüklemenizi öneririz.

1. Bir dil paketi yüklü ve açıklandığı gibi yapılandırılmış olduğundan emin olun [Intune Bağlayıcısı (Önizleme) dil gereksinimleri](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. [Intune](https://aka.ms/intuneportal)’da **Cihaz kaydı** > **Windows kaydı** > **Active Directory için Intune Bağlayıcısı (Önizleme)** > **Bağlayıcı ekle**’yi seçin. 
3. Bağlayıcıyı indirmek için yönergeleri izleyin.
4. Bağlayıcıyı indirmek için indirilen bağlayıcı kurulum dosyasını açın (ODJConnectorBootstrapper.exe).
5. Kurulumun sonunda **Yapılandır**’ı seçin.
6. **Oturum Aç**’ı seçin.
7. Genel Yönetici veya Intune Yöneticisi rolüne ait kimlik bilgilerini girin.
8. **Cihaz kaydı** > **Windows kaydı** > **Active Directory için Intune Bağlayıcısı (Önizleme)** seçeneğine giderek bağlantı durumunun **Etkin** olduğunu onaylayın.

### <a name="configure-web-proxy-settings"></a>Web proxy ayarlarını yapılandırma

Ağ ortamınızda bir Web proxy varsa şuradaki yönergeleri izleyerek Active Directory için Intune Bağlayıcısı’nın düzgün şekilde çalışmasını sağlayın: [Mevcut şirket içi proxy sunucularıyla çalışma](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Bir cihaz grubu oluşturma
1. [Intune](https://aka.ms/intuneportal)’da **Gruplar** > **Yeni grup**’u seçin.
2. **Gruplar** dikey penceresinde:
    1. **Grup türü** olarak **Güvenlik**’i seçin.
    2. Bir **Grup adı** ve **Grup açıklaması** girin.
    3. **Üyelik türü** seçin.
3. Yukarıda **Üyelik türü** olarak **Dinamik Cihazlar**’ı seçtiyseniz **Gruplar** dikey penceresinde **Dinamik cihaz üyeleri**’ni seçin ve **Gelişmiş kural** kutusuna aşağıdaki kodlardan birini yazın.
    - Tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")` yazın
    - Belirli bir sipariş kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") ` yazın
    - Belirli bir Satın Alma Sipariş Kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` yazın
    
    **Gelişmiş kural** kodunu ekledikten sonra **Kaydet**’i seçin.
5. **Oluştur**’u seçin.  

## <a name="register-your-autopilot-devices"></a>Autopilot cihazlarınızı kaydetme

Autopilot cihazlarınızı kaydetmek için aşağıdaki yollardan birini seçin:

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Daha önceden kaydedilmiş Autopilot cihazları kaydetme

1. **Hedeflenen cihazların tümünü Autopilot’a dönüştür** ayarı **Evet** olarak belirlenmiş bir Autopilot dağıtım profili oluşturun. 
2. Profili, Autopilot’a otomatik olarak kaydolmasını istediğiniz üyeleri barındıran gruba atayın.

Daha fazla bilgi için bkz. [Bir Autopilot dağıtım profili oluşturma](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Daha önceden kaydedilmemiş Autopilot cihazları kaydetme

Henüz kaydedilmemiş cihazlarınız varsa, bunları kendiniz kaydedebilirsiniz. Daha fazla bilgi için bkz. [Cihaz ekleme](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>OEM cihazlarını kaydetme

Yeni cihaz satın alırken bazı OEM’ler cihazları sizin için kaydedebilir. Daha fazla bilgi için bkz. [Windows Autopilot sayfası](http://aka.ms/WindowsAutopilot).

Autopilot cihazları kaydedildiğinde (ve Intune’a kaydolmadan önce), bunları üç yerde göreceksiniz (cihazların adı, seri numaraları olarak ayarlıdır):
- Azure portalında Intune’daki Autopilot Cihazlar dikey penceresi (**Cihaz kaydı** > **Windows kaydı** > **Cihazlar**).
- Azure portalında Intune’daki Azure Active Directory cihazlar dikey penceresi (**Cihazlar** > **Azure Active Directory Cihazları**).
- Azure portalında Azure Active Directory’deki AAD Tüm Cihazlar dikey penceresi (**Cihazlar** > **Tüm Cihazlar**).

Autopilot cihazları Intune’a kaydedildikten sonra bunları dört yerde görürsünüz:
- Azure portalında Intune’daki Autopilot Cihazlar dikey penceresi (**Cihaz kaydı** > **Windows kaydı** > **Cihazlar**).
- Azure portalında Intune’daki Azure Active Directory cihazlar dikey penceresi (**Cihazlar** > **Azure Active Directory Cihazları**).
- Azure portalında Azure Active Directory’deki AAD Tüm Cihazlar dikey penceresi (**Cihazlar** > **Tüm Cihazlar**).
- Azure portalında Intune’daki Tüm Cihazlar dikey penceresi (**Cihazlar** > **Tüm Cihazlar**).

AutoPilot cihazları kaydedildikten sonra cihaz adları, cihazın ana bilgisayar adı olarak değişir. Bu ad varsayılan olarak “DESKTOP-” ile başlar.




## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma ve atama
Autopilot dağıtım profilleri, Autopilot cihazlarını yapılandırmak için kullanılır.

1. [Intune’da](https://aka.ms/intuneportal) **Cihaz kaydı** > **Windows kaydı** > **Dağıtım Profilleri** > **Profil Oluştur**’u seçin.
2. Bir **Ad** ve isteğe bağlı olarak bir **Açıklama** girin.
3. **Dağıtım modu** olarak **Kullanıcı temelli**’yi seçin.
4. **Azure AD'ye katılma türü:** kutusunda **Karma Azure AD’ye katılmış (Önizleme)** seçeneğini belirleyin.
5. **İlk kez çalıştırma deneyimi (OOBE)** öğesini seçin, gereken seçenekleri yapılandırın ve **Kaydet**’e tıklayın.
6. Profili oluşturmak için **Oluştur**’a tıklayın. 
7. Profile dikey penceresinde **Atamalar**’ı seçin.
8. **Grup seç**’i seçin > **Grup seç** dikey penceresinde cihaz grubunu seçin ve **Seç**’e tıklayın.

**Atanmadı** olan cihaz profil durumunun **Atanıyor** ve son olarak **Atandı** şeklinde değişmesi yaklaşık 15 dakika sürer.

## <a name="turn-on-the-enrollment-status-page-optional"></a>Kayıt durumu sayfasını açma (isteğe bağlı)

1. [Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Windows kaydı** > **Kayıt Durumu Sayfası (Önizleme)**’yi seçin.
2. **Kayıt Durumu Sayfası** dikey penceresinde, **Varsayılan** > **Ayarlar**’ı seçin.
3. **Uygulama ve profil yükleme ilerleyişini göster** için **Evet**’i seçin.
4. Diğer seçenekleri gerektiği şekilde yapılandırın.
5. **Kaydet**’i seçin.

## <a name="create-and-assign-a-domain-join-profile"></a>Etki Alanına Katılım profili oluşturma ve atama

1. [Intune](https://aka.ms/intuneportal)’da **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’u seçin.
2. Aşağıdaki özellikleri girin:
   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin.
   - **Platform**: **Windows 10 ve üzeri** seçeneğini belirleyin.
   - **Profil türü**: **Etki Alanına Katılım (Önizleme)** seçeneğini belirleyin.
3. **Ayarlar**’ı seçin ve **Bilgisayar adı ön eki**, **Etki alanı adı** ve **Kuruluş birimi** (isteğe bağlı) öğelerini sağlayın. 
4. **Tamam** > **Oluştur**'u seçin. Profil oluşturulur ve listede görüntülenir.
5. Profili atamak için [Cihaz profili atama](device-profile-assign.md#assign-a-device-profile) altındaki adımları izleyin. 

## <a name="next-steps"></a>Sonraki adımlar

Windows Autopilot’ı yapılandırdıktan sonra, bu cihazları nasıl yöneteceğinizi öğrenin. Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir?](device-management.md)
