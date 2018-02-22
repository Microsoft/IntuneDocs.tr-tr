---
title: "Uygulama verilerini MAM ilkelerini kullanarak işleme"
description: "Bu konu başlığı altında, mobil uygulama yönetimi ilkelerinin şirket verilerinizi korumaya, veri kaybını önlemeye ve kişisel bilgilerle iş bilgilerini birbirinden ayırmaya nasıl yardımcı olabileceği açıklanmaktadır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e5f9eb33ca877fba0d59cfd9ddbc23f5eb2cd05c
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
---
# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a>Microsoft Intune ile uygulama koruma ilkelerini kullanarak uygulama verilerini koruma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>Uygulama verilerinizi nasıl koruyabilirsiniz?
Çalışanlarınız hem kişisel hem de iş amaçlı görevler için mobil cihazlar kullanır. Bir yandan çalışanlarınızın üretken olmasını sağlarken diğer yandan, isteyerek ve istemeyerek yaşanabilecek veri kayıplarını da önlemek istersiniz.  Ayrıca, çalışanların yönetmediğiniz cihazları kullanarak eriştiği şirket verilerini de koruyabilmek istersiniz.

Şirketinizin verilerini korumaya yardımcı olmak için Intune uygulama koruma ilkelerini kullanabilirsiniz. Intune Uygulama koruma ilkeleri, **herhangi bir mobil cihaz yönetimi (MDM) çözümünden bağımsız olarak** kullanılabildiğinden, cihazları bir cihaz yönetimi çözümüne kaydederek veya kaydetmeden şirketinizin verilerini korumak üzere MAM'ı kullanabilirsiniz. **Uygulama düzeyinde ilkeler** uygulayarak, şirket kaynaklarına erişimi kısıtlayabilir ve verileri BT departmanınızın kapsamında tutabilirsiniz.

Aşağıdaki özelliklere sahip cihazlarda çalışan uygulamalar için uygulama koruma ilkeleri yapılandırabilirsiniz:

-   **Microsoft Intune'a kayıtlı:** Bu kategorideki cihazlar normalde şirkete ait cihazlardır.

-   **Üçüncü taraf bir MDM çözümüne kayıtlı:** Bu kategorideki cihazlar normalde şirkete ait cihazlardır.

    > [!NOTE]
    > Üçüncü taraf mobil uygulama yönetimi veya güvenli kapsayıcı çözümleri ile uygulama koruma ilkelerinin kullanılması önerilmez.

-   **Herhangi bir MDM çözümüne kayıtlı değil:** Bu kategorideki cihazlar, normalde Intune veya diğer MDM çözümleriyle yönetilmeyen veya bunlara kayıtlı olmayan, çalışana ait cihazlardır.

> [!IMPORTANT]
> Office 365 hizmetlerine bağlanan Office mobil uygulamaları için uygulama koruma ilkeleri oluşturabilirsiniz. Uygulama koruma ilkeleri şirket içi Exchange, Skype Kurumsal veya SharePoint hizmetlerine bağlanan uygulamalar için desteklenmez.

## <a name="benefits-of-using-app-protection-policies"></a>Uygulama koruma ilkelerini kullanmanın yararları

-   **Şirket verilerinizi uygulama düzeyinde korumanıza yardımcı olurlar.** Mobil uygulama yönetimi, cihaz yönetimi gerektirmediği için şirket verilerini hem yönetilen hem de yönetilmeyen cihazlarda koruyabilirsiniz. Yönetim, kullanıcı kimliğine odaklandığından cihaz yönetimine gerek kalmaz.

-   **Kullanıcının üretkenliği etkilenmez ve uygulama kişisel bağlamda kullanılırken ilkeler uygulanmaz.** İlkeler yalnızca iş bağlamında uygulanır; bu da size şirket verilerini kişisel verilere dokunmadan koruma olanağı tanır.

MDM'yi uygulama koruma ilkeleriyle kullanmanın başka avantajları da vardır ve şirketler MAM'ı aynı anda MDM'li ve MDM'siz olarak kullanabilir. Örneğin bir çalışan, kişisel tabletin yanı sıra şirkete ait bir telefonu kullanabilir. Bu durumda, şirket telefonu MDM’ye kaydedilir ve uygulama koruma ilkeleriyle korunur. Kişisel cihaz ise yalnızca uygulama koruma ilkeleriyle korunur.

- **MDM, cihazın korunmasını sağlar.** Örneğin, cihaza erişim için PIN’i zorunlu kılabilir veya yönetilen uygulamaları cihaza dağıtabilirsiniz. Ayrıca, uygulama yönetimi üzerinde daha fazla denetime sahip olmak için MDM çözümünüz aracılığıyla cihazlara uygulama dağıtabilirsiniz.

- **Uygulama koruma ilkeleri, uygulama katmanındaki korumaların etkin olmasını sağlar.** Örneğin, bir uygulamanın iş bağlamında açılması için PIN gerektiren, uygulamalar arasında veri paylaşılmasını engelleyen ve şirket uygulama verilerinin kişisel bir depolama konumuna kaydedilmesini engelleyen bir ilkeniz olabilir.

## <a name="devices-that-support-mam"></a>MAM'ı destekleyen cihazlar
Intune uygulama koruma ilkeleri platformu desteği, Office uygulama platformu desteği ile uyumludur. Ayrıntılar için bkz. [Office Sistem Gereksinimleri](https://products.office.com/en-US/office-system-requirements).

>[!NOTE]
>Windows cihazları, kayıt senaryoları olmadan MAM’de desteklenmez. Ancak, Windows 10 cihazlarını Intune'a kaydettiğinizde, benzer bir işlevsellik sunan Windows Bilgi Koruması’nı kullanabilirsiniz. Ayrıntılar için bkz. [Windows Bilgi Koruması’nı (WIP) kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).


##  <a name="how-app-protection-policies-protect-app-data"></a>Uygulama koruma ilkeleri uygulama verilerini nasıl korur

###  <a name="apps-without-app-protection-policies"></a>Uygulama koruma ilkelerinin bulunmadığı uygulamalar

![Uygulama koruma ilkeleri etkin olmadığında verilerin uygulamalar arasında nasıl serbestçe taşınabildiğini gösteren resim](../media/Apps_without_MAM_policies.png)

Uygulamaları kısıtlamasız kullandığınızda, şirket verileri ve kişisel veriler birbirine karışabilir. Şirket verileri kişisel depolama alanlarına konabilir veya denetiminiz dışında uygulamalara aktarılabilir ve bunlar veri kaybına neden olabilir. Şemadaki oklar, uygulamalar arasındaki (şirket ve kişisel) ve depolama konumlarına yönelik kısıtlanmamış veri hareketlerini gösterir.

### <a name="data-protection-with-app-protection-policies"></a>Uygulama koruma ilkeleriyle veri koruma

![Uygulama koruma ilkeleri uygulandığında şirket verilerinin nasıl korunduğunu gösteren resim](../media/Apps_with_mobile_app_policies.png)

Uygulama koruma ilkelerini, şirket verilerinin cihazın yerel depolama birimine kaydedilmesini önlemek ve uygulama koruma ilkeleriyle korunmayan diğer uygulamalara veri taşınmasını kısıtlamak için kullanabilirsiniz. Uygulama koruma ilkesi ayarları aşağıdakileri içerir:
- **Farklı Kaydetmeyi Engelle**, **Kesme, kopyalama ve yapıştırma işlemlerini kısıtla** gibi veri yeri değiştirme ilkeleri.
- **Erişim için basit PIN gerektir**, **Yönetilen uygulamaların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** gibi erişim ilkesi ayarları.

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a>MDM çözümüyle yönetilen cihazlarda uygulama koruma ilkeleriyle veri koruması

![Kendi Cihazını Getir (KCG) cihazlarında uygulama koruma ilkelerinin nasıl çalıştığını gösteren görüntü](../media/MAM_BYOD_November.png)

**Bir MDM çözümüne kayıtlı cihazlarda**: Önceki şemada, MDM ve uygulama koruma ilkelerinin birlikte sunduğu koruma katmanları gösterilmektedir.

MDM çözümü:

-   Cihazı kaydeder.

-   Cihaza uygulama dağıtır.

-   Sürekli cihaz uyumluluğu ve yönetimi sağlar.

**Uygulama koruma ilkeleri, aşağıdaki sağlayarak değer katar:**

-   Şirket verilerinin tüketici uygulama ve hizmetlerine sızmasını önlemeye yardımcı olma.

-   Mobil uygulamalara kısıtlamalar (farklı kaydet, pano, PIN vs.) uygulama.

-   Uygulamaları cihazdan kaldırmadan şirket verilerini uygulamalardan silme.


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Kaydolmamış cihazlar için uygulama koruma ilkeleriyle veri koruması

![Uygulama koruma ilkelerinin yönetilen cihazlarda nasıl çalıştığını gösteren resim](../media/MAM_ManagedDevices_November.png)

Önceki şemada, veri koruma ilkelerinin uygulama düzeyinde MDM'siz nasıl çalıştığı gösterilmektedir.

Herhangi bir MDM çözümüne kayıtlı olmayan KCG cihazlarında uygulama koruma ilkeleri, şirket verilerinin uygulama düzeyinde korunmasına yardımcı olabilir.

Ancak dikkat edilmesi gereken bazı sınırlamalar vardır:

-   Cihaza uygulama dağıtamazsınız. Kullanıcı, uygulamaları mağazadan almak zorundadır.

-   Bu cihazlarda sertifika profilleri sağlayamazsınız.

-   Bu cihazlarda şirket Wi-Fi ve VPN ayarları yapamazsınız.


## <a name="multi-identity"></a>Çoklu kimlik

Uygulama koruma ilkeleri uygulamalar yalnızca iş bağlamında kullanılırken uygulanırken, birden çok kimliği destekleyen uygulamalar aynı uygulamalara erişmek için farklı hesaplar (iş ve kişisel) kullanmanıza izin verir.  

Örneğin, bir kullanıcı OneDrive uygulamasını iş hesabını kullanarak başlattığında, kişisel bir depolama konumuna dosya taşıyamaz. Ancak OneDrive'ı kendi kişisel hesabıyla kullandığında, kişisel OneDrive'ından kısıtlamasız olarak veri kopyalayabilir ve taşıyabilir.  

- Intune ile [MAM ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

##  <a name="next-steps"></a>Sonraki adımlar
- [Uygulama koruma ilkelerini yapılandırmaya hazırlanın](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
