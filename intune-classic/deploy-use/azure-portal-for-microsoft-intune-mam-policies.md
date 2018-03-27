---
title: MAM ilkeleri için Azure portalı
description: Azure portalını kullanarak mobil uygulama yönetimi ilkeleri oluşturun. Burada oluşturduğunuz ilkeler, Intune’da kaydı olan veya olmayan cihazlara uygulanabilir.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 10/22/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ae0acf53a4987dac21e576826477d32da1f56155
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="azure-portal-for-intune-app-protection-policies"></a>Intune uygulama koruma ilkeleri için Azure portalı

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure portalı, aşağıdakilere yönelik uygulama koruma ilkeleri oluşturmak ve yönetmek için kullanılır:

- **Intune’a kaydedilmiş ve Intune’da yönetilen** cihazlarda çalıştırılan uygulamalar.

- Herhangi bir MDM çözümüne **kaydedilmemiş** cihazlarda çalıştırılan uygulamalar.
- **Üçüncü taraf bir MDM çözümüne kaydedilmiş** cihazlarda çalıştırılan uygulamalar.

>[!IMPORTANT]
> Azure portalı, uygulama koruma ilkeleri oluşturmaya yönelik yeni yönetim konsoludur, ancak MDM senaryoları için [Intune yönetim konsolunu](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanarak Intune’a kaydedilen cihazlara yönelik uygulamaları destekleyen bir uygulama koruma ilkesi de oluşturabilirsiniz.

> Intune yönetim konsolunda kullanılabilir tüm uygulama koruma ilkesi ayarlarını göremeyebilirsiniz. Ayrıca, hem Intune yönetim konsolu hem de Azure portalında uygulama koruma ilkeleri oluşturursanız Azure portalında oluşturulan ilkeler, Intune yönetim konsolunda oluşturulan ilkeleri geçersiz kılar. Bu senaryoda Azure portalı uygulama koruma ilkeleri, uygulamalar için geçerli olur ve kullanıcılara dağıtılır.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Azure portalında oturum açma ve başlangıç sayfanızı özelleştirme

1.  [Azure Portal](https://portal.azure.com)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

    ![Azure portalı oturum açma sayfasının ekran görüntüsü](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Oturumunuz başarıyla açıldıktan sonra **Pano**'yu görürsünüz. **Pano** sayfası özelleştirilebilir.

    ![Azure portalı panosunun ekran görüntüsü](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

    ![Intune'un vurgulandığı Gözat menüsünün ekran görüntüsü](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  **Intune Uygulama Koruma** > **Intune mobil uygulama yönetimi** > **Tüm Ayarlar**’ı seçin.

    ![Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (İsteğe bağlı): **Başlat** sayfasına bir dikey pencere sabitlemek için dikey penceredeki **sabitle** seçeneğini kullanabilirsiniz. **Intune mobil uygulama yönetimi dikey penceresi** üzerindeki sabitleme simgesine tıklayarak dikey pencereyi **Başlat** sayfasına sabitleyin.

    ![Raptiye simgesinin vurgulandığı Intune mobil uygulama yönetimi dikey penceresinin ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Sabitlenmiş Intune kutucuğuyla panonun ekran görüntüsü](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Sonraki adımlar
[Uygulama koruma ilkelerini yapılandırmaya hazırlanın](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
