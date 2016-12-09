---
title: MAM ilkelerini kullanarak uygulama verilerini koruma | Microsoft Intune
description: "Bu konu başlığı altında, mobil uygulama yönetimi ilkelerinin şirket verilerinizi korumaya, veri kaybını önlemeye ve kişisel bilgilerle iş bilgilerini birbirinden ayırmaya nasıl yardımcı olabileceği açıklanmaktadır."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 66a5814ba34f9fd15460512b0a6d40566ec33401


---

# <a name="protect-app-data-using-mobile-application-management-policies-with-microsoft-intune"></a>Microsoft Intune ile mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma

## <a name="how-you-can-protect-app-data"></a>Uygulama verilerinizi nasıl koruyabilirsiniz?
Çalışanlarınız hem kişisel hem de iş amaçlı görevler için mobil cihazlar kullanır. Bir yandan çalışanlarınızın üretken olmasını sağlarken diğer yandan, isteyerek ve istemeyerek yaşanabilecek veri kayıplarını da önlemek istersiniz.  Ayrıca, çalışanların yönetmediğiniz cihazları kullanarak eriştiği şirket verilerini de koruyabilmek istersiniz.

Şirketinizin verilerini korumaya yardımcı olmak için Intune mobil uygulama yönetimi (MAM) ilkelerini kullanabilirsiniz. Intune MAM ilkeleri, **herhangi bir mobil cihaz yönetimi (MDM) çözümünden bağımsız olarak** kullanılabildiğinden, MAM'ı şirketinizin verilerini cihazları bir cihaz yönetimi çözümüne kaydederek veya kaydetmeden korumak üzere kullanabilirsiniz. **Uygulama düzeyinde ilkeler** uygulayarak, şirket kaynaklarına erişimi kısıtlayabilir ve verileri BT departmanınızın kapsamında tutabilirsiniz.

Aşağıdaki özelliklere sahip cihazlarda çalışan uygulamalar için MAM ilkeleri yapılandırabilirsiniz:

-   **Microsoft Intune'a kayıtlı:** Bu kategorideki cihazlar normalde şirkete ait cihazlardır.

-   **Üçüncü taraf bir MDM çözümüne kayıtlı:** Bu kategorideki cihazlar normalde şirkete ait cihazlardır.

  > [!NOTE]
  > Üçüncü taraf mobil uygulama yönetimi veya güvenli kapsayıcı çözümleri ile MAM ilkelerinin kullanılması önerilmez.

-   **Herhangi bir MDM çözümüne kayıtlı değil:** Bu kategorideki cihazlar, normalde Intune veya diğer MDM çözümleriyle yönetilmeyen veya bunlara kayıtlı olmayan, çalışana ait cihazlardır.

> [!IMPORTANT]
> Office 365 hizmetlerine bağlanan Office mobil uygulamaları için mobil uygulama yönetimi ilkeleri oluşturabilirsiniz. MAM ilkeleri, şirket içi Exchange, Skype Kurumsal veya SharePoint hizmetlerine bağlanan uygulamalar için desteklenmez.

## <a name="benefits-of-using-mam-policies"></a>MAM ilkeleri kullanmanın avantajları

-   **Şirket verilerinizi uygulama düzeyinde korumanıza yardımcı olurlar.** Mobil uygulama yönetimi, cihaz yönetimi gerektirmediği için şirket verilerini hem yönetilen hem de yönetilmeyen cihazlarda koruyabilirsiniz. Yönetim, kullanıcı kimliğine odaklandığından cihaz yönetimine gerek kalmaz.

-   **Kullanıcının üretkenliği etkilenmez ve uygulama kişisel bağlamda kullanılırken ilkeler uygulanmaz.** İlkeler yalnızca iş bağlamında uygulanır; bu da size şirket verilerini kişisel verilere dokunmadan koruma olanağı tanır.

MDM'yi MAM ilkeleriyle kullanmanın başka avantajları da vardır ve şirketler MAM'ı aynı anda MDM'li ve MDM'siz olarak kullanabilir. Örneğin bir çalışan, kişisel tabletin yanı sıra şirkete ait bir telefonu kullanabilir. Bu durumda, şirket telefonu MDM’ye kaydedilir ve MAM ilkeleriyle korunur. Kişisel cihaz ise yalnızca MAM ilkeleriyle korunur.

- **MDM, cihazın korunmasını sağlar.** Örneğin, cihaza erişim için PIN’i zorunlu kılabilir veya yönetilen uygulamaları cihaza dağıtabilirsiniz. Ayrıca, uygulama yönetimi üzerinde daha fazla denetime sahip olmak için MDM çözümünüz aracılığıyla cihazlara uygulama dağıtabilirsiniz.

- **MAM ilkeleri, uygulama katmanındaki korumaların devrede olmasını sağlar.** Örneğin, bir uygulamanın iş bağlamında açılması için PIN gerektiren, uygulamalar arasında veri paylaşılmasını engelleyen ve şirket uygulama verilerinin kişisel bir depolama konumuna kaydedilmesini engelleyen bir ilkeniz olabilir.

## <a name="devices-that-support-mam"></a>MAM'ı destekleyen cihazlar
MAM ilkeleri şu anda aşağıdakilerde desteklenmektedir:
-   iOS 8.1 veya üzeri
-   Android 4 veya üzeri

Windows cihazları şu anda desteklenmez.
##  <a name="how-mam-policies-protect-app-data"></a>MAM ilkeleri, uygulama verilerini nasıl korur?

###  <a name="apps-without-mam-policies"></a>MAM ilkeleri olmayan uygulamalar

![MAM ilkeleri devrede olmadığında verilerin uygulamalar arasında nasıl serbestçe taşınabildiğini gösteren resim](../media/Apps_without_MAM_policies.png)

Uygulamaları kısıtlamasız kullandığınızda, şirket verileri ve kişisel veriler birbirine karışabilir. Şirket verileri kişisel depolama alanlarına konabilir veya denetiminiz dışında uygulamalara aktarılabilir ve bunlar veri kaybına neden olabilir. Şemadaki oklar, uygulamalar arasındaki (şirket ve kişisel) ve depolama konumlarına yönelik kısıtlanmamış veri hareketlerini gösterir.

### <a name="data-protection-with-mam-policies"></a>MAM ilkeleriyle veri koruma

![MAM ilkeleri uygulandığında şirket verilerinin nasıl korunduğunu gösteren resim](../media/Apps_with_mobile_app_policies.png)

MAM ilkelerini, şirket verilerinin cihazın yerel depolama birimine kaydedilmesini önlemek ve MAM ilkeleriyle korunmayan diğer uygulamalara veri taşınmasını kısıtlamak için kullanabilirsiniz. MAM ilkesi ayarları aşağıdakileri içerir:
- **Farklı Kaydetmeyi Engelle**, **Kesme, kopyalama ve yapıştırma işlemlerini kısıtla** gibi veri yeri değiştirme ilkeleri.
- **Erişim için basit PIN gerektir**, **Yönetilen uygulamaların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** gibi erişim ilkesi ayarları.

### <a name="data-protection-with-mam-policies-on-devices-that-are-managed-by-a-mdm-solution"></a>MDM çözümüyle yönetilen cihazlarda MAM ilkeleriyle veri koruması

![Kendi Cihazını Getir (KCG) cihazlarında MAM ilkelerinin nasıl çalıştığını gösteren görüntü](../media/MAM_BYOD_November.png)

**Bir MDM çözümüne kayıtlı cihazlarda**: Önceki şemada MDM ve MAM ilkelerinin birlikte sunduğu koruma katmanları gösterilmektedir.

MDM çözümü:

-   Cihazı kaydeder.

-   Cihaza uygulama dağıtır.

-   Sürekli cihaz uyumluluğu ve yönetimi sağlar.

**MAM ilkeleri, aşağıdaki nedenlerle değer ekler:**

-   Şirket verilerinin tüketici uygulama ve hizmetlerine sızmasını önlemeye yardımcı olma.

-   Mobil uygulamalara kısıtlamalar (farklı kaydet, pano, PIN vs.) uygulama.

-   Uygulamaları cihazdan kaldırmadan şirket verilerini uygulamalardan silme.


### <a name="data-protection-with-mam-policies-for-devices-without-enrollment"></a>Kaydolmamış cihazlar için MAM ilkeleriyle veri koruması

![MAM ilkelerinin yönetilen cihazlarda nasıl çalıştığını gösteren resim](../media/MAM_ManagedDevices_November.png)

Önceki şemada, veri koruma ilkelerinin uygulama düzeyinde MDM'siz nasıl çalıştığı gösterilmektedir.

Herhangi bir MDM çözümüne kayıtlı olmayan KCG cihazlarında, MAM ilkeleri, şirket verilerinin uygulama düzeyinde korunmasına yardımcı olabilir.

Ancak dikkat edilmesi gereken bazı sınırlamalar vardır:

-   Cihaza uygulama dağıtamazsınız. Kullanıcı, uygulamaları mağazadan almak zorundadır.

-   Bu cihazlarda sertifika profilleri sağlayamazsınız.

-   Bu cihazlarda şirket Wi-Fi ve VPN ayarları yapamazsınız.


## <a name="multi-identity"></a>Çoklu kimlik

MAM ilkeleri yalnızca iş bağlamında kullanılan uygulamalara uygulanırken, birden çok kimliği destekleyen uygulamalar aynı uygulamalara erişmek için farklı hesaplar (iş ve kişisel) kullanmanıza izin verir.  

Örneğin, bir kullanıcı OneDrive uygulamasını iş hesabını kullanarak başlattığında, kişisel bir depolama konumuna dosya taşıyamaz. Ancak OneDrive'ı kendi kişisel hesabıyla kullandığında, kişisel OneDrive'ından kısıtlamasız olarak veri kopyalayabilir ve taşıyabilir.  

Tüm Office mobil uygulamaları birden çok kimlikle erişimi destekler.

##  <a name="next-steps"></a>Sonraki adımlar
- [Mobil uygulama yönetim ilkelerini yapılandırmaya hazırlanma](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Microsoft Intune ile mobil uygulama yönetim ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


