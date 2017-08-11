---
title: Uygulama koruma ilkeleri nedir?
titleSuffix: Intune on Azure
description: "Şirket verilerinizi Microsoft Intune uygulama koruma ilkeleriyle korumayı öğrenin.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 96cdcbf76e396c6eff9479fc95aea255df7e55e8
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2017
---
# <a name="what-are-app-protection-policies"></a>Uygulama koruma ilkeleri nelerdir?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune uygulama koruma ilkeleri, şirket verilerinizi korumaya ve veri kaybını önlemeye yardımcı olur.

## <a name="how-you-can-protect-app-data"></a>Uygulama verilerinizi nasıl koruyabilirsiniz?
Çalışanlarınız hem kişisel hem de iş amaçlı görevler için mobil cihazlar kullanır.  Bir yandan çalışanlarınızın üretken olmasını sağlarken diğer yandan, isteyerek ve istemeyerek yaşanabilecek veri kayıplarını önlemek isteyebilirsiniz.  Ayrıca, tarafınızdan yönetilmediği durumda dahi cihazları kullanarak erişilen şirket verilerini koruma becerisine sahip olmak istersiniz.

Şirketinizin verilerini korumaya yardımcı olmak için Intune uygulama koruma ilkelerini kullanabilirsiniz. Intune uygulama koruma ilkeleri, **herhangi bir mobil cihaz yönetimi (MDM) çözümünden bağımsız olarak** kullanılabildiğinden, bunu şirketinizin verilerini cihazları bir cihaz yönetimi çözümüne kaydederek veya kaydetmeden korumak üzere kullanabilirsiniz. **Uygulama düzeyinde ilkeler** uygulayarak, şirket kaynaklarına erişimi kısıtlayabilir ve verileri BT departmanınızın kapsamında tutabilirsiniz.

Aşağıdaki özelliklere sahip cihazlarda çalıştırılan uygulamalar için uygulama koruma ilkeleri yapılandırılabilir:

- **Microsoft Intune’a kayıtlı:** Bu kategorideki cihazlar normalde şirkete ait cihazlardır.

-   **Bir üçüncü taraf mobil cihaz Yönetimi (MDM) çözümde kayıtlı:**   Bu kategorideki cihazlar normalde şirkete ait cihazlardır.

  > [!NOTE]
  > mobil uygulama yönetimi ilkeleri, üçüncü taraf mobil uygulama yönetimi veya güvenli kapsayıcı çözümleri ile birlikte kullanılmamalıdır.

-   **Herhangi bir mobil cihaz yönetimi çözümünde kayıtlı değil:** Bu kategorideki cihazlar normalde Intune veya diğer MDM çözümlerinde yönetilmeyen veya kayıtlı olmayan, çalışana ait cihazlardır.

> [!IMPORTANT]
> Office 365 hizmetlerine bağlanan Office mobil uygulamaları için mobil uygulama yönetimi ilkeleri oluşturabilirsiniz. Uygulama koruma ilkeleri, şirket içi Exchange, Skype Kurumsal veya SharePoint hizmetlerine bağlanan uygulamalar için desteklenmez.

**Uygulama koruma ilkelerini kullanmanın önemli avantajları**

-   Şirket verilerinizi uygulama düzeyinde koruma.  Mobil uygulama yönetimi cihaz yönetimi gerektirmediğinden, hem yönetilen hem de yönetilmeyen cihazlardaki şirket verilerini koruyabilirsiniz. Yönetim, kullanıcı kimliğine odaklandığından cihaz yönetimine gerek kalmaz.

-   Son kullanıcının üretkenliği etkilenmez ve uygulama kişisel bağlamda kullanılırken ilkeler uygulanmaz.  İlkeler yalnızca çalışma bağlamında uygulanır; böylece kişisel verilere dokunmadan şirket verilerini koruyabilirsiniz.

MDM'yi Uygulama koruma ilkeleriyle kullanmanın başka avantajları da vardır ve şirketler Uygulama koruma ilkelerini aynı anda hem MDM'li hem de MDM'siz olarak kullanabilir. Örneğin, bir çalışan, şirket tarafından verilen bir telefonun yanı sıra kişisel bir tablet kullanabilir.  Bu durumda, şirket telefonu MDM’ye kaydedilir ve Uygulama koruma ilkeleriyle korunur. Kişisel cihaz ise yalnızca Uygulama koruma ilkeleriyle korunur.

- **MDM, cihazın korunmasını sağlar**.  Örneğin, cihaza erişim için PIN’i zorunlu kılabilir veya yönetilen uygulamaları cihaza dağıtabilirsiniz. Ayrıca, uygulama yönetimi üzerinde daha fazla denetime sahip olmak için uygulamaları MDM çözümünüz aracılığıyla cihazlara dağıtabilirsiniz.

- **Uygulama koruma ilkeleri, uygulama katmanındaki korumaların devrede olmasını sağlar**. Örneğin, bir uygulamayı çalışma bağlamında açmak için PIN’i zorunlu kılabilir, verilerin uygulamalar arasında paylaşılıp paylaşılmayacağını belirleyebilir ya da şirket uygulama verilerinin kişisel bir depolama konumuna kaydedilmesini engelleyebilirsiniz.


### <a name="supported-platforms-for-app-protection-polices"></a>Uygulama koruma ilkeleri için desteklenen platformlar
-   iOS 8.1 veya üzeri

-   Android 4 veya üzeri

Windows cihazları şu anda desteklenmez. Ancak, Windows 10 cihazlarını Intune'a kaydettiğinizde, benzer bir işlevsellik sunan Windows Bilgi Koruması’nı kullanabilirsiniz. Ayrıntılar için bkz. [Windows Bilgi Koruması’nı (WIP) kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).
##  <a name="how-app-protection-policies-protect-app-data"></a>Uygulama koruma ilkeleri uygulama verilerini nasıl korur

####  <a name="apps-without-app-protection-policies"></a>Uygulama koruma ilkelerinin bulunmadığı uygulamalar

![Uygulama koruma ilkeleri devrede olmadığında verilerin uygulamalar arasında serbestçe taşınabildiğini gösteren resim](./media/apps-without-protection-policies.png)

Uygulamalar kısıtlama olmadan kullanıldığında, şirket verileri ile kişisel veriler birbirine karışabilir.  Şirket verileri, kişisel depolama alanı gibi konumlara düşebilir veya kapsamınızın dışındaki uygulamalara aktarılarak veri kaybına neden olabilir. Şemadaki oklar, uygulamalar arasındaki (şirket ve kişisel) ve depolama konumlarına yönelik kısıtlanmamış veri hareketlerini gösterir.

### <a name="data-protection-with-app-protection-policies"></a>Uygulama koruma ilkeleriyle verileri koruma

![Uygulama koruma ilkeleri uygulandığında şirket verilerinin nasıl korunduğunu gösteren resim ](./media/apps-with-protection-policies.png)


Uygulama koruma ilkelerini, şirket verilerinin cihazın yerel depolama birimine kaydedilmesini önlemek ve Uygulama koruma ilkeleriyle korunmayan diğer uygulamalara veri taşınmasını kısıtlamak için kullanabilirsiniz. Uygulama koruma ilkesi ayarları aşağıdakileri içerir:
- **Farklı Kaydetmeyi Engelle**, **Kesme, kopyalama ve yapıştırma işlemlerini kısıtla** gibi veri yer değiştirme ilkeleri.
- **Erişim için basit PIN gerektir**, **Jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda, yönetilen uygulamaların çalışmasını engelle** gibi erişim ilkesi ayarları.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a>Bir MDM çözümüyle yönetilen cihazlarda uygulama koruma ilkeleriyle veri koruması

![Uygulama koruma ilkelerinin KCG cihazlarında nasıl çalıştığını gösteren resim](./media/app-protection-policies-with-mdm.png)

**Bir MDM çözümüne kaydedilen cihazlar için**-

Yukarıdaki çizimde, MDM ve Uygulama koruma ilkelerinin birlikte sunduğu koruma katmanları gösterilir.

MDM çözümü:

-   Cihazı kaydeder

-   Uygulamaları cihaza dağıtır

-   Sürekli cihaz uyumluluğu ve yönetimi sağlar

**Uygulama koruma ilkeleri, aşağıdaki nedenlerle değer ekler:**

-   Şirket verilerinin tüketici uygulamalarına ve hizmetlerini sızmasını önlemeye yardımcı olma

-   Mobil uygulamalara kısıtlamalar (farklı kaydet, pano, PIN, vs.) uygulama

-   Uygulamaları cihazdan kaldırmadan şirket verilerini uygulamalardan silme


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Kaydolmamış cihazlar için uygulama koruma ilkeleriyle veri koruması

![Uygulama koruma ilkelerinin yönetilen cihazlarda nasıl çalıştığını gösteren resim](./media/app-protection-policies-without-mdm.png)

Yukarıdaki şemada, veri koruma ilkelerinin uygulama düzeyinde MDM olmadan nasıl çalıştığı gösterilmektedir.

Herhangi bir MDM çözümüne kayıtlı olmayan KCG cihazlarında, Uygulama koruma ilkeleri şirket verilerinin uygulama düzeyinde korunmasına yardımcı olabilir.
Ancak, dikkat edilmesi gereken bazı sınırlamalar vardır, örneğin:

-   Uygulamaları cihaza dağıtamazsınız.  Son kullanıcı, uygulamaları mağazadan almak zorundadır.

-   Bu cihazlarda sertifika profillerini sağlayamazsınız.

-   Bu cihazlarda şirket Wi-Fi ve VPN ayarlarını sağlayamazsınız.


## <a name="multi-identity"></a>Çoklu kimlik

Uygulama koruma ilkeleri uygulamalar yalnızca iş bağlamında kullanılırken uygulanırken, birden çok kimliği destekleyen uygulamalar aynı uygulamalara erişmek için farklı hesaplar (iş ve kişisel) kullanmanıza izin verir.

Örneğin, bir kullanıcı OneDrive uygulamasını iş hesabını kullanarak başlattığında, kişisel bir depolama konumuna dosya taşıyamaz. Ancak OneDrive'ı kendi kişisel hesabıyla kullandığında, kişisel OneDrive'ından kısıtlamasız olarak veri kopyalayabilir ve taşıyabilir.

- Intune ile [MAM ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

##  <a name="next-steps"></a>Sonraki adımlar

[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
