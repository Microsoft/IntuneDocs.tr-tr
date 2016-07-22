---
title: "Uygulamaları ekleme | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: f85e91b985d9d30c71dff9e0d910293354fc40b7
ms.openlocfilehash: 119a795697feb0cdbc2b93293cd66df7e77147cf


---

# Microsoft Intune’la uygulamaları ekleme
Microsoft Intune’la uygulamaları dağıtmaya başlamadan önce, biraz zaman ayırın ve bu konu başlığı altında tanıtılan kavramları öğrenin. Bunlar, hangi uygulamaları hangi platforma dağıtabileceğinizi anlamanıza ve bunu yapmadan önce karşılanması gereken önkoşulları öğrenmenize yardımcı olur.

## Intune’la dağıtabileceğiniz uygulama türleri
Uygulamaları, Intune tarafından desteklenen tüm cihaz türlerine dağıtabilirsiniz. Dağıtmak istediğiniz uygulamanın türüne bağlı olarak, süreç ve desteklenen cihazlar farklılık gösterir. Neleri dağıtabileceğinizi ve neleri dağıtamayacağınızı anlamanıza yardımcı olması için aşağıdaki bilgileri kullanın:


### **Windows Installer (&#42;.exe, &#42;.msi)**
- Bu uygulama türü, kullanıcı girişi gerektirmeyen sessiz yüklemeyi desteklemelidir. Uygulama belgelerinizde, uygulamayı sessiz yüklemek için uygun komut satırı seçenekleri verilmiş olmalıdır (örneğin, **/q**). Yaygın komut satırı seçeneklerinin listesini [burada](https://support.microsoft.com/en-us/kb/227091) bulabilirsiniz.
- Uygulamanın kurulum programının gerektirdiği tüm ek dosya ve klasörler, uygulama kurulum dosyaları için belirttiğiniz konumda bulunmalıdır.
- Genellikle Windows Installer (.msi) ve Windows Installer Patch (.msp) dosyalarının Intune tarafından yüklenmesi için herhangi bir komut satırı bağımsız değişkeni gerekmez. Uygulama belgelerinize bakın. Komut satırı bağımsız değişkenleri gerekiyorsa, bu bağımsız değişkenler Ad=Değer çiftleri halinde girilmelidir (örneğin, TRANSFORMS=custom_transform.mst).

Bu uygulama türü bulut depolama alanınıza yüklenir.
### **Android için Uygulama Paketi (&#42;.apk dosyası)**
Bu uygulama türü bulut depolama alanınıza yüklenir.
### **iOS için Uygulama Paketi (&#42;.ipa dosyası)**
- iOS uygulamalarını dağıtmak için geçerli bir .ipa paketiniz olmalıdır.
- .ipa paketi Apple tarafından imzalanmalı ve sağlama profilinde belirtilen sona erme tarihi geçerli olmalıdır. Intune, kuruluş sertifikası iOS uygulamalarını dağıtabilir. Tüm Apple geliştirici sertifikası uygulamaları desteklenmez.
- Şirketiniz iOS Geliştirici Kurumsal Programı'na kayıtlı olmalıdır.
- Kuruluşunuzun güvenlik duvarının iOS sağlama ve sertifika web sitelerine erişim izni verdiğinden emin olun.
- Uygulamayla birlikte bir bildirim dosyasının (.plist) dağıtılması gerekmez.

Bu uygulama türü bulut depolama alanınıza yüklenir.

Şu anda son kullanıcılar iOS için Intune Şirket Portalı uygulamasından doğrudan şirket uygulamaları yükleyememektedir. Bunun nedeni iOS App Store'da yayımlanan uygulamalara getirilen kısıtlamalardır (bkz. [App Store Gözden Geçirme Yönergeleri](https://developer.apple.com/app-store/review/guidelines/)). Kullanıcılar, cihazlarında Şirket Portalı uygulamasını başlatarak ve tarayıcıyı açıp Intune Web Portalı'na yönlendiren Şirket Uygulamaları kutucuğuna dokunarak şirket uygulamalarına (yönetilen App Store uygulamaları ve iş kolu uygulama paketleri dahil) erişebilir.

### **Windows Phone uygulama paketi (&#42;.xap, .appx, .appxbundle)**
- Uygulamaları dağıtmak için, bir kurumsal mobil kod imzalama sertifikası gerekir. Ayrıntılar için bkz. [Microsoft Intune ile Windows Phone yönetimini ayarlama](set-up-windows-phone-management-with-microsoft-intune.md).

Bu uygulama türü bulut depolama alanınıza yüklenir.

Intune ile iş kolu Evrensel Windows Platformu (UWP) uygulamalarını yükleme hakkında bilgi için aşağıya bakın.

### **Windows uygulama paketi (.appx, .appxbundle)**
- Uygulamaları dağıtmak için, bir kurumsal mobil kod imzalama sertifikası gerekir. Ayrıntılar için bkz. [Microsoft Intune ile Windows cihazı yönetimini ayarlama](set-up-windows-device-management-with-microsoft-intune.md).

Bu uygulama türü bulut depolama alanınıza yüklenir.
### **MDM aracılığıyla Windows Installer (&#42;.msi)**
Bu yükleyici türü, Windows Installer tabanlı uygulamalar oluşturmanıza ve Windows 10 çalıştıran kayıtlı bilgisayarlara dağıtmanıza imkan sağlar.<br /><br />Bu yükleyici türünü kullandığınızda aşağıdaki maddeler geçerlidir:
- Yalnızca .msi uzantılı tek bir dosyayı karşıya yükleyebilirsiniz.
- Dosyanın ürün kodu ve ürün sürümü, uygulama algılama için kullanılır.
- Uygulamanın varsayılan yeniden başlatma davranışı kullanılır. Intune bunu denetlemez.
- Tek bir kullanıcı için kullanıcı başına MSI paketleri yüklenir.
- Cihazdaki tüm kullanıcılar için makine başına MSI paketleri yüklenir.
- Çift modlu MSI paketleri şu anda yalnızca cihazdaki tüm kullanıcılar için yüklenir.
- Her sürümün MSI ürün kodu aynı olduğunda uygulama güncelleştirmeleri desteklenir.

Bu uygulama türü bulut depolama alanınıza yüklenir.
### **Dış Bağlantı**
Kullanılması için aşağıdakilere sahip olmanız gerekir:
- Kullanıcıların uygulama mağazasından bir uygulama indirmesini sağlayan **URL**.
- Web tarayıcısından çalıştırılan web tabanlı bir uygulamanın **bağlantısı**.

Dış bağlantılara dayalı uygulamalar, Intune bulut depolama alanınızda depolanmaz.
### **Uygulama mağazasından yönetilen iOS uygulaması**
Uygulama mağazasından ücretsiz olarak sağlanan iOS uygulamalarını yönetmenizi ve dağıtmanızı sağlar. Ayrıca, [mobil uygulama yönetim ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) [uyumlu uygulamalarla](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) ilişkilendirmenize ve yönetici konsolunda bunların durumunu gözden geçirmenize de olanak tanır.<br /><br />Yönetilen iOS uygulamaları Intune bulut depolama alanınızda depolanmaz.
> [!TIP] Intune’u [Mobil Cihaz Yönetimi Yetkilisi olarak ayarlamadığınız](get-ready-to-enroll-devices-in-microsoft-intune.md) sürece, mobil cihazlara yönelik seçenekler kullanılamaz.

## Intune yazılım yayımcısı
**Microsoft Intune Yazılım Yayımcısı**, Microsoft Intune yönetici konsolundan uygulama eklediğinizde veya değiştirdiğinizde başlatılır. Yayımcıyı kullanarak, Intune bulut depolama alanında depolanacak uygulamaları (bilgisayarlar için programlar veya mobil cihazlar için uygulamalar) karşıya yükleyecek veya bir çevrimiçi mağaza ya da web uygulaması ile bağlantı kuracak türde bir yazılım yükleyicisi seçebilir ve yapılandırabilirsiniz.

### Gereksinimler
Microsoft Intune Yazılım Yayımcısı'nı kullanmaya başlamadan önce [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851)'ın tam sürümünü yüklemeniz gerekir. Yüklemeden sonra Yazılım Yayımcısı'nın doğru şekilde açılması için bilgisayarınızı yeniden başlatmanız gerekebilir.

## Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak oluşturduğunuz tüm uygulamalar (örneğin, bir iş kolu uygulaması), paketlenir ve Microsoft Intune bulut depolama alanına yüklenir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Ücretli abonelikler 20 GB içerir ve ek depolama alanı satın alma seçeneği de sağlanır.

**Yönetici** çalışma alanının **Depolama Kullanımı** düğümünde ne kadar alan kullandığınızı görebilir ve daha fazla depolama satın alabilirsiniz.

Intune için bulut tabanlı ek depolama alanı satın alma işleminde şu kurallar geçerlidir:

-   Ek depolama alanı satın almak için etkin bir ücretli aboneliğinizin olması gerekir.

-   Yalnızca Microsoft Online Service’inizin faturalama yöneticileri veya genel yöneticileri Office 365 Yönetim Portalı aracılığıyla ek depolama alanı satın alabilir. Bu yöneticileri eklemek, silmek veya yönetmek için bir genel yönetici olmanız ve Office 365 Yönetim Portalı’nda oturum açmış olmanız gerekir.

-   Intune’u veya Microsoft Intune Eklentisini kurumsal anlaşma ile satın almış bir toplu lisans müşterisiyseniz, fiyatlandırma konusunda bilgi edinmek ve ek depolama alanı satın almak için Microsoft Kurumsal Müşteri Yöneticiniz veya Microsoft İş Ortağınız ile iletişim kurun.

#### Bulut depolama alanı gereksinimleri

-   Tüm uygulama yükleme dosyalarının aynı klasörde olduğundan emin olun.

-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.


## Evrensel Windows Platformu (UWP) uygulamaları desteği
Windows 10 bilgisayarları, iş kolu uygulamalarını yüklemek için dışarıdan yükleme anahtarı gerektirmez. Bununla birlikte, dışarıdan yüklemeyi etkinleştirmek için, **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** kayıt defteri anahtarının değeri **1** olmalıdır.

Bu kayıt defteri anahtarı yapılandırılmazsa, cihaza ilk kez uygulama dağıttığınızda Intune bu değeri otomatik olarak **1**’e ayarlar. Bu değeri **0** olarak ayarlarsanız, Intune değeri otomatik olarak değiştiremez ve iş kolu uygulamalarının dağıtımı başarısız olur.

Evrensel Windows Platformu iş kolu uygulamaları, uygulamanın dağıtıldığı her cihazda güvenilen bir kod imzalama sertifikasıyla imzalanmalıdır. Şirket içi PKI altyapısından sertifikalar veya cihaza yüklenmiş üçüncü taraf genel kök sertifikasından bir sertifika kullanabilirsiniz.

Windows 10 Mobile cihazlarında, evrensel **.appx** uygulamalarını imzalamak için Symantec dışında bir kod imzalama sertifikası kullanabilirsiniz. **.xap** uygulamaları ve aynı zamanda Windows 10 Mobile cihazlarının üzerine yüklemek istediğiniz Windows Phone 8.1 için oluşturulmuş **.appx** paketleri için, Symantec kod imzalama sertifikası kullanmalısınız.

## Sonraki adımlar 

Bundan sonra, uygulamaları dağıtabilmek için önce Intune konsoluna eklemeniz gerekir. [Kayıtlı cihazlar](add-apps-for-mobile-devices-in-microsoft-intune.md) için veya [Intune istemci yazılımıyla yönettiğiniz Windows bilgisayarları](add-apps-for-windows-pcs-in-microsoft-intune.md) için uygulamalar ekleyebilirsiniz.



<!--HONumber=Jun16_HO3-->


