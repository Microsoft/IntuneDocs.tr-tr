---
title: Microsoft 365'te cihaz yönetimi
description: Microsoft 365 Kurumsal, Microsoft Intune'u içerir. Intune 'un kuruluşunuz için mobil cihaz yönetimi ve mobil uygulama yönetimi nasıl sağladığını öğrenin. Yaygın senaryoları okuyun ve ortamınızda Microsoft 365 dağıtmak için Intune 'u kullanın.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ab41026cd9b2ceeaaa478fc27c984d0d89db4c5
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74058520"
---
# <a name="device-management-overview"></a>Cihaz yönetimine genel bakış

Her Yönetici'nin başlıca görevlerinden biri kuruluşun kaynaklarının ve verilerinin güvenliğini sağlamaktır. Bu görev *cihaz yönetimi*. Kullanıcıların kişisel dosyaları açıp paylaştığı, Web sitelerini ziyaret eden ve uygulamaları ve oyunları yükleyen birçok cihazı vardır. Aynı kullanıcılar aynı zamanda çalışanlar ve öğrencilerlerdir. E-posta ve OneNote gibi iş ve okul kaynaklarına erişmek için cihazlarını kullanmak ister.

Cihaz yönetimi, kuruluşların kaynaklarını ve verilerini ve farklı cihazlardan korunmasını ve güvenliğini sağlar.

Kuruluş, bir cihaz yönetimi sağlayıcısı kullanarak yalnızca yetkili kişilerin ve cihazların mülkiyet bilgilerine erişmesini sağlayabilir. Benzer şekilde, cihaz kullanıcıları, cihazlarını kuruluşun güvenlik gereksinimlerini karşılayacak şekilde biledikleri için iş verilerine telefonlarından erişmeyi kolaylaştırabilir. Kuruluş olarak şunu soruyor olabilirsiniz: **Kaynaklarımızı korumak için ne kullanmalıyız?**

Yanıt [Microsoft Intune](what-is-intune.md). Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sunar. Her MDM ya da MAM çözümünün aşağıdakiler gibi bazı başlıca görevleri vardır:

- Farklı bir mobil ortamı destekler ve iOS, Android, Windows ve macOS cihazlarını güvenli bir şekilde yönetin.
- Cihazların ve uygulamaların kuruluşunuzun güvenlik gereksinimleriyle uyumlu olduğundan emin olun.
- Kuruluş verilerinizi kuruluşa ait ve kişisel cihazlarda güvende tutmaya yardımcı olan ilkeler oluşturun.
- Bu ilkeleri yaptırmak ve cihazları, uygulamaları, kullanıcıları ve grupları yönetmek için birleştirilmiş tek bir mobil çözüm sunma.
- İş gücünüzün erişimlerini ve verilerini nasıl paylaştığını denetlemeye yardımcı olarak şirket bilgilerinizi koruyun.

Intune, Microsoft Azure, Microsoft 365 ve Azure Active Directory (Azure AD) ile tümleşir. Azure AD kimin ve neye erişimi olduğunu denetlemeye yardımcı olur.

## <a name="microsoft-intune"></a>Microsoft Intune

Microsoft gibi birçok kuruluş, Intune'u kullanıcıların şirkete ait ve kişisel mobil cihazlardan eriştikleri şirkete ait verileri korumak için kullanmaktadır. Intune, veri erişimini güvenli hale getirmenize ve izlemenize yardımcı olmak için cihaz ve uygulama yapılandırma ilkeleri, yazılım güncelleştirme ilkeleri ve yükleme durumları (grafikler, tablolar ve raporlar) içerir.

İnsanların farklı platformlar kullanan birden çok cihazı olması sık görülen bir durumdur. Örneğin bir çalışan iş için Surface Pro ve kişisel yaşamı için bir Android mobil cihaz kullanabilir. Aynı kişilerin bu değişik cihazlardan Microsoft Outlook ve SharePoint gibi kuruluş kaynaklarına erişmesi de yine sık görülen bir durumdur.

Intune ile herkesin cihazlarını ve bu cihazlarda çalışan iOS, macOS, Android ve Windows gibi farklı platformları yönetebilirsiniz. Intune, ilkeleri ve ayarları cihaz platformuna göre ayırır. Bu nedenle belirli bir platformun cihazlarını kolayca yönetebilir ve görüntüleyebilirsiniz.

**[Yaygın senaryolar](common-scenarios.md)** Intune'un mobil cihazlarla çalışılırken sık karşılaşılan soruları nasıl yanıtladığını görmek için harika bir kaynaktır. Burada aşağıdakilerle ilgili senaryolar bulabilirsiniz:  

- Şirket içi Exchange ile e-postaların korunması
- Office 365'e emniyetli ve güvenli bir şekilde erişme
- Kişisel cihazları kurumsal kaynaklara erişmek için kullanma

Intune hakkında daha fazla bilgi için bkz. [Intune nedir](what-is-intune.md).

## <a name="integration-with-secure-and-protect-services"></a>Güvenli tutma ve koruma hizmetleri ile tümleştirme

Cihaz yönetim çözümlerinin başlıca görevlerinden biri güvenlik ve koruma sağlamaktır. Intune bu görevi gerçekleştirmek için başka hizmetlerle mükemmel bir şekilde tümleşir. Örneğin:

- **Microsoft 365** yaygın BT görevlerini basitleştirmek için temel bir bileşenidir. Microsoft 365 Yönetim merkezinde, kullanıcılar oluşturur ve grupları yönetirsiniz. Intune, Azure AD ve daha fazlası gibi diğer hizmetlere da erişebilirsiniz.

  Örneğin, Microsoft 365 ' de bir iOS cihazları grubu oluşturun. Daha sonra Intune'u uygulama mağazasına erişim, AirDrop, iCloud'a yedekleme, Apple'ın web filtresini kullanma vb. iOS özelliklerine odaklı iOS cihazları grubuna anında ilke iletmek için kullanabilirsiniz.

- **Windows Defender** Windows 10 cihazlarını korumaya yardımcı olacak birçok güvenlik özelliği içerir. Örneğin Intune'u ve Windows Defender'ı birlikte kullanarak şunları yapabilirsiniz:

  - Mobil cihazlarda dosya ve uygulamalarda kuşku verici etkinlik aramak için [Windows Defender SmartScreen](../protect/endpoint-protection-windows-10.md)'ı etkinleştirme.
  - Mobil cihazlarda güvenlik ihlallerinin önlenmesine yardımcı olması için [Microsoft Defender Gelişmiş tehdit koruması (ATP)](../protect/advanced-threat-protection.md) kullanın. Ve, bir kullanıcıyı Kurumsal kaynaklardan engelleyerek bir güvenlik ihlalinin etkilerini sınırlandırmaya yardımcı olur.

- **Koşullu erişim** Azure Active Directory bir özelliktir ve Intune ile birlikte tümleştirilir. [Koşullu erişimi](../protect/conditional-access.md)kullanarak yalnızca uyumlu cihazların e-postaya, SharePoint 'e ve diğer uygulamalara erişimine izin verildiğinden emin olun.

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Sizin için doğru olan cihaz yönetim çözümünü seçin

Cihaz yönetimine birkaç şekilde yaklaşılabilir. İlk olarak, Intune 'da yerleşik özellikleri kullanarak cihazların farklı yönlerini yönetebilirsiniz. Bu yaklaşım, **mobil cihaz yönetimi (MDM)** olarak adlandırılır. Kullanıcılar cihazlarını "kaydeder" ve Intune ile iletişim kurmak için sertifikaları kullanır. BT Yöneticisi olarak, uygulamaları cihazlara gönderir, cihazları belirli bir işletim sistemiyle kısıtlar, kişisel cihazları engeller ve daha fazlasını yapın. Ayrıca bir cihazın kaybolması veya çalınması durumunda bu cihazdaki tüm verileri kaldırabilirsiniz.

İkinci yaklaşımda cihazlardaki uygulamaları yönetirsiniz. Bu yaklaşım, **mobil uygulama yönetimi (MAM)** olarak adlandırılır. Kullanıcılar, kendi kişisel cihazlarını kurumsal kaynaklara erişmek için kullanabilir. E-posta veya SharePoint gibi bir uygulamayı açarken kullanıcılardan ek kimlik doğrulaması istenir. Bir cihazın kaybolması veya çalınması durumunda cihazdan kuruluşun tüm verilerini kaldırabilirsiniz.

Ayrıca [MDM ve MAM](byod-technology-decisions.md) yaklaşımlarını birlikte de kullanabilirsiniz.

Intune'u kurarken ayrıca cihazları yönetmek için yalnızca Azure portalında çalışmayı ya da Intune ve Microsoft 365'i birlikte kullanmayı da seçebilirsiniz. [Mobil cihaz yönetiminin Azure Portal Intune 'A geçirilmesi](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) bir Microsoft IT örnek olay araştırmaya sahiptir. Bu durumda, Microsoft BT 'nin modern cihaz yönetimi yaklaşımını nasıl seçtiği hakkında bilgi edinin ve öğrendiğimiz dersleri okuyun.

## <a name="simplify-it-tasks-using-the-device-management-admin-center"></a>Cihaz Yönetimi yönetim merkezini kullanarak BT görevlerini kolaylaştırın

[Microsoft Uç Nokta Yöneticisi Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) , mobil cihazlarınızla ilgili görevleri yönetmek ve gerçekleştirmek için tek seferlik bir mağaza. Bu çalışma alanı, Intune ve Azure Active Directory dahil olmak üzere cihaz yönetimi için kullanılan hizmetleri içerir ve istemci uygulamalarını da yönetir.

Cihaz Yönetimi yönetim merkezinde şunları yapabilirsiniz:

- [Cihazları kaydetme](../enrollment/device-enrollment.md)
- [Cihaz uyumluluğu ayarlama](../protect/device-compliance-get-started.md)
- [Cihazları yönetme](../remote-actions/device-management.md)
- [Uygulamaları yönetme](../apps/app-management.md)  
- [iOS e-Kitapları](../apps/vpp-ebooks-ios.md)  
- [Şirket içi Exchange bağlayıcısını yükleme](../protect/exchange-connector-install.md)  
- [Rolleri yönetme](role-based-access-control.md)  
- Yazılım güncelleştirmelerini yönetme
  - [Windows 10 güncelleştirmelerini yönetme](../protect/windows-update-for-business-configure.md)  
  - [iOS güncelleştirmelerini yönetme](../protect/software-updates-ios.md)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Kullanıcıları yönetme](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Grupları ve üyeleri yönetme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Sorun Giderme](help-desk-operators.md)

## <a name="next-steps"></a>Sonraki adımlar

Bir MDM veya MAM çözümüne başlamak için hazırsanız, Intune 'u ayarlama, cihazları kaydetme ve ilke oluşturmaya başlama gibi farklı adımları gözden geçir. [Microsoft 365 Için mobil cihaz yönetimi](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) de harika bir kaynaktır.
