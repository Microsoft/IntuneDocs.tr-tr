---
title: "Microsoft Intune Uygulama SDK’sını kullanmaya başlayın | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.author: oydang
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4623db80d711f3543b6d688fb1bb1ef228c62c
ms.openlocfilehash: 2a65ae79a0bba21d555dbed9f1bc40e01452f08c


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Microsoft Intune Uygulama SDK’sını kullanmaya başlayın

Bu kılavuz, mobil uygulamanızı Microsoft Intune ile mobil uygulama yönetimi (MAM) için hızlı bir şekilde etkinleştirmenize yardımcı olur. İlk olarak [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünde açıklanan Intune Uygulama SDK’sı avantajlarını öğrenmeniz yararlı olabilir.

Bu kılavuzda, Microsoft Intune ile uygulamanızda MAM’yi etkinleştirmeye yönelik önemli adımlarda yol gösterilir. Intune Uygulama SDK'sı platformlar genelinde benzer senaryoları destekler ve BT yöneticilerine platformlar genelinde tutarlı bir deneyim sağlamak amacıyla tasarlanmıştır. Ancak, platform sınırlamaları nedeniyle bazı özelliklerin desteklenmesinde küçük farklılıklar vardır.

## <a name="register-your-store-app-with-microsoft"></a>Mağaza uygulamanızı Microsoft’a kaydetme

**Uygulamanız şirketinizin dahili uygulamasıysa ve genel kullanıma açık bir uygulama mağazasına sunulmayacaksa**:

Uygulamanızı kaydetmeniz *gerekmez*. BT yöneticisi, uygulamayı dahili iş kolu uygulamaları için içeriden dağıtır. Intune, uygulamanın SDK ile oluşturulduğunu algılar ve BT yöneticisinin buna MAM ilkesi ayarlarını uygulamasına izin verir. [SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) bölümüne geçebilirsiniz.

**Uygulamanız Apple App Store veya Google Play gibi bir genel uygulama mağazasında yayınlanacaksa**:

Öncelikle uygulamanızı Microsoft Intune’a kaydetmeniz ve kayıt koşullarını kabul etmeniz *gerekir*. Bundan sonra BT yöneticileri, Intune MAM ilkesi ayarlarını bir Intune uygulama iş ortağı olarak listelenen uygulamaya uygulayabilir. Kayıt tamamlanıp Microsoft Intune ekibi tarafından onaylanana kadar, Intune yöneticilerinin uygulamanızın ayrıntılı bağlantısına MAM ilkesi uygulama seçeneği olmaz. Microsoft ayrıca uygulamanızı kendi [Microsoft Intune İş Ortakları sayfasına](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) ekler. Orada, Microsoft Intune MAM ilkesini desteklediğini göstermek üzere uygulamanın simgesi görüntülenir.

Kayıt işlemine başlamak için [Microsoft Intune İş Ortağı Anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)’ni doldurun.

Size ulaşmak ve kayıt işlemine devam etmek için anket yanıtlarınızda listelenen e-posta adresini (veya adreslerini) kullanacağız. Ayrıca, herhangi bir sorumuz olursa sizinle iletişim kurmak için kayıt e-posta adresinizi kullanırız.

> [!NOTE]
> Ankette ve Microsoft Intune ekibi ile yapılan e-posta yazışmaları aracılığıyla toplanan tüm bilgiler için [Microsoft Gizlilik Bildirimi](https://www.microsoft.com/en-us/privacystatement/default.aspx) geçerli olacaktır.

**Kayıt işleminde beklenmesi gerekenler**:

1. Siz anketi gönderdikten sonra, talebin başarıyla alındığını onaylamak veya kaydı tamamlamak amacıyla ek bilgi istemek için kayıt e-posta adresiniz üzerinden sizinle iletişim kurarız.
2. Gerekli tüm bilgileri sizden aldıktan sonra, imzalamanız için Microsoft Intune Uygulama İş Ortağı Sözleşmesi’ni size göndeririz. Bu sözleşmede, şirketinizin bir Microsoft Intune uygulama iş ortağı olmadan önce kabul etmesi gereken koşullar açıklanır.
3. Uygulamanız Microsoft Intune hizmetine başarıyla kaydedildiğinde ve [Microsoft Intune iş ortakları](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) sitesinde gösterildiğinde size bildirilir.
4. Son olarak, uygulamanızın ayrıntılı bağlantısı bir sonraki aylık Intune Hizmeti güncelleştirmesine eklenir. Örneğin kayıt bilgileri Temmuz'da tamamlanmışsa ayrıntılı bağlantı Ağustos ayının ortalarında desteklenecektir.

Uygulamanızın ayrıntılı bağlantısı gelecekte değişirse, uygulamanızı yeniden kaydetmeniz gerekir. Ayrıca, uygulamanızı Intune Uygulama SDK'sının yeni bir sürümüyle güncelleştirirseniz bunu lütfen bize bildirin.



## <a name="download-the-sdk-files"></a>SDK dosyalarını indirme

Yerel iOS ve Android için Intune Uygulama SDK'ları bir Microsoft GitHub hesabında barındırılır. Bu genel depolar sırasıyla iOS ve Android için SDK dosyalarını içerir:

* [iOS için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Android için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Uygulamanız bir Xamarin veya Cordova uygulaması ise, lütfen şu geliştirici araçlarını kullanın:

* [Intune Uygulama SDK’sı Xamarin Bileşeni](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune Uygulama SDK’sı Cordova Eklentisi](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Depolarımızdan çatallama ve çekme işlemleri yaparken kullanabileceğiniz bir GitHub hesabı oluşturmanız iyi olabilir. GitHub, geliştiricilerin ürün ekibimizle iletişim kurmasına, soru sorup hızlı yanıtlar almasına, sürüm notlarını görüntülemesine ve Microsoft'a geri bildirim sağlamasına olanak tanır. GitHub hesabı ve depolar hakkındaki sorularınız için msintuneappsdk@microsoft.com adresine başvurun.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme

Intune Uygulama SDK'sını yerel iOS uygulamanızla tümleştirmek için aşağıdakiler gerekir:

* **[iOS için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-ios.md)**: Bu belgede, mobil iOS uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme işleminde size adım adım yol gösterilir.


Intune Uygulama SDK'sını yerel Android uygulamanızla tümleştirmek için aşağıdakiler gerekir:

* **[Android için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-android.md)**: Bu belgede, mobil Android uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme işleminde size adım adım yol gösterilir.

Intune Uygulama SDK’sı Cordova Eklentisi ile Cordova uygulamaları oluşturmak için aşağıdakiler gereklidir:

* **[Intune Uygulama SDK’sı Cordova Eklentisi kılavuzu](intune-app-sdk-cordova)**: Bu belge, Intune mobil uygulama yönetimi için Cordova kullanarak iOS ve Android uygulamaları oluşturmanıza yardımcı olur.

Intune Uygulama SDK’sı Xamarin Bileşeni ile Xamarin uygulamaları oluşturmak için aşağıdakiler gereklidir:

* **[Intune Uygulama SDK’sı Xamarin Bileşeni kılavuzu](intune-app-sdk-xamarin)**: Bu belge, Intune mobil uygulaması yönetimi için Cordova kullanarak iOS ve Android uygulamaları oluşturmanıza yardımcı olur.




## <a name="configure-telemetry-for-your-app"></a>Uygulamanızda Telemetriyi yapılandırma

Microsoft Intune, uygulamanızdaki kullanım istatistikleri hakkında veri toplar.

* **iOS için Intune Uygulama SDK’sı**: SDK, kullanım etkinliklerine ilişkin SDK telemetri verilerini varsayılan olarak günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir.

    * Uygulamanızdan Microsoft Intune’a SDK telemetri verileri göndermek istemiyorsanız IntuneMAMSettings sözlüğündeki `MAMTelemetryDisabled` özelliğini “EVET” olarak ayarlayarak telemetri iletimini devre dışı bırakmanız gerekir.

* **Android için Intune Uygulama SDK’sı**: Telemetri verileri SDK aracılığıyla günlüğe kaydedilmez.

## <a name="test-your-mam-enabled-app-with-microsoft-intune"></a>MAM özellikli uygulamanızı Microsoft Intune ile test etme

iOS veya Android uygulamanızı Intune Uygulama SDK’sıyla tümleştirmek için gerekli adımları bitirdikten sonra, kullanıcı ile BT yöneticisi için tüm uygulama yönetimi ilkelerinin etkinleştirildiğinden ve çalıştığından emin olmanız gerekir. Tümleşik uygulamanızı sınamak için aşağıdakiler gerekir:

<!--TODO-->

* **Microsoft Intune ile MAM özellikli uygulamanızı test etme**: Bu belgede, MAM özellikli iOS veya Android uygulamalarınızı Microsoft Intune ile test etme işleminde size adım adım yol gösterilir. Bu belgeyi SDK'ların GitHub depolarında bulabilirsiniz.

* **Microsoft Intune hesabı**: MAM özellikli uygulamalarınızı Microsoft Intune ile test etmek için bir Microsoft Intune hesabınızın olması gerekir.
    * iOS veya Android mağazası uygulamalarınızı Intune MAM için etkinleştiren bir ISV iseniz Microsoft Intune kaydını, kayıt adımında belirtilen şekilde bitirdikten sonra bir promosyon kodu alırsınız. Promosyon kodu, bir yıllık uzatılmış kullanım sağlayan Microsoft Intune denemesine kaydolmanıza olanak tanır.
    * Mağazaya gönderilmeyecek bir iş kolu uygulaması geliştiriyorsanız kuruluşunuz aracılığıyla Microsoft Intune’a erişiminizin olması beklenir. [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ile bir aylık ücretsiz deneme için de kaydolabilirsiniz.



<!--HONumber=Nov16_HO3-->


