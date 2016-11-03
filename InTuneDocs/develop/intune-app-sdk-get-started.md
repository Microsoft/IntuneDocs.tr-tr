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
ms.sourcegitcommit: ba9ba203c9ec173dafd1d6f9e4828d4a8a51e1ef
ms.openlocfilehash: 136dd127c5e0f1784746b973ebc5594573f07925


---

# Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama

Bu Başlangıç Kılavuzu, mobil uygulamanızı Microsoft Intune ile Mobil Uygulama Yönetimi için hızlı bir şekilde etkinleştirmenize yardımcı olur. İlk olarak [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünde açıklanan Intune Uygulama SDK’sı avantajlarını öğrenmeniz faydalı olabilir.

Bu kılavuzda, Microsoft Intune ile uygulamanızdaki mobil uygulama yönetimini etkinleştirmeniz için gereken önemli adımlar anlatılmaktadır. Intune Uygulama SDK'sı platformlar genelinde benzer senaryoları destekler ve BT yöneticilerine platformlar genelinde tutarlı bir deneyim sağlamak amacıyla tasarlanmıştır. Ancak, platform sınırlamaları nedeniyle bazı özelliklerin desteklenmesi konusunda küçük farklılıklar vardır.

# Başlarken

## Mağaza uygulamanızı Microsoft’a kaydetme

**Uygulamanız şirketinizin dahili uygulamasıysa ve genel kullanıma açık bir uygulama mağazasına sunulmayacaksa**:

Uygulamanızı kaydetmeniz **gerekmez**. BT yöneticisi, dahili iş kolu uygulamaları için Microsoft Intune kullanarak uygulamayı dahili olarak dağıtır. Intune, uygulamanın SDK ile oluşturulduğunu algılar ve BT yöneticisinin buna MAM ilkesi ayarları uygulamasına izin verir. [SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) bölümüne geçebilirsiniz.

**Uygulamanız Apple App Store veya Google Play gibi bir genel uygulama mağazasında yayınlanacaksa**: 

Öncelikle uygulamanızı Microsoft Intune’a kaydetmeniz ve kayıt koşullarını kabul etmeniz **gerekir**. BT yöneticileri, kaydolduktan sonra Intune MAM ilkesi ayarlarını bir Intune uygulama iş ortağı olarak listelenen uygulamaya uygulayabilir. Kayıt tamamlanıp Microsoft Intune ekibi tarafından onaylanana kadar, Intune yöneticilerinin uygulamanızın ayrıntılı bağlantısına MAM ilkesi uygulama seçeneği olmaz. Microsoft, uygulamanızı [Microsoft Intune iş ortakları sayfasına](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) da ekler ve burada uygulamanın Microsoft Intune MAM ilkesini desteklediğini göstermek için uygulamanın simgesi görüntülenir.

Kayıt işlemine başlamak için **Microsoft Intune İş Ortağı Sözleşmesi**’ni [gözden geçirin ve imzalayın](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Bu sözleşmede, şirketinizin bir Microsoft Intune uygulama iş ortağı olmadan önce kabul etmesi gereken koşullar açıklanır. Bu belgeyi görüntüleyebilmek için oturum açmanız gerekir. Sözleşmeyi, Intune Uygulama SDK'sı Microsoft Connect sitesindeki Anketler sekmesinin altında veya burada bulabilirsiniz. Sizden ayrıca uygulamanın adı, şirketinizin adı ve uygulamanızın Google veya iTunes mağazasındaki ayrıntılı bağlantısı istenir.

![Microsoft Connect](../media/microsoft-connect.png)

Kaydın talebinin alındığını onaylamak ve kayıt işlemini tamamlamak için kayıt e-posta adresiniz kullanılır. Ayrıca, herhangi bir sorumuz olursa sizinle iletişim kurmak için kayıt e-posta adresinizi kullanırız.

**Kayıt işleminde beklenmesi gerekenler**: 

Siz formu gönderdikten sonra Microsoft, talebin başarıyla alındığını onaylamak veya kaydı tamamlamak amacıyla ek bilgi istemek için kayıt e-posta adresiniz üzerinden sizinle iletişim kurar. Ayrıca, uygulamanız Microsoft Intune’a başarıyla kaydedildiğinde ve Microsoft Intune iş ortakları sitesinde gösterildiğinde de sizinle iletişim kurulur. Bilgilerin alındığı onaylandıktan sonra uygulamanızın ayrıntılı bağlantısı sonraki aylık Intune Hizmeti güncelleştirmesine dahil edilir. Örneğin kayıt bilgileri Temmuz'da tamamlanmışsa uygulamanın ayrıntılı bağlantısı Ağustos ayının ortalarında desteklenecektir. Mağaza uygulamanızın ayrıntılı bağlantısı gelecekte değişirse uygulamanızı yeniden kaydetmeniz gerekir. Ayrıca, uygulamanızı Intune Uygulama SDK'sının yeni bir sürümüyle güncelleştirirseniz bunu bize bildirmeniz gerekir.

**Not**: Yukarıdaki form ve Intune ekibi ile yapılan e-posta yazışmaları aracılığıyla toplanan tüm bilgiler [Microsoft Gizlilik Bildirimi](https://www.microsoft.com/en-us/privacystatement/default.aspx)’ne uygun olacaktır.

## SDK dosyalarını indirme

iOS ve Android için Intune Uygulama SDK'ları bir Microsoft GitHub hesabında barındırılır. Aşağıdaki genel depolar sırasıyla iOS ve Android için SDK dosyalarını içerir:

* [iOS için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [Android için Intune Uygulama SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Depolarımızdan çatallama ve çekme için kullanabileceğiniz bir GitHub hesabı oluşturmanız önerilir. GitHub, geliştiricilerin ürün ekibimiz ile iletişim kurmasına, soru sorup hızlı yanıtlar almasına, sürüm notlarını görüntülemesine ve Microsoft'a geri bildirim sağlamasına olanak tanır. GitHub hesabı ve depolar hakkındaki sorularınız için msintuneappsdk@microsoft.com adresine başvurun.

## SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme

Intune Uygulama SDK'sını iOS uygulamanızla tümleştirmek için aşağıdakiler gerekir: 

* **[iOS için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-ios.md)**: Bu belgede mobil iOS uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme adımları anlatılır. 


Intune Uygulama SDK'sını Android uygulamanızla tümleştirmek için aşağıdakiler gerekir:

* **[Android için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-android.md)**: Bu belgede, mobil Android uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme adımları anlatılır. 



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




<!--HONumber=Sep16_HO4-->


