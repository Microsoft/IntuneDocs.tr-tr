---
title: Microsoft Intune nedir?
description: "Intune’un nasıl Enterprise Mobility + Security çözümünün mobil cihaz yönetim bileşeni olduğu ve şirket verilerinizi korumanıza nasıl yardım ettiği hakkında bilgi edinin."
keywords: Intune nedir?
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: 
ms.openlocfilehash: 53115eba5e5150139b8ff0f359cde279df297d47
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2017
---
# <a name="what-is-intune"></a>Intune nedir?

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune, çalışanlarınızın üretken olmasını sağlarken kurumsal verilerinizin korunmasına yardımcı olan bulut tabanlı bir kurumsal mobilite yönetim (EMM) hizmetidir. Intune ile şunları yapabilirsiniz:
* Çalışanlarınızın şirket verilerine erişmek için kullandığı mobil cihazları yönetebilirsiniz.
* Çalışanlarınızın kullandığı mobil uygulamaları yönetebilirsiniz.
* Çalışanlarınızın erişim ve paylaşım yöntemlerinin denetlenmesine yardımcı olarak şirket bilgilerinizi koruyabilirsiniz.
* Cihazların ve uygulamaların şirket güvenlik gereksinimlerine uygun olduğundan emin olabilirsiniz.

Intune, kimlik ve erişim denetimi için Azure Active Directory (Azure AD), veri koruma için ise Azure Information Protection ile yakın bir tümleştirmede çalışır.

Office 365 ve EMS birlikte çalışanlarınıza tüm cihazlardan üretken bir şekilde çalışma olanağı tanırken kuruluşunuzun bilgilerini de koruma altına alır. Office 365 ve EMS üretkenlik, kimlik, erişim denetimi, yönetim ve veri koruması özelliklerini içeren tam bir tümleşik kurumsal mobil çalışma paketidir. Kuruluşunuzda mobil çalışma çözümünü dağıtmak ve çalıştırmak için etkili bir yol sağlar.

## <a name="how-does-intune-work"></a>Intune nasıl çalışır?
Intune, mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) hizmetlerini sunar. Intune'un MDM ve MAM özellikleri, EMS veri koruma ve uyumluluk senaryolarına katkıda bulunur.  

Intune'un MDM/MAM özelliklerini ve EMS veri koruma hizmetlerini kullanma şekliniz, [çözmeye çalıştığınız işletme sorununa](#common-business-problems-that-intune-helps-solve) bağlıdır. Örneğin:
* Bir perakende satış mağazasındaki vardiyalı çalışanlar tarafından kullanılacak tek uygulama çalıştıran cihazlarla bir havuz oluşturuyorsanız, ağırlıklı olarak MDM'yi kullanırsınız.
* Çalışanların kurumsal verilere erişmek için kendi kişisel cihazlarını kullanmalarına (KCG) izin veriyorsanız MAM ve veri koruma hizmetlerinden yararlanırsınız.  
* Bilgi işlem çalışanlarına şirket telefonu veriyorsanız, tüm teknolojileri bir arada kullanırsınız.

## <a name="intune-mobile-device-management-mdm-explained"></a>Intune mobil cihaz yönetimi (MDM) açıklaması
MDM, mobil işletim sistemlerindeki protokollerden veya API'lerden faydalanır. Hizmet, şunun gibi görevleri içerir:
* BT departmanının kurumsal hizmetlere erişen cihazların listesine sahip olması için cihazları yönetime kaydetme
* Cihazları şirket güvenlik ve sistem durumu standartlarına uyacak şekilde yapılandırma
* Kurumsal hizmetlere erişim sağlamak için sertifikaları ve Wi-Fi/VPN profillerini sunma
* Cihazların kurumsal standartlar açısından uyumluluk durumunu ölçme ve raporlama
* Yönetilen cihazlardaki kurumsal verileri kaldırma  

Bazen **kurumsal veriler için erişim denetiminin** MDM özelliği olduğu düşünülür. Bu hizmet, mobil işletim sistemleri tarafından sunulan bir özellik olmadığı için biz bu şekilde sınıflandırmıyoruz. Bu hizmet, kimlik sağlayıcı tarafından sunulmaktadır. Burada kimlik sağlayıcı, Microsoft'un kimlik ve erişim yönetim sistemi olan Azure Active Directory (Azure AD) olacaktır.  

Intune, Azure AD ile birlikte geniş bir erişim denetim senaryosu kümesi sunar. Örneğin, bir mobil cihazın Exchange gibi kurumsal bir hizmete erişebilmesi için Intune'da tanımlanan kurumsal standartlara uygun olması şartını koyabilirsiniz. Benzer şekilde kurumsal hizmeti belirli bir mobil uygulama kümesiyle sınırlandırabilirsiniz. Örnek olarak, Exchange Online'a yalnızca Outlook veya Outlook Mobile ile erişilmesini sağlayabilirsiniz.

## <a name="intune-mobile-app-management-mam-explained"></a>Intune mobil uygulama yönetimi (MAM) açıklaması
MAM hizmetinde, çözümlerimizin BT uzmanlarının mobil uygulamalarla ilgili gerçekleştirmesini sağladığı aşağıdakilere benzer işlemler söz konusudur:
* Çalışanlar için mobil uygulama yayımlama
* Uygulamaları yapılandırma
* Kurumsal verilerin mobil uygulamalarda kullanım ve paylaşım şekillerini denetleme
* Mobil uygulamalardaki kurumsal verileri kaldırma   
* Mobil uygulamaları güncelleştirme
* Mobil uygulama envanter raporlarını alma
* Mobil uygulama kullanımını izleme

MAM teriminin bu işlevlerden herhangi biri veya birden fazlasının birlikte kullanıldığı senaryolar için kullanıldığına şahit olduk. Uygulama yapılandırma kavramının ([iOS'ta yönetilen uygulama yapılandırılması](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html) gibi teknolojileri kullanarak) mobil uygulamalar içindeki kurumsal verilerin güvenliğinin sağlanması kavramıyla bir arada kullanılması sık karşılaşılan bir durumdur. Bunun nedeni, bazı mobil uygulamalarda veri güvenliği özelliklerinin yapılandırılmasını sağlayan ayarların yer almasıdır.

Bu özelliklerin işletim sistemi veri koruma özellikleriyle (örneğin, Windows 10'daki Windows Bilgi Koruması gibi MDM özellikleri) birlikte kullanılması, mobil cihazlar için çok geniş veri koruma seçenekleri sunmaktadır.

Intune'u diğer EMS hizmetleriyle birlikte kullanarak kuruluşunuz için mobil işletim sistemi ve uygulama yapılandırması yoluyla mobil uygulamalar tarafından sunulandan daha fazla mobil uygulama güvenliği seçeneğine sahip olabilirsiniz. EMS üzerinden yönetilen uygulamalar, aşağıdakiler de dahil olmak üzere daha fazla mobil uygulama ve veri koruma özelliğine sahip olur:

* [Çoklu oturum açma](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Çok faktörlü kimlik doğrulaması](https://docs.microsoft.com/multi-factor-authentication/multi-factor-authentication)
* [Uygulamaya koşullu erişim - mobil uygulamada kurumsal veriler varsa erişim izni ver](app-based-conditional-access-intune.md)
* [Aynı uygulamadaki kurumsal verileri kişisel verilerden ayırma](app-protection-policy.md)
* [Uygulama koruma ilkesi (PIN, şifreleme, farklı kaydet, pano vs.)](app-protection-policies.md)
* [Mobil uygulamadan kurumsal verileri silme](apps-selective-wipe.md)
* [Hak yönetim desteği](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Uygulama yönetimi veri güvenliği düzeylerini gösteren görüntü](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Intune mobil uygulama güvenliği
Uygulama güvenliğini sağlama, MAM hizmetlerinden biridir. Intune'da mobil uygulama güvenliği şu anlamları taşır:
* Kişisel bilgileri kurumsal BT farkındalığından ayırma
* Kullanıcıların kurumsal bilgilerle gerçekleştirebilecekleri eylemleri (kopyala, kes/yapıştır, kaydet ve görüntüle gibi) sınırlama
* Mobil uygulamalardaki kurumsal verileri kaldırma (seçmeli silme veya kurumsal verileri silme olarak da bilinir)

Intune'un mobil uygulama güvenliği için sunduğu yöntemlerden biri, **uygulama koruma ilkesi** özelliğidir. Uygulama koruma ilkesi, kurumsal verileri kişisel verilerden ayırmak için Azure AD kimliğini kullanır. Kurumsal kimlik bilgileri kullanılarak erişilen veriler için ek kurumsal koruma önlemleri alınır.

Kullanıcı, cihazında kurumsal kimlik bilgileriyle oturum açtığında kişisel kimlik bilgileriyle erişemediği kurumsal verilere erişebilir. Kurumsal verilerin kullanılması sırasında Intune ve diğer EMS teknolojileri, verilerin kaydedilme ve paylaşılma şeklini denetler. Bu koruma özellikleri, kullanıcı cihazında kişisel kimlik bilgileriyle oturum açtığında eriştiği verilere uygulanmaz. Bu sayede BT departmanı kurumsal verilerin denetimini sağlarken kullanıcı da kişisel verilerinin denetimini ve gizliliğini denetlemiş olur.

## <a name="emm-with-and-without-device-enrollment"></a>Cihaz kaydı ile ve cihaz kaydı olmadan EMM
Kurumsal mobilite yönetimi çözümlerinin çoğu, temel mobil cihaz ve mobil uygulama teknolojilerini destekler. Bunlar genelde cihazın kuruluşunuzun MDM çözümüne kaydedilmesini gerektirir. Intune bu senaryolara ek olarak birçok "kayıt olmadan" senaryosunu da destekler.  

Kuruluşların "kayıt olmadan" senaryolarını kullanma şekli değişiklik gösterir. Bazı kuruluşlarda standarttır. Bazıları ise kişisel tablet gibi yardımcı cihazlar için izin verir. Diğerleri ise hiç desteklemez. Tüm çalışan cihazlarının MDM sistemine kaydedilmesini gerektiren kuruluşlar dahi genelde "kayıt olmadan" senaryolarını yükleniciler, satıcılar ve özel duruma sahip diğer cihazlar için destekler.

Intune'un "kayıt olmadan" teknolojisini sisteme kaydolan cihazlarda da kullanabilirsiniz. Örneğin, MDM sistemine kayıtlı bir cihazda mobil işletim sistemi tarafından sunulan birlikte açma koruması bulunabilir. (Open-in protection, Outlook gibi bir uygulamadan Word gibi başka bir uygulamaya belge açmanızı her iki uygulama da MDM sağlayıcısı tarafından yönetilmediği durumlarda kısıtlayan bir iOS özelliğidir.) Ayrıca, BT departmanı EMS tarafından yönetilen mobil uygulamalara, uygulama koruma ilkesi uygulayarak farklı kaydetme işlevini denetleyebilir veya çok faktörlü kimlik doğrulaması özelliği ekleyebilir.

Kuruluşunuzun kayıtlı ve kayıtsız mobil cihazlar ve uygulamalarla ilgili pozisyonu ne olursa olsun, EMS'nin bir parçası olan Intune'da çalışanlarınızın üretkenliğini artırmaya yardımcı olarak kurumsal verilerinizi korumanızı sağlayarak araçlar mevcuttur.

## <a name="common-business-problems-that-intune-helps-solve"></a>Intune'un çözmenize yardımcı olduğu yaygın iş sorunları
Aşağıdaki listede yer alan iş sorunlarına tıklayarak sunduğumuz çözümler hakkında daha fazla bilgi alabilirsiniz. Yalnızca son maddenin çözümü MDM kaydı gerektirmektedir:

* [Şirket içi e-postalarınızı ve verilerinizi koruyarak mobil cihazların bunlara erişmesini sağlama](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Office 365 e-postalarınızı ve verilerinizi koruyarak mobil cihazların bunlara güvenle erişmesini sağlama](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Çalışanlarınıza şirketin sahip olduğu telefonları verme](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Tüm çalışanlara kendi cihazını getir (KCG) veya kişisel cihaz programı sunma](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Çalışanlarınızın yönetilmeyen genel bir bilgi noktasından Office 365'e güvenle erişmesini sağlama](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Görevlerde çalışanlarınıza sınırlı kullanımı olan paylaşılan tabletler verme](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)

### <a name="next-steps"></a>Sonraki adımlar
* [Intune’u kullanmanın yaygın yolları](common-scenarios.md) hakkında yazılanları okuyun.
* [30 günlük Intune denemesini](free-trial-sign-up.md) kullanarak ürünle tanışın.
* Intune’un [teknik gereksinimlerini ve özelliklerini](supported-devices-browsers.md) derinlemesine öğrenin.
