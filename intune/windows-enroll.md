---
title: "Windows cihazlarını kaydetme"
titlesuffix: Azure portal
description: "Windows cihazları için Intune mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fea5a61da77a3f96e006ee9ceb4ec3d8de645072
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="enroll-windows-devices"></a>Windows cihazlarını kaydetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, BT yöneticilerinin Windows kaydını kullanıcıları için kolaylaştırmasına yardımcı olmaktadır. [Intune’u kurduğunuzda](setup-steps.md) kullanıcılar, iş veya okul hesaplarıyla [oturum açarak](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) Windows cihazlarını kaydederler.  

Bir Intune yöneticisi olarak, kayıt sürecini aşağıdaki yollarla basitleştirebilirsiniz:
- [Otomatik kaydı etkinleştirme](#enable-windows-10-automatic-enrollment) (Azure AD Premium gereklidir)
- [CNAME kaydı](#simplify-windows-enrollment-without-azure-ad-premium)
- [Toplu kaydı etkinleştirme](windows-bulk-enroll.md) (Azure AD Premium ve Windows Yapılandırma Tasarımcısı gereklidir)
- [Özel bir ileti ekleyerek](windows-enrollment-status.md) kaydolan kullanıcılarınızı karşılayabilir ve ilke ayarları uygulanırken ilerlemeyi görüntüleyebilirsiniz

Windows cihaz kaydını nasıl basit hale getirebileceğinizi iki faktör belirler:

- **Azure Active Directory Premium kullanıyor musunuz?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium), Enterprise Mobility + Security ve diğer lisanslama planlarına dahildir.
- **Kullanıcılar hangi Windows istemci sürümlerini kaydedecekler?** <br>Windows 10 cihazları iş veya okul hesabı eklenerek otomatik olarak kaydedilebilir. Önceki sürümlerin Şirket Portalı uygulamasını kullanarak kaydolması gerekir.

||**Azure AD Premium**|**Diğer AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Otomatik kayıt](#enable-windows-10-automatic-enrollment) |[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|
|**Önceki Windows sürümleri**|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|

Otomatik kayıt kullanabilen kuruluşlar, Windows Yapılandırma Tasarımcısı uygulamasını kullanarak [cihazları toplu kaydetmeyi](windows-bulk-enroll.md) de yapılandırabilirler.

**Çok kullanıcı desteği**<br>
Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış olan cihazlar artık Intune tarafından çok kullanıcılı yönetim için destekleniyor. Standart kullanıcılar, Azure AD kimlik bilgileriyle oturum açtığında kullanıcı adlarına atanmış uygulama ve ilkeleri alırlar. Kullanıcılar, uygulama yükleme gibi self servis senaryoları için Şirket Portalını şu anda kullanamaz.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Azure AD Premium olmadan Windows kaydını kolaylaştırma
Kayıt isteklerini otomatik olarak Intune sunucularına yönlendiren bir etki alanı adı sunucusu (DNS) diğer adı (CNAME kayıt türü) oluşturarak kullanıcılarınız için kayıt işlemini kolaylaştırabilirsiniz. Bir DNS CNAME kaynak kaydı oluşturmazsanız Intune’a bağlanmaya çalışan kullanıcılar kayıt sırasında Intune sunucu adını girmek zorunda kalırlar.

**1. Adım: CNAME oluşturma** (isteğe bağlı)<br>
Şirketinizin etki alanı için CNAME DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. CNAME kaydı bulunamazsa, kullanıcıların MDM sunucu adını (enrollment.manage.microsoft.com) el ile girmesi istenir.

|Tür|Konak adı|Şunu gösterir:|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 saat|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 saat|

Birden fazla UPN sonekiniz varsa her etki alanı için bir CNAME oluşturmanız ve EnterpriseEnrollment-s.manage.microsoft.com adresine yönlendirmeniz gerekir. Contoso kullanıcıları name@contoso.com adresini kullanıyor ancak e-posta/UPN olarak name@us.contoso.com ve name@eu.constoso.com öğelerini de kullanıyorlarsa Contoso DNS yöneticisinin aşağıdaki CNAME’leri oluşturması gerekir:

|Tür|Konak adı|Şunu gösterir:|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 saat|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 saat|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 saat|

`EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

**2. Adım: CNAME'i doğrulama** (isteğe bağlı)<br>
Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Intune dikey penceresinde **Cihazları kaydet** > **Windows Kaydı**’nı seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin URL'sini girin ve ardından **Otomatik Algılamayı Sına**’yı seçin.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini anlatma
Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın.

> [!NOTE]
> Windows'un belirli sürümlerinde, son kullanıcıların atadığınız Windows uygulamalarını görüntüleyebilmesi için Şirket Portalı web sitesinde Microsoft Edge üzerinden erişmesi gerekir. Google Chrome, Mozilla Firefox ve Internet Explorer gibi diğer tarayıcılar bu filtreleme türünü desteklemez.

Son kullanıcı kayıt yönergeleri için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Ayrıca kullanıcılara [BT yöneticim cihazımda neleri görebilir?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) sayfasındaki bilgilere göz atmalarını da söyleyebilirsiniz.

Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Azure'da Inture kullanarak Windows cihazlarını yönetirken dikkat edilmesi gerekenler](/intune-classic/deploy-use/intune-on-azure).
