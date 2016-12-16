---
title: "Uygulamaları ekleme | Microsoft Intune"
description: "Intune’la uygulamaları dağıtmaya başlamadan önce, biraz zaman ayırın ve bu konu başlığı altında tanıtılan kavramları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: f896f51c21beaf7561168f3f622cfc7b0d0c8068


---

# <a name="add-apps-with-microsoft-intune"></a>Microsoft Intune’la uygulamaları ekleme
Microsoft Intune’la uygulamaları dağıtmaya başlamadan önce, biraz zaman ayırın ve bu konu başlığı altında tanıtılan kavramları öğrenin. Bu kavramlar hangi uygulamaları hangi platforma dağıtabileceğinizi anlamanıza yardımcı olur. Ayrıca uygulamaları dağıtmadan önce karşılanması gereken önkoşulları anlamanıza da yardımcı olur.

## <a name="app-types-that-you-can-deploy"></a>Dağıtabileceğiniz uygulama türleri

### <a name="software-installer"></a>Yazılım yükleyicisi

|Uygulama türü|Ayrıntılar|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Bu uygulama türü, kullanıcı girişi gerektirmeyen sessiz yüklemeyi desteklemelidir. Uygulama belgelerinizde, uygulamayı sessiz yüklemek için uygun komut satırı seçenekleri verilmiş olmalıdır (örneğin, **/q**). [Microsoft Windows Installer Aracı için Komut Satırı Anahtarları](https://support.microsoft.com/en-us/kb/227091) bölümünde sık kullanılan komut satırı seçeneklerinin bir listesini bulabilirsiniz.<br><br>Uygulamanın kurulum programının gerektirdiği tüm ek dosya ve klasörler, uygulama kurulum dosyaları için belirttiğiniz konumda bulunmalıdır.<br><br>Genellikle Windows Installer (.msi) ve Windows Installer Düzeltme Eki (.msp) dosyaları, Intune tarafından herhangi bir komut satırı bağımsız değişkeni yüklenmesini gerektirmez. Uygulama belgelerinize bakın.<br><br>Komut satırı bağımsız değişkenleri gerekiyorsa, bu bağımsız değişkenler Ad=Değer çiftleri halinde girilmelidir (örneğin, TRANSFORMS=custom_transform.mst).|
|**Android için Uygulama Paketi (&#42;.apk)**|Android uygulamalarını dağıtmak için geçerli bir .apk paketiniz olmalıdır.|
|**iOS için Uygulama Paketi (&#42;.ipa)**|iOS uygulamalarını dağıtmak için geçerli bir .ipa paketiniz olmalıdır.<br><br>.ipa paketi Apple tarafından imzalanmalı ve sağlama profilinde belirtilen sona erme tarihi geçerli olmalıdır. Intune, kuruluş sertifikası iOS uygulamalarını dağıtabilir.<br><br>Tüm Apple geliştirici sertifikası uygulamaları desteklenmez.<br><br>Şirketiniz iOS Geliştirici Kurumsal Programı'na kayıtlı olmalıdır.<br><br>Kuruluşunuzun güvenlik duvarının iOS sağlama ve sertifika web sitelerine erişim izni verdiğinden emin olun.<br><br>Uygulamayla birlikte bildirim dosyası (.plist) dağıtmanız gerekmez.|
|**Windows Phone uygulama paketi (&#42;.xap, .appx, .appxbundle)**|Uygulamaları dağıtmak için, bir kurumsal mobil kod imzalama sertifikası gerekir. Ayrıntılar için bkz. [Microsoft Intune ile Windows Phone yönetimini ayarlama](set-up-windows-phone-management-with-microsoft-intune.md).|
|**Windows uygulama paketi (.appx, .appxbundle)**|Uygulamaları dağıtmak için, bir kurumsal mobil kod imzalama sertifikası gerekir. Ayrıntılar için bkz. [Microsoft Intune ile Windows cihazı yönetimini ayarlama](set-up-windows-device-management-with-microsoft-intune.md).|
|**MDM aracılığıyla Windows Installer (&#42;.msi)**|Bu uygulamayı Windows Installer tabanlı uygulamalar oluşturmak ve Windows 10 çalıştıran kayıtlı bilgisayarlara dağıtmak için kullanırsınız. Bu bilgisayarlar, mobil cihaz yönetimi (MDM) üzerinden yönetilir.<br /><br />Yalnızca .msi uzantılı tek bir dosyayı karşıya yükleyebilirsiniz.<br><br>Dosyanın ürün kodu ve ürün sürümü, uygulama algılama için kullanılır.<br><br>Uygulamanın varsayılan yeniden başlatma davranışı kullanılır. Intune bunu denetlemez.<br><br>Tek bir kullanıcı için kullanıcı başına MSI paketleri yüklenir.<br><br>Cihazdaki tüm kullanıcılar için makine başına MSI paketleri yüklenir.<br><br>Çift modlu MSI paketleri şu anda yalnızca cihazdaki tüm kullanıcılar için yüklenir.<br><br>Her sürümün MSI ürün kodu aynı olduğunda uygulama güncelleştirmeleri desteklenir.<br>
Tüm yazılım yükleyicisi uygulama türleri bulut depolama alanınıza yüklenir.

### <a name="external-link"></a>**Dış Bağlantı**
Aşağıdakilere sahipseniz dış bağlantı kullanın:
- Kullanıcıların uygulama mağazasından bir uygulama indirmesini sağlayan URL.
- Web tarayıcısından çalıştırılan web tabanlı bir uygulamanın bağlantısı.

Dış bağlantılara dayalı uygulamalar, Intune bulut depolama alanınızda depolanmaz.
### <a name="managed-ios-app-from-the-app-store"></a>**Uygulama mağazasından yönetilen iOS uygulaması**
Uygulama mağazasından ücretsiz olarak sağlanan iOS uygulamalarını yönetebilir ve dağıtabilirsiniz. Ayrıca, yönetilen iOS uygulamalarını [mobil uygulama yönetim ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) [uyumlu uygulamalar](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) ile ilişkilendirmek ve yönetici konsolundaki durumlarını gözden geçirmek için kullanabilirsiniz.<br /><br />Yönetilen iOS uygulamaları Intune bulut depolama alanınızda depolanmaz.

> [!TIP]
> Intune’u [MDM yetkilisi](prerequisites-for-enrollment.md) olarak ayarlamadığınız sürece, mobil cihazlara yönelik seçenekler kullanılamaz.

## <a name="intune-software-publisher"></a>Intune yazılım yayımcısı
Microsoft Intune Yazılım Yayımcısı, Intune yönetici konsolundan uygulama eklediğinizde veya değiştirdiğinizde başlatılır. Yayımcıdan şunlardan birini yapacak bir yazılım yükleyicisi türü seçin ve yapılandırın:

- Intune bulut depolama hizmetinde depolanacak uygulamaları (bilgisayarlar için programlar veya mobil cihazlar için uygulamalar) karşıya yükleyin.
- Bir çevrimiçi mağaza ya da web uygulaması bağlantısı kurun.

Yazılım yayımcısını kullanmaya başlamadan önce [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851)'ın tam sürümünü yüklemeniz gerekir. Yüklemeden sonra yazılım yayımcısının doğru şekilde açılması için bilgisayarınızı yeniden başlatmanız gerekebilir.

## <a name="cloud-storage-space"></a>Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak oluşturduğunuz tüm uygulamalar (örneğin, bir iş kolu uygulaması) paketlenir ve Microsoft Intune bulut depolama alanına yüklenir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Tam aboneliğiniz 20 GB depolama alanı içerir.

**Yönetici** çalışma alanının **Depolama Kullanımı** düğümünde ne kadar alan kullandığınızı görebilirsiniz.

Bulut depolama alanı gereksinimleri aşağıda belirtilmiştir:

-   Tüm uygulama yükleme dosyaları aynı klasörde olmalıdır.
-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.


## <a name="support-for-universal-windows-platform-uwp-apps"></a>Evrensel Windows Platformu (UWP) uygulamaları desteği
Windows 10 bilgisayarları, iş kolu uygulamalarını yüklemek için dışarıdan yükleme anahtarı gerektirmez. Bununla birlikte, dışarıdan yüklemeyi etkinleştirmek için, **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** kayıt defteri anahtarının değeri **1** olmalıdır.

Bu kayıt defteri anahtarı yapılandırılmazsa, cihaza ilk kez uygulama dağıttığınızda Intune bu değeri otomatik olarak **1**’e ayarlar. Bu değeri **0** olarak ayarlarsanız, Intune değeri otomatik olarak değiştiremez ve iş kolu uygulamalarının dağıtımı başarısız olur.

Evrensel Windows Platformu iş kolu uygulamaları, uygulamanın dağıtıldığı her cihazda güvenilen bir kod imzalama sertifikasıyla imzalanmalıdır. Şirket içi ortak anahtar altyapısından (PKI) bir sertifika veya cihaza yüklenmiş üçüncü taraf genel kök sertifikasından bir sertifika kullanabilirsiniz.

Windows 10 Mobile cihazlarında, evrensel **.appx** uygulamalarını imzalamak için Symantec dışında bir kod imzalama sertifikası kullanabilirsiniz. **.xap** uygulamaları ve aynı zamanda Windows 10 Mobile cihazlarının üzerine yüklemek istediğiniz Windows Phone 8.1 için oluşturulmuş **.appx** paketleri için, Symantec kod imzalama sertifikası kullanmalısınız.

### <a name="dependencies-for-uwp-apps"></a>UWP uygulamaları için bağımlılıklar

Intune’a bir Windows 10 Evrensel appxbundle paketi eklediğinizde, uygulama için tüm bağımlılıkların karşıya yüklendiğinden emin olmalısınız.
Bunu yapmak için uygulama oluşturulduğunda oluşturulan **Bağımlılıklar** klasörünün .appxbundle dosyası ile aynı klasörde olduğundan emin olun.
Bu şekilde, uygulamayı Intune’a yüklediğinizde **Bağımlılıklar** klasöründeki tüm dosyalar da karşıya yüklenir. Aşağıdaki ekran görüntüsü bunu göstermektedir:


![Windows 10 UWP appxbundle bağımlılıklarını seçme](./media/w10-dependencies.png)


## <a name="next-steps"></a>Sonraki adımlar

Uygulamaları dağıtabilmek için önce Intune konsoluna eklemeniz gerekir. [Kayıtlı cihazlar](add-apps-for-mobile-devices-in-microsoft-intune.md) için veya [Intune istemci yazılımıyla yönettiğiniz Windows bilgisayarları](add-apps-for-windows-pcs-in-microsoft-intune.md) için uygulamalar ekleyebilirsiniz.



<!--HONumber=Dec16_HO2-->


