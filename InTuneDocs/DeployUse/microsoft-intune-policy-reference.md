---
title: "Yapılandırma ilkesi başvurusu | Microsoft Intune"
description: "Cihazlarınızı yönetirken hangi Microsoft Intune ilkesine ihtiyaç duyduğunuza karar vermek için bu konu başlığı altındaki bilgileri kullanın."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: cce19141ef25a8cca785d6ae80d1fe03ab352a8e


---

# Microsoft Intune ilke başvurusu

Cihazlarınızı yönetirken hangi Microsoft Intune yapılandırma ilkesine ihtiyaç duyduğunuza karar vermek için bu konu başlığı altındaki bilgileri kullanın.

> [!TIP]
> İlkeleri kullanma hakkında daha ayrıntılı bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).


## Android yapılandırma ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (Android 4 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri)**|Cihaz özelliklerini denetlemek için kullanılabilen OMA-URI ayarlarını (Wi-Fi ayarları gibi) dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Android ilke ayarları](android-policy-settings-in-microsoft-intune.md).|
|**E-posta Profili (Samsung KNOX Standard 4.0 ve üzeri)**|Yönetilen cihazlarda Exchange ActiveSync e-posta ayarları oluşturun, dağıtın ve izleyin. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.<br /><br />Ayrıntılar için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Genel Yapılandırma (Android 4 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Uyumlu veya uyumsuz olan uygulamaları belirtin ve bunların ne zaman kullanıldığını bildirin.<br />Cihazı yalnızca belirli özellikleri çalışacak şekilde kilitleyen (örneğin, cihazın yalnızca bir uygulama çalıştırmasına izin vermek veya ses düğmelerini devre dışı bırakmak) bilgi noktası modunu yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Android ilke ayarları](android-policy-settings-in-microsoft-intune.md).|
|**PKCS #12 (.PFX) Sertifika Profili (Android 4 ve üzeri)**|Cihaz sertifika istekleri için PFX ayarları oluşturmak ve dağıtmak istiyorsanız bu profili kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**SCEP Sertifika Profili (Android 4 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilir Sertifika Profili (Android 4 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (Android 4 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak işlerine bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Profili (Android 4 ve üzeri)**|Kablosuz ağ ayarlarını yapılandırın ve kuruluşunuzdaki kullanıcılara dağıtın. Bu ayarları dağıtarak kablosuz ağa bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|

## iOS yapılandırma ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (iOS 7.1 ve üzeri)**|Apple Configurator aracını kullanarak oluşturduğunuz yapılandırma profillerini iOS cihazlara dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları](ios-policy-settings-in-microsoft-intune.md).|
|**E-posta Profili (iOS 7.1 ve üzeri)**|Yönetilen cihazlarda Exchange ActiveSync e-posta ayarları oluşturun, dağıtın ve izleyin. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.<br /><br />Ayrıntılar için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Genel Yapılandırma (iOS 7.1 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />-   Uyumlu veya uyumsuz olan uygulamaları belirtin ve bunların ne zaman kullanıldığını bildirin.<br />Cihazı yalnızca belirli özellikleri çalışacak şekilde kilitleyen (örneğin, cihazın yalnızca bir uygulama çalıştırmasına izin vermek veya ses düğmelerini devre dışı bırakmak) bilgi noktası modunu yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları](ios-policy-settings-in-microsoft-intune.md).|
|**Mobil Uygulama Yapılandırma İlkesi (iOS 7.1 ve üzeri)**|Kullanıcı bir iOS uygulaması çalıştırdığında gerekebilecek ayarları otomatik olarak sağlamak için mobil uygulama yapılandırma ilkelerini kullanın.<br /><br />Ayrıntılar için bkz. [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).|
|**Mobil Sağlama Profili İlkesi (iOS 7.1 ve üstü)**|Apple iOS iş kolu mobil uygulamaları, eklenen ve sertifika kullanılarak kodla imzalanan bir sağlama profiliyle oluşturulur. Uygulama iOS cihazında çalıştırıldığında, iOS uygulamanın bütünlüğünü onaylar ve sağlama profiliyle tanımlanan ilkeleri zorunlu tutar.<br><br>Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi normalde 3 yıldır. Öte yandan, 1 yıl sonra sağlama profilinin süresi dolar. Sertifikası hala geçerli olduğu halde süresi dolmak üzere olan uygulamaların bulunduğu cihazlara, yeni sağlama profili ilkesini önceden dağıtmak için bu ilkeyi kullanın.<br><br>Ayrıntılar için bkz. [Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanma](ios-mobile-app-provisioning-profiles.md).|
|**PKCS #12 (.PFX) Sertifika Profili (iOS 7.1 ve üstü)**|Cihaz sertifika istekleri için PFX ayarları oluşturmak ve dağıtmak istiyorsanız bu profili kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**SCEP Sertifika Profili (iOS 7.1 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilir Sertifika Profili (iOS 7.1 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (iOS 7.1 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak işlerine bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Profili (iOS 7.1 ve üzeri)**|Kablosuz ağ ayarlarını yapılandırın ve kuruluşunuzdaki kullanıcılara dağıtın. Bu ayarları dağıtarak kablosuz ağa bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|


## Mac OS X yapılandırma ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (Mac OS X 10.9 ve üzeri)**|Apple Configurator aracını kullanarak oluşturduğunuz yapılandırma profillerini Mac bilgisayarlara dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Mac OS X ilke ayarları](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Mac OS X 10.9 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Uyumlu veya uyumsuz olan uygulamaları belirtin ve bunların ne zaman kullanıldığını bildirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Mac OS X ilke ayarları](mac-os-x-policy-settings-in-microsoft-intune.md).|
|**SCEP Sertifika Profili (Mac OS X 10.9 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilir Sertifika Profili (Mac OS X 10.9 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (Mac OS X 10.9 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak işlerine bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune.md’de VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Profili (Mac OS X 10.9 ve üzeri)**|Kablosuz ağ ayarlarını yapılandırın ve kuruluşunuzdaki kullanıcılara dağıtın. Bu ayarları dağıtarak kablosuz ağa bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|

## Windows yapılandırma ilkeleri
Yalnızca Windows Phone ve kayıtlı Windows cihazları için geçerlidir.

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Özel Yapılandırma (Windows 10 Masaüstü ile Mobile ve üzeri)**|Cihaz özelliklerini denetlemek için kullanılabilen OMA-URI ayarlarını dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br />    Ayrıntılar için bkz. [Microsoft Intune’da Windows 10 ilke ayarları](windows-10-policy-settings-in-microsoft-intune.md).|
|**Özel Yapılandırma (Windows Phone 8.1 ve üzeri)**|Cihaz özelliklerini denetlemek için kullanılabilen OMA-URI ayarlarını dağıtın. Bu işlem, ihtiyacınız olan ayarın yapılandırma ilkesinde bulunmaması durumunda faydalı olur.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows Phone 8.1 ayarları](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**Sürüm Yükseltme İlkesi (Windows 10 Masaüstü ve sonrası)**<br><br>**Sürüm Yükseltme İlkesi (Windows 10 Holographic ve sonrası)**|Windows 10 cihazlarını daha yeni bir sürüme güncelleştirmek için kullanılan lisans veya ürün anahtarı bilgilerini içeren ilkeleri yapılandırın ve dağıtın<br><br>Ayrıntılar için bkz. [Microsoft Intune’da sürüm yükseltme ilkesi ayarları](edition-upgrade-policy-settings-in-microsoft-intune.md).|  
|**E-posta Profili (Windows Phone 8 ve üzeri)**<br /><br />**E-posta Profili (Windows 10 Masaüstü ile Mobile ve üzeri)**|Yönetilen cihazlarda Exchange ActiveSync e-posta ayarları oluşturun, dağıtın ve izleyin. Bu, kullanıcıların herhangi bir ayar yapmasına gerek kalmadan kişisel cihazlarından kurumsal e-postalara erişmelerini sağlar.<br /><br />Ayrıntılar için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).|
|**Genel Yapılandırma (Windows 10 Masaüstü ile Mobile ve üzeri)**|Kayıtlı Windows 10 masaüstü ve Mobile cihazları için mobil cihaz güvenliğini ve işlev ayarlarını yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows 10 ilke ayarları](windows-10-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Windows 10 Team ve üzeri)**|Kayıtlı Windows 10 Team cihazları (örneğin, Surface Hub cihazı) için cihaz güvenliğini ve işlevsel ayarları yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows Team yapılandırma ilkesi ayarları](windows-team-configuration-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Windows 8.1 ve üzeri)**|Kayıtlı Windows cihazları için mobil cihaz güvenliğini ve işlev ayarlarını yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows ilke ayarları](windows-configuration-policy-settings-in-microsoft-intune.md).|
|**Genel Yapılandırma (Windows Phone 8.1 ve üzeri)**|Mobil cihaz güvenliği ve işlev ayarlarını yapılandırın.<br />Kullanıcıların kullanabileceği ve kullanamayacağı uygulamaları belirtin ve uyumsuz uygulamaların yüklenmesini veya kullanılmasını engelleyin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Windows Phone 8.1 ayarları](windows-phone-8-1-policy-settings-in-microsoft-intune.md).|
|**PKCS #12 (.PFX) Sertifika Profili (Windows 10 Masaüstü ve Mobile ile üzeri)**|Cihaz sertifika istekleri için PFX ayarları oluşturmak ve dağıtmak istiyorsanız bu profili kullanın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**SCEP Sertifika Profili (Windows 8.1 ve üzeri)**<br /><br />**SCEP Sertifikası Profili (Windows Phone 8.1 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için güvenilen bir mobil cihaz sertifikasıyla birlikte kullanılabilen bir Basit Sertifika Kaydı Protokolü yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**Güvenilir Sertifika Profili (Windows 8.1 ve üzeri)**<br /><br />**Güvenilir Sertifika Profili (Windows Phone 8.1 ve üzeri)**|Mobil cihazların Wi-Fi ve VPN profilleri tarafından yapılandırılanlar gibi ağ kaynaklarına erişmesine izin vermek üzere kimliklerini doğrulamak için kullanılabilen bir güvenilir mobil cihaz sertifikası yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da sertifika profilleriyle güvenli kaynak erişimi](secure-resource-access-with-certificate-profiles.md).|
|**VPN Profili (Windows 10 Masaüstü ve Mobile ile üzeri)**<br /><br />**VPN Profili (Windows 8.1 ve üzeri)**<br /><br />**VPN Profili (Windows Phone 8.1 ve üzeri)**|Kullanıcıların mobil cihazlarından şirket ağınıza güvenli bir şekilde erişmesini sağlamak için ayarları yapılandırın ve dağıtın. Bu ayarları dağıtarak işlerine bağlanmak için gereken son kullanıcı çabasını en aza indirin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da VPN bağlantıları](vpn-connections-in-microsoft-intune.md).|
|**Wi-Fi Üzerinden İçeri Aktarma**|Önceden bir dosyaya aktardığınız Windows Wi-Fi yapılandırmalarını içeri aktarın ve dağıtın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Wi-Fi bağlantıları](wi-fi-connections-in-microsoft-intune.md).|
|**Windows Bilgi Koruması**<br>(eski adı kurumsal veri koruma)|Kuruluşta çalışanlara ait cihazlar arttıkça, kuruluşun denetimi dışında kalan e-posta, sosyal medya ve genel bulut gibi uygulamalar ve hizmetler aracılığıyla yanlışlıkla veri sızıntıları yaşama riski de artar. Örneğin, bir çalışan en son mühendislik çalışmalarının resimlerini kişisel e-posta hesabından gönderebilir, ürün bilgilerini bir tweet’e kopyalayıp yapıştırabilir veya hazırlanması devam eden satış raporunu genel bulut depolama alanına kaydedebilir.<br><br>Windows Bilgi Koruması, çalışanın deneyimine başka hiçbir şekilde müdahale etmeden bu olası veri sıkıntılarına karşı korumaya yardımcı olur. Ayrıca, ortamınızda veya diğer uygulamalarda değişiklik yapmaya gerek kalmadan, kuruluşa ait cihazlarda ve çalışanların iş yerine getirdiği kişisel cihazlarda yanlışlıkla ortaya çıkabilecek veri sızıntılarına karşı kurumsal uygulamaları ve verileri korumaya da yardımcı olur.<br><br>Bu Intune ilkesi, Windows Bilgi Koruması tarafından korunan uygulamalar listesini, kurumsal ağ konumlarını, koruma düzeyini ve şifreleme ayarlarını yönetir.<br><br>Daha fazla bilgi için bkz. [Windows Bilgi Koruması’nı kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-edp).|


## Yazılım ilkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Yönetilen Tarayıcı İlkesi (Android 4 ve üzeri)**<br /><br />**Yönetilen Tarayıcı İlkesi (iOS 7.1 ve üzeri)**|Kullanıcıların yönetilen tarayıcı uygulamasını kullanırken erişebileceği ve erişemeyeceği web sitelerini belirtin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme](manage-internet-access-using-managed-browser-policies.md).|
|**Mobil Uygulama Yönetimi İlkesi (Android 4 ve üzeri)**<br /><br />**Mobil Uygulama Yönetimi İlkesi (iOS 7.1 ve üzeri)**|Dağıttığınız uygulamaları şirket uyumluluk ve güvenlik ilkeleriyle uyumlu hale getirmeye yardımcı olmak için uygulamaların işlevlerini değiştirin. Örneğin, yönetilen bir uygulama içinde kesme, kopyalama ve yapıştırma işlemlerini kısıtlayabilir veya bir uygulamayı tüm web bağlantılarını yönetilen tarayıcıda açmak için yapılandırabilirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).|

## Ortak Mobil Cihaz Ayarları

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Exchange ActiveSync İlkesi**|Exchange ActiveSync tarafından yönetilen cihazlar için mobil cihaz güvenliğini ve işlev ayarlarını yapılandırın.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da Exchange ActiveSync ilkesi ayarları](exchange-activesync-policy-settings-in-microsoft-intune.md).|
|**Mobil Cihaz Güvenlik İlkesi**|<ul><li>Şunları içeren mobil cihaz ayarlarını (tüm platformlar) yapılandırır:<br /><br /><ul><li>Güvenlik</li><li>Şifreleme</li><li>Sistem</li><li>E-posta</li><li>Uygulamalar</li></ul></li></ul> **Önemli:** Microsoft Intune’da artık her cihaz platformu için ayrı **yapılandırma ilkeleri** vardır ve bu ilkeler kullanabileceğiniz en güncel ayarları içerir. Mobil cihaz güvenlik ilkesini kullanmaya devam edebilirsiniz ve var olan tüm dağıtımlar çalışmaya devam eder, ancak yeni yapılandırma ilkelerine geçmeyi en kısa sürede planlamanız gerekmektedir.<br />Ayrıntılar için bkz. [Microsoft Intune’da mobil cihaz güvenliği ilke ayarları](mobile-device-security-policy-settings-in-microsoft-intune.md).|

## Koşullu erişim ve uyumluluk ilkeleri

### Koşullu Erişim

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Exchange Online İlkesi**<br /><br />**Exchange Şirket İçi İlkesi**|Microsoft Exchange e-postasına Intune tarafından yönetilmeyen veya oluşturduğunuz bir uyumluluk ilkesiyle uyumlu olmayan cihazlar üzerinden erişimi yönetin.<br /><br />Ayrıntılar için bkz. [Intune ile Exchange Online’a ve yeni Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama](restrict-access-to-exchange-online-with-microsoft-intune.md).|
|**SharePoint Online İlkesi**|SharePoint Online'a Intune tarafından yönetilmeyen veya oluşturduğunuz bir uyumluluk ilkesiyle uyumlu olmayan cihazlar üzerinden erişimi yönetin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’la SharePoint Online’a erişimi kısıtlama](restrict-access-to-sharepoint-online-with-microsoft-intune.md).|
|**Skype Kurumsal**|Skype Kurumsal’a Intune tarafından yönetilmeyen veya oluşturduğunuz bir uyumluluk ilkesiyle uyumlu olmayan cihazlar üzerinden erişimi yönetin.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’la Skype Kurumsal’a erişimi kısıtlama](restrict-access-to-skype-for-business-online-with-microsoft-intune.md).|
> [!NOTE]
> Koşullu erişim ilkeleri kullanıcı ve cihazlara dağıtılmaz. Bunun yerine, gerekli ilkeyi yapılandırırsınız ve ilkede hedeflenen tüm gruplar için geçerli olur.

### Uyumluluk İlkeleri

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Uyumluluk ilkeleri**|Cihazlar için uyumluluk düzeylerini tanımlayın ve ardından uyumlu olmayan cihazları bildirin. Bu ilkeler hizmetlerden engellenmesi gereken cihazları değerlendirmek için koşullu erişimle kullanılır.<br /><br />Ayrıntılar için bkz. [Microsoft Intune’da cihaz uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune.md).|

## Windows Bilgisayarı Yönetimi

|İlke adı|Şunları yapmak istediğinizde kullanın|
|---------------|------------------------|
|**Microsoft Intune Aracısı Ayarları**|Aşağıdakilerle ilgili ayarlar dahil olmak üzere bilgisayarlarda Intune bilgisayar istemcisini yapılandırın:<br /><br />-   Endpoint Protection<br />-   Yazılım güncelleştirmeleri<br />-   İlke denetimi zamanlaması<br /><br />Bu tür bir ilke yalnızca cihaz gruplarına dağıtılabilir.<br /><br />Intune istemcileri yeni ve güncelleştirilmiş ilkeyi varsayılan olarak 8 saat olan **Güncelleştirme ve uygulama algılama sıklığı** ayarına göre indirir. Ancak, istediğiniz zaman bilgisayarlarda ilke yenileme uygulayabilirsiniz.<br /><br />Ayrıntılar için bkz. [Microsoft Intune'da yazılım güncelleştirmeleriyle Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Microsoft Intune Center Ayarları**|Yönetilen bilgisayarlarda, Microsoft Intune Merkezi'nde gösterilen ayrıntıları yapılandırın.<br /><br />Bu tür bir ilke yalnızca cihaz gruplarına dağıtılabilir.<br /><br />Ayrıntılar için bkz. [Microsoft Intune bilgisayar istemcisiyle ortak Windows bilgisayarı yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).|
|**Windows Güvenlik Duvarı Ayarları**|Bilgisayarlarda aşağıdakiler dahil Windows Güvenlik Duvarı ayarları ve ortak ağ iletişimi için özel durumları yapılandırır:<br /><br />-   BranchCache<br />-   Uzaktan Yardım<br />-   Medya paylaşımı<br /><br />Bu tür bir ilke yalnızca cihaz gruplarına dağıtılabilir.<br /><br />Ayrıntılar için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).|

### Ayrıca Bkz.

[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO3-->


