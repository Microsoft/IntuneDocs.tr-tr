---
title: "Android for Work Hakkında| Microsoft Intune"
description: "Intune, kullanıcılar iş için Android cihazlarını kullandıklarında ek yönetim özellikleri ve gizlilik sağlamak için Android for Work’ü yönetir."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 0238350139837a06a48d0bff7c53e4c39e07168c
ms.openlocfilehash: aafeb58e28144740540a765ac04de68b41ae5ce5


---

# <a name="manage-android-for-work-devices-with-intune"></a>Intune ile Android for Work cihazları yönetme

Android for Work, Android cihaz özellikleri ve hizmetlerinin bir bileşimidir. Bu özellikler ve hizmetler, kullanıcılar iş için Android cihazlarını kullandıklarında ek yönetim özellikleri ve gizlilik sağlar. Intune, iş bilgileri ve kişisel bilgilerin ayrı olmasını sağlamak için Android for Work cihazlara uygulamalar ve şirket kaynakları dağıtmanıza yardımcı olabilir. Başarıyla dağıtıldığında, uygulamalar ve bunların eriştiği veriler özel olarak cihazdaki Android for Work ortamında kalır.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>Desteklenen cihazlar

Birçok yönetim yeteneği yeni Android işletim sisteminin parçası olan özellikler gerektirdiğinden, Android for Work daha yeni Android donanımı gerektirir. Android for Work şu anda Android 5.0 Lollipop ve üzeri sürümleri çalıştıran ve iş profili desteği olan cihazlarda desteklenir. Yerel Android for Work desteği olmayan cihazlarda geleneksel Android yönetimi kullanılmaya devam edilebilir. [Android for Work gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) hakkında daha fazla bilgi edinin.

## <a name="onboarding"></a>Ekleme

Android for Work cihazları kaydetmeden önce bazı ekleme adımlarını tamamlamanız gerekir. Bu adımlar, Android for Work uygulama dağıtımı ve yönetimi sürecinin en önemli parçalarından biri olan Intune kiracınız ve Google Play for Work hizmeti arasında bağlantıyı kurar. [Android for Work kaydını etkinleştirme](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work) hakkında daha fazla bilgi edinin.

## <a name="work-profile-management"></a>İş profili yönetimi

Intune ile bir Android for Work cihaz yönettiğinizde, tüm cihazı yönetmezsiniz. Yönetim yetenekleri sadece kayıt sırasında oluşturulan iş profilini etkiler. Intune ile cihaza dağıtılan tüm uygulamalar iş profilinin bir parçasıdır. İş profilindeki uygulamaların simgeleri turuncu bir evrak çantası görüntüler. Bu işaretleme, cihazda şirket uygulamaları ile kişisel uygulamaları ayırır. Tüm Android uygulamaları ve cihazın Android for Work bölümü dışındaki veriler kişisel ve son kullanıcının denetimi altında kalır. Kullanıcılar cihazın kişisel kısmına istedikleri uygulamayı yükleyebilirken, yöneticiler iş profilinin kapsamındaki eylemleri yönetebilir ve izleyebilir.

## <a name="app-publishing-and-distribution"></a>Uygulama yayımlama ve dağıtma

Google Play for Work hizmeti uygulama dağıtımı ve yönetiminin önemli bir parçasıdır. İş profilinde Android for Work cihazlara dağıtılan tüm uygulamalar Play for Work’ten gelir. Play Store'da uygulamaları yönetmek ve dağıtmak için Play for Work web sitesinde bir Intune yöneticisi olarak oturum açar ve Intune kiracınız için uygulamaları onaylarsınız. Bu uygulamalar Intune konsoluna eşitlenir ve burada Intune kullanılarak dağıtılıp yönetilebilir. Kuruluşunuz tarafından geliştirilen iş kolu (LOB) uygulamalarının Google’ın Android uygulama yayımlama konsolu kullanılarak Play for Work’te yayımlanması gerekir. İş kolu uygulamalarının, kuruluşunuza erişimi kısıtlamak için Android uygulama yayımlama konsolunda yapılandırılması gerekir.

Uygulamalar kullanıcı etkileşimi olmadan ve kullanıcının **Bilinmeyen Kaynaklardan Yükleme**’ye izin vermesine gerek kalmadan yüklenir. İsteğe bağlı veya kullanılabilir uygulamalara göz atmak için kullanıcı cihazındaki iş rozetli Play Store uygulamasını kullanır. [Android for Work için uygulama dağıtma](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps) hakkında daha fazla bilgi edinin.

## <a name="app-configuration"></a>Uygulama yapılandırması

Android for Work, uygulama yapılandırma değerlerini bunları destekleyen uygulamalara dağıtmak için bir altyapı sağlar. İş uygulamaları için yapılandırma değerlerini belirterek, kullanıcılar uygulamayı ilk kez başlattığında bunların düzgün ayarlandığından emin olursunuz. Uygulama yapılandırması desteği için uygulama geliştiricilerinin kendi Android uygulamalarını yönetilen yapılandırma değerlerini spesifik olarak destekleyecek şekilde oluşturmaları gerekir. Eğer öyleyse, bu yapılandırma ayarlarını belirtmek ve uygulamak için Intune kullanabilirsiniz. [Android for Work uygulama yapılandırma ayarları](deploy-use/afw-app-configuration-policy.md) hakkında daha fazla bilgi edinin.

## <a name="email-configuration"></a>E-posta yapılandırması

Android for Work, iOS gibi varsayılan bir e-posta uygulaması veya yerel e-posta profili nesnesi sağlamaz. Bunun yerine, e-posta yapılandırmaları kendilerini destekleyen e-posta uygulamalarına uygulama yapılandırma ayarları uygulayarak ayarlanabilir. Gmail ve Nine Work, Play Store’da bulunan ve Android for Work uygulama yapılandırması ile yapılandırmayı destekleyen iki Exchange ActiveSync (EAS) istemci uygulamasıdır.

Intune, Gmail ve Nine Work uygulamaları için yapılandırma şablonları sağlar. Uygulama yapılandırma profillerini destekleyen diğer e-posta uygulamaları mobil uygulama yapılandırma ilkeleriyle yapılandırılabilir.

Android for Work cihazlar için EAS koşullu erişim kullanıyorsanız, Gmail veya Nine Work e-posta uygulamasını kullanmanız gerekir. Android için Microsoft Outlook uygulaması veya ADAL ile modern kimlik doğrulaması kullanan herhangi bir e-posta uygulaması da desteklenir. [Şirket e-postası için e-posta profilleri](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) hakkında daha fazla bilgi edinin.

## <a name="mobile-app-management-policies"></a>Mobil uygulama yönetimi ilkeleri

Mobil uygulama yönetimi (MAM) için etkinleştirilmiş uygulamalara uygulanan kısıtlama ilkeleri iş profilinde ve kişisel profilde tam olarak desteklenir. İş kolu uygulamalarını, Android uygulama yayımlama konsolunda şu adreste yayımlayabilirsiniz: https://play.google.com/apps/publish. Bu konsol, uygulamaları kuruluşunuza özel hale getirme seçeneğine sahiptir. [Uyumluluk ilkesi ayarları](afw-compliance-policy-settings-in-microsoft-intune.md) hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [mobil uygulama yönetimi ilkeleri](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

## <a name="vpn-profiles"></a>VPN profilleri

VPN desteği, Android VPN profillerine benzerdir. Aynı VPN sağlayıcıları ve temel yapılandırma seçenekleri kullanılabilir. İki temel fark vardır:

1.  **İş profili kapsamlı VPN** – VPN bağlantılarının kapsamı yalnızca iş profiline dağıtılan uygulamalarla sınırlıdır. Yalnızca Android for Work tarafından yönetilen uygulamalar VPN bağlantısını kullanabilir. Cihazdaki kişisel uygulamalar bir yönetilen VPN bağlantısı kullanamaz.

2.  **Uygulamaya özel VPN** – Bir VPN sağlayıcı uygulamaya özel VPN destekliyorsa ve Android for Work uygulama yapılandırma profili aracılığıyla uygulama başına VPN yapılandırma yeteneği sağlıyorsa, Intune’da uygulamaya özel VPN yapılandırılabilir. Bu yeteneğin desteklenip desteklenmediğini öğrenmek için VPN sağlayıcıya danışın. [VPN bağlantı profilleri](vpn-connections-in-microsoft-intune.md) hakkında daha fazla bilgi edinin.

## <a name="certificate-profiles"></a>Sertifika profilleri

Geleneksel Android yönetimi için kullanılabilir olan sertifika profili yapılandırma seçenekleri Android for Work cihazlar için de kullanılabilir. Android for Work gelişmiş sertifika yönetimi API'leri sağlar. Gelişmiş sertifika yönetimi aşağıdaki işlevleri sağlar:

1.  Sertifika dağıtımının sessiz ve kullanıcı için sorunsuz olmasını sağlar.

2.  Bir cihaz Intune’da kullanımdan kaldırıldığında ve iş profili kaldırıldığında dağıtılan sertifikaların tamamen kaldırılmasını sağlar.

3.  BT departmanı tarafından yönetim hizmeti aracılığıyla sertifikanın dağıtıldığını ve yapılandırıldığını kullanıcılara bildiren gelişmiş iletiler sağlar.

[Sertifika profilleri](secure-resource-access-with-certificate-profiles.md) hakkında daha fazla bilgi edinin.

## <a name="wifi-profiles"></a>Wi-Fi profilleri

Cihaz devre dışı bırakıldığında ve iş profili silindiğinde Android for Work tarafından yönetilen Wi-Fi profillerinin kaldırılması garanti altına alınır. [Wi-Fi profilleri](wi-fi-connections-in-microsoft-intune.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
[Android for Work kaydını etkinleştirme](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Android for Work için uygulama dağıtma](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO1-->


