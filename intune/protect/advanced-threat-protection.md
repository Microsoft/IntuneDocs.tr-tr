---
title: Use Microsoft Defender ATP in Microsoft Intune - Azure | Microsoft Docs
description: Use Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) with Intune, including setup and configuration, onboarding of your Intune devices with ATP, and then use a devices ATP risk assessment with your Intune device compliance and conditional access policies to protect network resources.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 889b0a7562f1a663556e955271681e0747aeb3c4
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199178"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Enforce compliance for Microsoft Defender ATP with Conditional Access in Intune

You can integrate Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) with Microsoft Intune as a Mobile Threat Defense solution. Integration can help you prevent security breaches and limit the impact of breaches within an organization. Microsoft Defender ATP works with devices that run Windows 10 or later.

To be successful, you use the following configurations in concert:

- **Establish a service-to-service connection between Intune and Microsoft Defender ATP**. This connection lets Microsoft Defender ATP collect data about machine risk from Windows 10 devices you manage with Intune.
- **Use a device configuration profile to onboard devices with Microsoft Defender ATP**. You onboard devices to configure them to communicate with Microsoft Defender ATP and to provide data that helps assess their risk level.
- **Use a device compliance policy to set the level of risk you want to allow**. Risk levels are reported by Microsoft Defender ATP. Devices that exceed the allowed risk level are identified as non-compliant.
- **Use a conditional access policy** to block users from accessing corporate resources from devices that are non-compliant.

When you integrate Intune with Microsoft Defender ATP, you can take advantage of ATPs Threat & Vulnerability Management (TVM) and [use Intune to remediate endpoint weakness identified by TVM](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Example of using Microsoft Defender ATP with Intune

The following example helps explain how these solutions work together to help protect your organization. For this example, Microsoft Defender ATP and Intune are already integrated.

Consider an event where someone sends a Word attachment with embedded malicious code to a user within your organization.

- Kullanıcı eki açar ve içeriği etkinleştirir.
- Bir yükseltilmiş ayrıcalık saldırısı başlar ve uzak makinedeki saldırgan, kurbanın cihazında yönetici haklarına sahip olur.
- Daha sonra saldırgan, kullanıcının diğer cihazlarına uzaktan erişir. Bu güvenlik ihlali tüm kuruluşu etkileyebilir.

Microsoft Defender ATP can help resolve security events like this scenario.

- In our example, Microsoft Defender ATP detects that the device executed abnormal code, experienced a process privilege escalation, injected malicious code, and issued a suspicious remote shell.
- Based on these actions from the device, Microsoft Defender ATP [classifies the device as high-risk](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) and includes a detailed report of suspicious activity in the Microsoft Defender Security Center portal.

Because you have an Intune device compliance policy to classify devices with a *Medium* or *High* level of risk as non-compliant, the compromised device is classified as non-compliant. This classification allows your conditional access policy to kick in and block access from that device to your corporate resources.

## <a name="prerequisites"></a>Önkoşullar

To use Microsoft Defender ATP with Intune, be sure you have the following configured, and ready for use:

- Enterprise Mobility + Security E3 ve Windows E5 (veya Microsoft 365 Kurumsal E5) için lisanslı kiracı
- Azure AD’ye katılmış [Intune tarafından yönetilen](../enrollment/windows-enroll.md) Windows 10 cihazların olduğu Microsoft Intune ortamı
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and access to the Microsoft Defender Security Center (ATP portal)

> [!NOTE]
> Microsoft Defender ATP is not supported with iOS and Android Intune app protection policies.

## <a name="enable-microsoft-defender-atp-in-intune"></a>Enable Microsoft Defender ATP in Intune

The first step you take is to set up the service-to-service connection between Intune and Microsoft Defender ATP. This requires administrative access to both the Microsoft Defender Security Center, and to Intune.

### <a name="to-enable-defender-atp"></a>To enable Defender ATP

You only need to enable Defender ATP a single time per tenant.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Endpoint security** > **Microsoft Defender ATP**, and then select **Open the Microsoft Defender Security Center**.

   ![Select to open the Microsoft Defender Security Center](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. In **Microsoft Defender Security Center**:
    1. **Ayarlar** > **Gelişmiş özellikler**’i seçin.
    2. **Microsoft Intune bağlantısı** için **Açık** seçeneğini belirleyin:

        ![Intune bağlantısını etkinleştirme](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. **Tercihleri kaydet**’i seçin.

4. Return to **Microsoft Defender ATP** in the Microsoft Endpoint Manager Admin Center. Under **MDM Compliance Policy Settings**, set **Connect Windows devices version 10.0.15063 and above to Microsoft Defender ATP** to **On**.

5. **Kaydet**’i seçin.

> [!TIP]
> When you integrate a new application to Intune Mobile Threat Defense and enable the connection to Intune, Intune creates a classic conditional access policy in Azure Active Directory. Each MTD app you integrate, including [Defender ATP](advanced-threat-protection.md) or any of our additional [MTD partners](mobile-threat-defense.md#mobile-threat-defense-partners), creates a new classic conditional access policy. These policies can be ignored, but should not be edited, deleted, or disabled.
>
> If the classic policy is deleted, you will need to delete the connection to Intune that was responsible for its creation, and then set it up again. This recreates the classic policy. Its not supported to migrate classic policies for MTD apps to the new policy type for conditional access.
>
> Classic conditional access policies for MTD apps:
>
> - Are used by Intune MTD to require that devices are registered in Azure AD so that they have a device ID before communicating to MTD partners. The ID is required so that devices and can successfully report their status to Intune.
> - Have no effect on any other Cloud apps or Resources.
> - Are distinct from conditional access policies you might create to help manage MTD.
> - By default, don’t interact with other conditional access policies you use for evaluation.
>
> To view classic conditional access policies, in [Azure](https://portal.azure.com/#home), go to **Azure Active Directory** > **Conditional Access** > **Classic policies**.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Onboard devices by using a configuration profile

After you establish the service-to-service connection between Intune and Microsoft Defender ATP, you onboard your Intune managed devices to ATP so that data about their risk level can be collected and used. To onboard devices, you use a device configuration profile for Microsoft Defender ATP.

When you established the connection to Microsoft Defender ATP, Intune received a Microsoft Defender ATP onboarding configuration package from Microsoft Defender ATP. This package is deployed to devices with the device configuration profile. The configuration package configures devices to communicate with [Microsoft Defender ATP services](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan files, detect threats, and report the risk to Microsoft Defender ATP.

After you onboard a device using configuration package, you don't need to do it again. [Bir grup ilkesi veya System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) kullanarak da cihaz ekleyebilirsiniz.

### <a name="create-the-device-configuration-profile"></a>Create the device configuration profile

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Configuration profiles** > **Create profile**.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzeri**’ni seçin
5. For **Profile type**, select **Microsoft Defender ATP (Windows 10 Desktop)** .
6. Şu ayarları yapılandırın:

   - **Microsoft Defender ATP client configuration package type**: Select **Onboard** to add the configuration package to the profile. Yapılandırma paketini profilden çıkarmak için **Çıkar**’ı seçin.
  
     > [!NOTE]
     > If you've properly established a connection with Microsoft Defender ATP, Intune will automatically **Onboard** the configuration profile for you, and the **Microsoft Defender ATP client configuration package type** setting will not be available.
  
   - **Sample sharing for all files**: **Enable** allows samples to be collected, and shared with Microsoft Defender ATP. For example, if you see a suspicious file, you can submit it to Microsoft Defender ATP for deep analysis. **Not configured** doesn't share any samples to Microsoft Defender ATP.
   - **Expedite telemetry reporting frequency**: For devices that are at high risk, **Enable** this setting so it reports telemetry to the Microsoft Defender ATP service more frequently.

     [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) has more details on these Microsoft Defender ATP settings.

7. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin, böylece profil oluşturulur.
8. [Assign the device configuration profile](../configuration/device-profile-assign.md) to devices you want to assess with Microsoft Defender ATP.

## <a name="create-and-assign-the-compliance-policy"></a>Create and assign the compliance policy

The compliance policy determines the level of risk that you consider as acceptable for a device.

### <a name="create-the-compliance-policy"></a>Uyumluluk ilkesini oluşturma

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Devices** > **Compliance policies** > **Create policy**.
3. Bir **Ad** ve **Açıklama** girin.
4. **Platform** olarak **Windows 10 ve üzerini** seçin.
5. Under **Settings**, select **Microsoft Defender ATP**.
6. Set **Require the device to be at or under the machine risk score** to your preferred level.

   Threat level classifications are [determined by Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Temiz**: En güvenli düzeydir. The device can't have any existing threats and still access company resources. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir. (Microsoft Defender ATP users the value *Secure*.)
   - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Devices with medium or high threat levels aren't compliant.
   - **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
   - **High**: This level is the least secure and allows all threat levels. So devices that with high, medium, or low threat levels are considered compliant.

7. **Tamam**’ı ve **Oluştur**’u seçerek değişikliklerinizi kaydedin (ve ilkeyi oluşturun).
8. [Assign the device compliance policy](create-compliance-policy.md#assign-the-policy) to applicable groups.

## <a name="create-a-conditional-access-policy"></a>Create a Conditional Access policy

The Conditional Access policy blocks access to resources for devices that exceed the threat level you set in your compliance policy. You can block access from the device to corporate resources, such as SharePoint or Exchange Online.

> [!TIP]
> Koşullu Erişim, bir Azure Active Directory (Azure AD) teknolojisidir. The Conditional Access node accessed from the Microsoft Endpoint Manager Admin Center is the same node as accessed from *Azure AD*.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Endpoint security** > **Conditional Access** > **New policy**.

3. İlke için bir **Ad** girin ve **Kullanıcılar ve gruplar**’ı seçin. İlke için grupları eklemek üzere Dahil Et veya Hariç Tut seçeneklerini kullanın ve **Bitti**’yi seçin.

4. **Bulut uygulamaları**’nı ve ardından hangi uygulamaların korunacağını seçin. Örneğin **Uygulama seçin**’e tıklayın, **Office 365 SharePoint Online** ve **Office 365 Exchange Online**’ı seçin.

   Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

5. **Koşullar** > **İstemci uygulamaları**’nı seçerek ilkeyi uygulamalara ve tarayıcılara uygulayın. Örneğin **Evet**’i seçin ve ardından **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i etkinleştirin.

   Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

6. Select **Grant** to apply Conditional Access based on device compliance. Örneğin **Erişim ver** > **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin.

    Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.

7. **İlkeyi etkinleştir**’i ve **Oluştur**’u seçerek değişikliklerinizi kaydedin.

## <a name="monitor-device-compliance"></a>Cihaz uyumluluğunu izleme

Next, monitor the state of devices that have the Microsoft Defender ATP compliance policy.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Monitor** > **Policy compliance**.

3. Find your Microsoft Defender ATP policy in the list, and see which devices are compliant or noncompliant.

## <a name="view-onboarding-status"></a>View onboarding status

To view the onboarding status of all Intune-managed Windows 10 devices, you can go to **Device compliance** > **Microsoft Defender ATP**. From this page, you can also initiate the creation of a device configuration profile for onboarding more devices to Microsoft Defender ATP.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft Defender ATP Conditional Access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)

[Microsoft Defender ATP risk dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)

[Use security tasks with ATPs Vulnerability Management to remediate issues on devices](atp-manage-vulnerabilities.md).

[Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)
