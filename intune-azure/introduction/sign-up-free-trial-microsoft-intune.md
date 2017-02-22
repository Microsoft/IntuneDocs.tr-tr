---
title: "30 günlük ücretsiz denemeye kaydolma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Azure’da Intune’a kaydolmayı öğrenin."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cd98141b4b377f0013607f2a2ebb93a93cd7f0ce
ms.openlocfilehash: ce69e7efbee286839a1bf3440db692bd237b0e06


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Azure Portal önizlemesi için Microsoft Intune ücretsiz denemesine kaydolma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bu makale, Azure Portal önizlemesinde tek başına Intune ürününe kaydolma işleminde size yol gösterir. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. [Intune Kayıt](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) sayfasını ziyaret edin ve bir deneme aboneliğine kaydolmak için formu doldurun.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Kayıt sayfasının resmi](./media/1-clicking-try.png)

 > [!TIP]
> BT işlemlerinizin ve kullanıcılarınızın çoğu sizin bölgenizden başka bir bölgedeyse, **Şirketiniz nerede?** başlığı altında o yerel ayarı seçmek isteyebilirsiniz.

2. Kaydolma işleminin sonunda, yeni hesap bilgilerinizi içeren bir ileti alırsınız. <br/> ![Hesap bilgilerinin resmi](./media/2-end-of-sign-up-process.png) <br/>Bu noktada **Başlatmaya hazırsınız** bağlantısına tıklarsanız, Office 365 Yönetim Merkezi’ne gelirsiniz ve burada test ortamınıza kullanıcıları ekleyebilirsiniz. <br/><br/>Öte yandan, doğrudan Intune Azure Portal önizlemesine gitmek isterseniz, yeni bir tarayıcı penceresi açın ve adres çubuğuna **https://portal.azure.com** girin. Size verilen kimlik bilgileriyle oturum açabileceğiniz Azure oturum açma sayfasına gelirsiniz. Intune denemenizde her oturum açmak istediğinizde bu adresi kullanın. <br/> ![Azure Portal oturum açma sayfasının resmi](./media/azure-portal-signin.png)

Azure Intune önizlemesinde ilk kez oturum açtığınızda Azure panonuzda Intune’u göremeyebilirsiniz. Intune hizmetini Azure panonuza eklemek için:
1. Panonun solundaki Azure hizmetleri listesinde **Diğer hizmetler>** öğesini seçin ve arama kutusuna **Intune** yazın.
2. Listeden **Intune**’u seçin ve hizmetler listesine eklemek için yıldızı seçin.<br/> ![Hizmetler listesinden Intune’u seçme görüntüsü](./media/azure-add-intune1.png)
3. Sonra, Intune panosunu açmak için hizmetler listesinden **Intune**’u seçin.

Deneme için kaydolduğunuzda, kayıt işlemi sırasında sağladığınız e-posta adresinin hesap bilgilerini içeren bir e-posta iletisi de gönderilir. Bu e-posta, denemenizin etkin olduğunu doğrular.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Yönetici deneyimlerini düzenli tutma
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Intune Azure önizlemesi için kullanacağınız üç portal vardır:
- [Azure Portal’da Intune özelliklerini](what-is-microsoft-intune.md) gözden geçirebileceğiniz Azure’daki Intune panosu ([portal.azure.com](https://portal.azure.com)).
- Kullanıcıları eklemek ve yönetmek için Azure Active Directory’yi kullanmıyorsanız, bu işlemleri yapabileceğiniz Office 365 Yönetim merkezi ([portal.office.com](https://portal.office.com)). Ayrıca hesabınızın faturalama ve destek gibi diğer yönlerini de yönetebilirsiniz.
- Henüz Azure’a eklenmemiş olan özellikleri gözden geçirebileceğiniz klasik Intune yönetim konsolu ([manage.microsoft.com](https://manage.microsoft.com)).

Normalde, işlerinizi aşağıda gösterildiği gibi Intune panosunda yaparsınız. Burası; gruplarınızı, ilkelerinizi, cihazlarınızı ve uygulamalarınızı kurduğunuz ve yönettiğiniz sitedir.

Panodan klasik Intune yönetim konsoluna gitmek için **Klasik Intune portalını aç** kutucuğunu seçin.

Intune Azure önizlemesine dönmek için tarayıcınızın adres çubuğuna https://portal.azure.com girin ve ardından hizmetler listesinden **Intune**’u yeniden seçin.

 ![Intune panosunun görüntüsü](./media/intune-azure-dashboard.png)


Ancak kullanıcılarınızı ve hesabınızın faturalama ve destek gibi diğer yönlerini eklemek ve yönetmek için aşağıda gösterildiği gibi Office 365 Yönetim merkezini kullanırsınız.

![Office 365 Yönetim merkezinin resmi](./media/office-admin-center.png)

Office 365 Yönetim merkezinden Intune panosuna gitmek için tarayıcınızın adres çubuğuna https://portal.azure.com girin. Hizmetler listesinden **Intune**’u seçin.

Intune’dan Office 365 Yönetim merkezine geri dönmek için tarayıcınızın adres çubuğuna https://portal.office.com girin. Intune'da zaten oturum açtıysanız doğrudan Office 365 Yönetim Merkezi'ne götürülürsünüz.

## <a name="next-steps"></a>Sonraki adımlar

### <a name="intune-azure-preview"></a>Intune Azure önizlemesi
[Azure portalı önizlemede Intune](what-is-microsoft-intune.md) hakkında daha fazla bilgi edinin
### <a name="classic-intune"></a>Klasik Intune
Değerlendirme senaryosu: [Microsoft Intune'da mobil cihaz yönetimini değerlendirme](https://docs.microsoft.com/intune/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Diğer ürünlerle tümleştirme
Azure Active Directory kullanıcı hesaplarınızı Intune ile kullanma hakkında daha fazla bilgi edinin:
- [Kimlik gereksinimleri](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Dizin eşitleme gereksinimleri](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Çok faktörlü kimlik doğrulama gereksinimleri](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

[Intune'u System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) ile kullanma hakkında daha fazla bilgi edinin



<!--HONumber=Feb17_HO1-->


