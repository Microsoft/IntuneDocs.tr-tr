---
title: "Uygulamaları ve verileri koruma | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ded7bd6c971a9448ad6e6492ebc5e42dfcb5d76e
ms.openlocfilehash: 9445b4b171eb2102d73cf0e866e85b535274eee2


---

# Microsoft Intune ile uygulamaları ve verileri koruma


Intune, şirket verilerini birden çok teknoloji katmanıyla korur.  Kimlik katmanında, koşullu erişim, yalnızca yönetilen ve uyumlu cihazlardan erişimine izin vererek, hizmetlere erişimi korur.  İstemci uygulaması katmanında, mobil uygulama yönetimi (MAM), verilerin korumalı olmayan uygulamalara veya depolama konumlarına taşınmasını engelleyerek ve bir cihaz kaybedildiğinde veya çalındığında verileri silerek, veri kaybı koruması sağlar.  Bu iki koruma katmanı, mobil iş gücünüzü üretken halde tutarken veri güvenliğini sağlamak için birlikte kullanılmalıdır.

Şirket verilerini korumada önemli bir ilk adım, bu verilere erişmek için kullanılan cihazların, güçlü parola, şifreleme gibi güvenlik korumaları kullandığından ve işletim sistemi kısıtlamalarının kaldırılmadığından emin olarak koşullu erişim uygulamaktır. Microsoft Intune, cihazların, şirket e-postalarınıza ve verilerinize erişmesine izin verilmeden önce uymaları gereken koşulları belirleme becerisi sağlar.

[Koşullu erişim,](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) Intune’dan ayarlayabileceğiniz iki tür ilke tarafından belirlenir:
- [Uyumluluk ilkeleri](introduction-to-device-compliance-policies-in-microsoft-intune.md), bir cihazın uyumluluğunu belirler. Bunlar, aşağıdaki gibi ayar ve koşulları değerlendirir:
  - PIN ve parolalar: Bir cihazın kilidini açmadan önce parola girilmesinin gerekip gerekmediği, parolaların karmaşıklık gereksinimleri ve diğer parola ayarları için kurallar oluşturabilirsiniz.
  - Şifreleme: Şifrelenmiş cihazlara erişimi kısıtlayabilirsiniz.
  - Cihaz işletim sistemi kısıtlamaları kaldırılmamış veya kök erişimi yok: Intune, kayıtlı bir cihazın sistem kısıtlamalarının kaldırılmış olduğunu algılayabilir ve bu cihazlara erişimin engellenmesini sağlayan ilkeyi ayarlayabilirsiniz.
- [Koşullu erişim ilkeleri](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), Exchange Online veya SharePoint Online gibi belirli bir hizmet için yapılandırılır. Her hizmet için bu ilkelerin hangi kullanıcı gruplarına uygulanacağını tanımlayabilirsiniz. Örneğin, finans departmanındaki herkesin şirket e-postalarına yalnızca kayıtlı ve uyumlu cihazlardan erişebildiğinden emin olabilirsiniz.

Şirket kaynaklarına erişimi güvenli duruma getirmek, şirket verilerini korumanın yalnızca ilk adımıdır. Cihazda erişildikten sonra verileri koruma özelliğine yine de ihtiyacınız vardır. Veriler artık kopyalanabilir, taşınabilir, farklı bir konuma kaydedilebilir veya paylaşılabilir. Intune, aşağıdaki gibi kurallar kümesi oluşturarak veri hareketini kısıtlama becerisi sağlayarak bu sorunu çözer:
- Blok kopyalama ve yapıştırma veya iş bağlamı dışında veri aktarımını önleme.
- Kişisel bulut depolamaya yedeklemeyi engelleme, Farklı kaydet özelliğini engelleme.
- PIN/geçiş kodu veya kurumsal kimlik bilgileri gerektirerek güvenli uygulama erişimi.
- Intune Yönetilen Tarayıcı içinde tüm web bağlantılarının açık olmasını sağlama.

Bu kurallar kümesine, [mobil uygulama yönetimi (MAM) ilkeleri](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) adı verilir.  MAM ilkeleri, sizin tarafınızdan yönetilen veya yönetilmeyen cihazlarda çalışan uygulamalara uygulanabilir.  Intune’a kaydedilmiş cihazlar, başka bir üçüncü taraf MDM tarafından yönetilen ve kaydedilmiş cihazlar veya çalışana ait cihazlar gibi sizin tarafınızdan yönetilmeyebilecek bir cihaz için MAM ilkeleri kullanarak şirket verilerinizi koruyabilirsiniz.

Bir uygulamayı bir MAM ilkesiyle ilişkilendirmek için, uygulama Microsoft Intune Uygulaması Yazılım Geliştirme Seti’ni (SDK) içermelidir veya Uygulama sarmalama aracını kullanmalıdır.

Microsoft Office uygulamaları gibi uygulamalarda, Uygulama SDK’sı tümleşiktir. Desteklenen uygulamaların tam listesi, Microsoft Intune uygulama iş ortakları sayfasındaki [Microsoft Intune mobil uygulama galerisinde](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) bulunabilir. Desteklenen senaryoları, platformları ve uygulamanın çoklu kimliği destekleyip desteklemediğini görmek için, uygulamayı seçin.

Ayrıca, MAM ilkeleriyle kullanmak üzere, [özel oluşturulan iş kolu uygulamalarınızı da etkinleştirebilirsiniz](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

Veri hareketini kısıtlamaya ek olarak, bir cihaz kaybedilirse veya çalınırsa ya da kullanıcı artık şirketinizde çalışmıyorsa, [şirket verilerini seçmeli olarak temizleyerek](wipe-managed-company-app-data-with-microsoft-intune.md), yalnızca kişisel verileri bırakabilirsiniz.



<!--HONumber=Jun16_HO4-->


