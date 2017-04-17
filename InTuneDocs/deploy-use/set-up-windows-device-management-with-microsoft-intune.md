---
title: "Microsoft Intune ile Windows cihaz yönetimini ayarlama | Microsoft Docs"
description: "Microsoft Intune ile, Windows cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 771aed4e1c57171183b9a9ea7d9e0f702dc1859c
ms.openlocfilehash: f6014c5500b05762d123b2285ef859d67382e402
ms.lasthandoff: 04/06/2017


---

# <a name="set-up-windows-device-management"></a>Windows cihaz yönetimini ayarlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Windows cihazlarında kaydı ayarlamak için aşağıdaki yöntemlerden birini kullanın:

- [**Azure Active Directory Premium ile Windows 10 otomatik kaydı**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Bu yöntem yalnızca Windows 10 cihazları için kullanılabilir.
 -  Bu yöntemi kullanabilmeniz için Azure Active Directory Premium’a sahip olmanız gerekir.
 -  Otomatik kaydı etkinleştirmemeyi seçerseniz, Windows 8.1 ve Windows Phone 8.1 için verilen kayıt yöntemini kullanın.

- [**Azure AD Premium otomatik kaydını kullanmadan kaydetme**](#enable-windows-enrollment-without-azure-ad-premium)
 - Windows 8.1 ve Windows Phone 8.1 cihazlarının kaydını yapmak için bu yöntemi kullanmalısınız.
 - Azure Active Directory (AD) Premium kullanmak istemiyorsanız, Windows 8.1 ve üstü cihazlarda bu yöntemi kullanabilirsiniz.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Otomatik kayıt olmadan Windows kaydını etkinleştirme
Kullanıcıların, Azure AD Premium otomatik kaydı olmadan cihazlarını yüklemelerine ve kaydetmelerine olanak sağlayabilirsiniz. Bir lisansı kullanıcının hesabına atadıktan sonra kullanıcı bu hesabı bir Windows cihazına ekleyip cihazı yönetim için kaydetmeyi kabul edebilir. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmeden Intune’a bağlanır ve kaydolur.

**1. Adım: CNAME oluşturma** (isteğe bağlı)<br>
Şirketinizin etki alanı için CNAME DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. CNAME kaydı bulunamazsa, kullanıcıların MDM sunucu adını (enrollment.manage.microsoft.com) el ile girmesi istenir.

Birden fazla doğrulanan etki alanı varsa, her bir etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

|TÜR|Konak adı|Şunu gösterir:|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

`EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

**2. Adım: CNAME'i doğrulama** (isteğe bağlı)<br>
[Intune yönetim konsolunda](http://manage.microsoft.com), **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows**’u seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini anlatma
Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın.
Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Ayrıca, kullanıcıları [BT yöneticim cihazımda neleri görebilir?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) bağlantısına da yönlendirebilirsiniz.

Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)

