---
title: Microsoft Intune Windows cihaz kaydı sorunlarını giderme
titleSuffix: Microsoft Intune
description: Intune 'A Windows cihazlarını kaydettiğinizde en yaygın sorunlardan bazılarının sorunlarını gidermeye yönelik öneriler.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d76b9581cac6e9d74e83ce50400e14468a13d3e6
ms.sourcegitcommit: c715c93bb242f4fe44bbdf2fd585909854ed72b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68664180"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Microsoft Intune Windows cihaz kaydı sorunlarını giderme

Bu makale, Intune yöneticilerinin Windows cihazlarını Intune 'A kaydetme sırasında sorunları anlamalarına ve sorunlarını gidermenize yardımcı olur.

## <a name="prerequisites"></a>Önkoşullar
Sorun gidermeye başlamadan önce bazı temel bilgilerin toplanması önemlidir. Bu bilgiler sorunu daha iyi anlamanıza ve çözüm bulma süresini azaltmanıza yardımcı olabilir.

Sorunla ilgili olarak aşağıdaki bilgileri toplayın:
- Kullanıcıya atanan geçerli bir Intune lisansı mı var? Kullanıcıların cihazlarını kaydedebilmesi için gerekli lisansın atanmış olması gerekir.
- Windows cihaza en son güncelleştirme yüklendi mi? Intune 'daki bazı özellikler yalnızca Windows 'un en son sürümüyle çalışır. Windows Update aracılığıyla kullanılabilen bilinen sorunlara yönelik birçok düzeltme vardır. En son güncelleştirmelerin uygulanması, genellikle bir Windows cihaz kayıt sorununu düzeltir. 
- Tam hata iletisi nedir?
- Hata iletisini nerede görüyorsunuz?
- Sorun ne zaman başladı? Kayıt hiç çalıştı mı? 
- Hangi platform (Android, iOS, Windows) soruna sahip?
- Kaç Kullanıcı etkilendi? Tüm kullanıcılar mı etkilendi?
- Kaç cihaz etkilendi? Tüm cihazlar etkileniyor mu ya da yalnızca bir şey var mı?
- MDM yetkilisi nedir? System Center Configuration Manager, Configuration Manager hangi sürümü kullanıyorsunuz?
- Kayıt nasıl gerçekleştirilir? Kayıt profilleriyle "kendi cihazını getir" (BYOD) veya Apple Aygıt Kayıt Programı (DEP) mi?

## <a name="error-messages"></a>Hata iletileri

### <a name="this-user-is-not-authorized-to-enroll"></a>Bu kullanıcının kaydolma yetkisi yok.

Hata 0x801c003: "Bu kullanıcının kaydolma yetkisi yok. Bunu yeniden deneyebilir veya hata kodu (0x801c0003) ile sistem yöneticinize başvurabilirsiniz. "
Hata 80180003: "Bir sorun oluştu. Bu kullanıcının kaydolma yetkisi yok. Bunu yeniden deneyebilir veya 80180003 hata koduyla sistem yöneticinize başvurabilirsiniz. "

**Sağlamak** Aşağıdaki koşullardan herhangi biri: 

- Kullanıcı, Intune 'da izin verilen en fazla cihaz sayısını zaten kaydettiniz.    
- Cihaz, cihaz türü kısıtlamaları tarafından engelleniyor.    
- Bilgisayar Windows 10 Home çalıştırıyorsa. Ancak, Intune 'A kaydolma veya Azure AD 'ye katılma yalnızca Windows 10 Pro ve üzeri sürümlerde desteklenir.

#### <a name="resolution"></a>Çözüm
Bu soruna yönelik birkaç olası çözüm vardır:

##### <a name="remove-devices-that-were-enrolled"></a>Kaydedilen cihazları kaldırma
1. [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) oturum açın.    
2.  **Kullanıcılara** > **tüm kullanıcılar**' a gidin.    
3. Etkilenen Kullanıcı hesabını seçin ve ardından **cihazlar**' a tıklayın.    
4. Kullanılmayan veya istenmeyen cihazları seçin ve ardından **Sil**' e tıklayın. 

##### <a name="increase-thedevice-enrollment-limit"></a>Cihaz kayıt sınırını artırma

> [!NOTE]
> Bu yöntem, yalnızca etkilenen kullanıcıyı değil, tüm kullanıcılar için cihaz kayıt sınırını artırır.

1. [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) oturum açın.
2.  **Cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin ve **cihaz sınırı kısıtlamaları**' nı seçin.    
3. **Cihaz sınırının**değerini artırın. 

##### <a name="checkdevice-type-restrictions"></a>Cihaz türü kısıtlamalarını denetle
1.  [Intune portalında](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) bir genel yönetici hesabıyla oturum açın.
2.  **Cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin ve ardından **cihaz türü kısıtlamaları**' nın altında **varsayılan** kısıtlamayı seçin.    
3.  **Platformlar**' ı seçin ve ardından Windows için **izin ver**  **(MDM)** seçeneğini belirleyin.

    > [!IMPORTANT]
    > Geçerli ayar zaten **izin veriyor**ise, bunu **Engelle**olarak değiştirin, ayarı kaydedin ve sonra yeniden **izin** verecek şekilde değiştirin ve ayarı yeniden kaydedin. Bu, kayıt ayarını sıfırlar.

4. Yaklaşık 15 dakika bekleyin ve ardından etkilenen cihazı yeniden kaydedin.    

##### <a name="upgrade-windows-10-home"></a>Windows 10 Home 'ı yükselt
[Windows 10 Home 'ı Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) veya daha yüksek bir sürüme yükseltin. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Bu kullanıcının kaydetmesine izin verilmiyor.

Hata 0x801c0003: "Bu kullanıcının kaydolmasına izin verilmiyor. Yeniden deneyebilir veya sistem yöneticinize başvurarak 801c0003 hata koduyla iletişim kurun. "

**Sağlamak** **Kullanıcılar cihazları Azure AD ayarına katabilir** , **none**olarak ayarlanır. Bu, yeni kullanıcıların cihazlarını Azure AD 'ye katılmasını önler. Bu nedenle, Intune kaydı başarısız olur.

#### <a name="resolution"></a>Çözüm
1.  [](https://portal.azure.com/)AzurePortal yönetici olarak oturum açın.    
2. **Azure Active Directory**  **** cihazlarcihazayarları ' na gidin.>>     
3.  **Kullanıcıları, cihazları Azure AD 'ye** bir **bütün**olarak birleştirebileceği şekilde ayarlayabilirsiniz.    
4. Cihazı yeniden kaydedin.   

### <a name="the-device-is-already-enrolled"></a>Cihaz zaten kayıtlı.

Hata 8018000a: "Bir sorun oluştu. Cihaz zaten kayıtlı.  Sistem yöneticinize başvurarak 8018000a hata koduyla iletişim sağlayabilirsiniz.

**Sağlamak** Aşağıdaki koşullardan biri doğru:
- Farklı bir Kullanıcı cihazı Intune 'a zaten kaydettiniz veya cihazı Azure AD 'ye katıldı. Durumun bu olup olmadığını anlamak için **Ayarlar** > **hesaplar** > **iş erişimi**' ne gidin. Aşağıdakine benzer bir ileti arayın: "Sistemdeki başka bir kullanıcı zaten bir iş veya okula bağlı. Lütfen bu iş veya okul bağlantısını kaldırın ve yeniden deneyin. "    
- Configuration Manager istemci Aracısı bilgisayara yüklenir.    

#### <a name="resolution"></a>Çözüm

Bu sorunu çözmek için aşağıdaki yöntemlerden birini kullanın:

##### <a name="remove-the-other-work-or-school-account"></a>Diğer iş veya okul hesabını kaldır
1. Windows oturumunu kapatın ve ardından cihazda kayıtlı veya katılmış olan diğer hesabı kullanarak oturum açın.    
2. **Ayarlar** > hesaplariş > **erişimi**' ne gidin, sonra iş veya okul hesabını kaldırın.
3. Windows oturumunu kapatın ve hesabınızı kullanarak oturum açın.    
4. Cihazı Intune 'a kaydedin veya cihazı Azure AD 'ye katın. 

##### <a name="remove-the-configuration-manager-client"></a>Configuration Manager istemcisini kaldır
Configuration Manager istemcisini kaldırın ve ardından cihazı yeniden kaydedin.



### <a name="this-account-is-not-allowed-on-this-phone"></a>Bu telefonda bu hesaba izin verilmiyor.

Hata: "Bu telefonda bu hesapta izin verilmiyor. Verdiğiniz bilgilerin doğru olduğundan emin olun ve sonra yeniden deneyin veya şirketinizde destek isteyin. "

**Sağlamak** Cihazı kaydetmeyi denediğiniz kullanıcının geçerli bir Intune lisansı yok.

#### <a name="resolution"></a>Çözüm
Kullanıcıya geçerli bir Intune lisansı atayın ve ardından cihazı kaydedin.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>MDM kullanım koşulları uç noktası doğru yapılandırılmamış gibi görünüyor.

**Sağlamak** Aşağıdaki koşullardan biri doğru: 
 - Kiracı üzerinde Office 365 ve Intune için hem mobil cihaz yönetimi (MDM) hem de cihazı kaydetmeye çalışan kullanıcının geçerli bir Intune lisansı veya bir Office 365 lisansı yoktur.     
- Azure AD 'deki MDM hüküm ve koşulları boş veya doğru URL 'YI içermiyor.    

#### <a name="resolution"></a>Çözüm

Bu sorunu onarmak için aşağıdaki yöntemlerden birini kullanın: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Kullanıcıya geçerli bir lisans ata
 [Microsoft 365 yönetim merkezine](https://portal.office.com/adminportal/home)gidin ve ardından kullanıcıya bir Intune veya Office 365 lisansı atayın.

##### <a name="correct-themdm-terms-of-use-url"></a>MDM kullanım koşulları URL 'sini düzeltin
  1.  [Azure Portal](https://portal.azure.com/)oturum açın ve **Azure Active Directory**' ı seçin.    
  2.  **Mobility (MDM ve MAM)** öğesini seçin ve ardından **Microsoft Intune**' ye tıklayın.    
  3.  **Varsayılan MDM URL 'Lerini geri yükle**' yi seçin, **MDM kullanım koşulları URL 'sinin** olarak **https://portal.manage.microsoft.com/TermsofUse.aspx** ayarlandığını doğrulayın.    
  4. **Kaydet**’i seçin.    


### <a name="something-went-wrong"></a>Bir sorun oluştu.

Hata 80180026: "Bir sorun oluştu. Doğru oturum açma bilgilerini kullandığınızı ve kuruluşunuzun bu özelliği kullandığını onaylayın. Bunu yeniden deneyebilir veya 80180026 hata koduyla sistem yöneticinize başvurabilirsiniz. "

**Sağlamak** Bu hata, bir Windows 10 bilgisayarını Azure AD 'ye katılmayı denediğinizde ve aşağıdaki koşulların her ikisi de doğru olduğunda oluşabilir: 
- MDM otomatik kaydı, Azure 'da etkindir.    
- Intune bilgisayar istemcisi (Intune bılgısayar Aracısı) veya Configuration Manager istemci Aracısı Windows 10 bilgisayarına yüklendi.

#### <a name="resolution"></a>Çözüm
Bu sorunu gidermek için aşağıdaki yöntemlerden birini kullanın:

##### <a name="disablemdm-automatic-enrollment-in-azure"></a>Azure 'da MDM otomatik kaydını devre dışı bırakın.
1.  [Azure Portal](https://portal.azure.com/)oturum açın.    
2.  > **Azure Active Directory** > **Mobility (MDM ve MAM)**  **Microsoft Intune**gidin.    
3.  **MDM Kullanıcı kapsamını** **none**olarak ayarlayın ve ardından **Kaydet**' e tıklayın.    
     
##### <a name="uninstall"></a>Kaldır
Intune bılgısayar istemcisini veya Configuration Manager istemci aracısını bilgisayardan kaldırın.    

### <a name="the-software-cannot-be-installed"></a>Yazılım yüklenemiyor.

Hata: "Yazılım yüklenemiyor, 0x80cf4017."

**Sağlamak** İstemci yazılımı güncel değil.

#### <a name="resolution"></a>Çözüm
1. Oturum açın [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2.  **Yönetici** > **istemci yazılımı indirmesi**' ne gidin ve ardından **istemci yazılımını indir**' e tıklayın.    
3. Yükleme paketini kaydedin ve ardından istemci yazılımını yükleme. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Hesap sertifikası geçerli değil ve zaman aşımına uğradı.

Hata: "Hesap sertifikası geçerli değil ve zaman aşımına ermeyebilir, 0x80cf4017."

**Sağlamak** İstemci yazılımı güncel değil.

#### <a name="resolution"></a>Çözüm
1. Oturum açın [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2.  **Yönetici** > **istemci yazılımı indirmesi**' ne gidin ve ardından **istemci yazılımını indir**' e tıklayın.    
3. Yükleme paketini kaydedin ve ardından istemci yazılımını yükleme.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Kuruluşunuz bu Windows sürümünü desteklemiyor. 

Hata: "Bir sorun oluştu. Kuruluşunuz bu Windows sürümünü desteklemiyor.  (0x80180014) "

**Sağlamak** Windows MDM kaydı, Intune kiracınızda devre dışı bırakıldı.

#### <a name="resolution"></a>Çözüm
Tek başına bir Intune ortamında bu sorunu onarmak için aşağıdaki adımları izleyin: 
 
1.  [](https://portal.azure.com/)AzurePortal yönetici olarak oturum açın.    
2. Sol tarafta **Intune** ' u seçin ve ardından **cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin.    
3.  **Cihaz türü kısıtlamaları**' nda **platformlar**' a ve ardından Windows için **izin ver** ' i **(MDM)** seçin.    
4. **Kaydet**’e tıklayın.    
 
Bu sorunu Intune ve Configuration Manager ile karma MDM 'de onarmak için aşağıdaki adımları izleyin: 
1. Configuration Manager konsolunu açın.    
2. **Yönetim**' i ve ardından **Cloud Services**' yi seçin.    
3. **Microsoft Intune aboneliği**' ne sağ tıklayın ve ardından **Windows > platformları Yapılandır**' ı seçin.    
4. **Windows kaydını** > Etkinleştir > ' in Tamam '**ı**işaretleyin.  


### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Toplu kayıt sırasında bir kurulum hatası oluştu.

**Sağlamak** İlgili sağlama paketinin hesap paketindeki (Package_GUID) Azure AD Kullanıcı hesaplarının cihazların Azure AD 'ye katılmasına izin verilmez. Bu Azure AD hesapları, Windows yapılandırma Tasarımcısı (WCD) veya okul bilgisayarlarını ayarla uygulaması ile bir sağlama paketi ayarlarken otomatik olarak oluşturulur ve bu hesaplar daha sonra cihazları Azure AD 'ye katmak için kullanılır.

#### <a name="resolution"></a>Çözüm
1.  [](https://portal.azure.com/)AzurePortal yönetici olarak oturum açın.    
2. **Cihaz ayarlarını > Azure Active Directory > cihazlar**' a gidin.    
3.  **Kullanıcıları, cihazları Azure AD** 'ye **Tüm** veya **Seçili**olarak birleştirebileceği şekilde ayarlar.

    **Seçili**' i seçerseniz, **Seçili**' e tıklayın ve ardından, cihazlarını Azure AD 'ye birleştirebilen tüm kullanıcıları eklemek için **üye Ekle** ' ye tıklayın. Sağlama paketi için tüm Azure AD hesaplarının eklendiğinden emin olun.
 
Windows yapılandırma Tasarımcısı için sağlama paketi oluşturma hakkında daha fazla bilgi için bkz. [Windows 10 için sağlama paketi oluşturma](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package).

Okul bilgisayarlarını ayarlama uygulaması hakkında daha fazla bilgi için bkz. [okul bilgisayarlarını ayarlama uygulamasını kullanma](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app).


### <a name="auto-mdm-enroll-failed"></a>Otomatik MDM kaydı: Başarısız 

Grup ilkesi kullanarak bir Windows 10 cihazını otomatik olarak kaydetmeyi denediğinizde aşağıdaki sorunlarla karşılaşırsınız: 
- Görev Zamanlayıcı, **Microsoft** > Windows > **EnterpriseMgmt**altında, **kayıt istemcisi tarafından aad 'den MDM 'yi otomatik olarak kaydetmek için oluşturulan zamanlamanın** son çalıştırma sonucu aşağıdaki gibidir: **Olay 76 otomatik MDM kaydı: Başarısız oldu (bilinmeyen Win32 hata kodu: 0x8018002b)**       
- Olay Görüntüleyicisi, aşağıdaki olay, **uygulamalar ve hizmetler günlükleri/Microsoft/Windows/DeviceManagement-Enterprise-Diagnostics-Provider/admin**altında günlüğe kaydedilir:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Sağlamak** Aşağıdaki koşullardan biri doğru: 
- UPN,. Local ( joe@contoso.localgibi) doğrulanmamış veya yönlendirilemeyen bir etki alanı içerir.    
- **MDM Kullanıcı kapsamı**  **none**olarak ayarlanır. 

#### <a name="resolution"></a>Çözüm
UPN doğrulanmamış veya yönlendirilemeyen bir etki alanı içeriyorsa, şu adımları izleyin: 

1. Active Directory Domain Services (AD DS) üzerinde çalıştığı sunucuda, **Çalıştır** iletişim kutusunda **dsa. msc** yazarak **Active Directory Kullanıcıları ve bilgisayarları** açın ve ardından **Tamam**' a tıklayın.    
2. Etki alanınız altındaki **Kullanıcılar** ' a tıklayın ve ardından aşağıdakileri yapın:  
    - Yalnızca bir etkilenen kullanıcı varsa, kullanıcıya sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Hesap** sekmesinde, **Kullanıcı oturum açma adı**' nın altındaki UPN soneki aşağı açılan listesinde, contoso.com gibi geçerli bir UPN son eki seçin ve ardından **Tamam**' a tıklayın.    
    - Birden çok etkilenen kullanıcı varsa, kullanıcılar ' ı seçin, **eylem** menüsünde **Özellikler**' e tıklayın. **Hesap** sekmesinde, **UPN soneki** onay kutusunu seçin, açılır listeden contoso.com gibi geçerli bir UPN soneki seçin ve ardından **Tamam**' a tıklayın.
3. Yükseltilmiş bir PowerShell isteminde aşağıdaki komutları çalıştırarak bir sonraki eşitlemeyi bekleyin veya eşitleme sunucusundan bir Delta eşitlemesi zorlayın:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

 **MDM Kullanıcı kapsamı**  **none**olarak ayarlandıysa, şu adımları izleyin: 
 
1. [Azure Portal](https://portal.azure.com/)oturum açın ve **Azure Active Directory**' ı seçin.
2. **Mobility (MDM ve MAM)** seçeneğini belirleyip **Microsoft Intune**seçin.    
3. **MDM Kullanıcı kapsamını** **Tümü**olarak ayarlayın. Ya da, **MDM Kullanıcı kapsamını** **bazılarına**ayarlayın ve Windows 10 cihazlarını otomatik olarak kaydedebilen grupları seçin.    
4. **Mam Kullanıcı kapsamını** **none**olarak ayarlayın.


## <a name="next-steps"></a>Sonraki adımlar

- [Intune’da cihaz kaydı sorunlarını giderme](troubleshoot-device-enrollment-in-intune.md)
- [Intune forumundan soru sorun](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Microsoft Intune destek ekibi blogunu denetleyin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Microsoft Enterprise Mobility ve Security blogunu denetleyin](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Microsoft Intune için destek alın](https://docs.microsoft.com/intune/get-support) 