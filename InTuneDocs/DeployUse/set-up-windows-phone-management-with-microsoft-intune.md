---
title: "Windows 10 Mobile ve Windows Phone yönetimini kurma | Microsoft Intune"
description: "Microsoft Intune ile, Windows 10 Mobile veya Windows Phone cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f28cce75626df1115283dc98547adcb97ee1cb4
ms.openlocfilehash: ce460c1b87b4759dcdeed061c2342b68dd491820


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Microsoft Intune ile Windows Phone ve Windows 10 Mobile yönetimini ayarlama

Bir Intune yöneticisi olarak Windows 10 Mobile ve Windows Phone cihazlar için kaydolmayı ve yönetmeyi iki biçimde etkinleştirebilirsiniz:

- **[Azure Active Directory ile otomatik kaydolma](#azure-active-directory-enrollment)** - Windows 10 ve Windows 10 Mobile kullanıcıları cihazlarını, cihaza bir iş veya okul hesabı ekleyerek kaydeder
- **[Şirket Portalı kaydı](#company-portal-app-enrollment)** - Windows Phone 8.1 ve üzeri sürümlerin kullanıcıları, Şirket Portalı uygulamasını indirip yükledikten sonra uygulamaya iş veya okul hesabı kimlik bilgileri girerek cihazlarını kaydeder.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Şirket Portalı uygulaması kaydı
Kullanıcıların, Intune Şirket Portalı uygulamasını kullanarak cihazlarını yüklemesine ve kaydetmesine izin verebilirsiniz. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmeden Intune’a bağlanır ve kaydolur.

1.  **Intune’u ayarlama**<br>Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi (MDM) yetkilisini](prerequisites-for-enrollment.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve ardından MDM’yi ayarlayın.

2.  **CNAME’ler oluşturma** (isteğe bağlı)<br>Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

    CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. Eğer CNAME kaydı bulunamazsa, kullanıcılardan MDM sunucusu adını (https://manage.microsoft.com) el ile girmeleri istenir. 

    DNS'de EnterpriseEnrollment.contoso.com adresini manage.microsoft.com adresine yönlendiren bir CNAME kaydınız varsa, bunun yerine DNS'de EnterpriseEnrollment.contoso.com adresini enterpriseenrollment-s.manage.microsoft.com adresine yönlendiren bir CNAME oluşturmanızı öneririz. Bu değişikliğin önerilmesinin nedeni, manage.microsoft.com uç noktasının gelecek sürümlerin birinde kayıt için kullanım dışı bırakılacak olmasıdır.

    Birden fazla doğrulanan etki alanı varsa, her bir etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

  |TÜR|Konak adı|Şunu gösterir:|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

  `EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

  `EnterpriseRegistration.windows.net` – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazları destekler

  Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

  Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

3.  **CNAME’i doğrulama**<br>[Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone**’u seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

    ![Windows için mobil cihaz yönetimini ayarlama iletişim kutusu](../media/windows-phone-enrollment.png)

4.  **İsteğe bağlı adımlar**<br>**Dışarıdan yükleme anahtarı ekleme** adımı Windows 10 için gerekli değildir. **Karşıya Kod İmzalama Sertifikası Yükleme** adımı yalnızca Windows Mağazası’nda cihazlar için sunulmayan iş kolu (LOB) uygulamalarını dağıtıyorsanız gereklidir.

5.  **Kullanıcılarınıza, şirket kaynaklarına erişmek için cihazlarını nasıl kaydedeceklerini anlatın.**

    Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](../enduser/enroll-your-device-in-intune-windows.md). Kullanıcılara ayrıca [Cihazınızı Intune’a kaydettiğiniz BT yöneticiniz neleri görebilir?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) sayfasını da gönderebilirsiniz.

    Diğer son kullanıcı görevleri hakkında daha fazla bilgi için şu makalelere bakın:
    - [Son kullanıcılarınıza Microsoft Intune kullanımı hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Windows cihazlar için son kullanıcı kılavuzu](../enduser/using-your-windows-device-with-intune.md)

Cihazlara Şirket Portalı’nı dağıtmayacaksanız, başka bir işlem yapmak gerekmez.  Yönetim konsolundaki 2. ve 3. adımlar rahatça yoksayılabilir.



<!--HONumber=Nov16_HO3-->


