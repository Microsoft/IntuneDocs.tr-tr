---
title: Microsoft Intune’u kullanmanın yaygın yolları
description: Microsoft Intune’un yönetimde size yardımcı olabileceği en yaygın altı görev hakkında bilgi edinin.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/29/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: d158cb01dbd13f032916f4dc2bf443ed0f6bfaae
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "71238577"
---
# <a name="common-ways-to-use-microsoft-intune"></a>Microsoft Intune’u kullanmanın yaygın yolları

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Uygulama görevlerine girmeden önce, şirketinizin kurumsal taşınabilirlik katılımcıları, Intune 'U kullanarak iş hedeflerine göre hizalanmanız önemlidir. Paydaş hizalaması, kurumsal hareketliliğin yeni mi yoksa başka bir üründen geçiş mi olduğunu önemli bir öneme sahiptir.  

Kurumsal mobil çalışma konusundaki gereksinimleri dinamik olarak artmaktadır ve Microsoft’un bu gereksinimlerini karşılamaya yönelik yaklaşımları pazardaki diğer çözümlerden farklı olabilir. İş hedefleri çerçevesinde uyumlu bir noktaya gelmenin en iyi yolu, çalışanlarınız, iş ortaklarınız ve BT departmanınıza olanak sağlamak istediğiniz senaryolar açısından hedeflerinizi ortaya koymaktır.  

Aşağıda, Intune’a dayalı en yaygın altı senaryoya kısa giriş bilgileri ve her birinin planlanması ve dağıtımıyla ilgili daha fazla bilgiye ulaştıran bağlantılar verilmiştir.

>[!NOTE]
>Microsoft mobil cihazlarından şirket kaynaklarına erişmesine olanak tanırken şirket verilerinin de güvenliğini korumak için Microsoft BT’sinin Intune’u nasıl kullandığını bilmek ister misiniz? Microsoft BT’sinin Intune’u ve diğer hizmetleri kullanarak kimlikleri, cihazları, uygulamaları ve verileri nasıl yönettiğini ayrıntılarıyla görmek için [bu teknik olay incelemesini okuyun](https://www.microsoft.com/itshowcase/Article/Content/588).  

>[!IMPORTANT]
>iOS cihazlar için geçtiğimiz günlerde ortaya çıkan “Trident” kötü amaçlı yazılım saldırılarından sonra mobil cihazların güncel olduğundan emin olmak istiyoruz. Bu nedenle [Microsoft Intune kullanarak mobil cihazların güncel kalmasını sağlama](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) konulu bir blog gönderisi yayımladık. Bu gönderide Intune’un, cihazlarınızın güvenli ve güncel kalmasına yardımcı olmak için sunduğu farklı yöntemlerle ilgili bilgilere yer verilmiştir.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Şirket içi e-postanızı ve verilerinizi koruyarak mobil cihazların bunlara güvenle erişmesini sağlama
Kurumsal mobil çalışma stratejilerinin çoğu çalışanların internete bağlanan mobil cihazlarıyla e-postaya güvenli erişimini sağlama planıyla başlar. Birçok kuruluşun hala kurumsal ağlarında barındırdıkları Microsoft Exchange gibi şirket içi veri ve uygulama sunucuları vardır.


Intune ve Microsoft Enterprise Mobility + Security (EMS), Exchange Server için benzersiz bir şekilde tümleştirilmiş [koşullu erişim çözümü](conditional-access.md) sağlar ve bu cihaz Intune 'a kaydedilinceye kadar hiçbir mobil uygulamanın e-postaya erişememesini sağlar. Şirket ağınızın kenarına başka bir ağ geçidi makinesi dağıtmadan bu tür bir e-posta erişimini uygulayabilirsiniz.

Intune bir iş kolu uygulama sunucusu gibi şirket içi verilere güvenli erişim gerektiren mobil uygulamalara erişim sağlamayı da destekler. Bu erişim türü genel olarak, erişim denetimi için [Intune tarafından yönetilen sertifikaları](certificates-configure.md) çevredeki standart bir VPN ağ geçidi veya ara sunucusuyla, örneğin Microsoft Azure Active Directory Uygulama Ara Sunucusu’yla birlikte kullanarak gerçekleştirilir. 

Böyle durumlarda, şirket verilerine erişmenin tek yolu cihazı yönetime kaydetmektir. Yönetim sistemi, kaydedilen cihazların şirket verilerine erişmeden önce ilkelerinizle uyumlu olmasını sağlar. Buna ek olarak, erişilen verilerin iş kolu uygulamanız içinde tutulmasına ve böylelikle şirket verilerinin tüketici uygulamalarına veya hizmetlerine geçirilememesine yardımcı olmak için Intune’un [Uygulama Kaydırma Aracı ve Uygulama SDK’sı](apps-prepare-mobile-application-management.md) kullanılabilir.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Office 365 e-postanızı ve verilerinizi koruyarak mobil cihazların bunlara güvenle erişmesini sağlama
Office 365’teki şirket verilerinin (e-posta, belgeler, anlık iletiler, kişiler) korunması sizin için bundan kolay ve kullanıcılarınız için bundan rahat olamazdı.

Intune ve Microsoft Enterprise Mobility + Security, şirketinizin uyumluluk gereksinimlerini karşılamayan hiçbir kullanıcının, uygulamanın veya cihazın Office 365 verilerine erişememesini sağlayan benzersiz bir şekilde tümleştirilmiş koşullu erişim çözümü sağlar ( [ ](multi-factor-authentication.md)yönetilen uygulama, desteklenen işletim sistemi sürümü, cihaz pin 'i, düşük Kullanıcı riski profili, vb. kullanarak Intune 'a kayıtlı Multi-Factor Authentication.


Uygulama mağazalarındaki Office mobil uygulamaları, Intune üzerinden yapılandırabileceğiniz veri kapsama ilkelerine sahiptir. Bu özellikler, BT tarafından yönetilmeyen uygulamalarla (yerel e-posta uygulaması gibi) ve depolama konumlarıyla (Dropbox gibi) veri paylaşılmasını engellemenizi sağlar. Bu işlevsellik tümüyle Office 365 ve EMS’de yerleşik olarak bulunur. Bu değerli işlevselliği elde etmek için ek altyapı dağıtımı yapmanız gerekmez.

Yaygın bir Office 365 dağıtım uygulaması, şirkete ait cihazlardaki yaygın bir senaryo olarak şirket uygulamaları, sertifikalar, Wi-Fi veya VPN yapılandırmaları ile tam olarak ayarlanması gereken cihazların yönetime kaydolmalarını gerektirmektir.  


Ancak, yalnızca kişisel cihazlarda olduğu gibi, kullanıcının yalnızca şirket e-postasına ve belgelerine erişmesi gerekiyorsa, kullanıcının Office mobil uygulamalarını ( [Uygulama koruma ilkelerini](app-protection-policies.md) uyguladığınız ve kaydetmeyi atlayan) kullanmasını zorunlu kılabilirsiniz Cihaz tamamen.  



Her iki yöntemde de, Office 365 verilerinin güvenliği sizin tanımladığınız ilkelerle sağlanır.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>Tüm çalışanlara kendi cihazını getir programı sunma
Donanım harcamalarını azaltmaya veya çalışanlar için mobil üretkenlik seçeneklerini artırmaya yönelik bir araç olarak kuruluşlar arasında kendi cihazını getir (KCG) modelinin popülerliği artmaya devam etmektedir. Bugünlerde artık hemen herkesin kişisel telefonu olduğuna göre, ceplerine bir telefon daha koymanın ne anlamı var? Bu yöntemde her zaman en önemli güçlük kişisel cihazlarını yönetime kaydetmeleri için çalışanları ikna etmektir çünkü BT bölümlerinin cihazlarında görebileceği ve yapabileceği şeylerden çekinirler.  

Cihaz kaydının uygulanabilir bir seçenek olmadığı durumlarda, Intune alternatif bir KCG yaklaşımı olarak [şirket verilerini içeren uygulamaları yönetme](app-protection-policies.md) yaklaşımını sunar. Intune, Office mobil uygulamalarında olduğu gibi söz konusu uygulamanın hem şirket verilerine hem de kişisel verilere eriştiği durumlarda bile şirket verilerini korur.  

Bir yönetici olarak, kullanıcıların Office mobil uygulamalarına Office 365’ten erişmelerini ve uygulamaları, verileri koruma altına alan (şifreleme, pin ile koruma vs.) ilkelerle yapılandırmalarını zorunlu tutabilirsiniz. Bu uygulama koruma ilkeleri, yönetilmeyen uygulamalardan ve bu uygulamaların içindeki ve dışındaki depolama konumlarından veri kaybetmeyi önler. Örneğin, ilkeler kullanıcın şirket e-posta profilinden tüketici e-posta profiline (her iki profil de Outlook Mobile içinde yapılandırılmış olsa bile) metin kopyalamasını önler. KCG kullanıcılarınıza gereken diğer hizmetler ve uygulamalar için de benzer yapılandırmalar dağıtılabilir.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-employees"></a>Çalışanlarınıza şirketin sahip olduğu telefonları verme
Bugünlerde çalışanların çoğu mobil çalıştığı için rekabet üstünlüğü açısından mobil cihazlarda üretkenlik sağlamak bir zorunluluktur. Bu çalışanların her zaman, gittikleri her yerde şirket uygulamalarına ve verilerine rahatça erişebilmeleri gerekir. Şirket verilerinin güvenli ve yönetim maliyetlerinin düşük olmasını sağlamalısınız.  

Intune, Apple Aygıt Kayıt Programı ve Samsung KNOX mobil güvenlik platformu dahil olmak üzere bugün pazardaki ana kurumsal cihaz yönetimi platformlarıyla tümleştirilmiş [toplu sağlama ve yönetim çözümleri](device-enrollment.md) sunar. Intune’la merkezi cihaz yapılandırmaları yazma özelliği, şirket cihazlarının sağlanmasını üst düzeyde otomatik bir işlem haline getirmeye yardımcı olur.  

Şunu düşünün: çalışana açılmamış bir iPhone kutusu veriyorsunuz. Çalışan iPhone’u çalıştırıyor kendi kimliğini doğrulamasını gerektiren şirket markalı bir kurulum akışında ilerliyor. iPhone, [güvenlik ilkeleri](device-profiles.md) ile sorunsuz bir şekilde yapılandırılıyor.

Ardından, çalışan kendine sağlanan isteğe bağlı şirket uygulamalarına erişmek için Intune Şirket Portalı uygulamasını başlatıyor.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-employees"></a>Çalışanlarınıza sınırlı kullanımı olan paylaşılan tabletler verme
Çalışanlar, mobil teknolojileri giderek daha fazla kullanmaktadır. Örneğin, paylaşılan tabletler mağaza çalışanları tarafından sıklıkla kullanılmaktadır.  İster satışı işlemek ister anında stok kontrolü yapmak için kullanılsın, tabletler harika müşteri etkileşimlerine yardımcı olur.

Bu örnekte, kullanıcı deneyiminin basitliği kritik önem taşır. Bu nedenle, tabletler genellikle çalışanlara sınırlı kullanım modunda sağlanır. bu şekilde, tek bir iş kolu uygulaması çalışanın etkileşime girebileceği tek şeydir. Intune, bu sınırlı kullanım modunda çalışacak şekilde yapılandırılabilecek bu paylaşılan [iOS ve Android](device-profiles.md) cihazlarını toplu olarak sağlamanıza, korumanıza ve merkezi olarak yönetmenize olanak sağlar.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Çalışanlarınızın yönetilmeyen genel bir bilgi noktasından Office 365’e güvenle erişmesini sağlama
Bazen çalışanlarınızın sergi alanlarında ve otel lobilerindeki genel kullanıma açık bilgisayarlar gibi yönetemediğiniz cihazları, uygulamaları veya tarayıcıları kullanması gerekebilir.

Çalışanlarınızın buralardan şirket e-postasına erişmesine izin vermeli misiniz? Intune ve Microsoft Enterprise Mobility + Security ile, yanıt yalnızca "Hayır" olabilir ve [e-posta erişimini kuruluşunuz tarafından yönetilen cihazlarla sınırlandırırsınız](conditional-access.md). Bu, kimliği sağlam bir şekilde doğrulanmış çalışanınızın güvenilmeyen bir bilgisayara şirket verileri bırakmamasını güvence altına alır.
