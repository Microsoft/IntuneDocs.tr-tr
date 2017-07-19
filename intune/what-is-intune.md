---
title: "Azure portalında Intune’a giriş"
titleSuffix: Intune on Azure
description: "Azure portalında Intune hakkındaki temel bilgileri alın ve cihazlarınızı yönetmenize nasıl yardımcı olabileceğini öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae42ab64945982fedc2d6858e2f3eca8fbed334c
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Azure portalında Microsoft Intune’a giriş


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune artık Azure portalda; bu da alıştığınız iş yükleriyle işlevlerin artık farklı olduğu anlamına geliyor.
Yeni portal, Azure portalında kuruluşunuzun mobil cihazlarını, bilgisayarlarını ve uygulamalarını yönetebileceğiniz yeni ve güncelleştirilmiş işlevler sunuyor.

> [!IMPORTANT]
> **Henüz yeni portalı görmüyor musunuz?**<br>
> Mevcut kiracılar yeni deneyime geçiriliyor. Kiracınız geçirilmeden önce Office İleti Merkezi'nde bir bildirim gösterilir.
>
> Apple Kaydı iş akışlarının Azure’da kullanılabilmesi için Ocak 2017 öncesinde oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz duyurulmamıştır. Mevcut hesabınız Azure portalına erişemiyorsa bir deneme hesabı oluşturmanızı öneririz.
>
> Olası engelleyiciler listesini gözden geçirin: https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/


Bu kitaplıkta yeni portal hakkında bilgiler bulabilirsiniz ve bunlar sürekli olarak güncelleştirilir. Görmek istediklerinize ilişkin önerileriniz varsa konu yorumlarında geri bildirim sağlayın. Görüşlerinizi öğrenmeyi çok isteriz.

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
Bu bölüm, Intune kullanmaya başlamanıza yardımcı olacak [giriş bilgileri](introduction-intune.md) içerir.
### <a name="plan-and-design"></a>Planlama ve tasarlama
Intune ortamınızı [planlamanıza ve tasarlamanıza](/intune-classic/plan-design/introduction) yardımcı olacak bilgiler.
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
[Yönettiğiniz cihazların kullanıcıları hakkında bilgi edinin ve kaynakları gruplara ayırın](users-add.md).
### <a name="groups"></a>Gruplar
[Azure Active Directory gruplarını Intune'la nasıl kullanabileceğiniz hakkında bilgi edinin](groups-get-started.md)
### <a name="intune-roles"></a>Intune rolleri
[Çeşitli Intune eylemlerini kimlerin gerçekleştirebileceğini ve bu eylemlerin kimlere uygulanacağını denetleyin](role-based-access-control.md). Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz.
### <a name="software-updates"></a>Yazılım güncelleştirmeleri
[Windows 10 cihazlaro için yazılım güncelleştirmelerini yapılandırma hakkında bilgi edinin](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Yenilikler

[Intune’daki yenilikleri öğrenin](whats-new.md).
