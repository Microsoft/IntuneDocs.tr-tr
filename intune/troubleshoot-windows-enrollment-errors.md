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
ms.openlocfilehash: 0f78f069f46ce036752fde80519abc03dc7c424c
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167781"
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
2. **Kullanıcılara** > **tüm kullanıcılar**' a gidin.    
3. Etkilenen Kullanıcı hesabını seçin ve ardından **cihazlar**' a tıklayın.    
4. Kullanılmayan veya istenmeyen cihazları seçin ve ardından **Sil**' e tıklayın. 

##### <a name="increase-the-device-enrollment-limit"></a>Cihaz kayıt sınırını artırma

> [!NOTE]
> Bu yöntem, yalnızca etkilenen kullanıcıyı değil, tüm kullanıcılar için cihaz kayıt sınırını artırır.

1. [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) oturum açın.
2. **Cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin ve **cihaz sınırı kısıtlamaları**' nı seçin.    
3. **Cihaz sınırının**değerini artırın. 

##### <a name="check-device-type-restrictions"></a>Cihaz türü kısıtlamalarını denetle
1. [Intune portalında](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) bir genel yönetici hesabıyla oturum açın.
2. **Cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin ve ardından **cihaz türü kısıtlamaları**' nın altında **varsayılan** kısıtlamayı seçin.    
3. **Platformlar**' ı seçin ve ardından Windows Için **ızın ver** **(MDM)** seçeneğini belirleyin.

    > [!IMPORTANT]
    > Geçerli ayar zaten **Izin veriyor**ise, bunu **Engelle**olarak değiştirin, ayarı kaydedin ve sonra yeniden **izin** verecek şekilde değiştirin ve ayarı yeniden kaydedin. Bu, kayıt ayarını sıfırlar.

4. Yaklaşık 15 dakika bekleyin ve ardından etkilenen cihazı yeniden kaydedin.    

##### <a name="upgrade-windows-10-home"></a>Windows 10 Home 'ı yükselt
[Windows 10 Home 'ı Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) veya daha yüksek bir sürüme yükseltin. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Bu kullanıcının kaydetmesine izin verilmiyor.

Hata 0x801c0003: "Bu kullanıcının kaydolmasına izin verilmiyor. Yeniden deneyebilir veya sistem yöneticinize başvurarak 801c0003 hata koduyla iletişim kurun. "

**Sağlamak** **Kullanıcılar cihazları Azure AD ayarına katabilir** , **none**olarak ayarlanır. Bu, yeni kullanıcıların cihazlarını Azure AD 'ye katılmasını önler. Bu nedenle, Intune kaydı başarısız olur.

#### <a name="resolution"></a>Çözüm
1. [Azure Portal](https://portal.azure.com/) yönetici olarak oturum açın.    
2. **Azure Active Directory** > cihazlarcihaz > **ayarları**' na gidin.    
3. **Kullanıcıları, cihazları Azure AD 'ye** bir **bütün**olarak birleştirebileceği şekilde ayarlayabilirsiniz.    
4. Cihazı yeniden kaydedin.   

### <a name="the-device-is-already-enrolled"></a>Cihaz zaten kayıtlı.

Hata 8018000a: "Bir sorun oluştu. Cihaz zaten kayıtlı.  Sistem yöneticinize başvurarak 8018000a hata koduyla iletişim sağlayabilirsiniz.

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

##### <a name="correct-the-mdm-terms-of-use-url"></a>MDM kullanım koşulları URL 'sini düzeltin
  1. [Azure Portal](https://portal.azure.com/)oturum açın ve **Azure Active Directory**' ı seçin.    
  2. **Mobility (MDM ve MAM)** öğesini seçin ve ardından **Microsoft Intune**' ye tıklayın.    
  3. **Varsayılan MDM URL 'Lerini geri yükle**' yi seçin, **MDM kullanım koşulları URL 'sinin** olarak **https://portal.manage.microsoft.com/TermsofUse.aspx** ayarlandığını doğrulayın.    
  4. **Kaydet**’i seçin.    


### <a name="something-went-wrong"></a>Bir sorun oluştu.

Hata 80180026: "Bir sorun oluştu. Doğru oturum açma bilgilerini kullandığınızı ve kuruluşunuzun bu özelliği kullandığını onaylayın. Bunu yeniden deneyebilir veya 80180026 hata koduyla sistem yöneticinize başvurabilirsiniz. "

**Sağlamak** Bu hata, bir Windows 10 bilgisayarını Azure AD 'ye katılmayı denediğinizde ve aşağıdaki koşulların her ikisi de doğru olduğunda oluşabilir: 
- MDM otomatik kaydı, Azure 'da etkindir.    
- Intune bilgisayar istemcisi (Intune bılgısayar Aracısı) veya Configuration Manager istemci Aracısı Windows 10 bilgisayarına yüklendi.

#### <a name="resolution"></a>Çözüm
Bu sorunu gidermek için aşağıdaki yöntemlerden birini kullanın:

##### <a name="disable-mdm-automatic-enrollment-in-azure"></a>Azure 'da MDM otomatik kaydını devre dışı bırakın.
1. [Azure Portal](https://portal.azure.com/) oturum açın.    
2.  >  **Azure Active Directory** > **Mobility (MDM ve MAM)** **Microsoft Intune**gidin.    
3. **MDM Kullanıcı kapsamını** **none**olarak ayarlayın ve ardından **Kaydet**' e tıklayın.    
     
##### <a name="uninstall"></a>Kaldır
Intune bılgısayar istemcisini veya Configuration Manager istemci aracısını bilgisayardan kaldırın.    

### <a name="the-software-cannot-be-installed"></a>Yazılım yüklenemiyor.

Hata: "Yazılım yüklenemiyor, 0x80cf4017."

**Sağlamak** İstemci yazılımı güncel değil.

#### <a name="resolution"></a>Çözüm
1. [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com) adresinde oturum açın.    
2. **Yönetici** > **istemci yazılımı indirmesi**' ne gidin ve ardından **istemci yazılımını indir**' e tıklayın.    
3. Yükleme paketini kaydedin ve ardından istemci yazılımını yükleme. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Hesap sertifikası geçerli değil ve zaman aşımına uğradı.

Hata: "Hesap sertifikası geçerli değil ve zaman aşımına ermeyebilir, 0x80cf4017."

**Sağlamak** İstemci yazılımı güncel değil.

#### <a name="resolution"></a>Çözüm
1. [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com) adresinde oturum açın.    
2. **Yönetici** > **istemci yazılımı indirmesi**' ne gidin ve ardından **istemci yazılımını indir**' e tıklayın.    
3. Yükleme paketini kaydedin ve ardından istemci yazılımını yükleme.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Kuruluşunuz bu Windows sürümünü desteklemiyor. 

Hata: "Bir sorun oluştu. Kuruluşunuz bu Windows sürümünü desteklemiyor.  (0x80180014) "

**Sağlamak** Windows MDM kaydı, Intune kiracınızda devre dışı bırakıldı.

#### <a name="resolution"></a>Çözüm
Tek başına bir Intune ortamında bu sorunu onarmak için aşağıdaki adımları izleyin: 
 
1. [Azure Portal](https://portal.azure.com/) yönetici olarak oturum açın.    
2. Sol tarafta **Intune** ' u seçin ve ardından **cihaz kaydı** > **Kayıt kısıtlamaları**' na gidin.    
3. **Cihaz türü kısıtlamaları**' nda **platformlar**' a ve ardından Windows için **ızın ver** ' i **(MDM)** seçin.    
4. **Kaydet**’e tıklayın.    
 
Bu sorunu Intune ve Configuration Manager ile karma MDM 'de onarmak için aşağıdaki adımları izleyin: 
1. Configuration Manager konsolunu açın.    
2. **Yönetim**' i ve ardından **Cloud Services**' yi seçin.    
3. **Microsoft Intune aboneliği**' ne sağ tıklayın ve ardından **Windows > platformları Yapılandır**' ı seçin.    
4. **Windows kaydını** > Etkinleştir > ' in Tamam '**ı**işaretleyin.  


### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Toplu kayıt sırasında bir kurulum hatası oluştu.

**Sağlamak** İlgili sağlama paketinin hesap paketindeki (Package_GUID) Azure AD Kullanıcı hesaplarının cihazların Azure AD 'ye katılmasına izin verilmez. Bu Azure AD hesapları, Windows yapılandırma Tasarımcısı (WCD) veya okul bilgisayarlarını ayarla uygulaması ile bir sağlama paketi ayarlarken otomatik olarak oluşturulur ve bu hesaplar daha sonra cihazları Azure AD 'ye katmak için kullanılır.

#### <a name="resolution"></a>Çözüm
1. [Azure Portal](https://portal.azure.com/) yönetici olarak oturum açın.    
2. **Cihaz ayarlarını > Azure Active Directory > cihazlar**' a gidin.    
3. **Kullanıcıları, cihazları Azure AD 'ye** **Tüm** veya **Seçili**olarak birleştirebileceği şekilde ayarlar.

   **Seçili**' i seçerseniz, **Seçili**' e tıklayın ve ardından, cihazlarını Azure AD 'ye birleştirebilen tüm kullanıcıları eklemek için **üye Ekle** ' ye tıklayın. Sağlama paketi için tüm Azure AD hesaplarının eklendiğinden emin olun.
 
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
- **MDM Kullanıcı kapsamı** **none**olarak ayarlanır. 

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

**MDM Kullanıcı kapsamı** **none**olarak ayarlandıysa, şu adımları izleyin: 
 
1. [Azure Portal](https://portal.azure.com/)oturum açın ve **Azure Active Directory**' ı seçin.
2. **Mobility (MDM ve MAM)** seçeneğini belirleyip **Microsoft Intune**seçin.    
3. **MDM Kullanıcı kapsamını** **Tümü**olarak ayarlayın. Ya da, **MDM Kullanıcı kapsamını** **bazılarına**ayarlayın ve Windows 10 cihazlarını otomatik olarak kaydedebilen grupları seçin.    
4. **Mam Kullanıcı kapsamını** **none**olarak ayarlayın.


### <a name="an-error-occurred-while-creating-autopilot-profile"></a>Autopilot profili oluşturulurken bir hata oluştu.

**Sağlamak** Cihaz adı şablonunun belirtilen adlandırma biçimi gereksinimleri karşılamıyor. Örneğin, seri makro için% seri% yerine% seri% gibi küçük harf kullanırsınız.

#### <a name="resolution"></a>Çözüm

Adlandırma biçiminin aşağıdaki gereksinimleri karşıladığından emin olun:

- Cihazlarınız için benzersiz bir ad oluşturun. Adlar 15 karakter veya daha az olmalıdır ve harf (a-z, A-Z), sayılar (0-9) ve kısa çizgi (verilere erişme) içerebilir.
- Ancak tamamen sayıdan oluşamaz.
- Adlarda boşluk bulunamaz.
- Donanıma özgü bir seri numarası eklemek için% SERIAL% makrosunu kullanın. Ya da rastgele bir sayı dizesi eklemek için% S_SAYI_ÜRET: < basamak sayısı >% makrosunu kullanın, dize > rakamlardan oluşan < # sayısını içerir. Örneğin, MYPC-% S_SAYI_ÜRET:% 6, MYPC-123456 gibi bir ad oluşturur.

### <a name="something-went-wrong-oobeidps"></a>Bir sorun oluştu. OOBEIDPS.

**Sağlamak** Bu sorun, kimlik sağlayıcısına (IDP) erişimi engelleyen bir ara sunucu, güvenlik duvarı veya başka bir ağ aygıtı varsa oluşur.

#### <a name="resolution"></a>Çözüm
Autopilot için internet tabanlı hizmetlere gereken erişimin engellenmediğinden emin olun. Daha fazla bilgi için bkz. [Windows Autopilot ağ gereksinimleri](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements-network).


### <a name="registering-your-device-for-mobile-management-failed3-0x801c03ea"></a>Cihazınızı mobil yönetim için kaydetme (başarısız oldu: 3, 0x801C03EA).

**Sağlamak** Cihazda 2,0 sürümünü destekleyen bir TPM yongası bulunur, ancak henüz 2,0 sürümüne yükseltilmemiştir.

#### <a name="resolution"></a>Çözüm
TPM yongasını 2,0 sürümüne yükseltin.

Sorun devam ederse, her gruba farklı bir Autopilot profili atanması halinde aynı cihazın iki atanmış grupta olup olmadığını kontrol edin. İki grupda varsa, cihaza hangi Autopilot profilinin uygulanacağını belirleyip, ardından diğer profilin atamasını kaldırın.

Windows cihazını Autopilot ile bilgi noktası modunda dağıtma hakkında daha fazla bilgi için bkz. [Windows Autopilot kullanarak bilgi noktası dağıtma](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/).


### <a name="securing-your-hardware-failed-0x800705b4"></a>Donanımınızın güvenliğini sağlama (başarısız oldu: 0x800705b4).

Hata 800705b4: 
```
Securing your hardware (Failed: 0x800705b4)
Joining your organization's network (Previous step failed)
Registering your device for mobile management (Previous step failed)
```

**Sağlamak** Hedeflenen Windows cihazı aşağıdaki gereksinimlerden birini karşılamıyor:

- Cihazda bir fiziksel TPM 2,0 yongasının olması gerekir. Sanal TPMs (örneğin, Hyper-V VM 'Leri) veya TPM 1,2 yongalarına sahip cihazlar kendi kendine dağıtım moduyla çalışmaz.
- Cihazın aşağıdaki Windows sürümlerinden birini çalıştırıyor olması gerekir:
    - Windows 10 derleme 1703 veya sonraki bir sürümü.
    - Karma Azure AD birleşimi kullanılırsa, Windows 10 derleme 1809 veya sonraki bir sürümü.


#### <a name="resolution"></a>Çözüm
Hedeflenen cihazın **neden** bölümünde açıklanan gereksinimleri karşıladığından emin olun.

Windows cihazını Autopilot ile bilgi noktası modunda dağıtma hakkında daha fazla bilgi için bkz. [Windows Autopilot kullanarak bilgi noktası dağıtma](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/).


### <a name="something-went-wrong-error-code-80070774"></a>Bir sorun oluştu. Hata kodu 80070774.

Hata 0x80070774: Bir sorun oluştu. Doğru oturum açma bilgilerini kullandığınızı ve kuruluşunuzun bu özelliği kullandığını onaylayın. Bunu yeniden deneyebilir veya 80070774 hata koduyla sistem yöneticinize başvurabilirsiniz.

Bu sorun, genellikle cihaz ilk oturum açma ekranında zaman aşımına uğrarsa karma bir Azure AD Autopilot senaryosunda cihaz yeniden başlatılmadan önce oluşur. Bağlantı sorunları nedeniyle etki alanı denetleyicisinin bulunamadığını veya başarıyla ulaşılamadığını gösterir. Ya da cihazın etki alanına katılamıyorum bir durum girmiş.

**Sağlamak** En yaygın neden, hibrit Azure AD JOIN 'in kullanıldığı ve Kullanıcı ata özelliğinin Autopilot profilinde yapılandırıldığı bir nedendir. Kullanıcı ata özelliğinin kullanılması, cihazın şirket içi etki alanınıza katılabileceği bir duruma koyduğu ilk oturum açma ekranı sırasında cihazda bir Azure AD katılımı gerçekleştirir. Bu nedenle, Kullanıcı ata özelliği yalnızca standart Azure AD JOIN Autopilot senaryolarında kullanılmalıdır.  Özellik, karma Azure AD JOIN senaryolarında kullanılmamalıdır.

#### <a name="resolution"></a>Çözüm

1. **Intune**cihazkaydı > **Windows kayıt** **cihazları**' na gidin. >  >  
2. Sorunu yaşayan cihazı seçin > en sağ taraftaki üç nokta (...) simgesine tıklayın.
3. **Kullanıcı atamasını Kaldır** ' ı seçin ve işlemin bitmesini bekleyin.
4. OOBE 'yi yeniden denemeden önce karma Azure AD Autopilot profilinin atandığını doğrulayın.

#### <a name="second-resolution"></a>İkinci çözünürlük
Sorun devam ederse, Intune Bağlayıcısı ile çevrimdışı etki alanına katılmayı barındıran sunucuda olay KIMLIĞI 30312 ' ın ODJ bağlayıcı hizmet günlüğünde kayıtlı olup olmadığını denetleyin. Event 30312 şuna benzer:

```
Log Name:      ODJ Connector Service
Source:        ODJ Connector Service Source
Event ID:      30132
Level:         Error
Description:
{
          "Metric":{
                   "Dimensions":{
                             "RequestId":"<RequestId>",
                             "DeviceId":"<DeviceId>",
                             "DomainName":"contoso.com",
                             "ErrorCode":"5",
                             "RetryCount":"1",
                              "ErrorDescription":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation",
                              "InstanceId":"<InstanceId>",
                              "DiagnosticCode":"0x00000800",
                              "DiagnosticText":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation [Exception Message: \"DiagnosticException: 0x00000800. Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation\"] [Exception Message: \"Failed to call NetProvisionComputerAccount machineName=<ComputerName>\"]"
                   },
                   "Name":"RequestOfflineDomainJoinBlob_Failure",
                   "Value":0
          }
}
```

Bu sorun genellikle Windows Autopilot cihazlarının oluşturulduğu kuruluş birimine izinlerin yanlış şekilde verilmesine neden olur. Daha fazla bilgi için bkz. [kuruluş birimindeki bilgisayar hesabı sınırını artırma](windows-autopilot-hybrid.md#increase-the-computer-account-limit-in-the-organizational-unit).

1. **Active Directory Kullanıcıları ve bilgisayarları (dsa. msc)** açın.
2. **Temsilci denetim**>, karma Azure AD 'ye katılmış bilgisayarları oluşturmak için kullanacağınız kurumsal birimi sağ tıklatın.
3. **Denetim temsili** sihirbazında, **İleri** > **nesne türleri** **Ekle** > ' yi seçin.
4. **Nesne türleri** bölmesinde, **Tamam**> **bilgisayarlar** onay kutusunu seçin.
5. **Kullanıcıları**, **bilgisayarları**veya **grupları** seçin bölmesinde **Seçilecek nesne adlarını girin** kutusuna bağlayıcının yüklendiği bilgisayarın adını girin.
6. Girdinizi doğrulamak için **adları denetle** '**yi**seçin > **Tamam ' ı** > seçin.
7.  > **Daha sonra** **atamak için özel bir görev oluştur**' u seçin.
8. Klasör onay kutusunda **yalnızca şu nesneleri** seçin ve ardından **bilgisayar nesnelerini**seçin, **Bu klasörde seçili nesneleri oluşturun**ve **Seçili nesneleri bu klasörde silin** onay kutularını işaretleyin.
9. **İleri**’yi seçin.
10. **İzinler**altında **tam denetim** onay kutusunu seçin. Bu eylem diğer tüm seçenekleri seçer.
11. **İleri** > **son**' u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Intune’da cihaz kaydı sorunlarını giderme](troubleshoot-device-enrollment-in-intune.md)
- [Intune forumundan soru sorun](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Microsoft Intune destek ekibi blogunu denetleyin](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Microsoft Enterprise Mobility ve Security blogunu denetleyin](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Microsoft Intune için destek alın](get-support.md)
