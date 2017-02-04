---
title: "MAM ilkeleri için Azure portalı | Microsoft Docs"
description: "Azure portalını kullanarak mobil uygulama yönetimi ilkeleri oluşturun. Burada oluşturduğunuz ilkeler, Intune’da kaydı olan veya olmayan cihazlara uygulanabilir."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: fa8d839da1cf0b2d207edc0b28de8a714ba0df02


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Microsoft Intune MAM ilkeleri için Azure portalı

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure portalı, mobil uygulama yönetimi (MAM) ilkelerini aşağıdakiler için oluşturmak ve yönetmek için kullanılır:

- **Intune’a kaydedilmiş ve Intune’da yönetilen** cihazlarda çalıştırılan uygulamalar.

- Herhangi bir MDM çözümüne **kaydedilmemiş** cihazlarda çalıştırılan uygulamalar.
- **Üçüncü taraf bir MDM çözümüne kaydedilmiş** cihazlarda çalıştırılan uygulamalar.

>[!IMPORTANT]
> Azure portalı MAM ilkeleri oluşturmak için yeni yönetim konsoludur ancak MDM senaryoları için [Intune yönetim konsolunu](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanarak Intune’a kaydedilen cihazlara yönelik uygulamaları destekleyen bir MAM ilkesi de oluşturabilirsiniz.

> Intune yönetim konsolunda kullanılabilir tüm MAM ilkesi ayarlarını göremeyebilirsiniz. Ayrıca, hem Intune yönetim konsolu hem de Azure portalında MAM ilkelerini oluşturursanız Azure portalında oluşturulan ilkeler, Intune yönetim konsolunda oluşturulan ilkeleri geçersiz kılar. Bu senaryoda Azure portalı MAM ilkeleri, uygulamalarda geçerli kılınır ve kullanıcılara dağıtılır.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Azure portalında oturum açma ve başlangıç sayfanızı özelleştirme

1.  [Azure portalına](https://portal.azure.com) gidin ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kimlik bilgilerinizle oturum açın.

    ![Azure portalı oturum açma sayfasının ekran görüntüsü](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Oturumunuz başarıyla açıldıktan sonra **Pano**'yu görürsünüz. **Pano** sayfası özelleştirilebilir.

    ![Azure portalı panosunun ekran görüntüsü](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  **Gözat** menüsünde **Intune**‘u bulun.

    ![Intune'un vurgulandığı Gözat menüsünün ekran görüntüsü](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  **Intune** > **Intune mobil uygulama yönetimi** > **Ayarlar**‘ı seçin.

    ![Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (İsteğe bağlı): **Başlat** sayfasına bir dikey pencere sabitlemek için dikey penceredeki **sabitle** seçeneğini kullanabilirsiniz. **Intune mobil uygulama yönetimi dikey penceresi** üzerindeki sabitleme simgesine tıklayarak dikey pencereyi **Başlat** sayfasına sabitleyin.

    ![Raptiye simgesinin vurgulandığı Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Sabitlenmiş Intune kutucuğuyla panonun ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Sonraki adımlar
[Mobil uygulama yönetimi ilkelerini yapılandırmak için hazırlama](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


