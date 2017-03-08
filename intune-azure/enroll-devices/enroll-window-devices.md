---
title: "Windows cihazlarını kaydetme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows cihazları için Intune mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 02/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 7262093700dab3a7befd5b82ac9f8ee3dde22dcf
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-windows-devices"></a>Windows cihazlarını kaydetme 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Windows cihazlarında kaydı ayarlamak için aşağıdaki yöntemlerden birini kullanın:

- [**Azure Active Directory Premium ile Windows 10 ve Windows 10 Mobile otomatik kaydı**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Bu yöntem yalnızca Windows 10 ve Windows 10 Mobile cihazları için geçerlidir.
 -  Bu yöntemi kullanabilmeniz için Azure Active Directory Premium’a sahip olmanız gerekir. Aksi takdirde, Windows 8.1 ve Windows Phone 8.1 için verilen kayıt yöntemini kullanın.
 -  Otomatik kaydı etkinleştirmemeyi seçerseniz, Windows 8.1 ve Windows Phone 8.1 için verilen kayıt yöntemini kullanın.

- [**CNAME’yi yapılandırarak Windows 8.1 ve Windows Phone 8.1 kaydı**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - Windows 8.1 ve Windows Phone 8.1 cihazlarının kaydını yapmak için bu yöntemi kullanmalısınız.


## <a name="prerequisites"></a>Önkoşullar

Aşağıdaki önkoşullardan bazıları henüz Intune Azure önizlemesine alınmamışsa, bunları klasik Intune yönetim konsolundan gerçekleştirmeniz gerekir.

- [Özel bir etki alanı adı yapılandırma](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Mobil cihaz yönetimi (MDM) yetkilisini](set-mdm-authority.md) **Microsoft Intune** olarak ayarlama
- [Şirket Portalı uygulamasını yapılandırma](/intune-azure/manage-apps/company-portal-app.md)
- Kullanıcılara lisansları atama

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>CNAME’yi yapılandırarak Windows 8.1 ve Windows Phone 8.1 kaydını ayarlama

Kullanıcıların, Intune Şirket Portalı’nı kullanarak cihazlarını yüklemesine ve kaydetmesine izin verebilirsiniz. DNS CNAME kaynak kayıtları oluşturursanız, kullanıcılar sunucu adı girmeden Intune’a bağlanır ve kaydolur.

1. **CNAME’ler oluşturma** (isteğe bağlı)<br>
 Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden enterpriseenrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz.

    CNAME DNS girişlerini oluşturma isteğe bağlı olmakla birlikte, CNAME kayıtları kullanıcılar için kaydolmayı kolaylaştırır. CNAME kaydı bulunamazsa, kullanıcıların MDM sunucu adını (enrollment.manage.microsoft.com) el ile girmesi istenir.

    Birden fazla doğrulanan etki alanı varsa, her bir etki alanı için bir CNAME kaydı oluşturun. CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

    CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

  |TÜR|Konak adı|Şunu gösterir:|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 Saat|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Saat|

  `EnterpriseEnrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler

  `EnterpriseRegistration.windows.net` – İş veya okul hesabı kullanılarak Azure Active Directory’ye kaydolacak Windows 8.1 ve Windows 10 Mobile cihazları destekler

  Şirketiniz kullanıcı kimlik bilgileri için birden fazla etki alanı kullanıyorsa, her etki alanı için bir CNAME kaydı oluşturun.

  Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden EnterpriseEnrollment-s.manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. DNS kaydındaki değişikliklerin yaygınlaştırılması 72 saat kadar sürebilir. DNS kaydı yaygınlaştırılıncaya kadar Intune’da DNS değişikliğini doğrulayamazsınız.

2.  **CNAME’i doğrulama**<br>[Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone**’u seçin. **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini girin ve ardından **Otomatik Algılamayı Sına**'yı seçin.

3.  **İsteğe bağlı adımlar**<br>**Dışarıdan yükleme anahtarı ekleme** adımı Windows 10 için gerekli değildir. <br>**Karşıya Kod İmzalama Sertifikası Yükleme** adımı yalnızca cihazlara Windows Mağazası’nda sağlanmayan iş kolu (LOB) uygulamalarını dağıtıyorsanız gereklidir.

4.  **Kullanıcılara cihazlarını nasıl kaydedeceklerini ve cihazları yönetim altında olduğunda nelerle karşılaşabileceklerini anlatın.**

    Son kullanıcı kayıt talimatları için bkz. [Windows cihazınızı Intune'a kaydetme](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows). Ayrıca, kullanıcıları [BT yöneticim cihazımda neleri görebilir](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) bağlantısına da yönlendirebilirsiniz.

    Son kullanıcı görevleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da son kullanıcı deneyimi hakkında kaynaklar](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).

Cihazlara Şirket Portalı’nı dağıtmayacaksanız, başka bir işlem yapmak gerekmez.  Yönetim konsolundaki 2. ve 3. adımlar rahatça yoksayılabilir.

