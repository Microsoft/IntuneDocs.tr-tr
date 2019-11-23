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
ms.openlocfilehash: 5066afdaf303a1cef20f80d3134f2382f718d86b
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390744"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Enroll Windows devices in Intune by using the Windows Autopilot  
The Windows Autopilot simplifies enrolling devices in Intune. Özelleştirilmiş işletim sistemi görüntülerinin derlenmesi ve bakımı çok zaman alan bir işlemdir. Ayrıca bu özel işletim sistemi görüntülerini, yeni cihazları son kullanıcılarınıza vermeden önce kullanıma hazırlamak amacıyla cihazlara uygulamak için de zaman harcayabilirsiniz. Microsoft Intune ve Autopilot ile cihazlarda özel işletim sistemi görüntüleri oluşturmanıza, bu görüntüleri cihazlara uygulamanıza ve bunların bakımını yapmanıza gerek kalmadan son kullanıcılarınıza yeni cihazlar verebilirsiniz. Autopilot cihazlarını yönetmek için Intune kullandığınızda, kaydolduktan sonra ilkeleri, profilleri, uygulamaları ve diğer nesneleri yönetebilirsiniz. Faydalara, senaryolara ve önkoşullara genel bir bakış için bkz. [Windows Autopilot’a genel bakış](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

There are four types of Autopilot deployment:
- [Self Deploying Mode](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) for kiosks, digital signage, or a shared device
- [White Glove](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) enables partners or IT staff to pre-provision a Windows 10 PC so that it's fully configured and business-ready -[Autopilot for existing devices](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) enables you to easily deploy the latest version of Windows 10 to your existing devices
- [User Driven Mode](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) for traditional users. 


## <a name="prerequisites"></a>Önkoşullar
- [Intune subscription](../fundamentals/licenses.md)
- [Windows otomatik kayıt etkin olmalıdır](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium subscription](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>How to get the CSV for Import in Intune

For more information, see the understanding powershell cmdlet.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Cihazları ekleme

Bilgilerini içeren CSV dosyasını içeri aktararak Windows Autopilot cihazlarını ekleyebilirsiniz.

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment** > **Windows enrollment** > **Devices** > **Import**.

    ![Windows Autopilot cihazlarının ekran görüntüsü](./media/enrollment-autopilot/autopilot-import-device.png)

2. **Windows Autopilot cihazları ekle** altında, eklemek istediğiniz cihazları listeleyen bir CSV dosyasına gözatın. The CSV file should list the serial numbers, Windows product IDs, hardware hashes, optional group tags, and optional assigned user. You can have up to 500 rows in the list. Use the header and line format shown below:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Windows Autopilot cihazları ekleme ekran görüntüsü](./media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > When you use CSV upload to assign a user, make sure that you assign valid UPNs. If you assign an invalid UPN (incorrect username), your device may be inaccessible until you remove the invalid assignment. During CSV upload the only validation we perform on the **Assigned User** column is to check that the domain name is valid. We're unable to perform individual UPN validation to ensure that you're assigning an existing or correct user.

3. Cihaz bilgilerini içeri aktarmayı başlatmak için **İçeri Aktar**'ı seçin. İçeri aktarma birkaç dakika sürebilir.

4. After import is complete, choose **Device enrollment** > **Windows enrollment** > **Windows Autopilot** > **Devices** > **Sync**. A message displays that the synchronization is in progress. Kaç tane cihazın eşitlendiğine bağlı olarak işlemin tamamlanması birkaç dakikayı bulabilir.

5. Yeni cihazları görmek için görüntüyü yenileyin.

## <a name="create-an-autopilot-device-group"></a>Bir Autopilot cihaz grubu oluşturma

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Groups** > **New group**.
2. **Gruplar** dikey penceresinde:
    1. **Grup türü** olarak **Güvenlik**’i seçin.
    2. Bir **Grup adı** ve **Grup açıklaması** girin.
    3. **Üyelik türü** olarak **Atanan** veya **Dinamik Cihaz**’ı seçin.
3. Önceki adımda **Üyelik türü** olarak **Atanan**'ı seçtiyseniz, **Gruplar** dikey penceresinde **Üyeler**'i seçin ve gruba Autopilot cihazları ekleyin.
    Henüz kaydedilmemiş Autopilot cihazları, adın cihaz seri numarası olduğu cihazlardır.
4. Yukarıda **Üyelik türü** olarak **Dinamik Cihazlar**’ı seçtiyseniz **Gruplar** dikey penceresinde **Dinamik cihaz üyeleri**’ni seçin ve **Gelişmiş kural** kutusuna aşağıdaki kodlardan birini yazın. Only Autopilot devices are gathered by these rules, because they target attributes that are only possessed by Autopilot devices. Creating a group based off non-autopilot attributes won't guarantee that devices included in the group are actually registered to Autopilot.
    - If you want to create a group that includes all of your Autopilot devices, type: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Intune's group tag field maps to the OrderID attribute on Azure AD devices. If you want to create a group that includes all of your Autopilot devices with a specific group tag (the Azure AD device OrderID), you must type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Belirli bir Satın Alma Sipariş Kimliğine sahip tüm Autopilot cihazlarınızı içeren bir grup oluşturmak istiyorsanız `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` yazın
    
    **Gelişmiş kural** kodunu ekledikten sonra **Kaydet**’i seçin.
5. **Oluştur**’u seçin.  

## <a name="create-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profili oluşturma
Autopilot dağıtım profilleri, Autopilot cihazlarını yapılandırmak için kullanılır. You can create up to 350 profiles per tenant.
1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > **Create Profile**.
2. On the **Basics** page, type a **Name** and optional **Description**.

    ![Screenshot of Basics page](./media/enrollment-autopilot/create-profile-basics.png)

3. Atanan gruplardaki tüm cihazların otomatik olarak Autopilot'a dönüştürülmesini istiyorsanız **Hedeflenen tüm cihazları Autopilot'a dönüştür** seçeneğini **Evet** olarak ayarlayın. All corporate owned, non-Autopilot devices in assigned groups will register with the Autopilot deployment service. Personally owned devices will not be converted to Autopilot. Kaydın işlenmesi için 48 saat kadar bekleyin. Kaydı kaldırılıp sıfırlandığında Autopilot cihazı kaydeder. Bir cihaz bu şekilde kaydedildikten sonra bu seçeneğin devre dışı bırakılması veya profil atamasının kaldırılması cihazı Autopilot dağıtım hizmetinden kaldırmaz. Bunun yerine [cihazı doğrudan kaldırmanız](enrollment-autopilot.md#delete-autopilot-devices) gerekir.
4. **İleri**'yi seçin.
5. On the **Out-of-box experience (OOBE)** page, for **Deployment mode**, choose one of these two options:
    - **Kullanıcı temelli**: Bu profile sahip cihazlar, cihazı kaydeden kullanıcı ile ilişkilidir. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekir.
    - **Self-deploying (preview)** : (requires Windows 10, version 1809 or later) Devices with this profile aren't associated with the user enrolling the device. Cihazı kaydetmek için kullanıcı kimlik bilgileri gerekmez. When a device has no user associated with it, user-based compliance policies don't apply to it. When using self-deploying mode, only compliance policies targeting the device will be applied.

    ![Screenshot of OOBE page](./media/enrollment-autopilot/create-profile-outofbox.png)

6. **Azure AD’ye farklı katıl** kutusunda **Azure AD katılımlı**’yı seçin.
7. Configure the following options:
    - **Son kullanıcı lisans sözleşmesi (EULA)** : (Windows 10, sürüm 1709 veya sonrası) EULA'yı kullanıcılara göstermek istiyorsanız seçin.
    - **Gizlilik ayarları**: Gizlilik ayarlarını kullanıcılara göstermek istiyorsanız seçin.
    >[!IMPORTANT]
    >The default value for the Diagnostic Data setting varies between Windows versions. For devices running Windows 10, version 1903, the default value is set to Full during the out-of-box experience. For more information, see [Windows Diagnostics Data](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) <br>
    
    - **Hide change account options (requires Windows 10, version 1809 or later)** : Choose **Hide** to prevent change account options from displaying on the company sign-in and domain error pages. Bu seçenek, [Azure Active Directory’de şirket markasının yapılandırılmasını](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) gerektirir.
    - **Kullanıcı hesap türü**: Kullanıcı hesap türü **Yönetici** ya da **Standart** olarak seçin. We allow the user joining the device to be a local Administrator by adding them to the local Admin group. We don't enable the user as the default administrator on the device.
    - **Allow White Glove OOBE** (requires Windows 10, version 1903 or later; [additional physical requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): Choose **Yes** to allow white glove support.
    - **Apply device name template** (requires Windows 10, version 1809 or later, and Azure AD join type): Choose **Yes** to create a template to use when naming a device during enrollment. Adlar en çok 15 karakter olmalıdır; harf, rakam ve tire içerebilir. Ancak tamamen sayıdan oluşamaz. Donanıma özgü seri numarası eklemek için [%SERIAL% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanın. Veya x değerinin eklenecek basamak sayısına karşılık geldiği [%RAND:x% makrosunu](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) kullanarak rastgele bir sayı dizesi ekleyin. You can only provide a pre-fix for hybrid devices in a [domain join profile](windows-autopilot-hybrid.md#create-and-assign-a-domain-join-profile). 
    - **Dil (Bölge)** \*: Cihazda kullanılacak dili seçin. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
    - **Automatically configure keyboard**\*: If a **Language (Region)** is selected, choose **Yes** to skip the keyboard selection page. Bu seçenek, yalnızca **Dağıtım modu** olarak **Kendi kendine dağıtım** seçtiyseniz kullanılabilir.
8. **İleri**'yi seçin.
9. On the **Scope tags** page, optionally add the scope tags you want to apply to this profile. For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md).
10. **İleri**'yi seçin.
11. On the **Assignments** page, choose **Selected groups** for **Assign to**.

    ![Screenshot of Assignments page](./media/enrollment-autopilot/create-profile-assignments.png)

12. Choose **Select groups to include**, and choose the groups you want to include in this profile.
13. If you want to exclude any groups, choose **Select groups to exclude**, and choose the groups you want to exclude.
14. **İleri**'yi seçin.
15. On the **Review + Create** page, choose **Create** to create the profile.

    ![Screenshot of Review page](./media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Intune will periodically check for new devices in the assigned groups, and then begin the process of assigning profiles to those devices. This process can take several minutes to complete. Before deploying a device, ensure that this process has completed.  You can check under **Device enrollment** > **Windows enrollment** > **Devices** where you should see the profile status change from "Unassigned" to "Assigning" and finally to "Assigned."

## <a name="edit-an-autopilot-deployment-profile"></a>Bir Autopilot dağıtım profilini düzenleme
Bir Autopilot dağıtım profili oluşturduktan sonra bu profilin bazı kısımlarını düzenleyebilirsiniz.   

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment**.
2. **Windows kaydı** altındaki **Windows Autopilot** bölümünde **Dağıtım Profilleri**’ni seçin.
3. Düzenlemek istediğiniz profili seçin.
4. Solda bulunan **Özellikler**’e tıklayarak dağıtım profilinin adını veya açıklamasını değiştirin. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.
5. OOBE ayarlarında değişiklik yapmak için **Ayarlar**’a tıklayın. Değişiklikleri tamamladıktan sonra **Kaydet**’e tıklayın.

> [!NOTE]
> Profilde yapılan değişiklikler, bu profile atanmış cihazlara uygulanır. Ancak güncelleştirilmiş profil, Intune’a önceden kaydedilmiş cihazlarda cihaz sıfırlanıp yeniden kaydedilene kadar uygulanmaz.

## <a name="edit-autopilot-device-attributes"></a>Edit Autopilot device attributes
After you've uploaded an Autopilot device, you can edit certain attributes of the device.

1. In Intune in the Azure portal, choose **Device enrollment**.
2. Under **Windows enrollment**, in the **Windows Autopilot** section, choose **Devices**.
3. Select the device you want to edit.
4. In the pane on the right of the screen, you can edit the device name, group tag, or User Friendly Name (if you've assigned a user).
5. **Kaydet**’i seçin.

> [!NOTE]
> Device names can be configured for all devices, but are ignored in Hybrid Azure AD joined deployments. Device name still comes from the domain join profile for Hybrid Azure AD devices.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alerts for Windows Autopilot unassigned devices  <!-- 163236 -->  

Uyarılar kaç Autopilot programı cihazının Autopilot dağıtım profili olmadığını gösterir. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows Autopilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz.

Atanmamış cihazlar için uyarı görmek istiyorsanız [Azure portalında Intune’da](https://aka.ms/intuneportal) **Cihaz kaydı** > **Genel bakış** > **Atanmamış cihazlar**’ı seçin.  

## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Belirli bir Autopilot cihazına kullanıcı atama

Belirli bir Autopilot cihazına kullanıcı atayabilirsiniz. Bu atama, Windows kurulumu sırasında [şirket markalı](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) oturum açma sayfasında Azure Active Directory’den bir kullanıcıyı önceden doldurur. Ayrıca özel bir karşılama adı ayarlamanıza imkan verir. Windows oturum açmayı önceden doldurmaz ve değiştirmez. Yalnızca lisanslı Intune kullanıcıları bu yolla atanabilir.

Prerequisites: Azure Active Directory Company Portal has been configured and Windows 10, version 1809 or later.

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment** > **Windows enrollment** > **Devices** > choose the device > **Assign user**.

    ![Kullanıcı ata ekran görüntüsü](./media/enrollment-autopilot/assign-user.png)

2. Intune’u kullanmak için Azure lisanslı bir kullanıcıyı seçin ve **Seç**’e tıklayın.

    ![Kullanıcı seç ekran görüntüsü](./media/enrollment-autopilot/select-user.png)

3. **Kolay Ad** kutusuna kolay bir ad girin veya varsayılanı kabul edin. Bu dize, kullanıcı Windows kurulumu sırasında oturum açtığında görüntülenen kolay addır.

    ![Kolay ad ekran görüntüsü](./media/enrollment-autopilot/friendly-name.png)

4. **Tamam**’ı seçin.

## <a name="autopilot-deployments-report"></a>Autopilot deployments report
You can see details on each device deployed through Windows Autopilot.
To see the report, go to **Intune** and, under **Monitor**, choose **Autopilot deployments**.
The data is available for 30 days after deployment.


## <a name="delete-autopilot-devices"></a>Autopilot cihazlarını silme

You can delete Windows Autopilot devices that aren't enrolled into Intune:

- Delete the devices from Windows Autopilot at **Device enrollment** > **Windows enrollment** > **Devices**. Choose the devices you want to delete, then choose **Delete**. Windows Autopilot device deletion can take a few minutes to complete.

Completely removing a device from your tenant requires you to delete the Intune device, the Azure Active Directory device, and the Windows Autopilot device records. This can all be done from Intune:

1. If the devices are enrolled in Intune, you must first [delete them from the Intune All devices blade](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Delete the devices in Azure Active Directory devices at **Devices** > **Azure AD devices**.

3. Delete the devices from Windows Autopilot at **Device enrollment** > **Windows enrollment** > **Devices**. Choose the devices you want to delete, then choose **Delete**. Windows Autopilot device deletion can take a few minutes to complete.

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
