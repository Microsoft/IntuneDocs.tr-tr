---
title: "Intune’u kullanmanın yaygın yolları | Microsoft Docs"
description: "Intune’un yardımcı olduğu en yaygın altı görevi listeler"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6a20136e078edd2b4b82cdd8abe9cfe4968ca703
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="common-ways-to-use-intune"></a>Intune'u kullanmanın yaygın yolları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Uygulama görevleri konusuna girmeden önce, şirketinizde kurumsal mobil çalışmayla ilgilenen katılımcıları iş hedefleri çerçevesinde uyumlu bir noktaya getirmek önemlidir.  Kurumsal mobil çalışmaya yenim mi başladığınız yoksa başka bir üründen geçiş mi yaptığınız da önemlidir.  

Kurumsal mobil çalışma konusundaki gereksinimleri dinamik olarak artmaktadır ve Microsoft’un bu gereksinimlerini karşılamaya yönelik yaklaşımları pazardaki diğer çözümlerden farklı olabilir. İş hedefleri çerçevesinde uyumlu bir noktaya gelmenin en iyi yolu, çalışanlarınız, iş ortaklarınız ve BT departmanınıza olanak sağlamak istediğiniz senaryolar açısından hedeflerinizi ortaya koymaktır.  

Aşağıda, Intune’a dayalı en yaygın altı senaryoya kısa giriş bilgileri ve her birinin planlanması ve dağıtımıyla ilgili daha fazla bilgiye ulaştıran bağlantılar verilmiştir.

>[!NOTE]
>Microsoft mobil cihazlarından şirket kaynaklarına erişmesine olanak tanırken şirket verilerinin de güvenliğini korumak için Microsoft BT’sinin Intune’u nasıl kullandığını bilmek ister misiniz? Microsoft BT’sinin Intune’u ve diğer hizmetleri kullanarak kimlikleri, cihazları, uygulamaları ve verileri nasıl yönettiğini ayrıntılarıyla görmek için [bu teknik olay incelemesini okuyun](https://www.microsoft.com/itshowcase/Article/Content/588).  

>[!IMPORTANT]
>iOS cihazlar için geçtiğimiz günlerde ortaya çıkan "Trident" kötü amaçlı yazılım saldırılarından sonra mobil cihazların güncel olduğundan emin olmak istiyoruz. Bu nedenle [Microsoft Intune kullanarak mobil cihazların güncel kalmasını sağlama](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) konulu bir blog gönderisi yayımladık. Bu gönderide Intune'un, cihazlarınızın güvenli ve güncel kalmasına yardımcı olmak için sunduğu farklı yöntemlerle ilgili bilgilere yer verilmiştir.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Şirket içi e-postanızı ve verilerinizi koruyarak mobil cihazların bunlara güvenle erişmesini sağlama
Kurumsal mobil çalışma stratejilerinin çoğu çalışanların internete bağlanan mobil cihazlarıyla e-postaya güvenli erişimini sağlama planıyla başlar. Birçok kuruluşun hala kurumsal ağlarında barındırdıkları Microsoft Exchange gibi şirket içi veri ve uygulama sunucuları vardır.

Cihaz Intune ile kaydedilmediği sürece hiçbir mobil uygulamanın e-postaya erişememesini sağlayan Exchange Server için Intune ve Microsoft Enterprise Mobility + Security /intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune). Bunu, kurumsal ağınızın en önüne başka bir ağ geçidi makinesi daha dağıtmak zorunda kalmadan yapabilirsiniz!

Intune bir iş kolu uygulama sunucusu gibi şirket içi verilere güvenli erişim gerektiren mobil uygulamalara erişim sağlamayı da destekler. Bu tipik olarak, erişim denetimi için [Intune tarafından yönetilen sertifikaları](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) çevredeki standart bir VPN ağ geçidi veya ara sunucusuyla, örneğin Microsoft Azure Active Directory Uygulama Ara Sunucusu’yla birlikte kullanarak gerçekleştirilir.  

Böyle durumlarda, şirket verilerine erişmenin tek yolu cihazı yönetime kaydetmektir. Yönetim sistemi, kaydedilen cihazların şirket verilerine erişmeden önce ilkelerinizle uyumlu olmasını sağlar.  Buna ek olarak, erişilen verilerin iş kolu uygulamanız içinde tutulmasına ve böylelikle şirket verilerinin tüketici uygulamalarına veya hizmetlerine geçirilememesine yardımcı olmak için Intune’un [Uygulama Kaydırma Aracı ve Uygulama SDK’sı](/intune-classic/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) kullanılabilir.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->


## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Office 365 e-postanızı ve verilerinizi koruyarak mobil cihazların bunlara güvenle erişmesini sağlama
Office 365’teki şirket verilerinin (e-posta, belgeler, anlık iletiler, kişiler) korunması sizin için bundan kolay ve kullanıcılarınız için bundan rahat olamazdı.

Intune ve Microsoft Enterprise Mobility + Security’nin sağladığı benzersiz bir şekilde tümleştirilmiş koşullu erişim çözümüyle, şirketinizin uyumluluk gereksinimlerini /intune-classic/deploy-use/protect-windows-devices-with-multi-factor-authentication), Intune’a kaydolma, yönetilen uygulama kullanma, desteklenen işletim sistemi sürümü, cihaz pin’i, düşük riskli kullanıcı profili vb.) karşılamayan hiçbir kullanıcının, uygulamanın veya cihazın Office 365 verilerine erişememesi güvence altına alınır.

Uygulama mağazalarındaki Office mobil uygulamaları, Intune üzerinden yapılandırabileceğiniz veri kapsama ilkelerine sahiptir. Bu özellikler, BT tarafından yönetilmeyen uygulamalarla (yerel e-posta uygulaması gibi) ve depolama konumlarıyla (Dropbox gibi) veri paylaşılmasını engellemenizi sağlar. Bu işlevsellik tümüyle Office 365 ve EMS’de yerleşik olarak bulunur. Bu değerli işlevselliği elde etmek için ek altyapı dağıtımı yapmanız gerekmez.

Yaygın bir Office 365 dağıtım uygulaması, şirkete ait cihazlardaki yaygın bir senaryo olarak şirket uygulamaları, sertifikalar, Wi-Fi veya VPN yapılandırmaları ile tam olarak ayarlanması gereken cihazların yönetime kaydolmalarını gerektirmektir.  

Ancak kişilere ait cihazlarda çoğunlukla olduğu gibi, kullanıcının yalnızca şirket e-postasına ve belgelerine erişmesi gerekiyorsa kullanıcının Office mobil uygulamalarını /intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune)) kullanmalarını gerektirebilir ve cihazı kaydetme işlemini tamamen atlayabilirsiniz!  

Her iki yöntemde de, Office 365 verilerinin güvenliği sizin tanımladığınız ilkelerle sağlanır.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->


## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>Tüm çalışanlara kendi cihazını getir programı sunma
Donanım harcamalarını azaltmaya veya çalışanlar için mobil üretkenlik seçeneklerini artırmaya yönelik bir araç olarak kuruluşlar arasında kendi cihazını getir (KCG) modelinin popülerliği artmaya devam etmektedir. Bugünlerde artık hemen herkesin kişisel telefonu olduğuna göre, ceplerine bir telefon daha koymanın ne anlamı var? Bu yöntemde her zaman en önemli güçlük kişisel cihazlarını yönetime kaydetmeleri için çalışanları ikna etmektir çünkü BT bölümlerinin cihazlarında görebileceği ve yapabileceği şeylerden çekinirler.  

Cihaz kaydının uygulanabilir bir seçenek olmadığı durumlarda, Intune alternatif bir KCG yaklaşımı olarak [şirket verilerini içeren uygulamaları yönetme](/intune-classic/deploy-use/protect-apps-and-data-with-microsoft-intune) yaklaşımını sunar.  Intune, Office mobil uygulamalarında olduğu gibi söz konusu uygulamanın hem şirket verilerine hem de kişisel verilere eriştiği durumlarda bile şirket verilerini korur.  

Bir yönetici olarak, kullanıcıların Office mobil uygulamalarına Office 365’ten erişmelerini ve uygulamaları, verileri koruma altına alan (şifreleme, pin ile koruma vs.) ilkelerle yapılandırmalarını zorunlu tutabilirsiniz. Bu ilkeler, yönetilmeyen uygulamalara ve bu uygulamaların içindeki ve dışındaki depolama konumlarına veri kaybetmeyi önler. Örneğin, ilkeler kullanıcın şirket e-posta profilinden tüketici e-posta profiline (her iki profil de Outlook Mobile içinde yapılandırılmış olsa bile) metin kopyalamasını önler. KCG kullanıcılarınıza gereken diğer hizmetler ve uygulamalar için de benzer yapılandırmalar dağıtılabilir.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-employees"></a>Çalışanlarınıza şirketin sahip olduğu telefonları verme
Bugünlerde çalışanların çoğu mobil çalıştığı için rekabet üstünlüğü açısından mobil cihazlarda üretkenlik sağlamak bir zorunluluktur. Bu çalışanların her zaman, gittikleri her yerde şirket uygulamalarına ve verilerine rahatça erişebilmeleri gerekir. Şirket verilerinin güvenli ve yönetim maliyetlerinin düşük olmasını sağlamalısınız.  

Intune pazara sunulmuş olan Apple Cihaz Kayıt Programı ve Samsung KNOX mobil güvenlik platformu gibi başlıca şirket cihazı yönetim platformlarıyla tümleşik çalışan [toplu sağlama ve yönetim çözümleri](/intune-classic/deploy-use/manage-corporate-owned-devices) sunar. Intune’la merkezi cihaz yapılandırmaları yazma özelliği, şirket cihazlarının sağlanmasını üst düzeyde otomatik bir işlem haline getirmeye yardımcı olur.  

Şunu düşünün: çalışana açılmamış bir iPhone kutusu veriyorsunuz. Çalışan iPhone’u çalıştırıyor kendi kimliğini doğrulamasını gerektiren şirket markalı bir kurulum akışında ilerliyor. iPhone, [güvenlik ilkeleri](/intune-classic/deploy-use/add-apps) ile sorunsuz bir şekilde yapılandırılıyor.

Ardından, çalışan kendine sağlanan isteğe bağlı şirket uygulamalarına erişmek için Intune Şirket Portalı uygulamasını başlatıyor.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-employees"></a>Çalışanlarınıza sınırlı kullanımı olan paylaşılan tabletler verme
Çalışanlar, mobil teknolojileri giderek daha fazla kullanmaktadır. Örneğin, paylaşılan tabletler mağaza çalışanları tarafından sıklıkla kullanılmaktadır.  İster satışı işlemek ister anında stok kontrolü yapmak için kullanılsın, tabletler harika müşteri etkileşimlerine yardımcı olur.

Bu örnekte, kullanıcı deneyiminin basitliği kritik önem taşır. Bu nedenle, tabletler çoğunlukla çalışanlara sınırlı kullanım modunda verilir. Bu sayede çalışan yalnızca tek bir iş kolu uygulamasıyla etkileşimli çalışabilir. Intune, sınırlı kullanım modunda yapılandırılabilen bu paylaşılan [iOS](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) tabletleri toplu olarak sağlamanıza, güvenlik altına almanıza ve merkezi olarak yönetmenize olanak tanır.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Çalışanlarınızın yönetilmeyen genel bir bilgi noktasından Office 365’e güvenle erişmesini sağlama
Bazen çalışanlarınızın sergi alanlarında ve otel lobilerindeki genel kullanıma açık bilgisayarlar gibi yönetemediğiniz cihazları, uygulamaları veya tarayıcıları kullanması gerekebilir.

Çalışanlarınızın buralardan şirket e-postasına erişmesine izin vermeli misiniz? Intune ve Microsoft Enterprise Mobility + Security ile <!--you have choices. The--> yanıt basitçe "hayır" olabilir ve [e-posta erişimini kuruluşunuz tarafından yönetilen cihazlarla sınırlandırırsınız](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).--> Bu da sağlam bir şekilde kimliği doğrulanmış çalışanınızın güvenilmeyen bir bilgisayara şirket verilerini bırakmamasını güvence altına alır.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->
