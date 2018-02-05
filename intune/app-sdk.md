---
title: "Intune App SDK’sının yararları"
description: "Intune Uygulama SDK'sı hem iOS hem de Android platformu için kullanılabilir ve Microsoft Intune ile mobil uygulama yönetim özelliklerini etkinleştirir."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 08/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 75965145c38e94516846937e4dd408730d3ce10f
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="intune-app-sdk-overview"></a>Intune Uygulama SDK'sına genel bakış
iOS ve Android için kullanılabilen Intune uygulama SDK'sı, uygulamanızı Intune uygulama koruma ilkeleri için etkinleştirir. Uygulama geliştiricisinin yapması gereken kod değişikliklerini en aza indirme çabası içindedir. Uygulamanızın davranışını değiştirmeden SDK’nın özelliklerinin birçoğunu etkinleştirebileceğinizi göreceksiniz. Gelişmiş son kullanıcı ve BT yöneticisi deneyimi için API’lerimizi kullanarak uygulamanızın davranışını, uygulama katılımınızı gerektiren özelliklere göre özelleştirebilirsiniz.

Uygulama koruma ilkeleri için uygulamanızı etkinleştirdikten sonra, BT yöneticileri bu ilkeleri uygulama içindeki kurumsal verileri korumak için dağıtabilir.

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
BT yöneticileri, uygulamadaki web bağlantılarının [Intune Managed Browser uygulaması](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies) ile açılmasını zorunlu hale getirebilir. Bu, şirket ortamında görünen bağlantıların Intune tarafından yönetilen uygulamaların etki alanı içinde kalmasını sağlar.

### <a name="enforce-a-pin-policy"></a>PIN ilkesini zorunlu kılma
BT yöneticileri, son kullanıcının uygulamadaki kurumsal verilere erişmeden önce bir PIN girmesini zorunlu kılabilir. Bu, uygulamayı kullanan kişinin başlangıçta iş veya okul hesabıyla oturum açan kişi olmasını sağlar. Son kullanıcılar PIN kodlarını yapılandırdığında, Intune Uygulama SDK'sı Azure Active Directory kullanarak son kullanıcıların kimlik bilgilerini kayıtlı Intune hesabıyla karşılaştırarak doğrular.

### <a name="require-users-to-sign-in-with-work-or-school-account-for-app-access"></a>Kullanıcıların uygulama erişimi için iş veya okul hesabıyla oturum açmasını zorunlu kılma
BT yöneticileri, kullanıcıların uygulamaya erişmek için iş veya okul hesaplarıyla oturum açmasını zorunlu kılabilir. Intune Uygulama SDK'sı, girilen kimlik bilgilerinin sonraki oturumlar için yeniden kullanıldığı çoklu oturum açma deneyimini sağlamak üzere Azure Active Directory’i kullanır. Ayrıca Azure Active Directory ile federasyon uygulanmış kimlik yönetimi çözümlerinin kimlik doğrulaması da desteklenir.

### <a name="check-device-health-and-compliance"></a>Cihaz durumunu ve uyumluluğunu denetleme
BT yöneticileri, son kullanıcıların uygulamaya erişmesinden önce cihazın durumunu ve Intune ilkeleriyle uyumluluğunu denetleyebilir. iOS’ta bu ilke, cihaza jailbreak uygulanıp uygulanmadığını denetler. Android’de bu ilke, cihaza kök erişim izni verilip verilmediğini denetler.

### <a name="multi-identity-support"></a>Çoklu kimlik desteği
Çoklu kimlik desteği, ilkeyle yönetilen (şirket) ve yönetilmeyen (kişisel) hesapların tek bir uygulamada birlikte bulunmasını sağlayan bir SDK özelliğidir.

Örneğin, çok sayıda kullanıcı, iOS ve Android için Office mobil uygulamalarında hem şirket hem de kişisel e-posta hesaplarını yapılandırır. Bir kullanıcı kurumsal hesabıyla verilere eriştiğinde, BT yöneticisi uygulama koruma ilkesinin uygulanacağından emin olmalıdır. Ancak, bir kullanıcı kişisel e-posta hesabına erişirken bu veriler BT yöneticisinin denetimi dışında olmalıdır. Intune Uygulama SDK'sı bunu, uygulama koruma ilkesini **yalnızca** uygulamadaki kurumsal kimliğine hedefleyerek sağlar.

Çoklu kimlik özelliği, kuruluşların hem kişisel hesapları hem de iş hesaplarını destekleyen mağaza uygulamalarında karşılaştığı veri koruma sorununu çözmeye yardımcı olur.
 
### <a name="app-protection-without-device-enrollment"></a>Cihaz kaydı olmadan uygulama koruma

>[!IMPORTANT]
>Intune Uygulama Sarmalama Araçları, Android için Intune Uygulama SDK’sı, iOS için Intune Uygulama SDK’sı, SDK Xamarin Bileşeni ve SDK Cordova Eklentisi ile cihaz kaydı olmaksızın Intune uygulama koruması kullanılabilir.

Kişisel cihaz kullanan çok sayıda kullanıcı cihazını bir Mobil Cihaz Yönetimi (MDM) sağlayıcısına kaydetmeden şirket verilerine erişmeyi ister. MDM kaydı cihazın genel denetimini gerektirdiğinden, kullanıcılar genellikle kendi kişisel cihazlarının denetimini şirketlerine verme konusunda tereddütlüdür.

Cihaz kaydı olmadan uygulama koruma, Microsoft Intune hizmetinin uygulama koruma ilkesini bir cihaz yönetim kanalı kullanmadan, doğrudan uygulamaya dağıtmasını sağlar.
