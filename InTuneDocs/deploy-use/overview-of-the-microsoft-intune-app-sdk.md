---
title: "Microsoft Intune Uygulama SDK&quot;sına Genel Bakış | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4cb153c601b83b113a22b2acf3da5200cdb70472


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Microsoft Intune Uygulama SDK'sına Genel Bakış
Intune Uygulama SDK'sı hem iOS hem de Android platformu için kullanılabilir ve Microsoft Intune ile mobil uygulama yönetim özelliklerini etkinleştirir. Ayrıca, geliştiricilerin yapması gereken kod değişikliği miktarının azaltılması konusunda da çalışmalar yapılmaktadır.

Uygulamanızın davranışını değiştirmeden SDK özelliklerinin birçoğunu etkinleştirebileceğinizi göreceksiniz. Gelişmiş son kullanıcı ve BT yöneticisi deneyimleri için API’lerimizi kullanarak uygulamanızın davranışını, uygulama katılımınızı gerektiren özelliklere göre özelleştirebilirsiniz.

Uygulamanızı etkinleştirdikten sonra BT yöneticileri, ilkeleri Intune ile yönetilen uygulamalara dağıtabilir ve kurumsal verileri korumak için bu özelliklerden yararlanabilir.

# <a name="features"></a>Özellikler
## <a name="control-users-ability-to-move-corporate-documents"></a>Kullanıcıların kurumsal belgeleri taşıma yeteneğini denetleme
BT yöneticileri, Intune ile yönetilen uygulamalarda kurumsal belgelerin dosyalarda yeniden konumlandırmasını denetleyebilir. Örneğin, dosya yedekleme uygulamalarının kurumsal verileri buluta yedeklemesini devre dışı bırakan bir ilke dağıtabilirler.  

## <a name="configure-clipboard-restrictions"></a>Pano kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen uygulamalarda pano davranışını yapılandırabilir. Örneğin, son kullanıcıların Intune ile yönetilen bir uygulamadan kesme veya kopyalama ve yönetilmeyen bir uygulamaya yapıştırma işlemleri için panoyu kullanmasını engelleyen bir ilke dağıtabilirler.

## <a name="enforce-encryption-on-saved-data"></a>Kaydedilen veriler üzerinde şifrelemeyi zorunlu kılma
BT yöneticileri, cihaza uygulama tarafından kaydedilen verilerin şifrelenmesini sağlayan bir ilke uygulayabilir.

## <a name="remotely-wipe-corporate-data"></a>Kurumsal verileri uzaktan silme
Cihazın Microsoft Intune kaydı silindiğinde, BT yöneticileri kurumsal verileri Intune ile yönetilen bir uygulamadan uzaktan silebilir. Bu özellik kimliğe dayalıdır ve yalnızca son kullanıcının kurumsal kimliğiyle ilişkili olan dosyaları siler. Özellik, bunun yapılabilmesi için uygulamanın katılımını gerektirir. Uygulama, kullanıcı ayarlarına göre silmenin hangi kimlik için gerçekleşeceğini belirtebilir. Uygulamada bu kullanıcı ayarlarının belirtilmemiş olması durumunda varsayılan davranış, uygulama dizininin silinmesi ve şirket kaynaklarının kaldırıldığının son kullanıcıya bildirilmesidir.

## <a name="enforce-the-use-of-a-managed-browser"></a>Yönetilen tarayıcı kullanımını zorunlu kılma
BT yöneticileri, kullanıcılar Intune ile yönetilen uygulamaların içinden bağlantılar açtığında yönetilen bir tarayıcı kullanılmasını zorunlu kılabilir. Son kullanıcılar Microsoft Intune ile yönetilen bir tarayıcı kullanması, Intune ile yönetilen bir posta istemcisinde bulunan e-postalarda görünen bağlantıların, Intune ile yönetilen uygulamaların etki alanında tutulmasını sağlamaya yardımcı olur.

## <a name="enforce-a-pin-policy"></a>PIN ilkesini zorunlu kılma
BT yöneticileri, Intune ile yönetilen bir uygulama başlatıldığında PIN ilkesini zorunlu kılabilir. Bu ilke, cihazlarını Microsoft Intune’a kaydeden son kullanıcıların uygulamaları başlatan kişiler olduğundan emin olmaya yardımcı olur. Son kullanıcılar PIN’lerini yapılandırdığında, Intune Uygulama SDK'sı Azure Active Directory kullanarak son kullanıcıların kimlik bilgilerini cihaz kaydı kimlik bilgilerine göre doğrular.

## <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Kullanıcıların uygulamaları başlatabilmesi için kimlik bilgisi girmesini zorunlu kılma
BT yöneticileri, son kullanıcıların Intune ile yönetilen bir uygulamayı başlatmadan önce kimlik bilgilerini girmelerini isteyebilir. Intune Uygulama SDK'sı tek bir oturum açma deneyimi sağlamak için Azure Active Directory kullanır. Yani kimlik bilgileri bir kez girildikten sonra, sonraki oturum açmalarda yeniden kullanılır. SDK ayrıca [Azure Active Directory ile federasyon uygulanmış](/active-directory/active-directory-aadconnect-federation-compatibility) kimlik yönetimi çözümlerinin kimlik doğrulamasını da destekler.

## <a name="check-device-health-and-compliance"></a>Cihaz durumunu ve uyumluluğunu denetleme
BT yöneticileri, son kullanıcıların Intune ile yönetilen uygulamalara erişmesinden önce cihazın durumunu ve şirket ilkeleriyle uyumluluğunu denetleyebilir. iOS platformunda bu ilke, cihaza jailbreak uygulanmış olup olmadığını denetler. Android platformunda bu ilke, cihaza kök erişimi verilip verilmediğini denetler.  



<!--HONumber=Nov16_HO5-->


