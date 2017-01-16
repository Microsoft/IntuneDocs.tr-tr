---
title: "Microsoft Intune ile Windows cihaz yönetimini ayarlama | Microsoft Docs"
description: "Microsoft Intune ile, Windows 10 cihazları da dahil olmak üzere Windows bilgisayarları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 31d58d9973cca4023186731a5411c9c9e830e32a
ms.openlocfilehash: e24251a066349e23beb94b75a66c5710ba7e41f1


---

# <a name="set-up-windows-device-management"></a>Windows cihaz yönetimini ayarlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bir Intune yöneticisi olarak Windows bilgisayarlar için kaydolmayı ve yönetmeyi iki biçimde etkinleştirebilirsiniz:

- **[Azure Active Directory ile otomatik kaydolma](#azure-active-directory-enrollment)** - Windows 10 ve Windows 10 Mobile kullanıcıları cihazlarını, cihaza bir iş veya okul hesabı ekleyerek kaydeder.

- **[Şirket Portalı kaydı](#set-up-company-portal-app-enrollment)** - Windows 8.1 ve üzeri sürümlerin kullanıcıları, Şirket Portalı uygulaması indirip yükledikten sonra uygulamaya iş veya okul hesabı kimlik bilgileri girerek cihazlarını kaydeder.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Şirket Portalı uygulaması kaydını ayarlama
Kullanıcıların, Intune Şirket Portalı uygulamasını kullanarak cihazlarını yüklemesine ve kaydetmesine izin verebilirsiniz. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmeden Intune’a bağlanır ve kaydolur.

1. **Intune’u ayarlama**<br>
Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi (MDM) yetkilisini](prerequisites-for-enrollment.md#step-2-set-mdm-authority) **Microsoft Intune** olarak ayarlayın ve ardından MDM’yi ayarlayın.

2. **CNAME’ler oluşturma** (isteğe bağlı)<br>Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

    DNS'de EnterpriseEnrollment.contoso.com adresini manage.microsoft.com adresine yönlendiren bir CNAME kaydınız varsa, bunun yerine DNS'de EnterpriseEnrollment.contoso.com adresini enterpriseenrollment-s.manage.microsoft.com adresine yönlendiren bir CNAME oluşturmanızı öneririz. Bu değişikliğin önerilmesinin nedeni, manage.microsoft.com uç noktasının gelecek sürümlerin birinde kayıt için kullanım dışı bırakılacak olmasıdır.

    CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

  |TÜR|Konak adı|Şunu gösterir:|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

  `EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

  `EnterpriseRegistration.windows.net` – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazları destekler

  Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

  Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

3.  **CNAME’i doğrulama**<br>[Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows**’u seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

4.  **İsteğe bağlı adımlar**<br>**Dışarıdan yükleme anahtarı ekleme** adımı Windows 10 için gerekli değildir. **Karşıya Kod İmzalama Sertifikası Yükleme** adımı yalnızca Windows Mağazası’nda cihazlar için sunulmayan iş kolu (LOB) uygulamalarını dağıtacaksanız gereklidir.

6.  **Kullanıcılara cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın.**

    Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO3-->


