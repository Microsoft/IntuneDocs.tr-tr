---
title: Hızlı Başlangıç - Uyumsuz cihazlara bildirim gönderme
titleSuffix: Microsoft Intune
description: In this quickstart, you use Microsoft Intune to send email notifications to noncompliant devices.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d89cfcafd5452b990509e0fa6fd431a614ee5c1
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410227"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Hızlı Başlangıç: Uyumsuz cihazlara bildirim gönderme

In this quickstart, you'll use Microsoft Intune to send an email notification to the members of your workforce that have noncompliant devices.

Varsayılan olarak, Intune uyumlu olmayan bir cihaz algıladığında hemen cihazı uyumsuz olarak işaretler. Azure Active Directory (Azure AD) [Conditional Access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) then blocks the device. When a device isn't compliant, Intune allows you to add actions for noncompliance, which gives you flexibility to decide what to do. Örneğin uyumsuz cihazları engellemeden önce kullanıcılara uyumlu olmaları için yetkisiz kullanım süresi sağlayabilirsiniz.

One action to take when a device doesn't meet compliance is to send email to the devices user. You can also customize an email notification before sending it. Özellikle şirket logosu ve kişi bilgileri dahil olmak üzere alıcılar, konu ve ileti gövdesini özelleştirebilirsiniz. Intune also includes details about the noncompliant device in the email notification.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

When using device compliance policies to block devices from corporate resources, Azure AD Conditional Access must be set up. If you've completed the [Create a device compliance policy](quickstart-set-password-length-android.md) quickstart, you're using Azure Active Directory. For more information about Azure AD, see [Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) and [common ways to use Conditional Access with Intune](../protect/conditional-access-intune-common-ways-use.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) as a [Global administrator](../fundamentals/users-add.md#types-of-administrators) or an Intune [Service administrator](../fundamentals/users-add.md#types-of-administrators). If you've created an Intune Trial subscription, the account you created the subscription with is the Global administrator.

## <a name="create-a-notification-message-template"></a>Bildirim iletisi şablonu oluşturma

Kullanıcılarınıza e-posta göndermek için bir bildirim iletisi şablonu oluşturun. Cihazın uyumsuz olması durumunda, şablona girdiğiniz ayrıntılar kullanıcılarınıza gönderilen e-postada görüntülenir.

1. In Intune, select **Devices** > **Compliance policies** > **Notifications** > **Create notification**.
2. Aşağıdaki bilgileri girin:

   - **Ad**: *Contoso Yöneticisi*
   - **Konu**: *Cihaz uyumluluğu*
   - **Message**: *Your device is currently not meeting our organization's compliance requirements.*
   - **E-posta üst bilgisi – Şirket logosunu ekle**: Kuruluşunuzun logosunu göstermek için **Etkin** olarak ayarlayın.
   - **E-posta alt bilgisi – Şirket adını ekle**: Kuruluşunuzun adını göstermek için **Etkin** olarak ayarlayın.
   - **E-posta alt bilgisi – Kişi bilgilerini ekle**: Kuruluşunuzdaki kişinin bilgilerini göstermek için **Etkin** olarak ayarlayın.

   ![Intune'da örnek uyumluluk bildirimi iletisi](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. Select **Next** and review your notification. Select **Create** and the notification message template is ready to use.

   > [!NOTE]
   > Daha önceden oluşturulmuş bir Bildirim şablonunu da düzenleyebilirsiniz.

For details about setting your company name, company contact information, and company logo, see the following articles:

- [Company information and privacy statement](../apps/company-portal-app.md#company-information-and-privacy-statement)
- [Support information](../apps/company-portal-app.md#support-information)
- [Company identity branding customization](../apps/company-portal-app.md#company-identity-branding-customization).

## <a name="add-a-noncompliance-policy"></a>Uyumsuzluk ilkesi ekleme

Cihaz uyumluluğu ilkesi oluşturduğunuzda, Intune uyumsuzluk için otomatik olarak bir eylem oluşturur. Intune then marks devices as noncompliant when they fail to meet your compliance policy. Cihazın ne kadar süreyle uyumsuz olarak işaretleneceğini ayarlayabilirsiniz. Ayrıca, uyumluluk ilkesi oluştururken veya mevcut uyumluluk ilkesini güncelleştirirken başka bir eylem ekleyebilirsiniz.

Aşağıdaki adımlar, Windows 10 cihazları için uyumluluk ilkesi oluşturmayı gösterir.

1. In Intune, select **Devices** > **Compliance Policies** > **Create Policy**.

2. Aşağıdaki bilgileri girin:

   - **Ad**: *Windows 10 uyumluluk*
   - **Açıklama**: *Windows 10 uyumluluk ilkesi*
   - **Platform**: Windows 10 ve üzeri

3. **Ayarlar** > **Sistem Güvenliği**’ni seçerek cihazın güvenlikle ilgili ayarlarını görüntüleyin.

4. Configure the following options:

   - **Mobil cihazların kilidini açmak için parola gerektir** ayarını **Gerekli Kıl** olarak belirleyin. Bu ayar, kullanıcılara mobil cihazlarındaki bilgilere erişim verilmeden önce bu kullanıcılardan parola istenip istenmeyeceğini belirtir.

   - **En az parola uzunluğu**’nu **6** olarak ayarlayın. Bu ayar, parolada en az kaç rakam veya karakter bulunması gerektiğini belirtir.

   ![Yeni bir uyumluluk ilkesi için Sistem Güvenliği ayarları](./media/quickstart-send-notification/system-security-settings-01.png)

5. Select **OK** > **OK** > **Create** to create your compliance policy.

6. **Özellikler** > **Uyumsuzluğa yönelik eylemler** > **Ekle**’yi seçin.

7. Açılan **Eylem** kutusunda **Son kullanıcılara e-posta gönder** seçeneğinin belirlendiğini doğrulayın.

8. Select **Message template**,  the template you created earlier in this article, and then **Select** to select the message template.

9. Select **ADD** > **OK** > **Save** to save your changes.

## <a name="assign-the-policy"></a>İlke atama

Uyumluluk ilkesini belirli bir kullanıcı grubuna veya tüm kullanıcılara atayabilirsiniz. When Intune recognizes that a device is noncompliant, the user is notified that they must update their device to meet the compliance policy. Use the following steps to assign the policy.

1. In Intune go to **Devices** > **Compliance Policies** and select the **Windows 10 compliance** policy that you created earlier.

2. **Atamalar**’ı seçin.

3. Açılan **Şuna ata** kutusunda **Tüm Kullanıcılar**’ı seçin. Bu eylem, tüm kullanıcıları seçer. **Windows 10 ve üzeri** cihaza sahip olan ve bu uyumluluk ilkesine uymayan tüm kullanıcılara bildirim gönderilir.

    > [!NOTE]
    > Uyumluluk ilkeleri atarken bazı grupları dahil edebilir veya dışlayabilirsiniz.

4. **Kaydet**'e tıklayın.

When you've successfully created and saved the policy, it will appear in the list of **Compliance policies - Policies**. Listede **Atandı** ayarının **Evet** olarak belirlenmiş olduğuna dikkat edin.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta iş gücünüze ait Windows 10 cihazların en az altı karakter uzunluğunda parolalar gerektirmesi için bir uyumluluk ilkesi oluşturmak ve atamak amacıyla Intune’u kullandınız. Windows cihazları için uyumluluk ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Intune’da Windows cihazları için bir cihaz uyumluluk ilkesi ekleme](compliance-policy-create-windows.md).

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: İstemci uygulaması ekleme ve atama](../apps/quickstart-add-assign-app.md)
