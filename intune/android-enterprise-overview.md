---
title: Microsoft Intune Android kurumsal iş profili cihazları yönetme
titleSuffix: ''
description: Microsoft Intune Android kişisel cihazlarını iş için kullandıklarında ek yönetim özellikleri ve gizlilik sağlamak için Android kurumsal iş profili cihazları yönetir.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 305ed5c18ad0e8beeaa47bc644266d4cb19f80e6
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501060"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Intune ile Android iş profili cihazlarını yönetme

Android Kurumsal kullanıcılara en güncel ve güvenli özelliklerle sağlamak kayıt seçenekleri kümesi sunar. Android kurumsal iş profiliyle kaydetme, bir dizi özellik ve kişisel uygulamalar ve veriler iş uygulamaları ve verileri ayrı hizmetler sağlar. Kişisel Android cihazlarını iş için kullandıklarında ek yönetim özellikleri ve gizlilik da sağlar. 

## <a name="supported-devices"></a>Desteklenen cihazlar

Android kurumsal yönetim özellikleri, daha yeni Android işletim sistemlerini parçası olan özelliklerden faydalanır kullanır. Android Kurumsal desteklemeyen cihazlar geleneksel Android Yönetimi kullanılmaya devam edilebilir. Daha fazla bilgi için [Android Kurumsal gereksinimleri](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Ekleme

Android Kurumsal kaydetmeden önce iş profili cihazları, bazı ekleme adımlarını tamamlamanız gerekir. Bu adımları, Intune kiracınız ve yönetilen Google Play arasında bağlantı kurun. Daha fazla bilgi için [Android kurumsal iş profili cihazların kaydını etkinleştirme](android-work-profile-enroll.md).

## <a name="work-profile-management"></a>İş profili yönetimi

Android kurumsal iş profili cihazı Intune ile yönetirken, tüm cihazı yönetmezsiniz. Yönetim yetenekleri yalnızca kayıt sırasında cihazda oluşturulan iş profilini etkiler. Intune ile cihaza dağıtılan tüm uygulamalar, iş profiline yüklenir. İş profilindeki uygulama simgeleri, cihazdaki kişisel uygulamalardan farklıdır. Cihazın Android iş profili bölümü dışındaki tüm Android uygulama ve verileri, kişiseldir ve son kullanıcının denetimindedir. Kullanıcılar, cihazın kişisel kısmına istedikleri uygulamaları yükleyebilir. Yöneticiler ise iş profili kapsamındaki tüm uygulamaları yönetebilir ve izleyebilir.

Intune, Android iş profili cihazlarında yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. Daha fazla bilgi için bkz. [Android iş profili cihazlarında ilke ayarları](compliance-policy-create-android-for-work.md).

## <a name="app-publishing-and-distribution"></a>Uygulama yayımlama ve dağıtma

Yönetilen Google Play Android Kurumsal uygulama dağıtımı ve yönetiminin önemli bir parçasıdır. İş profilindeki Kurumsal Android iş profili cihazları için dağıtılan tüm uygulamalar yönetilen Google Play hizmetinden gelir. Play Store’daki uygulamaları yönetmek ve dağıtmak için Google Play web sitesinde şirketinizin Google yönetimi yönetici kimlik bilgileriyle oturum açarsınız. Uygulamaları bunları cihazlarınızın iş profillerinde görünmesini sağlamak Android kurumsal dağıtım için onaylayabilirsiniz. Ardından bu uygulamalar Intune konsoluna eşitlenir ve burada Intune kullanılarak dağıtılıp yönetilebilir. Kuruluşunuz tarafından geliştirilen iş kolu (LOB) uygulamalarının Google’ın Android uygulama yayımlama konsolu kullanılarak Yönetilen Google Play’de yayımlanması gerekir. İş kolu uygulamalarının, kuruluşunuza erişimi kısıtlamak için Android uygulama yayımlama konsolunda yapılandırılması gerekir.

Uygulamalar kullanıcı etkileşimi olmadan ve kullanıcının **Bilinmeyen Kaynaklardan Yükleme**'ye izin vermesine gerek kalmadan yüklenebilir. İsteğe bağlı veya kullanılabilir uygulamalara göz atmak ve onları yüklemek için kullanıcı cihazındaki Play for Work mağazasını gözden geçirebilir. Daha fazla bilgi için [iş profili cihazları Intune ile Android Kurumsal uygulamaları atama](apps-add-android-for-work.md).

## <a name="app-configuration"></a>Uygulama yapılandırması

Android Kurumsal uygulama yapılandırma değerlerini bunları destekleyen uygulamalara dağıtmak için altyapı sağlar. İş uygulamaları için yapılandırma değerlerini belirterek, kullanıcılar uygulamayı ilk kez başlattığında bunların düzgün ayarlandığından emin olursunuz. Uygulama yapılandırması desteği için uygulama geliştiricilerinin kendi Android uygulamalarını yönetilen yapılandırma değerlerini spesifik olarak destekleyecek şekilde oluşturmaları gerekir. Eğer öyleyse, bu yapılandırma ayarlarını belirtmek ve uygulamak için Intune kullanabilirsiniz. Daha fazla bilgi için bkz. [Yönetilen Android cihazlar için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-android.md).

## <a name="email-configuration"></a>E-posta yapılandırması

Android kurumsal bir varsayılan e-posta uygulaması veya iOS tarafından sağlanan gibi yerel e-posta profili nesnesi sağlamaz. Bunun yerine, e-posta yapılandırmaları kendilerini destekleyen e-posta uygulamalarına uygulama yapılandırma ayarları uygulayarak ayarlanabilir. Gmail ve Nine Work Android Kurumsal Uygulama yapılandırması ile yapılandırmayı destekleyen iki Exchange ActiveSync (EAS) istemci Play Store içinde uygulamalardır.

Intune, iş uygulamaları olarak yönetildiklerinde Gmail ve Nine Work uygulamaları için yapılandırma şablonları sağlar. Uygulama yapılandırma profillerini destekleyen diğer e-posta uygulamaları mobil uygulama yapılandırma ilkeleriyle yapılandırılabilir.

Android kurumsal iş profili cihaz için Exchange ActiveSync koşullu erişim kullanıyorsanız, Gmail veya Nine Work e-posta uygulamasını kullanarak göz önünde bulundurun. Android için Microsoft Outlook uygulaması veya ADAL ile modern kimlik doğrulaması kullanan herhangi bir e-posta uygulaması da desteklenir. Daha fazla bilgi için bkz. [Microsoft Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md).

## <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

Uygulaman uygulama koruma ilkeleri, iş profilinde ve kişisel profilde tümüyle desteklenir. İş kolu uygulamalarını, https://play.google.com/apps/publish adresindeki Android uygulama yayımlama konsolunda yayımlayabilirsiniz. Bu konsol, uygulamaları kuruluşunuza özel hale getirme seçeneğine sahiptir. Daha fazla bilgi için [Intune'da Android kurumsal iş profili cihazları için cihaz uyumluluk ilkesi ekleme](compliance-policy-create-android-for-work.md). Uygulama koruma ilkeleri hakkında genel bilgiler için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

## <a name="vpn-profiles"></a>VPN profilleri

VPN desteği, Android VPN profillerine benzerdir. Aynı VPN sağlayıcıları ve temel yapılandırma seçenekleri Android kuruluş yönetimi iki fark için kullanılabilir:

-  **İş profili kapsamlı VPN** – VPN bağlantıları yalnızca iş profiline dağıtılan uygulamalarla sınırlıdır. Yalnızca Android Kurumsal ilkeyle yönetilen uygulamalar VPN bağlantısını kullanabilir. Cihazdaki kişisel uygulamalar bir yönetilen VPN bağlantısı kullanamaz. Daha fazla bilgi için [Android Kurumsal VPN ayarları](vpn-settings-android.md#android-enterprise-vpn-settings).

-  **Uygulamaya özel VPN** – Uygulamaya özel VPN, VPN sağlayıcısı bunu destekliyorsa Intune’da yapılandırılabilir:
    - uygulamaya özel VPN yapılandırması
    - Android Kurumsal uygulama yapılandırma profili aracılığıyla uygulama başına VPN yapılandırma yeteneği.
    Daha fazla bilgi için bkz. [Microsoft Intune özel profili kullanarak Android cihazlar için uygulama başına VPN profili oluşturma](android-pulse-secure-per-app-vpn.md).

## <a name="certificate-profiles"></a>Sertifika profilleri

Android yönetimi için kullanılabilir olan sertifika profili yapılandırma seçenekleri Android kurumsal iş profili cihazları üzerinde kullanılabilir. Android Kurumsal gelişmiş sertifika yönetimi API'leri sağlar. Gelişmiş sertifika yönetimi aşağıdaki işlevleri sağlar:

-  Sertifika dağıtımının sessiz ve kullanıcı için sorunsuz olmasını sağlar.
-  Bir cihaz Intune’da devre dışı bırakıldığında ve iş profili kaldırıldığında dağıtılan sertifikaların kaldırılmasını sağlar.
-  BT departmanı tarafından yönetim hizmeti aracılığıyla sertifikanın dağıtıldığını ve yapılandırıldığını kullanıcılara bildiren gelişmiş iletiler sağlar.

Daha fazla bilgi için bkz. [Microsoft Intune’da cihazlarınız için sertifika profili yapılandırma](certificates-configure.md).

## <a name="wi-fi-profiles"></a>Wi-Fi profilleri

Cihaz Intune'da kullanımdan kaldırıldığında ve iş profili silindiğinde Android kuruluş tarafından yönetilen Wi-Fi profilleri kaldırılır. Daha fazla bilgi için bkz. [Microsoft Intune’da Wi-Fi ayarlarını yapılandırma](wi-fi-settings-configure.md).

## <a name="next-steps"></a>Sonraki adımlar
- [Android cihazlarını kaydetme](android-enroll.md)
- [Android kurumsal iş profili cihazları Intune ile uygulamaları atama](apps-add-android-for-work.md)
