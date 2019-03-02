---
title: Microsoft Intune kullanarak Windows cihazları için kaydı ayarlama
titlesuffix: ''
description: Windows cihazları için kaydı ayarlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2192b6d653bfb51503b006a5045d454c202618f
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234121"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Windows cihazları için kaydı ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale BT yöneticilerinin kullanıcıları için Windows kaydını kolaylaştırmasına yardımcı olur. [Intune’u kurduğunuzda](setup-steps.md) kullanıcılar, iş veya okul hesaplarıyla [oturum açarak](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) Windows cihazlarını kaydederler.  

Bir Intune yöneticisi olarak, kayıt sürecini aşağıdaki yollarla basitleştirebilirsiniz:
- [Otomatik kaydı etkinleştirme](#enable-windows-10-automatic-enrollment) (Azure AD Premium gereklidir)
- [CNAME kaydı](#simplify-windows-enrollment-without-azure-ad-premium)
- [Toplu kaydı etkinleştirme](windows-bulk-enroll.md) (Azure AD Premium ve Windows Yapılandırma Tasarımcısı gereklidir)

Windows cihaz kaydını nasıl basit hale getirebileceğinizi iki faktör belirler:

- **Azure Active Directory Premium kullanıyor musunuz?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium), Enterprise Mobility + Security ve diğer lisanslama planlarına dahildir.
- **Kullanıcılar hangi Windows istemci sürümlerini kaydedecekler?** <br>Windows 10 cihazları iş veya okul hesabı eklenerek otomatik olarak kaydedilebilir. Önceki sürümlerin Şirket Portalı uygulamasını kullanarak kaydolması gerekir.

||**Azure AD Premium**|**Diğer AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Otomatik kayıt](#enable-windows-10-automatic-enrollment) |[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|
|**Önceki Windows sürümleri**|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|[Kullanıcı kaydı](#enable-windows-enrollment-without-azure-ad-premium)|

Otomatik kayıt kullanabilen kuruluşlar, Windows Yapılandırma Tasarımcısı uygulamasını kullanarak [cihazları toplu kaydetmeyi](windows-bulk-enroll.md) de yapılandırabilirler.

## <a name="multi-user-support"></a>Çok kullanıcı desteği

Intune, Windows 10 Oluşturucu güncelleştirmesi çalıştıran ve Azure Active Directory etki alanına katılmış cihazlar için çoklu yönetimi destekler. Standart kullanıcılar Azure AD kimlik bilgileriyle oturum açtığında, kullanıcı adlarına atanmış uygulama ve ilkeler alırlar. Kullanıcılar uygulama yükleme gibi self servis senaryoları için Şirket Portalı'nı şu anda kullanamamaktadır.

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Azure AD Premium olmadan Windows kaydını kolaylaştırma
Kaydolmayı basitleştirmek için, kayıt isteklerini Intune sunucularına yönlendiren bir etki alanı adı sunucusu (DNS) diğer adı (CNAME kayıt türü) oluşturun. Aksi takdirde Intune'a bağlanmaya çalışan kullanıcıların kayıt sırasında Intune sunucu adını girmeleri gerekir.

**1. adım: CNAME oluşturma** (isteğe bağlı)<br>
Şirketinizin etki alanı için CNAME DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. CNAME kaydı bulunamazsa, kullanıcıların MDM sunucu adını (enrollment.manage.microsoft.com) el ile girmesi istenir.

|Tür|Konak adı|Şunu gösterir:|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 saat|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 saat|

Şirket birden fazla UPN soneki kullanıyorsa, her etki alanı için bir CNAME oluşturmanız ve bunları EnterpriseEnrollment-s.manage.microsoft.com adresine yönlendirmeniz gerekir. Örneğin Contoso kullanıcıları e-posta/UPN'leri olarak aşağıdaki biçimleri kullanın:

- name@contoso.com
- name@us.contoso.com
- name@eu.contoso.com

Contoso DNS yöneticisinin aşağıdaki CNAME'leri oluşturması gerekir:

|Tür|Konak adı|Şunu gösterir:|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 saat|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 saat|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 saat|

`EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yayılıncaya kadar DNS değişikliğini Intune'da doğrulayamazsınız.

## <a name="additional-endpoints-are-supported-but-not-recommended"></a>Ek uç noktalar desteklenir, ancak önerilmez
EnterpriseEnrollment-s.manage.microsoft.com, kayıt için tercih edilen FQDN'yi olmakla birlikte, müşteriler tarafından daha önce kullanılmış olan ve desteklenen iki diğer uç nokta vardır. Otomatik bulma sunucunun, ancak kullanıcı için hedef üzerinde bir onay iletisi Tamam dokunması olumsuz etkileyeceğinden (olmadan -s) adresinden EnterpriseEnrollment.manage.microsoft.com ve manage.microsoft.com hem de çalışır. EnterpriseEnrollment-s.manage.microsoft.com adresine işaret ederseniz, kullanıcının bu önerilen yapılandırma, bu nedenle ek doğrulama adımı yapmanız gerekmeyecek

## <a name="alternate-methods-of-redirection-are-not-supported"></a>Yeniden yönlendirme alternatif yöntemler desteklenmez
CNAME yapılandırma dışında bir yöntem kullanılarak desteklenmiyor. Örneğin, için iki enterpriseenrollment-s.manage.microsoft.com/EnrollmentServer/Discovery.svc enterpriseenrollment.contoso.com/EnrollmentServer/Discovery.svc yönlendirmek için bir proxy sunucusu kullanarak veya manage.microsoft.com/EnrollmentServer/Discovery.svc desteklenmiyor.

**2. adım: CNAME'i doğrulama** (isteğe bağlı)<br>
1. [Azure portalında Intune](https://aka.ms/intuneportal)'da **Cihaz kaydı** > **Windows kaydı** > **CNAME Doğrulaması**'nı seçin.
2. **Etki Alanı** kutusuna şirket Web sitesini girin ve ardından **Test Et**'i seçin.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini anlatma
Kullanıcılara Windows cihazlarını nasıl kaydedeceklerini ve cihazları yönetilmeye başladıktan sonra nelerle karşılaşabileceklerini anlatın.

> [!NOTE]
> Windows'un belirli sürümlerinde, son kullanıcıların atadığınız Windows uygulamalarını görüntüleyebilmesi için Şirket Portalı web sitesinde Microsoft Edge üzerinden erişmesi gerekir. Google Chrome, Mozilla Firefox ve Internet Explorer gibi diğer tarayıcılar bu filtreleme türünü desteklemez.

Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Ayrıca kullanıcılara [BT yöneticim cihazımda neleri görebilir?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) sayfasındaki bilgilere göz atmalarını da söyleyebilirsiniz.

>[!IMPORTANT]
> Otomatik MDM kaydını etkinleştirmediyseniz ancak Azure AD’ye katılmış Windows 10 cihazlarınız varsa, kayıt sonrasında Intune konsolunda iki kayıt görünecektir. Azure AD’ye katılmış cihazların, aynı hesabı kullanarak **Hesaplar** > **İş veya okula erişim** ve **Bağlan**’a gitmesini sağlayarak bunu önleyebilirsiniz. 

Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](end-user-educate.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Azure'da Inture kullanarak Windows cihazlarını yönetirken dikkat edilmesi gerekenler](intune-legacy-pc-client.md).
