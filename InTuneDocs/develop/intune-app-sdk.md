---
title: "Intune App SDK’sının yararları | Microsoft Docs"
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Intune Uygulama SDK'sına genel bakış
Intune Uygulama SDK'sı hem iOS hem de Android platformu için kullanılabilir ve Microsoft Intune ile mobil uygulama yönetim özelliklerini etkinleştirir. Uygulama geliştiricisinin yapması gereken kod değişikliklerini en aza indirme çabası içindedir. Uygulamanızın davranışını değiştirmeden SDK’nın özelliklerinin birçoğunu etkinleştirebileceğinizi göreceksiniz. Gelişmiş son kullanıcı ve BT yöneticisi deneyimi için API’lerimizi kullanarak uygulamanızın davranışını, uygulama katılımınızı gerektiren özelliklere göre özelleştirebilirsiniz. 

Uygulamanızı etkinleştirdikten sonra BT yöneticileri, ilkeleri Intune ile yönetilen uygulamalara dağıtabilir ve kurumsal verileri korumak için bu özelliklerden yararlanabilir.

## <a name="regular-features"></a>Normal Özellikler

### <a name="control-users-ability-to-move-corporate-documents"></a>Kullanıcıların kurumsal belgeleri taşıma yeteneğini denetleme
BT yöneticileri, Intune ile yönetilen uygulamalarda kurumsal belgelerin dosyalarda yeniden konumlandırmasını denetleyebilir. Örneğin, dosya yedekleme uygulamalarının kurumsal verileri buluta yedeklemesini devre dışı bırakan bir ilke dağıtabilirler.

### <a name="configure-clipboard-restrictions"></a>Pano kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen uygulamalarda pano davranışını yapılandırabilir. Örneğin, son kullanıcıların Intune ile yönetilen bir uygulamadan kesme/kopyalama ve yönetilmeyen kişisel bir uygulamaya yapıştırma işlemleri için panoyu kullanmasını engelleyen bir ilke dağıtabilir.

### <a name="enforce-encryption-on-saved-data"></a>Kaydedilen veriler üzerinde şifrelemeyi zorunlu kılma
BT yöneticileri, cihaza uygulama tarafından kaydedilen verilerin şifrelenmesini sağlayan bir ilke uygulayabilir.

### <a name="remotely-wipe-corporate-data"></a>Kurumsal verileri uzaktan silme
BT yöneticileri Intune tarafından yönetilen bir uygulamadaki şirket verilerini uzaktan silebilir. Bu özellik kimlik tabanlıdır ve yalnızca son kullanıcının kurumsal kimliğiyle ilişkili olan dosyaları siler. Özellik, bunun yapılabilmesi için uygulamanın katılımını gerektirir. Uygulama, kullanıcı ayarlarına göre silmenin hangi kimlik için gerçekleşeceğini belirtebilir. Uygulamada bu kullanıcı ayarlarının belirtilmemiş olması durumunda varsayılan davranış, uygulama dizininin silinmesi ve erişimin kaldırıldığının son kullanıcıya bildirilmesidir.

### <a name="enforce-the-use-of-a-managed-browser"></a>Yönetilen tarayıcı kullanımını zorunlu kılma
BT yöneticileri, Intune ile yönetilen uygulamaların içinden bağlantı açılırken Intune Managed Browser uygulamasının kullanılmasını zorunlu kılabilir. Bu, şirket ortamında görünen bağlantıların Intune tarafından yönetilen uygulamaların etki alanı içinde kalmasını sağlar.

### <a name="enforce-a-pin-policy"></a>PIN ilkesini zorunlu kılma
BT yöneticileri, Intune ile yönetilen bir uygulama başlatıldığında PIN ilkesini zorunlu kılabilir. Bu, uygulamayı başlatan kullanıcının başlangıçta kayıtlı bir iş veya okul hesabıyla oturum açan kullanıcı olmasını sağlar. Son kullanıcılar PIN kodlarını yapılandırdığında, Intune Uygulama SDK'sı Azure Active Directory kullanarak son kullanıcıların kimlik bilgilerini kayıtlı Intune hesabıyla karşılaştırarak doğrular.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Kullanıcıların uygulamaları başlatabilmesi için kimlik bilgisi girmesini zorunlu kılma
BT yöneticileri, kullanıcıların Intune ile yönetilen bir uygulamayı başlatmadan önce kimlik bilgilerini girmelerini isteyebilir. Intune Uygulama SDK'sı, girilen kimlik bilgilerinin sonraki oturumlar için yeniden kullanıldığı çoklu oturum açma deneyimini sağlamak üzere Azure Active Directory’i kullanır. Ayrıca [Azure Active Directory ile federasyon uygulanmış](https://msdn.microsoft.com/library/azure/jj679342.aspx) kimlik yönetimi çözümlerinin kimlik doğrulaması da desteklenir.

### <a name="check-device-health-and-compliance"></a>Cihaz durumunu ve uyumluluğunu denetleme
BT yöneticileri, son kullanıcıların Intune ile yönetilen uygulamalara erişmesinden önce cihazın durumunu ve şirket ilkeleriyle uyumluluğunu denetleyebilir. iOS platformunda bu ilke, cihaza jailbreak uygulanmış olup olmadığını denetler. Android platformunda bu ilke, cihaza kök erişimi verilip verilmediğini denetler.

### <a name="sdk-multi-identity-support"></a>SDK çoklu kimlik desteği
Çoklu kimlik desteği, ilkeyle yönetilen (şirket) ve yönetilmeyen (kişisel) hesapların tek bir uygulamada birlikte bulunmasını sağlayan bir özelliktir.

Örneğin, çok sayıda kullanıcı, iOS ve Android için Outlook uygulamasında hem şirket hem de kişisel e-posta hesaplarını yapılandırır. Bir kullanıcı şirket hesabındaki verilere eriştiğinde, BT yöneticileri MAM ilkesi yönetiminin uygulanacağından emin olmalıdır. Ancak, bir kullanıcı kişisel e-posta hesabına erişirken bu veriler BT yöneticisinin denetimi dışında olmalıdır. Microsoft Intune bunu, yönetim ilkesini uygulamada yalnızca şirket hesabına yönlendirerek uygular. Bu çoklu kimlik özelliği, kuruluşların hem kişisel hesapları hem de iş hesaplarını destekleyen cihaz ve uygulamalarda karşılaştığı veri koruma sorununu çözmeye yardımcı olur.

* **Çoklu kimliği destekleme**: Microsoft Intune Uygulama SDK’sı API’leri; pano işlemleri ve dosya işlemleri gibi belirli veri işlemleriyle Kullanıcı Asıl Adı (UPN) belirtmenize olanak tanır. SDK, yapılan çağrı ile cihazı Microsoft Intune hizmetine kaydetmek için kullanılan UPN’yi eşleştirmek üzere UPN kullanır. UPN’ler eşleşiyorsa, çağrı "şirket verileri" çağrısı olarak kabul edilir ve veriler korunur; UPN’ler eşleşmiyorsa, çağrı "kişisel veriler" çağrısı olarak kabul edilir ve veriler korunmaz.

### <a name="app-management-without-device-enrollment"></a>Cihaz kaydı olmadan uygulama yönetimi

>[!IMPORTANT]
>Cihaz kaydı olmadan Intune mobil uygulama yönetimi şu anda yalnızca iOS için Intune Uygulama SDK'sı ile kullanılabilir. 


Kişisel cihaz kullanan çok sayıda kullanıcı cihazını bir Mobil Cihaz Yönetimi (MDM) ürününe kaydetmeden şirket verilerini görmeyi ve kullanmayı tercih eder. MDM kaydı cihazın genel denetimini gerektirdiğinden, kullanıcılar kendi kişisel cihazlarının genel denetimini şirketlerine vermek istemeyebilir.

Cihaz kaydı olmadan uygulama yönetimi, Microsoft Intune hizmetinin MAM ilkesini MDM kanalı kullanmadan, doğrudan uygulamaya dağıtmasını sağlar. MDM kanalı gerekli olmadığından MDM kaydı da gerekli değildir.



<!--HONumber=Dec16_HO2-->


