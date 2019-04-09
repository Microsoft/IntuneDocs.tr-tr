---
title: Uygulama koruma ilkeleri nedir?
titleSuffix: Microsoft Intune
description: Microsoft Intune uygulama koruma ilkelerinin, şirket verilerinizi korumaya ve veri kaybını önlemeye nasıl yardımcı olduğunu öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 45e9f50881ff7da0554a4731712441b5fedb01d8
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292252"
---
# <a name="what-are-app-protection-policies"></a>Uygulama koruma ilkeleri nelerdir?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune uygulama koruma ilkeleri, şirket verilerinizi korumaya ve veri kaybını önlemeye yardımcı olur.

## <a name="how-you-can-protect-app-data"></a>Uygulama verilerinizi nasıl koruyabilirsiniz?
Çalışanlarınız hem kişisel hem de iş amaçlı görevler için mobil cihazlar kullanır. Bir yandan çalışanlarınızın üretken olmasını sağlarken diğer yandan, isteyerek ve istemeyerek yaşanabilecek veri kayıplarını önlemek isteyebilirsiniz. Ayrıca sizin yönetiminizde olmayan cihazlardan erişilen şirket verilerini de korumak istersiniz.

Intune uygulama koruma ilkelerini **mobil cihaz yönetimi (MDM) çözümlerinden bağımsız olarak** kullanabilirsiniz. Bu bağımsız kullanım imkanı, bir cihaz yönetim çözümüne dahil ettiğiniz ve etmediğiniz cihazlarda şirketinizin verilerini korumanıza yardımcı olur. **Uygulama düzeyinde ilkeler** uygulayarak, şirket kaynaklarına erişimi kısıtlayabilir ve verileri BT departmanınızın kapsamında tutabilirsiniz.

Aşağıdaki özelliklere sahip cihazlarda çalıştırılan uygulamalar için uygulama koruma ilkeleri yapılandırılabilir:

- **Microsoft Intune'a kayıtlı:** Bu genellikle şirket aygıtlardır ait.

- **Bir üçüncü taraf mobil cihaz Yönetimi (MDM) çözümde kayıtlı:** Bu genellikle şirket aygıtlardır ait.

  > [!NOTE]
  > Mobil uygulama yönetimi ilkeleri, üçüncü taraf mobil uygulama yönetimi veya güvenli kapsayıcı çözümleri ile birlikte kullanılmamalıdır.

- **Herhangi bir mobil cihaz yönetim çözümüne kayıtlı değil:** Normalde Intune veya diğer MDM çözümlerinde kayıtlı veya yönetilen çalışana ait cihazlardır.

> [!IMPORTANT]
> Office 365 hizmetlerine bağlanan Office mobil uygulamaları için mobil uygulama yönetimi ilkeleri oluşturabilirsiniz. iOS ve Android için Outlook'a yönelik olarak karma Modern Kimlik Doğrulaması ile etkinleştirilen Intune uygulama koruma ilkeleri oluşturarak Exchange şirket içi posta kutularına erişimi de koruyabilirsiniz. Bu özelliği kullanmadan önce [iOS ve Android için Outlook gereksinimlerini](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) karşıladığınızdan emin olun. Uygulama koruma ilkeleri, şirket içi Exchange veya SharePoint hizmetlerine bağlanan diğer uygulamalar için desteklenmez.

**Uygulama koruma ilkelerini kullanmanın önemli avantajları şunlardır:**:

-   Şirket verilerinizi uygulama düzeyinde koruma. Mobil uygulama yönetimi, cihaz yönetimi gerektirmediği için şirket verilerini hem yönetilen hem de yönetilmeyen cihazlarda koruyabilirsiniz. Yönetim, kullanıcı kimliğine odaklandığından cihaz yönetimine gerek kalmaz.

-   Son kullanıcının üretkenliği etkilenmez ve uygulama kişisel bağlamda kullanılırken ilkeler uygulanmaz. İlkeler yalnızca iş bağlamında uygulanır; bu da size şirket verilerini kişisel verilere dokunmadan koruma olanağı tanır.

MDM'yi Uygulama koruma ilkeleriyle kullanmanın başka avantajları da vardır ve şirketler Uygulama koruma ilkelerini aynı anda hem MDM'li hem de MDM'siz olarak kullanabilir. Hem şirket telefonunu hem de kendine ait olan tableti kullanan bir çalışanı düşünün. Şirket telefonu MDM’ye kaydedilir ve Uygulama koruma ilkeleriyle korunur. Kişisel cihaz ise yalnızca Uygulama koruma ilkeleriyle korunur.

- **MDM, cihazın korunmasını sağlar**. Örneğin, cihaza erişim için PIN’i zorunlu kılabilir veya yönetilen uygulamaları cihaza dağıtabilirsiniz. Ayrıca, uygulama yönetimi üzerinde daha fazla denetime sahip olmak için uygulamaları MDM çözümünüz aracılığıyla cihazlara dağıtabilirsiniz.

- **Uygulama koruma ilkeleri, uygulama katmanındaki korumaların devrede olmasını sağlar**. Örneğin, şunları yapabilirsiniz:
  - Bir uygulamanın iş bağlamında açılması için PIN isteyebilirsiniz 
  - Uygulamalar arasındaki veri paylaşımını denetleyebilirsiniz 
  - Şirket uygulaması verilerinin kişisel depolama konumuna kaydedilmesini önleyebilirsiniz


### <a name="supported-platforms-for-app-protection-policies"></a>Uygulama koruma ilkeleri için desteklenen platformlar
Intune uygulama koruma ilkeleri platformu desteği, Android ve iOS cihazlar için Office mobil uygulama platformu desteği ile hizalar. Ayrıntılar için [Office Sistem Gereksinimleri](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg)'nin **Mobil uygulamalar** bölümüne bakın.

> [!IMPORTANT]
> Intune Şirket portalı, cihazda, Android uygulama koruma ilkelerini almak için gereklidir. Daha fazla bilgi için [Intune Şirket portalı erişim uygulama gereksinimleri](end-user-mam-apps-android.md#access-apps).

## <a name="how-app-protection-policies-protect-app-data"></a>Uygulama koruma ilkeleri uygulama verilerini nasıl korur

#### <a name="apps-without-app-protection-policies"></a>Uygulama koruma ilkelerinin bulunmadığı uygulamalar

![Yerinde hiçbir ilkelerine sahip uygulamalar arasında veri taşıma için kavramsal resmi](./media/apps-without-protection-policies.png)

Uygulamalar kısıtlama olmadan kullanıldığında, şirket verileri ile kişisel veriler birbirine karışabilir. Şirket verileri, kişisel depolama alanı gibi konumlara düşebilir veya kapsamınızın ötesindeki uygulamalara aktarılarak veri kaybına neden olabilir. Yukarıda şemada yer alan oklar, kurumsal ve kişisel uygulamalar arasındaki ve depolama konumlarına yönelik kısıtlanmamış veri hareketlerini gösterir.


### <a name="data-protection-with-app-protection-policies"></a>Uygulama koruma ilkeleriyle verileri koruma

![İlkeleri tarafından korunan şirket verilerini gösteren kavramsal resim](./media/apps-with-protection-policies.png)


Uygulama koruma ilkelerini kullanarak şirket verilerinin cihazın yerel depolama alanına kaydedilmesini engelleyebilirsiniz. Ayrıca Uygulama koruma ilkesi kapsamında olmayan diğer uygulamalara veri taşımayı da kısıtlayabilirsiniz. Uygulama koruma ilkesi ayarları aşağıdakileri içerir:
- **Farklı Kaydetmeyi Engelle**, **Kesme, kopyalama ve yapıştırma işlemlerini kısıtla** gibi veri yeri değiştirme ilkeleri.
- **Erişim için basit PIN gerektir**, **Yönetilen uygulamaların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** gibi erişim ilkesi ayarları.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mobile-device-management-solution"></a>Bir Mobil Cihaz Yönetimi çözümüyle yönetilen cihazlarda uygulama koruma ilkeleriyle veri koruması

![Uygulama koruma ilkelerinin KCG cihazlarında nasıl çalıştığını gösteren resim](./media/app-protection-policies-with-mdm.png)

**Bir MDM çözümüne kaydedilen cihazlar için**-

Yukarıdaki çizimde, MDM ve Uygulama koruma ilkelerinin birlikte sunduğu koruma katmanları gösterilir.

MDM çözümü:

-   Cihazı kaydeder

-   Uygulamaları cihaza dağıtır

-   Sürekli cihaz uyumluluğu ve yönetimi sağlar

**Uygulama koruma ilkeleri, aşağıdaki nedenlerle değer ekler:**

-   Şirket verilerinin tüketici uygulamalarına ve hizmetlerini sızmasını önlemeye yardımcı olma

-   İstemci uygulamalara *farklı kaydetme*, *pano* veya *PIN* gibi kısıtlamalar uygulama

-   Uygulamaları cihazdan kaldırmadan şirket verilerini uygulamalardan silme


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Kaydolmamış cihazlar için uygulama koruma ilkeleriyle veri koruması

![Uygulama koruma ilkelerinin yönetilen cihazlarda nasıl çalıştığını gösteren resim](./media/app-protection-policies-without-mdm.png)

Önceki şemada, veri koruma ilkelerinin uygulama düzeyinde MDM'siz nasıl çalıştığı gösterilmektedir.

Herhangi bir MDM çözümüne kayıtlı olmayan KCG cihazlarında, Uygulama koruma ilkeleri şirket verilerinin uygulama düzeyinde korunmasına yardımcı olabilir.
Ancak, dikkat edilmesi gereken bazı sınırlamalar vardır, örneğin:

-   Cihaza uygulama dağıtamazsınız. Son kullanıcı, uygulamaları mağazadan almak zorundadır.

-   Bu cihazlarda sertifika profilleri sağlayamazsınız.

-   Bu cihazlarda şirket Wi-Fi ve VPN ayarlarını sağlayamazsınız.

## <a name="app-protection-global-policy"></a>Uygulama koruma genel ilkesi

Bir OneDrive yöneticisi **admin.office.com** adresine gidip **Cihaz** erişimini seçtiğinde **Mobil uygulama yönetimi** denetimlerini OneDrive ve SharePoint istemci uygulamalarında ayarlayabilir. 

OneDrive Admin konsolundan bulunabilecek ayarlar **Genel** ilke olarak adlandırılan özel bir Intune uygulama koruma ilkesini yapılandırır. Bu genel ilke kiracınızdaki tüm kullanıcılar için geçerlidir ve ilkenin uygulanacağı nesneleri seçmenin bir yolu yoktur. 

Etkinleştirildikten sonra iOS ve Android için OneDrive ve SharePoint uygulamaları varsayılan olarak seçilen ayarlar tarafından korunur. Bir BT uzmanı bu ilkeyi Intune konsolunda düzenleyebilir ve hedeflenen başka uygulamalar ekleyebilir ve herhangi bir ilke ayarını değiştirebilir. 

Varsayılan olarak kiracı başına yalnızca bir **Genel** ilke olabilir. Ancak kiracı başına fazladan genel ilkeler oluşturmak için [Intune Grafik API'leri](intune-graph-apis.md) kullanılabilirse de bu önerilmez. Fazladan genel ilkeler oluşturmak, böyle bir ilkenin uygulanmasındaki sorunları gidermek karmaşık hale gelebileceği için önerilmez.

**Genel** ilke kiracınızdaki tüm kullanıcılar için geçerli olsa da herhangi bir standart Intune uygulama koruma ilkesi bu ayarları geçersiz kılabilir.


## <a name="multi-identity"></a>Çoklu kimlik

Uygulama koruma ilkeleri uygulamalar yalnızca iş bağlamında kullanılırken uygulanırken, birden çok kimliği destekleyen uygulamalar aynı uygulamalara erişmek için farklı hesaplar (iş ve kişisel) kullanmanıza izin verir.

Yeni bir belge Word'de başlatan bir kullanıcı bir kişisel bağlam örneğini düşünün için Intune uygulama koruma ilkeleri uygulanmaz şekilde bu kişisel bağlam kabul edilir. Sonra şirket OneDrive hesabı Belge kaydedildikten sonra kurumsal bağlam kabul edilir ve Intune uygulama koruma ilkeleri uygulanır.

İş bağlamı bir örneği için kendi iş hesabını kullanarak OneDrive uygulamasını başlatan kullanıcı göz önünde bulundurun. Bu kullanıcı iş bağlamında dosyaları kişisel depolama alanına taşıyamaz. Daha sonra OneDrive'ı kendi kişisel hesabıyla kullandığında, kişisel OneDrive'ından kısıtlamasız olarak veri kopyalayabilir ve taşıyabilir.

- Intune ile [MAM ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)

## <a name="see-also"></a>Ayrıca bkz.
Salesforce mobil uygulaması gibi üçüncü taraf uygulamalar, Intune ile özel şekillerde çalışarak şirket verilerini korur. Doğrudan Salesforce uygulamasının Intune ile nasıl çalıştığını (MDM uygulama yapılandırma ayarları dahil) öğrenmek için bkz. [Salesforce Uygulaması ve Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
