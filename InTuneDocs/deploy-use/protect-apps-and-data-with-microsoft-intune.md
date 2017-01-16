---
title: "Uygulamaları ve verileri koruma | Microsoft Docs"
description: "Bu konu başlığı altında, şirket uygulamalarınızı ve verilerinizi korumanıza yardımcı olmak için sağlanan çeşitli Intune özellikleri ve yetenekleri açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f46f13e9dbf03fa2b3e2ec7339cad927ea0b38e0
ms.openlocfilehash: 16e4b6ddd1df9c56e36318dfd3050d1a1f627adc


---

# <a name="protect-apps-and-data-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları ve verileri koruma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, şirket verilerini birden çok teknoloji katmanıyla korur. Kimlik katmanında, koşullu erişim, yalnızca yönetilen ve uyumlu cihazlardan erişimine izin vererek, hizmetlere erişimi korur. İstemci uygulaması katmanında, mobil uygulama yönetimi (MAM), verilerin korumalı olmayan uygulamalara veya depolama konumlarına taşınmasını engelleyerek ve bir cihaz kaybedildiğinde veya çalındığında verileri silerek veri kaybı koruması sağlar. Mobil iş gücünüzün üretkenliğini korurken veri güvenliğini sağlamak için bu iki koruma katmanının birlikte kullanılması önerilir.

Şirket verilerini korumak için önemli bir ilk adım, koşullu erişim uygulamaktır. Bunu yapmak için bu verilere erişmek amacıyla kullanılan cihazlarda güçlü parolalar ve şifreleme gibi güvenlik korumaları kullanıldığından ve bu cihazlara jailbreak uygulanmamış olduğundan emin olmanız gerekir. Intune, cihazların şirket e-postalarınıza ve verilerinize erişmesine izin verilmeden önce uymaları gereken koşulları belirlemenize imkan tanır.

[Koşullu erişim](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), Intune’dan ayarlayabileceğiniz iki tür ilke tarafından belirlenir:
- Bir cihazın uyumluluğunu belirlemek için [uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune.md) kullanırsınız. Bunlar, aşağıdaki gibi ayar ve koşulları değerlendirir:
  - PIN ve parolalar: Bir cihazın kilidini açmadan önce parola girilmesinin gerekip gerekmediği, parolaların karmaşıklık gereksinimleri ve diğer parola ayarları için kurallar oluşturabilirsiniz.
  - Şifreleme: Şifrelenmiş cihazlara erişimi kısıtlayabilirsiniz.
  - Cihaza jailbreak uygulanmamışsa veya kök erişimi izni verilmemişse: Intune, kayıtlı bir cihaza jailbreak uygulanıp uygulanmadığını algılayabilir. Bu cihazlara erişimin engellenmesini sağlayan ilkeyi ayarlayabilirsiniz.
- [Koşullu erişim ilkelerini](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), Exchange Online veya SharePoint Online gibi belirli bir hizmet için yapılandırırsınız. Her hizmet için bu ilkelerin hangi kullanıcı gruplarına uygulanacağını tanımlayabilirsiniz. Örneğin, finans departmanındaki herkesin şirket e-postalarına yalnızca kayıtlı ve uyumlu cihazlardan erişebildiğinden emin olabilirsiniz.

Şirket kaynaklarına erişimi güvenli duruma getirmek, şirket verilerini korumanın yalnızca ilk adımıdır. Cihazda erişildikten sonra verileri koruma özelliğine yine de ihtiyacınız vardır. Veriler artık kopyalanabilir, taşınabilir, farklı bir konuma kaydedilebilir veya paylaşılabilir. Intune, aşağıdaki gibi kurallar kümesi oluşturarak veri hareketini kısıtlama becerisi sağlayarak bu sorunu çözer:
- Kopyalama ve yapıştırmayı engelleme veya iş bağlamı dışında veri aktarımını önleme.
- Kişisel bulut depolamaya yedeklemeyi ve “Farklı kaydet” özelliğini engelleme.
- PIN/geçiş kodu veya kurumsal kimlik bilgileri gerektirerek uygulama erişiminin güvenliğini sağlama.
- Intune Managed Browser içinde tüm web bağlantılarının açık olmasını sağlama.

Bu kurallar kümesine, [mobil uygulama yönetimi (MAM) ilkeleri](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) adı verilir. MAM ilkelerini sizin tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulayabilirsiniz.  

**Intune’a kaydedilmiş cihazlar**, **başka bir üçüncü taraf mobil cihaz yönetimi (MDM) çözümü tarafından kaydedilmiş ve yönetilen cihazlar** veya çalışana ait cihazlar gibi **hiçbir MDM çözümüne kaydedilmemiş** cihazlar için MAM ilkelerini kullanarak şirket verilerinizi koruyabilirsiniz.

Bir uygulamayı MAM ilkesiyle ilişkilendirmek için uygulama, Microsoft Intune Uygulaması Yazılım Geliştirme Seti’ni (SDK) içermelidir veya Uygulama Sarmalama Aracını kullanabilirsiniz.

Microsoft Office uygulamaları gibi uygulamalarda Intune Uygulama SDK’sı tümleşiktir. Desteklenen uygulamaların tam listesini, Microsoft Intune uygulama iş ortakları sayfasında [Microsoft Intune mobil uygulama galerisinde](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) görebilirsiniz. Desteklenen senaryoları, platformları ve uygulamanın çoklu kimliği destekleyip desteklemediğini görmek için uygulamayı seçin.

Ayrıca, MAM ilkeleriyle kullanmak üzere, [özel oluşturulan iş kolu uygulamalarınızı da etkinleştirebilirsiniz](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Veri hareketini kısıtlamaya ek olarak, bir cihaz kaybedilirse veya çalınırsa ya da kullanıcı artık şirketinizde çalışmıyorsa, [şirket verilerini seçmeli olarak silerek](wipe-managed-company-app-data-with-microsoft-intune.md) yalnızca kişisel verileri bırakabilirsiniz.



<!--HONumber=Dec16_HO3-->


