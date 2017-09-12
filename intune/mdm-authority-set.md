---
title: "Mobil cihaz yönetimi yetkilisini ayarlayın"
titlesuffix: Azure portal
description: "Intune'da mobil cihaz yönetimi yetkilisini ayarlamayı öğrenin. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e042ccbc085b2cf511d3cd21f2da5e23299264a9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Mobil cihaz yönetimi yetkilisini ayarlayın

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mobil cihaz yönetimi (MDM) yetkili ayarı, cihazlarınızı yönetme şeklinizi belirler. Kullanıcıların yönetilmek üzere cihaz kaydedebilmeleri için, BT yöneticisi olarak bir MDM yetkilisi ayarlamanız gerekir.

Olası yapılandırmalar şunlardır:

- **Intune Tek Başına** - Azure Portal’ı kullanarak yapılandırdığınız yalnızca bulut yönetimi. Intune’un sunduğu özelliklerin tamamını içerir. [MDM yetkilisini Intune konsolundan ayarlama](#set-mdm-authority-to-intune).

- **Intune Karma** - Intune bulut çözümünün System Center Configuration Manager ile tümleştirmesi. Configuration Manager konsolunu kullanarak Intune’u siz yapılandırırsınız. [MDM yetkilisini Yapılandırma Yöneticisi’nden ayarlama](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Office 365 için Mobil Cihaz Yönetimi** - Office 365’in Intune bulut çözümüyle tümleştirmesi. Office 365 Yönetim Merkezi’nden Intune’u siz yapılandırırsınız. Intune Tek Başına ile sağlanan özelliklerin bir alt kümesini içerir. MDM yetkilisini Office 365 Yönetim Merkezi’nden ayarlama.

>[!IMPORTANT]    
Configuration Manager'ın 1610 veya sonraki bir sürümü ve Microsoft Intune'un 1705 sürümünde, MDM yetkilisini, Microsoft Destek ile iletişim kurmaya ve mevcut yönetilen cihazlarınızın kaydını silip tekrar kaydetmeye gerek kalmadan değiştirebilirsiniz. Ayrıntılar için bkz. [Yanlış MDM yetkilisi ayarı seçilirse yapılacaklar](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>MDM yetkilisini Intune olarak ayarlama

1. [Azure portalında](https://portal.azure.com) **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
2. **Mobil Cihaz Yönetim Yetkilisi** ayarını açmak için turuncu başlığı seçin.
3. **Mobil Cihaz Yönetimi Yetkilisi** altında, aşağıdakilerden birini MDM yetkiliniz olarak belirtin:
  - **Intune MDM Yetkilisi**
  - **System Center Configuration Manager MDM Yetkilisi**
  - **Yok.**

  ![Intune tarafından ayarlı mobil cihaz yönetim yetkilisi ekranının ekran görüntüsü](media/set-mdm-auth.png)

  MDM yetkilinizi başarıyla Intune olarak ayarladığınızı bildiren bir ileti görüntülenir.

## <a name="enable-device-enrollment"></a>Cihaz kaydını etkinleştirme

MDM yetkiliniz olarak Intune’u ayarladığınızda kullanıcılar; kişisel cihazlarını kaydedebilir ve Şirket Portalı (iOS ve Android) uygulamasını yükleyerek, iş kimlik bilgilerini ekleyerek (Windows) veya Şirket Portalı web sitesine erişerek (iOS, Android, macOS) e-posta gibi kaynaklara erişim kazanabilir.

Kaydı etkinleştirmek veya kolaylaştırmak için farklı platformlarda aşağıdaki gereksinimler vardır:
- **iOS** - (gerekli) [Bir Apple MDM anında iletme sertifikası alma](apple-mdm-push-certificate-get.md) ve [Şirkete ait iOS cihazlar için kaydı etkinleştirme](ios-enroll.md) (isteğe bağlı).
- **Android** - (isteğe bağlı) [Android iş profillerini etkinleştirme](android-enroll.md)
- **Windows** - (isteğe bağlı) [Otomatik kaydı](windows-enroll.md) veya [toplu kaydı](windows-bulk-enroll.md) etkinleştirme
- **macOS** - Gereksinim yok


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>MDM sertifikası süre sonunda mobil cihazı temizleme

Mobil cihazlar Intune hizmetiyle iletişim kurduğunda MDM sertifikası otomatik olarak yenilenir. Mobil cihazlar temizlendiğinde veya belirli bir süre boyunca Intune hizmetiyle iletişim kuramadığında, MDM sertifikası yenilenmez. MDM sertifikasının süre sonundan 180 gün sonra, cihaz Azure Portal’dan kaldırılır.
