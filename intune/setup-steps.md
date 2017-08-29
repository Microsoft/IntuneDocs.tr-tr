---
title: "Intune’u ayarlama"
description: "Intune aboneliğinizi kullanmaya başlamak için gereksinimler ve önkoşullar"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fba27041fb55cfbef1cbba39e3679ce6884cd5f0
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2017
---
# <a name="set-up-intune"></a>Intune’u ayarlama

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Bu kurulum adımları, mobil cihaz yönetimini (MDM) etkinleştirmenize yardımcı olur. Kullanıcılara şirket kaynakları erişimi vermeniz veya cihazlarda ayarları yönetmeniz için önce bu cihazların yönetilmesi gerekir.

Intune aboneliği ayarlama ve MDM yetkilisi ayarlama gibi bazı adımlar, çoğu senaryoda gereklidir. Özel bir etki alanı yapılandırma veya uygulama ekleme gibi diğer adımlar ise şirketinizin ihtiyaçlarına göre isteğe bağlıdır.

Şu anda bilgisayar ve sunucuları yönetmek için Microsoft System Center Configuration Manager'ı kullanıyorsanız, [Configuration Manager'ın kapsamını mobil cihazları da yönetecek şekilde genişletebilirsiniz](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).

>[!TIP]
>Uygun bir planda Intune için en az 150 lisans satın alırsanız *FastTrack Center Avantajını* kullanabilirsiniz. Bu hizmet ile Microsoft uzmanları, ortamınızı Intune’a hazırlamak için sizinle birlikte çalışır. Bkz. [Enterprise Mobility + Security (EMS) için FastTrack Center Avantajı](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).



| Adımlar | Durum  |
| ------------- |-------------|
| 1  | [Önkoşullar](supported-devices-browsers.md) - Başlamadan önce bilmeniz gerekenler. Bunlar arasında desteklenen yapılandırmalar ve ağ gereksinimleri vardır.|
| 2 |  [Intune’da oturum açma](account-sign-up.md) - Deneme aboneliğinizde oturum açın veya yeni bir Intune aboneliği oluşturun. |  
| 3 | [Etki alanı adı yapılandırma](custom-domain-name-configure.md) - Şirketinizin etki alanı adını Intune’a bağlamak için DNS kaydı ayarlayın. Böylece, Intune’a bağlanırken ve kaynakları kullanırken kullanıcılara tanıdık bir etki alanı sağlarsınız.  |
| 4 | [Kullanıcı ekleme](users-add.md) - Kullanıcıları el ile ekleyin veya Intune ile eşitlemek için Active Directory'ye bağlanın. Cihazlarınız, “kullanıcısız” bilgi noktası cihazları gibi cihazlar değilse gereklidir. |
| 5 | [Lisans atama](licenses-assign.md) - Kullanıcıların Intune’u kullanmasına izin verin. Tüm kullanıcılar veya kullanıcısız cihazların Intune’a erişmesi için bir Intune lisansı gerekir.|
| 6 |  [Grup ekleme](groups-add.md) - Yönetim görevlerini basitleştirmek için kullanıcı ve cihaz gruplarını kullanın. Gruplar; uygulama, ayar ve diğer kaynakları atamak için kullanılır. |
| 7 | [Uygulama ekleme](apps-add.md) - Uygulamalar otomatik olarak gruplara atanabilir veya isteğe bağlı olarak yüklenebilir. |
| 8 | [Cihaz yapılandırma](device-profiles.md) - Cihaz ayarlarını yöneten profiller ayarlayın. Cihaz profilleri; e-posta, VPN, Wi-Fi ve cihaz özellikleri için ayarları önceden yapılandırabilir. Ayrıca cihazları ve verileri korumak için cihazları kısıtlayabilir.  |
| 9 | [Şirket Portalı’nı Özelleştirme](company-portal-app.md) - Kullanıcıların cihaz kaydetmek ve uygulama yüklemek için kullandığı Intune Şirket Portalı’nı özelleştirin. Bu ayarlar hem Şirket Portalı uygulamasında hem de Intune Şirket Portalı web sitesinde bulunur. |
| 10 | [Cihaz kaydını etkinleştirme](mdm-authority-set.md) - MDM yetkilisini ayarlayarak ve belirli platformları etkinleştirerek iOS, Windows, Android ve Mac cihazların Intune yönetimini etkinleştirin. |
