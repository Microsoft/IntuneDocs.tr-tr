---
title: Microsoft Intune'u ayarlama
description: Intune aboneliğinizi kullanmaya başlamak için gereksinimler ve önkoşullar
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a45160fc0e728b4c53590455a2bd0b5d904ddb1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504905"
---
# <a name="set-up-intune"></a>Intune’u ayarlama

Bu kurulum adımları, Intune kullanarak mobil cihaz yönetimini (MDM) etkinleştirmenize yardımcı olur. Kullanıcılara şirket kaynakları erişimi vermeniz veya cihazlarda ayarları yönetmeniz için önce bu cihazların yönetilmesi gerekir.

Intune aboneliği ayarlama ve MDM yetkilisi ayarlama gibi bazı adımlar, çoğu senaryoda gereklidir. Özel bir etki alanı yapılandırma veya uygulama ekleme gibi diğer adımlar ise şirketinizin ihtiyaçlarına göre isteğe bağlıdır.

Şu anda bilgisayarları ve sunucuları yönetmek için Microsoft System Center Configuration Manager kullanıyorsanız, [ortak yönetim ile buluta iliştirebilirsiniz Configuration Manager](https://docs.microsoft.com/sccm/comanage/overview).

>[!TIP]
>Uygun bir planda Intune için en az 150 lisans satın alırsanız *FastTrack Center Avantajını* kullanabilirsiniz. Bu hizmet ile Microsoft uzmanları, ortamınızı Intune’a hazırlamak için sizinle birlikte çalışır. Bkz. [Enterprise Mobility + Security (EMS) için FastTrack Center Avantajı](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).



| Adımlar |                                                                                                                       Durum                                                                                                                       |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   1   |                                        [Desteklenen yapılandırmalar](supported-devices-browsers.md) - Başlamadan önce bilmeniz gerekenler. Bunlar arasında desteklenen yapılandırmalar ve ağ gereksinimleri vardır.                                         |
|   2   |                                                                 [Intune’da oturum açma](account-sign-up.md) - Deneme aboneliğinizde oturum açın veya yeni bir Intune aboneliği oluşturun.                                                                  |
|   3   |                [Etki alanı adı yapılandırma](custom-domain-name-configure.md) - Şirketinizin etki alanı adını Intune’a bağlamak için DNS kaydı ayarlayın. Böylece, Intune’a bağlanırken ve kaynakları kullanırken kullanıcılara tanıdık bir etki alanı sağlarsınız.                |
|   4   |                                   [Kullanıcı ekleme](users-add.md) - Kullanıcıları el ile ekleyin veya Intune ile eşitlemek için Active Directory'ye bağlanın. Cihazlarınız, “kullanıcısız” bilgi noktası cihazları gibi cihazlar değilse gereklidir.                                    |
|   5   |                                            [Lisans atama](../licenses-assign.md) - Kullanıcıların Intune’u kullanmasına izin verin. Tüm kullanıcılar veya kullanıcısız cihazların Intune’a erişmesi için bir Intune lisansı gerekir.                                             |
|   6   |                                               [Grup ekleme](../groups-add.md) - Yönetim görevlerini basitleştirmek için kullanıcı ve cihaz gruplarını kullanın. Gruplar; uygulama, ayar ve diğer kaynakları atamak için kullanılır.                                                |
|   7   |                                                                        [Uygulama ekleme](../apps/apps-add.md) - Uygulamalar otomatik olarak gruplara atanabilir veya isteğe bağlı olarak yüklenebilir.                                                                         |
|   8   | [Cihaz yapılandırma](../configuration/device-profiles.md) - Cihaz ayarlarını yöneten profiller ayarlayın. Cihaz profilleri; e-posta, VPN, Wi-Fi ve cihaz özellikleri için ayarları önceden yapılandırabilir. Ayrıca cihazları ve verileri korumak için cihazları kısıtlayabilir. |
|   9   |       [Şirket Portalı’nı Özelleştirme](../apps/company-portal-app.md) - Kullanıcıların cihaz kaydetmek ve uygulama yüklemek için kullandığı Intune Şirket Portalı’nı özelleştirin. Bu ayarlar hem Şirket Portalı uygulamasında hem de Intune Şirket Portalı web sitesinde bulunur.       |
|  10   |                                [Cihaz kaydını etkinleştirme](mdm-authority-set.md) - MDM yetkilisini ayarlayarak ve belirli platformları etkinleştirerek iOS, Windows, Android ve Mac cihazların Intune yönetimini etkinleştirin.                                 |
|  11   |                                                        [Uygulama ilkeleri yapılandırma](../apps/app-protection-policy.md) - Microsoft Intune’da uygulama koruma ilkelerine bağlı olarak belirli ayarları sağlayın.                                                         |

