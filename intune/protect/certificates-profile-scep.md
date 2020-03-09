---
title: Azure Microsoft Intune SCEP sertifika profillerini kullanma | Microsoft Docs
description: Microsoft Intune ile Basit Sertifika Kayıt Protokolü (SCEP) sertifika profilleri oluşturun ve atayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a8daab16d0b595444ff5cb13f97cd2703127340
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78369881"
---
# <a name="create-and-assign-scep-certificate-profiles-in-intune"></a>Intune 'da SCEP sertifika profilleri oluşturma ve atama

Altyapınızı Basit Sertifika Kayıt Protokolü (SCEP) sertifikalarını destekleyecek şekilde [yapılandırdıktan](certificates-scep-configure.md) sonra, Intune 'da kullanıcılara ve cihazlara SCEP sertifika profilleri oluşturup atayabilirsiniz.

> [!IMPORTANT]  
> SCEP sertifika profilleri oluşturmadan önce, SCEP sertifika profilini kullanacak cihazların güvenilen kök sertifika yetkilinizin (CA) güvenmesi gerekir. Intune 'da güvenilen bir *sertifika profili* kullanarak güvenilen sertifika profili hakkında bilgi edinmek Için GÜVENILEN kök CA sertifikasını kullanıcılara ve cihazlara sağlama konusuna bakın. [Güvenilen kök CA sertifikasını dışarı aktarma](certificates-configure.md#export-the-trusted-root-ca-certificate) ve [Güvenilen sertifika profilleri oluşturma](certificates-configure.md#create-trusted-certificate-profiles) ' da *Intune 'da kimlik doğrulaması için sertifikaları kullanma*.


## <a name="create-a-scep-certificate-profile"></a>Bir SCEP sertifika profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profili** > **cihazları** seçin.

3. Aşağıdaki özellikleri girin:

4. SCEP sertifika profili için bir **Ad** ve **Açıklama** girin.

5. **Platform** açılan listesinde, bu SCEP sertifikası için desteklenen bir [Cihaz platformu](certificates-configure.md#supported-platforms-and-certificate-profiles) seçin.

6. **Profil türü** açılan listesinden **SCEP sertifikası**' nı seçin.  

   **Android kurumsal** platformu için *profil türü* , yalnızca *cihaz sahibi* ve *yalnızca iş profili*olmak üzere iki kategoriye ayrılmıştır. Yönettiğiniz cihazlar için doğru SCEP sertifika profilini seçtiğinizden emin olun.  

   *Yalnızca cihaz sahibi* profılı için SCEP sertifika profilleri aşağıdaki sınırlamalara sahiptir:

   1. Izleme altında, sertifika raporlama cihaz sahibi SCEP sertifika profilleri için kullanılamaz.

   2. Cihaz sahipleri için SCEP sertifika profilleri tarafından sağlanan sertifikaları iptal etmek için Intune 'U kullanamazsınız. İptali bir dış işlem veya doğrudan sertifika yetkilisi ile yönetebilirsiniz. 

   4. Android kurumsal adanmış cihazlarda, SCEP sertifika profilleri yalnızca Wi-Fi ağ yapılandırması ve kimlik doğrulaması için desteklenir.  Android kurumsal adanmış cihazlarda SCEP sertifika profilleri VPN veya uygulama kimlik doğrulaması için desteklenmez.   

   
7. **Ayarlar**' ı seçin ve ardından aşağıdaki konfigürasyonları doldurun:

   - **Sertifika türü**:

     *(İçin geçerlidir: Android, Android Enterprise, iOS/ıpados, macOS, Windows 8.1 ve üzeri ve Windows 10 ve üzeri.)*

     Sertifika profilini nasıl kullanacağınızı gösteren bir tür seçin:

     - **Kullanıcı**: *Kullanıcı* sertifikaları hem Kullanıcı hem de cihaz özniteliklerini, sertifikanın konu ve San 'ı içerebilir.  
     - **Cihaz**: *cihaz* sertifikaları, sertifikanın konu ve San 'ı yalnızca cihaz özniteliklerini içerebilir.

       **Cihazı** , kiosks gibi Kullanıcı-daha az cihazlar veya Windows cihazları gibi senaryolar için kullanın. Windows cihazlarında, sertifika yerel bilgisayar sertifika deposuna yerleştirilir.

   - **Konu adı biçimi**:

     Intune 'un sertifika isteğinde konu adını otomatik olarak nasıl oluşturduğunu seçin. Konu adı biçimi için seçenekler, **Kullanıcı** veya **cihaz**' ı seçtiğiniz sertifika türüne bağlıdır.

     > [!NOTE]
     > Elde edilen sertifika Imzalama Isteğindeki (CSR) konu adı, kaçış karakteri olarak şu karakterlerden birini içerdiğinde (bir ters eğik çizgi \\), sertifika almak için SCEP kullanmanın [bilinen bir sorunu](#avoid-certificate-signing-requests-with-escaped-special-characters) vardır:
     > - \+
     > - ;
     > - ,
     > - =

     - **Kullanıcı sertifika türü**

       *Konu adı biçimi* için biçim seçenekleri şunları içerir:

       - **Yapılandırılmadı**
       - **Ortak ad**
       - **E-postayı içeren ortak ad**
       - **E-posta olarak ortak ad**
       - **IMEI (Uluslararası Mobil Donanım Kimliği)**
       - **Seri numarası**
       - **Özel**: Bu seçeneği işaretlediğinizde bir **Özel** metin kutusu da gösterilir. Bu alanı, değişkenler dahil özel bir konu adı biçimi girmek için kullanın. Özel biçim, şu iki değişkeni destekler: **Ortak Ad (CN)** ve **E-posta (E)** . **Ortak Ad (CN)** şu iki değerden biri olarak ayarlanabilir:

         - **CN = {{username}}** : kullanıcının janedoe@contoso.comgibi Kullanıcı asıl adı.
         - **CN={{AAD_Device_ID}}** : Azure Active Directory’ye (AD) yeni bir cihaz kaydettiğinizde atanan bir kimlik. Bu kimlik genellikle Azure AD’de kimlik doğrulamak için kullanılır.
         - **CN = {{SERIALNUMBER}}** : genellikle üretici tarafından bir cihazı tanımlamak için kullanılan benzersiz seri numarası (sn).
         - **CN = {{ımekarmsayı}}** : bir cep telefonu tanımlamak Için kullanılan uluslararası mobil ekipman KIMLIĞI (IMEI) benzersiz numarası.
         - **CN = {{OnPrem_Distinguished_Name}}** : *CN = Gamze Etikan, OU = USERACCOUNTS, DC = Corp, DC = contoso, DC = com*gibi virgülle ayrılmış göreli ayırt edici adların sırası.

           *{{OnPrem_Distinguished_Name}}* değişkenini kullanmak Için, Azure AD 'nize [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak *onpremisesdistinguishedname* Kullanıcı özniteliğini eşitlediğinizden emin olun.

         - **CN = {{onPremisesSamAccountName}}** : Yöneticiler, *adlı BIR*özniteliğe Azure AD connect kullanarak sAMAccountName ÖZNITELIĞINI Active Directory 'den Azure AD 'ye eşitleyebilir. Intune, bu değişkeni bir sertifika konusunun sertifika verme isteğinin bir parçası olarak kullanabilir. SamAccountName özniteliği, Windows 'un önceki bir sürümünden (Windows 2000 öncesi) istemcileri ve sunucuları desteklemek için kullanılan Kullanıcı oturum açma adıdır. Kullanıcı oturum açma adı biçimi: EtkiAlanıAdı \ *testuser*veya yalnızca *testuser*.

            *{{OnPremisesSamAccountName}}* değişkenini kullanmak Için, Azure AD 'nize [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak *onPremisesSamAccountName* User özniteliğini eşitlediğinizden emin olun.

         Bu değişkenlerin ve statik dizelerin bir veya birkaç tanesinin bir bileşimini kullanarak aşağıdaki gibi özel bir konu adı biçimi oluşturabilirsiniz:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

         Bu örnekte, CN ve E değişkenlerini kullanan bir konu adı biçimi ve kuruluş birimi, kuruluş, konum, durum ve ülke değerleri için dizeler bulunur. [CertStrToName işlevi](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx), bu işlevi ve desteklenen dizelerini açıklar.

      - **Cihaz sertifika türü**

        Konu adı biçimi için biçim seçenekleri aşağıdaki değişkenleri içerir:

        - **{{AAD_Device_ID}}** veya **{{azureaddeviceıd}}** -her iki değişken de BIR cihazı Azure AD kimliğine göre belirlemek için kullanılabilir.
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{Imekarmsayı}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEı}}**
        - **{{Aygıtadı}}**
        - **{{Fullyıqualifieddomainname}}** *(yalnızca Windows ve etki alanına katılmış cihazlar için geçerlidir)*
        - **{{MEıD}}**

        Bu değişkenleri ve metin kutusu içinde değişkeni için metni belirtebilirsiniz. Örneğin, *Device1* adlı bir cihazın ortak adı **CN = {{aygıtadı}} Device1**olarak eklenebilir.

        > [!IMPORTANT]
        > - Bir değişken belirttiğinizde, bir hatadan kaçınmak için, değişken adını örnekte görüldüğü gibi küme ayraçları {} içine alın.  
        > - **IMEI**, **SerialNumber**ve **fullyıqualifieddomainname**gibi bir cihaz sertifikasının *Konu* veya *San* 'ı üzerinde kullanılan cihaz özellikleri, cihaza erişimi olan bir kişi tarafından sızılmış özelliklerdir.
        > - Bir cihazın, bu cihaza yüklemek için bir sertifika profilinde belirtilen tüm değişkenleri desteklemesi gerekir.  Örneğin, bir SCEP profilinin konu adında **{{IMEI}}** kullanılıyorsa ve IMEI numarası olmayan bir cihaza atanırsa, profil yüklenemez.

   - **Konu diğer adı**: Intune 'un sertifika isteğinde konu alternatif adı 'Nı (San) otomatik olarak nasıl oluşturduğunu seçin. SAN seçenekleri seçtiğiniz sertifika türüne bağlıdır; **Kullanıcı** ya da **cihaz**.

      - **Kullanıcı sertifika türü**

        Kullanılabilir özniteliklerden seçin:

        - **E-posta adresi**
        - **Kullanıcı asıl adı (UPN)**

        Örneğin, Kullanıcı sertifika türleri konu alternatif adına Kullanıcı asıl adını (UPN) içerebilir. İstemci sertifikası bir Ağ İlkesi Sunucusunda kimlik doğrulamak için kullanılacaksa konu alternatif adını UPN'ye ayarlayın.

      - **Cihaz sertifika türü**

        **Öznitelik** açılan listesini kullanın ve bir öznitelik seçin, bir **değer**atayın ve bunu sertifika profiline **ekleyin** . Ek öznitelikler ' i seçerek birden çok değer ekleyebilirsiniz.

        Kullanılabilir öznitelikler şunlardır:

        - **E-posta adresi**
        - **Kullanıcı asıl adı (UPN)**
        - **DNS**

        *Cihaz* sertifika türüyle değer için aşağıdaki cihaz sertifika değişkenlerini kullanabilirsiniz:

        - **{{AAD_Device_ID}}** veya **{{azureaddeviceıd}}** -her iki değişken de BIR cihazı Azure AD kimliğine göre belirlemek için kullanılabilir.
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{Imekarmsayı}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEı}}**
        - **{{Aygıtadı}}**
        - **{{Fullyıqualifieddomainname}}**
        - **{{MEıD}}**

        Bir özniteliğe ilişkin bir değer belirtmek için, değişken adını küme ayraçları ile, sonra da bu değişken için olan metinle birlikte ekleyin. Örneğin, DNS özniteliği için bir değer **{{Azureaddeviceıd}}. domain. com** ' u *. domain.com* ise metindir. *Kullanıcı1* adlı bir Kullanıcı Için e-posta adresi {{Fullyıqualifieddomainname}} olarak görünebilirUser1@Contoso.com.

        > [!IMPORTANT]
        > - Bir cihaz sertifikası değişkeni kullanırken, değişken adını kaşlı ayraçlar {} içine alın.
        > - Değişkeni izleyen metinde süslü ayraçları **{}** , kanal sembolleri **|** ve noktalı virgül **;** kullanmayın.
        > - **IMEI**, **SerialNumber**ve **fullyıqualifieddomainname**gibi bir cihaz sertifikasının *Konu* veya *San* 'ı üzerinde kullanılan cihaz özellikleri, cihaza erişimi olan bir kişi tarafından sızılmış özelliklerdir.
        > - Bir cihazın, bu cihaza yüklemek için bir sertifika profilinde belirtilen tüm değişkenleri desteklemesi gerekir.  Örneğin, **{{IMEI}}** bir SCEP profilinin San 'ı içinde kullanılıyorsa ve IMEI numarası olmayan bir cihaza atanırsa, profil yüklenemez.

   - **Sertifika geçerlilik süresi**:

     Sertifika şablonundaki geçerlilik süresinden düşük bir değer girebilirsiniz ancak daha yüksek bir değer giremezsiniz. Sertifika şablonunu [Intune konsolu içinden ayarlanılabilecek özel bir değeri destekleyecek](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template)şekilde yapılandırdıysanız, sertifikanın süresi dolmadan önce kalan süreyi belirtmek için bu ayarı kullanın.

     Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa beş yıl değerini giremezsiniz ancak bir yıl değerini girebilirsiniz. Değerin, yayımlayan sertifika yetkilisinin sertifikası için kalan geçerlilik süresinden de düşük olması gerekir.

   - **Anahtar depolama sağlayıcısı (KSP)** :

     *(İçin geçerlidir: Windows 8.1 ve üzeri, ve Windows 10 ve üzeri)*

     Sertifika anahtarının depolanacağı yeri belirtin. Aşağıdaki değerlerden birini seçin:

     - **Varsa Güvenilir Platform Modülü (TPM) KSP'sine, aksi halde Yazılım KSP'sine kaydol**
     - **Güvenilir Platform Modülü (TPM) KSP'sine kaydol, aksi halde hata ver**
     - **Passport'a kaydet, aksi halde hata ver (Windows 10 ve üzeri)**
     - **Software KSP’ye kaydol**

   - **Anahtar kullanımı**:

     Sertifika için anahtar kullanım seçeneklerini belirleyin:

     - **Dijital imza**: Yalnızca anahtarın korunmasına bir dijital imza yardımcı olduğunda anahtar değişimine izin verir.
     - **Anahtar şifreleme**: Yalnızca anahtar şifreli olduğunda anahtar değişimine izin verir.

   - **Anahtar boyutu (bit)** :

     Anahtarda bulunan bitlerin sayısını seçin.

   - **Karma algoritması**:

     *(Android, Android Enterprise, Windows Phone 8,1, Windows 8.1 ve üzeri ve Windows 10 ve üzeri için geçerlidir)*

     Bu sertifika ile kullanmak için kullanılabilir karma algoritma türlerinden birini seçin. Bağlanan cihazların destekleyeceği en güçlü güvenlik düzeyini seçin.

   - **Kök sertifika**:

     Daha önce yapılandırdığınız ve bu SCEP sertifika profili için geçerli kullanıcılara ve cihazlara atadığınız *Güvenilen sertifika profilini* seçin. Güvenilen sertifika profili, kullanıcılara ve cihazlara güvenilen kök CA sertifikası sağlamak için kullanılır. Güvenilen sertifika profili hakkında daha fazla bilgi için bkz. *Intune 'da kimlik doğrulaması için sertifikaları kullanma*' da [Güvenilen kök CA sertifikanızı dışarı aktarma](certificates-configure.md#export-the-trusted-root-ca-certificate) ve [Güvenilen sertifika profilleri oluşturma](certificates-configure.md#create-trusted-certificate-profiles) . Kök sertifika yetkiliniz ve veren bir sertifika yetkiliniz varsa, sertifika verme yetkilisi ile ilişkili güvenilen kök sertifika profilini seçin.

   - **Genişletilmiş anahtar kullanımı**:

     Sertifikanın amaçlanan amacı için değer ekleyin. Çoğu durumda, Kullanıcı veya cihazın bir sunucuda kimliğini doğrulayabilmesi için sertifika *istemci kimlik doğrulaması* gerektirir. Gerektiğinde ek anahtar kullanımları ekleyebilirsiniz.

   - **Yenileme eşiği (%)** :

     Cihazın sertifikayı yenilemeyi istemesi için kalan sertifika ömrünün yüzdesini girin. Örneğin, 20 girerseniz, sertifikanın %80 ' ı dolduğunda sertifikanın yenilenmesi denenir. Yenileme başarılı olana kadar yenileme denemeleri devam eder. Yenileme, yeni bir ortak/özel anahtar çifti ile sonuçlanan yeni bir sertifika oluşturur.

   - **SCEP sunucu URL 'leri**:

     SCEP aracılığıyla sertifika veren NDES sunucuları için bir veya daha fazla URL girin. Örneğin, *https://ndes.contoso.com/certsrv/mscep/mscep.dll* gibi bir ad girin. URL 'Ler, profille cihaza rastgele gönderildiğinden, yük dengeleme için gereken ek SCEP URL 'Leri ekleyebilirsiniz. SCEP sunucularından biri kullanılamıyorsa, SCEP isteği başarısız olur ve daha sonraki cihaz iadelerinde, sertifika isteği aşağı doğru aynı sunucuya göre yapılabilir.

8. **Tamam**' ı ve ardından **Oluştur**' u seçin. Profil oluşturulur ve *cihaz yapılandırması-profiller* listesinde görüntülenir.

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>Kaçışlı özel karakterlerle sertifika imzalama isteklerinden kaçının

Bir kaçan karakter olarak aşağıdaki özel karakterlerden birini veya daha fazlasını içeren bir konu adı (CN) içeren SCEP ve PKCS sertifika istekleri için bilinen bir sorun vardır. Kaçış karakteri olarak özel karakterlerden birini içeren konu adları, yanlış konu adına sahip bir CSR 'de sonuçlanır. Yanlış konu adı, Intune SCEP sınama doğrulaması başarısız olur ve sertifika verilmemiş olur.

Özel karakterler şunlardır:
- \+
- ,
- ;
- =

Konu adınız özel karakterlerden birini içerdiğinde, bu sınırlamaya geçici bir çözüm bulmak için aşağıdaki seçeneklerden birini kullanın:

- Tırnak işaretleriyle özel karakteri içeren CN değerini kapsülle.  
- CN değerinden özel karakteri kaldırın.

**Örneğin**, *test kullanıcısı (TESTCOMPANY, LLC)* olarak görünen bir konu adı vardır.  *Testcompany* ve *LLC* arasında virgül bulunan BIR CN içeren bir CSR bir sorun gösterir.  Bu sorun, tüm CN 'nin çevresine tırnak işareti koyarak veya tam olarak *Testcompany* ile *LLC*arasında virgül kaldırılarak önlenebilir:

- **Tırnak Işaretleri ekleme**: *CN =* "test kullanıcısı (testcompany, LLC)", OU = useraccounts, DC = Corp, DC = contoso, DC = com *
- **Virgülü kaldırın**: *CN = test kullanıcısı (testcompany LLC), OU = useraccounts, DC = Corp, DC = contoso, DC = com*

 Ancak, bir ters eğik çizgi karakterini kullanarak virgül kaçış girişimleri, CRP günlüklerinde hata vererek başarısız olur:
 
- **Atlanan virgül**: *CN = test kullanıcısı (TESTCOMPANY\\, LLC), OU = USERACCOUNTS, DC = Corp, DC = contoso, DC = com*

Hata aşağıdaki hatayla benzerdir:

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```

## <a name="assign-the-certificate-profile"></a>Sertifika profilini atama

SCEP sertifika profillerini, diğer amaçlar için [Cihaz profillerini dağıttığınız](../configuration/device-profile-assign.md) şekilde atayın. Ancak, devam etmeden önce aşağıdakileri göz önünde bulundurun:

- Gruplara SCEP sertifika profilleri atadığınızda, güvenilen kök CA sertifika dosyası ( *Güvenilen sertifika profilinde*belirtildiği gibi) cihaza yüklenir. Cihaz, bu güvenilen kök CA sertifikasına yönelik bir sertifika isteği oluşturmak için SCEP sertifika profilini kullanır.

- SCEP sertifika profili yalnızca, sertifika profilini oluştururken belirttiğiniz platformu çalıştıran cihazlara yüklenir.

- Sertifika profillerini kullanıcı koleksiyonlarına veya cihaz koleksiyonlarına atayabilirsiniz.

- Cihaz kaydolduktan sonra cihaza hızlıca bir sertifika yayımlamak için sertifika profilini bir cihaz grubu yerine bir kullanıcı grubuna atayın. Bir cihaz grubuna atarsanız, ilkeleri almadan önce cihazın tam olarak kaydedilmesi gerekir.

- Intune ve Configuration Manager için ortak yönetim kullanıyorsanız, Configuration Manager ' de kaynak erişim Ilkeleri için [iş yükü kaydırıcısını](https://docs.microsoft.com/configmgr/comanage/how-to-switch-workloads) **Intune** veya **pilot Intune**'a ayarlayın. Bu ayar, Windows 10 istemcilerinin sertifika isteme işlemini başlatmasını sağlar.

- Güvenilen sertifika profilini ve SCEP sertifika profilini ayrı ayrı oluşturup atarsanız, her ikisi de atanmalıdır. Bir cihaza her ikisi de yüklü olmadan, SCEP sertifika ilkesi başarısız olur. Tüm güvenilen kök sertifika profillerinin Ayrıca SCEP profiliyle aynı gruplara dağıtıldığından emin olun. Örneğin, bir kullanıcı grubuna SCEP sertifikası profili dağıtıyorsanız, güvenilen kök (ve ara) sertifika profili de aynı kullanıcı grubuna dağıtılmalıdır.

> [!NOTE]
> İOS cihazlarında, bir SCEP sertifika profili veya PKCS sertifika profili, Wi-Fi veya VPN profili gibi ek bir profille ilişkilendirildiğinde, cihaz bu ek profillerin her biri için bir sertifika alır. Bu, iOS cihazının SCEP veya PKCS sertifika isteği tarafından sunulan birden çok sertifikaya sahip olmasına neden olur. 


## <a name="next-steps"></a>Sonraki adımlar

[Profiller atama](../configuration/device-profile-assign.md)

[SCEP Sertifika profillerinin dağıtımı sorunlarını giderme](../protect/troubleshoot-scep-certificate-profiles.md)
