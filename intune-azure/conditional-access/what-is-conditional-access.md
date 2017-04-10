---
title: "Koşullu erişim nedir?"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Microsoft Intune Azure önizlemesinde kullanıcıların ve cihazların şirket kaynaklarına erişmek için uymaları gereken koşulları tanımlamayı öğrenin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 18ec39a15f9cc2ac8ce912eaa91e54371e7dd423


---

# <a name="what-is-conditional-access"></a>Koşullu erişim nedir?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Bu konu başlığı altında, Enterprise Mobility + Security’de geçerli olan koşullu erişimi açıklıyor ve ardından Intune’daki koşullu erişim özelliklerini anlatıyoruz.

Enterprise Mobility + Security (EMS) çözümünün koşullu erişim özelliği, bir yandan kurumsal verilerinizin güvenliği için ihtiyacınız olan denetimi sağlarken diğer yandan da kullanıcılarınıza her cihazda en iyi çalışmalarını ortaya koymalarını sağlayan bir deneyim sunmak için Azure Active Directory Premium ile Microsoft Intune’un gücünden yararlanır.

Koşullu erişimle, konum, cihaz ve kullanıcı durumu ve uygulama duyarlılığı temelinde kurumsal verilerinize erişimi sınırlayan koşullar tanımlayabilirsiniz.

Cihaz açısından bakıldığında, Intune ve Azure Active Directory birlikte çalışarak e-postaya ve Office 365 hizmetlerine yalnızca yönetilen ve uyumlu cihazların erişimine izin verildiğinden emin olunmasını sağlar. Örneğin, Azure Active Directory’de bir ilke ayarlayarak yalnızca etki alanına katılmış bilgisayarların veya Intune gibi bir mobil cihaz yönetimi uygulamasına kaydedilmiş mobil cihazların Office 365 hizmetlerine erişebilmesine olanak tanıyabilirsiniz. Intune’u kullanarak, cihazın uyumluluk durumunu denetleyen bir cihaz uyumluluk profili ayarlayabilirsiniz. Uyumluluk durumu Azure Active Directory’ye raporlanır ve kullanıcı şirket kaynaklarına erişmeye çalıştığında Azure Active Directory’de ilkenin zorunlu tutulması için kullanılır. Intune’da cihaz uyumluluğu hakkında bilgi edinmek için bkz. [Cihaz uyumluluğu nedir?](/intune-azure/set-device-compliance/what-is-device-compliance)

Exchange Online gibi bulut uygulamaları için koşullu erişim, Azure Active Directory aracılığıyla yapılandırılabilir. Daha fazla bilgi için bu [makaleye](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal) bakın.

## <a name="on-premises-conditional-access-in-intune"></a>Intune’da şirket içi koşullu erişim

Intune’da koşullu erişim, cihaz yönetimi ve kaydı temelinde **Şirket içi Exchange**’e erişime izin vermek veya erişimi engellemek için kullanılabilir.

Cihaz uyumluluk profili ayarları kullanılarak cihazın uyumluluğu değerlendirilir. Koşullu erişim bu değerlendirmeyi kullanarak şirket içi Exchange’e erişime izin verir veya erişimi engeller. Koşullu erişim bir cihaz uyumluluk profiliyle birlikte kullandığınızda, yalnızca uyumlu cihazların şirket içi Exchange’e erişmesine izin verilir. Belirli platformlara izin verme veya engelleme ya da Intune tarafından yönetilmeyen cihazları hemen engelleme gibi daha ayrıntılı bir denetim için, koşullu erişimde gelişmiş ayarlar yapılandırabilirsiniz.

Cihaz uyumluluk profili ve koşullu erişim, kullanıcıya atanır. Kullanıcının şirket içi Exchange’e erişirken kullandığı her cihaz, uyumluluk açısından denetlenir. Cihazın uyumluluk açısından değerlendirilebilmesi için, cihazı kullanan kullanıcıya atanmış bir uyumluluk profili olması gerektiğini unutmayın. Kullanıcıya hiçbir uyumluluk ilkesi dağıtılmadıysa, cihaz uyumlu olarak kabul edilir ve hiçbir erişim kısıtlaması uygulanmaz.

Cihazlar ayarlanan koşullara uymadığında, son kullanıcı cihazı kaydetmeye ve cihazın uyumsuz olmasına neden olan sorunu düzeltmeye yönlendirilir.

## <a name="next-steps"></a>Sonraki adımlar

[Şirket içi Exchange için koşullu erişim ilkesi oluşturma](create-conditional-access-policy-for-exchange-on-premises.md)

[Azure Active Directory’de koşullu erişimi yapılandırma](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)



<!--HONumber=Feb17_HO3-->


