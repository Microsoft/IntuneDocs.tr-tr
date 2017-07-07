---
title: "Android for Work hakkında"
description: "Intune, kullanıcılar iş için Android cihazlarını kullandıklarında ek yönetim özellikleri ve gizlilik sağlamak için Android for Work’ü yönetir."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ms.custom: intune-classic
ms.openlocfilehash: 12045c3e81686ad3e351cd5a85bc663832b87b2e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="manage-android-for-work-devices-with-intune"></a>Intune ile Android for Work cihazları yönetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work kişisel uygulamaları ve verileri, uygulama ve veri içeren bir iş profilinden ayıran Android cihazı özellik ve hizmet kümesidir. Android for Work, kullanıcılar Android cihazlarını iş için kullandıklarında ek yönetim özellikleri ve gizlilik sağlar. Intune, iş bilgileri ve kişisel bilgilerin ayrı olmasını sağlamak için Android for Work cihazlara uygulamalar ve şirket kaynakları dağıtmanıza yardımcı olur. Başarıyla dağıtıldığında, uygulamalar ve bunların eriştiği veriler özel olarak cihazdaki Android for Work ortamında kalır.

## <a name="supported-devices"></a>Desteklenen cihazlar

Android for Work yönetim özellikleri, daha yeni Android işletim sisteminin parçası olan özelliklerden faydalanır. Android for Work şu anda Android 5.0 Lollipop ve üzeri sürümleri çalıştıran ve iş profili desteği olan cihazlarda desteklenir. Android for Work desteği olmayan cihazlarda geleneksel Android yönetimi kullanılmaya devam edilebilir. [Android for Work gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) hakkında daha fazla bilgi edinin.

## <a name="onboarding"></a>Ekleme

Android for Work cihazları kaydetmeden önce bazı ekleme adımlarını tamamlamanız gerekir. Bu adımlar, Android for Work uygulama dağıtımı ve yönetimi sürecinin en önemli parçalarından biri olan Intune kiracınız ve Google Play for Work hizmeti arasında bağlantıyı kurar. [Android for Work kaydını etkinleştirme](/intune-classic/deploy-use/set-up-android-for-work) hakkında daha fazla bilgi edinin.

## <a name="work-profile-management"></a>İş profili yönetimi

Intune ile bir Android for Work cihaz yönettiğinizde, tüm cihazı yönetmezsiniz. Yönetim yetenekleri yalnızca kayıt sırasında cihazda oluşturulan iş profilini etkiler. Intune ile cihaza dağıtılan tüm uygulamalar, iş profiline yüklenir. Cihazdaki iş uygulamalarının kişisel uygulamalardan ayrılabilmesi için iş profilindeki uygulamaların yanında turuncu renkli evrak çantası görüntülenir. Tüm Android uygulamaları ve cihazın Android for Work bölümü dışındaki veriler kişisel ve son kullanıcının denetimi altında kalır. Kullanıcılar cihazın kişisel kısmına istedikleri uygulamayı yükleyebilirken, yöneticiler iş profilinin kapsamındaki uygulamaları ve eylemleri yönetip izleyebilir.

Intune, Android for Work cihazlarda yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. [Android for Work ilke ayarları](android-for-work-policy-settings-in-microsoft-intune.md) hakkında daha fazla bilgi edinin

## <a name="app-publishing-and-distribution"></a>Uygulama yayımlama ve dağıtma

Google Play for Work hizmeti, Android for Work uygulama dağıtımı ve yönetiminin önemli bir parçasıdır. İş profilinde Android for Work cihazlara dağıtılan tüm uygulamalar Play for Work hizmetinden gelir. Play Store’daki uygulamaları yönetmek ve dağıtmak için, Google Play web sitesinde şirketinizin Google yönetimi için yönetici kimlik bilgileriyle oturum açarsınız. Cihazlarınızın iş profillerinde gösterilmeleri için, Android for Work dağıtımının uygulamalarını onaylayabilirsiniz. Ardından bu uygulamalar Intune konsoluna eşitlenir ve burada Intune kullanılarak dağıtılıp yönetilebilir. Kuruluşunuz tarafından geliştirilen iş kolu (LOB) uygulamalarının Google’ın Android uygulama yayımlama konsolu kullanılarak Play for Work’te yayımlanması gerekir. İş kolu uygulamalarının, kuruluşunuza erişimi kısıtlamak için Android uygulama yayımlama konsolunda yapılandırılması gerekir.

Uygulamalar kullanıcı etkileşimi olmadan ve kullanıcının **Bilinmeyen Kaynaklardan Yükleme**'ye izin vermesine gerek kalmadan yüklenebilir. İsteğe bağlı veya kullanılabilir uygulamalara göz atmak ve onları yüklemek için kullanıcı cihazındaki Play for Work mağazasını gözden geçirebilir. [Android for Work için uygulama dağıtma](/intune-classic/deploy-use/android-for-work-apps) hakkında daha fazla bilgi edinin.

## <a name="app-configuration"></a>Uygulama yapılandırması

Android for Work, uygulama yapılandırma değerlerini bunları destekleyen uygulamalara dağıtmak için bir altyapı sağlar. İş uygulamaları için yapılandırma değerlerini belirterek, kullanıcılar uygulamayı ilk kez başlattığında bunların düzgün ayarlandığından emin olursunuz. Uygulama yapılandırması desteği için uygulama geliştiricilerinin kendi Android uygulamalarını yönetilen yapılandırma değerlerini spesifik olarak destekleyecek şekilde oluşturmaları gerekir. Eğer öyleyse, bu yapılandırma ayarlarını belirtmek ve uygulamak için Intune kullanabilirsiniz. [Android for Work uygulama yapılandırma ayarları](afw-app-configuration-policy.md) hakkında daha fazla bilgi edinin.

## <a name="email-configuration"></a>E-posta yapılandırması

Android for Work, iOS gibi varsayılan bir e-posta uygulaması veya yerel e-posta profili nesnesi sağlamaz. Bunun yerine, e-posta yapılandırmaları kendilerini destekleyen e-posta uygulamalarına uygulama yapılandırma ayarları uygulayarak ayarlanabilir. Gmail ve Nine Work, Play Store’da bulunan ve Android for Work uygulama yapılandırması ile yapılandırmayı destekleyen iki Exchange ActiveSync (EAS) istemci uygulamasıdır.

Intune, iş uygulamaları olarak yönetildiklerinde Gmail ve Nine Work uygulamaları için yapılandırma şablonları sağlar. Uygulama yapılandırma profillerini destekleyen diğer e-posta uygulamaları mobil uygulama yapılandırma ilkeleriyle yapılandırılabilir.

Android for Work cihazlar için Exchange ActiveSync koşullu erişim kullanıyorsanız, Gmail veya Nine Work e-posta uygulamasını kullanmanız gerekir. Android için Microsoft Outlook uygulaması veya ADAL ile modern kimlik doğrulaması kullanan herhangi bir e-posta uygulaması da desteklenir. [Şirket e-postası için e-posta profilleri](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) hakkında daha fazla bilgi edinin.

## <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

Uygulaman uygulama koruma ilkeleri, iş profilinde ve kişisel profilde tümüyle desteklenir. İş kolu uygulamalarını, Android uygulama yayımlama konsolunda şu adreste yayımlayabilirsiniz: https://play.google.com/apps/publish. Bu konsol, uygulamaları kuruluşunuza özel hale getirme seçeneğine sahiptir. [Android for Work uyumluluk ilkesi ayarları](afw-compliance-policy-settings-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. Uygulama koruma ilkeleri hakkındaki genel bilgiler için bkz. [uygulama ilkeleri](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>VPN profilleri

VPN desteği, Android VPN profillerine benzerdir. Android for Work yönetimi için aynı VPN sağlayıcıları ve temel yapılandırma mevcuttur ancak iki fark vardır:

-  **İş profili kapsamlı VPN** – VPN bağlantıları yalnızca iş profiline dağıtılan uygulamalarla sınırlıdır. Yalnızca Android for Work tarafından yönetilen uygulamalar VPN bağlantısını kullanabilir. Cihazdaki kişisel uygulamalar bir yönetilen VPN bağlantısı kullanamaz.

-  **Uygulamaya özel VPN** – Bir VPN sağlayıcı uygulamaya özel VPN destekliyorsa ve Android for Work uygulama yapılandırma profili aracılığıyla uygulama başına VPN yapılandırma yeteneği sağlıyorsa, Intune’da uygulamaya özel VPN yapılandırılabilir. Bu yeteneğin desteklenip desteklenmediğini öğrenmek için VPN sağlayıcıya danışın. [VPN bağlantı profilleri](vpn-connections-in-microsoft-intune.md) hakkında daha fazla bilgi edinin.

## <a name="certificate-profiles"></a>Sertifika profilleri

Android yönetimi için kullanılabilir olan sertifika profili yapılandırma seçenekleri Android for Work cihazlar için de kullanılabilir. Android for Work gelişmiş sertifika yönetimi API'leri sağlar. Gelişmiş sertifika yönetimi aşağıdaki işlevleri sağlar:

- Sertifika dağıtımının sessiz ve kullanıcı için sorunsuz olmasını sağlar.
-  Bir cihaz Intune’da kullanımdan kaldırıldığında ve iş profili kaldırıldığında dağıtılan sertifikaların tamamen kaldırılmasını sağlar.
-  BT departmanı tarafından yönetim hizmeti aracılığıyla sertifikanın dağıtıldığını ve yapılandırıldığını kullanıcılara bildiren gelişmiş iletiler sağlar.

[Sertifika profilleri](secure-resource-access-with-certificate-profiles.md) hakkında daha fazla bilgi edinin.

## <a name="wi-fi-profiles"></a>Wi-Fi profilleri

Cihaz devre dışı bırakıldığında ve iş profili silindiğinde Android for Work tarafından yönetilen Wi-Fi profilleri kaldırılır. [Wi-Fi profilleri](wi-fi-connections-in-microsoft-intune.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
[İş için Android kaydını etkinleştirme](/intune-classic/deploy-use/set-up-android-for-work)

[Android for Work için uygulama dağıtma](/intune-classic/deploy-use/android-for-work-apps)
