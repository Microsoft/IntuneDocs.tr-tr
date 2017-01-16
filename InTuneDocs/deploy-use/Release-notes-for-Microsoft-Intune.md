---
title: "Microsoft Intune için sürüm notları | Microsoft Docs"
description: "Intune sürüm notları"
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: fd300a5dfe6d6976491988453ec69e99668889fb


---

# <a name="release-notes-for-microsoft-intune"></a>Microsoft Intune için sürüm notları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Windows'un en yeni sürümü için araçlar, raporlar ve yükseltme lisansları sağlayan tümleştirilmiş, bulut tabanlı bir istemci yönetimi çözümüdür. Ayrıca, bilgisayarlarınızın güncel kalmasına ve güvenli olmasına yardımcı olur. Ayrıca, Intune, ağdaki mobil cihazlarınızı Exchange ActiveSync üzerinden veya doğrudan Intune üzerinden yönetmenizi sağlar. Aşağıdaki sürüm notlarında Microsoft Intune hakkında önemli bilgiler ve bilinen sorunlar açıklanmaktadır.


## <a name="android-users-cant-send-email-when-conditional-access-for-exchange-online-is-implemented"></a>Exchange Online için koşullu erişim uygulandığında Android kullanıcıları e-posta gönderemiyor.

**Sorun:** Cihazlarında Samsung Android 5.1.1 ve sonraki sürümleri çalıştıran kullanıcılar, Exchange Online için koşullu erişim ayarlandığında e-posta gönderemiyor. Samsung, sorunun, Android 5.1.1 ve sonraki sürümlerdeki yerleşik posta istemcileriyle ilgili olduğunu kabul etmektedir ve bir çözüm üzerinde çalışmaktadır.

**Geçici Çözüm 1:** Kullanıcıların Android için Outlook uygulaması kullanmasını öneriyoruz.

**Geçici Çözüm 2:** Etkilenen kullanıcıların e-posta göndermesine izin vermek için aşağıdaki adımları uygulayabilirsiniz:

1. Etkilenen her kullanıcıyı, Exchange Online için koşullu erişim ilkesinin "muaf tutulan gruplar" bölümündeki bir güvenlik grubuna yerleştirin.
2. Kullanıcının, yerleşik e-posta istemcisinde geçici olarak e-posta eşitlemesine izin verin.
3. Etkilenen kullanıcıyı muaf tutulan gruptan kaldırın ve kullanıcının artık e-posta gönderebildiğini onaylayın.

Microsoft, bir düzeltme veya ilave geçici çözümler için Samsung ile yakından çalışmaya devam edecektir.



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

**Geçici çözüm:** Aracın yükleneceği konuma göz atın ve dizini silin. Varsayılan yükleme konumu: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Uygulama sarmalama aracı hakkında daha fazla bilgi için bkz. [Android uygulamalarını Uygulama Sarmalama Aracı ile yönetim için hazırlama](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81"></a>Windows 8 veya Windows 8.1 çalıştıran bilgisayarlarda uzaktan yardım kullanılamıyor
**Sorun:** Bu sürümde, Windows 8 veya Windows 8.1 çalıştıran bilgisayarlarda uzaktan yardım özelliği kullanılamaz.

**Geçici çözüm:** Yok.

## <a name="alert-notifications-for-recipients-that-are-automatically-added-might-not-work"></a>Otomatik olarak eklenen alıcılar için uyarı bildirimleri çalışmayabilir
**Sorun:** Alıcılar bir uyarı bildirimine otomatik olarak eklendiyse her zaman bir uyarı almayabilirler.

**Geçici çözüm:** Alıcıların ileti bildirimlerini aldığından emin olmak için alıcıları uyarı bildirimlerine elle eklemelisiniz.

## <a name="language-support-in-the-azure-portal"></a>Azure portalında dil desteği
Azure önizleme portalı şu dilleri desteklemektedir: Çince (Basitleştirilmiş), Çince (Geleneksel), Çekçe, Felemenkçe, İngilizce, Almanca, Macarca, İtalyanca, Japonca, Portekizce (Brezilya), Portekizce (Portekiz), Rusça, İspanyolca, İngilizce, Fransızca, Korece, Lehçe, İsveççe, Türkçe.

Intune Yönetici Konsolu ve kullanıcıya yönelik mobil deneyimler, Azure portalının desteklediği tüm dillere ek olarak Danca, Yunanca, Fince, Norveççe ve Rumence destekler.



<!--HONumber=Dec16_HO2-->


