---
title: Microsoft Intune ile Windows Holographic cihazları kullanma - Azure | Microsoft Docs
description: Microsoft Intune kullanarak Windows Holographic for Business ve HoloLens çalıştıran cihazlarda Şirket Portalı’nı yapılandırmak, bir uyumluluk ilkesi oluşturmak, OMA-URI ayarlarını özelleştirmek, uygulama dağıtmak, gruplarda cihazları kategorilere ayırmak, profil oluşturmak, cihazları kısıtlamak, yazılım güncelleştirmelerini etkinleştirmek, hüküm ve koşullar ayarlamak, VPN ve Wi-Fi ayarları yapılandırmak ve İş İçin Hello kullanmak gibi farklı görevler gerçekleştirebilir ve yönetebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.openlocfilehash: 721d3a26e25c14a2e4ccd20b179ae7d4611d3186
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203391"
---
# <a name="manage-and-use-different-device-management-features-on-windows-holographic-and-hololens-devices-with-intune"></a>Yönetme ve farklı bir cihaz yönetim özellikleri, Windows Holographic ve HoloLens cihazları Intune ile kullanma

Microsoft Intune, [Microsoft HoloLens](https://docs.microsoft.com/hololens/) gibi Windows Holographic for Business çalıştıran cihazları yönetmenize yardımcı olan birçok özelliğe sahiptir. Intune ile cihazlarınızın kuruluş kurallarına uygun olduğunu onaylayabilir ve VPN veya WiFi profili ekleyerek cihazları özelleştirebilirsiniz. Bir diğer önemli özellik de cihazı Bilgi noktası olarak kullanmak ve belirli bir uygulamayı veya belirli bir uygulama dizisini çalıştırmaktır.

Bu makaledeki görevler yazılım güncelleştirmeleri ve Windows Hello for Business kullanımı dahil olmak üzere Windows Holographic for Business çalıştıran cihazlarınızı yönetme, özelleştirme ve güvenliğini sağlama konusunda yardımcı olacaktır.

Windows Holographic cihazlarını Intune ile birlikte kullanmak için bir Sürüm Yükseltme profili oluşturun. Bu yükseltme profili, cihazları Windows Holographic’ten Windows Holographic for Business’a yükseltir. Microsoft HoloLens için ise yükseltme için gereken lisansı almak üzere Commercial Suite satın alabilirsiniz. Daha fazla bilgi için bkz. [Windows Holographic çalıştıran cihazları Windows Holographic for Business’a yükseltme](holographic-upgrade.md).

## <a name="azure-active-directory"></a>Azure Active Directory

Azure Active Directory (AD), Windows Holographic for Business çalıştıran cihazlarınızı yönetmeye ve denetlemeye yardımcı olmak için mükemmel bir kaynaktır. Intune ve Azure AD kullanarak şunları yapabilirsiniz: 

- **[Cihazları Azure Active Directory'ye katılmasını](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)**: Azure Active Directory (AD), Windows Holographic for Business çalıştıran cihazlar dahil olmak üzere iş ait Windows 10 cihazlarınızı ekleyebilirsiniz. Bu özellik, Azure AD’nin cihazı denetlemesini sağlar. Kullanıcıların şirket kaynaklarına güvenlik ve uyumluluk standartlarına uygun cihazlardan eriştiğini doğrulamaya yardımcı olur.

  [Azure AD'de cihaz Yönetimi](https://docs.microsoft.com/azure/active-directory/devices/overview) daha fazla ayrıntı sağlar.

- **[Windows cihazlar için toplu kayıt](windows-bulk-enroll.md)**: Çok sayıda yeni Windows cihazını Azure Active Directory (AD) ve Intune'a katılmasını sağlayabilirsiniz. Bu özellik, toplu kayıt olarak adlandırılır ve sağlama paketleri kullanır. Bu paketler, Windows Holographic for Business çalıştıran cihazları Azure AD kiracınıza dahil eder ve Intune’a kaydeder.

## <a name="company-portal"></a>Şirket Portalı
**[Şirket Portalı uygulamasını yapılandırma](company-portal-app.md)**

Intune; kullanıcıların şirket verilerine erişmesi, cihaz kaydetmesi, uygulama yüklemesi, BT departmanıyla iletişime geçmesi ve benzeri pek çok işlemi yapması için kullanıcılara Şirket Portalı uygulamasını sağlar. Windows Holographic for Business çalıştıran cihazlarınız için Şirket Portalı uygulamasını özelleştirebilirsiniz.

Şirket Portalı uygulamasını kullanarak aşağıdaki eylemleri de çalıştırabilirsiniz:

- Ayarlar uygulamasını veya Şirket Portalı uygulamasını kullanarak [bir cihazı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-windows)
- [Bir cihazı yeniden adlandırma](/intune-user-help/rename-your-device-cpapp)
- Bir cihaza [uygulama yükleme](/intune-user-help/install-apps-cpapp-windows)
- Ayarlar uygulamasını veya Şirket Portalı uygulamasını kullanarak [cihazları el ile eşitleme](/intune-user-help/sync-your-device-manually-windows)

## <a name="compliance-policy"></a>Uyumluluk ilkesi
**[Cihaz uyumluluğu ilkesi oluşturma](compliance-policy-create-windows.md)**

Uyumluluk ilkeleri, cihazların uyumlu olmak için karşılaması gereken kurallar ve ayarlardır. Uyumlu olmayan cihazların erişimini engellemek için bu ilkeleri koşullu erişimle birlikte kullanın. Intune’da Windows Holographic for Business çalıştıran cihazlar için erişime izin vermek veya erişimi engellemek üzere uyumluluk ilkeleri oluşturun. Örneğin BitLocker’ın etkin olmasını gerektiren bir ilke oluşturabilirsiniz.

Ayrıca bkz. **[Uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)**.

## <a name="deploy-and-manage-apps"></a>Uygulamaları dağıtma ve yönetme
**[Intune’a uygulama ekleme](apps-add.md)**

Intune kullanarak Windows Holographic for Business çalıştıran cihazlarınıza uygulama ekleyebilirsiniz. Uygulama dağıtmanın pek çok yolu vardır, örneğin:

- [Microsoft Store uygulamaları ekleme](store-apps-windows.md)
- [Oluşturduğunuz uygulamaları ekleme](lob-apps-windows.md)
- [Gruplara uygulama ekleme](apps-deploy.md)

Microsoft Intune, Windows Holographic for Business çalıştıran Microsoft HoloLens cihazlara Evrensel Windows Uygulamaları dağıtabilir. Uygulama paketlerinizi doğrudan Intune Azure portalından karşıya yükleyebilir veya İş İçin Microsoft Store’dan dağıtabilirsiniz. İlgili alanlar hakkında daha fazla bilgi için aşağıdaki makalelere bakın:
- Intune Azure portalını kullanarak İş Kolu (LOB) uygulamalarını dağıtmak için bkz. [Windows iş kolu uygulamalarını Microsoft Intune’a ekleme](lob-apps-windows.md).

    > [!NOTE]
    > Intune, en fazla 8 GB’lık paket boyutuna izin verir. Bu paket boyutu, yalnızca Intune’a yüklenen LOB uygulamaları için geçerlidir.

- İş İçin Microsoft Store kullanarak uygulama dağıtmak için bkz. [Microsoft Intune ile İş İçin Microsoft Mağazası’ndan satın aldığınız uygulamaları yönetme](windows-store-for-business.md). 
- Microsoft Intune ile uygulama yönetimi hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune’da uygulama yönetimi nedir?](app-management.md).
- Microsoft HoloLens için uygulama geliştirmek hakkında daha fazla bilgi edinmek için bkz. [Microsoft HoloLens için karma gerçeklik uygulamaları](https://www.microsoft.com/hololens/apps). 

> [!NOTE]
> Windows 10 Holographic for Business 1607 çalıştıran HoloLens cihazlar, İş İçin Microsoft Store’dan çevrimiçi lisanslandırılmış uygulamaları desteklemez. Daha fazla bilgi için bkz. [HoloLens’te uygulama yükleme](https://docs.microsoft.com/hololens/hololens-install-apps).

## <a name="device-actions"></a>Cihaz eylemleri
Intune’da BT yöneticilerinin gerek cihazda yerel olarak gerekse Azure portalında Intune yoluyla uzaktan farklı görevler yapmasına imkan veren bazı yerleşik eylemler vardır. Kullanıcılar Intune'a kayıtlı kişiye ait cihazlara Intune Şirket Portalı’ndan uzaktan komut da verebilir.

Windows Holographic for Business çalıştıran cihazlar kullanırken şu eylemler kullanılabilir: 

- **[Temizleme](devices-wipe.md#wipe)**: **Silme** eylemi, cihazı Intune'dan kaldırır ve cihazı fabrika varsayılan ayarlarına geri yükler. Bu eylemi cihazı yeni bir kullanıcıya vermeden önce veya cihazın kaybolma/çalınma durumu söz konusu olduğunda kullanın.

- **[Devre dışı bırakma](devices-wipe.md#retire)**: **Devre dışı bırakma** eylemi, cihazı Intune'dan kaldırır. Ayrıca Intune tarafından atanmış yönetilen uygulama verilerini, ayarları ve e-posta profillerini de kaldırır. Kullanıcının kişisel verileri cihazda kalır.

- **[En son ilkeleri ve eylemleri almak için cihazları eşitleme](device-sync.md)**: **Eşitleme** eylemi, cihazı Intune ile hemen iade zorlar. Bir cihaz iade ettiğinde, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır. Bu özellik, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan doğrulamanıza ve ilkelerin sorunlarını gidermenize yardımcı olur.

**[Microsoft Intune cihaz yönetimi nedir?](device-management.md)** makalesi, Azure portalını kullanarak cihaz yönetmeyi öğrenmek iyi bir kaynaktır. 

## <a name="device-categories-and-groups"></a>Cihaz kategorileri ve gruplar
**[Cihazları gruplar halinde kategorilere ayırma](device-group-mapping.md)**

Intune ile cihaz kategorileri oluşturarak cihazları Satış, Muhasebe, İnsan Kaynakları vb. gibi kategorilere göre gruplara otomatik olarak ekleyebilirsiniz. Burada amaç, Windows Holographic for Business çalıştıran cihazlarınızı yönetmeyi kolaylaştırmaktır.

## <a name="device-configuration-profiles"></a>Cihaz yapılandırma profilleri 
**[Yapılandırma profillerini kullanmaya başlayın](device-profiles.md) ve [kendi profilinizi oluşturun](device-profile-create.md)**

Intune, kuruluşunuzdaki farklı cihazlarda etkinleştirebileceğiniz veya devre dışı bırakabileceğiniz ayarları ve özellikleri içerir. Bu ayarlar ve özellikler, profiller kullanılarak yönetilir. Örneğin Windows Holographic for Business çalıştıran cihazlarınızda Cortana’yı etkinleştiren veya Windows Defender Smart Screen kullanan bir profil oluşturabilirsiniz.

Profillerinizde bazı ayarları özelleştirmek, cihaz kısıtlamaları oluşturmak ve sanal özel ağ (VPN) ve Wi-Fi yapılandırmak için OMA-URI kullanabilirsiniz.

#### <a name="custom-device-settingscustom-settings-windows-holographicmd"></a>[Özel cihaz ayarları](custom-settings-windows-holographic.md)

OMA-URI (Açık Mobil Birlik Tekdüzen Kaynak Tanımlayıcısı) ayarlarını yapılandırmak için Intune’da özel bir profil oluşturabilirsiniz. Windows Holographic for Business cihazlarınızda VPN’i etkinleştirmek veya Microsoft Update’te güncelleştirmeleri denetlemek gibi farklı özellikleri kontrol etmek için OMA-URI ayarlarını kullanın.

#### <a name="configure-kiosk-modekiosk-settingsmdwindows-holographic-for-business"></a>[Bilgi noktası modunu yapılandırma](kiosk-settings.md#windows-holographic-for-business)

Intune’un paylaşılan veya misafir bilgisayar özelliklerini kullanarak Windows Holographic for Business cihazları bilgi noktası olarak çalışacak şekilde yapılandırabilirsiniz. Bu cihazlar, tek uygulama (tekli uygulama bilgi noktası modu) veya birden fazla uygulama (çoklu uygulama bilgi noktası modu) çalıştırabilir.

#### <a name="device-restrictionsdevice-restrictions-windows-holographicmd"></a>[Cihaz kısıtlamaları](device-restrictions-windows-holographic.md)

Cihaz kısıtlamaları; cihazlarınızda bir parola gerektirme, [Microsoft Store](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)’dan uygulama indirme, Bluetooth’u etkinleştirme gibi pek çok farklı ayar ve özelliği denetlemenize olanak tanır. Bu kısıtlamalar bir Intune profilinde oluşturulur. Bu profil, Windows Holographic for Business çalıştıran birden fazla cihaza uygulanabilir.

#### <a name="configure-vpnvpn-settings-configuremd"></a>[VPN’i yapılandırma](vpn-settings-configure.md)

Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Intune’da Windows Holographic for Business çalıştıran cihazlarınız için belirli ayarları barındıran bir VPN profili oluşturabilirsiniz. Örneğin tüm Windows Holographic for Business cihazların bağlantı türü olarak Citrix VPN kullanması için bir VPN profili oluşturabilirsiniz.

#### <a name="configure-wi-fiwi-fi-settings-configuremd"></a>[Wi-Fi yapılandırma](wi-fi-settings-configure.md)

Windows Holographic for Business cihazlarınıza kablosuz ağ ayarları atamak için bir Wi-Fi profili de oluşturabilirsiniz. Bir Wi-Fi profili atadığınızda son kullanıcılarınız, hiçbir ağ yapılandırmasına gerek kalmadan kuruluş ağ erişimi kazanır. Örneğin yalnızca Windows Holographic for Business cihazlarınıza adanmış bir Wi-Fi ağı oluşturabilirsiniz.

## <a name="shared-multi-user-devices"></a>Paylaşılan birden çok kullanıcı cihazları
[Paylaşılan cihazlar](shared-user-device-settings-windows-holographic.md)

, Microsoft HoloLens gibi Windows Holographic for Business çalıştıran cihazlar birden çok kullanıcı olması. Intune yönetim hesabı yerel depolama ile güç yönetimi gibi paylaşılan bu cihazlarda farklı özellikleri denetlemek için ayarlar içerir. Yapılandırma profilleri, farklı işletim sistemi kullanan cihazları için de uygulanabilir. Örneğin, cihazlar grubu aynı grupta RS2 ve RS3 çalıştıran cihazlara sahip olabilir.

## <a name="software-updates"></a>Yazılım güncelleştirmeleri
**[Yazılım güncelleştirmelerini yönetme](windows-update-for-business-configure.md)**

Intune’da Windows 10 cihazlar için güncelleştirme halkaları adı verilen bir özellik vardır. Bu güncelleştirme halkaları, güncelleştirmelerin nasıl yüklendiğini belirleyen bir grup ayar barındırır. Örneğin güncelleştirmeleri yüklemek için bir bakım penceresi oluşturabilir veya güncelleştirmeler yüklendikten sonra yeniden başlatmayı seçebilirsiniz. Güncelleştirme halkası, Windows Holographic for Business çalıştıran birden fazla cihaza uygulanabilir.

## <a name="terms-and-conditions"></a>hüküm ve koşullar
**[Kullanıcı erişimi için şirketinizin hüküm ve koşullarını ayarlama](terms-and-conditions-create.md)**

Kullanıcıların cihazlarını kaydedip e-posta gibi şirket uygulamalarına erişmesi için önce şirket hüküm ve koşullarını kabul etmelerini gerekli kılın. Intune’da hüküm ve koşulların Şirket Portalı’nda nasıl gösterildiğini belirleyin ve bu hüküm ve koşulları Windows Holographic for Business çalıştıran cihazlara atayın.

## <a name="windows-hello-for-business"></a>İş İçin Windows Hello
**[İş İçin Windows Hello’yu kullanma](windows-hello.md)**

İş İçin Hello bir parolayı, akıllı kartı ya da sanal akıllı kartı değiştirmek için bir Azure Active Directory hesabı kullanan alternatif bir oturum açma yöntemidir. İş İçin Hello ile Windows Holographic for Business cihazlarınız, ayarladığınız en düşük uzunlukta bir PIN ile oturum açabilir.
