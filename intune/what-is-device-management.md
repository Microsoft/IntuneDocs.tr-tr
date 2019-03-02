---
title: Microsoft 365'te cihaz yönetimi
description: Microsoft 365 Kurumsal, Microsoft Intune'u içerir. Intune'un sık görülen senaryolarda kuruluşunuza nasıl mobil cihaz yönetimi ve mobil uygulama yönetimi sağladığını ve ortamınızda Microsoft 365 dağıtmak için Intune kullanmayı öğrenin.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93e34c3de77dde59b87829617b8cbbd2614f7081
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231256"
---
# <a name="what-is-device-management"></a>Cihaz yönetimi nedir? 

Her Yönetici'nin başlıca görevlerinden biri kuruluşun kaynaklarının ve verilerinin güvenliğini sağlamaktır. Bu görev cihaz yönetimidir. Kullanıcıların kişisel dosya açıp paylaştığı, web sitesi ziyaret ettiği ve uygulama ve oyun yüklediği pek çok cihazı vardır. Bu kullanıcılar ayrıca çalışan ve öğrencidirler ve cihazlarını e-posta ve OneNote gibi iş ve okul kaynaklarına erişmek için de kullanmak isterler. *Cihaz yönetimi* kuruluşların kendi kaynak ve verilerini korumasını ve güvenli tutmasını sağlar. 

Kuruluşlar, bir cihaz yönetim sağlayıcısı kullanarak şirketin mülkiyeti olan bilgilere yalnızca yetkili kişi ve cihazların eriştiğinden emin olabilir. Aynı şekilde kullanıcılar da cihazlarının kuruluşun güvenlik gereksinimlerini karşıladığını bildikleri için telefonlarından iş verilerine erişirken rahatlayabilirler. Kuruluş olarak şunu soruyor olabilirsiniz: **Kaynaklarımızı korumak için ne kullanmalıyız?**

[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) burada devreye girer. Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) sunar. Her MDM ya da MAM çözümünün aşağıdakiler gibi bazı başlıca görevleri vardır:

- Çok değişken bir modil ortamı destekleme&mdash;iOS, Android, Windows ve macOS cihazlarını güvenli bir şekilde yönetme
- Cihazların ve uygulamaların kuruluşunuzun güvenlik gereksinimlerine uygun olmasını sağlama
- Kuruluşunuzun verilerini şirkete ait ve kişisel cihazlarda güvende tutmayı sağlayacak ilkeler oluşturma
- Bu ilkeleri yaptırmak ve cihazları, uygulamaları, kullanıcıları ve grupları yönetmek için birleştirilmiş tek bir mobil çözüm sunma.

Intune, Microsoft 365'e dahil edilmiştir ve Azure Active Directory (Azure AD) ile tümleşir. Azure AD kimin ve neye erişimi olduğunu denetlemeye yardımcı olur.

## <a name="hello-intune"></a>Merhaba Intune!
Microsoft gibi birçok kuruluş, Intune'u kullanıcıların şirkete ait ve kişisel mobil cihazlardan eriştikleri şirkete ait verileri korumak için kullanmaktadır. Intune; cihaz ve uygulama yapılandırma ilkeleri, yazılım güncelleştirme ilkeleri ve yükleme durumları (ayrıca grafikler, tablolar ve raporlar) gibi veri erişimini güvende tutmanızı ve izlemenizi sağlayan özellikler içerir.

İnsanların farklı platformlar kullanan birden çok cihazı olması sık görülen bir durumdur. Örneğin bir çalışan iş için Surface Pro ve kişisel yaşamı için bir Android mobil cihaz kullanabilir. Aynı kişilerin bu değişik cihazlardan Microsoft Outlook ve SharePoint gibi kuruluş kaynaklarına erişmesi de yine sık görülen bir durumdur.

Intune ile herkesin cihazlarını ve bu cihazlarda çalışan iOS, macOS, Android ve Windows gibi farklı platformları yönetebilirsiniz. Intune, belirli bir platformun cihazlarını yönetmeyi ve görüntülemeyi kolaylaştırmak için ilkeleri ve ayarları cihaz platformuna göre ayırır.

**[Yaygın senaryolar](https://docs.microsoft.com/intune/common-scenarios)** Intune'un mobil cihazlarla çalışılırken sık karşılaşılan soruları nasıl yanıtladığını görmek için harika bir kaynaktır. Burada aşağıdakilerle ilgili senaryolar bulabilirsiniz:  
- Şirket içi Exchange ile e-postaların korunması
- Office 365'e emniyetli ve güvenli bir şekilde erişme
- Kişisel cihazları kurumsal kaynaklara erişmek için kullanma

## <a name="integration-with-secure-and-protect-services"></a>Güvenli tutma ve koruma hizmetleri ile tümleştirme
Cihaz yönetim çözümlerinin başlıca görevlerinden biri güvenlik ve koruma sağlamaktır. Intune bu görevi gerçekleştirmek için başka hizmetlerle mükemmel bir şekilde tümleşir. Örneğin:

- **Microsoft 365** yaygın BT görevlerini basitleştirmek için temel bir bileşenidir. Microsoft 365 yönetim merkezini kullanarak kullanıcılar oluşturabilir, grupları yönetebilir ve Intune, Azure Active Directory ve daha pek çokları gibi başka hizmetlere erişebilirsiniz. Örneğin Microsoft 365'te bir iOS cihazları grubu oluşturabilirsiniz. Daha sonra Intune'u uygulama mağazasına erişim, AirDrop, iCloud'a yedekleme, Apple'ın web filtresini kullanma vb. iOS özelliklerine odaklı iOS cihazları grubuna anında ilke iletmek için kullanabilirsiniz.

- **Windows Defender** Windows 10 cihazlarını korumaya yardımcı olacak birçok güvenlik özelliği içerir. Örneğin Intune'u ve Windows Defender'ı birlikte kullanarak şunları yapabilirsiniz: 

    - Mobil cihazlarda dosya ve uygulamalarda kuşku verici etkinlik aramak için [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10)'ı etkinleştirme. 
    - [Windows Defender Gelişmiş Tehdit Koruması (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) kullanarak mobil cihazlarda güvenlik ihlallerini engellemeye ve bunların etkisini, kullanıcının kurumsal kaynaklara erişimini engelleyerek sınırlamaya yardımcı olma.

- **Koşullu erişim** Azure Active Directory'nin bir özelliğidir ve Intune ile sorunsuz tümleşir. [Koşullu erişim](https://docs.microsoft.com/intune/conditional-access) kullanarak e-posta, SharePoint ve diğer uygulamalara yalnızca uyumlu cihazların erişmesine izin verildiğinden emin olabilirsiniz. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>Sizin için doğru olan cihaz yönetim çözümünü seçin

Cihaz yönetimine birkaç şekilde yaklaşılabilir. İlk olarak Intune'daki yerleşik tüm özellikleri kullanarak cihazları her yönüyle yönetebilirsiniz. Buna **Mobil cihaz yönetimi (MDM)** denir. Bu yaklaşımda kullanıcılar cihazlarını "kaydeder" ve Intune ile iletişim kurmak için sertifika kullanır. BT yöneticisi olarak cihazlara uygulama gönderebilir, bunları belirli bir işletim sistemleriyle sınırlayabilir, kişisel cihazları engelleyebilir ve daha birçok şey yapabilirsiniz. Ayrıca bir cihazın kaybolması veya çalınması durumunda bu cihazdaki tüm verileri kaldırabilirsiniz. 

İkinci yaklaşımda cihazlardaki uygulamaları yönetirsiniz. Buna **Mobil uygulama yönetimi (MAM)** denir. Bu yaklaşımda kullanıcılar, kuruluş kaynaklarına erişmek için kişisel cihazlarını kullanabilir. E-posta veya SharePoint gibi bir uygulamayı açarken kullanıcılardan ek kimlik doğrulaması istenir. Bir cihazın kaybolması veya çalınması durumunda cihazdan kuruluşun tüm verilerini kaldırabilirsiniz. 

Ayrıca [MDM ve MAM](https://docs.microsoft.com/intune/byod-technology-decisions) yaklaşımlarını birlikte de kullanabilirsiniz.

Intune'u kurarken ayrıca cihazları yönetmek için yalnızca Azure portalında çalışmayı ya da Intune ve Microsoft 365'i birlikte kullanmayı da seçebilirsiniz. Microsoft BT vaka çalışmasında, Microsoft BT'nin nasıl modern bir cihaz yönetim yaklaşımını tercih ettiğini ve [Mobil cihaz yönetimini Azure portalında Intune'a taşıma](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal)'dan alınan dersleri görün. 

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
Bir MDM veya MAM çözümünü kullanmaya başlamaya, Intune'u kurma adımlarını uygulamaya, cihazlar kaydetmeye ve ilkeler oluşturmaya hazır olduğunuzda [Microsoft 365 için mobil cihaz yönetimi](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)'ne bakın. 
