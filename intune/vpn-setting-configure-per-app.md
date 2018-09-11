---
title: Microsoft Intune - Azure’da iOS cihazlar için uygulama başına VPN ayarlama | Microsoft Docs
description: iOS cihazlarda Microsoft Intune’da ön koşullara bakın, sanal özel ağ (VPN) kullanıcıları için bir grup oluşturun, SCEP sertifika profili ekleyin, uygulama başına VPN profili yapılandırın ve VPN profiline bazı uygulamalar atayın. Ayrıca cihazda VPN bağlantısını doğrulama adımları da listelenir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7cf005b225dd11ca6b95dbed0a82330544575f92
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347483"
---
# <a name="set-up-per-app-virtual-private-network-vpn-in-intune-for-ios-devices"></a>iOS cihazlar için Intune’da uygulama başına Sanal Özel Ağ (VPN) ayarlama

Intune ile yönetilen iOS cihazlarda hangi yönetilen uygulamaların Sanal Özel Ağınızı (VPN) kullanabileceğini belirtebilirsiniz. Intune’da bir uygulama başına VPN oluşturduğunuzda, şirket belgelerine erişirken son kullanıcılar otomatik olarak VPN’iniz yoluyla bağlanır.

Uygulama başına VPN şu anda şu sağlayıcılar için kullanılabilir durumda:

 - Check Point Remote Access VPN
 - Cisco AnyConnect
 - Citrix
 - F5
 - Pulse Connect Secure
 - SonicWall
 - Palo Alto Networks GlobalProtect
 - Zscaler

## <a name="prerequisites-for-per-app-vpn"></a>Uygulama başına VPN önkoşulları

> [!IMPORTANT]
> VPN satıcınızın uygulama başına VPN için belirli bir donanım veya lisanslama gibi başka bazı gereksinimleri olabilir. Satıcının belgelerini gözden geçirmeyi unutmayın ve Intune'da uygulama başına VPN'yi ayarlamadan önce önkoşulları yerine getirin.

VPN sunucusu, kimliğini doğrulamak amacıyla cihaz bir istem yapmadan kabul edilmesi gereken sertifikayı sunar. Sertifikanın otomatik olarak onaylanacağından emin olmak için, Sertifika Yetkilisi (CA) tarafından verilen VPN sunucusu kök sertifikasını barındıran bir güvenilir sertifika profili oluşturun. 

Sertifikayı dışarı aktarın ve CA’yı ekleyin.

1. VPN sunucunuzda yönetim konsolunu açın.
2. VPN sunucunuzun Sertifika Tabanlı Kimlik Doğrulaması kullandığını doğrulayın. 
3. Güvenilir kök sertifika dosyasını dışarı aktarın. .cer uzantısına sahip bu dosyayı, güvenilir sertifika profili oluştururken eklersiniz.
4. VPN sunucusunda kimlik doğrulaması için sertifikayı veren CA’nın adını ekleyin.
    Cihazın sunduğu CA, VPN sunucusundaki Güvenilir CA listesindeki bir CA ile eşleşirse, VPN sunucusu cihazın kimliğini başarıyla doğrular.

## <a name="create-a-group-for-your-vpn-users"></a>VPN kullanıcılarınız için grup oluşturma

Uygulama Başına VPN’e erişimi olan üyeleri barındırması için Azure Active Directory’de (Azure AD) bir grup oluşturun veya mevcut bir grubu seçin.

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Gruplar**’ı seçin ve daha sonra **Yeni grup**’a tıklayın.
3. Grubun **Grup türü**’nü seçin. 
3. Grubun **Grup adı**’nı yazın. 
4. Grubun **Grup açıklaması**’nı yazın. 
5. **Üyelik türü** için **Atandı**’yı seçin.
7. **Üyeler** bölmesinde VPN kullanıcılarını adları veya e-posta adresleriyle arayın.
8. Her bir kullanıcıyı seçin ve **Seç**’e tıklayın.
9. **Oluştur**'a tıklayın.

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

CA tarafından verilen VPN sunucusu kök sertifikasını Intune’da oluşturulan bir profile aktarın. Güvenilen sertifika profili, iOS cihaza VPN sunucusu tarafından sunulan CA’ya otomatik olarak güvenmesi talimatını verir.

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması**’nı seçin ve daha sonra **Profiller**’e tıklayın.
3. **Profil oluştur**’a tıklayın. **Profil oluştur**’da:
    1. **Ad** yazın.
    2. **Açıklama** yazın.
    3. **Platform** için **iOS**’u seçin.
    4. **Profil türü** için **Güvenilen sertifika**’yı seçin.
4. Klasör simgesine tıklayarak VPN yönetim konsolundan aktardığınız VPN sertifikanıza (.cer dosyası) göz atın. **Tamam**'ı tıklatın.
5. **Oluştur**'a tıklayın.

    ![Güvenilen bir sertifika profili oluşturma](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Bir SCEP sertifika profili oluşturma

Güvenilen kök sertifika profili, iOS’un VPN sunucusuna otomatik olarak güvenmesini mümkün kılar. SCEP sertifikası ise iOS VPN istemcisinden VPN sunucusuna kimlik bilgileri sağlar. Sertifika, iOS cihaz kullanıcısına kullanıcı adı ve parola için istemde bulunmaya gerek kalmaksızın cihazın sessizce kimlik doğrulamasına imkan verir. 

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması**’nı seçin ve daha sonra **Profiller**’e tıklayın.
3. **Profil oluştur**’a tıklayın. **Profil oluştur**’da:
    1. **Ad** yazın.
    2. **Açıklama** yazın.
    3. **Platform** için **iOS**’u seçin.
    4. **Profil türü** için **SCEP sertifikası**’nı seçin.
4. **Yıllar**’ı seçin ve **Sertifika geçerlilik süresi** için `2` yazın.
5. **Konu adı biçimi** için **Ortak ad**’ı seçin.
6. **Konu alternatif adı** için **Kullanıcı asıl adı (UPN)** seçin.
7. **Anahtar kullanımı** için **Dijital imza** ve **Anahtar şifreleme**’yi seçin.
8. **Anahtar boyutu (bit cinsinden)** için **2048**’i seçin.
9. Kök Sertifika’ya tıklayın ve bir SCEP sertifikası seçin. **Tamam**'ı tıklatın.
10. **Genişletilmiş anahtar kullanımı**’nın **Ad**’ına `Client Authentication` yazın.
11. **Nesne tanımlayıcısı**’na `1.3.6.1.5.5.7.3.2` yazın.
12. **Ekle**'yi tıklatın.
13. ***Sunucu URL’sini*** yazın ve **Ekle**’ye tıklayın.
14. **Tamam**'ı tıklatın.
15. **Oluştur**'a tıklayın.

    ![Bir SCEP sertifika profili oluşturma](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Uygulama başına VPN profili oluşturma

VPN profili; istemci kimlik bilgilerini taşıyan SCEP sertifikasını, VPN’ye bağlantı bilgilerini ve uygulama başına VPN özelliğini iOS uygulaması tarafından kullanılmak üzere etkinleştirecek olan uygulama başına VPN bayrağını barındırır.

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması**’nı seçin ve daha sonra **Profiller**’e tıklayın.
3. **Profil oluştur**’a tıklayın. **Profil oluştur**’da:
    1. **Ad** yazın.
    2. **Açıklama** yazın.
    3. **Platform** için **iOS**’u seçin.
    4. **Profil türü** için **VPN**’i seçin.
4. **Temel VPN**’i seçin. **Temel VPN**’de:
    1. **Bağlantı adı**’nı yazın.
    2. **IP adresi veya FQDN**’yi yazın.
    3. **Kimlik doğrulama** yöntemi için **Sertifikalar**’ı seçin.
    4. **Kimlik doğrulama sertifikası** altında SCEP sertifikasını seçin ve **Tamam**’a tıklayın.
    5. **Bağlantı türü** için VPN’inizi seçin.
    6. Gerekirse VPN’inizin özniteliklerini yapılandırın.
    7. **Bölünmüş Tüneli Devre Dışı Bırak**’ı seçin.
5. **Otomatik VPN**’e tıklayın. **Otomatik VPN**’de:
    1. **Otomatik VPN türü** için **Uygulama Başına VPN**’i seçin.
    2. VPN URL’sini yazın ve **Ekle**’ye tıklayın.
    3. **Tamam**'ı tıklatın.
6. **Tamam**'ı tıklatın.
7. **Oluştur**'a tıklayın.

    ![Uygulama başına VPN profili oluşturma](./media/vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Bir uygulamayı VPN profiliyle ilişkilendirme

VPN profilinizi ekledikten sonra, uygulamayı ve Azure AD grubunu bu profil ile ilişkilendirin.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **İstemci uygulamaları**’nı seçin.
4. **Uygulamalar**’a tıklayın.
5. Uygulama listesinden uygulamayı seçin.
6. **Atamalar**’a tıklayın.
7. **Grup ekle**’ye tıklayın.
8. **Grup ekle** bölmesindeki **Atama türü** için **Gerekli**’yi seçin.
9. Daha önce tanımladığınız grubu seçip **Bu uygulamayı gerekli kıl**’ı seçin.
10. **VPN** için VPN tanımınızı seçin.
 
    > [!NOTE]  
    > Bazen VPN tanımının değeri alması bir dakikayı bulabilir. 3-5 dakika bekledikten sonra **Kaydet**’e tıklayın.

11. **Tamam**’a ve **Kaydet**’e tıklayın.

    ![Bir uygulamayı VPN ile ilişkilendirme](./media/vpn-per-app-app-to-vpn.png)

Aşağıdaki koşullar var olduğunda, cihazın bir sonraki iade edilişinde uygulama ile profil arasındaki ilişkilendirme kaldırılacak:
- Uygulama gerekli yükleme amacı kullanılarak hedeflendi.
- Hem profil hem de uygulama aynı grubu hedeflendi.
- Uygulama başına VPN yapılandırmasını uygulama atamasından kaldırıyorsunuz.

Aşağıdaki koşullar var olduğunda, son kullanıcı şirket portalından yeniden yükleme isteğinde bulunana kadar uygulamayla profil arasındaki ilişkilendirme kalır:
- Uygulama sağlanan yükleme amacı kullanılarak hedeflendi.
- Hem profil hem de uygulama aynı grubu hedeflendi.
- Son kullanıcı şirket portalından uygulama yüklemesi istedi ve bunun sonucunda uygulama ve profil cihaza yüklenir.
- Uygulama başına VPN yapılandırmasını uygulama atamasından kaldırıyorsunuz.

## <a name="verify-the-connection-on-the-ios-device"></a>iOS cihazda bağlantıyı doğrulama

Uygulama başına VPN’niz ayarlı ve uygulamanızla ilişkili olduğunda, bağlantının çalıştığını bir cihazda doğrulayın.

### <a name="before-you-attempt-to-connect"></a>Bağlanmayı denemeden önce

 - iOS 9 veya üzerini çalıştırdığınızdan emin olun.
 - Yukarıda bahsedilen *tüm* ilkeleri aynı grup ve kullanıcılara dağıttığınızdan emin olun. Bunu yapmamanız durumunda uygulama başına VPN deneyimi kesinlikle başarısız olacaktır.  
 - Desteklenen üçüncü taraf VPN uygulamasına sahip olduğunuzdan emin olun. Aşağıdaki VPN uygulamaları desteklenmektedir:
    - Check Point Capsule Connect
    - Cisco AnyConnect
    - Citrix VPN
    - F5 Access
    - Pulse Secure
    - SonicWall Mobile Connect
    - Zscaler Uygulaması

    > [!NOTE]
    > Pulse Secure VPN uygulamasını kullanıyorsanız uygulama katmanı veya paket katmanı tünelini kullanmayı seçebilirsiniz. **ProviderType** değerini uygulama katmanı tüneli için **app-proxy** olarak veya paket katmanı tüneli için **packet-tunnel** ayarlayın.

### <a name="connect-using-the-per-app-vpn"></a>Uygulama başına VPN kullanarak bağlanma

VPN’i seçmek veya kimlik bilgilerinizi girmek zorunda kalmadan bağlanarak sıfır dokunma deneyimini dpğrulayın. Sıfır dokunma deneyimi ile:

 - Cihaz, VPN sunucusuna güvenmenizi istemez. Yani **Dinamik Güven** iletişim kutusunu görmezsiniz.
 - Kimlik bilgileri girmeniz gerekmez.
 - Bağlan düğmesine dokunduktan sonra VPN’e bağlanırsınız.

iOS cihazda bağlantıyı doğrulayın.

1. VPN uygulamasına dokunun.
2. **Bağlan**’a dokunun.  
VPN, başka bir istem yapmadan başarıyla bağlanır.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Sonraki adımlar

- iOS ayarlarını gözden geçirmek için bkz. [Microsoft Intune’da iOS cihazlar için VPN ayarları](vpn-settings-ios.md).
-  VPN ayarı ve Intune hakkında daha fazla bilgi almak için bkz. [Microsoft Intune’da VPN ayarlarını yapılandırma](vpn-settings-configure.md).
