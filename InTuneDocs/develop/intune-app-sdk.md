---
# required metadata

title: Intune App SDK’sının yararları | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune Uygulama SDK'sına genel bakış
Intune Uygulama SDK'sı hem iOS hem de Android platformu için kullanılabilir ve Microsoft Intune ile mobil uygulama yönetim özelliklerini etkinleştirir. Ayrıca, geliştiricilerin yapması gereken kod değişikliği miktarının azaltılması konusunda da çalışmalar yapılmaktadır. Uygulamanızın davranışını değiştirmeden SDK özelliklerinin birçoğunu etkinleştirebileceğinizi göreceksiniz. Gelişmiş son kullanıcı ve BT yöneticisi deneyimi için, API’lerimizi kullanarak uygulamanızın davranışını uygulama katılımınızı gerektiren özelliklere göre özelleştirebilirsiniz. 
Uygulamanızı etkinleştirdikten sonra BT yöneticileri, ilkeleri Intune ile yönetilen uygulamalara dağıtabilir ve kurumsal verileri korumak için bu özelliklerden yararlanabilir.

## Normal Özellikler

### Kullanıcıların kurumsal belgeleri taşıma yeteneğini denetleme
BT yöneticileri, Intune ile yönetilen uygulamalarda kurumsal belgelerin dosyalarda yeniden konumlandırmasını denetleyebilir. Örneğin, dosya yedekleme uygulamalarının kurumsal verileri buluta yedeklemesini devre dışı bırakan bir ilke dağıtabilirler.

### Pano kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen uygulamalarda pano davranışını yapılandırabilir. Örneğin, son kullanıcıların Intune ile yönetilen bir uygulamadan kesme/kopyalama ve yönetilmeyen bir uygulamaya yapıştırma işlemleri için panoyu kullanmasını engelleyen bir ilke dağıtabilirler.

### Ekran yakalama kısıtlamalarını yapılandırma
BT yöneticileri, Intune ile yönetilen bir uygulama görüntülendiğinde kullanıcıların ekran yakalamasını engelleyebilir. Bu kısıtlamanın uygulanması, gizli kurumsal içeriğin yakalanıp yayınlanmasını engeller. Bu özellik yalnızca Android cihazlarda kullanılabilir.

### Kaydedilen veriler üzerinde şifrelemeyi zorunlu kılma
BT yöneticileri, cihaza uygulama tarafından kaydedilen verilerin şifrelenmesini sağlayan bir ilke uygulayabilir.

### Kurumsal verileri uzaktan silme
Cihazın Microsoft Intune kaydı silindiğinde, BT yöneticileri kurumsal verileri Intune ile yönetilen bir uygulamadan uzaktan silebilir. Bu özellik, kimliğe dayalıdır ve yalnızca son kullanıcının kurumsal kimliğiyle ilişkili olan dosyaları siler. Özellik, bunun yapılabilmesi için uygulamanın katılımını gerektirir. Uygulama, kullanıcı ayarlarına göre silmenin hangi kimlik için gerçekleşeceğini belirtebilir. Uygulamada bu kullanıcı ayarlarının belirtilmemiş olması durumunda varsayılan davranış, uygulama dizininin silinmesi ve şirket kaynaklarının kaldırıldığının son kullanıcıya bildirilmesidir.

### Yönetilen tarayıcı kullanımını zorunlu kılma
BT yöneticileri, bağlantılar Intune ile yönetilen uygulamaların içinden açılırken yönetilen bir tarayıcı kullanılmasını zorunlu kılabilir. Microsoft Intune ile yönetilen bir tarayıcının kullanılması, e-postalarda (Intune ile yönetilen bir posta istemcisinde bulunan e-postalar) görünen bağlantıların, Intune ile yönetilen uygulamaların etki alanında tutulmasını sağlamaya yardımcı olur.

### PIN ilkesini zorunlu kılma
BT yöneticileri, Intune ile yönetilen bir uygulama başlatıldığında PIN ilkesini zorunlu kılabilir. Bu ilke, cihazlarını Microsoft Intune’a kaydeden son kullanıcıların uygulamaları başlatan kişiler olduğundan emin olmaya yardımcı olur. Son kullanıcılar PIN kodlarını yapılandırdığında, Intune Uygulama SDK'sı Azure Active Directory kullanarak son kullanıcıların kimlik bilgilerini cihaz kaydı kimlik bilgilerine göre doğrular

### Kullanıcıların uygulamaları başlatabilmesi için kimlik bilgisi girmesini zorunlu kılma
BT yöneticileri, kullanıcıların Intune ile yönetilen bir uygulamayı başlatmadan önce kimlik bilgilerini girmelerini isteyebilir. Intune Uygulama SDK'sı, girilen kimlik bilgilerinin sonraki oturumlar için yeniden kullanıldığı çoklu oturum açma deneyimini sağlamak üzere Azure Active Directory’i kullanır. Ayrıca [Azure Active Directory ile federasyon uygulanmış](https://msdn.microsoft.com/library/azure/jj679342.aspx) kimlik yönetimi çözümlerinin kimlik doğrulaması da desteklenir.

### Cihaz durumunu ve uyumluluğunu denetleme
BT yöneticileri, son kullanıcıların Intune ile yönetilen uygulamalara erişmesinden önce cihazın durumunu ve şirket ilkeleriyle uyumluluğunu denetleyebilir. iOS platformunda bu ilke, cihaza jailbreak uygulanmış olup olmadığını denetler. Android platformunda bu ilke, cihaza kök erişimi verilip verilmediğini denetler.

## Önizleme Özellikleri
Microsoft Intune Uygulama SDK’sı, "önizleme" aşamasında olan çeşitli özellikler içerir. Önizleme API'leri ile tümleştirmeye başlayabilirsiniz, ancak bu işlemi yalnızca test amacıyla yapabilirsiniz. Bu önizlemeler mevcut senaryolara katkıda bulunur; söz konusu senaryoların yerini almaz.

### Microsoft Intune Uygulama SDK’sı çoklu kimlik desteği
Çoklu kimlik desteği, ilkeyle yönetilen (şirket) ve yönetilmeyen (kişisel) hesapların tek bir uygulamada birlikte bulunmasını sağlayan bir özelliktir.

### Çoklu kimlik senaryosu örneği
Çok sayıda kullanıcı, iOS ve Android için Outlook uygulamasında hem şirket hem de kişisel e-posta hesaplarını yapılandırır. Bir kullanıcı şirket hesabındaki verilere eriştiğinde, BT yöneticileri MAM ilkesi yönetiminin uygulanacağından emin olmalıdır. Ancak, bir kullanıcı kişisel e-posta hesabına erişirken bu veriler BT yöneticisinin denetimi dışında olmalıdır. Microsoft Intune bunu, yönetim ilkesini uygulamada yalnızca şirket hesabına yönlendirerek uygular. Bu çoklu kimlik özelliği, kuruluşların hem kişisel hesapları hem de iş hesaplarını destekleyen cihaz ve uygulamalarda karşılaştığı veri koruma sorununu çözmeye yardımcı olur.

### Çoklu kimliği destekleme
Önizleme API'leri; pano işlemleri ve dosya işlemleri gibi belirli veri işlemleriyle Kullanıcı Asıl Adı (UPN) belirtmenize olanak tanır. Microsoft Intune Uygulama SDK’sı, yapılan çağrı ile cihazı Microsoft Intune hizmetine kaydetmek için kullanılan UPN’yi eşleştirmek üzere UPN kullanır. UPN’ler eşleşiyorsa, çağrı "şirket verileri" çağrısı olarak kabul edilir ve veriler korunur; UPN’ler eşleşmiyorsa, çağrı "kişisel veriler" çağrısı olarak kabul edilir ve veriler korunmaz.

### Cihaz kaydı olmadan uygulama yönetimi
Kişisel cihaz kullanan çok sayıda kullanıcı cihazını bir Mobil Cihaz Yönetimi (MDM) ürününe kaydetmeden şirket verilerini görmeyi ve kullanmayı tercih eder. MDM kaydı cihazın genel denetimini gerektirdiğinden, kullanıcılar kendi kişisel cihazlarının genel denetimini şirketlerine vermek istemeyebilir.

Cihaz kaydı olmadan uygulama yönetimi, Microsoft Intune hizmetinin MAM ilkesini MDM kanalı kullanmadan, doğrudan uygulamaya dağıtmasını sağlar. MDM kanalı gerekli olmadığından MDM kaydı da gerekli değildir.



<!--HONumber=May16_HO2-->


