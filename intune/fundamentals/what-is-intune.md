---
title: Microsoft Intune-Azure | Microsoft Docs
description: Microsoft Intune Enterprise Mobility + Security çözümünün mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) bileşeni ve şirket verilerini korumanıza nasıl yardımcı olduğu hakkında bilgi edinin.
keywords: Intune nedir?
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/14/2019
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
ms.openlocfilehash: 56c76663330cae5cb771358542fd22ff09398118
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314742"
---
# <a name="microsoft-intune-is-an-mdm-and-mam-provider-for-your-devices"></a>Microsoft Intune, cihazlarınız için MDM ve MAM sağlayıcısıdır

Microsoft Intune, mobil cihaz yönetimine (MDM) ve mobil uygulama yönetimine (MAM) odaklanan bulut tabanlı bir hizmettir. Intune, Microsoft 'un [Enterprise Mobility + Security (EMS) Suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)'e dahil edilmiştir ve kuruluşunuzun verilerinin korunmasını sağlarken kullanıcıların üretken olmalarını sağlar. Kimlerin erişebileceğini ve ne erişimleri olduğunu denetlemek için Microsoft 365 ve Azure Active Directory (Azure AD) dahil diğer hizmetlerle tümleştirilir ve veri koruma için Azure Information Protection. Microsoft 365 ile birlikte kullandığınızda, iş gücünüzün tüm cihazlarında üretken olmasını sağlayarak kuruluşunuzun bilgilerini korumalı hale getirebilirsiniz.

![Intune mimarisinin görüntüsü](./media/what-is-intune/intunearch_sm.png)

Intune mimari diyagramının [daha büyük bir sürümünü](./media/what-is-intune/intunearchitecture.svg) görüntüleyin.

Intune ile şunları yapabilirsiniz:

- Intune ile %100 bulut veya Configuration Manager ile Intune ile [birlikte yönetilen](https://docs.microsoft.com/sccm/comanage/overview) bir şekilde seçin.
- Verilere ve ağlara erişmek için kuralları ayarlayın ve kişisel ve kuruluşa ait cihazlarda ayarları yapılandırın.
- Şirket içi ve mobil cihazlarda uygulamaları dağıtın ve kimlik doğrulaması yapın.
- Kullanıcıların bilgilere erişme ve paylaşma şeklini denetleyerek şirket bilgilerinizi koruyun.
- Cihazların ve uygulamaların güvenlik gereksinimlerle uyumlu olduğundan emin olun.

## <a name="manage-devices"></a>Cihazları yönetme

Intune 'da, sizin için doğru olan bir yaklaşımı kullanarak cihazları yönetirsiniz. Kuruluşa ait cihazlar için, ayarlar, Özellikler ve güvenlik dahil olmak üzere cihazlarda tam denetim yapmak isteyebilirsiniz. Bu yaklaşımda, cihazlar ve bu cihazların kullanıcıları Intune 'da "kaydolmalıdır". Kaydolduktan sonra, kurallarınızı ve ayarlarınızı Intune 'da yapılandırılmış ilkeler aracılığıyla alırlar. Örneğin, parola ve PIN gereksinimlerini ayarlayabilir, bir VPN bağlantısı oluşturabilir, tehdit koruması ayarlayabilir ve daha fazlasını yapabilirsiniz.

Kişisel cihazlar veya kendi cihazlarını getir (KCG) için, kullanıcılar kuruluş yöneticilerinin tam denetime sahip olmasını istemiyor olabilir. Bu yaklaşımda kullanıcılara seçenekler verin. Örneğin, kullanıcılar, kuruluş kaynaklarınıza tam erişim istediklerinde cihazlarını [kaydeder](../enrollment/device-enrollment.md) . Ya da bu kullanıcılar yalnızca e-posta veya Microsoft ekiplerine erişim gerektiriyorsa, bu uygulamaları kullanmak için çok faktörlü kimlik doğrulaması (MFA) gerektiren uygulama koruma ilkelerini kullanın.

Cihazlar Intune 'A kaydedildiğinde ve yönetildiğinde yöneticiler şunları yapabilir:

- Kaydedilen cihazları görün ve kuruluş kaynaklarına erişen cihazların envanterini alın.
- Cihazları güvenlik ve sistem durumu standartlarınızı karşılayacak şekilde yapılandırın. Örneğin, büyük olasılıkla jailbreak uygulanmış cihazlarını engellemek isteyebilirsiniz.
- Kullanıcıların Wi-Fi ağınıza kolayca erişebilmeleri için sertifikaları cihazlara gönderin veya ağınıza bağlanmak için bir VPN kullanın.
- Uyumlu ve uyumlu olmayan kullanıcılar ve cihazlar hakkındaki raporlara bakın.
- Bir cihaz kaybolduğunda, çalınırsa veya artık kullanılmıyorsa kuruluş verilerini kaldırın.

**Çevrimiçi kaynaklar**:

- [Cihaz kaydı nedir?](../enrollment/device-enrollment.md)

- [Cihaz profillerini kullanarak cihazlarınızda Özellikler ve ayarlar uygulama](../configuration/device-profiles.md)

- [Microsoft Intune ile cihaz koruma](../protect/device-protect.md)

## <a name="manage-apps"></a>Uygulamaları yönetme

Intune 'daki mobil uygulama yönetimi (MAM), özel uygulamalar ve Mağaza uygulamaları dahil olmak üzere uygulama düzeyinde kuruluş verilerini korumak için tasarlanmıştır. Uygulama yönetimi, kuruluşa ait cihazlarda ve kişisel cihazlarda kullanılabilir.

Uygulamalar Intune 'da yönetildiğinde yöneticiler şunları yapabilir:

- Belirli gruplardaki kullanıcılar, belirli gruplardaki cihazlar ve daha fazlası dahil olmak üzere Kullanıcı gruplarına ve cihazlarına mobil uygulamalar ekleyin ve atayın.
- Uygulamaları, belirli ayarları etkin olarak başlatılacak veya çalıştıracak şekilde yapılandırın ve cihazda zaten var olan uygulamaları güncelleştirin.
- Uygulamaların kullanıldığı raporlara bakın ve kullanımlarını izleyin.
- Yalnızca uygulamalardan kuruluş verilerini kaldırarak seçmeli silme işlemi yapın.

Intune 'un mobil uygulama güvenliği sağladığı yollardan biri, **[Uygulama koruma ilkeleri](../apps/app-protection-policy.md)** kullanmaktır. Uygulama koruma ilkeleri:

- Kurumsal verileri kişisel verilerden yalıtmak için Azure AD kimliği ' ni kullanın. Bu nedenle, kişisel bilgiler kurumsal BT tanıma 'dan yalıtılmıştır. Kuruluş kimlik bilgileri kullanılarak erişilen verilere ek güvenlik koruması verilir.
- Kopyalama ve yapıştırma, kaydetme ve görüntüleme gibi eylemlerin gerçekleştirebileceği eylemleri kısıtlayarak kişisel cihazlara erişimi güvenli hale getirmeye yardımcı olun.
- Intune 'a kayıtlı, başka bir MDM hizmetine kayıtlı veya herhangi bir MDM hizmetine kayıtlı olmayan cihazlarda oluşturulabilir ve dağıtılabilir. Kayıtlı cihazlarda, uygulama koruma ilkeleri ek bir koruma katmanı ekleyebilir.

Örneğin, bir Kullanıcı bir cihazda kuruluş kimlik bilgileriyle oturum açar. Kuruluş kimlikleri, kişisel kimlikleri için reddedilmiş verilere erişim sağlar. Bu kuruluş verileri kullanıldığında, uygulama koruma ilkeleri verilerin nasıl kaydedildiğini ve paylaşıldığını denetler. Kullanıcılar kendi kişisel kimliğiyle oturum açtığında, aynı korumalar uygulanmaz. Bu şekilde, son kullanıcılar kendi kişisel verileri üzerinde denetim ve gizliliği koruurken, kuruluş verilerinin denetimini içerir.

Aynı şekilde, Intune 'u EMS 'deki diğer hizmetlerle de kullanabilirsiniz. Bu özellik, kuruluşunuzun mobil uygulama güvenliğini işletim sistemine ve tüm uygulamalara dahil nelerin ötesinde sağlar. EMS ile yönetilen uygulamaların daha geniş bir mobil uygulama ve veri koruma özellikleri kümesine erişimi vardır.

![Uygulama yönetimi veri güvenliği düzeylerini gösteren resim](./media/what-is-intune/managing-mobile-apps.png)

## <a name="compliance-and-conditional-access"></a>Uyumluluk ve koşullu erişim

Intune, çok sayıda erişim denetimi senaryosunu etkinleştirmek için Azure AD ile tümleşir. Örneğin, mobil cihazların e-posta veya SharePoint gibi ağ kaynaklarına erişmeden önce Intune 'da tanımlanan kuruluş standartları ile uyumlu olmasını gerektir. Benzer şekilde, hizmetleri yalnızca belirli bir mobil uygulama kümesi için kullanılabilir olacak şekilde kapatabilirsiniz. Örneğin, Exchange Online 'ı yalnızca Outlook veya Outlook Mobile tarafından erişilen şekilde kapatabilirsiniz.

**Çevrimiçi kaynaklar**:

- [Cihazlarda kuruluşunuzun kaynaklarına erişime izin vermek için kurallar ayarlama](../protect/device-compliance-get-started.md)

- [Intune ile koşullu erişim kullanmanın yaygın yolları](../protect/conditional-access-intune-common-ways-use.md)

## <a name="how-to-get-intune"></a>Intune alma

Intune kullanılabilir:

- Tek başına [Azure hizmeti](https://go.microsoft.com/fwlink/?linkid=2090973) olarak
- [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune) ve [Microsoft 365 Kamu](https://www.microsoft.com/microsoft-365/government) ile birlikte
- Bazı sınırlı Intune özelliklerinden oluşan [Office 365 ' de mobil cihaz yönetimi](https://support.office.com/article/choose-between-mdm-for-office-365-and-microsoft-intune-c93d9ab9-efb2-4349-9b93-30c30562ee22)olarak

Intune, [kamu](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description), [eğitim](https://www.microsoft.com/en-us/education/intune), [bilgi noktası veya](../configuration/kiosk-settings.md) üretim ve perakende için adanmış cihaz gibi birçok sektörde kullanılır ve daha fazlasını yapın.

## <a name="next-steps"></a>Sonraki adımlar

- [Intune 'un çözmesine yardımcı olduğu yaygın iş sorunlarından](https://docs.microsoft.com/intune/common-scenarios)bazılarını okuyun.
- [Intune 'un 30 günlük deneme sürümü](free-trial-sign-up.md)ile başlayın.
- [Intune 'a geçişinizi](migration-guide.md)planlayın.
- Ücretsiz deneme sürümünüzü veya aboneliğinizi kullanarak, [hızlı başlangıç: iOS için bir e-posta cihaz profili oluşturun](../configuration/quickstart-email-profile.md).
