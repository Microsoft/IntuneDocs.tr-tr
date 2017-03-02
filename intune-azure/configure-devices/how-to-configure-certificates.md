---
title: "Intune ile sertifika yapılandırma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Wi-Fi, VPN ve diğer bağlantıların güvenliğini sağlamaya yardımcı olan sertifikaları oluşturmak ve atamak için Intune kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 364534ad788466f8b268b4091decee5326b94163
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Microsoft Intune’da sertifika yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

VPN, Wi-Fi veya e-posta profilleri aracılığıyla kullanıcılara şirket kaynaklarına erişim izni verdiğinizde, her kullanıcının cihazına yüklenen bir sertifika kullanarak erişim güvenliğini sağlayabilirsiniz. Üst düzey iş akışı şöyledir:

1. Doğru sertifika altyapısını sağladığınızdan emin olun. [SCEP sertifikalarını](configure-certificate-infrastructure-for-scep.md) ve [PKCS sertifikalarını](configure-certificate-infrastructure-for-pfx.md) kullanabilirsiniz.
2. Her cihaza bir kök sertifika veya ara Sertifika Yetkilisi (CA) sertifikası yükleyerek cihazın Sertifika Yetkilinizin meşruluğunu tanımasını sağlayın. Bunu yapmak için **güvenilen sertifika profili** oluşturun ve atayın. Bu profili atadığınızda Intune ile yönettiğiniz cihazlar kök sertifikayı ister ve alır. Her platform için ayrı bir profil oluşturmanız gerekir. Şu platformlar için güvenilen sertifika profilleri sağlanır:
    - iOS 8.0 ve üzeri
    - macOS 10.9 ve üzeri
    - Android 4.0 ve üzeri <!--Android for Work --->
    - Windows 8.1 ve üzeri
    - Windows Phone 8.1 ve üzeri
    - Windows 10 ve üzeri
3. Sertifika profilleri oluşturarak cihazların VPN, Wi-Fi ve e-posta erişimi kimlik doğrulaması için kullanılacak bir sertifika istemelerini sağlayın. Aşağıdaki platformları çalıştıran cihazlar için **PKCS** veya **SCEP** sertifika profili oluşturabilir ve dağıtabilirsiniz:
    - iOS 8.0 ve üzeri
    - Android 4.0 ve üzeri
    - Android for Work
    - Windows 10 (masaüstü ve Mobile) ve üzeri

    Aşağıdaki platformlarla yalnızca SCEP sertifika profilini kullanabilirsiniz:

-     macOS 10.9 ve üzeri
-     Windows Phone 8.1 ve üzeri

Her cihaz platformu için ayrı profil oluşturmanız gerekir. Profili oluştururken daha önce oluşturduğunuz güvenilen kök sertifika profiliyle ilişkilendirin.

### <a name="further-considerations"></a>Dikkat edilecek diğer konular

- Kuruluş Sertifika Yetkiliniz yoksa oluşturmanız gerekir.
- Cihaz platformlarınıza bağlı olarak Basitleştirilmiş Sertifika Kayıt Protokolü (SCEP) profili kullanmaya karar verirseniz ayrıca bir Ağ Cihazı Kayıt Hizmeti (NDES) sunucusunu yapılandırmanız gerekir.
- SCEP veya PKCS profilleri kullanmayı planlıyorsanız Microsoft Intune Sertifika Bağlayıcısı'nı indirip yapılandırmanız gerekir.

## <a name="before-you-start"></a>Başlamadan önce


### <a name="if-you-want-to-use-scep-certificates"></a>SCEP sertifikalarını kullanmak istiyorsanız

[SCEP için sertifika altyapısı](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep) bölümündeki gerekli önkoşulları tamamlayın.

### <a name="if-you-want-to-use-pkcs-certificates"></a>PKCS sertifikalarını kullanmak istiyorsanız

[PKCS için sertifika altyapısı](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx) bölümündeki gerekli önkoşulları tamamlayın.

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Görev 1: Güvenilen Kök CA sertifikasını dışarı aktarın
Güvenilen Kök Sertifika Yetkilileri (CA) sertifikasını, veren CA'dan veya veren CA'nıza güvenen herhangi bir cihazdan bir **.cer** dosyası olarak dışarı aktarın. Özel anahtarı dışarı aktarmayın.

Güvenilen sertifika profili ayarlarken bu sertifikayı içeri aktaracaksınız.

## <a name="task-2-create-trusted-certificate-profiles"></a>Görev 2: Güvenilen sertifika profilleri oluşturun
SCEP veya PKCS sertifika profili oluşturabilmeniz için önce bir güvenilen sertifika profili oluşturmanız gerekir. Her cihaz platformu için bir güvenilen sertifika profiline ve SCEP veya PKCS profiline ihtiyacınız vardır.

### <a name="to-create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturmak için

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, güvenilen sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu güvenilen sertifika için cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinde **Güvenilen sertifika**’yı seçin.
7. 1. görevde kaydettiğiniz sertifikaya gidin ve **Tamam**’a tıklayın.
8. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:
    - **Bilgisayar sertifika deposu - Kök**
    - **Bilgisayar sertifika deposu - Ara**
    - **Kullanıcı sertifika deposu - Ara**
8. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).


> [!Note]
> Android cihazları, bir üçüncü tarafın güvenli sertifika yüklediğini belirten bir bildirim görüntüler.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Görev 3: SCEP veya PKCS sertifika profillerini oluşturma
Güvenilen sertifika profilini oluşturduktan sonra, kullanmak istediğiniz her platform için SCEP veya PKCS sertifika profillerini oluşturun. SCEP sertifika profilini oluştururken, aynı platform için bir güvenilen sertifika profili belirtmeniz gerekir. Bu, iki sertifika profilini birbirine bağlasa da her profili ayrı atamalısınız.

### <a name="to-create-an-scep-certificate-profile"></a>Bir SCEP sertifika profili oluşturmak için

1. Azure Portal’da **Cihazları yapılandır** iş yükünü seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, SCEP sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu SCEP sertifikası için cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinde **SCEP sertifikası**’nı seçin.
7. **SCEP Sertifikası** dikey penceresinde aşağıdaki ayarları yapılandırın:
    - **Sertifika geçerlilik süresi** - Veren sertifika yetkilisinde, özel bir geçerlilik süresine izin veren **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** komutunu çalıştırdıysanız, sertifikanın süresi dolmadan önce kalan zamanı belirtebilirsiniz.<br>Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, yayımlayan sertifika yetkilisinin sertifikası için kalan geçerlilik süresinden de düşük olması gerekir. 
    - **Anahtar depolama sağlayıcısı (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - Sertifika anahtarının depolanacağı yeri belirtin. Aşağıdaki değerlerden birini seçin:
        - **Varsa Güvenilir Platform Modülü (TPM) KSP'sine, aksi halde Yazılım KSP'sine kaydol**
        - **Güvenilir Platform Modülü (TPM) KSP'sine kaydol, aksi halde hata ver**
        - **Passport'a kaydet, aksi halde hata ver (Windows 10 ve üzeri)**
        - **Software KSP’ye kaydol**
    - **Konu adı biçimi** - Listeden, sertifika isteğindeki konu adının Intune tarafından otomatik olarak nasıl oluşturulacağını seçin. Sertifika bir kullanıcı içinse, konu adına kullanıcının e-posta adresini de ekleyebilirsiniz. Aşağıdakilerden birini seçin:
        - **Yapılandırılmadı**
        - **Ortak ad**
        - **E-postayı içeren ortak ad**
        - **E-posta olarak ortak ad**
    - **Konu diğer adı** - Intune uygulamasının, sertifika isteğinde konu diğer adı (SAN) için değerleri otomatik olarak nasıl oluşturacağını belirtin. Örneğin, bir kullanıcı sertifikası türü seçtiyseniz, konu alternatif adına kullanıcı asıl adını (UPN) ekleyebilirsiniz. İstemci sertifikası, bir Ağ İlkesi Sunucusuna kimlik doğrulamak için kullanılacaksa, UPN'ye konu alternatif adını ayarlamanız gerekir. 
    - **Anahtar kullanımı** - Sertifika için anahtar kullanımı seçeneklerini belirtin. Aşağıdaki seçeneklerden birini seçebilirsiniz: 
        - **Anahtar şifreleme:** Yalnızca anahtar şifreli olduğunda anahtar değişimine izin verin. 
        - **Dijital imza:** Yalnızca anahtarın korunmasına bir dijital imza yardımcı olduğunda anahtar değişimine izin verin. 
    - **Anahtar boyutu (bit)** - Anahtarın içereceği bit sayısını seçin. 
    - **Karma algoritması** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - Bu sertifika ile kullanmak için uygun karma algoritması türlerinden birini seçin. Bağlanan cihazların destekleyeceği en güçlü güvenlik düzeyini seçin. 
    - **Kök Sertifika** - Daha önce yapılandırdığınız ve kullanıcıya veya cihaza atadığınız kök CA sertifika profilini seçin. Bu CA sertifikası, bu sertifika profilinde yapılandırdığınız sertifikayı verecek CA'nın kök sertifikası olmalıdır. 
    - **Genişletilmiş anahtar kullanımı** - Sertifikaların hedeflenen amacına yönelik değerler eklemek için **Ekle**'yi seçin. Çoğu durumda, kullanıcı veya cihazın bir sunucuya kimlik doğrulaması gerçekleştirebilmesi için, sertifika **İstemci Kimlik Doğrulaması** gerektirir. Ancak, gerektiğinde başka herhangi bir anahtar kullanımı ekleyebilirsiniz. 
    - **Kayıt Ayarları**
        - **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
        - **SCEP Sunucu URL’leri** - SCEP aracılığıyla sertifika verecek olan NDES Sunucuları için bir veya birden çok URL belirtin. 
8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

SCEP sertifika profili ayarlarını yapılandırmak için, profil yapılandırma sayfasındaki yönergeleri izleyin.
>[!Note]
> Yalnızca iOS cihazları için: Konu adı biçimi’nin altında Özel’i seçerek özel bir konu adı biçimi girin.
> Özel biçim için şu an desteklenen iki değişken **Ortak Ad (CN)** ve **E-posta (E)**’dır. Bu değişkenlerin ve statik dizelerin bir bileşimini kullanarak şunun gibi özel bir konu adı biçimi oluşturabilirsiniz: **CN={{KullanıcıAdı}},E={{EpostaAdresi}},OU=Mobil,O=Finans Grubu,L=Redmond,ST=Washington,C=ABD** Bu örnekte, CN ve E değişkenlerine ek olarak Kuruluş Birimi, Kuruluş, Konum, Eyalet ve Ülke değerleri için de dizeler kullanan bir konu adı biçimi oluşturursunuz. [Bu konu](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx), **CertStrToName** işlevini ve bu işlevin desteklenen dizelerini gösterir.


### <a name="to-create-a-pkcs-certificate-profile"></a>PKCS sertifika profili oluşturmak için

Azure Portal’da **Cihazları yapılandır** iş yükünü seçin.
2. **Cihaz yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’a tıklayın.
4. **Profil Oluştur** dikey penceresinde, PKCS sertifika profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinde, bu PKCS sertifikası için cihaz platformu olarak aşağıdakilerden birini seçin:
    - **Outlook Web Access (OWA)**
    - **iOS**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinde **PKCS sertifikası**’nı seçin.
7. **PKCS Sertifikası** dikey penceresinde aşağıdaki ayarları yapılandırın:
    - **Yenileme eşiği (%)** - Cihazın, sertifikanın yenilenmesini istemesi için kalan sertifika ömrünün yüzde kaç olması gerektiğini belirtin.
    - **Sertifika geçerlilik süresi** - Veren sertifika yetkilisinde, özel bir geçerlilik süresine izin veren **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** komutunu çalıştırdıysanız, sertifikanın süresi dolmadan önce kalan zamanı belirtebilirsiniz.<br>Belirtilen sertifika şablonundaki geçerlilik süresinden düşük bir değer belirtebilirsiniz, daha yüksek bir değer belirtemezsiniz. Örneğin, sertifika şablonunda sertifika geçerlilik süresi iki yılsa, beş yıl değerini belirtemez ancak bir yıl değerini belirtebilirsiniz. Değerin, yayımlayan sertifika yetkilisinin sertifikası için kalan geçerlilik süresinden de düşük olması gerekir.
    - **Anahtar depolama sağlayıcısı (KSP)** (Windows 10) -
    - **Sertifika yetkilisi** -
    - **Sertifika yetkilisi adı** -
    - **Sertifika şablonu adı** - Ağ Cihazı Kayıt Hizmeti'nin kullanmak üzere yapılandırıldığı ve sertifikayı veren sertifika yetkilisine eklenmiş bir sertifika şablonunun adını girin.
    Adın, Ağ Cihazı Kayıt Hizmeti'ni çalıştıran sunucunun kayıt defterinde listelenen sertifika şablonlarından biriyle tam olarak aynı olduğundan emin olun. Sertifika şablonu ekran adını değil, sertifika şablonu adını belirttiğinizden emin olun. 
    Sertifika şablonlarının adlarını bulmak için şu anahtara gidin: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. **EncryptionTemplate**, **GeneralPurposeTemplate**ve **SignatureTemplate**için değerler olarak listelenen sertifika şablonlarını göreceksiniz. Varsayılan olarak, sertifika şablonlarının üçü için de değer IPSECIntermediateOffline'dır; bu, **IPSec (Çevrimdışı istek)** şablon ekran adına eşlenir. 
    - **Konu adı biçimi** - Listeden, sertifika isteğindeki konu adının Intune tarafından otomatik olarak nasıl oluşturulacağını seçin. Sertifika bir kullanıcı içinse, konu adına kullanıcının e-posta adresini de ekleyebilirsiniz. Aşağıdakilerden birini seçin:
        - **Yapılandırılmadı**
        - **Ortak ad**
        - **E-postayı içeren ortak ad**
        - **E-posta olarak ortak ad**
    - **Konu diğer adı** - Intune uygulamasının, sertifika isteğinde konu diğer adı (SAN) için değerleri otomatik olarak nasıl oluşturacağını belirtin. Örneğin, bir kullanıcı sertifikası türü seçtiyseniz, konu alternatif adına kullanıcı asıl adını (UPN) ekleyebilirsiniz. İstemci sertifikası, bir Ağ İlkesi Sunucusuna kimlik doğrulamak için kullanılacaksa, UPN'ye konu alternatif adını ayarlamanız gerekir.
    - **Genişletilmiş anahtar kullanımı** (Android) - Sertifikaların hedeflenen amacına yönelik değerler eklemek için **Ekle**'yi seçin. Çoğu durumda, kullanıcı veya cihazın bir sunucuya kimlik doğrulaması gerçekleştirebilmesi için, sertifika **İstemci Kimlik Doğrulaması** gerektirir. Ancak, gerektiğinde başka herhangi bir anahtar kullanımı ekleyebilirsiniz. 
    - **Kök Sertifika** (Android) - Daha önce yapılandırdığınız ve kullanıcıya veya cihaza atadığınız kök CA sertifika profilini seçin. Bu CA sertifikası, bu sertifika profilinde yapılandırdığınız sertifikayı verecek CA'nın kök sertifikası olmalıdır.
8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="task-4-assign-certificate-profiles"></a>Görev 4: Sertifika profillerini atayın

Gruplara sertifika profillerini atamadan önce aşağıdaki noktaları göz önünde bulundurun:

- Sertifika profillerini gruplara atadığınızda, Güvenilen CA sertifika profilinden alınan sertifika dosyası cihaza yüklenir. Cihaz, bir sertifika isteği oluşturmak için SCEP veya PKCS sertifika profilini kullanır.
- Sertifika profilleri, yalnızca profili oluşturduğunuzda kullandığınız platformu çalıştıran cihazlara yüklenir.
- Sertifika profillerini kullanıcı koleksiyonlarına veya cihaz koleksiyonlarına dağıtabilirsiniz.
- Cihaz kaydolduktan sonra cihaza çabucak bir sertifika yayımlamak için sertifika profilini bir cihaz grubu yerine bir kullanıcı grubuna dağıtın. Bir cihaz grubuna dağıtırsanız, ilkeleri almadan önce cihazın tam olarak kaydedilmesi gerekir.
- Her profili ayrı olarak dağıtsanız da Güvenilen Kök CA’sını ve SCEP veya PKCS profilini de dağıtmanız gerekir. Aksi takdirde SCEP veya PKCS sertifika ilkesi başarısız olur.

## <a name="next-steps"></a>Sonraki adımlar
Cihaz profillerini atama hakkındaki genel bilgiler için bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).

