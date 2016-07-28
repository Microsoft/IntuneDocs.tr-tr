---
title: "Microsoft Intune için sürüm notları | Microsoft Intune"
description: "Intune sürüm notları"
keywords: 
author: Staciebarker
manager: arob98
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 376e6c1ae229187ab8ec73390f091f1d534365dd
ms.openlocfilehash: b7643ccb64185adb1eb4326a19d56814d8667462


---

# Microsoft Intune için sürüm notları
Microsoft Intune, Windows'un en yeni sürümü için araçlar, raporlar ve yükseltme lisansları sağlayan tümleştirilmiş, bulut tabanlı bir istemci yönetimi çözümüdür ve bilgisayarlarınızı güncel ve güvenli tutar. Ayrıca, Intune, ağdaki mobil cihazlarınızı Exchange ActiveSync üzerinden veya doğrudan Intune üzerinden yönetmenizi sağlar. Aşağıdaki sürüm notlarında Microsoft Intune hakkında önemli bilgiler ve bilinen sorunlar açıklanmaktadır.


## Exchange Online için koşullu erişim uygulandığında Android kullanıcıları e-posta gönderemiyor.

Cihazlarında Samsung Android 5.1.1 ve üzeri çalıştıran kullanıcılar, Exchange Online için koşullu erişim yapılandırıldığında e-posta gönderemiyor. Samsung, sorunun, Android 5.1.1 ve üzerindeki yerleşik posta istemcileriyle ilgili olduğunu kabul etmektedir ve şu anda bir çözüm üzerinde çalışmaktadır.

**Geçici Çözüm 1:** Son kullanıcıların Android için Outlook uygulaması kullanmasını öneriyoruz.

**Geçici Çözüm 2:** Etkilenen kullanıcıların e-posta göndermesini sağlamak için, aşağıdaki adımları uygulayabilirsiniz:

1. Etkilenen kullanıcıyı, Exchange Online için koşullu erişim ilkesinin "muaf tutulan gruplar" bölümündeki bir güvenlik grubuna yerleştirin.
2. Kullanıcının, yerleşik e-posta istemcisinde geçici olarak e-posta eşitlemesine izin verin.
3. Etkilenen kullanıcıyı muaf tutulan gruptan kaldırın ve kullanıcının artık e-posta gönderebildiğini onaylayın.

Microsoft, bir düzeltme veya ilave geçici çözümler için Samsung ile yakından çalışmaya devam edecektir.



## iOS ve Android için gruplar arasında kaynak erişim profillerinin değiştirilmesi başarısız olabilir
**Sorun:** Gruplar arasında e-posta veya Basit Sertifika Kayıt Protokolü (SCEP) kaynak erişim profillerini değiştirdiğinizde, profiller çakışabilir ve başarısız olabilir. Örneğin, şirket içi Exchange server’ı işaret eden, Grup A’ya hedeflenen mevcut bir e-posta profiliniz olduğunu ve ardından Exchange online’a işaret eden, Grup B’ye hedeflenen yeni bir e-posta profili oluşturduğunuzu düşünelim. Kullanıcıları Grup A’dan Grup B’ye taşıdığınızda, cihazlar şirket içi Exchange e-posta profilini koruyacak ve Grup B’ye hedeflenen Exchange online e-posta profilini yüklemeye çalışacaktır.

Bu noktada, aşağıdakilerden biri gerçekleşir: 
* E-posta profilleri A ve B aynıysa, cihaz, e-posta profili B zaten e-posta profili A’yı içerdiğinden, e-posta profili B’yi reddeder.
* Yukarıdaki örnekte belirtildiği gibi, e-posta profili A, e-posta profili B’den farklı ise, sonuçta cihazda iki e-posta profili olur.

**Not:** Ana bilgisayar adı ve kullanıcı adı için kullanılan öznitelik, bir e-posta profili değerinden ayırt etmek için denetlenir.

Yukarıdaki her iki durumda, bir kullanıcının e-postaya veya istemcinin SCEP sertifikasına erişiminin yanlışlıkla kaldırılmaması amacıyla, kaynak erişim profili (e-posta profili) cihazdan kaldırılmamıştır.

**Geçici çözüm:** Yok.

## Bir proxy sunucusunda kimlik doğrulaması yapması gereken bir Windows 8.1 cihaz kaydettiğinizde, kayıt işlemi hatanın nedenine yönelik görünür bir gösterge olmadan başarısız oluyor
**Sorun:** Bir Windows 8.1 cihazı kaydettiğinizde ve cihazın kayıt işlemi sırasında bir proxy sunucusuna kimlik doğrulaması yapması gerektiğinde, cihaz proxy sunucusu kimlik bilgilerini önbelleğe almadıysa kayıt başarısız olur. Proxy sunucusu için kimlik bilgileri cihazda önbelleğe alınmadığında, kayıt işlemi kullanıcının kimlik bilgilerini belirtmesini beklemelidir. Ancak, proxy sunucusu kimlik bilgilerini sağlama istemi kayıt işlemi sırasında görüntülenmez. Sonuç olarak kayıt işlemi proxy sunucusunda kimlik doğrulaması yapamaz ve bu hatanın görünür bir göstergesi kullanıcıya sunulmaz.

**Geçici çözüm:** Kimliği doğrulanmış bir proxy sunucusunun kullanılmasını gerektiren bir ağa kaydedilmesi gereken Windows 8.1 cihazları için, proxy sunucusu için kimlik bilgilerini cihazı kaydetmeden önce yapılandırın ve kaydedin. Bir Windows 8.1 cihazında kimlik bilgilerini yapılandırmak ve kaydetmek için:

1.  Windows 8.1 cihazında **Internet Explorer**’ı açın.

2.  Proxy sunucusu kimlik bilgileri istendiğinde, kimlik bilgilerini girin ve **Kimlik bilgilerimi anımsa**seçeneğini belirleyin.

3.  Cihazı kaydedin.

## AD FS'de cihaz kimlik doğrulaması etkinleştirildiğinde Windows Phone 8.1 cihazların Microsoft Intune'la kaydedilmesi başarısız oluyor
**Sorun:** Bir Windows Phone 8.1 cihazını kaydettiğinizde, Active Directory Federasyon Hizmetleri'nde (AD FS) genel kimlik doğrulama ilkesinin bir parçası olarak cihaz kimlik doğrulaması için isteğe bağlı ayar etkinse, kayıt başarısız olur.

**Geçici çözüm:** AD FS sunucusunda **genel kimlik doğrulama ilkesini Düzenle** bölümündeki **Cihaz kimlik doğrulamasını etkinleştir**seçeneğinin işaretini kaldırarak cihaz kimlik doğrulamasını devre dışı bırakın. Daha fazla bilgi için bkz. [Kimlik Doğrulaması İlkelerini Yapılandırma](http://technet.microsoft.com/library/dn486781.aspx)


## Android için Microsoft Intune Uygulaması Kaydırma Aracı’nın yerleşik bir kaldırma yeteneği yoktur
**Sorun:** **Android için Microsoft Intune Uygulaması Kaydırma Aracı**’nın yerleşik bir aracı kaldırma işlevi yoktur.

**Geçici çözüm:** Aracın yükleneceği konuma göz atın ve dizini silin. Varsayılan yükleme konumu: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Uygulama kaydırma aracı hakkında daha fazla bilgi için, bkz. [Android uygulamalarını Uygulama Kaydırma Aracı ile yönetim için hazırlama](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## Windows 8 veya Windows 8.1 çalıştıran bilgisayarlarda uzaktan yardım kullanılamıyor
**Sorun:** Bu sürümde, Windows 8 veya Windows 8.1 çalıştıran bilgisayarlarda uzaktan yardım özelliği kullanılamaz.

**Geçici çözüm:** Yok.

## Otomatik olarak eklenen alıcılar için uyarı bildirimleri çalışmayabilir
**Sorun:** Bir alıcı bir uyarı bildirimine otomatik olarak eklendiyse her zaman bir uyarı almayabilir.

**Geçici çözüm:** Alıcıların ileti bildirimlerini aldığından emin olmak için alıcıları uyarı bildirimlerine elle eklemelisiniz.

## Azure önizleme portalında dil desteği
Azure önizleme portalı, yeni bir platformda inşa edilmiştir ve şu dilleri desteklemektedir: Çince (Basitleştirilmiş), Çince (Geleneksel), Çekçe, Felemenkçe, İngilizce, Almanca, Macarca, İtalyanca, Japonca, Portekizce (Brezilya), Portekizce (Portekiz), Rusça, İspanyolca, İngilizce, Fransızca, Korece, Lehçe, İsveççe, Türkçe.

Intune Yönetici Konsolu ve son kullanıcıya yönelik mobil deneyimler, Azure Önizleme portalının desteklediği tüm dillere ek olarak, Danca, Yunanca, Fince, Norveççe ve Rumence destekler.



<!--HONumber=Jul16_HO3-->


