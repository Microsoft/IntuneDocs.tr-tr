---
title: "Microsoft Intune ile Windows cihaz yönetimini ayarlama | Microsoft Docs"
description: "Microsoft Intune ile, Windows cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: e020ac2a4f600a94e7409e04c4c48f0c405c56cf


---

# <a name="set-up-windows-device-management"></a>Windows cihaz yönetimini ayarlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Windows cihazlarında kaydı ayarlamak için aşağıdaki yöntemlerden birini kullanın:

- **[Azure Active Directory Premium ile Windows 10 ve Windows 10 Mobile otomatik kaydı](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  Bu yöntem yalnızca Windows 10 ve Windows 10 Mobile cihazları için geçerlidir.
 -  Bu yöntemi kullanabilmeniz için Azure Active Directory Premium’a sahip olmanız gerekir. Aksi takdirde, Windows 8.1 ve Windows Phone 8.1 için verilen kayıt yöntemini kullanın.
 -  Otomatik kaydı etkinleştirmemeyi seçerseniz, Windows 8.1 ve Windows Phone 8.1 için verilen kayıt yöntemini kullanın.


- **[CNAME’yi yapılandırarak Windows 8.1 ve Windows Phone 8.1 kaydı](#set-up-windows-8--1-and-windows-phone-8--1-enrollment-by-configuring-cname)** 
 - Windows 8.1 ve Windows Phone 8.1 cihazlarının kaydını yapmak için bu yöntemi kullanmalısınız.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>CNAME’yi yapılandırarak Windows 8.1 ve Windows Phone 8.1 kaydını ayarlama
Kullanıcıların, Intune Şirket Portalı’nı kullanarak cihazlarını yüklemesine ve kaydetmesine izin verebilirsiniz. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmeden Intune’a bağlanır ve kaydolur.

1. **Intune’u ayarlama**<br>
Henüz yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi (MDM) yetkilisini](prerequisites-for-enrollment.md#step-2-set-mdm-authority) **Microsoft Intune** olarak ayarlayın ve ardından MDM’yi ayarlayın.

2. **CNAME’ler oluşturma** (isteğe bağlı)<br>
Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

    CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. Kaydolma için CNAME kaydı bulunamazsa kullanıcıların MDM sunucu adını el ile girmesi istenir, enrollment.manage.microsoft.com.    

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

4.  **Kullanıcılara cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın.**

    Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)



<!--HONumber=Feb17_HO2-->


