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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d7ff50eb821e0927c3c6ea21f3cdb1257762a0
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Azure Portal önizlemesinde Microsoft Intune’a giriş


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Microsoft Intune Azure Portal’a taşınıyor ve bu da alıştığınız iş yükleriyle işlevlerin değişeceği anlamına geliyor.
Yeni portal, kuruluşunuzun mobil cihazlarını, bilgisayarlarını ve uygulamalarını yönetebileceğiniz Azure portalındaki yeni ve güncelleştirilmiş işlevlerin bir önizlemesini sunuyor.
Tüm Intune işlevselliği sonunda Azure’a taşınacaktır. Ancak pek çok Intune görevini bugünden Azure portalında gerçekleştirebilirsiniz. Bu yeni deneyim henüz önizleme aşamasında olduğundan, bazı işlevler henüz portalda bulunmayabilir. Ayrıntılı bilgiler için [Yenilikler](#whats-new) bölümünü gözden geçirin.

> [!IMPORTANT]
> **Henüz yeni portalı görmüyor musunuz?**<br>
> Belirli kiracılara önizlemenin dağıtımına şimdiden başladık. 2017 takvim yılının başlarında mevcut kiracıların yeni deneyime geçirilmesine başlanacak. Kiracınızın geçişinden önce, Office İleti Merkezi’nde bir bildirim alacaksınız.
>
> Apple Kaydı iş akışlarının Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.


Yeni ürün belgelerini bu kitaplıkta bulabileceksiniz ve önizleme boyunca kitaplık güncelleştirilecek. Görmek istediklerinize ilişkin önerileriniz varsa, lütfen konu yorumlarında geri bildirim sağlayın. Görüşlerinizi öğrenmeyi çok isteriz.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Yeni deneyimde öne çıkan özellikler:

- Tüm Enterprise Mobility + Security (EMS) bileşenleriniz için tümleşik bir konsol
- Web standartlarında hazırlanan HTML tabanlı bir konsol
- Birçok eylemi otomatik hale getirmek için Microsoft Graph API’si desteği
- Tüm Azure uygulamalarınız genelinde uyumluluk sağlamak için Azure Active Directory (AD) grupları
- En modern web tarayıcıları için destek

Klasik Intune konsolu hakkındaki belgeleri arıyorsanız, bkz. [Intune belge kitaplığı](https://docs.microsoft.com/intune-classic/).

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
Bu bölüm, [yenilikler](whats-new.md), [bilinen sorunlar](known-issues.md), [nasıl destek alınacağı](get-support.md) ve Intune [ücretsiz deneme sürümünü kullanmaya başlama](free-trial-sign-up.md) hakkında bilgiler içerir.
### <a name="plan-and-design"></a>Planlama ve tasarlama
Intune ortamınızı [planlamanıza ve tasarlamanıza](/intune-classic/plan-and-design/introduction) yardımcı olacak bilgiler.
### <a name="device-enrollment"></a>Cihaz kaydı
[Cihazlarınızın Intune tarafından yönetilmesini nasıl sağlarsınız?](device-enrollment.md).
### <a name="device-compliance"></a>Cihaz uyumluluğu
[Cihazlarınız için bir uyumluluk düzeyi tanımlayın, ardından uyumlu olmayan tüm cihazları rapor edin](device-compliance.md).
### <a name="device-configuration"></a>Cihaz yapılandırması
[Yönettiğiniz cihazlarda ayarları ve özellikleri yapılandırmak için kullanabileceğiniz profilleri öğrenin](device-profiles.md).
### <a name="devices"></a>Cihazlar
[Envanter ve raporlarla, yönettiğiniz cihazlar hakkında bilgi edinin](device-management.md).
### <a name="mobile-apps"></a>Mobil uygulamalar
[Uygulamaları yayımlama, yönetme, yapılandırma ve koruma](app-management.md).
### <a name="conditional-access"></a>Koşullu erişim
[Belirlediğiniz koşullara bağlı olarak Exchange hizmetlerine erişimi kısıtlayın](conditional-access.md).
### <a name="on-premises-access"></a>Şirket içi erişim
[Exchange ActiveSync’e ve şirket içi Exchange’e erişimi yapılandırma](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Yönettiğiniz cihazların kullanıcıları hakkında bilgi edinin ve kaynakları gruplara ayırın](user-management.md).
### <a name="groups"></a>Gruplar
[Azure Active Directory gruplarını Intune'la nasıl kullanabileceğiniz hakkında bilgi edinin](groups-get-started.md)
### <a name="intune-roles"></a>Intune rolleri
[Çeşitli Intune eylemlerini kimlerin gerçekleştirebileceğini ve bu eylemlerin kimlere uygulanacağını denetleyin](role-based-access-control.md). Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz.
### <a name="software-updates"></a>Yazılım güncelleştirmeleri
[Windows 10 cihazlaro için yazılım güncelleştirmelerini yapılandırma hakkında bilgi edinin](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Yenilikler

[Önizleme sürümündeki yenilikleri keşfedin](whats-new.md).

