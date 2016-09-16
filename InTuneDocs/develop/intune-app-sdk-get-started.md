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
ms.sourcegitcommit: 952cfa4f23f8ba080ce53f6785baceb8a0a367c6
ms.openlocfilehash: 9adcf9ce1c2c6e40b3fcbb6c733585bb73a5cc01


---

# Microsoft Intune Uygulama SDK’sını Kullanmaya Başlama

Bu Başlangıç Kılavuzu, mobil uygulamanızı Microsoft Intune ile Mobil Uygulama Yönetimi için hızlı bir şekilde etkinleştirmenize yardımcı olur. İlk olarak [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünde açıklanan Intune Uygulama SDK’sı avantajlarını öğrenmeniz faydalı olabilir.

Bu kılavuzda, Microsoft Intune ile uygulamanızdaki mobil uygulama yönetimini etkinleştirmeniz için gereken önemli adımlar anlatılmaktadır. Intune Uygulama SDK'sı platformlar genelinde benzer senaryoları destekler ve BT yöneticilerine platformlar genelinde tutarlı bir deneyim sağlamak amacıyla tasarlanmıştır. Ancak, platform sınırlamaları nedeniyle bazı özelliklerin desteklenmesi konusunda küçük farklılıklar vardır.

# Başlarken

## Microsoft Connect Kaydı

Intune Uygulama SDK'sına şu anda Microsoft Connect üzerinden erişilebilir ve bunun için kaydolmanız gerekir. Bunu yapmak için şirket e-postanızı kullanarak bir [Microsoft Hesabı](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X)’na kaydolun.

Intune ekibi isteğinizi inceleyene kadar kaydınız bekleme durumunda kalır. Genellikle 2-3 iş günü içinde yanıt verilir. İsteğiniz onaylandıktan sonra platformlarınız için Intune Uygulama SDK'sını ve tüm ilgili kılavuzları indirebileceğiniz bağlantıları içeren bir e-posta bildirimi alırsınız. Bu kılavuzlara MSDN sitesinden de erişebilirsiniz.

## Mağaza uygulamanızı Microsoft Intune’a kaydetme

**Etkin uygulamanız şirket içinde kullanıma yönelikse ve Apple veya Google uygulama mağazasında kullanıma sunulmayacaksa**: Uygulamanızı kaydetmeniz gerekmez. Bu tür şirket içi uygulamalar söz konusu olduğunda BT yöneticisi, uygulamayı dağıtım için doğrudan Microsoft Intune konsoluna yükler; Intune, uygulamanın SDK ile oluşturulduğunu algılar ve BT yöneticisine bu uygulamaya MAM ilkesini uygulama seçeneği sunar. [SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) bölümüne atlayabilirsiniz.

**Apple veya Google uygulama mağazaları üzerinden müşterilerin kullanımına sunulacak bir uygulama geliştiren ISV iseniz**: Öncelikle uygulamanızı Microsoft Intune’a kaydetmeniz ve kayıt koşullarını kabul etmeniz gerekir. Bu noktada uygulamanın ayrıntılı bağlantısını verebilirsiniz. Daha sonra bir BT yöneticisi, uygulamaya Intune MAM ilkesi uygulayabilir. Kayıt tamamlanıp Microsoft Intune ekibi tarafından onaylanana kadar, uygulamanızın ayrıntılı bağlantısı için yönetici konsolunda MAM ilkesi uygulama seçeneği verilmez. Microsoft ayrıca, uygulamanın kaydedileceği bir Microsoft Intune İş Ortakları web sitesine sahiptir. Bu site, müşterilerin Microsoft Intune MAM ilkesinin uygulama tarafından desteklendiğini bilmesini sağlar.

Kayıt işlemine başlamak için **Microsoft Intune İş Ortağı Sözleşmesi**’ni [gözden geçirin ve imzalayın](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Bu sözleşmede, şirketinizin bir Microsoft Intune uygulama iş ortağı olmadan önce kabul etmesi gereken koşullar açıklanır. Bu belgeyi görüntüleyebilmek için oturum açmanız gerekir. Sözleşmeyi, Intune Uygulama SDK'sı Microsoft Connect sitesindeki Anketler sekmesinin altında veya burada bulabilirsiniz. Sizden ayrıca uygulamanın adı, şirketinizin adı ve uygulamanızın Google veya iTunes mağazasındaki ayrıntılı bağlantısı istenir.

![Microsoft Connect](../media/microsoft-connect.png)

Kaydın talebinin alındığını onaylamak ve kayıt işlemini tamamlamak için kayıt e-posta adresiniz kullanılır. Ayrıca, herhangi bir sorumuz olursa sizinle iletişim kurmak için kayıt e-posta adresinizi kullanırız.

**Kayıt işleminde beklenmesi gerekenler**: Siz formu gönderdikten sonra Microsoft, talebin başarıyla alındığını onaylamak veya kaydı tamamlamak amacıyla ek bilgi istemek için kayıt e-posta adresiniz üzerinden sizinle iletişim kurar. Ayrıca, uygulamanız Microsoft Intune’a başarıyla kaydedildiğinde ve Microsoft Intune iş ortakları sitesinde gösterildiğinde de sizinle iletişim kurulur. Bilgilerin alındığı onaylandıktan sonra uygulamanızın ayrıntılı bağlantısı sonraki aylık Intune Hizmeti güncelleştirmesine dahil edilir. Örneğin kayıt bilgileri Temmuz'da tamamlanmışsa uygulamanın ayrıntılı bağlantısı Ağustos ayının ortalarında desteklenecektir. Mağaza uygulamanızın ayrıntılı bağlantısı gelecekte değişirse uygulamanızı yeniden kaydetmeniz gerekir. Ayrıca, uygulamanızı Intune Uygulama SDK'sının yeni bir sürümüyle güncelleştirirseniz bunu bize bildirmeniz gerekir.

**Not**: Yukarıdaki form ve Intune ekibi ile yapılan e-posta yazışmaları aracılığıyla toplanan tüm bilgiler [Microsoft Gizlilik Bildirimi](https://www.microsoft.com/en-us/privacystatement/default.aspx)’ne uygun olacaktır.

## SDK ile iOS veya Android mobil uygulamanızı MAM için etkinleştirme

iOS mobil uygulamanızı etkinleştirmek için aşağıdakiler gerekir:

1. **[iOS için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-ios.md)**: Bu belgede mobil iOS uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme adımları anlatılır. Bu belgeyi, Intune Uygulama SDK'sı paketinin bir parçası olarak indirdiğiniz belge klasöründe bulabilirsiniz.
2. **iOS için Intune Uygulama SDK’sı**: Microsoft Intune’dan indirilen Intune Uygulama SDK'sı paketinin bir parçası olarak, imzalanmış bir "iOS için Intune Uygulama SDK'sı" klasörü görürsünüz. Bu klasör, iOS içeriğine yönelik tüm Intune Uygulama SDK'larını içerir.

Android mobil uygulamanızı Intune Uygulama SDK'sı ile etkinleştirmek için aşağıdakiler gerekir:

1. **[Android için Intune Uygulama SDK’sı Geliştirici Kılavuzu](intune-app-sdk-android.md)**: Bu belgede, mobil Android uygulamanızı Intune Uygulama SDK’sı ile etkinleştirme adımları anlatılır. Bu belgeyi, Intune Uygulama SDK'sı paketinin bir parçası olarak indirdiğiniz belge klasöründe bulabilirsiniz.
2. **Android için Intune Uygulama SDK’sı**: Microsoft Intune’dan indirilen Intune Uygulama SDK'sı paketinin bir parçası olarak, imzalanmış bir "Android için Intune Uygulama SDK'sı" klasörü görürsünüz. Bu klasör, Android içeriğine yönelik tüm Intune Uygulama SDK'larını içerir.

## Uygulamanızda Telemetriyi kapatma

**iOS için Intune Uygulama SDK’sı**: SDK, kullanım etkinliklerine ilişkin SDK telemetri verilerini varsayılan olarak günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir.

Uygulamanızdan Microsoft Intune’a SDK telemetri verileri göndermek istemiyorsanız **MAMTelemetryDisabled** özelliğini `MAMTelemetryDisabled` içinde “YES” olarak ayarlayarak SDK telemetri iletimini `IntuneMAMSettings`.

**Android için Intune Uygulama SDK’sı**: SDK telemetri verileri SDK aracılığıyla günlüğe kaydedilmez.

## MAM özellikli uygulamanızı Microsoft Intune ile test etme

iOS veya Android Intune Uygulama SDK’nızı kullandırmak (Intune Uygulama SDK’sını tümleştirmek) için gerekli adımları tamamladıktan sonra, son kullanıcı ile BT yöneticisi için tüm uygulama yönetimi ilkelerinin etkinleştirildiğinden ve çalıştığından emin olmanız gerekir. Kullanan uygulamanızı test etmek için aşağıdakiler gerekir:

1. **Microsoft Intune ile MAM özellikli uygulamanızı test etme**: Bu belgede, MAM özellikli iOS veya Android uygulamalarınızı Microsoft Intune ile test etme adımlarını anlatılır. Bu belgeyi, Intune Uygulama SDK'sı paketinin bir parçası olarak indirdiğiniz belge klasöründe bulabilirsiniz.
2. **Microsoft Intune Hesabı**: MAM özellikli uygulamalarınızı Microsoft Intune ile test etmek için bir Microsoft Intune hesabınızın olması gerekir. iOS veya Android mağazası uygulamalarınızı MAM için etkinleştiren bir ISV iseniz Microsoft Intune kaydını, kayıt adımında belirtilen şekilde tamamladıktan sonra bir promosyon kodu alırsınız. Promosyon kodu, 1 yıllık uzatılmış kullanım içeren bir Microsoft Intune deneme sürümüne kaydolmanızı sağlar. Mağazaya gönderilmeyecek bir iş kolu uygulaması geliştiriyorsanız kuruluşunuz aracılığıyla Microsoft Intune’a erişiminizin olması beklenir. [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) ile 1 aylık ücretsiz deneme sürümü için de kaydolabilirsiniz.




<!--HONumber=Sep16_HO2-->


