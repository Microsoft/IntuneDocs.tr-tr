---
title: "Windows cihazlarını kaydetme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows cihazları için Intune mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 687be18cedd063b3c2701937f2522e801e51644b
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-windows-devices"></a>Windows cihazlarını kaydetme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bu konu, BT yöneticilerinin Windows kaydını kullanıcıları için kolaylaştırmasına yardımcı olmaktadır.  Windows cihazları ek adım olmadan kaydedilebilir ancak kayıt işlemini kullanıcılar için kolay hale getirebilirsiniz.

Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış olan cihazlar artık Intune tarafından çok kullanıcılı yönetim için destekleniyor. Bu destek sayesinde farklı standart kullanıcılar, Azure AD kimlik bilgilerini kullanarak cihazda oturum açtığında kullanıcı adlarına atanmış olan uygulamalara ve ilkelere erişecek. Kullanıcılar, uygulama yükleme gibi self servis senaryoları için Şirket Portalını şu anda kullanamaz.

Windows cihaz kaydını nasıl basit hale getirebileceğinizi iki faktör belirler:

- **Azure Active Directory Premium kullanıyor musunuz?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium), Enterprise Mobility + Security ve diğer lisanslama planlarına dahildir.
- **Hangi Windows istemci sürümleri kaydolur?** <br>Windows 10 cihazları iş veya okul hesabı eklenerek otomatik olarak kaydedilebilir. Önceki sürümlerin Şirket Portalı uygulamasını kullanarak kaydolması gerekir.

||**Azure AD Premium**|**Diğer AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Otomatik kayıt](#enable-windows-10-automatic-enrollment) |[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|
|**Önceki Windows sürümleri**|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-azure-ad-premium"></a>Azure AD Premium olmadan Windows kaydını etkinleştirme
Kullanıcıların, Azure AD Premium otomatik kaydı olmadan cihazlarını kaydetmelerine olanak sağlayabilirsiniz. Lisans atadıktan sonra, kullanıcılar kendi iş hesabını kişisel cihazlarına ekledikten veya şirkete ait cihazlarının Azure AD'nize katılmasını sağladıktan sonra kayıt işlemini gerçekleştirebilir. DNS diğer adı (CNAME kayıt türü) oluşturmak, kullanıcıların cihazlarını kaydetmelerini kolaylaştırır. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmek zorunda kalmadan Intune'a bağlanır ve kaydolur.

**1. Adım: CNAME oluşturma** (isteğe bağlı)<br>
Şirketinizin etki alanı için CNAME DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. CNAME kaydı bulunamazsa, kullanıcıların MDM sunucu adını (enrollment.manage.microsoft.com) el ile girmesi istenir.

|Tür|Konak adı|Şunu gösterir:|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 saat|

Birden fazla UPN sonekiniz varsa her etki alanı için bir CNAME oluşturmanız ve EnterpriseEnrollment-s.manage.microsoft.com adresine yönlendirmeniz gerekir. Örneğin Contoso kullanıcıları name@contoso.com adresini kullanıyor ancak e-posta/UPN olarak name@us.contoso.com ve name@eu.constoso.com biçimlerini de kullanıyorsa Contoso DNS yöneticisinin aşağıdaki CNAME kayıtlarını oluşturması gerekir.

|Tür|Konak adı|Şunu gösterir:|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 saat|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 saat|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 saat|

`EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

**2. Adım: CNAME'i doğrulama** (isteğe bağlı)<br>
Azure Intune portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**'u seçin. Intune dikey penceresinde **Cihazları kaydet** > **Windows Kaydı**’nı seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini anlatma
Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın. Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Ayrıca, kullanıcılara [BT yöneticim cihazımda neleri görebilir?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) sayfasındaki bilgileri de anlatabilirsiniz.

Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

