---
title: Microsoft Intune ile JAMF Pro tümleştirmesi sorunlarını giderme
titleSuffix: Microsoft Intune
description: Mac cihazları için JAMF Pro 'Yu Microsoft Intune ile tümleştirdiğinizde, en yaygın sorunlardan bazılarının sorunlarını gidermeye yönelik öneriler.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e92e3442e1347cb1a2cd1c737078912b74f075c9
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71817558"
---
# <a name="troubleshoot-integration-of-jamf-pro-with-microsoft-intune"></a>JAMF Pro ile Microsoft Intune tümleştirme sorunlarını giderme

Bu makale, Intune yöneticilerinin macOS for macOS için Intune ile tümleştirmesiyle ilgili sorunları anlamayı ve sorunlarını gidermenize yardımcı olur.

> [!TIP]  
> Bu makaledeki bilgilerin çoğu, support.microsoft.com üzerindeki [Microsoft Intune JAMF ile tümleştirdiğinizde sorun giderme sorunları giderilir](https://support.microsoft.com/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune) .

## <a name="prerequisites"></a>Önkoşullar

Sorun gidermeye başlamadan önce, sorunu açıklığa kavuşturmak ve çözüm bulma süresini azaltmak için bazı temel bilgileri toplayın. Örneğin, JAMF-Intune tümleştirmesiyle ilgili bir sorunla karşılaştığınızda, her zaman önkoşulların karşılandığından emin olun. Sorun gidermeye başlamadan önce aşağıdaki konuları gözden geçirin:

- [JAMF Pro 'Yu Intune Ile tümleştirme](conditional-access-integrate-jamf.md#prerequisites)' dan önkoşulları gözden geçirin.
- Tüm kullanıcıların Microsoft Intune ve Microsoft AAD Premium P1 lisanslarına sahip olması gerekir 
- JAMF Pro konsolunda Microsoft Intune tümleştirme izinlerine sahip bir kullanıcı hesabına sahip olmanız gerekir.
- Azure 'da genel yönetici izinlerine sahip bir kullanıcı hesabına sahip olmanız gerekir.


Intune ile JAMF Pro tümleştirmesini araştırırken aşağıdaki bilgileri göz önünde bulundurun: 
- Hata iletisinde tam olarak ne yazıyor?
- Hata iletisi nerede?
- Sorun ne zaman başladı?  Intune ile JAMF Pro tümleştirmesi hiç çalıştı mı?
- Kaç Kullanıcı etkilendi? Tüm kullanıcılar mı etkilendi?
- Kaç cihaz etkilendi? Tüm cihazlar etkileniyor mu ya da yalnızca bir şey var mı?
 

## <a name="common-problems"></a>Yaygın sorunlar 

Aşağıdaki bilgiler, Intune ve JAMF Pro tümleştirmesini ayarladıktan sonra cihazlarda yaygın sorunları belirlemenize ve çözmenize yardımcı olabilir.  

| Sorun   | Daha fazla bilgi                  |
|-----------------|--------------------------|
| **JAMF Pro 'da cihazlar yanıt vermiyor olarak işaretlendi**  | [Cihazlar JAMF Pro ile veya Azure AD ile iade etme başarısız](#devices-are-marked-as-unresponsive-in-jamf-pro) |
| **Mac cihazları bir uygulama cihazını açtığınızda Anahtarlık oturum açma işlemi için istemde bulun**  | [Kullanıcıların, uygulamaların Azure AD 'ye kaydolmalarına izin vermek için parola girmesi istenir](#mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app). |
| **Cihazların kaydı başarısız oldu**  | Aşağıdaki nedenler şunlar olabilir: <br> **-** [ ***Neden 1*** -Azure 'da JAMF Pro uygulamasının izinleri yanlış](#cause-1) <br> **-** [ ***neden 2*** -Azure AD 'de *JAMF Native MacOS Bağlayıcısı* için bir sorun var](#cause-2) <br> **-** [ ***Neden 3*** -kullanıcının geçerli bir Intune veya JAMF lisansı yok](#cause-3) <br> **-** [ ***Neden 4*** -Kullanıcı, Şirket portalı uygulamayı başlatmak için JAMF Self Service 'i kullanmadı](#cause-4) <br> **-** [ ***neden 5*** -Intune tümleştirmesi kapalı](#cause-5) <br> **-** [ ***Neden 6*** -cihaz daha önce Intune 'a kaydoldu veya Kullanıcı cihazı birden çok kez kaydetmeyi denedi](#cause-6) <br> **-** [ ***neden 7*** -jamfaad istekleri kullanıcıların anahtarlığınızdan bir "Microsoft Workplace Join anahtarına" erişim istiyor](#cause-7) |
|  **Mac cihazı, Azure 'da Intune ile uyumlu ancak uyumsuz olarak gösteriliyor** | [Cihaz kayıt sorunları](#mac-device-shows-compliant-in-intune-but-noncompliant-in-azure) |
| **JAMF kullanılarak kaydedilen Mac cihazları için Intune konsolunda yinelenen girişler görüntülenir** | [Birden çok kayıt aynı cihazı testten olarak](#duplicate-entries-appear-in-the-intune-console-for-mac-devices-enrolled-by-using-jamf) |
| **Uyumluluk ilkesi cihazı değerlendiremiyor** | [İlke, cihaz gruplarını hedefliyor](#compliance-policy-fails-to-evaluate-the-device) |
| **Microsoft Graph API 'SI için erişim belirteci alınamadı** | Aşağıdaki nedenler şunlar olabilir: <br> [Azure 'Da JAMF Pro uygulaması için](#theres-a-permission-issue-with-the-jamf-pro-application-in-azure) - izinleri <br> @no__t-[JAMF veya Intune için](#a-license-required-for-jamf-intune-integration-has-expired) 0 süre sonu lisansı <br> **-** [bağlantı noktaları açık değil](#the-required-ports-arent-open-on-your-network)|
 

### <a name="devices-are-marked-as-unresponsive-in-jamf-pro"></a>JAMF Pro 'da cihazlar yanıt vermiyor olarak işaretlendi  

**Neden**: aşağıda, cihazların JAMF Pro tarafından *yanıt vermeyen* olarak işaretlendikleri yaygın nedenleri verilmiştir:

- Cihaz, JAMF Pro ile iade etme işlemi yapamıyor.  
  JAMF Pro cihazların 15 dakikada bir iade olmasını bekler. Cihazlar, 24 saatlik bir dönemde iade etme başarısız olduğunda JAMF tarafından yanıt vermiyor olarak işaretlenir.  

- Cihaz Azure AD 'ye iade etme işlemi yapamıyor.  
  Azure AD 'ye başarıyla kaydolma, macOS cihazları bir Azure belirteci alır:
  - Bu belirteç her 12 saatte bir yenilenir.   
  - Belirteç yenilemesi 24 saat veya daha uzun bir sürede başarısız olduğunda, JAMF Pro cihazı yanıt vermeyen olarak işaretler.  
  - Azure belirtecinin süresi dolarsa, kullanıcılardan yeni bir belirteç almak için Azure 'da oturum açması istenir. Her yedi günde bir Azure erişimi için yenileme belirteci oluşturulur.

**Çözünürlüğüne**  
Bir cihaz JAMF Pro *yanıt vermiyor* olarak işaretlendikten sonra, cihazın kayıtlı kullanıcısının yanıt vermeyen durumunu düzeltmek için oturum açması gerekir. Bu, kullanıcının oturum açma anahtarlığışı içinde Intune 'dan kimliğe sahip olduğu hesaba katılmış olan kullanıcı olmalıdır.



### <a name="mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app"></a>Mac cihazları bir uygulamayı açtığınızda Anahtarlık oturum açma için istemde bulun  

Intune ve JAMF Pro tümleştirmesini yapılandırdıktan ve koşullu erişim ilkeleri dağıttıktan sonra, JAMF Pro alma ile yönetilen cihazların kullanıcıları takımlar, Outlook ve Azure gerektiren diğer uygulamalar gibi Microsoft Office 365 uygulamalarını açarken parola ister. AD kimlik doğrulaması. 

Örneğin, aşağıdaki örneğe benzer bir metin istemi Microsoft ekipleri açılırken görünür:

``` 
  Microsoft Teams wants to sign using key “Microsoft Workplace Join Key” in your keychain.  
  To allow this, enter the “login” keychain password 
```

**Neden**: Bu Istemler, Azure ad kaydı gerektiren her ilgili uygulama Için JAMF Pro tarafından oluşturulmuştur. 

**Çözüm**   
Sorulduğunda, kullanıcının Azure AD 'de oturum açmak için cihaz parolasını sağlaması gerekir. Seçeneklere şunlar dahildir:
- **Reddet** -oturum açma ve uygulamayı kullanmayın.
- **Izin ver** -bir kez oturum açma. Uygulama bir dahaki sefer açıldığında, oturum açmayı yeniden sorar.
- **Her zaman Izin ver** -oturum açma kimlik bilgileri uygulama için önbelleğe alınır. Uygulama bir dahaki sefer açıldığında oturum açma istemez.  

Tek bir uygulama için *her zaman Izin ver* seçildiğinde bu uygulama yalnızca gelecekteki oturum açma için onaylanır. Ek uygulamalar *her zaman Izin ver*olarak ayarlanana kadar kimlik doğrulaması için istemde bulunur. Bir uygulama için önbelleğe alınan kimlik bilgileri başka bir uygulama tarafından kullanılamaz.  

### <a name="devices-fail-to-register"></a>Cihazların kaydı başarısız oldu  

Mac cihazlarının kaydedemeyecek bazı yaygın nedenleri vardır.  

#### <a name="cause-1"></a>Neden 1  

**Azure 'daki JAMF Pro Enterprise uygulamasının izinleri yanlış veya birden fazla izni vardır**  

  Uygulamayı Azure 'da oluşturduğunuzda, tüm varsayılan API izinlerini kaldırmalı ve ardından Intune 'un tek bir *update_device_attributes*atamasını atamanız gerekir. 

  **Çözünürlüğüne**  
  Azure AD 'de oluşturduğunuz JAMF uygulamasının izinlerini gözden geçirin ve gerekirse düzeltin. [Azure AD 'de JAMF için uygulama oluşturma](conditional-access-integrate-jamf.md#create-an-application-in-azure-active-directory)yordamına bakın. 

#### <a name="cause-2"></a>Neden 2  

****JAMF Native macOS bağlayıcı** uygulaması, Azure AD kiracınızda oluşturulmamış veya bağlayıcı için onay onayı, genel yönetici haklarına sahip olmayan bir hesap tarafından imzalandı**  

  **Çözünürlüğüne**  
  Docs.jamf.com üzerinde [Microsoft Intune tümleştirmede](https://docs.jamf.com/10.13.0/jamf-pro/administrator-guide/Integrating_with_Microsoft_Intune.html) *MacOS Intune tümleştirmesini yapılandırma* bölümüne bakın. 

#### <a name="cause-3"></a>Neden 3

**Kullanıcının geçerli bir Intune veya JAMF lisansı yok**  

  Geçerli bir lisansın olmaması, JAMF lisansının dolduğunu belirten aşağıdaki hataya yol açabilir:  
  ```
    Unable to connect to Microsoft Intune.  
    
    Check your Microsoft Intune Integration configuration.
  ```  

  **Çözünürlüğüne**
  - JAMF lisansı: JAMF için yeni bir lisans edinme yardımı için JAMF ile Iletişim kurun.  
  - Intune lisansı: kullanıcıya geçerli bir lisans atayın veya geçerli bir lisansın nasıl alınacağı hakkında bilgi için Microsoft veya Iş ortağınız ile iletişim kurun.

#### <a name="cause-4"></a>Neden 4  

**Kullanıcı Şirket Portalı uygulamayı başlatmak için *JAMF Self Service* 'i kullanmadı**

Bir cihazın JAMF aracılığıyla Intune 'a başarıyla kaydolmasını ve kaydolmasını sağlamak için, kullanıcının Intune Şirket Portalı açması için JAMF Self Service kullanması gerekir. Kullanıcı şirket portalını el ile açarsa, cihaz, JAMF bağlantısı olmadan kaydolur ve kaydettirir.  

Cihazın kaydetmek ve kaydetmek için kullandığı hizmeti öğrenmek için cihazdaki Şirket Portalı uygulamasına bakın. JAMF üzerinden kaydedildiğinde, değişiklikler yapmak için Self Servis uygulamasını açmak üzere bir bildirim almanız gerekir.

Şirket Portalı uygulamasında, Kullanıcı **`Not registered`** ' i görebilir ve aşağıdaki örneğe benzer bir giriş şirket portalı günlüklerinde görünebilir:  

```
   Line 7783: <DATE> <IP ADDRESS> INFO com.microsoft.ssp.application TID=1  
 
   WelcomeViewController.swift: 253 (startLogin()) Portal launched without WPJ only arg while account is under partner management
```

**Çözünürlüğüne**  
Kayıt kaynağını Intune 'dan JAMF 'ye değiştirmek için:
1. [MacOS cihazının Intune kaydını](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-macos)silme. Intune 'dan tamamen kaldırılmamış cihazların daha karmaşıklıkları önlemek için, bu nedenler listesinde 6 ' ya [*neden*](#cause-6) oldu konusuna bakın.  

2. Cihazda, Şirket Portalı uygulamasını açmak için JAMF Self Service kullanın ve ardından cihazı Intune 'a kaydedin. Bu görev, [macOS için şirket portalı uygulamasını dağıtmak Için JAMF](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro)kullanmanızı ve [Kullanıcı cihazını Azure AD 'ye kaydeden JAMF Pro 'da bir ilke oluşturulmasını](conditional-access-assign-jamf.md#create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory)gerektirir.  

3. Portal açıldığında, gördüğünüz ilk ekran oturum açmanızı ister. İş veya okul hesabınızı kullanın  

4. Şirket Portalı hesap bilgilerinizi onaylar ve cihaz kaydınız ile cihaz uyumluluk durumlarını gösterir. Sarı üçgenler, macOS cihazınızın okul veya çalışma için güvenliğini sağlamak üzere gerçekleştirmeniz gereken eylemleri vurgular. Kaydı başlatmak için Başlat ' a tıklayın.  

5. İstenirse bilgisayarınızın oturum açma bilgilerini yazın.  
     
Cihazınızın yönetimine kaydedilmesi birkaç dakika sürebilir. Bu süre boyunca cihazınızda başka şeyler yapabilirsiniz. Şirket erişimi kurulumunu tamamladıktan sonra, işiniz gerektiğini bilmenizi sağlamak için bir ileti alırsınız.

#### <a name="cause-5"></a>Neden 5  

**Intune tümleştirmesi kapalı**

Intune tümleştirmesi kapalıysa, kullanıcılar bir cihazı kaydetmeye çalıştıklarında aşağıdaki iletiyle Şirket Portalı bir açılır pencere alır:  

```
   Invalid command line input
   
   Registration-only command line flag (-r) can only be used when partner management is enabled in Intune. Please contact your IT admin.
```  

JAMF Pro sunucusu, Intune 'un tümleştirme devre dışı bırakıldığını bildiren bir tümleştirme devre dışı bırakıldığında, Intune sunucularına bir Pulse gönderir. 

**Çözünürlüğüne**  
JAMF Pro içinde Intune tümleştirmesini yeniden etkinleştirin. Bkz. [JAMF Pro 'da Microsoft Intune tümleştirmesini yapılandırma](conditional-access-integrate-jamf.md#enable-intune-to-integrate-with-jamf-pro).


#### <a name="cause-6"></a>Neden 6  

**Cihaz daha önce Intune 'a kaydoldu veya Kullanıcı cihazı birden çok kez kaydetmeyi denedi**

Bir cihazın JAMF 'den kaydı kaldırılırsa ancak Intune 'dan doğru şekilde kaldırılmadıysa veya birkaç kayıt girişimi yapıldığında, portalda aynı cihazın birden çok örneğini görebilirsiniz. Bu, JAMF kaydının başarısız olmasına neden olur.

**Çözünürlüğüne**  
1. Mac üzerinde, **terminali**başlatın.
2. **Sudo JAMF removemdmprofile**komutunu çalıştırın.
3. **Sudo JAMF removeFramework 'ü**çalıştırın.
4. JAMF Pro sunucusunda bilgisayarın envanter kaydını silin.
5. Cihazı AzureAD konumundan silin.
6. Varsa, cihazdaki aşağıdaki dosyaları silin:
   - /Library/Application Support desteği/com. Microsoft. CompanyPortal. UserContext. INFO
   - /Library/Application Support desteği/com. Microsoft. CompanyPortal
   - /Library/Application Support desteği/com. jamfsoftware. selfservice. Mac
   - /Library/Saved uygulaması
   - Eyalet/com. jamfsoftware. selfservice. Mac. savedState
   - /Library/Saved uygulama durumu/com. Microsoft. CompanyPortal. savedState
   - /Library/Preferences/com.microsoft.CompanyPortal.plist
   - /Library/Preferences/com.jamfsoftware.selfservice.mac.plist
   - /Library/Preferences/com.jamfsoftware.management.jamfAAD.plist
   - /Users/<username>/Library/Cookies/com. Microsoft. CompanyPortal. binarycookies
   - /Users/<username>/Library/Cookies/com. JAMF. Management. jamfAAD. binarycookies
   - com. Microsoft. CompanyPortal
   - com. Microsoft. CompanyPortal. HockeySDK
   - enterpriseregistration.windows.net
   - https://device.login.microsoftonline.com
   - https://device.login.microsoftonline.com/
   - Microsoft oturum aktarma anahtarı (ortak ve özel anahtarlar)
   - Microsoft Workplace Join anahtarı (ortak ve özel anahtarlar)
7. DeviceLogin.microsoft.com sertifikaları dahil olmak üzere *Microsoft*, *Intune*veya *Şirket portalı*başvuran cihazdaki anahtarlıktan herhangi bir şeyi kaldırın. JAMF ortak ve özel anahtar dışında *JAMF* başvurularını kaldırın. 
   > [!IMPORTANT]  
   > Ortak ve özel anahtarı kaldırmak, cihaz kaydını keser.

8. Bulduğunuz aşağıdaki girdilerden birini silin:  
   - Tür: uygulama parolası; Hesap: com. Microsoft. workplacejoın. parmak izi
   - Tür: uygulama parolası; Hesap: com. Microsoft. workplacejoın. registeredUserPrincipalName
   - Tür: sertifika; Veren: MS-Kuruluş-erişim
   - Tür: Kimlik tercihi; Ad (varsa ADFS STS URL 'SI): https://adfs\<DNSName>.com/adfs/ls
   - Tür: Kimlik tercihi; Ad: https://enterpriseregistration.windows.net
   - Tür: Kimlik tercihi; Ad: https://enterpriseregistration.windows.net/  
9. Mac cihazını yeniden başlatın.
10. Cihazdan Şirket Portalı kaldırın.
11. Portal.manage.microsoft.com adresine gidin ve Mac cihazının tüm örneklerini silin. Sonraki adıma geçmeden önce en az 30 dakika bekleyin.
12. Cihazı JAMF Pro 'Ya yeniden kaydedin.
13. Self Servis 'i yeniden açın ve kayıt ilkesini başlatın.


#### <a name="cause-7"></a>Neden 7  

**JamfAAD, kullanıcıların anahtarlığınızdan bir "Microsoft Workplace Join anahtarına" erişim ister**

Kayıt sırasında, macOS cihazının kullanıcısı anahtar anahtarlarından bir anahtara JamfAAD erişimine izin vermek için aşağıdaki istemi alır: 

```
   JamfAAD wants to access key “Microsoft Workplace Join Key" in your keychain. 
    
   To allow this, enter the “login” keychain password
```

**Çözünürlüğüne**  
Cihazı Azure AD 'ye başarıyla kaydetmek için JAMF kullanıcının hesap parolasını sağlamasını ve **Izin ver**' i seçmesini gerektirir.

Bu istek, bu makalenin önceki kısımlarında yer aldığı [bir uygulamayı açtığınızda Anahtarlık oturum açma Için Mac cihazlarına](#mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app)yönelik isteğe benzerdir.  

 
### <a name="mac-device-shows-compliant-in-intune-but-noncompliant-in-azure"></a>Mac cihazı, Azure 'da Intune ile uyumlu ancak uyumsuz olarak gösteriliyor  

**Neden**: aşağıdaki koşullar, bir cihazın Intune 'da uyumlu olmasına karşın Azure 'da uyumlu olmadığı gösterebilir:  
- Cihaz doğru kaydettirilmemiş.  
- Cihaz, gerekli temizlik olmadan birden çok kez kaydedildi.

**Çözünürlüğüne**  
Bu sorunu çözmek için, bu makalenin önceki kısımlarında yer aldığı *cihazların* [*6. nedenine*](#cause-6) yönelik çözümü izleyin. 


### <a name="duplicate-entries-appear-in-the-intune-console-for-mac-devices-enrolled-by-using-jamf"></a>JAMF kullanılarak kaydedilen Mac cihazları için Intune konsolunda yinelenen girişler görüntülenir  
 
**Neden**: bir cihaz Intune 'a birden çok kez kaydedilir, genellikle Intune 'dan kaldırıldıktan sonra yeniden kaydedilir.  

Bir cihaz Intune ve JAMF Pro tümleştirmesinden kaldırıldığında, bazı veriler arka arkaya kalabilir ve bu da sonraki kayıtlar yinelenen girişler oluşturulmasına neden olabilir.  

**Çözünürlüğüne**  
Bu sorunu çözmek için, bu makalenin önceki kısımlarında yer aldığı *cihazların* [*6. nedenine*](#cause-6) yönelik çözümü izleyin. 

### <a name="compliance-policy-fails-to-evaluate-the-device"></a>Uyumluluk ilkesi cihazı değerlendiremiyor  

**Neden**: Intune ile JAMF tümleştirmesi, cihaz gruplarını hedefleyen Uyumluluk ilkesini desteklemez. 

**Çözünürlüğüne**  
MacOS cihazlarının Uyumluluk ilkesini Kullanıcı gruplarına atanacak şekilde değiştirin. 


### <a name="could-not-retrieve-the-access-token-for-microsoft-graph-api"></a>Microsoft Graph API 'SI için erişim belirteci alınamadı

Aşağıdaki hatayı alıyorsunuz:

```
   Could not retrieve the access token for Microsoft Graph API. Check the configuration for Microsoft Intune Integration.
```   

Bu hatanın kaynağı aşağıdakilerden biri olabilir: 

#### <a name="theres-a-permission-issue-with-the-jamf-pro-application-in-azure"></a>Azure 'da JAMF Pro uygulamasıyla ilgili bir izin sorunu var

JAMF Pro uygulamasını Azure 'a kaydederken aşağıdaki koşullardan biri oluştu:  
- Uygulama birden fazla izin aldı.
- ***@No__t-2 > şirketiniz* Için yönetici onayı verme** seçeneği seçilmemiş.  

**Çözünürlüğüne**  
Bu makalenin önceki bölümlerinde yer aldığı [cihazların](#devices-fail-to-register)1. nedeni için çözüm bölümüne bakın.

#### <a name="a-license-required-for-jamf-intune-integration-has-expired"></a>JAMF-Intune tümleştirmesi için gereken bir lisansın süresi doldu

**Çözüm**: [cihazların kaydolması](#devices-fail-to-register)için neden 3 ' ün çözümüne bakın. 

#### <a name="the-required-ports-arent-open-on-your-network"></a>Gerekli bağlantı noktaları ağınızda açık değil

**Çözüm**: JAMF Pro 'yu Intune ile tümleştirmek için [önkoşulları](conditional-access-integrate-jamf.md#prerequisites) içindeki ağ bağlantı noktaları için bilgileri gözden geçirin.


## <a name="next-steps"></a>Sonraki adımlar
[JAMF Pro 'Yu Intune ile tümleştirme](conditional-access-integrate-jamf.md) hakkında daha fazla bilgi edinin