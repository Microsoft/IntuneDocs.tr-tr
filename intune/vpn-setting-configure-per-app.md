---
title: Microsoft Intune - Azure’da iOS cihazlar için uygulama başına VPN ayarlama | Microsoft Docs
description: iOS cihazlarda Microsoft Intune’da ön koşullara bakın, sanal özel ağ (VPN) kullanıcıları için bir grup oluşturun, SCEP sertifika profili ekleyin, uygulama başına VPN profili yapılandırın ve VPN profiline bazı uygulamalar atayın. Ayrıca cihazda VPN bağlantısını doğrulama adımları da listelenir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7609b3a190cacc7b722f408133f6c5f10d96771
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233143"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-ios-devices-in-intune"></a>Yedekleme uygulama başına sanal özel ağ (VPN) ıntune'da iOS cihazları için ayarlayın

Microsoft Intune oluşturun ve sanal özel bir uygulamaya atanan ağlar (VPN) kullanın. Bu özellik, "uygulama başına VPN" olarak adlandırılır. Intune tarafından yönetilen cihazlardaki VPN kullanabileceğiniz yönetilen uygulamaları seçin. Uygulama başına VPN kullanırken, son kullanıcılar otomatik olarak VPN üzerinden bağlanır ve belgeler gibi kuruluş kaynaklarına erişin.

Bu özellik şu platformlarda geçerlidir:

- iOS 9 ve üzeri

VPN uygulama başına VPN destekleyip desteklemediğini görmek için VPN sağlayıcıya ait belgelere bakın.

Bu makalede, uygulama başına VPN profili oluşturma ve uygulamalarınıza bu profili atarsınız işlemini göstermektedir. Son kullanıcılarınız için sorunsuz uygulama başına VPN deneyimi oluşturmak için aşağıdaki adımları kullanın. Uygulama başına VPN desteği çoğu VPN'lerle, kullanıcı bir uygulamayı açan ve VPN için otomatik olarak bağlanır.

Bazı VPN, uygulama başına VPN ile kullanıcı adı ve parola kimlik doğrulamasına izin verin. Diğer bir deyişle kullanıcı adı ve VPN'ye bağlanmak için parola girmeniz gerekir.

## <a name="per-app-vpn-with-zscaler"></a>Zscaler ile uygulama başına VPN

Zscaler özel erişim (ZPA) kimlik doğrulaması için Azure Active Directory (Azure AD) ile tümleşir. ZPA kullanırken, ihtiyacınız olmayan [güvenilen sertifika](#create-a-trusted-certificate-profile) veya [SCEP veya PKCS sertifika](#create-a-scep-or-pkcs-certificate-profile) profilleri (Bu makalede açıklanmıştır). Uygulama başına VPN profili kümesi varsa Zscaler, ilgili uygulamalardan birini açmak için yukarı ZPA için otomatik olarak bağlan değil. Bunun yerine, kullanıcının Zscaler uygulamada oturum açmanız gerekir. Ardından, ilişkili uygulamalar için uzaktan erişim sınırlıdır.

## <a name="prerequisites-for-per-app-vpn"></a>Uygulama başına VPN önkoşulları

> [!IMPORTANT]
> VPN satıcınız, belirli donanım ya da lisans gibi uygulama başına VPN için diğer gereksinimleri olabilir. Satıcının belgelerini gözden geçirmeyi unutmayın ve Intune'da uygulama başına VPN'yi ayarlamadan önce önkoşulları yerine getirin.

VPN sunucusu, kimliğini doğrulamak amacıyla cihaz bir istem yapmadan kabul edilmesi gereken sertifikayı sunar. Sertifika otomatik olarak onaylanacağından onaylamak için sertifika yetkilisi (CA) tarafından verilen VPN sunucusu kök sertifikasını içeren bir güvenilen sertifika profili oluşturun. 

#### <a name="export-the-certificate-and-add-the-ca"></a>Sertifikayı dışarı aktarın ve CA'yı ekleyin

1. VPN sunucunuzda yönetim konsolunu açın.
2. VPN sunucunuzun sertifika tabanlı kimlik doğrulaması kullandığını onaylayın. 
3. Güvenilir kök sertifika dosyasını dışarı aktarın. .cer uzantısına sahip bu dosyayı, güvenilir sertifika profili oluştururken eklersiniz.
4. VPN sunucusunda kimlik doğrulaması için sertifikayı veren CA’nın adını ekleyin.

    Ardından cihazın sunduğu CA VPN sunucusundaki güvenilir CA listesindeki bir CA eşleşirse, VPN sunucusu cihazın başarıyla kimliğini doğrular.

## <a name="create-a-group-for-your-vpn-users"></a>VPN kullanıcılarınız için grup oluşturma

Oluşturun veya mevcut bir grubu Azure Active Directory'de (Azure AD) kullanıcı veya uygulama başına VPN kullanan cihazlar için seçin. Yeni bir grup oluşturmak için bkz: [kullanıcıları ve cihazları düzenlemek için gruplar ekleyin](groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

CA tarafından verilen VPN sunucusu kök sertifikasını Intune’da oluşturulan bir profile aktarın. Güvenilen sertifika profili, iOS cihaza VPN sunucusu tarafından sunulan CA’ya otomatik olarak güvenmesi talimatını verir.

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:
    - **Ad**
    - **Açıklama**
    - **Platform**: Seçin **iOS**.
    - **Profil türü**: Seçin **güvenilen sertifika**.
4. Klasör simgesini seçin ve, VPN yönetim konsolundan aktardığınız VPN sertifikanıza (.cer dosyası) göz atın. 
5. Seçin **Tamam** > **oluşturma**.

    ![Microsoft Intune iOS cihazları için bir güvenilen sertifika profili oluşturma](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>Bir SCEP veya PKCS sertifika profili oluşturma

Güvenilen kök sertifika profili cihaza otomatik olarak VPN sunucusuna güvenmesini sağlar. SCEP veya PKCS sertifika, iOS VPN istemcisinden VPN sunucusuna kimlik bilgilerini sağlar. Sertifika bir kullanıcı adı ve parola istemeden sessizce kimlik izin verir. 

Yapılandırma ve istemci kimlik doğrulama sertifikası atamak için aşağıdaki makalelerden birine bakın:

- [Intune ile SCEP sertifikalarını yapılandırma ve yönetme](certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](certficates-pfx-configure.md)

İstemci kimlik doğrulama sertifikası yapılandırdığınızdan emin olun. Bu doğrudan SCEP sertifika profillerini ayarlayabilirsiniz (**genişletilmiş anahtar kullanımı** listesi > **istemci kimlik doğrulaması**). PKCS için istemci kimlik doğrulaması sertifika şablonunda sertifika yetkilisi (CA) olarak ayarlayın.

![Konu adı biçimi, anahtar kullanımı, genişletilmiş anahtar kullanımı ve daha fazlası dahil olmak üzere Microsoft Intune bir SCEP sertifika profili oluşturma](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Uygulama başına VPN profili oluşturma

VPN profili SCEP veya PKCS sertifika istemci kimlik bilgileri, VPN bağlantı bilgilerini içerir ve uygulama başına VPN özelliğini etkinleştirmek için uygulama başına VPN bayrağını iOS uygulaması tarafından kullanır.

1. İçinde **Intune**seçin **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**. 
2. Aşağıdaki özellikleri girin: 
    - **Ad**
    - **Açıklama**
    - **Platform**: Seçin **iOS**.
    - **Profil türü**: Seçin **VPN**.
3. İçinde **bağlantı türü**, VPN istemci uygulamanızı seçin.
4. **Temel VPN**’i seçin. [iOS VPN ayarları](vpn-settings-ios.md) listeler ve tüm ayarlarını açıklar. Uygulama başına VPN kullanırken, listelenen aşağıdaki özellikleri ayarlayın emin olun: 
    
    - **Kimlik doğrulama yöntemi**: Seçin **sertifikaları**. 
    - **Kimlik doğrulama sertifikası**: Mevcut bir SCEP veya PKCS sertifika seçin > **Tamam**.      
    - **Bölünmüş tünel**: Seçin **devre dışı** tüm trafiği VPN bağlantısı etkin olduğunda VPN tünelini kullanmasını zorunlu kılmak için. 

      ![Uygulama başına VPN profili, bir bağlantı, IP adresi veya FQDN, kimlik doğrulama yöntemi, girin ve Microsoft Intune tunning Böl](./media/vpn-per-app-create-vpn-profile.png)

    Diğer ayarlar hakkında daha fazla bilgi için bkz: [iOS VPN ayarları](vpn-settings-ios.md).

5. Seçin **otomatik VPN** > **otomatik VPN türü** > **uygulama başına VPN**

    ![Intune'da uygulama başına VPN için otomatik VPN, iOS cihazlarında ayarlayın.](./media/vpn-per-app-automatic.png)

6. Seçin **Tamam** > **Tamam** > **oluşturma**.

## <a name="associate-an-app-with-the-vpn-profile"></a>Bir uygulamayı VPN profiliyle ilişkilendirme

VPN profilinizi ekledikten sonra, uygulamayı ve Azure AD grubunu bu profil ile ilişkilendirin.

1. **Intune**’da **İstemci uygulamaları** > **Uygulamalar**’ı seçin.
2. Listeden bir uygulama seçin > **atamaları** > **Grup Ekle**.
3. İçinde **atama türü**seçin **gerekli** veya **kayıtlı cihazlar için kullanılabilir**.
4. Seçin **eklenen gruplar** > **dahil edilecek grupları seçin** > grubu seçin [oluşturduğunuz](#create-a-group-for-your-vpn-users) (Bu makaledeki) > **seçin**.
5. İçinde **VPN'ler**, uygulama başına VPN profili seçin [oluşturduğunuz](#create-a-per-app-vpn-profile) (Bu makaledeki).

    ![Bir uygulamayı Microsoft Intune uygulama başına VPN profili atama](./media/vpn-per-app-app-to-vpn.png)

6. Seçin **Tamam** > **Kaydet**.

Aşağıdaki koşulların tümü mevcut olduğunda sonraki cihaz iade sırasında bir profil ile bir uygulama arasındaki ilişkiyi kaldırılır:

- Uygulama gerekli yükleme amacı kullanılarak hedeflendi.
- Hem profil hem de uygulama aynı grubu hedeflendi.
- Uygulama başına VPN yapılandırmasını uygulama atamasından kaldırıyorsunuz.

Bir profil ile bir uygulama arasındaki ilişkiyi, aşağıdaki koşulların tümü mevcut olduğunda kullanıcı şirket Portalı'ndan bir yeniden yükleme istekleri kadar devam eder:

- Uygulama sağlanan yükleme amacı kullanılarak hedeflendi.
- Hem profil hem de uygulama aynı grubu hedeflendi.
- Son kullanıcı uygulama ve cihaza yüklenen profil sonuçlanır şirket Portalı'ndan uygulama yükleme istedi.
- Uygulama başına VPN yapılandırmasını uygulama atamasından kaldırır veya değiştirirsiniz.

## <a name="verify-the-connection-on-the-ios-device"></a>iOS cihazda bağlantıyı doğrulama

Uygulama başına VPN’niz ayarlı ve uygulamanızla ilişkili olduğunda, bağlantının çalıştığını bir cihazda doğrulayın.

### <a name="before-you-attempt-to-connect"></a>Bağlanmayı denemeden önce

 - Yukarıda belirtilen tüm ilkeler için aynı grup dağıttığınızdan emin olun. Aksi takdirde, uygulama başına VPN deneyimi işe yaramaz.
 - Pulse Secure VPN veya özel VPN istemci uygulaması kullanıyorsanız, uygulama katmanı veya paket Katman Tünel kullanmayı da tercih edebilirsiniz. **ProviderType** değerini uygulama katmanı tüneli için **app-proxy** olarak veya paket katmanı tüneli için **packet-tunnel** ayarlayın. Doğru değeri kullandığınızdan emin olmak için VPN sağlayıcıya ait belgelere bakın.

### <a name="connect-using-the-per-app-vpn"></a>Uygulama başına VPN kullanarak bağlanma

VPN’i seçmek veya kimlik bilgilerinizi girmek zorunda kalmadan bağlanarak sıfır dokunma deneyimini dpğrulayın. Sıfır dokunma deneyimi ile:

 - Cihaz VPN sunucusuna güvenmesini ister değil. Diğer bir deyişle, kullanıcının görmez **dinamik güven** iletişim kutusu.
 - Kullanıcı kimlik bilgilerini türüne sahip değil.
 - İlişkili uygulamalar biri kullanıcı oturum açtığında kullanıcı cihazının VPN'ye bağlı.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Sonraki adımlar

- iOS ayarlarını gözden geçirmek için bkz. [Microsoft Intune’da iOS cihazlar için VPN ayarları](vpn-settings-ios.md).
- VPN ayarı ve Intune hakkında daha fazla bilgi için bkz. [Intune VPN ayarlarını yapılandırma](vpn-settings-configure.md).
