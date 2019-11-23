---
title: Tutorial - Protect Exchange Online email on unmanaged devices
titleSuffix: Microsoft Intune
description: Learn to secure Office 365 Exchange Online with Intune app protection policies and Azure AD Conditional Access.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/10/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cc997bfb11ebcfe58a6d44705c34a7077a4f787
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410294"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Tutorial: Protect Exchange Online email on unmanaged devices

Learn about using app protection policies with Conditional Access to protect Exchange Online, even when devices aren't enrolled in a device management solution like Intune. Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:

> [!div class="checklist"]
> * Create an Intune app protection policy for the Outlook app. You'll limit what the user can do with app data by preventing "Save As" and restrict cut, copy, and paste actions.
> * Create Azure Active Directory (Azure AD) Conditional Access policies that allow only the Outlook app to access company email in Exchange Online. You'll also require multi-factor authentication (MFA) for Modern authentication clients, like Outlook for iOS and Android.

## <a name="prerequisites"></a>Önkoşullar

Bu öğretici için aşağıdaki abonelik sahip bir test kiracısına ihtiyacınız olacak:

- Azure Active Directory Premium ([ücretsiz deneme](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Intune subscription ([free trial](../fundamentals/free-trial-sign-up.md))
- Exchange içeren Office 365 Business aboneliği ([ücretsiz deneme](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

For this tutorial, when you sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), sign in as a [Global administrator](../fundamentals/users-add.md#types-of-administrators) or an Intune [Service administrator](../fundamentals/users-add.md#types-of-administrators). If you've created an Intune Trial subscription, the account you created the subscription with is the Global administrator.

## <a name="create-the-app-protection-policy"></a>Create the app protection policy

In this tutorial, we’ll set up an Intune app protection policy for iOS for the Outlook app to put protections in place at the app level. We'll require a PIN to open the app in a work context. We'll also limit data sharing between apps and prevent company data from being saved to a personal location.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Apps** > **App protection policies** > **Create policy**, and select **iOS/iPadOS** for the platform.

3. On the **Basics** page, configure the following settings:

   - **Name**: Enter **Outlook app policy test**.
   - **Description**: Enter **Outlook app policy test**.

   The **Platform** value is set to your previous choice.

   Devam etmek için **İleri** 'ye tıklayın.

4. The **Apps** page allows you to choose how you want to apply this policy to apps on different devices. Configure the following options:

   - For **Target to all app types**: Select **No**, and then for **App types**, select the checkbox for **Apps on unmanaged devices**.
   - Click **Select public apps**. In the Apps list, select **Outlook**, and then choose **Select**.  Outlook now appears under *Public apps*.

   Devam etmek için **İleri** 'ye tıklayın.

5. The **Data protection** page provides settings that determine how users interact with data in the apps that this app protection policy applies. Configure the following options:

   Below *Data Transfer*, configure the following settings, leaving all other settings at their default values:

   - For **Send org data to other apps**, select **None**.  
   - For **Receive data from other apps**, select **None**.  
   - For **Save copies of org data**, select **Block**.  
   - For **Restrict cut, copy and paste between other apps**, select **Blocked**. 

   ![Select the Outlook app protection policy data relocation settings](./media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Select **Next** to continue.

6. The **Access requirements** page provides settings to allow you to configure the PIN and credential requirements that users must meet to access apps in a work context. Configure the following settings, leaving all other settings at their default values:

   - For **PIN for access**, select **Require**.
   - For **Work or school account credentials for access**, select **Require**.

   ![Select the Outlook app protection policy access actions](./media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

   Select **Next** to continue.

7. The **Conditional launch** page provides settings to set the sign-in security requirements for your app protection policy. For this tutorial, you don't need to configure these settings.

   Devam etmek için **İleri** 'ye tıklayın.

8. Use the **Assignments** page to assign the app protection policy to groups of users. For this tutorial, you won't assign this policy to a group.  
 don't need to configure these settings.

   Devam etmek için **İleri** 'ye tıklayın.

9. On the **Next: Review + create** page, review the values and settings you entered for this app protection policy. Click **Create** to create the app protection policy in Intune.

The app protection policy for Outlook is created. Next, you'll set up Conditional Access to require devices to use the Outlook app.

## <a name="create-conditional-access-policies"></a>Create Conditional Access policies

Now we’ll create two Conditional Access policies to cover all device platforms.  

- The first policy will require that Modern Authentication clients use the approved Outlook app and multi-factor authentication (MFA). Modern Authentication clients include Outlook for iOS and Outlook for Android.  

- The second policy will require that Exchange ActiveSync clients use the approved Outlook app. (Currently, Exchange Active Sync doesn't support conditions other than device platform). You can configure Conditional Access policies in either the Azure AD portal or the Intune portal. Zaten Intune portalında olduğumuz için ilkeyi burada oluşturalım.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Create an MFA policy for Modern Authentication clients  

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Endpoint security** >  **Conditional access** > **New policy**.  

3. For **Name**, enter **Test policy for modern auth clients**.  

4. **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. **Dahil et** sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

5. Under **Assignments**, select **Cloud apps or actions**. Office 365 Exchange Online e-postalarını korumak istediğimiz için şu adımları izleyeceğiz:

   1. **Dahil et** sekmesinde **Uygulama seç**’i seçin.
   2. **Seçin** öğesini belirleyin.
   3. In the Applications list, select **Office 365 Exchange Online**, and then choose **Select**.
   4. Select **Done** to return to the New policy pane.

   ![Office 365 Exchange Online uygulamasını seçin](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

6. **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.

   1. **Yapılandır** altında **Evet**’i seçin.
   2. On the **Include** tab, select **Any device**.
   3. **Bitti**’yi seçin.

7. On the **Conditions** pane, select **Client apps**.

   1. **Yapılandır** altında **Evet**’i seçin.
   2. Select **Mobile apps and desktop clients** and **Modern authentication clients**.
   3. Clear the other check boxes.
   4. Select **Done** > **Done** to return to the New policy pane.

   ![Select Mobile apps and clients](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

8. **Erişim denetimleri** altında **Ver**’i seçin.

   1. **Ver** bölmesinde **Erişim ver**’i seçin.
   2. Select **Require multi-factor authentication**.
   3. **Onaylı istemci uygulaması gerektir**’e tıklayın.
   4. **Çoklu denetim için** altında **Tüm seçili denetimleri gerektir**’i seçin. Bu ayar, bir cihaz e-postaya erişmeye çalıştığında seçtiğiniz her iki gereksinimin de uygulanmasını sağlar.
   5. **Seçin** öğesini belirleyin.

   ![Select access controls](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

9. Under **Enable policy**, select **On**, and then select **Create**.

   ![Create policy](./media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

The Conditional Access policy for Modern Authentication clients is created. Now you can create a policy for Exchange Active Sync clients.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Create a policy for Exchange Active Sync clients

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Endpoint security** > **Conditional Access** > **New policy**.

3. For **Name**, enter **Test policy for EAS clients**.

4. **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. *Dahil et* sekmesinde **Tüm Kullanıcılar**’ı ve daha sonra **Bitti**’yi seçin.

5. Under **Assignments**, select **Cloud apps or actions**. Select Office 365 Exchange Online email with these steps:

   1. *Dahil et* sekmesinde **Uygulama seç**’i seçin.
   2. **Seçin** öğesini belirleyin.
   3. From the list of *Applications*, select **Office 365 Exchange Online**, and then choose **Select**, and then **Done**.
  
6. **Atamalar** altında **Koşullar** > **Cihaz platformları**’nı seçin.

   1. **Yapılandır** altında **Evet**’i seçin.
   2. On the **Include** tab, select **Any device**, and then select **Done**.

7. On the **Conditions** pane, select **Client apps**.

   1. **Yapılandır** altında **Evet**’i seçin.
   2. Select **Mobile apps and desktop clients**.
   3. Select **Exchange ActiveSync clients** and **Apply policy only to supported platforms**.  
   4. Diğer tüm onay kutularının işaretini kaldırın.  
   5. **Bitti**’yi ve ardından tekrar **Bitti**’yi seçin.  

   ![Apply to supported platforms](./media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

8. **Erişim denetimleri** altında **Ver**’i seçin.

   1. **Ver** bölmesinde **Erişim ver**’i seçin.
   2. **Onaylı istemci uygulaması gerektir**’e tıklayın. Diğer tüm onay kutularının işaretini kaldırın.
   3. **Seçin** öğesini belirleyin.

   ![Require approved client app](./media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

9. Under **Enable policy**, select **On**, and then select **Create**.

Your app protection policies and Conditional Access are now in place and ready to test.

## <a name="try-it-out"></a>Deneme

With the policies you’ve created, devices will need to enroll in Intune and use the Outlook mobile app to access Office 365 email. Bu senaryoyu bir iOS cihazda test etmek için test kiracınızdaki kullanıcılardan birine ait kimlik bilgilerini kullanarak Exchange Online’da oturum açmayı deneyin.

1. Bu testi bir iPhone’da yapmak için **Ayarlar** > **Parolalar ve Hesaplar** > **Hesap Ekle** > **Exchange**’i seçin.

2. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.  
3. **Oturum Aç**’a basın.

4. Test kullanıcısının parolasını girin ve **Oturum aç**’a basın.

5. The message **More information is required** appears, which means you're being prompted to set up MFA. Go ahead and set up an additional verification method.

6. Next you'll see a message that says you're trying to open this resource with an app that isn't approved by your IT department. The message means you're being blocked from using the native mail app. Cancel the sign-in.

7. Open the Outlook app and select **Settings** > **Add Account** > **Add Email Account**.

8. Test kiracınızdaki bir kullanıcıya ait e-posta adresini girin ve **İleri**’ye basın.

9. Press **Sign in with Office 365**. You'll be prompted for additional authentication and registration. Once you've signed in, you can test actions such as cut, copy, paste, and "Save As".

## <a name="clean-up-resources"></a>Kaynakları temizleme

Test ilkelerine artık ihtiyacınız kalmadığında bunları kaldırabilirsiniz.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** **Compliance policies**.

3. **İlke Adı** listesinde test ilkenizin açılır menüsünü ( **...** ) seçin ve daha sonra **Sil**’e tıklayın. Onaylamak için **Tamam**’ı seçin.

4. Select **Endpoint security** > **Conditional access**.

5. In the **Policy Name** list, select the context menu ( **...** ) for each of your test policies, and then select **Delete**. Select **Yes** to confirm.

## <a name="next-steps"></a>Sonraki adımlar
In this tutorial, you created app protection policies to limit what the user can do with the Outlook app, and you created Conditional Access policies to require the Outlook app and require MFA for Modern Authentication clients. To learn about using Intune with Conditional Access to protect other apps and services, see [Set up Conditional Access](conditional-access.md).
