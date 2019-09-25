---
title: Microsoft Intune nedir?
description: Microsoft Intune Enterprise Mobility + Security çözümünün mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) bileşeni ve şirket verilerini korumanıza nasıl yardımcı olduğu hakkında bilgi edinin.
keywords: Intune nedir?
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/20/2019
ms.topic: overview
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2cde4e37889b981decfd18138feeb4edac46c4c8
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "71238242"
---
# <a name="what-is-microsoft-intune"></a>Microsoft Intune nedir?

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Microsoft Intune kurumsal taşınabilirlik yönetimi (EMM) alanındaki bulut tabanlı bir hizmettir ve Şirket verilerinizi korumalı tutarken iş gücünüzün üretken olmasına yardımcı olur. Diğer Azure hizmetleri gibi Microsoft Intune da Azure portalında kullanılabilir. Intune ile şunları yapabilirsiniz:
* Şirket verilerine erişmek için iş gücünüzün kullandığı mobil cihazları ve bilgisayarları yönetin.
* Çalışanlarınızın kullandığı mobil uygulamaları yönetebilirsiniz.
* Çalışanlarınızın erişim ve paylaşım yöntemlerinin denetlenmesine yardımcı olarak şirket bilgilerinizi koruyabilirsiniz.
* Cihazların ve uygulamaların şirket güvenlik gereksinimlerine uygun olduğundan emin olabilirsiniz.

## <a name="common-business-problems-that-intune-helps-solve"></a>Intune'un çözmenize yardımcı olduğu yaygın iş sorunları

* [Şirket içi e-postalarınızı ve verilerinizi koruyarak mobil cihazların bunlara erişmesini sağlama](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Office 365 e-postalarınızı ve verilerinizi koruyarak mobil cihazların bunlara güvenle erişmesini sağlama](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Çalışanlarınıza şirketin sahip olduğu telefonları verme](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Tüm çalışanlara kendi cihazını getir (KCG) veya kişisel cihaz programı sunma](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Çalışanlarınızın yönetilmeyen genel bir bilgi noktasından Office 365'e güvenle erişmesini sağlama](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Görev çalışanlarınıza sınırlı kullanımlı paylaşılan tabletler verme](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)


## <a name="how-does-intune-work"></a>Intune nasıl çalışır?
Intune, mobil cihazları ve uygulamaları yöneten Microsoft Enterprise Mobility + Security (EMS) paketinin bileşenidir. Kimlik ve erişim denetimi için Azure Active Directory (Azure AD) gibi diğer EMS bileşenleriyle, veri koruma için ise Azure Information Protection ile tümleşir. Office 365 ile birlikte kullanıldığında, çalışanlarınıza tüm cihazlardan üretken bir şekilde çalışma olanağı tanırken kuruluşunuzun bilgilerini de koruma altına alır.

![Intune mimarisi görüntüsü](./media/intunearch_sm.png)

Intune mimari diyagramının [daha büyük bir sürümünü](./media/intunearchitecture.svg) görüntüleyin.

Intune ve EMS veri koruma hizmetinin cihaz ve uygulama yönetimi özelliklerini kullanma şekliniz, [çözmeye çalıştığınız işletme sorununa](#common-business-problems-that-intune-helps-solve) bağlıdır. Örneğin:
* Bir perakende satış mağazasındaki vardiyalı çalışanlar tarafından kullanılacak tek uygulama çalıştıran cihazlarla bir havuz oluşturuyorsanız ağırlıklı olarak cihaz yönetimini kullanırsınız.
* Çalışanların kurumsal verilere erişmek için kendi kişisel cihazlarını kullanmalarına (KCG) izin veriyorsanız uygulama yönetimi ve veri koruma hizmetlerinden yararlanırsınız.  
* Bilgi işlem çalışanlarına şirket telefonu veriyorsanız tüm teknolojileri bir arada kullanırsınız.

## <a name="intune-device-management-explained"></a>Intune cihaz yönetimi açıklaması
Intune cihaz yönetimi, mobil işletim sistemlerindeki kullanılabilir protokollerden veya API’lerden faydalanır. Hizmet, şunun gibi görevleri içerir:
* BT departmanınızın kurumsal hizmetlere erişen cihazların listesine sahip olması için cihazları yönetime kaydetme
* Cihazları şirket güvenlik ve sistem durumu standartlarına uyacak şekilde yapılandırma
* Kurumsal hizmetlere erişim sağlamak için sertifikaları ve Wi-Fi/VPN profillerini sunma
* Cihazların kurumsal standartlar açısından uyumluluk durumunu ölçme ve raporlama
* Yönetilen cihazlardaki kurumsal verileri kaldırma  

Bazen, kişiler **Denetim erişimini şirket verilerine** düşünebilir ve bir cihaz yönetimi özelliğidir. Bu hizmet, mobil işletim sistemleri tarafından sunulan bir özellik olmadığı için biz bu şekilde sınıflandırmıyoruz. Bu hizmet, kimlik sağlayıcı tarafından sunulmaktadır. Burada kimlik sağlayıcı, Microsoft'un kimlik ve erişim yönetim sistemi olan Azure Active Directory (Azure AD) olacaktır.  

Intune, Azure AD ile birlikte geniş bir erişim denetim senaryosu kümesi sunar. Örneğin, bir mobil cihazın Exchange gibi kurumsal bir hizmete erişebilmesi için Intune’da tanımladığınız kurumsal standartlara uygun olması şartını koyabilirsiniz. Benzer şekilde kurumsal hizmeti belirli bir mobil uygulama kümesiyle sınırlandırabilirsiniz. Örnek olarak, Exchange Online'a yalnızca Outlook veya Outlook Mobile ile erişilmesini sağlayabilirsiniz.

## <a name="intune-app-management-explained"></a>Intune uygulama yönetimi açıklaması
Uygulama yönetimi dendiğinde şunlar akla gelmelidir:
* Çalışanlara mobil uygulama atama
* Uygulama çalıştırıldığında kullanılan standart ayarlarla uygulama yapılandırma
* Kurumsal verilerin mobil uygulamalarda kullanım ve paylaşım şekillerini denetleme
* Mobil uygulamalardaki kurumsal verileri kaldırma   
* Uygulama güncelleştirme
* Mobil uygulama envanter raporlarını alma
* Mobil uygulama kullanımını izleme

Mobil uygulama yönetimi (MAM) teriminin bu işlevlerden herhangi birinin veya birkaçının birlikte kullanıldığı senaryolar için kullanıldığına şahit olduk. Özellikle, uygulama yapılandırması kavramını mobil uygulamalar içindeki kurumsal verilerin güvenliğini sağlama kavramıyla birleştirmek yaygın bir uygulamadır. Bunun nedeni, bazı mobil uygulamalarda veri güvenliği özelliklerinin yapılandırılmasını sağlayan ayarların yer almasıdır.

Uygulama yapılandırma ve Intune dediğimizde, özel olarak [iOS’ta yönetilen uygulama yapılandırması](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html) gibi teknolojilerden bahsediyoruz.

Intune'u diğer EMS hizmetleriyle birlikte kullanarak kuruluşunuz için mobil işletim sistemi ve uygulama yapılandırması yoluyla mobil uygulamalar tarafından sunulandan daha fazla mobil uygulama güvenliği seçeneğine sahip olabilirsiniz. EMS ile yönetilen bir uygulama, daha geniş bir mobil uygulama kümesine ve aşağıdakiler de dahil olmak üzere veri koruma özelliklerine erişebilir:

* [Çoklu oturum açma](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
* [Çok faktörlü kimlik doğrulaması](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)
* [Uygulama koşullu erişimi-mobil uygulama şirket verilerini içeriyorsa erişime izin ver](app-based-conditional-access-intune.md)
* [Aynı uygulamadaki kurumsal verileri kişisel verilerden ayırma](app-protection-policy.md)
* [Uygulama koruma ilkesi (PIN, şifreleme, farklı kaydet, pano vs.)](app-protection-policies.md)
* [Mobil uygulamadan kurumsal verileri silme](apps-selective-wipe.md)
* [Hak yönetim desteği](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Uygulama yönetimi veri güvenliği düzeylerini gösteren görüntü](./media/managing-mobile-apps.png)

### <a name="intune-app-security"></a>Intune uygulama güvenliği
Uygulama güvenliğini sağlama, uygulama yönetimi hizmetlerinden biridir. Intune’da mobil uygulama güvenliği şu anlamları taşır:
* Kişisel bilgileri kurumsal BT farkındalığından ayırma
* Kullanıcıların kurumsal bilgilerle gerçekleştirebilecekleri eylemleri (kopyala, kes/yapıştır, kaydet ve görüntüle gibi) sınırlama
* Mobil uygulamalardaki kurumsal verileri kaldırma (seçmeli silme veya kurumsal verileri silme olarak da bilinir)

Intune 'un mobil uygulama güvenliği sağladığı bir yöntem, **Uygulama koruma ilkesi** özelliği aracılığıyla yapılır. Uygulama koruma ilkesi, kurumsal verileri kişisel verilerden ayırmak için Azure AD kimliğini kullanır. Şirket kimlik bilgilerini kullanarak erişilen verilere ek kurumsal korumalar sağlanacaktır.

Örneğin, bir Kullanıcı cihazlarıyla kurumsal kimlik bilgileriyle oturum açtığında, bunların şirket kimlikleri kendi kişisel kimlikleri tarafından reddedilen verilere erişmesine izin verir. Bu şirket verileri kullanıldıkça, uygulama koruma ilkeleri bunların nasıl kaydedildiği ve paylaşıldığını denetler. Aynı korumalar, Kullanıcı kendi cihazlarıyla kendi kişisel kimliğiyle oturum açtığında erişilen verilere uygulanmaz. Bu şekilde, Son Kullanıcı kendi kişisel verileri üzerinde denetim ve gizliliği sürdürirken şirket verilerinin denetimine sahiptir.

## <a name="emm-with-and-without-device-enrollment"></a>Cihaz kaydı ile ve cihaz kaydı olmadan EMM
Kurumsal mobilite yönetimi çözümlerinin çoğu, temel mobil cihaz ve mobil uygulama teknolojilerini destekler. Bunlar genelde cihazın kuruluşunuzun mobil cihaz yönetimi (MDM) çözümüne kaydedilmesini gerektirir. Intune bu senaryolara ek olarak birçok "kayıt olmadan" senaryosunu da destekler.  

Kuruluşların "kayıt olmadan" senaryolarını kullanma şekli değişiklik gösterir. Bazı kuruluşlarda standarttır. Bazıları ise kişisel tablet gibi yardımcı cihazlar için izin verir. Diğerleri ise hiç desteklemez. Bu son durumda bile, bir kuruluşun tüm çalışan cihazlarının MDM 'ye kaydedilmesini gerektiren, genellikle yükleniciler, satıcılar ve belirli bir istisna olan diğer cihazlar için "kayıt olmadan" senaryolar desteklenir.

Intune'un "kayıt olmadan" teknolojisini sisteme kaydolan cihazlarda da kullanabilirsiniz. Örneğin, MDM sistemine kayıtlı bir cihazda mobil işletim sistemi tarafından sunulan “birlikte açma” koruması bulunabilir. "Birlikte açma" koruması, her iki uygulama da aynı MDM sağlayıcısı tarafından yönetilmediği müddetçe, Outlook gibi bir uygulamadan bir belgeyi Word gibi başka bir uygulamaya açmanızı kısıtlayan bir Apple iOS özelliğidir. Ayrıca, farklı kaydet 'i denetlemek veya Multi-Factor Authentication sağlamak üzere EMS tarafından yönetilen mobil uygulamalara Uygulama koruma ilkesi uygulayabilir.

Kuruluşunuzun kayıtlı ve kayıtsız mobil cihazlar ve uygulamalarla ilgili pozisyonu ne olursa olsun, EMS'nin bir parçası olan Intune'da çalışanlarınızın üretkenliğini artırmaya yardımcı olarak kurumsal verilerinizi korumanızı sağlayarak araçlar mevcuttur.

## <a name="microsoft-intune-in-the-azure-portal"></a>Azure portalında Microsoft Intune

[Azure portalı](https://portal.azure.com), Microsoft Intune hizmetini bulabileceğiniz yerdir.

Azure portalında Microsoft Intune deneyiminin en önemli özellikleri şunlardır:

- Tüm Enterprise Mobility + Security (EMS) bileşenleriniz için tümleşik bir konsol
- Web standartlarında hazırlanan HTML tabanlı bir konsol
- Birçok eylemi otomatik hale getirmek için Microsoft Graph API’si desteği
- Tüm Azure uygulamalarınız genelinde uyumluluk sağlamak için Azure Active Directory (AD) grupları
- En modern web tarayıcıları için destek

Portal deneyiminizi özelleştirmeye yönelik hızlı bir kılavuz için bkz. [Azure portalında Intune’a başlarken](get-started-azure.md).

> [!NOTE]
> Microsoft Intune’un önceki bir sürümünü kullandıysanız aşağıdaki bilgiler işinize yarayabilir:
> * [Özelliklerim Azure’da nereye gitti?](ui-changes.md) size, Azure’a taşınma sonucu değişmiş olan iş akışları ve kullanıcı arabirimlerini gösteren bir başvurudur.
> * [Azure portalında klasik Intune grupları](groups-get-started.md), grup yönetimi için Azure Active Directory güvenlik gruplarına geçmiş olmanın olası sonuçlarını açıklar.

### <a name="before-you-start"></a>Başlamadan önce

Azure Portal’da Intune’u kullanmak için, bir Intune yönetici ve kiracı hesabınız olmalıdır. Hesabınız yoksa [bir hesap için kaydolun](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

### <a name="supported-web-browsers-for-the-azure-portal"></a>Azure Portal için desteklenen web tarayıcıları

Azure Portal, modern PC ve Mac bilgisayarlarla tabletlerin çoğunda çalışır. Cep telefonları desteklenmez.
Şu anda, aşağıdaki web tarayıcıları desteklenmektedir:

- Microsoft Edge (en son sürüm)
- Microsoft Internet Explorer 11
- Safari (en so sürüm, yalnızca Mac)
- Chrome (en son sürüm)
- Firefox (en son sürüm)

Desteklenen tarayıcılar hakkındaki en son bilgiler için [Azure portalını](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) kontrol edin.

## <a name="next-steps"></a>Sonraki adımlar
* [Intune’u kullanmanın yaygın yolları](common-scenarios.md) hakkında yazılanları okuyun.
* [30 günlük Intune denemesini](free-trial-sign-up.md) kullanarak ürünle tanışın.
* Intune’un [teknik gereksinimlerini ve özelliklerini](supported-devices-browsers.md) derinlemesine öğrenin.
