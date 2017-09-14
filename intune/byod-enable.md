---
title: "Microsoft Intune’da KCG’yi etkinleştirme"
description: "Kuruluşunuzda Kendi Cihazını Getir (KCG) çözümünü etkinleştirmek üzere Intune’u ayarlamanız için yüksek düzey bir iş akışı."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: f4e414f3696c64f8ea450394928aa055ad427afd
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="enable-byod-with-intune"></a>Intune ile KCG'yi Etkinleştirme

Bu konu, kuruluşunuzda Kendi cihazını Getir (KCG) çözümünü etkinleştirmek üzere Intune’u ayarlamanız için yüksek düzey bir iş akışı sağlar. Görev, üç işleme ayrılır ve “Nasıl Yapılır?” konularına giden destekleyici bağlantılar sağlanır.

İş akışı aşağıdaki gibi üç işleme ayrılmıştır. Kuruluşunuzun gereksinimlerine göre süreçlerde değişiklik yapabilirsiniz.

-   **[Cihazları kaydetme ve uyumluluğu denetleme](#enroll-devices-and-check-for-compliance)**, kullanıcıların kişisel cihazlarını Intune yönetimine nasıl kaydedeceğini açıklar. Intune; iOS, macOS, Android ve Windows cihazları yönetebilir. Bu bölüm ayrıca, cihazlara nasıl ilke dağıtılacağını açıklar ve cihazların temel güvenlik gereksinimlerini karşıladığından emin olmanıza yardımcı olur.

- **[Şirket kaynaklarına erişim sağlama](#provide-access-to-company-resources)** işlemi, kullanıcıların şirket kaynaklarına kolay ve güvenli erişimi nasıl sağlayacağınızı gösterir. Bunu, yönetilen cihazlara erişim profilleri dağıtarak yaparsınız. Bu bölüm ayrıca toplu satın alınan uygulama dağıtımlarını Intune’da nasıl yöneteceğinizi açıklar.

-   **[Şirket verilerini koruma](#protect-company-data)**, şirket kaynaklarına koşullu erişim sağlamayı, veri kaybını önlemeyi ve şirket uygulama ve verileri, iş için artık gerekli olmadığında veya kaybedildiğinde/çalındığında bunların nasıl kaldırılacağını öğrenmenize yardımcı olur.

[![Microsoft Intune’da KCG’yi etkinleştirmek için yüksek düzey iş akışı diyagramı](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Başlamadan önce
Kullanıcıların cihazlarını kaydetmesi için önce Intune hizmetini hazırlamanız gerekir. Bunu yapmak için [kullanıcılara lisans atayın](licenses-assign.md) ve [mobil cihaz yönetim yetkilisini ayarlayın](mdm-authority-set.md).

Başlamışken [şirket portalını da özelleştirebilirsiniz](company-portal-customize.md). Şirket markasını ekleyin ve kullanıcılar için destek bilgileri sağlayın. Böylece kullanıcılarınıza güvenilir bir kayıt ve destek deneyimi sunabilirsiniz. Kullanıcıların, kaydolmadan önce kabul etmesi gereken [kullanım koşulları](terms-and-conditions-create.md) oluşturabilir veya desteklediğiniz platformu belirlemek için [cihaz kısıtlamaları](enrollment-restrictions-set.md) uygulayabilirsiniz.

## <a name="enroll-devices-and-check-for-compliance"></a>Cihazları kaydetme ve uyumluluk denetimi yapma

Intune hizmetini hazırladıktan sonra, yönetmek istediğiniz cihaz türleri için çeşitli kayıt gereksinimlerini karşılamanız gerekir. Cihazları yönetime kaydetme işlemi oldukça basittir ancak çeşitli cihaz türlerine göre biraz farklılık gösterir.

-   **iOS ve Mac cihazlar** iPad, iPhone veya macOS cihazları kaydetmek için [bir Apple MDM anında iletme sertifikası almanız](apple-mdm-push-certificate-get.md) gerekir. MDM anında iletme sertifikanızı Intune’a yükledikten sonra kullanıcılar, [iOS cihazlarını kaydetmek](/intune-user-help/enroll-your-device-in-intune-ios) için Şirket Portalı uygulamasını, [MacOS cihazlarını kaydetmek](/intune-user-help/enroll-your-device-in-intune-macos) içinse Şirket Portalı web sitesini kullanabilir.

-   **Android cihazlar** Intune hizmetini Android cihazların kaydına hazır hale getirmek için yapmanız gereken bir şey yoktur. Kullanıcılar Google Play’den edinilebilecek Şirket Portalı uygulamasını kullanarak [Android cihazlarını yönetime kaydedebilir](/intune-user-help/enroll-your-device-in-intune-android).

-   **Windows Phone ve bilgisayarlar** Windows cihazlar ek yapılandırma ile kaydedilebilir. Azure Active Directory (AD) Premium’da Windows 10 bilgisayarlar ve Windows 10 mobil cihazlar için otomatik kaydı etkinleştirerek kullanıcılarınızın deneyimini kolaylaştırabilirsiniz. Azure AD Premium’a sahip değilseniz veya Windows 8.1’i desteklemeniz gerekiyorsa kaydı kolaylaştırmak üzere [kayıt sunucusu için bir DNS diğer adı](windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium) oluşturabilirsiniz.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Yönetilen cihazların, temel güvenlik gereksinimlerini karşıladığından emin olma

Kullanıcılar cihazlarını yönetime kaydettikten sonra BT çalışanlarının, şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların temel güvenlik gereksinimlerini karşıladığından emin olmaları gerekir. Bu kurallar, cihazlara ve cihazlarda depolanan şifreleme verilerine erişmek için bir PIN kullanmayı içerebilir. Bu tür bir kurallar kümesine [uyumluluk ilkesi](device-compliance.md) adı verilir.

Bir kullanıcıya [uyumluluk ilkesi dağıttığınızda](device-compliance-get-started.md) Intune, KCG ilkenizin bir parçası olarak tanımladığınız temel güvenlik gereksinimlerine uyup uymadıklarını görmek için kullanıcının Intune tarafından yönetilen tüm cihazlarını kontrol eder. İlke uyumluluk değerlendirmesi yapılan cihazın durumu, Intune hizmetine bildirilir. Bazen kullanıcıların, PIN veya cihaz şifreleme gibi ayarları düzeltmeleri istenebilir. Bunun dışında şirket portalı uygulaması, ilkenize uymayan herhangi bir ayarı yalnızca kullanıcıya bildirir.

## <a name="provide-access-to-company-resources"></a>Şirket kaynaklarına erişim sağlama

Çalışanlarınızın çoğu, mobil cihazlarından ilk olarak şirket e-posta ve belgelerine erişmek ister. Bunu, karmaşık adımlarla uğraşmadan veya yardım masasını aramadan ayarlamayı beklerler. Intune, mobil cihazlara önceden yüklenen yerel e-posta uygulamaları için [e-posta ayarları oluşturup dağıtmanızı](email-settings-configure.md) kolaylaştırır.


> [!NOTE]
> Intune, Google Play mağazasında bulunan Gmail ve Nine Work e-posta uygulamaları için İş için Android e-posta profili yapılandırmasını destekler.

Intune ayrıca, kullanıcılar dışarıda çalıştığında şirket içi şirket verilerine erişimi denetlemenize ve korumanıza yardımcı olur. Intune [Wi-Fi](wi-fi-settings-configure.md), [VPN](vpn-settings-configure.md) ve e-posta profilleri birlikte çalışarak, işlerini nerede olursa olsun yapmak için ihtiyaç duydukları dosyalara ve kaynaklara erişim izni verir. Azure Active Directory Uygulama Proxy'si ve koşullu erişim kullanarak şirketinizin şirket içinde barındırılan web uygulamaları ve hizmetlerinin de erişim güvenliği ve koruması sağlanabilir.

### <a name="manage-volume-purchased-apps"></a>Toplu satın alınan uygulamaları yönetme
Intune ile şunları kolayca yapabilirsiniz:
* Herhangi bir uygulama mağazasından toplu lisans bilgisini içeri aktarma
* Kaç lisans kullandığınızı takip etme
* Kullanıcılarınızın, sahip olduğunuz uygulamanın birden fazla kopyasını indirmelerini önleme
* [Mağaza uygulamalarını yönetilen cihazlara gönderme](apps-deploy.md)
* Şirket portalı web sitesini kullanarak uygulamaları, yönetilmeyen cihazlara gönderme

Ayrıca, iOS uygulama mağazasından ve İş İçin Microsoft Mağazası’ndan toplu olarak satın aldığınız uygulamaları Intune ile yönetebilirsiniz. Bu durum, toplu satın alınan uygulamaları izlemeye yönelik yönetim yükünü azaltmanıza yardımcı olabilir.

> [!TIP]
> [Azure AD Connect ile Çoklu Oturum Açma’yı (SSO) yapılandırabilirsiniz](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). SSO ile kullanıcılar, şirkette kullandıkları etki alanı kullanıcı adı ve parolaları ile uygulamalarda oturum açabilir. Ayrıca Azure Active Directory Uygulama Proxy’si ile [şirket içinde barındırılan web uygulamalarına İnternet üzerinden erişim sağlayabilirsiniz](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [iOS cihazları için toplu satın alınan uygulamaları yönetme](vpp-apps-ios.md). [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ile iOS için birden çok lisans satın alabilirsiniz. Apple web sitesinden bir Apple VPP hesabı ayarlamanız ve Apple VPP belirtecini Intune’a yüklemeniz gerekir. Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

-   [İş İçin Microsoft Mağazası’ndan satın alınan uygulamaları yönetme](windows-store-for-business.md). [İş İçin Microsoft Mağazası](https://www.microsoft.com/business-store), kuruluşunuz için uygulamaları tek tek veya toplu olarak bulabileceğiniz ve satın alabileceğiniz bir yerdir. Mağazayı Intune’a bağlayarak, toplu satın alınan uygulamaları Azure portalından yönetebilirsiniz.

## <a name="protect-company-data"></a>Şirket verilerini koruma

Intune, şirket verilerini pek çok teknoloji katmanıyla korur. Kimlik katmanında koşullu erişim, hizmetlere erişimi korur. Koşullu erişim, yalnızca yönetilen ve uyumlu cihazların şirket kaynaklarına erişmesine izin verir. Uygulama koruma ilkeleri, istemci uygulama katmanında veri kaybına karşı koruma sağlar. Uygulama koruma ilkeleri, verilerin korunmayan uygulamalara veya depolama konumlarına taşınmasını engeller. Bu ilkeler ayrıca, bir cihaz kaybolduğunda veya çalındığında tüm şirket verilerini silmenize imkan tanır.

### <a name="enforce-conditional-access-to-company-resources"></a>Şirket kaynaklarına koşullu erişimi zorunlu kılma

Uyumluluk ilkelerini [koşullu erişim ilkeleriyle](device-compliance.md) birlikte kullanarak cihazların KCG ilkenizle belirlenen temel güvenlik gereksinimlerini karşılayıp karşılamadığını denetleyebilirsiniz. Bir cihaz bu gereksinimleri karşılamıyorsa kurallar uygulamaya girer ve cihaz, ilke gereksinimlerine uyum sağlayana kadar erişim engellenir. Bu seçenek, yalnızca yönetilen ve uyumlu cihazların Exchange ([Şirket içi Exchange](exchange-connector-install.md) veya [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype Kurumsal Çevrimiçi Sürüm gibi hizmetlerden şirket verilerine erişmesini sağlar.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Uyumluluğu doğrulayacak herhangi bir uyumluluk ilkesi yoksa koşullu erişim ilkeleri çalışmaz.

### <a name="prevent-data-loss-of-company-data-with-app-protection-policies"></a>Uygulama koruma ilkeleriyle şirket verilerinin kaybını önleme

Intune’un uygulama koruma ilkelerini kullanarak, verilerinize erişim için cihazların kayıtlı olmasını gerektirmeyi seçebilirsiniz. Bu seçim, şirket verilerini korumanıza yardımcı olur ve bir kullanıcı, cihazını Intune’a kaydetmese bile şirket verilerine güvenli bir şekilde erişebilir.

iOS ve Android cihazlar tarafından erişilen şirket verilerini korumaya yardımcı olmak için [Intune uygulama koruma ilkelerini](app-protection-policies.md) kullanabilirsiniz. Bu uygulama düzeyinde ilkeleri uyguladığınızda, cihazın Intune tarafından yönetilmediği durumlarda dahi şirket verilerinin çalışanlar tarafından nasıl kullanıldığını ve paylaşıldığını denetleyebilirsiniz

Bu işlemi yönetilen Windows 10 cihazlarda yapmak için [Windows Bilgi Koruması](app-protection-policies-configure-windows-10.md)’nı (WIP) kullanın. Bu ilkeler, çalışanların deneyimini etkilemeden çalışır. Ağ ortamınız veya diğer uygulamalarınızda değişiklik gerektirmez.

### <a name="remove-company-data-while-leaving-personal-data-intact"></a>Kişisel verileri korurken şirket verilerini silme

Bir cihazın iş için artık gerekli olmadığı, kullanım amacının değiştirildiği veya kaybolduğu durumlarda bu cihazdan şirket uygulamaları ve verilerini kaldırabilirsiniz. Bunu yapmak için Intune'un şirket verilerini ve kaldırma ve fabrika sıfırlaması özelliklerini kullanabilirsiniz. Kullanıcılarınız, Intune yönetimine kaydettikleri kişisel cihazlarını Intune Şirket Portalı aracılığıyla uzaktan da sıfırlayabilir.

[Fabrika sıfırlaması](devices-wipe.md), cihazı fabrika varsayılan ayarlarına geri yükler, kullanıcı verileri ile ayarlarını kaldırır ve cihazı Intune yönetiminden kaldırır. [Şirket verilerini kaldırma](devices-wipe.md#remove-company-data) işlemi, cihazdan yalnızca şirket verilerini kaldırır ve kullanıcının kişisel verilerine dokunmaz.

Cihaz başlatıldıktan hemen sonra sıfırlama işlemine başlar. İşlem tamamlandığında, tüm şirket verileri silinir ve cihaz adı Intune’dan kaldırılır. Böylece cihaz yönetimi yaşam döngüsü sonlanır.
