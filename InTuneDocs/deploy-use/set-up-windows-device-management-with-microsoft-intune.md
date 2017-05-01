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
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: f1291d6eec32ad834d33fcbfff320ce173521a25
ms.lasthandoff: 04/24/2017


---

# <a name="set-up-windows-device-management"></a>Windows cihaz yönetimini ayarlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu, BT yöneticilerinin Windows kaydını kullanıcıları için kolaylaştırmasına yardımcı olmaktadır.  Windows cihazları ek adım olmadan kaydedilebilir ancak kayıt işlemini kullanıcılar için kolay hale getirebilirsiniz.

Windows cihaz kaydını nasıl basit hale getirebileceğinizi iki faktör belirler:
- **Azure Active Directory Premium kullanıyor musunuz?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium), Enterprise Mobility + Security ve diğer lisanslama planlarına dahildir.
- **Hangi Windows istemci sürümleri kaydolur?** <br>Windows 10 cihazları iş veya okul hesabı eklenerek otomatik olarak kaydedilebilir. Önceki sürümlerin Şirket Portalı uygulamasını kullanarak kaydolması gerekir.

||**Azure AD Premium**|**Diğer AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Otomatik kayıt](#enable-windows-10-automatic-enrollment) |[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|
|**Önceki Windows sürümleri**|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Otomatik kayıt olmadan Windows kaydını etkinleştirme
Kullanıcıların, Azure AD Premium otomatik kaydı olmadan cihazlarını kaydetmelerine olanak sağlayabilirsiniz. Lisans atadıktan sonra, kullanıcılar kendi iş hesabını kişisel cihazlarına ekledikten veya şirkete ait cihazlarının Azure AD'nize katılmasını sağladıktan sonra kayıt işlemini gerçekleştirebilir. DNS diğer adı (CNAME kayıt türü) oluşturmak, kullanıcıların cihazlarını kaydetmelerini kolaylaştırır. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmek zorunda kalmadan Intune'a bağlanır ve kaydolur.

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
[Intune yönetim konsolunda](https://manage.microsoft.com), **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows**’u seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini anlatma
Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın.
Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Ayrıca, kullanıcıları [BT yöneticim cihazımda neleri görebilir?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) bağlantısına da yönlendirebilirsiniz.

Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’da cihazları kaydetmenin önkoşulları](prerequisites-for-enrollment.md)

