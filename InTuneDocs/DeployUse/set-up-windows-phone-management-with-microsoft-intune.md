---
title: "Windows 10 Mobile ve Windows Phone yönetimini kurma | Microsoft Intune"
description: "Microsoft Intune ile, Windows 10 Mobile veya Windows Phone cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: 344f1cf4367deb12288f9c361e043d345f9846bb


---


# Microsoft Intune ile Windows Phone ve Windows 10 Mobile yönetimini ayarlama
Windows cihazınızı ayarlamak için [buradan](../enduser/using-your-windows-device-with-intune.md) yardım alabilirsiniz.

Windows 10 Mobile veya Windows Phone cihazlarını Microsoft Intune’la yönetebilmeniz için, önce cihazların Intune’la iletişim kurabilmesi gerekir. Bunu basitleştirmek için bir DNS kaydı oluşturabilirsiniz ve bu sayede kullanıcıların sunucu adresini girmesi gerekmez. Aşağıdaki adımlar, kullanıcılar için kaydın nasıl basitleştirileceğini açıklar.  

Çoğu senaryoda, kullanıcılar Şirket Portalı uygulamasını Windows Mağazası’ndan yükleyebilir. Windows Phone 8.0 cihazlarını yönetiyorsanız veya Windows Phone cihazlarına Şirket Portalı’nı dağıtmanız gerekiyorsa, Şirket Portalı uygulamasını da indirmeli ve imzalamalısınız. Bkz. [Windows Phone 8.0 yönetimini ayarlama](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Intune’u ayarlama** Henüz bu işlemi yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2.  **Kayıt sunucusu adresi için bir DNS diğer adı ayarlama** (isteğe bağlı)

    DNS diğer adı (CNAME kayıt türü) oluşturmak, kullanıcıların cihazlarını kaydetmelerini kolaylaştırır. CNAME DNS girdisi Windows cihaz yönetiminde isteğe bağlı olsa da, Windows cihaz yönetimi işlemi sırasında işleri kolaylaştırmak için, gerektiğinde bir veya birden çok kayıt oluşturmanız önerilir. Hiç CNAME kaydı bulunamazsa, kullanıcıdan MDM sunucu adını el ile girmesi istenir.

  1.  Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. Birden çok doğrulanmış etki alanı varsa, her etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları şu bilgileri içermelidir:

      |TÜR|Konak adı|Şunu gösterir:|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

      DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

      **EnterpriseEnrollment-s.manage.microsoft.com** – E-postanın etki alanı adından etki alanı tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler.

      **EnterpriseRegistration.windows.net** – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazlarını destekler.

    2.  [Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone**’a tıklayın.

      ![Windows için mobil cihaz yönetimini ayarlama iletişim kutusu](../media/windows-device-enrollment.png)

    3.  **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini yazın ve ardından **Otomatik Algılamayı Sına**'ya tıklayın.

    4.  Kullanıcılarınızın cihazlarını nasıl kaydedeceklerini ve cihazları yönetim altına alındıktan sonra neler bekleyebileceklerini bilmeleri gerekir.
        - [Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md)
        - [Windows cihazları için son kullanıcı rehberi](../enduser/using-your-windows-device-with-intune.md)



Cihazlara Şirket Portalı’nı dağıtmayacaksanız, başka bir işlem yapmak gerekmez.  Yönetim konsolundaki 2. ve 3. adımlar rahatça yoksayılabilir.



<!--HONumber=Aug16_HO1-->


