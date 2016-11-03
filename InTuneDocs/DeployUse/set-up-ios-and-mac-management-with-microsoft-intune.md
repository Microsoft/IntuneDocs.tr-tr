---
title: "iOS ve Mac yönetimini ayarlama | Microsoft Intune"
description: "Microsoft Intune’la, iPad, iPhone ve Mac OS X cihazları gibi iOS cihazlarınız için mobil uygulama yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 263fb9add8d30c0f98af46e46b566f15513db109


---

# iOS ve Mac yönetimini ayarlama
iOS veya Mac cihazınızı ayarlamak için [buradan](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md) yardım bulabilirsiniz.

Intune iPad’ler, iPhone’lar ve Mac OS X cihazları için mobil uygulama yönetimini etkinleştirir ve kullanıcılara şirket e-postasına ve uygulamalarına erişim izni sağlar. Intune’un iOS ve Mac cihazlarını yönetebilmesi için Apple Anında İletim Bildirimi hizmeti (APNs) sertifikası gerekir. Sertifika Intune’a eklendikten sonra, kullanıcılar cihazlarını kaydetmek için Şirket Portalı uygulamasını yükleyebilir veya yönetici [şirkete ait iOS cihazı yönetimini](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) ayarlayabilir.

1.  **Intune’u ayarlama**<br>
    Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](prerequisites-for-enrollment.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2.  **Sertifika imzalama isteği alma**<br>
    Bir yönetici kullanıcı olarak [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) açın, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS ve Mac OS X** &gt; **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifika isteğini indir**’e tıklayın. Sertifika imzalama isteği (.csr) dosyasını yerel olarak kaydedin. .csr dosyası Apple Anında İletilen Bildirim Sertifikaları Portalı'ndan bir güven ilişkisi sertifikası istemek için kullanılır.

    ![APNs sertifikasını karşıya yükle iletişim kutusu](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Bir Apple Anında İletilen Bildirim servisi sertifikası alma**<br>
    [Apple Anında İletilen Bildirim Sertifikaları Portalı](http://go.microsoft.com/fwlink/?LinkId=269844)'na gidin ve .csr dosyasını kullanarak APNs sertifikasını oluşturmak için şirketinizin Apple kimliğiyle oturum açın. Apple’ın Anında İletilen Sertifika Portalı’nda **Karşıya Yükle** tıklandıktan sonra, APNs için kullanılamayan bir .json dosyası alırsınız. İndirme işlemini tamamlayın, **Üçüncü Taraf Sunucular için Sertifikalar** için Apple Anında İletme Sertifikaları Portalı’na dönün ve **İndir**’e tıklayın.

    APNs (.pem) sertifikasını indirin ve dosyayı yerel olarak kaydedin. Bu Apple kimliği gelecekte APNs sertifikanızı yenilemek için kullanılır.

4.  **APNs sertifikasını Intune'a ekleme**<br>
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS ve Mac OS X** &gt; **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifikasını karşıya yükle**’ye tıklayın. **Gözat** ile sertifika (.pem) dosyasına gidin ve **Aç** 'a tıklayarak **Apple Kimliğinizi**girin. APNs sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.

5.  **Kullanıcılara şirket portalı ile şirket kaynaklarına nasıl erişeceklerini anlatın**<br>
    Kullanıcılarınızın cihazlarını nasıl kaydedeceklerini ve cihazları yönetim altına alındıktan sonra neler bekleyebileceklerini bilmeleri gerekir.
    - [Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [iOS ve Mac cihazlar için son kullanıcı kılavuzu](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Şirketiniz veya kuruluşunuz kullanıcılarına iOS cihazları satın aldıysa, bu cihazlar [şirkete ait iOS cihazları](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) olarak yönetime kaydedilebilir.

### Ayrıca bkz.
[Microsoft Intune kaydı için önkoşullar](prerequisites-for-enrollment.md)



<!--HONumber=Sep16_HO4-->


