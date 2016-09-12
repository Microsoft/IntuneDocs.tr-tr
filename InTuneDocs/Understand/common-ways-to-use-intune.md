---
title: "Intune’u kullanmanın yaygın yolları | Microsoft Intune"
description: "Intune’un yardımcı olduğu en yaygın altı görevi listeler"
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2ebb8fcf348cfdc7600c37b40824f5bba37a7f36
ms.openlocfilehash: 4614c13d98c4b05882bbeabfbbd7de83d9bea2da


---

# Intune'u kullanmanın yaygın yolları

Uygulama görevleri konusuna girmeden önce, şirketinizde kurumsal mobil çalışmayla ilgilenen katılımcıları iş hedefleri çerçevesinde uyumlu bir noktaya getirmek önemlidir.  Kurumsal mobil çalışmaya yenim mi başladığınız yoksa başka bir üründen geçiş mi yaptığınız da önemlidir.  Kurumsal mobil çalışma konusundaki gereksinimleri dinamik olarak artmaktadır ve Microsoft’un bu gereksinimlerini karşılamaya yönelik yaklaşımları pazardaki diğer çözümlerden farklı olabilir.  İş hedefleri çerçevesinde uyumlu bir noktaya gelmenin en iyi yolu, çalışanlarınız, iş ortaklarınız ve BT’nize olanak sağlamak istediğiniz senaryolar açısından neleri başarmak istediğinizi ortaya koymaktır.  Aşağıda, Intune’a dayalı en yaygın 6 senaryoya kısa giriş bilgileri ve her birinin planlanması ve dağıtımıyla ilgili daha fazla bilgiye ulaştıran bağlantılar verilmiştir.

>[!NOTE]
>Microsoft çalışanlarının mobil cihazlarından şirket kaynaklarına erişmesine olanak tanırken şirket verilerinin de güvenliğini korumak için Microsoft BT’sinin Intune’u nasıl kullandığını bilmek ister misiniz? Microsoft BT’sinin Intune’u ve diğer hizmetleri kullanarak kimlikleri, cihazları, uygulamaları ve verileri nasıl yönettiğini ayrıntılarıyla görmek için [bu teknik olay incelemesini okuyun](https://www.microsoft.com/itshowcase/Article/Content/588).  

>[!IMPORTANT]
>Mobil cihazların güncel kalmasını sağlama<br>
>Yakın zamanda iOS cihazlarına yapılan "Trident" kötü amaçlı yazılım saldırılarından sonra, Intune’un cihazınızı güvenli ve güncel tutmaya yardımcı olabileceği farklı yolları göstermek için [Microsoft Intune kullanarak mobil cihazların güncel kalmasını sağlama](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) adında yeni bir blog gönderisi yayımladık.

## Şirket içi e-postanızı ve verilerinizi güvenlik altına alarak mobil cihazların bunlara güvenle erişmesini sağlama
Kurumsal mobil çalışma stratejilerinin çoğu çalışanların mobil cihazlarıyla dışarıdan, İnternet üzerinden e-postaya güvenli erişimini sağlama planıyla başlar. Birçok kuruluşun hala kurumsal ağlarında barındırdıkları Microsoft Exchange gibi şirket içi veri ve uygulama sunucuları vardır. Intune ve Enterprise Mobility Suite’in (EMS) Exchange Server için sağladığı benzersiz bir şekilde tümleştirilmiş [koşullu erişim çözümüyle](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) cihaz Intune’a kaydolmadıkça hiçbir mobil uygulamanın e-postaya erişememesi güvence altına alınır ve bunun için şirket ağınızın ucuna hiçbir ağ geçidi makinesinin kurulması gerekmez!

E-postanın ötesinde, Intune bir iş kolu uygulama sunucusu gibi şirket içi verilere güvenli erişim gerektiren mobil uygulamalara erişim sağlamayı da destekler.  Bu tipik olarak, erişim denetimi için [Intune tarafından yönetilen sertifikaları](/intune/deploy-use/secure-resource-access-with-certificate-profiles) çevredeki standart bir VPN ağ geçidi veya ara sunucusuyla, örneğin Microsoft Azure AD Uygulama Ara Sunucusu’yla birlikte kullanarak gerçekleştirilir.  Böyle durumlarda, şirket verilerine erişmenin tek yolu cihazı yönetime kaydetmektir.  Kaydedildikten sonra, yönetim sistemi şirket verilerine erişen cihazların ilkelerinizle uyumlu olmasını güvence altına alır.  Buna ek olarak, erişilen verilerin iş kolu uygulamanız içinde tutulmasına ve böylelikle şirket verilerinin tüketici uygulamalarına veya hizmetlerine geçirilememesine yardımcı olmak için Intune’un [Uygulama Kaydırma Aracı ve Uygulama SDK’sı](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) kullanılabilir.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## Office 365 e-postanızı ve verilerinizi güvenlik altına alarak mobil cihazların bunlara güvenle erişmesini sağlama
Office 365’teki şirket verilerinin (e-posta, belgeler, anlık iletiler, kişiler) korunması sizin için bundan kolay ve kullanıcılarınız için bundan rahat olamazdı. Intune ve Enterprise Mobility Suite’in sağladığı benzersiz bir şekilde tümleştirilmiş koşullu erişim çözümüyle, şirketinizin uyumluluk gereksinimlerini (yönetilen uygulama, desteklenen işletim sistemi sürümü, cihaz pin’i, düşük kullanıcı riski profili, vb. kullanarak [çok faktörlü kimlik doğrulaması](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication) yapma, Intune’a kaydolma) karşılamayan hiçbir kullanıcının, uygulamanın veya cihazın Office 365 verilerine erişememesi güvence altına alınır. Kendi uygulama mağazalarındaki Office mobil uygulamaları, Intune yoluyla yapılandırabileceğiniz veri kapsama ilkelerine uyumlu davranmaya hazır olduğundan, verilerin BT tarafından yönetilmeyen uygulamalarla (yerel e-posta uygulaması gibi) ve depolama konumlarıyla (Dropbox gibi) paylaşılmasını önleyebilirsiniz.  Bu işlevsellik tümüyle Office 365 ve EMS’de yerleşik olarak bulunur.  Bu değerli işlevselliği elde etmek için ek altyapı dağıtımı yapmanız gerekmez.

Yaygın bir Office 365 dağıtım uygulaması, kendilerine şirket uygulama/sertifika/Wi-Fi/VPN yapılandırmalarının tamamen sağlanması gereken cihazların yönetime kaydolmalarının gerekli olmasıdır ve şirketin sahip olduğu cihazlarda çoğunlukla bu durum geçerlidir.  Öte yandan, kişilerin sahip olduğu cihazlarda çoğunlukla olduğu gibi kullanıcının yalnızca şirket e-postasına ve belgelerine erişmesi gerekiyorsa, kullanıcının Office mobil uygulamalarını ([veri kapsama ilkelerini uyguladığınız](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune) uygulamalar) kullanmaları ve cihazı kaydetme işlemini tamamen atlamaları gerekir!  Her iki yöntemde de, Office 365 verilerinin güvenliği sizin tanımladığınız ilkelerle sağlanır.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## Tüm çalışanlara “kendi cihazını getir” (KCG) programı sunma
Donanım harcamalarını azaltmaya veya çalışanlar için mobil üretkenlik seçeneklerini artırmaya yönelik bir araç olarak kuruluşlar arasında KCG’nin popülerliği artmaya devam etmektedir. Bugünlerde artık hemen herkesin kişisel telefonu olduğuna göre, ceplerine bir telefon daha koymanın ne anlamı var? Bu yöntemde her zaman en önemli güçlük kişisel cihazlarını yönetime kaydetmeleri için çalışanları ikna etmektir çünkü BT bölümlerinin cihazlarında görebileceği ve yapabileceği şeylerden çekinirler.  

Cihaz kaydının uygulanabilir bir seçenek olmadığı durumlarda, Intune alternatif bir KCG yaklaşımı olarak [şirket verilerini içeren uygulamaları yönetme](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune) yaklaşımını sunar.  Intune, Office mobil uygulamalarında olduğu gibi söz konusu uygulamanın hem şirket verilerine hem de kişisel verilere eriştiği durumlarda bile şirket verilerini korur.  Bir yönetici olarak, kullanıcıların Office mobil uygulamalarına Office 365’ten erişmelerini ve uygulamaları, verileri koruma altına alan (şifrelenmiş, korumalı, vb.) ilkelerle yapılandırmalarını zorunlu tutabilirsiniz.  Bu ilkeler, yönetilmeyen uygulamalara ve bu uygulamaların içindeki ve dışındaki depolama konumlarına veri kaybetmeyi önler.  Örneğin, ilkeler kullanıcın şirket e-posta profilinden tüketici e-posta profiline (her iki profil de Outlook Mobile içinde yapılandırılmış olsa bile) metin kopyalamasını önler.  KCG kullanıcılarınıza gereken diğer hizmetler ve uygulamalar için de benzer yapılandırmalar dağıtılabilir.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## Bilişim elemanlarınıza şirketin sahip olduğu telefonları verme
Bugünlerde bilişim elemanlarının çoğunluğu mobil çalıştığından, rekabet üstünlüğü açısından mobil cihazlarda üretkenlik sağlamak bir zorunluluktur.  Bu çalışanların her zaman, gittikleri her yerde şirket uygulamalarına ve verilerine rahatça erişebilmeleri gerekir.  Şirket verilerinin güvenli ve yönetim maliyetlerinin düşük olmasını sağlamalısınız.  

Intune pazara sunulmuş olan Apple Cihaz Kayıt Programı ve Samsung KNOX mobil güvenlik platformu gibi başlıca şirket cihazı yönetim platformlarıyla tümleşik çalışan [toplu sağlama ve yönetim çözümleri](/intune/deploy-use/manage-corporate-owned-devices) sunar.  Intune’la merkezi cihaz yapılandırmaları yazma özelliği, şirket cihazlarının sağlanmasını üst düzeyde otomatik bir işlem haline getirebilir.  

Şunu düşünün: çalışana açılmamış bir iPhone kutusu veriyorsunuz. Çalışan iPhone’u çalıştırıyor kendi kimliğini doğrulamasını gerektiren şirket markalı bir kurulum akışında ilerliyor. iPhone, [güvenlik ilkeleri](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (şifreli sabit sürücü, cihaz pin’i, vb.), [e-posta/Wi-Fi/VPN/sertifika profilleri](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) ve temel bir [uygulamalar](/intune/deploy-use/add-apps) kümesiyle rahatça yapılandırılır. Ardından, çalışan kendine sağlanan isteğe bağlı şirket uygulamalarına erişmek için Intune Şirket Portalı uygulamasını başlatıyor.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## Görevlerde çalışanlarınıza sınırlı kullanımı olan paylaşılan tabletler verme
Görevlerde çalışanlar mobil teknolojileri giderek daha fazla kullanmaktadır.  Örneğin, paylaşılan tabletler mağaza çalışanları için artık sıradan bir hale gelmiştir.  İster satışı işlemek ister anında stok kontrolü yapmak için kullanılsın, tabletler harika müşteri etkileşimlerine yardımcı olur.  Bu örnekte, kullanıcı deneyiminin basitliği kritik önem taşır.  Bu nedenle, tabletler çoğunlukla çalışanlara sınırlı kullanım modunda verilir. Şöyle ki, çalışan yalnızca tek bir iş kolu uygulamasıyla etkileşimli çalışabilir.  Intune, bu paylaşılan [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings) ve [Android](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy) tabletleri toplu olarak sağlamanıza, güvenlik altına almanıza ve merkezi olarak yönetmenize olanak tanır. Bu tabletler, sınırlı kullanım modunda çalışmaları için yapılandırılabilir.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## Çalışanlarınızın yönetilmeyen genel bir bilgi noktasından Office 365’e güvenle erişmesini sağlama
Bazen çalışanlarınızın sergi alanlarında ve otel lobilerindeki genel kullanıma açık bilgisayarlar gibi yönetemediğiniz cihazları, uygulamaları veya tarayıcıları kullanması gerekebilir. Çalışanlarınızın buralardan şirket e-postasına erişmesine izin vermeli misiniz? Intune ve Enterprise Mobility Suite ile <!--you have choices. The--> yanıt basitçe “hayır” olabilir ve [e-posta erişimini kuruluşunuz tarafından yönetilen cihazlarla sınırlandırırsınız](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).-->  Bu da, sağlam bir şekilde kimliği doğrulanmış çalışanınızın güvenilmeyen bir bilgisayara şirket verilerini bırakmamasını güvence altına alır.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Sep16_HO1-->


