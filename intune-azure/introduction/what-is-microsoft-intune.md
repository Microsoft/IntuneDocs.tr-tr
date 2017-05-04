---
title: "Azure portalı önizlemesinde Intune’a giriş"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Azure Portal önizlemesinde Intune hakkındaki temel bilgileri alın ve cihazlarınızı yönetmenize nasıl yardımcı olabileceğini öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 92e07a49205ffaf287fc3aa2da6a6376b75fda4f
ms.lasthandoff: 04/24/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Azure Portal önizlemesinde Microsoft Intune’a giriş


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune Azure Portal’a taşınıyor ve bu da alıştığınız iş yükleriyle işlevlerin değişeceği anlamına geliyor.
Yeni portal, kuruluşunuzun mobil cihazlarını, bilgisayarlarını ve uygulamalarını yönetebileceğiniz Azure portalındaki yeni ve güncelleştirilmiş işlevlerin bir önizlemesini sunuyor.
Tüm Intune işlevselliği sonunda Azure’a taşınacaktır. Ancak pek çok Intune görevini bugünden Azure portalında gerçekleştirebilirsiniz. Bu yeni deneyim henüz önizleme aşamasında olduğundan, bazı işlevler henüz portalda bulunmayabilir. Ayrıntılı bilgiler için [Yenilikler](#what's-new) bölümünü gözden geçirin.

> [!IMPORTANT]
> **Henüz yeni portalı görmüyor musunuz?**<br>
> Belirli kiracılara önizlemenin dağıtımına şimdiden başladık. 2017 takvim yılının başlarında mevcut kiracıların yeni deneyime geçirilmesine başlanacak. Kiracınızın geçişinden önce, Office İleti Merkezi’nde bir bildirim alacaksınız.


Yeni ürün belgelerini bu kitaplıkta bulabileceksiniz ve önizleme boyunca kitaplık güncelleştirilecek. Görmek istediklerinize ilişkin önerileriniz varsa, lütfen konu yorumlarında geri bildirim sağlayın. Görüşlerinizi öğrenmeyi çok isteriz.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Yeni deneyimde öne çıkan özellikler:

- Tüm Enterprise Mobility + Security (EMS) bileşenleriniz için tümleşik bir konsol
- Web standartlarında hazırlanan HTML tabanlı bir konsol
- Birçok eylemi otomatik hale getirmek için Microsoft Graph API’si desteği
- Tüm Azure uygulamalarınız genelinde uyumluluk sağlamak için Azure Active Directory (AD) grupları
- En modern web tarayıcıları için destek

Klasik Intune konsolu hakkındaki belgeleri arıyorsanız, bkz. [Intune belge kitaplığı](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Başlamadan önce

Azure Portal’da Intune’u kullanmak için, bir Intune yönetici ve kiracı hesabınız olmalıdır. Hesabınız yoksa [bir hesap için kaydolun](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Azure Portal için desteklenen web tarayıcıları

Azure Portal, modern PC ve Mac bilgisayarlarla tabletlerin çoğunda çalışır. Cep telefonları desteklenmez.
Şu anda, aşağıdaki web tarayıcıları desteklenmektedir:

- Microsoft Edge (en son sürüm)
- Microsoft Internet Explorer 11
- Safari (en so sürüm, yalnızca Mac)
- Chrome (en son sürüm)
- Firefox (en son sürüm)

Desteklenen tarayıcılar hakkındaki en son bilgiler için [Azure portalını](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) kontrol edin.

## <a name="whats-in-this-library"></a>Bu kitaplıkta neler var?

Aradığınız bilgileri bulmanızı kolaylaştırmak için, belgeler Intune portalının düzenini yansıtır.

![Azure Portal iş yükleri](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Giriş ve çalışmaya başlama
Bu bölüm, [yenilikler](/intune-azure/introduction/whats-new), [bilinen sorunlar](/intune-azure/introduction/known-issues-in-the-intune-preview), [nasıl destek alınacağı](/intune-azure/introduction/how-to-get-support-for-microsoft-intune) ve Intune [ücretsiz deneme sürümünü kullanmaya başlama](/intune-azure/introduction/sign-up-free-trial-microsoft-intune) hakkında bilgiler içerir.
### <a name="plan-and-design"></a>Planlama ve tasarlama
Intune ortamınızı [planlamanıza ve tasarlamanıza](/intune-azure/plan-and-design/get-started) yardımcı olacak bilgiler.
### <a name="device-enrollment"></a>Cihaz kaydı
[Cihazlarınızın Intune tarafından yönetilmesini nasıl sağlarsınız?](/intune-azure/enroll-devices/what-is).
### <a name="device-compliance"></a>Cihaz uyumluluğu
[Cihazlarınız için bir uyumluluk düzeyi tanımlayın, ardından uyumlu olmayan tüm cihazları rapor edin](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="device-configuration"></a>Cihaz yapılandırması
[Yönettiğiniz cihazlarda ayarları ve özellikleri yapılandırmak için kullanabileceğiniz profilleri öğrenin](/intune-azure/configure-devices/what-are-device-profiles).
### <a name="devices"></a>Cihazlar
[Envanter ve raporlarla, yönettiğiniz cihazlar hakkında bilgi edinin](/intune-azure/manage-devices/what-is).
### <a name="mobile-apps"></a>Mobil uygulamalar
[Uygulamaları yayımlama, yönetme, yapılandırma ve koruma](/intune-azure/manage-apps/what-is-app-management).
### <a name="conditional-access"></a>Koşullu erişim
[Belirlediğiniz koşullara bağlı olarak Exchange hizmetlerine erişimi kısıtlayın](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="on-premises-access"></a>Şirket içi erişim
[Exchange ActiveSync’e ve şirket içi Exchange’e erişimi yapılandırma](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Yönettiğiniz cihazların kullanıcıları hakkında bilgi edinin ve kaynakları gruplara ayırın](/intune-azure/manage-users/what-is).
### <a name="groups"></a>Gruplar
[Azure Active Directory gruplarını Intune'la nasıl kullanabileceğiniz hakkında bilgi edinin](/intune-azure/manage-users/get-started-with-groups)
### <a name="intune-roles"></a>Intune rolleri
[Çeşitli Intune eylemlerini kimlerin gerçekleştirebileceğini ve bu eylemlerin kimlere uygulanacağını denetleyin](/intune-azure/access-control/role-based-access-control). Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz.
### <a name="software-updates"></a>Yazılım güncelleştirmeleri
[Windows 10 cihazlaro için yazılım güncelleştirmelerini yapılandırma hakkında bilgi edinin](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).



## <a name="whats-new"></a>Yenilikler

[Önizleme sürümündeki yenilikleri keşfedin](/intune-azure/introduction/whats-new).

