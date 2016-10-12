---
title: "Microsoft Intune ile Windows cihaz yönetimini ayarlama | Microsoft Intune"
description: "Microsoft Intune ile, Windows 10 cihazları da dahil olmak üzere Windows bilgisayarları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: 149508942b89b15308591e17723884add3ac78ae


---

# Windows cihaz yönetimini ayarlama

Bir Intune yöneticisi olarak Windows bilgisayarlar için kaydolmayı ve yönetmeyi iki biçimde etkinleştirebilirsiniz:

- **[Azure AD ile otomatik kaydolma](#azure-active-directory-enrollment)** - Windows 10 ve Windows 10 Mobile kullanıcıları cihazlarını, cihaza bir iş veya okul hesabı ekleyerek kaydeder
- **[Şirket Portalı kaydı](#company-portal-app-enrollment)** - Windows 8.1 ve üzeri cihazlar, Şirket Portalı uygulaması indirilip yüklenerek, sonra uygulamaya iş veya okul hesabı kimlik bilgileri girilerek kaydedilir.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Şirket Portalı uygulaması kaydını yapılandırma
Kullanıcıların, Intune Şirket Portalı uygulamasını yükleyip cihazlarını kaydetmelerine izin verebilirsiniz. DNS CNAME oluşturmak, kullanıcıların sunucu adı girmeden bağlantı kurmalarına ve Intune’a kaydolmalarına yardımcı olur.

1. **Intune’u ayarlama**<br>
Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](prerequisites-for-enrollment.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2. **CNAME’ler oluşturma** (isteğe bağlı)<br>Kaydolmayı basitleştirmek amacıyla şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları oluşturmak kullanıcılar için kaydolmayı kolaylaştırır. Hiçbir kaydolma CNAME kaydı bulunamazsa, kullanıcılardan MDM sunucu adını `https://manage.microsoft.com` el ile girmeleri istenir.  CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

  |TÜR|Konak adı|Şunu gösterir:|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

  `EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler.

  `EnterpriseRegistration.windows.net` – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazları destekler

  Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

  Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

3.  **CNAME’i doğrulama**<br>[Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows**’a tıklayın. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini yazın ve ardından **Otomatik Algılamayı Sına**'ya tıklayın.

  ![Windows cihaz yönetimi iletişim kutusu](../media/enroll-intune-winenr.png)

4.  **İsteğe bağlı adımlar**<br>**Dışarıdan yükleme anahtarı ekleme** adımı Windows 10 için gerekli değildir. **Karşıya Kod İmzalama Sertifikası Yükleme** adımı yalnızca cihazlara Windows Mağazası’nda bulunmayan iş kolu (LOB) uygulamaları dağıtacaksanız gereklidir. [Daha fazlasını öğrenin](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Kullanıcılara bildirme**<br>Kullanıcılara cihazlarını nasıl kaydedeceklerini ve yönetime alındıktan sonra nelerle karşılaşabileceklerini anlatmanız gerekir:
      - [Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Windows cihazlar için son kullanıcı kılavuzu](../enduser/using-your-windows-device-with-intune.md)

### Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)



<!--HONumber=Sep16_HO4-->


