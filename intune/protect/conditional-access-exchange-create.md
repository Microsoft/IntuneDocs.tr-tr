---
title: Create Exchange Conditional Access policy
titleSuffix: Microsoft Intune
description: Configure Conditional Access for Exchange on-premises and legacy Exchange Online Dedicated in Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 644297777e8a103d6ffdc5f025ebf8f29591fda8
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188461"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Create a Conditional Access policy for Exchange on-premises and legacy Exchange Online Dedicated

This article shows you how to configure Conditional Access for Exchange on-premises based on device compliance.

Ayrılmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa, hesap yöneticinize başvurun. To control email access to Exchange on-premises or to your legacy Exchange Online Dedicated environment, configure Conditional Access to Exchange on-premises in Intune.

## <a name="before-you-begin"></a>Başlamadan önce

Before you can configure Conditional Access, verify the following configurations exist:

- Your Exchange version is **Exchange 2010 SP1 or later**. Exchange Server İstemci Erişimi Sunucusu (CAS) dizisi desteklenir.

- You have installed and use the [Exchange Active Sync on-premises Exchange connector](exchange-connector-install.md), which connects Intune to on-premises Exchange.

    >[!IMPORTANT]  
    >Intune abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler.  However, each on-premises Exchange connector is specific to a single Intune tenant and cannot be used with any other tenant.  Birden çok şirket içi Exchange kuruluşunuz varsa, her Exchange kuruluşu için ayrı bağlayıcılar ayarlayabilirsiniz.

- The connector for an on-premises Exchange organization can install on any machine as long as that machine can communicate with the Exchange server.

- Bağlayıcı **Exchange CAS ortamını** destekler. Intune supports installing the connector on the Exchange CAS server directly. We recommend you install it on a separate computer because of the additional load the connector puts on the server. Bağlayıcıyı yapılandırırken Exchange CAS sunucularından biriyle iletişim kurabilecek şekilde yapılandırmanız gerekir.

- **Exchange ActiveSync**, sertifika tabanlı kimlik doğrulaması veya kullanıcı kimlik bilgileri girişiyle yapılandırılmalıdır.

- When Conditional Access policies are configured and targeted to a user, before a user can connect to their email, the **device** they use must be:
  - Intune’a **kayıtlı** veya etki alanına katılmış bir bilgisayar olmalıdır.
  - **Azure Active Directory’de kayıtlı olmalıdır**. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.

- Azure AD Cihaz Kayıt Hizmeti (DRS), Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. Customers who have already deployed the ADFS Device Registration Service don't see registered devices in their on-premises Active Directory. **Bu, Windows bilgisayarları ve Windows Phone cihazları için geçerli değildir**.

- Söz konusu cihaza dağıtılan cihaz uyumluluk ilkeleriyle **uyumluluk**.

- If the device doesn't meet Conditional Access settings, the user is presented with one of the following messages when they sign in:
  - If the device isn't enrolled with Intune, or isn't registered in Azure Active Directory, a message displays with instructions about how to install the Company Portal app, enroll the device, and activate email. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki cihaz kaydıyla ilişkilendirir.
  - If the device isn't compliant, a message displays that directs the user to the Intune Company Portal website, or the Company Portal app. From the company portal, they can find information about the problem and how to remediate it.

### <a name="support-for-mobile-devices"></a>Mobil cihaz desteği

- Windows Phone 8.1 ve üzeri
- iOS’ta yerel e-posta uygulaması.
- Android 4 veya sonraki sürümlerdeki Gmail gibi EAS posta istemcileri.
- EAS posta istemcileri **Android iş profili cihazları:** Android iş profili cihazlarında yalnızca **iş profilindeki** **Gmail** ve **Android Enterprise için Nine Work** desteklenir. For Conditional Access to work with Android work profiles, you must deploy an email profile for the Gmail or Nine Work for Android Enterprise app, and also deploy those apps as a required installation.

> [!NOTE]
> Microsoft Outlook for Android and iOS is not supported via the Exchange on-premises connector. If you want to leverage Azure Active Directory Conditional Access policies and Intune App Protection Policies with Outlook for iOS and Android for your on-premises mailboxes, please see [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).

### <a name="support-for-pcs"></a>Bilgisayarlar için destek

The native **Mail** application on Windows 8.1 and later (when enrolled into MDM with Intune)

## <a name="configure-exchange-on-premises-access"></a>Şirket içi Exchange erişimini yapılandırma

Before you can use the following procedure to set up Exchange on-premises access control, you must install and configure at least one [Intune on-premises Exchange connector](exchange-connector-install.md) for Exchange on-premises.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Go to **Tenant administration** > **Exchange access**, and then select **Exchange On-premises access**.

3. On the **Exchange on-premises access** pane, choose **Yes** to *Enable Exchange on-premises access control*.

4. Under **Assignment**, choose **Select groups to include**, and then select one or more groups to configure access.

   Members of the groups you select have the Conditional Access policy for Exchange on-premises access applied to them. Users who receive this policy must enroll their devices in Intune and be compliant with the compliance profiles before they can access Exchange on-premises.

5. To exclude groups, choose **Select groups to exclude**, and then select one or more groups that are exempt from requirements to enroll devices and to be compliant with the compliance profiles before accessing Exchange on-premises. 

6. Next, configure settings for the Intune on-premises Exchange connector.  Under **Setup** on the *Exchange on-premises access* window, select **Exchange ActiveSync on-premises connector** and then select the connector for the Exchange organization that you want to configure.

7. Under **Settings**, choose **User notifications** to modify the default email message that’s sent to users if their device isn't compliant and they want to access Exchange on-premises. İleti şablonunda Biçimlendirme dili kullanılır.  Ayrıca yazarken iletinin nasıl görüneceğini gösteren bir önizleme de görebilirsiniz.
   > [!TIP]
   > Biçimlendirme dili hakkında daha fazla bilgi edinmek için bu Wikipedia [makalesine](https://en.wikipedia.org/wiki/Markup_language) bakın.
 
   Select **OK** to save your edits to complete configuration of Exchange on-premises access.

8. Next, select **Advanced Exchange Active Sync access settings** to open the *Advanced Exchange ActiveSync access settings* pane where you configure device access rules:  

   - For **Unmanaged device access**, set the global default rule for access from devices that are not affected by Conditional Access or other rules:

     - **Allow access** - All devices can access Exchange on-premises immediately. Devices that belong to the users in the groups you configured as included in the previous procedure are blocked if they're later evaluated as not compliant with the compliant policies or not enrolled in Intune.

     - **Block access** and **Quarantine** – All devices are immediately blocked from accessing Exchange on-premises initially. Devices that belong to users in the groups you configured as included in the previous procedure get access after the device enrolls in Intune and is evaluated as compliant. 

       Android devices that *do not* run Samsung Knox standard don’t support this setting and are always blocked.

   -  For **Device platform exceptions**, select **Add**, and then specify platform details as needed for your environment. 
   
      If the **Unmanaged device access** setting is set to **Blocked**, devices that are enrolled and compliant are allowed even if there's a platform exception to block them.  
   
   Select **OK** to save your edits.

9. Select **Save** to save the Exchange Conditional Access policy.

Next, create a compliance policy and assign it to the users for Intune to evaluate their mobile devices, See [Get started with device compliance](device-compliance-get-started.md).

## <a name="next-steps"></a>Sonraki adımlar

[Troubleshooting Intune on-premises Exchange connector in Microsoft Intune](https://support.microsoft.com/help/4471887)
