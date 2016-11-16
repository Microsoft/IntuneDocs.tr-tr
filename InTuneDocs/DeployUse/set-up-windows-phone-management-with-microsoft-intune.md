---
title: "Windows 10 Mobile ve Windows Phone yönetimini kurma | Microsoft Intune"
description: "Microsoft Intune ile, Windows 10 Mobile veya Windows Phone cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0b4bf6aa6fa9d693c0458562e7fcb71fc8000bb4
ms.openlocfilehash: 46bd457af51d3fac513cfc36af1766e1e37222cd


---


# Microsoft Intune ile Windows Phone ve Windows 10 Mobile yönetimini ayarlama

Bir Intune yöneticisi olarak Windows 10 Mobile ve Windows Phone cihazlar için kaydolmayı ve yönetmeyi iki biçimde etkinleştirebilirsiniz:

- **[Azure Active Directory ile otomatik kaydolma](#azure-active-directory-enrollment)** - Windows 10 ve Windows 10 Mobile kullanıcıları cihazlarını, cihaza bir iş veya okul hesabı ekleyerek kaydeder
- **[Şirket Portalı kaydı](#company-portal-app-enrollment)** - Windows Phone 8.1 ve üzeri sürümlerin kullanıcıları, Şirket Portalı uygulamasını indirip yükledikten sonra uygulamaya iş veya okul hesabı kimlik bilgileri girerek cihazlarını kaydeder.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Şirket Portalı uygulaması kaydı
Kullanıcıların, Intune Şirket Portalı uygulamasını kullanarak cihazlarını yüklemesine ve kaydetmesine izin verebilirsiniz. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmeden Intune’a bağlanır ve kaydolur. Windows Phone 8.0 cihazlarını yönetiyorsanız veya Windows Phone cihazlarına Şirket Portalı’nı dağıtmanız gerekiyorsa, Şirket Portalı uygulamasını da indirmeli ve imzalamalısınız. Bkz. [Windows Phone 8.0 yönetimini ayarlama](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Intune’u ayarlama**<br>Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi (MDM) yetkilisini](prerequisites-for-enrollment.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve ardından MDM’yi ayarlayın.

2.  **CNAME’ler oluşturma** (isteğe bağlı)<br>Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. Birden fazla doğrulanan etki alanı varsa, her bir etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

  |TÜR|Konak adı|Şunu gösterir:|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

  `EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler.

  `EnterpriseRegistration.windows.net` – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazları destekler

  Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

  Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

3.  **CNAME’i doğrulama**<br>[Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone**’u seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

    ![Windows için mobil cihaz yönetimini ayarlama iletişim kutusu](../media/windows-phone-enrollment.png)

4.  **İsteğe bağlı adımlar**<br>**Dışarıdan yükleme anahtarı ekleme** adımı Windows 10 için gerekli değildir. **Karşıya Kod İmzalama Sertifikası Yükleme** adımı yalnızca Windows Mağazası’nda cihazlar için sunulmayan iş kolu (LOB) uygulamalarını dağıtacaksanız gereklidir. [Daha fazla bilgi edinin](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

5.  **Kullanıcılara bildirme**<br>Kullanıcılarınızın cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra neler bekleyebileceklerini bilmeleri gerekir.
    - [Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Windows cihazları için son kullanıcı rehberi](../enduser/using-your-windows-device-with-intune.md)

Cihazlara Şirket Portalı’nı dağıtmayacaksanız, başka bir işlem yapmak gerekmez.  Yönetim konsolundaki 2. ve 3. adımlar rahatça yoksayılabilir.



<!--HONumber=Oct16_HO3-->


