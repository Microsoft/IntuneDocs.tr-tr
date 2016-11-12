---
title: "Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama

Bu Başlangıç Kılavuzu, mobil uygulamanızı Microsoft Intune ile Mobil Uygulama Yönetimi için hızlı bir şekilde etkinleştirmenize yardımcı olur. İlk olarak [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünde açıklanan Intune Uygulama SDK’sı avantajlarını öğrenmeniz faydalı olabilir.

Bu kılavuzda, Microsoft Intune ile uygulamanızdaki mobil uygulama yönetimini etkinleştirmeniz için gereken önemli adımlar anlatılmaktadır. Intune Uygulama SDK'sı platformlar genelinde benzer senaryoları destekler ve BT yöneticilerine platformlar genelinde tutarlı bir deneyim sağlamak amacıyla tasarlanmıştır. Ancak, platform sınırlamaları nedeniyle bazı özelliklerin desteklenmesi konusunda küçük farklılıklar vardır.

# Başlarken

## Mağaza uygulamanızı Microsoft’a kaydetme

**Uygulamanız şirketinizin dahili uygulamasıysa ve genel kullanıma açık bir uygulama mağazasına sunulmayacaksa**:

Uygulamanızı kaydetmeniz **gerekmez**. BT yöneticisi, uygulamayı dahili iş kolu uygulamaları için içeriden dağıtır. Intune, uygulamanın SDK ile oluşturulduğunu algılar ve BT yöneticisinin buna MAM ilkesi ayarları uygulamasına izin verir. [SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) bölümüne geçebilirsiniz.

**Uygulamanız Apple App Store veya Google Play gibi bir genel uygulama mağazasında yayınlanacaksa**: 

Öncelikle uygulamanızı Microsoft Intune’a kaydetmeniz ve kayıt koşullarını kabul etmeniz **gerekir**. BT yöneticileri, kaydolduktan sonra Intune MAM ilkesi ayarlarını bir Intune uygulama iş ortağı olarak listelenen uygulamaya uygulayabilir. Kayıt tamamlanıp Microsoft Intune ekibi tarafından onaylanana kadar, Intune yöneticilerinin uygulamanızın ayrıntılı bağlantısına MAM ilkesi uygulama seçeneği olmaz. Microsoft, uygulamanızı [Microsoft Intune iş ortakları sayfasına](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) da ekler ve burada uygulamanın Microsoft Intune MAM ilkesini desteklediğini göstermek için uygulamanın simgesi görüntülenir.

Kayıt işlemine başlamak için **[Microsoft Intune İş Ortağı Anketi](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)**’ni doldurun. 

Microsoft size ulaşmak ve kayıt işlemine devam etmek için anket yanıtlarınızda listelenen e-posta adresini (veya adreslerini) kullanır. Ayrıca, herhangi bir sorumuz olursa sizinle iletişim kurmak için kayıt e-posta adresinizi kullanırız.

> [!NOTE]
> Yukarıdaki form ve Microsoft Intune ekibi ile yapılan e-posta yazışmaları aracılığıyla toplanan tüm bilgiler [Microsoft Gizlilik Bildirimi](https://www.microsoft.com/en-us/privacystatement/default.aspx)’ne uygun olacaktır.

**Kayıt işleminde beklenmesi gerekenler**: 

1. Siz anketi gönderdikten sonra Microsoft, talebin başarıyla alındığını onaylamak veya kaydı tamamlamak amacıyla ek bilgi istemek için kayıt e-posta adresiniz üzerinden sizinle iletişim kurar. 
2. Gerekli tüm bilgileri sizden aldıktan sonra, imzalamanız için Microsoft Intune Uygulama İş Ortağı Sözleşmesi’ni size göndeririz. Bu sözleşmede, şirketinizin bir Microsoft Intune uygulama iş ortağı olmadan önce kabul etmesi gereken koşullar açıklanır. 
3. Uygulamanız Microsoft Intune hizmetine başarıyla kaydedildiğinde ve [Microsoft Intune iş ortakları](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) sitesinde gösterildiğinde size bildirilir. 
4. Son olarak, uygulamanızın ayrıntılı bağlantısı bir sonraki aylık Intune Hizmeti güncelleştirmesine eklenir. Örneğin kayıt bilgileri Temmuz'da tamamlanmışsa uygulamanın ayrıntılı bağlantısı Ağustos ayının ortalarında desteklenecektir. 

Mağaza uygulamanızın ayrıntılı bağlantısı gelecekte değişirse uygulamanızı yeniden kaydetmeniz gerekir. Ayrıca, uygulamanızı Intune Uygulama SDK'sının yeni bir sürümüyle güncelleştirirseniz bunu lütfen bize bildirin.



## SDK dosyalarını indirme

Yerel iOS ve Android için Intune Uygulama SDK'ları bir Microsoft GitHub hesabında barındırılır. Aşağıdaki genel depolar sırasıyla iOS ve Android için SDK dosyalarını içerir:

* [iOS için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Android için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Uygulamanız bir Xamarin veya Cordova uygulaması ise, lütfen aşağıdaki geliştirici araçlarını kullanın**:

* [Intune Uygulama SDK’sı Xamarin Bileşeni](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune Uygulama SDK’sı Cordova Eklentisi](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Depolarımızdan çatallama ve çekme için kullanabileceğiniz bir GitHub hesabı oluşturmanız önerilir. GitHub, geliştiricilerin ürün ekibimiz ile iletişim kurmasına, soru sorup hızlı yanıtlar almasına, sürüm notlarını görüntülemesine ve Microsoft'a geri bildirim sağlamasına olanak tanır. GitHub hesabı ve depolar hakkındaki sorularınız için msintuneappsdk@microsoft.com adresine başvurun.





## SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme

Intune Uygulama SDK'sını yerel iOS uygulamanızla tümleştirmek için aşağıdakiler gerekir: 

* **[iOS için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-ios.md)**: Bu belgede mobil iOS uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme adımları anlatılır. 


Intune Uygulama SDK'sını yerel Android uygulamanızla tümleştirmek için aşağıdakiler gerekir:

* **[Android için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-android.md)**: Bu belgede, mobil Android uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme adımları anlatılır. 

Intune Uygulaması SDK Xamarin Bileşeni ve Intune Uygulaması SDK Cordova Eklentisi belgeleri, ilgili GitHub depoları içinde bulunabilir. 


## Uygulamanızda Telemetriyi yapılandırma

Microsoft Intune, uygulamanızdaki kullanım istatistikleri hakkında veri toplar.

* **iOS için Intune Uygulama SDK’sı**: SDK, kullanım etkinliklerine ilişkin SDK telemetri verilerini varsayılan olarak günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir.

    * Uygulamanızdan Microsoft Intune’a SDK telemetri verileri göndermek istemiyorsanız IntuneMAMSettings sözlüğündeki `MAMTelemetryDisabled` özelliğini “EVET” olarak ayarlayarak telemetri iletimini devre dışı bırakmanız gerekir.

* **Android için Intune Uygulama SDK’sı**: Telemetri verileri SDK aracılığıyla günlüğe kaydedilmez.

## MAM özellikli uygulamanızı Microsoft Intune ile test etme

iOS veya Android uygulamanızı Intune Uygulama SDK’sıyla tümleştirmek için gerekli adımları tamamladıktan sonra, son kullanıcı ile BT yöneticisi için tüm uygulama yönetimi ilkelerinin etkinleştirildiğinden ve çalıştığından emin olmanız gerekir. Tümleşik uygulamanızı sınamak için aşağıdakiler gerekir:

<!--TODO-->

* **Microsoft Intune ile MAM özellikli uygulamanızı sınama**: Bu belgede, MAM özellikli iOS veya Android uygulamalarınızı Microsoft Intune ile sınama adımları anlatılır. Bu belgeyi SDK'ların GitHub depolarında bulabilirsiniz.

* **Microsoft Intune Hesabı**: MAM özellikli uygulamalarınızı Microsoft Intune ile test etmek için bir Microsoft Intune hesabınızın olması gerekir. 
    * iOS veya Android mağazası uygulamalarınızı Intune MAM için etkinleştiren bir ISV iseniz Microsoft Intune kaydını, kayıt adımında belirtilen şekilde tamamladıktan sonra bir promosyon kodu alırsınız. Promosyon kodu, 1 yıllık uzatılmış kullanım içeren bir Microsoft Intune deneme sürümüne kaydolmanızı sağlar. 
    * Mağazaya gönderilmeyecek bir iş kolu uygulaması geliştiriyorsanız kuruluşunuz aracılığıyla Microsoft Intune’a erişiminizin olması beklenir. [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ile 1 aylık ücretsiz deneme sürümü için de kaydolabilirsiniz.




<!--HONumber=Nov16_HO1-->


