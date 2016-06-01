---
# required metadata

title: Mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama
Bu konuda, Azure portalında mobil uygulama yönetimi ilkeleri (MAM) oluşturabilmek için yapmanız gerekenler açıklanmaktadır
Şu anda, cihazlarınızı yönetmek için **Intune yönetici konsolu** kullanıyorsanız, [Intune yönetici konsolu](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanılarak Intune’a kaydedilen cihazlar için uygulamaları destekleyen bir MAM ilkesi oluşturabilirsiniz
>[!IMPORTANT]
> Intune yönetici konsolunda tüm MAM ilkesi ayarlarını göremeyebilirsiniz. Azure portalı, MAM ilkeleri oluşturmak için yeni yönetim konsoludur.

##  Desteklenen platformlar
- iOS 8.1 veya üzeri

- Android 4 veya üzeri

##  Desteklenen uygulamalar
Desteklenen uygulamaların tam listesi görmek için, Microsoft Intune uygulama iş ortakları sayfasında [Microsoft Intune mobil uygulama galerisine](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) gidin.
Desteklenen senaryoları, platformları ve uygulamanın çoklu kimliği destekleyip desteklemediğini görmek için uygulamaya tıklayın.

MAM ilkelerini yapılandırmadan **önce** aşağıdakilere ihtiyacınız olacak:

-   **Microsoft Intune için bir abonelik**.    Son kullanıcıların uygulamaları MAM ilkesiyle edinebilmesi için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisanslarına sahip olması gerekir.

-   Cihazlarınızı yönetmek için yalnızca Intune veya Intune ile tümleşik Configuration Manager kullanmanıza bağlı olarak, **mobil cihaz yönetimi yetkilisi** **Intune** veya **Configuration manager** olarak ayarlanmalıdır. O365 yerleşik mobil cihaz yönetimi kullanıyorsanız bir Intune aboneliği satın almanız ve [mobil cihaz yönetimi yetkilisini Intune olarak ayarlamanız](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) gerekir
-   Aşağıdakiler için gerekli bir **Office 365 (O365)** aboneliği:
  - Çoklu kimliği desteği olan uygulamalara MAM ilkeleri uygulamak için.
  - SharePoint Online ve Exchange Online iş hesaplarını oluşturmak için. Exchange Şirket İçi ve SharePoint şirket içi desteklenmez.


- Kullanıcılar oluşturmak için **Azure Active Directory (Azure AD)**. Son kullanıcı uygulamayı başlatıp iş kimlik bilgilerini girdiğinde Azure AD, kullanıcının kimliğini doğrular.

    > [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsolunu kullanarak kullanıcıları ayarlıyorsanız, MAM ilke yapılandırmasının ileride Azure portalına taşınacağını ve bu portalı kullanmak için Office 365 portalı aracılığıyla Azure AD kullanıcı grupları ayarlamanız gerektiğini unutmayın.


## Kullanıcılar oluşturma ve Microsoft Intune lisansları atama

1. Intune aboneliğine ihtiyacınız vardır: Şu anda cihazlarınızı yönetmek için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanıyorsanız [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğiniz zaten var demektir.  Ayrıca, bir EMS lisansı satın aldıysanız da [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğiniz vardır. MAM özelliklerini kullanıma almak için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uygulamasını deniyorsanız [buradan](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/)bir deneme hesabı alabilirsiniz

    [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğinizin olup olmadığını denetlemek için Faturalama sayfasına gidin.  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] seçeneğini abonelikler altında **Etkin** olarak görmeniz gerekir.

2.  Yönetici kimlik bilgilerinizle [Office portalında](http://portal.office.com) oturum açın.

3.  **Etkin Kullanıcılar** sayfasına giderek kullanıcı ekleyin ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansları atayın.

    ![Office Portalı kullanıcı ekleme sayfası](../media/AppManagement/OfficePortal_AddUsers.png)

4.  Bir kullanıcıya Office portalı, Azure AD portalı ve Azure önizleme portalı erişimi vermek için kullanıcıya **Genel yönetici rolü** atayın.

    ![Etkin Kullanıcılar sayfasını gösteren Office portalı ekran görüntüsü ](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  MAM ilkeleri Azure Active Directory'deki kullanıcı gruplarına dağıtılır. MAM ilkeleriniz için kullanmak istediğiniz kullanıcı grupları oluşturmak için, **Office portalı**’ndaki **Gruplar** sayfasına gidin ve **+** simgesine tıklayarak yeni bir güvenlik grubu oluşturun.  Bir ad ve açıklama yazıp **Oluştur**’a tıklayın. Grup oluşturulduğunda, yeni oluşturulan grupta **Üyeleri düzenle** ‘ye tıklayarak kullanıcıyı gruba ekleyebilirsiniz. Azure Active Directory’de güvenlik grubu oluşturulur.

    ![Kullanıcı rollerini düzenleme sayfasında Genel yönetici rolü seçimi gösterilen sayfanın ekran görüntüsü](../media/AppManagement/OfficePortal_CreateGroups.png)

Aşağıdaki tabloda yönetici kullanıcılara atayabileceğiniz rol ve izinler listelenmektedir.

|||
|--|----|
|**Rol**|**İzinler**|
|Genel yönetici (O365 portalı)|O365 portalına ve Azure AD portalına erişim<br /><br />Azure portalına erişim (hem rol yönetimi hem de mobil uygulama yönetimi görevlerini gerçekleştirebilir).|
|Sahip rolü (Azure portalı)|Azure portalına erişim (hem rol yönetimi hem de mobil uygulama yönetimi görevlerini gerçekleştirebilir).|
|Katkıda bulunan rolü (Azure portalı)|Azure portalına erişim (yalnızca mobil uygulama yönetimi görevlerini gerçekleştirebilir).|

## Bir kullanıcıya katkıda bulunan rolü atama

**Genel yöneticiler** Azure portalına erişebilir.  Diğer yönetici kullanıcıların ilkeleri yapılandırabilmesini ve diğer mobil uygulama yönetim görevlerini yapabilmesini istiyorsanız **katkıda bulunan rolü** ’nü kullanıcıya aşağıda açıklandığı gibi atayabilirsiniz:


1.  **Ayarlar** dikey penceresindeki **Kaynak yönetimi** bölümünde **Kullanıcılar**’a tıklayın

    ![Azure portalındaki Kullanıcılar dikey ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.   **Erişim ekle** dikey penceresini açmak için **Ekle** ‘ye tıklayın.

3.  **Bir rol seçin**’e, ardından **Katkıda bulunan rolü**’ne tıklayın.

    ![Azure portalındaki Bir rol seçin dikey ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Rolü seçtikten sonra **Kullanıcı Ekle**’ye tıklayın ve kullanıcıyı, kullanıcı adına veya e-posta adresine göre arayın. Bu listede, Azure AD'de daha önce Office portalını kullanarak oluşturduğunuz ilk 1000 kullanıcıyı görürsünüz. Rolü kaydetmek ve kullanıcıya atamak için **Erişim ekle** dikey penceresinde **Tamam** ’a tıklayın.

    ![Azure portalındaki Kullanıcı ekle dikey ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisansı atanmamış bir kullanıcı seçerseniz, kullanıcı bu portala erişemez.

## Sonraki adımlar
[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO2-->


