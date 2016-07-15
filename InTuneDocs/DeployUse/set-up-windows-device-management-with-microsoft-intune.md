---
title: "Microsoft Intune ile Windows cihaz yönetimini ayarlama | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6951ccdb0e37489217ef939f0cbf6fc1133a6d3c
ms.openlocfilehash: c18445385e8361cf01948b583f08e992658a8762


---

# Windows cihaz yönetimini ayarlama
Intune’la, şirket e-postasına ve uygulamalarına erişim sağlamak üzere Windows bilgisayarları için KCG ("kendi cihazını getir") cihaz kaydını etkinleştirebilirsiniz. Azure Active Directory ile kullanılan bu özellik ayrıca, yeni Windows 10 cihazlarını yönetime getirmenin ve bilgisayarın görüntüsünü yeniden oluşturmak zorunda kalmadan şirket kaynaklarına erişim kazanmanın hızlı ve müdahale gerektirmeyen bir yolunu sağlar. Kayıt yapıldıktan sonra, kullanıcılar oturum açabilir ve Intune yönetim konsolu kullanılarak ilkeler, uygulamalar ve ayarlarda cihazları hedeflenebilir. Ayrıca, [Microsoft Intune’la Windows Phone yönetimini ayarlamak](set-up-windows-phone-management-with-microsoft-intune.md) veya Intune istemcisini kullanarak [Intune istemci yazılımıyla bilgisayarları yönetmek](manage-windows-pcs-with-microsoft-intune.md) isteyebilirsiniz.

DNS CNAME oluşturmak, kullanıcıların sunucu adı girmeden bağlantı kurmalarına ve Intune’a kaydolmalarına yardımcı olur.

### Windows cihaz yönetimini ayarlama

  1.  Şirketinizin etki alanı için **CNAME** DNS kaynak kaydını oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. Birden çok doğrulanmış etki alanı varsa, her etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları şu bilgileri içermelidir:

  |TÜR|Konak adı|Şunu gösterir:|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

    DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

    **EnterpriseEnrollment-s.manage.microsoft.com** – E-postanın etki alanı adından etki alanı tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler.

    **EnterpriseRegistration.windows.net** – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazlarını destekler.

  2.  [Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows** öğelerine tıklayın.
  ![Windows cihaz yönetimi iletişim kutusu](../media/enroll-intune-winenr.png)
  3.  **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini yazın ve ardından **Otomatik Algılamayı Sına**'ya tıklayın.

### Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmeye hazırlanma](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


