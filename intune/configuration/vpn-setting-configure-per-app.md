---
title: Microsoft Intune-Azure 'da iOS/ıpados cihazları için uygulama başına VPN ayarlama | Microsoft Docs
description: Önkoşullara bakın, sanal özel ağ (VPN) kullanıcıları için bir grup oluşturun, bir SCEP sertifikası profili ekleyin, bir uygulama başına VPN profili yapılandırın ve iOS/ıpados cihazlarında Microsoft Intune VPN profiline bazı uygulamalar atayın. Ayrıca cihazda VPN bağlantısını doğrulama adımları da listelenir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd53172a1086f48dc1646e1b8a63de8bec37b934
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512611"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-iosipados-devices-in-intune"></a>Intune 'da iOS/ıpados cihazları için uygulama başına sanal özel ağ (VPN) ayarlama

Microsoft Intune, bir uygulamaya atanan sanal özel ağları (VPN 'Ler) oluşturabilir ve kullanabilirsiniz. Bu özellik "uygulama başına VPN" olarak adlandırılır. Intune tarafından yönetilen cihazlarda VPN 'nizi kullanlebilecek yönetilen uygulamaları seçersiniz. Uygulama başına VPN 'Ler kullanırken, son kullanıcılar VPN üzerinden otomatik olarak bağlanır ve belgeler gibi kuruluş kaynaklarına erişim sağlar.

Bu özellik şu platformlarda geçerlidir:

- iOS 9 ve üzeri
- ıpados 13,0 ve üzeri

VPN 'nizin uygulama başına VPN 'i destekleyip desteklemediğini görmek için VPN sağlayıcınızın belgelerini denetleyin.

Bu makalede, uygulama başına VPN profili oluşturma ve bu profili uygulamalarınıza atama işlemlerinin nasıl yapılacağı gösterilir. Son kullanıcılarınız için sorunsuz bir uygulama başına VPN deneyimi oluşturmak için bu adımları kullanın. Uygulama başına VPN 'yi destekleyen çoğu VPN için, Kullanıcı bir uygulama açar ve VPN 'ye otomatik olarak bağlanır.

Bazı VPN 'Ler uygulama başına VPN ile Kullanıcı adı ve parola doğrulamasına izin verir. Yani, kullanıcıların VPN 'ye bağlanmak için bir Kullanıcı adı ve parola girmesi gerekir.

> [!IMPORTANT]
> İOS/ıpados için IKEv2 VPN profilleri için uygulama başına VPN desteklenmez.

## <a name="per-app-vpn-with-zscaler"></a>Zscaler ile uygulama başına VPN

Zscaler özel erişimi (ZPA) kimlik doğrulaması için Azure Active Directory (Azure AD) ile tümleşir. ZPA kullanırken, [güvenilir sertifika](#create-a-trusted-certificate-profile) veya [SCEP veya PKCS sertifika](#create-a-scep-or-pkcs-certificate-profile) profillerine (Bu makalede açıklanmıştır) gerek kalmaz. Zscaler için ayarlanmış bir uygulama başına VPN profiliniz varsa, ilişkili uygulamalardan birini açmak otomatik olarak ZPA 'ya bağlanamaz. Bunun yerine, kullanıcının önce Zscaler uygulamasında oturum açması gerekir. Daha sonra, uzaktan erişim ilişkili uygulamalarla sınırlıdır.

## <a name="prerequisites-for-per-app-vpn"></a>Uygulama başına VPN önkoşulları

> [!IMPORTANT]
> VPN satıcınız, belirli donanım veya lisanslama gibi uygulama başına VPN için başka gereksinimlere sahip olabilir. Satıcının belgelerini gözden geçirmeyi unutmayın ve Intune'da uygulama başına VPN'yi ayarlamadan önce önkoşulları yerine getirin.

VPN sunucusu, kimliğini doğrulamak amacıyla cihaz bir istem yapmadan kabul edilmesi gereken sertifikayı sunar. Sertifikanın otomatik onayını onaylamak için, sertifika yetkilisi (CA) tarafından verilen VPN sunucusu kök sertifikasını içeren bir güvenilen sertifika profili oluşturun. 

### <a name="export-the-certificate-and-add-the-ca"></a>Sertifikayı dışarı aktarın ve CA 'yı ekleyin

1. VPN sunucunuzda, yönetim konsolunu açın.
2. VPN sunucunuzun sertifika tabanlı kimlik doğrulaması kullandığını doğrulayın. 
3. Güvenilir kök sertifika dosyasını dışarı aktarın. .cer uzantısına sahip bu dosyayı, güvenilir sertifika profili oluştururken eklersiniz.
4. VPN sunucusunda kimlik doğrulaması için sertifikayı veren CA’nın adını ekleyin.

    Cihaz tarafından sunulan CA, VPN sunucusundaki güvenilen CA listesinde bulunan bir CA ile eşleşiyorsa, VPN sunucusu aygıtın kimliğini başarıyla doğrular.

## <a name="create-a-group-for-your-vpn-users"></a>VPN kullanıcılarınız için grup oluşturma

Uygulama başına VPN kullanan kullanıcı veya cihazlar için Azure Active Directory (Azure AD) içinde mevcut bir grup oluşturun veya seçin. Yeni bir grup oluşturmak için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](../fundamentals/groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

CA tarafından verilen VPN sunucusu kök sertifikasını Intune’da oluşturulan bir profile aktarın. Güvenilen sertifika profili, iOS/ıpados cihazının VPN sunucusunun sunduğu CA 'ya otomatik olarak güvenmesini sağlar.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki özellikleri girin:
    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı, **tüm şirket Için iOS/ıpados güvenilen SERTIFIKA VPN profilidir**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **IOS/ıpados**' ı seçin.
    - **Profil türü**: **Güvenilen sertifika**' yı seçin.
4. Klasör simgesini seçin ve VPN yönetim konsolundan verdiğiniz VPN sertifikanıza (. cer dosyası) gidin. 
5. **Oluştur** > **Tamam ' ı** seçin.

    ![Microsoft Intune 'de iOS/ıpados cihazları için bir güvenilen sertifika profili oluşturma](./media/vpn-setting-configure-per-app/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>SCEP veya PKCS sertifika profili oluşturma

Güvenilen kök sertifika profili, cihazın VPN sunucusuna otomatik olarak güvenmesini sağlar. SCEP veya PKCS sertifikası, iOS/ıpados VPN istemcisinden VPN sunucusuna kimlik bilgileri sağlar. Sertifika, cihazın Kullanıcı adı ve parola istemeden sessizce kimlik doğrulaması yapmasına izin verir. 

İstemci kimlik doğrulama sertifikasını yapılandırmak ve atamak için aşağıdaki makalelerden birine bakın:

- [Altyapıyı Intune ile SCEP destekleyecek şekilde yapılandırma](../protect/certificates-scep-configure.md)
- [Intune ile PKCS sertifikalarını yapılandırma ve yönetme](../protect/certficates-pfx-configure.md)

Sertifikayı istemci kimlik doğrulaması için yapılandırmayı unutmayın. Bu ayarı doğrudan SCEP sertifika profillerinde (**genişletilmiş anahtar kullanımı** listesi > **istemci kimlik doğrulaması**) ayarlayabilirsiniz. PKCS için, sertifika yetkilisinde (CA) sertifika şablonunda istemci kimlik doğrulamasını ayarlayın.

![Konu adı biçimi, anahtar kullanımı, genişletilmiş anahtar kullanımı ve daha fazlası dahil Microsoft Intune bir SCEP sertifikası profili oluşturun](./media/vpn-setting-configure-per-app/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Uygulama başına VPN profili oluşturma

VPN profili, uygulama başına VPN özelliğinin iOS/ıpados uygulaması tarafından kullanımını etkinleştirmek için istemci kimlik bilgileri, VPN ile bağlantı bilgileri ve uygulama başına VPN bayrağını içeren SCEP veya PKCS sertifikasını içerir.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **cihaz** > **yapılandırma profilleri** > **Profil oluştur**' u seçin.
2. Aşağıdaki özellikleri girin:
    - **Ad**: özel profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı, **tüm şirket Için iOS/ıpados BAŞıNA VPN profilidir**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **IOS/ıpados**' ı seçin.
    - **Profil türü**: **VPN**' yi seçin.
3. **Bağlantı türü**' nde VPN istemci uygulamanızı seçin.
4. **Temel VPN**’i seçin. [iOS/ıpados VPN ayarları](vpn-settings-ios.md) , tüm ayarları listeler ve tanımlar. Uygulama başına VPN kullanırken, aşağıdaki özellikleri listelenmiş şekilde ayarladığınızdan emin olun:

    - **Kimlik doğrulama yöntemi**: **Sertifikalar**' ı seçin. 
    - **Kimlik doğrulama sertifikası**: **Tamam**> mevcut bir SCEP veya PKCS sertifikası seçin.
    - **Bölünmüş tünel**: VPN bağlantısı etkin olduğunda tüm trafiğin VPN tüneli kullanmasını zorlamak Için **devre dışı bırak** ' ı seçin. 

      ![Uygulama başına VPN profilinde, Microsoft Intune bir bağlantı, IP adresi veya FQDN, kimlik doğrulama yöntemi ve bölünmüş tünel girin](./media/vpn-setting-configure-per-app/vpn-per-app-create-vpn-profile.png)

    Diğer ayarlar hakkında daha fazla bilgi için bkz. [iOS/ıpados VPN ayarları](vpn-settings-ios.md).

5. Otomatik **vpn > ** **uygulama başına VPN** > **türünü** seçin

    ![Intune 'da iOS/ıpados cihazlarında uygulama başına VPN 'ye otomatik VPN ayarla](./media/vpn-setting-configure-per-app/vpn-per-app-automatic.png)

6.  > **Tamam** ' **ı seçin** > **Oluştur**' a tıklayın.

## <a name="associate-an-app-with-the-vpn-profile"></a>Bir uygulamayı VPN profiliyle ilişkilendirme

VPN profilinizi ekledikten sonra, uygulamayı ve Azure AD grubunu bu profil ile ilişkilendirin.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431), **uygulamalar** > **tüm uygulamalar**' ı seçin.
2. Listeden bir uygulama seçin > **atamaları** > **Grup Ekle**' ye tıklayın.
3. **Atama türü**' nde, **gerekli** veya **Kayıtlı cihazlar için kullanılabilir**' ı seçin.
4. **Dahil edilen grupları** seçin > **dahil edilecek grupları** seçin > [oluşturduğunuz](#create-a-group-for-your-vpn-users) grubu seçin (Bu makalede) > **seçin**.
5. **VPN**'lerde, [oluşturduğunuz](#create-a-per-app-vpn-profile) uygulama başına VPN profilini seçin (Bu makalede).

    ![Microsoft Intune içindeki uygulama başına VPN profiline bir uygulama atama](./media/vpn-setting-configure-per-app/vpn-per-app-app-to-vpn.png)

6. **Kaydet** > **Tamam ' ı** seçin.

Aşağıdaki koşulların tümü mevcut olduğunda, bir uygulama ile bir profil arasındaki ilişki sonraki cihaz iade işlemi sırasında kaldırılır:

- Uygulama gerekli yükleme amacı kullanılarak hedeflendi.
- Hem profil hem de uygulama aynı grubu hedeflendi.
- Uygulama başına VPN yapılandırmasını uygulama atamasından kaldırıyorsunuz.

Aşağıdaki koşulların tümü mevcut olduğunda, bir uygulama ve bir profil arasındaki ilişki, Kullanıcı Şirket Portalı 'den bir yeniden yükleme istemesi kadar devam ettirir:

- Uygulama sağlanan yükleme amacı kullanılarak hedeflendi.
- Hem profil hem de uygulama aynı grubu hedeflendi.
- Son Kullanıcı, uygulama ve profilin cihaza yüklenme sonucu olan Şirket Portalı 'den uygulama yüklemeyi istedi.
- Uygulama başına VPN yapılandırmasını uygulama atamasından kaldırır veya değiştirirsiniz.

## <a name="verify-the-connection-on-the-iosipados-device"></a>İOS/ıpados cihazında bağlantıyı doğrulama

Uygulama başına VPN’niz ayarlı ve uygulamanızla ilişkili olduğunda, bağlantının çalıştığını bir cihazda doğrulayın.

### <a name="before-you-attempt-to-connect"></a>Bağlanmayı denemeden önce

- Yukarıda bahsedilen tüm ilkeleri aynı gruba dağıttığınızdan emin olun. Aksi takdirde, uygulama başına VPN deneyimi çalışmaz.
- Pulse Secure VPN uygulaması veya özel bir VPN istemci uygulaması kullanıyorsanız, uygulama katmanını veya paket katmanı tünelini kullanmayı seçebilirsiniz. **ProviderType** değerini uygulama katmanı tüneli için **app-proxy** olarak veya paket katmanı tüneli için **packet-tunnel** ayarlayın. Doğru değeri kullandığınızdan emin olmak için VPN sağlayıcınızın belgelerini denetleyin.

### <a name="connect-using-the-per-app-vpn"></a>Uygulama başına VPN kullanarak bağlanma

VPN’i seçmek veya kimlik bilgilerinizi girmek zorunda kalmadan bağlanarak sıfır dokunma deneyimini dpğrulayın. Sıfır dokunma deneyimi ile:

- Cihaz, VPN sunucusuna güvenip güvenmesini istemez. Diğer bir deyişle, Kullanıcı **dinamik güven** iletişim kutusunu görmez.
- Kullanıcının kimlik bilgilerini yazmak zorunda değildir.
- Kullanıcı, ilişkili uygulamalardan birini açtığında kullanıcının cihazı VPN 'e bağlanır.

## <a name="next-steps"></a>Sonraki adımlar

- İOS/ıpados ayarlarını gözden geçirmek için, bkz. [Microsoft Intune iOS/ıpados cihazları Için VPN ayarları](vpn-settings-ios.md).
- VPN ayarı ve Intune hakkında daha fazla bilgi için bkz. [MICROSOFT INTUNE VPN ayarlarını yapılandırma](vpn-settings-configure.md).
