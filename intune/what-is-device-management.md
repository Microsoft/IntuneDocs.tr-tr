---
title: Microsoft 365'te cihaz yönetimi
description: Microsoft 365 Kurumsal, Microsoft Intune'u içerir. Intune mobil cihaz yönetimi ve kuruluşunuz için mobil uygulama yönetimine nasıl sağladığını görürsünüz. Yaygın senaryoları okuyun ve Microsoft 365 ortamınızda dağıtmak için Intune kullanıyor.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/12/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d5614f0657175658c1a8442d650e16c8550c1ac1
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043846"
---
# <a name="what-is-device-management"></a>Cihaz yönetimi nedir? 

Her Yönetici'nin başlıca görevlerinden biri kuruluşun kaynaklarının ve verilerinin güvenliğini sağlamaktır. Bu görev *cihaz Yönetimi*. Kullanıcılar nerede bunlar açın ve kişisel dosyaları, Web sitelerini ziyaret ve uygulamaları ve oyunları yüklemek birçok cihaz sahip. Bu aynı de çalışanlara ve öğrencilere kullanıcılardır. Şirket erişimi iş ve Okul e-posta ve OneNote gibi kaynakları için kendi cihazlarını kullanmalarına istemektedir. Cihaz yönetimi, kuruluşların kendi kaynakları ve veri korunmasına olanak sağlar. 

Bir cihaz yönetimi sağlayıcısı'nı kullanarak, kuruluş, yalnızca yetkili kişiler doğrulayabilen ve aygıtları şirkete özel bilgiler erişin. Benzer şekilde, alışık oldukları cihazlarını, kuruluşun güvenlik gereksinimlerini karşılamak için cihaz kullanıcılarının telefonlarından, iş verilerine erişme kolaylığı adresindeki düşünüyor. Kuruluş olarak şunu soruyor olabilirsiniz: **Kaynaklarımızı korumak için ne kullanmalıyız?**

Yanıt [Intune](https://docs.microsoft.com/intune/introduction-intune). Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sunar. Her MDM ya da MAM çözümünün aşağıdakiler gibi bazı başlıca görevleri vardır:

- Farklı mobil bir ortamı desteklemek ve iOS, Android, Windows ve macOS cihazların güvenli bir şekilde yönetin.
- Cihazlar ve uygulamalar, kuruluşunuzun güvenlik gereksinimlerine uygun olduğundan emin olun.
- Şirket ve kişisel cihazlarda kuruluş verilerinizi güvende tutmak ilkeleri oluşturun.
- Bu ilkeleri yaptırmak ve cihazları, uygulamaları, kullanıcıları ve grupları yönetmek için birleştirilmiş tek bir mobil çözüm sunma.

Intune, Microsoft 365'e dahil edilmiştir ve Azure Active Directory (Azure AD) ile tümleşir. Azure AD kimin ve neye erişimi olduğunu denetlemeye yardımcı olur.

## <a name="hello-intune"></a>Merhaba Intune!
Microsoft gibi birçok kuruluş, Intune'u kullanıcıların şirkete ait ve kişisel mobil cihazlardan eriştikleri şirkete ait verileri korumak için kullanmaktadır. Intune, cihaz ve uygulama yapılandırma ilkeleri, yazılım güncelleştirme ilkeleri ve güvenli ve veri erişimini izlemeye yardımcı olması için yükleme durumlarını (grafikler, tablolar ve raporlar) içerir.

İnsanların farklı platformlar kullanan birden çok cihazı olması sık görülen bir durumdur. Örneğin bir çalışan iş için Surface Pro ve kişisel yaşamı için bir Android mobil cihaz kullanabilir. Aynı kişilerin bu değişik cihazlardan Microsoft Outlook ve SharePoint gibi kuruluş kaynaklarına erişmesi de yine sık görülen bir durumdur.

Intune ile herkesin cihazlarını ve bu cihazlarda çalışan iOS, macOS, Android ve Windows gibi farklı platformları yönetebilirsiniz. Intune ilkeleri ve ayarları, cihaz platformuna göre ayırır. Bu nedenle yönetmek ve belirli bir platforma ait cihazları görüntülemek kolaydır.

**[Yaygın senaryolar](https://docs.microsoft.com/intune/common-scenarios)** Intune'un mobil cihazlarla çalışılırken sık karşılaşılan soruları nasıl yanıtladığını görmek için harika bir kaynaktır. Burada aşağıdakilerle ilgili senaryolar bulabilirsiniz:  
- Şirket içi Exchange ile e-postaların korunması
- Office 365'e emniyetli ve güvenli bir şekilde erişme
- Kişisel cihazları kurumsal kaynaklara erişmek için kullanma

## <a name="integration-with-secure-and-protect-services"></a>Güvenli tutma ve koruma hizmetleri ile tümleştirme
Cihaz yönetim çözümlerinin başlıca görevlerinden biri güvenlik ve koruma sağlamaktır. Intune bu görevi gerçekleştirmek için başka hizmetlerle mükemmel bir şekilde tümleşir. Örneğin:

- **Microsoft 365** yaygın BT görevlerini basitleştirmek için temel bir bileşenidir. Microsoft 365 Yönetim Merkezi'nde kullanıcıları oluşturun ve grupları yönetin. Intune, Azure AD gibi diğer hizmetlere erişimi ayrıca Al ve daha fazlası. 

  Örneğin, Microsoft 365'te bir iOS cihaz grubu oluşturun. Daha sonra Intune'u uygulama mağazasına erişim, AirDrop, iCloud'a yedekleme, Apple'ın web filtresini kullanma vb. iOS özelliklerine odaklı iOS cihazları grubuna anında ilke iletmek için kullanabilirsiniz.

- **Windows Defender** Windows 10 cihazlarını korumaya yardımcı olacak birçok güvenlik özelliği içerir. Örneğin Intune'u ve Windows Defender'ı birlikte kullanarak şunları yapabilirsiniz: 

    - Mobil cihazlarda dosya ve uygulamalarda kuşku verici etkinlik aramak için [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10)'ı etkinleştirme. 
    - Kullanım [Windows Defender Gelişmiş tehdit Koruması (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) mobil cihazlarda güvenlik ihlallerini önlemeye yardımcı olmak için. Ayrıca, bir kullanıcı şirket kaynaklarına engelleyerek güvenlik ihlali etkisini sınırlamaya Yardım.

- **Koşullu erişim** Azure Active Directory özelliğidir ve Intune ile sorunsuz şekilde tümleşir. Kullanarak [koşullu erişim](https://docs.microsoft.com/intune/conditional-access), yalnızca uyumlu cihazların e-posta, SharePoint ve diğer uygulamalara erişim sağlandığından emin olun. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Sizin için doğru olan cihaz yönetim çözümünü seçin

Cihaz yönetimine birkaç şekilde yaklaşılabilir. İlk olarak, cihazları Intune'a yerleşik özellikleri kullanarak farklı özelliklerini yönetebilir. Bu yaklaşım adlı **mobil cihaz Yönetimi (MDM)**. Kullanıcılar, "kullanıcıların cihazlarını kaydetmelerini" ve Intune ile iletişim kurmak için sertifikaları kullanır. BT yöneticisi, uygulama gönderme cihazlarda, belirli bir işletim sistemi, kişisel cihazları engellemek ve diğer cihazları kısıtlama. Ayrıca bir cihazın kaybolması veya çalınması durumunda bu cihazdaki tüm verileri kaldırabilirsiniz. 

İkinci yaklaşımda cihazlardaki uygulamaları yönetirsiniz. Bu yaklaşım adlı **mobil uygulama yönetimi (MAM)**. Kullanıcılar kişisel cihazlarından kurumsal kaynaklara erişmek için kullanabilirsiniz. E-posta veya SharePoint gibi bir uygulamayı açarken kullanıcılardan ek kimlik doğrulaması istenir. Bir cihazın kaybolması veya çalınması durumunda cihazdan kuruluşun tüm verilerini kaldırabilirsiniz. 

Ayrıca [MDM ve MAM](https://docs.microsoft.com/intune/byod-technology-decisions) yaklaşımlarını birlikte de kullanabilirsiniz.

Intune'u kurarken ayrıca cihazları yönetmek için yalnızca Azure portalında çalışmayı ya da Intune ve Microsoft 365'i birlikte kullanmayı da seçebilirsiniz. [Azure portalında ıntune'a geçirme mobil cihaz Yönetimi](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) Microsoft IT incelemesi olduğunu. Bu durumda incelemek, Microsoft IT modern cihaz Yönetimi yaklaşımı seçtiğiniz ve dersler okuma bakın.

## <a name="simplify-it-tasks-using-the-device-management-dashboard"></a>Cihaz Yönetim panosunu kullanarak BT görevlerini basitleştirin

[Cihaz Yönetim panosu](https://devicemanagement.portal.azure.com/) mobil cihazlarınızın görevlerini yönetmek ve tamamlamak için tek yerdir. Bu pano, Intune ve Azure Active Directory dahil olmak üzere cihaz ve ayrıca istemci uygulama yönetimi için kullanılan hizmetleri içerir. 

Cihaz Yönetim panosunda şunları yapabilirsiniz:

- [Cihazları kaydetme](https://docs.microsoft.com/intune/device-enrollment)
- [Cihaz uyumluluğu ayarlama](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Cihazları yönetme](https://docs.microsoft.com/intune/device-management)
- [Uygulamaları yönetme](https://docs.microsoft.com/intune/app-management)  
- [iOS e-Kitapları](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [Şirket içi Exchange bağlayıcısını yükleme](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Rolleri yönetme](https://docs.microsoft.com/intune/role-based-access-control)  
- Yazılım güncelleştirmelerini yönetme
  - [Windows 10 güncelleştirmelerini yönetme](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [iOS güncelleştirmelerini yönetme](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Kullanıcıları yönetme](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Grupları ve üyeleri yönetme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Sorun giderme](https://docs.microsoft.com/intune/help-desk-operators)

## <a name="next-step"></a>Sonraki adım
Ne zaman bir MDM veya MAM çözümlerini kullanmaya başlama, ıntune'u ayarlama, cihazları kaydetmek ve ilkeleri oluşturmaya başlamak için farklı adım adım hazırsınız. [Microsoft 365 için mobil cihaz Yönetimi](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) de harika bir kaynaktır.
