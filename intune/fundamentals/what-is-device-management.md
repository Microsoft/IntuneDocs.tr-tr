---
title: Microsoft 365 cihaz yönetimi
description: Microsoft 365 Kurumsal Microsoft Intune içerir. Intune 'un kuruluşunuz için mobil cihaz yönetimi ve mobil uygulama yönetimi nasıl sağladığını öğrenin. Yaygın senaryoları okuyun ve ortamınızda Microsoft 365 dağıtmak için Intune 'u kullanın.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/14/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93d8107d235d9f13af487bba4cbf6a71fc92eeab
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314540"
---
# <a name="device-management-overview"></a>Cihaz yönetimine genel bakış

Herhangi bir yöneticinin önemli bir görevi, bir kuruluşun kaynaklarını ve verilerini korumak ve güvence altına almak için kullanılır. Bu görev *cihaz yönetimi*. Kullanıcıların kişisel dosyaları açıp paylaştığı, Web sitelerini ziyaret eden ve uygulamaları ve oyunları yükleyen birçok cihazı vardır. Aynı kullanıcılar aynı zamanda çalışanlar ve öğrencilerlerdir. E-posta ve OneNote gibi iş ve okul kaynaklarına erişmek için cihazlarını kullanmak ister.

Cihaz yönetimi, kuruluşların kaynaklarını ve verilerini ve farklı cihazlardan korunmasını ve güvenliğini sağlar.

Kuruluş, bir cihaz yönetimi sağlayıcısı kullanarak yalnızca yetkili kişilerin ve cihazların mülkiyet bilgilerine erişmesini sağlayabilir. Benzer şekilde, cihaz kullanıcıları, cihazlarını kuruluşun güvenlik gereksinimlerini karşılayacak şekilde biledikleri için iş verilerine telefonlarından erişmeyi kolaylaştırabilir. Bir kuruluş olarak, **kaynaklarımızı korumak Için ne kullanmalıyım?**

Yanıt [Microsoft Intune](what-is-intune.md). Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sunar. Herhangi bir MDM veya MAM çözümünün bazı önemli görevleri şunlardır:

- Farklı bir mobil ortamı destekler ve iOS, Android, Windows ve macOS cihazlarını güvenli bir şekilde yönetin.
- Cihazların ve uygulamaların kuruluşunuzun güvenlik gereksinimleriyle uyumlu olduğundan emin olun.
- Kuruluş verilerinizi kuruluşa ait ve kişisel cihazlarda güvende tutmaya yardımcı olan ilkeler oluşturun.
- Bu ilkeleri zorlamak ve cihazları, uygulamaları, kullanıcıları ve grupları yönetmeye yardımcı olmak için tek ve birleştirilmiş bir mobil çözüm kullanın.
- İş gücünüzün erişimlerini ve verilerini nasıl paylaştığını denetlemeye yardımcı olarak şirket bilgilerinizi koruyun.

Intune, Microsoft Azure, Microsoft 365 ve Azure Active Directory (Azure AD) ile tümleşir. Azure AD kimlerin erişebileceğini ve ne erişimleri olduğunu denetlemenize yardımcı olur.

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft gibi birçok kuruluş, kullanıcıların şirkete ait ve kişisel mobil cihazlarından erişebileceği özel verileri güvenli hale getirmek için Intune 'u kullanır. Intune, veri erişimini güvenli hale getirmenize ve izlemenize yardımcı olmak için cihaz ve uygulama yapılandırma ilkeleri, yazılım güncelleştirme ilkeleri ve yükleme durumları (grafikler, tablolar ve raporlar) içerir.

Kişilerin farklı platformlar kullanan birden çok cihazı olması yaygındır. Örneğin, bir çalışan Surface Pro 'Yu ve kişisel yaşamına bir Android mobil cihazı kullanabilir. Ayrıca, bir kişinin Microsoft Outlook ve SharePoint gibi kuruluş kaynaklarına bu birden fazla cihazdan erişmesi yaygındır.

Intune ile, her kişi için birden çok cihazı ve iOS, macOS, Android ve Windows dahil olmak üzere her cihazda çalışan farklı platformları yönetebilirsiniz. Intune, ilkeleri ve ayarları cihaz platformuna göre ayırır. Bu nedenle belirli bir platformun cihazlarını kolayca yönetebilir ve görüntüleyebilirsiniz.

**[Yaygın senaryolar](common-scenarios.md)** , Intune 'un mobil cihazlarla çalışırken yaygın soruların nasıl yanıt verdiği hakkında bilgi almak için harika bir kaynaktır. Hakkında senaryolar bulacaksınız:  

- Şirket içi Exchange ile e-postayı koruma
- Office 365 güvenli ve güvenli erişim
- Kuruluş kaynaklarına erişmek için kişisel cihazları kullanma

Intune hakkında daha fazla bilgi için bkz. [Intune nedir](what-is-intune.md).

## <a name="integration-with-secure-and-protect-services"></a>Güvenli ve koruma hizmetleriyle tümleştirme

Herhangi bir cihaz yönetimi çözümünün önemli bir görevi, güvenlik ve koruma sağlamaktır. Intune, bu görevi gerçekleştirmek için diğer hizmetlerle tümleştirmeyle ilgili harika bir iş sağlar. Örnek:

- **Microsoft 365** , yaygın BT görevlerini basitleştirecek bir temel bileşendir. Microsoft 365 Yönetim merkezinde, kullanıcılar oluşturur ve grupları yönetirsiniz. Intune, Azure AD ve daha fazlası gibi diğer hizmetlere da erişebilirsiniz.

  Örneğin, Microsoft 365 ' de bir iOS cihazları grubu oluşturun. Daha sonra, Intune 'u kullanarak App Store 'a erişim, AirDrop, iCloud 'a yedekleme, Apple 'ın Web Filter ve daha fazlası gibi iOS özelliklerine odaklanarak ilkeleri gönderin.

- **Windows Defender** , Windows 10 cihazlarının korunmasına yardımcı olmak için birçok güvenlik özelliği içerir. Örneğin, Intune ve Windows Defender 'ı birlikte kullanarak şunları yapabilirsiniz:

  - Mobil cihazlardaki dosyalardaki ve uygulamalardaki şüpheli etkinlikleri aramak için [Windows Defender SmartScreen](../protect/endpoint-protection-windows-10.md) 'i etkinleştirin.
  - Mobil cihazlarda güvenlik ihlallerinin önlenmesine yardımcı olması için [Microsoft Defender Gelişmiş tehdit koruması (ATP)](../protect/advanced-threat-protection.md) kullanın. Ve, bir kullanıcıyı Kurumsal kaynaklardan engelleyerek bir güvenlik ihlalinin etkilerini sınırlandırmaya yardımcı olur.

- **Koşullu erişim** Azure Active Directory bir özelliktir ve Intune ile birlikte tümleştirilir. [Koşullu erişimi](../protect/conditional-access.md)kullanarak yalnızca uyumlu cihazların e-postaya, SharePoint 'e ve diğer uygulamalara erişimine izin verildiğinden emin olun.

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Sizin için doğru olan cihaz yönetimi çözümünü seçin

Cihaz yönetimine yaklaşıma yönelik birkaç yöntem vardır. İlk olarak, Intune 'da yerleşik özellikleri kullanarak cihazların farklı yönlerini yönetebilirsiniz. Bu yaklaşım, **mobil cihaz yönetimi (MDM)** olarak adlandırılır. Kullanıcılar cihazlarını "kaydeder" ve Intune ile iletişim kurmak için sertifikaları kullanır. BT Yöneticisi olarak, uygulamaları cihazlara gönderir, cihazları belirli bir işletim sistemiyle kısıtlar, kişisel cihazları engeller ve daha fazlasını yapın. Bir cihaz kaybolduysa veya çalınırsa cihazdaki tüm verileri de kaldırabilirsiniz.

İkinci yaklaşımda, cihazlarda uygulamaları yönetirsiniz. Bu yaklaşım, **mobil uygulama yönetimi (MAM)** olarak adlandırılır. Kullanıcılar, kendi kişisel cihazlarını kurumsal kaynaklara erişmek için kullanabilir. E-posta veya SharePoint gibi bir uygulama açılırken kullanıcılardan ek kimlik doğrulaması istenir. Bir cihaz kaybolduysa veya çalınırsa, cihazdaki tüm kuruluş verilerini kaldırabilirsiniz.

[MDM ve Mam](byod-technology-decisions.md) birleşimini de birlikte kullanabilirsiniz.

Intune 'u ayarlarken, cihazları yönetmek için yalnızca Azure portal çalışmayı ya da Intune 'u ve Microsoft 365 cihazları yönetmek için birlikte kullanmayı da tercih edersiniz. [Mobil cihaz yönetiminin Azure Portal Intune 'A geçirilmesi](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) bir Microsoft IT örnek olay araştırmaya sahiptir. Bu durumda, Microsoft BT 'nin modern cihaz yönetimi yaklaşımını nasıl seçtiği hakkında bilgi edinin ve öğrendiğimiz dersleri okuyun.

## <a name="simplify-it-tasks-using-the-device-management-admin-center"></a>Cihaz Yönetimi yönetim merkezini kullanarak BT görevlerini kolaylaştırın

[Cihaz yönetimi Yönetim Merkezi](https://devicemanagement.microsoft.com/) , mobil cihazlarınızla ilgili görevleri yönetmek ve gerçekleştirmek için tek seferlik bir mağaza ' dur. Bu çalışma alanı, Intune ve Azure Active Directory dahil olmak üzere cihaz yönetimi için kullanılan hizmetleri içerir ve istemci uygulamalarını da yönetir.

Cihaz Yönetimi yönetim merkezinde şunları yapabilirsiniz:

- [Cihazları kaydetme](../enrollment/device-enrollment.md)
- [Cihaz uyumluluğunu ayarla](../protect/device-compliance-get-started.md)
- [Cihazları yönetme](../remote-actions/device-management.md)
- [Uygulamaları yönetme](../apps/app-management.md)  
- [iOS e-kitapları](../apps/vpp-ebooks-ios.md)  
- [Exchange şirket içi Bağlayıcısı 'nı yükler](../protect/exchange-connector-install.md)  
- [Rolleri yönetme](role-based-access-control.md)  
- Yazılım güncelleştirmelerini yönetme
  - [Windows 10 güncelleştirmelerini yönetme](../protect/windows-update-for-business-configure.md)  
  - [İOS güncelleştirmelerini yönetme](../protect/software-updates-ios.md)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Kullanıcıları yönetme](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Grupları ve üyeleri yönetme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Sorun giderme](help-desk-operators.md)

## <a name="next-steps"></a>Sonraki adımlar

Bir MDM veya MAM çözümüne başlamak için hazırsanız, Intune 'u ayarlama, cihazları kaydetme ve ilke oluşturmaya başlama gibi farklı adımları gözden geçir. [Microsoft 365 Için mobil cihaz yönetimi](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) de harika bir kaynaktır.
