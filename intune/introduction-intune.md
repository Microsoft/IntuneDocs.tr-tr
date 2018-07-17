---
title: Microsoft Intune nedir?
description: Intune’un nasıl Enterprise Mobility + Security çözümünün mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) bileşeni olduğu ve şirket verilerinizi korumanıza nasıl yardım ettiği hakkında bilgi edinin.
keywords: Intune nedir?
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/01/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: ''
ms.openlocfilehash: 6f92cb350a69aeb600f1d48e9bdb0b22a623cb52
ms.sourcegitcommit: 2198a39ae48beca5fc74316976bc3fc9db363659
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38224815"
---
# <a name="what-is-intune"></a>Intune nedir?

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Intune, çalışanlarınızın üretken olmasını sağlarken kurumsal verilerinizin korunmasına yardımcı olan bulut tabanlı bir kurumsal mobilite yönetim (EMM) hizmetidir. Intune ile şunları yapabilirsiniz:
* Çalışanlarınızın şirket verilerine erişmek için kullandığı mobil cihazları yönetebilirsiniz.
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
Intune, Enterprise Mobility + Security’nin (EMS) mobil cihaz ve uygulamaları yöneten bileşenidir. Kimlik ve erişim denetimi için Azure Active Directory (Azure AD) gibi diğer EMS bileşenleriyle, veri koruma için ise Azure Information Protection ile tümleşir. Office 365 ile birlikte kullanıldığında, çalışanlarınıza tüm cihazlardan üretken bir şekilde çalışma olanağı tanırken kuruluşunuzun bilgilerini de koruma altına alır.

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

Bazen **kurumsal veriler için erişim denetiminin** bir cihaz yönetimi özelliği olduğu düşünülür. Bu hizmet, mobil işletim sistemleri tarafından sunulan bir özellik olmadığı için biz bu şekilde sınıflandırmıyoruz. Bu hizmet, kimlik sağlayıcı tarafından sunulmaktadır. Burada kimlik sağlayıcı, Microsoft'un kimlik ve erişim yönetim sistemi olan Azure Active Directory (Azure AD) olacaktır.  

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

Mobil uygulama yönetimi (MAM) teriminin bu işlevlerden herhangi birinin veya birkaçının birlikte kullanıldığı senaryolar için kullanıldığına şahit olduk. Özellikle uygulama yapılandırma kavramının mobil uygulamalar içindeki kurumsal verilerin güvenliğinin sağlanması kavramıyla bir arada kullanılması sık karşılaşılan bir durumdur. Bunun nedeni, bazı mobil uygulamalarda veri güvenliği özelliklerinin yapılandırılmasını sağlayan ayarların yer almasıdır.

Uygulama yapılandırma ve Intune dediğimizde, özel olarak [iOS’ta yönetilen uygulama yapılandırması](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html) gibi teknolojilerden bahsediyoruz.

Intune'u diğer EMS hizmetleriyle birlikte kullanarak kuruluşunuz için mobil işletim sistemi ve uygulama yapılandırması yoluyla mobil uygulamalar tarafından sunulandan daha fazla mobil uygulama güvenliği seçeneğine sahip olabilirsiniz. EMS üzerinden yönetilen uygulamalar, aşağıdakiler de dahil olmak üzere daha fazla mobil uygulama ve veri koruma özelliğine sahip olur:

* [Çoklu oturum açma](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Çok faktörlü kimlik doğrulaması](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication)
* [Uygulamaya koşullu erişim - mobil uygulamada kurumsal veriler varsa erişim izni ver](app-based-conditional-access-intune.md)
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

Intune'un mobil uygulama güvenliği için sunduğu yöntemlerden biri, **uygulama koruma ilkesi** özelliğidir. Uygulama koruma ilkesi, kurumsal verileri kişisel verilerden ayırmak için Azure AD kimliğini kullanır. Kurumsal kimlik bilgileri kullanılarak erişilen veriler için ek kurumsal koruma önlemleri alınır.

Örneğin kullanıcı, cihazında kurumsal kimlik bilgileriyle oturum açtığında kişisel kimlik bilgileriyle erişemediği kurumsal verilere erişebilir. Bu şirket verileri kullanıldıkça, uygulama koruma ilkeleri bunların nasıl kaydedildiği ve paylaşıldığını denetler. Bu koruma özellikleri, kullanıcı cihazında kişisel kimlik bilgileriyle oturum açtığında eriştiği verilere uygulanmaz. Bu sayede BT departmanı kurumsal verilerin denetimini sağlarken kullanıcı da kişisel verilerinin denetimini ve gizliliğini denetlemiş olur.

## <a name="emm-with-and-without-device-enrollment"></a>Cihaz kaydı ile ve cihaz kaydı olmadan EMM
Kurumsal mobilite yönetimi çözümlerinin çoğu, temel mobil cihaz ve mobil uygulama teknolojilerini destekler. Bunlar genelde cihazın kuruluşunuzun mobil cihaz yönetimi (MDM) çözümüne kaydedilmesini gerektirir. Intune bu senaryolara ek olarak birçok "kayıt olmadan" senaryosunu da destekler.  

Kuruluşların "kayıt olmadan" senaryolarını kullanma şekli değişiklik gösterir. Bazı kuruluşlarda standarttır. Bazıları ise kişisel tablet gibi yardımcı cihazlar için izin verir. Diğerleri ise hiç desteklemez. Tüm çalışan cihazlarının MDM sistemine kaydedilmesini gerektiren kuruluşlar bile genelde “kayıt olmadan” senaryolarını yükleniciler, satıcılar ve özel duruma sahip diğer cihazlar için destekler.

Intune'un "kayıt olmadan" teknolojisini sisteme kaydolan cihazlarda da kullanabilirsiniz. Örneğin, MDM sistemine kayıtlı bir cihazda mobil işletim sistemi tarafından sunulan “birlikte açma” koruması bulunabilir. “Birlikte açma” koruması, Outlook gibi bir uygulamadan Word gibi başka bir uygulamaya belge açmanızı her iki uygulama da MDM sağlayıcısı tarafından yönetilmediği durumlarda kısıtlayan bir iOS özelliğidir. Ayrıca, BT departmanı EMS tarafından yönetilen mobil uygulamalara, uygulama koruma ilkesi uygulayarak farklı kaydetme işlevini denetleyebilir veya çok faktörlü kimlik doğrulaması özelliği ekleyebilir.

Kuruluşunuzun kayıtlı ve kayıtsız mobil cihazlar ve uygulamalarla ilgili pozisyonu ne olursa olsun, EMS'nin bir parçası olan Intune'da çalışanlarınızın üretkenliğini artırmaya yardımcı olarak kurumsal verilerinizi korumanızı sağlayarak araçlar mevcuttur.



### <a name="next-steps"></a>Sonraki adımlar
* [Intune’u kullanmanın yaygın yolları](common-scenarios.md) hakkında yazılanları okuyun.
* [30 günlük Intune denemesini](free-trial-sign-up.md) kullanarak ürünle tanışın.
* Intune’un [teknik gereksinimlerini ve özelliklerini](supported-devices-browsers.md) derinlemesine öğrenin.
