---
title: Microsoft Intune - Azure ile Windows Holographic cihazları yönetme | Microsoft Docs
description: Microsoft Intune kullanarak Windows Holographic for Business çalıştıran cihazlarda Şirket Portalı’nı yapılandırmak, bir uyumluluk ilkesi oluşturmak, OMA-URI ayarlarını özelleştirmek, uygulama dağıtmak, gruplarda cihazları kategorilere ayırmak, profil oluşturmak, cihazları kısıtlamak, yazılım güncelleştirmelerini etkinleştirmek, hüküm ve koşullar ayarlamak, VPN ve Wi-Fi ayarları yapılandırmak ve İş İçin Hello kullanmak gibi farklı görevler gerçekleştirebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41c1ea3bf12b83a0f09c8535275ffb58e5f46931
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="customize-devices-running-windows-holographic-with-intune"></a>Intune ile Windows Holographic çalıştıran cihazları özelleştirme

Microsoft Intune, Windows Holographic for Business çalıştıran cihazları destekler, örneğin [Microsoft HoloLens](https://docs.microsoft.com/en-us/hololens/).

Windows Holographic çalıştıran cihazları Microsoft Intune ile yönetmek için bir Sürüm Yükseltme profili oluşturmanız gerekir. Bu yükseltme profili, cihazları Windows Holographic’ten Windows Holographic for Business’a yükseltir. Microsoft HoloLens için ise yükseltme için gereken lisansı almak üzere Commercial Suite satın alabilirsiniz. Daha fazla bilgi için bkz. [Windows Holographic çalıştıran cihazları Windows Holographic for Business’a yükseltme](holographic-upgrade.md).

Windows Holographic for Business çalıştıran cihazları yönetmenize ve özelleştirmenize yardımcı olması için bu makaledeki görevleri kullanabilirsiniz. Örneğin yazılım güncelleştirmelerini yönetebilir, VPN ayarlarını yapılandırabilir ve daha pek çok işlem yapabilirsiniz.

## <a name="company-portal"></a>Şirket Portalı
**[Şirket Portalı uygulamasını yapılandırma](company-portal-app.md)**

Kullanıcıların şirket verilerine eriştiği, cihaz kaydettiği, uygulama yüklediği, BT departmanınızla iletişime geçtiği ve benzeri pek çok işlemi yaptığı Şirket Portalı, Intune’a dahildir. Windows Holographic for Business çalıştıran cihazlarınız için Şirket Portalı uygulamasını özelleştirebilirsiniz.

## <a name="compliance-policy"></a>Uyumluluk ilkesi
**[Cihaz uyumluluğu ilkesi oluşturma](compliance-policy-create-windows.md)**

Uyumluluk ilkeleri, cihazların uyumlu olmak için karşılaması gereken kurallar ve ayarlardır. Uyumlu olmayan cihazların erişimini engellemek için bu ilkeleri koşullu erişimle birlikte kullanabilirsiniz. Intune’da Windows Holographic for Business çalıştıran cihazlar için erişime izin vermek veya erişimi engellemek üzere uyumluluk ilkeleri oluşturabilirsiniz. Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.

Ayrıca bkz. **[Uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)**.

## <a name="deploy-apps"></a>Uygulama dağıtma
**[Intune’a uygulama ekleme](apps-add.md)**

Intune kullanarak Windows Holographic for Business çalıştıran cihazlarınıza uygulama ekleyebilirsiniz. Uygulama dağıtmanın pek çok yolu vardır, örneğin:

- [Microsoft Store uygulamaları ekleme](store-apps-windows.md)
- [Oluşturduğunuz uygulamaları ekleme](lob-apps-windows.md)
- [Gruplara uygulama ekleme](apps-deploy.md)

## <a name="device-categories-and-groups"></a>Cihaz kategorileri ve gruplar
**[Cihazları gruplar halinde kategorilere ayırma](device-group-mapping.md)**

Intune ile cihaz kategorileri oluşturarak cihazları Satış, Muhasebe, İnsan Kaynakları vb. gibi kategorilere göre gruplara otomatik olarak ekleyebilirsiniz. Burada amaç, Windows Holographic for Business çalıştıran cihazlarınızı yönetmeyi kolaylaştırmaktır.

## <a name="device-configuration-profiles"></a>Cihaz yapılandırma profilleri 
**[Yapılandırma profillerini kullanmaya başlayın](device-profiles.md) ve [kendi profilinizi oluşturun](device-profile-create.md)**

Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler, profiller kullanılarak yönetilir. Örneğin Windows Holographic for Business çalıştıran cihazlarınızda Cortana’yı etkinleştiren veya Windows Defender Smart Screen kullanan bir profil oluşturabilirsiniz.

Profillerinizde bazı ayarları özelleştirmek, cihaz kısıtlamaları oluşturmak ve sanal özel ağ (VPN) ve Wi-Fi yapılandırmak için OMA-URI kullanabilirsiniz.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Özel cihaz ayarları](custom-settings-windows-holographic.md)

OMA-URI (Açık Mobil Birlik Tekdüzen Kaynak Tanımlayıcısı) ayarlarını yapılandırmak için Intune’da özel bir profil oluşturabilirsiniz. Windows Holographic for Business cihazlarınızda VPN’i etkinleştirmek veya Microsoft Update’te güncelleştirmeleri denetlemek gibi farklı özellikleri kontrol etmek için OMA-URI ayarlarını kullanın.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Cihaz kısıtlamaları](device-restrictions-windows-holographic.md)

Cihaz kısıtlamaları; cihazlarınızda bir parola gerektirme, [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)’dan uygulama indirme, Bluetooth’u etkinleştirme gibi pek çok farklı ayar ve özelliği denetlemenize olanak tanır. Bu kısıtlamalar bir Intune profilinde oluşturulur. Bu profil, Windows Holographic for Business çalıştıran birden fazla cihaza uygulanabilir.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[VPN’i yapılandırma](vpn-settings-configure.md)

Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Intune’da Windows Holographic for Business çalıştıran cihazlarınız için belirli ayarları barındıran bir VPN profili oluşturabilirsiniz. Örneğin tüm Windows Holographic for Business cihazların bağlantı türü olarak Citrix VPN kullanması için bir VPN profili oluşturabilirsiniz.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Wi-Fi yapılandırma](wi-fi-settings-configure.md)

Windows Holographic for Business cihazlarınıza kablosuz ağ ayarları atamak için bir Wi-Fi profili de oluşturabilirsiniz. Bir Wi-Fi profili atadığınızda son kullanıcılarınız, hiçbir ağ yapılandırmasına gerek kalmadan kuruluş ağ erişimi kazanır. Örneğin yalnızca Windows Holographic for Business cihazlarınıza adanmış bir Wi-Fi ağı oluşturabilirsiniz.

## <a name="software-updates"></a>Yazılım güncelleştirmeleri
**[Yazılım güncelleştirmelerini yönetme](windows-update-for-business-configure.md)**

Intune’da Windows 10 cihazlar için güncelleştirme halkaları adı verilen bir özellik vardır. Bu güncelleştirme halkaları, güncelleştirmelerin nasıl yüklendiğini belirleyen bir grup ayar barındırır. Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz. Güncelleştirme halkası, Windows Holographic for Business çalıştıran birden fazla cihaza uygulanabilir.

## <a name="terms-and-conditions"></a>hüküm ve koşullar
**[Kullanıcı erişimi için şirketinizin hüküm ve koşullarını ayarlama](terms-and-conditions-create.md)**

Kullanıcıların cihazlarını kaydedip e-posta gibi şirket uygulamalarına erişmesi için önce şirket hüküm ve koşullarını kabul etmelerini gerekli kılabilirsiniz. Intune’da hüküm ve koşulların Şirket Portalı’nda nasıl gösterildiğini belirleyebilir ve bu hüküm ve koşulları Windows Holographic for Business çalıştıran cihazlara atayabilirsiniz.

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello
**[İş İçin Windows Hello’yu kullanma](windows-hello.md)**

İş İçin Hello bir parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek için bir Azure Active Directory hesabı kullanan alternatif bir oturum açma yöntemidir. İş İçin Hello ile Windows Holographic for Business cihazlarınız, ayarladığınız en düşük uzunlukta bir PIN ile oturum açabilir.
