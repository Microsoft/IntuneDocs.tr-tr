---
# required metadata

title: Microsoft Intune ile iOS ve Mac yönetimini ayarlama | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS ve Mac yönetimini ayarlama
Microsoft Intune kullanarak, iPhone, iPad ve Mac kullanıcılarının şirket e-postasına ve uygulamalarına erişmesini sağlamak için iOS ve Mac OS X cihaz kaydında KCG’yi ("kendi cihazını getir") etkinleştirebilirsiniz. Kayıt yapıldıktan sonra, kullanıcılar Şirket Portalı uygulamasını yükleyebilir ve Intune yönetim konsolu kullanılarak ilkede cihazları hedeflenebilir.

iOS cihazlarını Intune’la yönetebilmeniz için, önce cihazların Intune’la iletişim kurabilmesi gerekir. Apple, Apple Anında İletilen Bildirim Servisi (APNs) sertifikasını içeri aktararak Intune’la bir güven ilişkisi kurulmasını gerektirir.

1.  **Intune’u ayarlama**<br>
    Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2.  **Sertifika imzalama isteği alma**<br>
    Bir yönetici kullanıcı olarak [Microsoft Intune yönetim konsolunu](http://manage.microsoft.com) açın, **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS ve Mac OS X** &gt; **APNs Sertifikasını Karşıya Yükle**'ye gidin ve **APNs sertifika isteğini indir**’e tıklayın. Sertifika imzalama isteği (.csr) dosyasını yerel olarak kaydedin. .csr dosyası Apple Anında İletilen Bildirim Sertifikaları Portalı'ndan bir güven ilişkisi sertifikası istemek için kullanılır.

    ![APNs sertifikasını karşıya yükle iletişim kutusu](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Bir Apple Anında İletilen Bildirim servisi sertifikası alma**<br>
    [Apple Anında İletilen Bildirim Sertifikaları Portalı](http://go.microsoft.com/fwlink/?LinkId=269844)'na gidin ve .csr dosyasını kullanarak APNs sertifikasını oluşturmak için şirketinizin Apple kimliğiyle oturum açın. Apple’ın Anında İletilen Sertifika Portalı’nda **Karşıya Yükle** tıklandıktan sonra, APNs için kullanılamayan bir .json dosyası alırsınız. İndirme işlemini tamamlayın, **Üçüncü Taraf Sunucular için Sertifikalar** için Apple Anında İletme Sertifikaları Portalı’na dönün ve **İndir**’e tıklayın.

    APNs (.pem) sertifikasını indirin ve dosyayı yerel olarak kaydedin. Bu Apple kimliği gelecekte APNs sertifikanızı yenilemek için kullanılır.

4.  **APNs sertifikasını Intune'a ekleme**<br>
    [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **iOS ve Mac OS X** &gt; **APNs Sertifikasını Karşıya Yükle**’ye gidin, **APNs sertifikasını karşıya yükle**. **Gözat**’a tıklayarak sertifika (.pem) dosyasına göz atın, **Aç**’a tıklayın ve sonra da **Apple Kimliğinizi** girin. APNs sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir. Kullanıcılara şirket portalı ile şirket kaynaklarına nasıl erişeceklerini anlatın

5.  **Kullanıcılarınızın cihazlarını nasıl kaydedeceklerini ve cihazları yönetim altına alındıktan sonra neler bekleyebileceklerini bilmeleri gerekir.**<br>
    Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler [Şirketiniz veya kuruluşunuz kullanıcılarına iOS cihazları satın aldıysa, bu cihazlar [şirkete ait iOS cihazları](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) olarak yönetime kaydedilebilir.](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Ayrıca Bkz.

### Microsoft Intune’da cihazları kaydetmeye hazırlanma
[Get ready to enroll devices in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->


