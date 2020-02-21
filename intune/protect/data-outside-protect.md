---
title: Şirket verilerine yetkisiz erişimi engelleme
titleSuffix: Microsoft Intune
description: Microsoft Intune kullanarak şirket ağı dışında paylaşılan şirket verilerine yetkisiz erişimi engelleyin.
keywords: Office 365 O365 Azure Information Protection verileri şirket verilerini ağ dışında koruma
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6a88573a-aa60-455c-858c-74562798246b
ms.reviewer: pchacon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7520e5883a89d6cd040be670aedc8436cc40fadb
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515195"
---
# <a name="prevent-unauthorized-access-to-company-data-using-microsoft-intune"></a>Microsoft Intune kullanarak şirket verilerine yetkisiz erişimi engelleme

Office 365 belgelerini ve e-postaları, verilere yalnızca yetkili kullanıcıların erişebilmesi için sınıflandırabilir, etiketleyebilir ve bunları koruyabilirsiniz. Ayarlar, BT yöneticileri veya kullanıcılar kurallar ve koşullar koyduktan sonra otomatik olarak yönetilir. Alternatif olarak BT ekibi, kullanıcıların izlemesi için önerilen ayarlar sağlayabilir. Ayrıca yöneticiler ve kullanıcılar daha önceden başkalarıyla paylaşılan verilere erişimi başka bir yetkilinin yardımı gerekmeden iptal edebilir. Bu işlemlerin sonucu, şirket ağının dışına çıktıklarında bile korumalı verileri kimin açtığını veya güncelleştirdiğini denetlemektir. 

## <a name="before-you-begin"></a>Başlamadan önce

Aşağıdaki koşulları yerine getirdiğinizde aşağıdaki eylem planı kullanılabilir:
* Şirketiniz buluta güvenli bir şekilde geçiş yapmaya hazırdır.
* Şirketiniz Office 365 Exchange Online, SharePoint Online, OneDrive İş veya Yammer kullanmaktadır.
* Şirketinizin Microsoft 365, Enterprise Mobility + Security (EMS) veya Azure Information Protection lisansları vardır.
* Şirketiniz Windows 7 Service Pack 1 veya üzerini çalıştıran cihazlarla çalışıyordur.
* Şirketiniz Office 365 ProPlus ile 2016 ya da 2013 uygulamaları, Office Professional Plus 2016, Office Professional Plus 2013 Service Pack 1 veya Office Professional Plus 2010 kullanıyordur.

## <a name="action-plan"></a>Eylem planı

[Azure Information Protection için hızlı başlangıç öğreticisi](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)'ni tamamlayın.  

## <a name="what-to-tell-employees-and-students"></a>Çalışanlara ve öğrencilere söylenecekler

[Hassas bilgiler içeren belge ve e-postaları nasıl ve ne zaman koruyacağınızın](https://docs.microsoft.com/information-protection/deploy-use/help-users) ayrıntılarını paylaşabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Sonraki adımların parçası olarak, şirket verilerinizin güvenliğini arttırmak için aşağıdaki gibi diğer yollar hakkında bilgi edinebilirsiniz: 

* [İOS/ıpados ve Android cihazlarda Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq)kullanmayı öğrenin.
* Windows Phone ve Mac bilgisayarlarında [Microsoft Rights Management Özellikli Paylaşım Uygulaması](https://technet.microsoft.com/dn451248) hakkında daha fazla bilgi edinin.
