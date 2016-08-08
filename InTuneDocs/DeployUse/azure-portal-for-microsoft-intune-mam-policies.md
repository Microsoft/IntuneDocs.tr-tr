---
title: "MAM ilkeleri için Azure portalı | Microsoft Intune"
description: "Azure portalını kullanarak mobil uygulama yönetimi ilkeleri oluşturun. Burada oluşturduğunuz ilkeler, Intune’da kaydı olan veya olmayan cihazlara uygulanabilir."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 22aea1a9a2ff55ae7a8a115fae31b1358305a4a5


---

# Microsoft Intune MAM ilkeleri için Azure portalı
## Azure portalına erişim
**Azure portalı**, mobil uygulama yönetimi ilkeleri oluşturmanıza ve bunları yönetmenize olanak tanır.

Azure portalı, aşağıdakiler için MAM ilkeleri oluşturmayı destekler:
- **Intune’a kaydedilmiş ve Intune tarafından yönetilen** cihazlarda çalıştırılan uygulamalar.
- Herhangi bir MDM çözümüne **kaydedilmemiş** cihazlarda çalıştırılan uygulamalar.
- **Üçüncü taraf bir MDM çözümüne kaydedilmiş** cihazlarda çalıştırılan uygulamalar.

>[!IMPORTANT]

> Şu anda, cihazlarınızı yönetmek için [Intune yönetici konsolunu](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanıyorsanız, Intune yönetici konsolu kullanılarak Intune’a kaydedilen cihazlar için olan uygulamaları destekleyen bir MAM ilkesi oluşturabilirsiniz.

> Intune yönetici konsolunda tüm MAM ilkesi ayarlarını göremeyebilirsiniz. Azure portalı, MAM ilkeleri oluşturmak için yeni yönetim konsoludur. Hem Intune yönetim konsolunda hem de Azure portalında MAM ilkeleri oluşturursanız, uygulamalara Azure portalındaki ilke uygulanır ve kullanıcılara bu ilke dağıtılır.

## Azure portalında oturum açma ve başlangıç sayfanızı özelleştirme

1.  [Azure portalı](https://portal.azure.com)’na gidin ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kimlik bilgilerinizle oturum açın.

    ![Azure portalı oturum açma sayfasının ekran görüntüsü](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Oturumunuz başarıyla açıldıktan sonra **Pano**’yu görürsünüz. **Pano** sayfası özelleştirilebilir.

    ![Azure portalı panosunun ekran görüntüsü](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  **Gözat** menüsünde **Intune**’u bulun.![Intune’un vurgulandığı Gözat menüsünün ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  **Intune > Intune mobil uygulama yönetimi > Ayarlar**‘ı seçin.

    ![Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    >  **Başlat** sayfasına bir dikey pencere sabitlemek için dikey penceredeki **sabitle** seçeneğini kullanabilirsiniz.   **Intune mobil uygulama yönetimi dikey penceresi**üzerindeki sabitleme simgesine tıklayarak dikey pencereyi **Başlat** sayfasına sabitleyin.

    ![Raptiye simgesinin vurgulandığı Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Sabitlenmiş Intune kutucuğuyla panonun ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Sonraki adımlar
[Mobil uygulama yönetimi ilkelerini yapılandırmak için hazırlanma](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


