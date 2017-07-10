---
title: "Microsoft Intune için sürüm notları"
description: "Intune sürüm notları"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 751bd0bc90b762c5b51b85fae2129e53773b54fe
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="release-notes-for-microsoft-intune"></a>Microsoft Intune için sürüm notları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Windows'un en yeni sürümü için araçlar, raporlar ve yükseltme lisansları sağlayan tümleştirilmiş, bulut tabanlı bir istemci yönetimi çözümüdür. Ayrıca, bilgisayarlarınızın güncel kalmasına ve güvenli olmasına yardımcı olur. Ayrıca, Intune, ağdaki mobil cihazlarınızı Exchange ActiveSync üzerinden veya doğrudan Intune üzerinden yönetmenizi sağlar. Aşağıdaki sürüm notlarında Microsoft Intune hakkında önemli bilgiler ve bilinen sorunlar açıklanmaktadır.

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## <a name="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail"></a>iOS ve Android için gruplar arasında kaynak erişim profillerinin değiştirilmesi başarısız olabilir
**Sorun:** Gruplar arasında e-posta veya Basit Sertifika Kayıt Protokolü (SCEP) kaynak erişim profillerini değiştirdiğinizde, profiller çakışabilir ve başarısız olabilir. Örneğin, şirket içi Exchange server’ı işaret eden, Grup A’ya hedeflenen mevcut bir e-posta profiliniz olduğunu farz edelim. Ardından Exchange Online’a işaret eden, Grup B’ye hedeflenen yeni bir e-posta profili oluşturduğunuzu düşünelim. Kullanıcıları Grup A’dan Grup B’ye taşıdığınızda, cihazlar şirket içi Exchange e-posta profilini koruyacak ve Grup B’ye hedeflenen Exchange Online e-posta profilini yüklemeye çalışacaktır.

Bu noktada, aşağıdakilerden biri gerçekleşir: 
* E-posta profilleri A ve B aynıysa, cihaz, e-posta profili B zaten e-posta profili A’yı içerdiğinden, e-posta profili B’yi reddeder.
* Örnekte belirtildiği gibi, e-posta profili A, e-posta profili B’den farklı ise, sonuçta cihazda iki e-posta profili olur.

> [!NOTE]
> Konak adı ve kullanıcı adı için kullanılan öznitelik, bir e-posta profili değerinden ayırt etmek için denetlenir.

Her iki durumda, bir kullanıcının e-postaya veya istemcinin SCEP sertifikasına erişiminin yanlışlıkla kaldırılmaması amacıyla, kaynak erişim profili (e-posta profili) cihazdan kaldırılmamıştır.

**Geçici çözüm:** Yok.

## <a name="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause"></a>Bir proxy sunucusunda kimlik doğrulaması yapması gereken bir Windows 8.1 cihaz kaydettiğinizde, kayıt işlemi görünür bir neden olmadan başarısız oluyor
**Sorun:** Bir Windows 8.1 cihazı kaydettiğinizde ve cihazın kayıt işlemi sırasında bir proxy sunucusuna kimlik doğrulaması yapması gerektiğinde, cihaz proxy sunucusu kimlik bilgilerini önbelleğe almadıysa kayıt başarısız olur. Proxy sunucusu için kimlik bilgileri cihazda önbelleğe alınmadığında, kayıt işlemi kullanıcının kimlik bilgilerini belirtmesini beklemelidir. Ancak, proxy sunucusu kimlik bilgilerini sağlama istemi kayıtta görünmez. Sonuçta proxy sunucusunda kayıt işleminin kimlik doğrulaması yapılamaz. Bu hatanın görünür bir göstergesi kullanıcıya sunulmaz.

**Geçici çözüm:** Kimliği doğrulanmış bir proxy sunucusunun kullanıldığı bir ağa kaydedilmesi gereken Windows 8.1 cihazları için proxy sunucusuna kimlik bilgilerini cihazı kaydetmeden önce ayarlayın ve kaydedin. Bir Windows 8.1 cihazında kimlik bilgilerini ayarlamak ve kaydetmek için:

1.  Windows 8.1 cihazında Internet Explorer’ı açın.
2.  Proxy sunucusu kimlik bilgileri istendiğinde, kimlik bilgilerini girin ve **Kimlik bilgilerimi anımsa** seçeneğini belirleyin.
3.  Cihazı kaydedin.

## <a name="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs"></a>AD FS'de cihaz kimlik doğrulaması etkinleştirildiğinde Windows Phone 8.1 cihazların Microsoft Intune'la kaydedilmesi başarısız oluyor
**Sorun:** Bir Windows Phone 8.1 cihazını kaydettiğinizde, Active Directory Federasyon Hizmetleri'nde (AD FS) genel kimlik doğrulama ilkesinin bir parçası olarak cihaz kimlik doğrulaması için isteğe bağlı ayar etkinse, kayıt başarısız olur.

**Geçici çözüm:** AD FS sunucusunda **genel kimlik doğrulama ilkesini Düzenle** bölümündeki **Cihaz kimlik doğrulamasını etkinleştir**seçeneğinin işaretini kaldırarak cihaz kimlik doğrulamasını devre dışı bırakın. Daha fazla bilgi için bkz. [Kimlik Doğrulama İlkelerini Yapılandırma](http://technet.microsoft.com/library/dn486781.aspx).


## <a name="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability"></a>Android için Microsoft Intune Uygulaması Kaydırma Aracı’nın yerleşik bir kaldırma yeteneği yoktur
**Sorun:** **Android için Microsoft Intune Uygulaması Kaydırma Aracı**’nın yerleşik bir aracı kaldırma işlevi yoktur.

**Geçici çözüm:** Aracın yükleneceği konuma göz atın ve dizini silin. Varsayılan yükleme konumu: **C:\Program Files\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool. Uygulama sarmalama aracı hakkında daha fazla bilgi için bkz. [Android uygulamalarını Uygulama Sarmalama Aracı ile yönetim için hazırlama](/intune/app-wrapper-prepare-android).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>Windows 8 veya Windows 8.1 çalıştıran bilgisayarlarda uzaktan yardım kullanılamıyor
**Sorun:** Bu sürümde, Windows 8 veya Windows 8.1 çalıştıran bilgisayarlarda uzaktan yardım özelliği kullanılamaz.

**Geçici çözüm:** Yok.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Otomatik olarak eklenen alıcılar için uyarı bildirimleri çalışmayabilir
**Sorun:** Alıcılar bir uyarı bildirimine otomatik olarak eklendiyse her zaman bir uyarı almayabilirler.

**Geçici çözüm:** Alıcıların ileti bildirimlerini aldığından emin olmak için alıcıları uyarı bildirimlerine elle eklemelisiniz.

## <a name="language-support-in-the-azure-portal"></a>Azure portalında dil desteği
Azure önizleme portalı şu dilleri desteklemektedir: Çince (Basitleştirilmiş), Çince (Geleneksel), Çekçe, Felemenkçe, İngilizce, Almanca, Macarca, İtalyanca, Japonca, Portekizce (Brezilya), Portekizce (Portekiz), Rusça, İspanyolca, İngilizce, Fransızca, Korece, Lehçe, İsveççe, Türkçe.

Intune Yönetici Konsolu ve kullanıcıya yönelik mobil deneyimler, Azure portalının desteklediği tüm dillere ek olarak Danca, Yunanca, Fince, Norveççe ve Rumence destekler.
