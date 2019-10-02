---
title: Intune App SDK’sının yararları
titleSuffix: Microsoft Intune
description: Intune Uygulama SDK'sı hem iOS hem de Android platformu için kullanılabilir ve Microsoft Intune ile mobil uygulama yönetim özelliklerini etkinleştirir.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 580e9f51532a5606ca8955abc5bf3b3fa3a63713
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730293"
---
# <a name="microsoft-intune-app-sdk-overview"></a>Microsoft Intune Uygulama SDK’sına genel bakış
Hem iOS hem de Android için kullanılabilen Intune uygulama SDK 'Sı, uygulamanızın Intune [Uygulama koruma ilkelerini](../apps/app-protection-policy.md)desteklemesini sağlar. Uygulamanıza uygulama koruma ilkeleri uygulandığında, Intune tarafından yönetilebilir ve Intune tarafından yönetilen bir uygulama olarak tanınabilirler. SDK, uygulama geliştiricisinden gereken kod değişikliği miktarını en aza indirir. Uygulamanızın davranışını değiştirmeden SDK’nın özelliklerinin birçoğunu etkinleştirebileceğinizi göreceksiniz. Gelişmiş Son Kullanıcı ve BT Yöneticisi deneyimi için, uygulamanızın davranışını, uygulama katılımınızı gerektiren özellikleri destekleyecek şekilde özelleştirmek için SDK 'nın API 'Lerini kullanabilirsiniz.

Uygulamanızı Intune uygulama koruma ilkelerini destekleyecek şekilde etkinleştirdikten sonra, BT yöneticileri uygulama içindeki kurumsal verilerini korumak için bu ilkeleri dağıtabilir.

## <a name="app-protection-features"></a>Uygulama koruma özellikleri

SDK ile etkinleştirilebilen Intune uygulama koruma özellikleri örnekleri aşağıda verilmiştir.

### <a name="control-users-ability-to-move-corporate-files"></a>Kullanıcıların kurumsal dosyaları taşıma yeteneğini denetleme
BT yöneticileri uygulamadaki iş veya okul verilerinin nereye taşınabileceğini denetleyebilir. Örneğin, uygulamanın kurumsal verileri buluta yedeklemesini devre dışı bırakan bir ilke dağıtabilirler.

### <a name="configure-clipboard-restrictions"></a>Pano kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen uygulamalarda pano davranışını yapılandırabilir. Örneğin, son kullanıcıların uygulamadan veri kesmesini veya kopyalamasını ve yönetilmeyen, kişisel bir uygulamaya yapıştırmasını engellemek üzere bir ilke dağıtabilirler.

### <a name="enforce-encryption-on-saved-data"></a>Kaydedilen veriler üzerinde şifrelemeyi zorunlu kılma
BT yöneticileri, cihaza uygulama tarafından kaydedilen verilerin şifrelenmesini sağlayan bir ilke uygulayabilir.

### <a name="remotely-wipe-corporate-data"></a>Kurumsal verileri uzaktan silme
BT yöneticileri Intune tarafından yönetilen bir uygulamadaki şirket verilerini uzaktan silebilir. Bu özellik kimlik tabanlıdır ve yalnızca son kullanıcının kurumsal kimliğiyle ilişkili olan dosyaları siler. Özellik, bunun yapılabilmesi için uygulamanın katılımını gerektirir. Uygulama, kullanıcı ayarlarına göre silmenin hangi kimlik için gerçekleşeceğini belirtebilir. Uygulamada bu kullanıcı ayarlarının belirtilmemiş olması durumunda varsayılan davranış, uygulama dizininin silinmesi ve erişimin kaldırıldığının son kullanıcıya bildirilmesidir.

### <a name="enforce-the-use-of-a-managed-browser"></a>Yönetilen tarayıcı kullanımını zorunlu kılma
BT yöneticileri, uygulamadaki web bağlantılarının [Intune Managed Browser uygulaması](../apps/app-configuration-managed-browser.md) ile açılmasını zorunlu hale getirebilir. Bu işlev, şirket ortamında görünen bağlantıların Intune tarafından yönetilen uygulamaların etki alanı içinde kalmasını sağlar.

### <a name="enforce-a-pin-policy"></a>PIN ilkesini zorunlu kılma
BT yöneticileri, son kullanıcının uygulamadaki kurumsal verilere erişmeden önce bir PIN girmesini zorunlu kılabilir. Bu, uygulamayı kullanan kişinin başlangıçta iş veya okul hesabıyla oturum açan kişi olmasını sağlar. Son kullanıcılar PIN kodlarını yapılandırdığında, Intune Uygulama SDK'sı Azure Active Directory kullanarak son kullanıcıların kimlik bilgilerini kayıtlı Intune hesabıyla karşılaştırarak doğrular.

### <a name="require-users-to-sign-in-with-a-work-or-school-account-for-app-access"></a>Kullanıcıların uygulama erişimi için bir iş veya okul hesabıyla oturum açmasını gerektir
BT yöneticileri, kullanıcıların uygulamaya erişmek için iş veya okul hesaplarıyla oturum açmasını zorunlu kılabilir. Intune Uygulama SDK'sı, girilen kimlik bilgilerinin sonraki oturumlar için yeniden kullanıldığı çoklu oturum açma deneyimini sağlamak üzere Azure Active Directory’i kullanır. Ayrıca Azure Active Directory ile federasyon uygulanmış kimlik yönetimi çözümlerinin kimlik doğrulaması da desteklenir.

### <a name="check-device-health-and-compliance"></a>Cihaz durumunu ve uyumluluğunu denetleme
BT yöneticileri, son kullanıcıların uygulamaya erişmesinden önce cihazın durumunu ve Intune ilkeleriyle uyumluluğunu denetleyebilir. iOS’ta bu ilke, cihaza jailbreak uygulanıp uygulanmadığını denetler. Android’de bu ilke, cihaza kök erişim izni verilip verilmediğini denetler.

### <a name="support-multi-identity"></a>Çoklu kimlik desteği
Çoklu kimlik desteği, ilkeyle yönetilen (şirket) ve yönetilmeyen (kişisel) hesapların tek bir uygulamada birlikte bulunmasını sağlayan bir SDK özelliğidir.

Örneğin, çok sayıda kullanıcı, iOS ve Android için Office mobil uygulamalarında hem şirket hem de kişisel e-posta hesaplarını yapılandırır. Bir kullanıcı kurumsal hesabıyla verilere eriştiğinde, BT yöneticisi uygulama koruma ilkesinin uygulanacağından emin olmalıdır. Ancak, bir kullanıcı kişisel e-posta hesabına erişirken bu veriler BT yöneticisinin denetimi dışında olmalıdır. Intune Uygulama SDK'sı bunu, uygulama koruma ilkesini **yalnızca** uygulamadaki kurumsal kimliğine hedefleyerek sağlar.

Çoklu kimlik özelliği, kuruluşların hem kişisel hesapları hem de iş hesaplarını destekleyen mağaza uygulamalarında karşılaştığı veri koruma sorununu çözmeye yardımcı olur.
 
### <a name="app-protection-without-device-enrollment"></a>Cihaz kaydı olmadan uygulama koruma

>[!IMPORTANT]
>Intune Uygulama Sarmalama Araçları, Android için Intune Uygulama SDK’sı, iOS için Intune Uygulama SDK’sı ve Intune Uygulama SDK’sı Xamarin Bağlamaları ile cihaz kaydı olmaksızın Intune uygulama koruması kullanılabilir.

Kişisel cihaz kullanan çok sayıda kullanıcı cihazını bir Mobil Cihaz Yönetimi (MDM) sağlayıcısına kaydetmeden şirket verilerine erişmeyi ister. MDM kaydı cihazın genel denetimini gerektirdiğinden, kullanıcılar genellikle kendi kişisel cihazlarının denetimini şirketlerine verme konusunda tereddütlüdür.

Cihaz kaydı olmadan uygulama koruma, Microsoft Intune hizmetinin uygulama koruma ilkesini bir cihaz yönetim kanalı kullanmadan, doğrudan uygulamaya dağıtmasını sağlar.

### <a name="on-demand-application-vpn-connections-with-citrix-mvpn"></a>Citrix mVPN ile isteğe bağlı uygulama VPN bağlantıları 
Cihazları ve uygulamaları Citrix XenMobile MDX ve Microsoft Intune bileşimi ile yönetebilirsiniz. Bu bileşim, Citrix’in mVPN teknolojisini kullanırken uygulamaları Intune uygulama koruma ilkesiyle yönetebileceğiniz anlamına gelir. Citrix ile tümleştirme, iOS ve Android için Intune Uygulama SDK’sının yanı sıra iOS ve Android için Intune Uygulama Sarmalama Aracı (-citrix bayrağı olan) ile kullanılabilir.
 
Citrix MDX hakkında daha fazla bilgi edinmek için bkz. [MDX Toolkit hakkında](https://docs.citrix.com/en-us/mdx-toolkit/10/about-mdx-toolkit.html), [iOS için Citrix MDX uygulama sarmalayıcı](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-ios.html) ve [Android için Citrix MDX uygulama sarmalayıcı](https://docs.citrix.com/en-us/mdx-toolkit/10/xmob-mdx-kit-app-wrap-android.html).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune uygulama SDK 'sını kullanmaya](app-sdk-get-started.md)başlayın.
