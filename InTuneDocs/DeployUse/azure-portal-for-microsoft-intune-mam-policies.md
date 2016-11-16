---
title: "MAM ilkeleri için Azure portalı | Microsoft Intune"
description: "Azure portalını kullanarak mobil uygulama yönetimi ilkeleri oluşturun. Burada oluşturduğunuz ilkeler, Intune’da kaydı olan veya olmayan cihazlara uygulanabilir."
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: 9eb7e79bee2bc36dffab97ffdb6f665218bc739e
ms.openlocfilehash: 0acef421f179ebf922ec8af71ba336e3e5f96bd2


---

# Microsoft Intune MAM ilkeleri için Azure portalı
## Azure portalını kullanma
Azure portalı, mobil uygulama yönetimi (MAM) ilkeleri oluşturmanıza ve bunları yönetmenize olanak tanır.

Azure portalı, aşağıdakiler için MAM ilkeleri oluşturmayı destekler:
- **Intune’a kaydedilmiş ve Intune’da yönetilen** cihazlarda çalıştırılan uygulamalar.
- Herhangi bir MDM çözümüne **kaydedilmemiş** cihazlarda çalıştırılan uygulamalar.
- **Üçüncü taraf bir MDM çözümüne kaydedilmiş** cihazlarda çalıştırılan uygulamalar.

>[!IMPORTANT]

> Cihazlarınızı yönetmek için Intune yönetici konsolunu kullanıyorsanız, Intune’da kayıtlı cihazlara yönelik uygulamaları destekleyen bir MAM ilkesini [Intune yönetici konsolu](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) aracılığıyla oluşturabilirsiniz.

> Intune yönetici konsolunda tüm MAM ilkesi ayarlarını göremeyebilirsiniz. Azure portalı, MAM ilkeleri oluşturmak için yeni yönetim konsoludur. Hem Intune yönetici konsolunda hem de Azure portalında MAM ilkeleri oluşturursanız, uygulamalara Azure portalındaki ilke uygulanır ve kullanıcılara bu ilke dağıtılır.

## Azure portalında oturum açma ve başlangıç sayfanızı özelleştirme

1.  [Azure portalına](https://portal.azure.com) gidin ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kimlik bilgilerinizle oturum açın.

    ![Azure portalı oturum açma sayfasının ekran görüntüsü](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Oturumunuz açıldıktan sonra **Pano** sayfasını görürsünüz. **Pano** sayfası özelleştirilebilir.

    ![Azure portalı panosunun ekran görüntüsü](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  **Gözat** menüsünde **Intune**’u bulun.![Intune’un vurgulandığı Gözat menüsünün ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  **Intune** > **Intune mobil uygulama yönetimi** > **Ayarlar**‘ı seçin.

    ![Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Bir dikey pencereyi **Başlat** sayfasına sabitlemek için **Intune mobil uygulama yönetimi** dikey penceresindeki sabitleme simgesini seçin.

    ![Raptiye simgesinin vurgulandığı Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Sabitlenmiş Intune kutucuğuyla panonun ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Sonraki adımlar
[Mobil uygulama yönetimi ilkelerini yapılandırmak için hazırlama](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


