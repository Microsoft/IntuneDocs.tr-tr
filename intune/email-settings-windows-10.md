---
title: "Windows 10 çalıştıran cihazlar için Microsoft Intune e-posta ayarları"
titleSuffix: 
description: "Windows 10 çalıştıran cihazlarda e-posta ayarlarını yapılandırmak için kullanabileceğiniz Microsoft Intune ayarları hakkında bilgi edinin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b02579895123995f9b4205d64e9bf67ce04de746
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-windows-10"></a>Windows 10 çalıştıran cihazlar için Microsoft Intune'da e-posta profili ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu makalede, Windows 10 çalıştıran cihazlarınız için yapılandırabileceğiniz e-posta profili ayarları gösterilmektedir.


- **E-posta sunucusu** - Exchange sunucunuzun konak adı.
- **Hesap adı** - E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.
- **AAD’den kullanıcı adı özniteliği** - Bu öznitelik, bu e-posta profili için kullanıcı adını oluşturmak üzere kullanılan Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** için **user1@contoso.com** gibi bir değer seçin veya **Kullanıcı Asıl Adı**’nı (**kullanıcı1** veya **user1@contoso.com** gibi) belirtin.
- **AAD’den e-posta adresi özniteliği** - E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**’ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**’nı seçin.


## <a name="security-settings"></a>Güvenlik ayarları

- **SSL** - E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.



## <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı** - Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postayı eşitleyin.
- **Eşitleme zamanlaması** - Cihazların Exchange sunucusundan veri eşitleyeceği zamanlamayı seçin. Ayrıca, verileri ulaşır ulaşmaz eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneğini belirleyebilirsiniz.

## <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**Aşağıdaki türler arasından, cihazlara eşitlemek istediğinizi içerik türlerini seçin:
    - **Kişiler**
    - **Takvim**
    - **Görevler**
