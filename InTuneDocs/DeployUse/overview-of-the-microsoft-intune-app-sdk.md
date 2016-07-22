---
title: "Microsoft Intune Uygulama SDK'sına Genel Bakış | Microsoft Intune"
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
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 8a9dfe8224b4e0e441691043eaffea73c456b3ec


---

# Microsoft Intune Uygulama SDK'sına Genel Bakış
Intune Uygulama SDK'sı hem iOS hem de Android platformu için kullanılabilir ve Microsoft Intune ile mobil uygulama yönetim özelliklerini etkinleştirir. Ayrıca, geliştiricilerin yapması gereken kod değişikliği miktarının azaltılması konusunda da çalışmalar yapılmaktadır. Uygulamanızın davranışını değiştirmeden SDK özelliklerinin birçoğunu etkinleştirebileceğinizi göreceksiniz. Gelişmiş son kullanıcı ve BT yöneticisi deneyimi için, API’lerimizi kullanarak uygulamanızın davranışını uygulama katılımınızı gerektiren özelliklere göre özelleştirebilirsiniz. 

Uygulamanızı etkinleştirdikten sonra BT yöneticileri, ilkeleri Intune ile yönetilen uygulamalara dağıtabilir ve kurumsal verileri korumak için bu özelliklerden yararlanabilir.

# Özellikler
## Kullanıcıların kurumsal belgeleri taşıma yeteneğini denetleme
BT yöneticileri, Intune ile yönetilen uygulamalarda kurumsal belgelerin dosyalarda yeniden konumlandırmasını denetleyebilir. Örneğin, dosya yedekleme uygulamalarının kurumsal verileri buluta yedeklemesini devre dışı bırakan bir ilke dağıtabilirler.  

## Pano kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen uygulamalarda pano davranışını yapılandırabilir. Örneğin, son kullanıcıların Intune ile yönetilen bir uygulamadan kesme/kopyalama ve yönetilmeyen bir uygulamaya yapıştırma işlemleri için panoyu kullanmasını engelleyen bir ilke dağıtabilirler.

## Ekran yakalama kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen bir uygulama görüntülendiğinde kullanıcıların ekran yakalamasını engelleyebilir. Bu kısıtlamanın uygulanması, gizli kurumsal içeriğin yakalanıp yayınlanmasını engeller. Bu özellik yalnızca Android cihazlarda kullanılabilir. 

## Kaydedilen veriler üzerinde şifrelemeyi zorunlu kılma
BT yöneticileri, cihaza uygulama tarafından kaydedilen verilerin şifrelenmesini sağlayan bir ilke uygulayabilir.

## Kurumsal verileri uzaktan silme
Cihazın Microsoft Intune kaydı silindiğinde, BT yöneticileri kurumsal verileri Intune ile yönetilen bir uygulamadan uzaktan silebilir. Bu özellik, kimliğe dayalıdır ve yalnızca son kullanıcının kurumsal kimliğiyle ilişkili olan dosyaları siler. Özellik, bunun yapılabilmesi için uygulamanın katılımını gerektirir. Uygulama, kullanıcı ayarlarına göre silmenin hangi kimlik için gerçekleşeceğini belirtebilir. Uygulamada bu kullanıcı ayarlarının belirtilmemiş olması durumunda varsayılan davranış, uygulama dizininin silinmesi ve şirket kaynaklarının kaldırıldığının son kullanıcıya bildirilmesidir. 

## Yönetilen tarayıcı kullanımını zorunlu kılma
BT yöneticileri, bağlantılar Intune ile yönetilen uygulamaların içinden açılırken yönetilen bir tarayıcı kullanılmasını zorunlu kılabilir. Microsoft Intune ile yönetilen bir tarayıcının kullanılması, e-postalarda (Intune ile yönetilen bir posta istemcisinde bulunan e-postalar) görünen bağlantıların, Intune ile yönetilen uygulamaların etki alanında tutulmasını sağlamaya yardımcı olur.

## PIN ilkesini zorunlu kılma
BT yöneticileri, Intune ile yönetilen bir uygulama başlatıldığında PIN ilkesini zorunlu kılabilir. Bu ilke, cihazlarını Microsoft Intune’a kaydeden son kullanıcıların uygulamaları başlatan kişiler olduğundan emin olmaya yardımcı olur. Son kullanıcılar PIN kodlarını yapılandırdığında, Intune Uygulama SDK'sı Azure Active Directory kullanarak son kullanıcıların kimlik bilgilerini cihaz kaydı kimlik bilgilerine göre doğrular. 

## Kullanıcıların uygulamaları başlatabilmesi için kimlik bilgisi girmesini zorunlu kılma
BT yöneticileri, kullanıcıların Intune ile yönetilen bir uygulamayı başlatmadan önce kimlik bilgilerini girmelerini isteyebilir. Intune Uygulama SDK'sı, girilen kimlik bilgilerinin sonraki oturumlar için yeniden kullanıldığı çoklu oturum açma deneyimini sağlamak üzere Azure Active Directory’i kullanır. Ayrıca [Azure Active Directory ile federasyon uygulanmış](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx) kimlik yönetimi çözümlerinin kimlik doğrulama yöntemleri desteklenir. 

## Cihaz durumunu ve uyumluluğunu denetleme
BT yöneticileri, son kullanıcıların Intune ile yönetilen uygulamalara erişmesinden önce cihazın durumunu ve şirket ilkeleriyle uyumluluğunu denetleyebilir. iOS platformunda bu ilke, cihaza jailbreak uygulanmış olup olmadığını denetler. Android platformunda bu ilke, cihaza kök erişimi verilip verilmediğini denetler.  





<!--HONumber=Jun16_HO4-->


