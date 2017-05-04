---
title: "Microsoft Intune Önizlemesinde bilinen sorunlar"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Önizlemedeki bilinen sorunlar hakkında sağlanan bilgileri okuyun"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 08e2f65bcd600489f6599d37e5ef56c205176cd7
ms.lasthandoff: 04/25/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Microsoft Intune önizlemesinde bilinen sorunlar


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Intune önizlemesindeki tüm bilinen sorunlar hakkında bilgi edinmek için bu konuyu kullanın.

Burada listelenmeyen bir hatayı bildirmek istiyorsanız, [bir destek isteği açın](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Intune’a yeni bir özellik eklenmesini istiyorsanız, [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) sitemizde bir rapor doldurabilirsiniz.

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Geçiş sırasında Intune tarafından oluşturulan gruplar diğer Microsoft ürünlerinin işlevlerini etkileyebilir

Klasik Intune'dan Azure Portalı'na geçiş yaptığınızda **Tüm Kullanıcılar - b0b08746-4dbe-4a37-9adf-9e7652c0b421** adlı yeni bir grup görebilirsiniz. Bu grupta yalnızca Intune lisanslı kullanıcılar değil Azure Active Directory'niz içindeki tüm kullanıcılar bulunur. Var olan kullanıcılardan bazılarının veya yeni kullanıcıların herhangi bir gruba üye olmamasını bekliyorsanız bu durum diğer Microsoft ürünlerinde sorunlara neden olabilir.

### <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Intune tarafından geçiş sırasında oluşturulan grupların değiştirilmesi geçiş işleminde gecikmelere neden olacaktır

Geçiş için hazırlık aşamasında gruplarınız Intune'dan Azure AD'ye kopyalanır. Klasik Intune portalında yaptığınız ek değişikliklere göre Azure AD grubu güncelleştirilir. Ancak Azure AD'de yapılan değişiklikler klasik Intune konsoluyla eşitlenmez. Bu da Azure portalına geçiş işleminin başarısız olmasına ve geçişinizin gecikmesine neden olabilir.

### <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Intune'daki uyumluluk ilkeleri yeni konsolda gösterilmez 

Klasik Intune portalında oluşturduğunuz uyumluluk ilkeleri geçirilir ancak Azure portalında görüntülenmez. Bunun nedeni Azure portalındaki tasarım değişikliğidir. Klasik Intune portalında oluşturduğunuz uyumluluk ilkeleri uygulanmaya devam eder ancak bunları klasik portalda görüntülemeniz ve düzenlemeniz gerekir.
Ayrıca Azure portalında oluşturduğunuz yeni uyumluluk ilkeleri klasik portalda görünmez.
Daha fazla bilgi için bkz. [Cihaz uyumluluğu nedir?](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance)




### <a name="administration-and-accounts"></a>Yönetim ve hesaplar

Genel Yöneticiler (Kiracı Yöneticileri olarak da bilinir) ayrı bir Intune veya Enterprise Mobility Suite (EMS) lisansı olmadan günlük yönetim görevlerine devam edebilir. Ancak, Genel Yöneticiler kendi cihazlarını veya bir şirket cihazını kaydetme gibi amaçlarla hizmeti kullanmak ya da Intune Şirket Portalı’nı kullanmak isterse diğer tüm kullanıcılar gibi bir Intune veya EMS lisansına ihtiyaç duyacaklardır.

### <a name="apple-enrollment-profile-migration"></a>Apple kayıt profili geçişi
Intune, önümüzdeki birkaç ay içinde Apple Aygıt Kayıt Programı ve Apple Configurator kayıtlarınızı yeni Azure Portal aracılığıyla yönetmenize olanak sağlayacaktır. Apple Aygıt Kayıt Programı belirtecini siler ve güncelleştirilmiş bir belirteci karşıya yüklemezseniz özgün belirteç, Intune hesabınızı geçirme sürecinin bir parçası olarak yeni Azure Portal’a geri yüklenir. Bu belirteci kaldırmak ve DEP kaydını önlemek için belirteci Azure Portal’da silmeniz yeterlidir. 

