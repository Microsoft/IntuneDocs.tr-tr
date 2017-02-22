---
title: "Azure Portal önizlemesinde Intune’a giriş | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Azure Portal önizlemesinde Intune hakkındaki temel bilgileri alın ve cihazlarınızı yönetmenize nasıl yardımcı olabileceğini öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 01/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: f7f6dd79531d8d69eda3ed80bbb1cddf2692ab81


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Azure Portal önizlemesinde Microsoft Intune’a giriş


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune Azure Portal’a taşınıyor ve bu da alıştığınız iş yükleriyle işlevlerin değişeceği anlamına geliyor.
Yeni portal, kuruluşunuzun mobil cihazlarını, bilgisayarlarını ve uygulamalarını yönetebileceğiniz Azure Portal’daki yeni ve güncelleştirilmiş işlevlerin bir önizlemesini sunuyor.
Tüm Intune işlevselliği sonunda Azure’a taşınacak ama Intune görevlerinden bazılarını bugünden Azure Portal’da gerçekleştirebilirsiniz. Bu yeni deneyim henüz önizleme aşamasında olduğundan, bazı işlevler henüz portalda bulunmayabilir. Ayrıntılar için [Önizlemedeki yenilikler](#what's-new-in-the-preview) bölümünü gözden geçirin.

> [!IMPORTANT]
> **Henüz yeni portalı görmüyor musunuz?**<br>
> Belirli kiracılara önizlemenin dağıtımına şimdiden başladık. 2017 takvim yılının başlarında mevcut kiracıların yeni deneyime geçirilmesine başlanacak. Kiracınızın geçişinden önce, Office İleti Merkezi’nde bir bildirim alacaksınız. Kiracınızın geçişinin zaman çizelgesi hakkında sorunuz varsa, geçiş ekibimize şuradan ulaşabilirsiniz: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).


Yeni ürün belgelerini bu kitaplıkta bulabileceksiniz ve önizleme boyunca kitaplık güncelleştirilecek. Görmek istediklerinize ilişkin önerileriniz varsa, lütfen konu yorumlarında geri bildirim sağlayın. Görüşlerinizi öğrenmeyi çok isteriz.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Yeni deneyimde öne çıkan özellikler:

- Tüm Enterprise Mobility + Security (EMS) bileşenleriniz için tümleşik bir konsol
- Web standartlarında hazırlanan HTML tabanlı bir konsol
- Birçok eylemi otomatik hale getirmek için Microsoft Graph API’si desteği
- Tüm Azure uygulamalarınız genelinde uyumluluk sağlamak için Azure AD grupları
- En modern web tarayıcıları için destek

Klasik Intune konsolu hakkındaki belgeleri arıyorsanız, bkz. [Intune Belge Kitaplığı](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Başlamadan önce

Azure Portal’da Intune’u kullanmak için, bir Intune yönetici ve kiracı hesabınız olmalıdır. Hesap için [burada](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) kaydolabilirsiniz.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Azure Portal için desteklenen web tarayıcıları

Azure Portal, modern PC ve Mac bilgisayarlarla tabletlerin çoğunda çalışır. Cep telefonları desteklenmez.
Şu anda, aşağıdaki web tarayıcıları desteklenmektedir:

- Microsoft Edge (en son sürüm)
- Microsoft Internet Explorer 11
- Safari (en so sürüm, yalnızca Mac)
- Chrome (en son sürüm)
- Firefox (en son sürüm)

Desteklenen tarayıcılar hakkındaki en son bilgiler için [buraya](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) bakın.

## <a name="whats-in-this-library"></a>Bu kitaplıkta neler var?

Aradığınız bilgileri bulmanızı kolaylaştırmak için, belgeler Intune portalının düzenini yansıtır.

![Azure Portal iş yükleri](./media/azure-portal-workloads.png)

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>Cihazları kaydetme
Cihazlarınızın Intune tarafından yönetilmesini nasıl sağlarsınız?
[Daha fazla bilgi edinin](/intune-azure/enroll-devices/what-is)
### <a name="devices--groups"></a>Cihazlar ve Gruplar
Envanter ve raporlarla, yönettiğiniz cihazlar hakkında bilgi edinin.
[Daha fazla bilgi edinin](/intune-azure/manage-devices/what-is)
### <a name="manage-users"></a>Kullanıcıları yönetme
Yönettiğiniz cihazların kullanıcıları hakkında bilgi edinin.
[Daha fazla bilgi edinin](/intune-azure/manage-users/what-is)
### <a name="manage-apps"></a>Uygulamaları yönetme
Uygulamaları yayımlama, yönetme, yapılandırma ve koruma hakkında bilgi içerir.
[Daha fazla bilgi edinin](/intune-azure/manage-apps/what-is-app-management)
### <a name="configure-devices"></a>Cihazları yapılandırma
Yönettiğiniz cihazlarda ayarları ve özellikleri yapılandırmak için kullanabileceğiniz profiller hakkında bilgi içerir.
[Daha fazla bilgi edinin](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="set-device-compliance"></a>Cihaz uyumluluğu ayarlama
Cihazlarınız için bir uyumluluk düzeyi tanımlayın, ardından uyumlu olmayan tüm cihazları raporlayın [Daha fazla bilgi edinin](/intune-azure/set-device-compliance/what-is-device-compliance)
### <a name="conditional-access"></a>Koşullu erişim
Belirttiğiniz koşullara bağlı olarak Exchange hizmetlerine erişimi kısıtlayın.
[Daha fazla bilgi edinin](/intune-azure/conditional-access/what-is-conditional-access)
### <a name="access-control"></a>Erişim denetimi
Çeşitli Intune eylemlerini kimlerin gerçekleştirebileceğini ve bu eylemlerin kimlere uygulanacağını denetlemenize yardımcı olur. Bazı yaygın Intune senaryolarını kapsayan yerleşik rolleri kullanabileceğiniz gibi, kendi rollerinizi de oluşturabilirsiniz.
[Daha fazla bilgi edinin](/intune-azure/access-control/role-based-access-control)


## <a name="whats-new"></a>Yenilikler

[Önizleme sürümündeki yenilikleri keşfedin](/intune-azure/introduction/whats-new).


<!--HONumber=Feb17_HO1-->


