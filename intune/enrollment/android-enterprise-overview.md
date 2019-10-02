---
title: Microsoft Intune 'de Android kurumsal iş profili cihazlarını yönetme
titleSuffix: ''
description: Microsoft Intune, kullanıcılar kişisel Android cihazlarını iş için kullandıklarında ek yönetim özellikleri ve gizliliği sağlamak üzere Android kurumsal iş profili cihazlarını yönetir.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 89baddf3fcaec9379765facd547d4e6c8133ef8b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730089"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Intune ile Android iş profili cihazlarını yönetme

Android Enterprise, kullanıcılara en güncel ve güvenli özellikleri sağlayan bir kayıt seçenekleri kümesi sunar. Android kurumsal iş profiliyle kaydetme, kişisel uygulamaları ve verileri iş uygulamaları ve verilerinden ayıran bir dizi özellik ve hizmeti sağlar. Ayrıca insanlar kişisel Android cihazlarını iş için kullandıklarında ek yönetim özellikleri ve gizlilik sağlar. 

## <a name="supported-devices"></a>Desteklenen cihazlar

Android kurumsal yönetim özellikleri, daha yeni Android işletim sistemlerinin parçası olan özelliklerden yararlanır. Android Enterprise 'ı desteklemeyen cihazlar için geleneksel Android yönetimi kullanılabilir kalır. Daha fazla bilgi için bkz. [Android Enterprise Requirements](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Ekleme

Android kurumsal iş profili cihazlarını kaydetmeden önce bazı ekleme adımlarını gerçekleştirmeniz gerekir. Bu adımlar, Intune kiracınız ile yönetilen Google Play arasında bir bağlantı kurar. Daha fazla bilgi için bkz. [Android kurumsal iş profili cihazlarının kaydını etkinleştirme](android-work-profile-enroll.md).

## <a name="work-profile-management"></a>İş profili yönetimi

Intune ile bir Android kurumsal iş profili cihazını yönetirken, tüm cihazı yönetmezsiniz. Yönetim yetenekleri yalnızca kayıt sırasında cihazda oluşturulan iş profilini etkiler. Intune ile cihaza dağıtılan tüm uygulamalar, iş profiline yüklenir. İş profilindeki uygulama simgeleri, cihazdaki kişisel uygulamalardan farklıdır. Cihazın Android iş profili bölümü dışındaki tüm Android uygulama ve verileri, kişiseldir ve son kullanıcının denetimindedir. Kullanıcılar, cihazın kişisel kısmına istedikleri uygulamaları yükleyebilir. Yöneticiler ise iş profili kapsamındaki tüm uygulamaları yönetebilir ve izleyebilir.

Intune, Android iş profili cihazlarında yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. Daha fazla bilgi için bkz. [Android iş profili cihazlarında ilke ayarları](../protect/compliance-policy-create-android-for-work.md).

## <a name="app-publishing-and-distribution"></a>Uygulama yayımlama ve dağıtma

Yönetilen Google Play, Android kurumsal uygulama dağıtımı ve yönetiminin ayrılmaz bir parçasıdır. İş profilindeki Android kurumsal iş profili cihazlarına dağıtılan tüm uygulamalar, yönetilen Google Play hizmetinden gelir. Play Store’daki uygulamaları yönetmek ve dağıtmak için Google Play web sitesinde şirketinizin Google yönetimi yönetici kimlik bilgileriyle oturum açarsınız. Android kurumsal dağıtım için uygulamaları, cihazların iş profillerinde görünmesini sağlamak üzere onaylayabilirsiniz. Ardından bu uygulamalar Intune konsoluna eşitlenir ve burada Intune kullanılarak dağıtılıp yönetilebilir. Kuruluşunuz tarafından geliştirilen iş kolu (LOB) uygulamalarının Google’ın Android uygulama yayımlama konsolu kullanılarak Yönetilen Google Play’de yayımlanması gerekir. İş kolu uygulamalarının, kuruluşunuza erişimi kısıtlamak için Android uygulama yayımlama konsolunda yapılandırılması gerekir.

Uygulamalar kullanıcı etkileşimi olmadan ve kullanıcının **Bilinmeyen Kaynaklardan Yükleme**'ye izin vermesine gerek kalmadan yüklenebilir. İsteğe bağlı veya kullanılabilir uygulamalara göz atmak ve onları yüklemek için kullanıcı cihazındaki Play for Work mağazasını gözden geçirebilir. Daha fazla bilgi için bkz. [Intune Ile Android Enterprise iş profili cihazlarına uygulama atama](../apps/apps-add-android-for-work.md).

## <a name="app-configuration"></a>Uygulama yapılandırması

Android Enterprise, uygulama yapılandırma değerlerini onları destekleyen uygulamalara dağıtmak için altyapı sağlar. İş uygulamaları için yapılandırma değerlerini belirterek, kullanıcılar uygulamayı ilk kez başlattığında bunların düzgün ayarlandığından emin olursunuz. Uygulama yapılandırması desteği için uygulama geliştiricilerinin kendi Android uygulamalarını yönetilen yapılandırma değerlerini spesifik olarak destekleyecek şekilde oluşturmaları gerekir. Eğer öyleyse, bu yapılandırma ayarlarını belirtmek ve uygulamak için Intune kullanabilirsiniz. Daha fazla bilgi için bkz. [Yönetilen Android cihazlar için uygulama yapılandırma ilkeleri ekleme](../apps/app-configuration-policies-use-android.md).

## <a name="email-configuration"></a>E-posta yapılandırması

Android Enterprise, iOS tarafından sağlananlar gibi varsayılan bir e-posta uygulaması veya yerel e-posta profili nesnesi sağlamaz. Bunun yerine, e-posta yapılandırmaları kendilerini destekleyen e-posta uygulamalarına uygulama yapılandırma ayarları uygulayarak ayarlanabilir. Gmail ve dokuz Iş, Android Enterprise App Configuration ile yapılandırmayı destekleyen Play Store iki Exchange ActiveSync (EAS) istemci uygulamasıdır.

Intune, iş uygulamaları olarak yönetildiklerinde Gmail ve Nine Work uygulamaları için yapılandırma şablonları sağlar. Uygulama yapılandırma profillerini destekleyen diğer e-posta uygulamaları mobil uygulama yapılandırma ilkeleriyle yapılandırılabilir.

Android kurumsal iş profili cihazı için Exchange ActiveSync koşullu erişimi kullanıyorsanız Gmail veya dokuz Iş e-posta uygulamasını kullanmayı düşünün. Android için Microsoft Outlook uygulaması veya ADAL ile modern kimlik doğrulaması kullanan herhangi bir e-posta uygulaması da desteklenir. Daha fazla bilgi için bkz. [Microsoft Intune’da e-posta ayarlarını yapılandırma](../configuration/email-settings-configure.md).

## <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

Uygulaman uygulama koruma ilkeleri, iş profilinde ve kişisel profilde tümüyle desteklenir. İş kolu uygulamalarını, https://play.google.com/apps/publish adresindeki Android uygulama yayımlama konsolunda yayımlayabilirsiniz. Bu konsol, uygulamaları kuruluşunuza özel hale getirme seçeneğine sahiptir. Daha fazla bilgi için bkz. [Intune 'Da Android kurumsal iş profili cihazları için cihaz uyumluluk Ilkesi ekleme](../protect/compliance-policy-create-android-for-work.md). Uygulama koruma ilkeleri hakkında genel bilgiler için bkz. [Uygulama koruma ilkeleri nelerdir?](../apps/app-protection-policy.md)

## <a name="vpn-profiles"></a>VPN profilleri

VPN desteği, Android VPN profillerine benzerdir. Aynı VPN sağlayıcıları ve temel yapılandırma seçenekleri, Android Kurumsal Yönetimi için iki fark ile kullanılabilir:

- **İş profili kapsamlı VPN** – VPN bağlantıları yalnızca iş profiline dağıtılan uygulamalarla sınırlıdır. Yalnızca Android Enterıse tarafından yönetilen uygulamalar VPN bağlantısını kullanabilir. Cihazdaki kişisel uygulamalar bir yönetilen VPN bağlantısı kullanamaz. Daha fazla bilgi için bkz. [Android ENTERPRISE VPN ayarları](../configuration/vpn-settings-android-enterprise.md).

- **Uygulamaya özel VPN** – Uygulamaya özel VPN, VPN sağlayıcısı bunu destekliyorsa Intune’da yapılandırılabilir:
  - uygulamaya özel VPN yapılandırması
  - Android kurumsal uygulama yapılandırma profili aracılığıyla uygulama başına VPN yapılandırma özelliği.
  Daha fazla bilgi için bkz. [Microsoft Intune özel profili kullanarak Android cihazlar için uygulama başına VPN profili oluşturma](../configuration/android-pulse-secure-per-app-vpn.md).

## <a name="certificate-profiles"></a>Sertifika profilleri

Android yönetimi için kullanılabilir olan sertifika profili yapılandırma seçenekleri Android kurumsal iş profili cihazlarında kullanılabilir. Android Enterprise, gelişmiş sertifika yönetimi API 'Leri sağlar. Gelişmiş sertifika yönetimi aşağıdaki işlevleri sağlar:

- Sertifika dağıtımının sessiz ve kullanıcı için sorunsuz olmasını sağlar.
- Bir cihaz Intune’da devre dışı bırakıldığında ve iş profili kaldırıldığında dağıtılan sertifikaların kaldırılmasını sağlar.
- BT departmanı tarafından yönetim hizmeti aracılığıyla sertifikanın dağıtıldığını ve yapılandırıldığını kullanıcılara bildiren gelişmiş iletiler sağlar.

Daha fazla bilgi için bkz. [Microsoft Intune’da cihazlarınız için sertifika profili yapılandırma](../protect/certificates-configure.md).

## <a name="wi-fi-profiles"></a>Wi-Fi profilleri

Cihaz Intune 'dan kullanımdan kaldırıldığında ve iş profili silindiğinde, Android Enterprise tarafından yönetilen Wi-Fi profilleri kaldırılır. Daha fazla bilgi için bkz. [Microsoft Intune’da Wi-Fi ayarlarını yapılandırma](../configuration/wi-fi-settings-configure.md).

## <a name="next-steps"></a>Sonraki adımlar
- [Android cihazlarını kaydetme](android-enroll.md)
- [Intune ile Android Enterprise iş profili cihazlarına uygulama atama](../apps/apps-add-android-for-work.md)
