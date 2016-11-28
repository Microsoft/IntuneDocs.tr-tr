---
title: "iOS ve Mac yönetimini ayarlama | Microsoft Intune"
description: "Microsoft Intune’la, iPad, iPhone ve Mac OS X cihazları gibi iOS cihazlarınız için mobil uygulama yönetimini (MDM) etkinleştirin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cfbf04627892dd700d2e31fabe8bca357f692d51
ms.openlocfilehash: 1d7aa8f028d57d4749706b8632aec342483cac5e


---

# <a name="set-up-ios-and-mac-device-management"></a>iOS ve Mac yönetimini ayarlama
Intune iPad’ler, iPhone’lar ve Mac OS X cihazları için mobil uygulama yönetimini (MDM) etkinleştirir ve kullanıcılara şirket e-postası ve uygulamalarına erişim izni sağlar. Intune’un iOS ve Mac cihazlarını yönetebilmesi için Apple Anında İletim Bildirimi hizmeti (APNs) sertifikası gerekir. Sertifika Intune’a eklendikten sonra, kullanıcılar cihazlarını kaydetmek için Şirket Portalı uygulamasını yükleyebilir veya yönetici [şirkete ait iOS cihazı yönetimini](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) ayarlayabilir.

1.  **Intune’u ayarlama**<br>
    Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](prerequisites-for-enrollment.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2.  **Sertifika imzalama isteği alma**<br>
    Bir yönetici kullanıcı olarak [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) açın, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS ve Mac OS X** &gt; **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifika isteğini indir**’i seçin. Sertifika imzalama isteği (.csr) dosyasını yerel olarak kaydedin. .csr dosyası Apple Anında İletilen Bildirim Sertifikaları Portalı'ndan bir güven ilişkisi sertifikası istemek için kullanılır.

    ![APNs sertifikasını karşıya yükle iletişim kutusu](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Bir Apple Anında İletilen Bildirim Servisi sertifikası alma**<br>
    [Apple Anında İletilen Bildirim Sertifikaları Portalı](http://go.microsoft.com/fwlink/?LinkId=269844)'na gidin ve .csr dosyasını kullanarak APNs sertifikasını oluşturmak için şirketinizin Apple kimliğiyle oturum açın. Apple’ın Anında İletilen Sertifika Portalı’nda **Karşıya Yükle**’yi seçtikten sonra, APNs için kullanılamayan bir .json dosyası alırsınız. İndirme işlemini tamamlayın, **Üçüncü Taraf Sunucular için Sertifikalar** için Apple Anında İletme Sertifikaları Portalı’na dönün ve **İndir**’i seçin.

    APNs (.pem) sertifikasını indirin ve dosyayı yerel olarak kaydedin. 

    > [!NOTE]
    > Bu APNs sertifikasını her yıl yenilemeniz (değiştirmeniz değil) gerekir. Sertifikayı yenilemek üzere aynı Apple kimliğini kullanarak Apple Push Certificate Portal’da oturum açın, sertifikayı indirmek için yine bu konudaki yönergeleri izleyin ve sonra sertifikayı Intune’a yükleyin.

4.  **APNs sertifikasını Intune'a ekleme**<br>
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS ve Mac OS X** &gt; **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifikasını karşıya yükle**’yi seçin. Sertifika (.pem) dosyasına gidin, **Aç**’ı seçin ve **Apple kimliğinizi** girin. APNs sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.

5.  **Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın.**

    Son kullanıcı kayıt talimatları için bkz. [iOS cihazınızı Intune'a kaydetme](../enduser/enroll-your-device-in-intune-ios.md) veya [Mac OS X cihazınızı Intune'a kaydetme](../enduser/enroll-your-device-in-intune-mac-os-x.md). Kayıt işlemi kullanıcıları neler bekleyebilecekleri ve BT yöneticilerinin görebileceği ve göremeyeceği cihaz içeriği hakkında bilgilendirir.

    Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:
    - [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [iOS ve Mac cihazlar için son kullanıcı kılavuzu](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Şirketiniz veya kuruluşunuz kullanıcılarına iOS cihazları satın aldıysa, bu cihazlar [şirkete ait iOS cihazları](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) olarak yönetime kaydedilebilir.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune kaydı için önkoşullar](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO3-->


