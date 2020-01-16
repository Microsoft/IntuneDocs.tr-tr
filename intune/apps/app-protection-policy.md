---
title: Uygulama koruma ilkelerine genel bakış
titleSuffix: Microsoft Intune
description: Microsoft Intune uygulama koruma ilkelerinin, şirket verilerinizi korumaya ve veri kaybını önlemeye nasıl yardımcı olduğunu öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3c340ffaacad303c4ff395c84d92e3907e42a521
ms.sourcegitcommit: 52475fcd8d05d2f6b858d780ebb3d88eaadb0849
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2020
ms.locfileid: "76036639"
---
# <a name="app-protection-policies-overview"></a>Uygulama koruma ilkelerine genel bakış

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Uygulama koruma ilkeleri (uygulama), bir kuruluşun verilerinin güvenli kalmasını veya yönetilen bir uygulamada yer aldığından emin olmanızı sağlayan kurallardır. İlke, kullanıcı “kurumsal” verilere erişmeye veya bunları taşımaya çalıştığında uygulanan bir kural veya kullanıcı uygulamadayken yasaklanan veya izlenen bir eylemler kümesi olabilir. Yönetilen bir uygulama, uygulama koruma ilkelerinin uygulandığı ve Intune tarafından yönetilebilen bir uygulamadır.

Mobil uygulama yönetimi (MAM) uygulama koruma ilkeleri, kuruluşunuzun verilerini bir uygulama içinde yönetmenizi ve korumanızı sağlar. **Kayıt olmadan mam** (mam-we) ile, hassas veriler içeren iş veya okul ile ilgili bir uygulama, **kendi cihazını getir** (KCG) senaryolarında kişisel cihazlar dahil olmak üzere neredeyse her [cihazda](app-management.md#app-management-capabilities-by-platform)yönetilebilir. Microsoft Office uygulamaları gibi birçok üretkenlik uygulaması Intune MAM tarafından yönetilebilir. Genel kullanıma sunulan [Microsoft Intune korunan uygulamaların](apps-supported-intune-apps.md) resmi listesine bakın.

## <a name="how-you-can-protect-app-data"></a>Uygulama verilerinizi nasıl koruyabilirsiniz?
Çalışanlarınız hem kişisel hem de iş amaçlı görevler için mobil cihazlar kullanır. Bir yandan çalışanlarınızın üretken olmasını sağlarken diğer yandan, isteyerek ve istemeyerek yaşanabilecek veri kayıplarını önlemek isteyebilirsiniz. Ayrıca sizin yönetiminizde olmayan cihazlardan erişilen şirket verilerini de korumak istersiniz.

Intune uygulama koruma ilkelerini **mobil cihaz yönetimi (MDM) çözümlerinden bağımsız olarak** kullanabilirsiniz. Bu bağımsız kullanım imkanı, bir cihaz yönetim çözümüne dahil ettiğiniz ve etmediğiniz cihazlarda şirketinizin verilerini korumanıza yardımcı olur. **Uygulama düzeyinde ilkeler** uygulayarak, şirket kaynaklarına erişimi kısıtlayabilir ve verileri BT departmanınızın kapsamında tutabilirsiniz.

### <a name="app-protection-policies-on-devices"></a>Cihazlarda uygulama koruma ilkeleri

Aşağıdaki özelliklere sahip cihazlarda çalıştırılan uygulamalar için uygulama koruma ilkeleri yapılandırılabilir:

- **Microsoft Intune’a kayıtlı:** Bu cihazlar genellikle şirkete aittir.

- **Bir üçüncü taraf mobil cihaz Yönetimi (MDM) çözümde kayıtlı:** Bu cihazlar genellikle şirkete aittir.

  > [!NOTE]
  > Mobil uygulama yönetimi ilkeleri, üçüncü taraf mobil uygulama yönetimi veya güvenli kapsayıcı çözümleri ile birlikte kullanılmamalıdır.

- **Herhangi bir mobil cihaz yönetimi çözümüne kayıtlı değil:** Bu cihazlar genellikle, Intune veya diğer MDM çözümlerinde yönetilmeyen veya kayıtlı olmayan, çalışana ait cihazlardır.

> [!IMPORTANT]
> Office 365 hizmetlerine bağlanan Office mobil uygulamaları için mobil uygulama yönetimi ilkeleri oluşturabilirsiniz. iOS ve Android için Outlook'a yönelik olarak karma Modern Kimlik Doğrulaması ile etkinleştirilen Intune uygulama koruma ilkeleri oluşturarak Exchange şirket içi posta kutularına erişimi de koruyabilirsiniz. Bu özelliği kullanmadan önce [iOS ve Android için Outlook gereksinimlerini](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) karşıladığınızdan emin olun. Uygulama koruma ilkeleri, şirket içi Exchange veya SharePoint hizmetlerine bağlanan diğer uygulamalar için desteklenmez.

## <a name="benefits-of-using-app-protection-policies"></a>Uygulama koruma ilkelerini kullanmanın avantajları

Uygulama koruma ilkelerini kullanmanın önemli avantajları şunlardır:

- **Şirket verilerinizi uygulama düzeyinde koruma.** Mobil uygulama yönetimi, cihaz yönetimi gerektirmediği için şirket verilerini hem yönetilen hem de yönetilmeyen cihazlarda koruyabilirsiniz. Yönetim, kullanıcı kimliğine odaklandığından cihaz yönetimine gerek kalmaz.

- **Son Kullanıcı üretkenliği etkilenmez ve uygulama kişisel bağlamda kullanılırken ilkeler uygulanmaz.** İlkeler yalnızca iş bağlamında uygulanır; bu da size şirket verilerini kişisel verilere dokunmadan koruma olanağı tanır.

- **Uygulama koruma ilkeleri, uygulama katmanı korumalarının yerinde olmasını sağlar.** Örneğin, şunları yapabilirsiniz:
  - Bir uygulamanın iş bağlamında açılması için PIN isteyebilirsiniz 
  - Uygulamalar arasındaki veri paylaşımını denetleyebilirsiniz 
  - Şirket uygulaması verilerinin kişisel depolama konumuna kaydedilmesini önleyebilirsiniz

- **MDM, mam 'e ek olarak cihazın korunduğundan emin olmanızı sağlar**. Örneğin, cihaza erişim için PIN’i zorunlu kılabilir veya yönetilen uygulamaları cihaza dağıtabilirsiniz. Ayrıca, uygulama yönetimi üzerinde daha fazla denetime sahip olmak için uygulamaları MDM çözümünüz aracılığıyla cihazlara dağıtabilirsiniz.

MDM'yi Uygulama koruma ilkeleriyle kullanmanın başka avantajları da vardır ve şirketler Uygulama koruma ilkelerini aynı anda hem MDM'li hem de MDM'siz olarak kullanabilir. Hem şirket telefonunu hem de kendine ait olan tableti kullanan bir çalışanı düşünün. Şirket telefonu MDM’ye kaydedilir ve Uygulama koruma ilkeleriyle korunur. Kişisel cihaz ise yalnızca Uygulama koruma ilkeleriyle korunur.

Kullanıcıya cihaz durumunu ayarlamadan bir MAM ilkesi uygularsanız, Kullanıcı hem KCG cihazında hem de Intune tarafından yönetilen cihazda MAM ilkesini alır. Yönetilen duruma göre bir MAM ilkesi de uygulayabilirsiniz. Bu nedenle, bir uygulama koruma ilkesi oluşturduğunuzda, **hedefi tüm uygulama türleri**' nin yanında **Hayır**' ı seçin. Ardından aşağıdakilerden birini yapın:
- Intune tarafından yönetilen cihazlara daha az sıkı bir MAM ilkesi uygulayın ve MDM 'ye kayıtlı olmayan cihazlara daha kısıtlayıcı bir MAM ilkesi uygulayın.
- Yalnızca kaydı silinen cihazlara bir MAM ilkesi uygulayın.

## <a name="supported-platforms-for-app-protection-policies"></a>Uygulama koruma ilkeleri için desteklenen platformlar

Intune, ihtiyacınız olan uygulamaları çalıştırmak istediğiniz cihazlara almanıza yardımcı olacak çeşitli özellikler sunar. Daha fazla bilgi için bkz. [platforma göre uygulama yönetimi özellikleri](app-management.md#app-management-capabilities-by-platform).

Intune uygulama koruma ilkeleri platformu desteği, Android ve iOS cihazlar için Office mobil uygulama platformu desteği ile uyumludur. Ayrıntılar için [Office Sistem Gereksinimleri](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg)'nin **Mobil uygulamalar** bölümüne bakın.

> [!IMPORTANT]
> Android cihazlarda Uygulama Koruma İlkelerini almak için Intune Şirket Portalı gereklidir. Daha fazla bilgi için bkz. [Intune Şirket Portalı uygulama erişim gereksinimleri](../fundamentals/end-user-mam-apps-android.md#access-apps).

## <a name="how-app-protection-policies-protect-app-data"></a>Uygulama koruma ilkeleri uygulama verilerini nasıl korur

### <a name="apps-without-app-protection-policies"></a>Uygulama koruma ilkelerinin bulunmadığı uygulamalar

Uygulamalar kısıtlama olmadan kullanıldığında, şirket verileri ile kişisel veriler birbirine karışabilir. Şirket verileri, kişisel depolama alanı gibi konumlara düşebilir veya kapsamınızın ötesindeki uygulamalara aktarılarak veri kaybına neden olabilir. Aşağıdaki diyagramdaki oklar, hem şirket hem de kişisel uygulamalar ve depolama konumları arasında Kısıtlanmamış veri hareketini gösterir.

![İlke olmadan uygulama arasındaki veri hareketini gösteren kavramsal görüntü](./media/app-protection-policy/apps-without-protection-policies.png)

### <a name="data-protection-with-app-protection-policies-app"></a>Uygulama koruma ilkeleriyle veri koruma (uygulama)

Şirket verilerinin cihazın yerel depolama alanına kaydedilmesini engellemek için uygulama koruma ilkelerini kullanabilirsiniz (aşağıdaki resme bakın). Ayrıca Uygulama koruma ilkesi kapsamında olmayan diğer uygulamalara veri taşımayı da kısıtlayabilirsiniz. Uygulama koruma ilkesi ayarları aşağıdakileri içerir:
- **Kuruluş verilerinin kopyalarını kaydetme**ve **kesme, kopyalama ve yapıştırmayı kısıtlama**gibi veri konumu değiştirme ilkeleri.
- **Erişim için basit PIN gerektir**, **Yönetilen uygulamaların, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engelle** gibi erişim ilkesi ayarları.

![İlkelere tarafından korunan şirket verilerini gösteren kavramsal görüntü](./media/app-protection-policy/apps-with-protection-policies.png)

### <a name="data-protection-with-app-on-devices-managed-by-an-mdm-solution"></a>MDM çözümü tarafından yönetilen cihazlarda uygulamayla veri koruma

Aşağıdaki çizimde, MDM ve uygulama koruma ilkelerinin birlikte sunduğu koruma katmanları gösterilmektedir.

![Uygulama koruma ilkelerinin KCG cihazlarında nasıl çalıştığını gösteren resim](./media/app-protection-policy/app-protection-policies-with-mdm.png)

MDM çözümü, aşağıdakileri sağlayarak değer ekler:

- Cihazı kaydeder
- Uygulamaları cihaza dağıtır
- Sürekli cihaz uyumluluğu ve yönetimi sağlar

Uygulama koruma ilkeleri, aşağıdakileri sağlayarak değer ekler:

- Şirket verilerinin tüketici uygulamalarına ve hizmetlerine sızmasını korumaya yardımcı olma
- İstemci uygulamalarına *kaydetme*, *Pano*veya *PIN*gibi kısıtlamalar uygulama
- Bu uygulamaları cihazdan kaldırmadan, uygulamalardan gerektiğinde şirket verilerini silme

### <a name="data-protection-with-app-for-devices-without-enrollment"></a>Kayıt olmadan cihazlar için uygulamayla veri koruma

Aşağıdaki diyagramda, veri koruma ilkelerinin uygulama düzeyinde MDM olmadan nasıl çalıştığı gösterilmektedir.

![Uygulama koruma ilkelerinin kayıt olmadan cihazlarda nasıl çalıştığını gösteren resim (yönetilmeyen cihazlar)](./media/app-protection-policy/app-protection-policies-without-mdm.png)

Herhangi bir MDM çözümüne kayıtlı olmayan KCG cihazlarında, Uygulama koruma ilkeleri şirket verilerinin uygulama düzeyinde korunmasına yardımcı olabilir.
Bununla birlikte, dikkat edilecek bazı sınırlamalar vardır, örneğin:

- Cihaza uygulama dağıtamazsınız. Son kullanıcı, uygulamaları mağazadan almak zorundadır.
- Bu cihazlarda sertifika profilleri sağlayamazsınız.
- Bu cihazlarda şirket Wi-Fi ve VPN ayarlarını sağlayamazsınız.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Uygulama koruma ilkeleri ile yönetebileceğiniz uygulamalar

Intune [SDK](../developer/app-sdk.md) ile tümleştirilmiş veya [Intune uygulama sarmalama aracı](../developer/apps-prepare-mobile-application-management.md) tarafından Sarmalanan tüm uygulamalar, Intune uygulama koruma ilkeleri kullanılarak yönetilebilir. Bu araçlar kullanılarak oluşturulan ve genel kullanıma açık olan [Microsoft Intune korunan uygulamaların](apps-supported-intune-apps.md) resmi listesine bakın.

Intune SDK geliştirme ekibi etkin bir şekilde sınar ve yerel Android, iOS (obj-C, Swift), Xamarin, Xamarin. Forms ve Cordova platformlarıyla oluşturulmuş uygulamalar için destek sağlar. Bazı müşteriler, bir Kullanıcı ve NativeScript gibi diğer platformlarla Intune SDK tümleştirmesi ile başarılı olmuş olsa da, desteklenen platformlarımızdan başka herhangi bir şeyi kullanarak uygulama geliştiricileri için açık rehberlik veya eklentiler sağlamayız.

[INTUNE SDK](../developer/app-sdk.md) 'sı, hem 1. taraf hem de SDK 'nın 3. taraf sürümleri Için[Azure Active Directory kimlik doğrulama kitaplıklarından](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) gelişmiş modern kimlik doğrulama özellikleri kullanır. Bu nedenle, [Microsoft kimlik doğrulama kitaplığı](https://docs.microsoft.com/azure/active-directory/develop/reference-v2-libraries) (msal), Intune uygulama koruması hizmetinde kimlik doğrulaması ve koşullu başlatma gibi temel senaryolarımızda iyi çalışmaz. Microsoft 'un kimlik ekibinin tüm Microsoft Office uygulamalar için MSAL 'e geçiş yapması, [Intune SDK 'sının](../developer/app-sdk.md) bu uygulamayı desteklemesi gerekir, ancak bugün bir plan yoktur.

## <a name="end-user-requirements-to-use-app-protection-policies"></a>Uygulama koruma ilkelerini kullanmak için son kullanıcı gereksinimleri

Aşağıdaki listede, Intune tarafından yönetilen bir uygulamada uygulama koruma ilkelerini kullanmak için son kullanıcı gereksinimleri verilmiştir:

- Son kullanıcının bir Azure Active Directory (AAD) hesabı olması gerekir. Azure Active Directory’de Intune kullanıcılarını nasıl oluşturacağınızı öğrenmek için [Kullanıcı ekleme ve Intune'a yönetici izni verme](../fundamentals/users-add.md) konusuna bakın.

- Son kullanıcının Azure Active Directory hesabına atanmış bir Microsoft Intune lisansının olması gerekir. Son kullanıcılara Intune lisanslarını nasıl atayacağınızı öğrenmek için [Intune lisanslarını yönetme](../fundamentals/licenses-assign.md) konusuna bakın.

- Son kullanıcı bir uygulama koruma ilkesi tarafından hedeflenen bir güvenlik grubuna ait olmalıdır. Aynı uygulama koruma ilkesi, kullanılan belirli uygulamayı hedeflemelidir. Uygulama koruma ilkeleri [Azure portalındaki](https://portal.azure.com) Intune konsolunda oluşturulabilir ve dağıtılabilir. Güvenlik grupları Şu anda [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)oluşturulabilir.

- Son kullanıcının AAD hesabını kullanarak uygulamada oturum açması gerekir.

## <a name="app-protection-policies-for-microsoft-office-apps"></a>Microsoft Office uygulamalar için uygulama koruma ilkeleri

Uygulama koruma ilkelerini Microsoft Office uygulamalarla kullanırken farkında olmak istediğiniz birkaç ek gereksinim vardır.

### <a name="outlook-mobile-app"></a>Outlook mobil uygulaması
[Outlook Mobile uygulamasını](https://products.office.com/outlook) kullanmak için ek gereksinimler şunlardır:

- Son kullanıcının cihazında Outlook mobil uygulamasının yüklü olması gerekir.
- Son kullanıcının, Azure Active Directory hesabına bağlı bir [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) posta kutusuna ve lisansına sahip olması gerekir.

  >[!NOTE]
  > Outlook mobil uygulaması şu anda yalnızca Microsoft Exchange Online için Intune Uygulama Koruması’nı ve [Hibrit modern kimlik doğrulaması ile Exchange Server](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx)’ı destekler ve Exchange’deki Office 365 Özel’i desteklemez.

### <a name="word-excel-and-powerpoint"></a>Word, Excel ve PowerPoint
[Word, Excel ve PowerPoint](https://products.office.com/business/office) uygulamalarını kullanmak için ek gereksinimler şunlardır:

- Son kullanıcının Azure Active Directory hesabına bağlı bir [Office 365 İş veya Kurumsal](https://products.office.com/business/compare-more-office-365-for-business-plans) lisansına sahip olması gerekir. Aboneliğin mobil cihazlarda Office uygulamalarını içermesi gerekir ve [OneDrive İş](https://onedrive.live.com/about/business/)’te bir bulut depolama hesabını içerebilir. Office 365 lisansları, bu [yönergeleri](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)izleyerek [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com) atanabilir.

- Son kullanıcının, "kuruluş verilerinin kopyalarını Kaydet" uygulama koruma ilkesi ayarının altında parçalı farklı kaydet işlevi kullanılarak yapılandırılmış bir yönetilen konumu olmalıdır. Örneğin, yönetilen konum OneDrive ise [OneDrive](https://onedrive.live.com/about/) uygulaması son kullanıcının Word, Excel veya PowerPoint uygulamasında yapılandırılmalıdır.

- Yönetilen konum OneDrive ise uygulama, son kullanıcıya dağıtılan uygulama koruma ilkesi tarafından hedeflenmelidir.

  >[!NOTE]
  > Office mobil uygulamaları şu anda yalnızca SharePoint Online’ı destekler ve SharePoint şirket içi sürümünü desteklemez.

### <a name="managed-location-needed-for-office"></a>Office için gereken yönetilen konum
Office için yönetilen bir konum (örneğin OneDrive) gereklidir. Intune, uygulamadaki tüm verileri "Şirket" veya "kişisel" olarak işaretler. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Office uygulamaları söz konusu olduğunda Intune, aşağıdakileri iş konumu olarak kabul eder: e-posta (Exchange) veya bulut depolama (OneDrive İş hesabı içeren OneDrive uygulaması).

### <a name="skype-for-business"></a>Skype Kurumsal
Skype Kurumsal 'ı kullanmak için ek gereksinimler vardır. [Skype Kurumsal](https://products.office.com/skype-for-business/it-pros) lisans gereksinimlerine bakın. Skype Kurumsal (SfB) hibrit ve şirket içi yapılandırmaları için bkz. [Skype Kurumsal ve Exchange için Hibrit Modern Kimlik Doğrulaması Genel Kullanıma Sunuldu](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) ve [AAD ile Skype Kurumsal için Modern Kimlik Doğrulaması](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910).

## <a name="app-protection-global-policy"></a>Uygulama koruma genel ilkesi

Bir OneDrive Yöneticisi **admin.OneDrive.com** 'e gözatan **cihaz erişimini**seçerse, **mobil uygulama yönetimi** denetimlerini OneDrive ve SharePoint istemci uygulamalarına ayarlayabilirler. 

OneDrive Admin konsolundan bulunabilecek ayarlar **Genel** ilke olarak adlandırılan özel bir Intune uygulama koruma ilkesini yapılandırır. Bu genel ilke kiracınızdaki tüm kullanıcılar için geçerlidir ve ilkenin uygulanacağı nesneleri seçmenin bir yolu yoktur. 

Etkinleştirildikten sonra iOS ve Android için OneDrive ve SharePoint uygulamaları varsayılan olarak seçilen ayarlar tarafından korunur. Bir BT uzmanı bu ilkeyi Intune konsolunda düzenleyebilir ve hedeflenen başka uygulamalar ekleyebilir ve herhangi bir ilke ayarını değiştirebilir. 

Varsayılan olarak kiracı başına yalnızca bir **Genel** ilke olabilir. Ancak kiracı başına fazladan genel ilkeler oluşturmak için [Intune Grafik API'leri](../developer/intune-graph-apis.md) kullanılabilirse de bu önerilmez. Fazladan genel ilkeler oluşturmak, böyle bir ilkenin uygulanmasındaki sorunları gidermek karmaşık hale gelebileceği için önerilmez.

**Genel** ilke kiracınızdaki tüm kullanıcılar için geçerli olsa da herhangi bir standart Intune uygulama koruma ilkesi bu ayarları geçersiz kılabilir.

## <a name="app-protection-features"></a>Uygulama koruma özellikleri

### <a name="multi-identity"></a>Çoklu kimlik

Çoklu kimlik desteği, bir uygulamanın birden çok kitci desteklemesini sağlar. Bu izleyiciler "Şirket" kullanıcıları ve "kişisel" kullanıcılardır. İş ve okul hesapları "Kurumsal" izleyiciler tarafından kullanılır, ancak kişisel hesaplar, Microsoft Office kullanıcılar gibi tüketici kitleleri için kullanılır. Çoklu kimliği destekleyen bir uygulama, uygulama koruma ilkelerinin yalnızca uygulama iş ve okul ("Kurumsal") bağlamında kullanıldığı zaman uygulandığı herkese açık bir şekilde dağıtılabilir. Çoklu kimlik desteği, [Intune SDK 'sını](../developer/app-sdk.md) yalnızca uygulamada oturum açan iş veya okul hesabına uygulama koruma ilkeleri uygulamak için kullanır. Kişisel bir hesap uygulamada oturum açarsa, verilere koruma uygulanmaz.

"Kişisel" bağlam örneği için, Word 'de yeni bir belge Başlatan bir kullanıcıyı göz önünde bulundurun. Intune Uygulama Koruması İlkeleri uygulanmadığından bu, kişisel bağlam olarak kabul edilir. Belge "Şirket" OneDrive hesabına kaydedildikten sonra, "Kurumsal" içerik olarak kabul edilir ve Intune Uygulama Koruması ilkeleri uygulanır.

İş veya "Kurumsal" bağlam örneği için iş hesabını kullanarak OneDrive uygulamasını Başlatan bir kullanıcıyı göz önünde bulundurun. Bu kullanıcı iş bağlamında dosyaları kişisel depolama alanına taşıyamaz. Daha sonra OneDrive'ı kendi kişisel hesabıyla kullandığında, kişisel OneDrive'ından kısıtlamasız olarak veri kopyalayabilir ve taşıyabilir.

Outlook 'ta "kişisel" ve "Kurumsal" e-postaların birleştirilmiş bir e-posta görünümü vardır. Bu durumda, Outlook uygulaması başlatma sırasında Intune PIN 'ı ister.

Intune 'da çoklu kimlik hakkında daha fazla bilgi için bkz. [mam and Multi-Identity](apps-supported-intune-apps.md).

### <a name="intune-app-pin"></a>Intune uygulama PIN 'ı

Kişisel Kimlik Numarası (PIN), bir uygulamadaki kuruluş verilerine doğru kullanıcının eriştiğini doğrulamak için kullanılan bir paroladır.

**PIN istemi**<br>
Intune, kullanıcının uygulama PIN’ini yalnızca kullanıcı “kurumsal” verilere erişmek üzereyken ister. Word, Excel veya PowerPoint gibi çoklu kimlik uygulamalarında, "Kurumsal" bir belgeyi veya dosyayı açmaya çalıştıklarında kullanıcıdan PIN kodu istenir. [Intune uygulaması sarmalama aracı](../developer/apps-prepare-mobile-application-management.md)kullanılarak yönetilen iş kolu uygulamaları gibi tek kimlikli uygulamalarda, [Intune SDK 'sı](../developer/app-sdk.md) kullanıcının uygulamadaki deneyiminin her zaman "Kurumsal" olduğunu bildiğinden PIN başlatıldığında PIN istenir.

**PIN istemi veya Şirket kimlik bilgileri istemi, sıklık**<br>
BT Yöneticisi, Intune yönetici konsolunda **(dakika) sonra erişim gereksinimlerini yeniden denetle** Intune uygulama koruma ilkesi ayarını tanımlayabilir. Bu ayar, erişim gereksinimlerinin cihazda denetlenme süresini ve uygulama PIN ekranı veya Şirket kimlik bilgileri istemi 'nin yeniden gösterildiğini belirtir. Ancak kullanıcıdan PIN istenme sıklığını etkileyen önemli PIN ayrıntıları şöyledir:

- **PIN, kullanılabilirliği geliştirmek için aynı yayımcının uygulamaları arasında paylaşılır:**<br> İOS 'ta, bir uygulama PIN 'i **aynı uygulama yayımcısının**tüm uygulamaları arasında paylaşılır. Örneğin, tüm Microsoft uygulamaları aynı PIN 'ı paylaşır. Android’de bir uygulama PIN’i tü uygulamalar arasında paylaşılır.
- **Cihaz yeniden başlatıldıktan sonra *erişim gereksinimlerini yeniden denetle (dakika)* davranışı:**<br> Bir zamanlayıcı, Intune uygulama PIN 'inin ne zaman gösterileceğini veya bir sonraki Şirket kimlik bilgisi isteğini belirten işlem yapılmayan dakika sayısını izler. İOS 'ta Zamanlayıcı, cihaz yeniden başlatıldıktan sonra etkilenmez. Bu nedenle, cihazın yeniden başlatılması, kullanıcının Intune PIN (veya Şirket kimlik bilgileri) ilkesiyle hedeflenen bir iOS uygulamasından etkin olmadığı dakika sayısı üzerinde hiçbir etkiye sahip değildir. Android 'de Zamanlayıcı, cihaz yeniden başlatıldığında sıfırlanır. Bu nedenle, Intune PIN (veya Şirket kimlik bilgileri) ilkesi ile Android Uygulamaları, **cihaz yeniden başlatıldıktan sonra**' erişim gereksinimlerini yeniden denetle (dakika) ' ayarından bağımsız olarak BIR uygulama PIN 'i veya Şirket kimlik bilgileri istemi ister.  
- **PIN ile ilişkili zamanlayıcının hareketli yapısı:**<br> Bir uygulamaya (uygulama A) erişmek için bir PIN girildikten sonra uygulama, ön planda (ana giriş odağını), bu PIN için sıfırlanarak kalır. Bu PIN’i paylaşan başka bir uygulama (uygulama B), zamanlayıcı sıfırlandığı için kullanıcıdan PIN girmesini istemeyecektir. “(dakika) sonra erişim gereksinimlerini yeniden denetle” değeri yeniden karşılandığında istem yeniden görüntülenecektir.

iOS cihazlarda PIN, farklı yayımcılardan gelen uygulamalar arasında paylaşılsa bile **(dakika) sonra erişim gereksinimlerini yeniden denetle** süresi geçtikten sonra ana giriş odağı olmayan uygulamada istem yeniden görüntülenir. Yani, örneğin bir kullanıcıda _X_ yayımcısının _A_ uygulaması ve _Y_ yayımcısının _B_ uygulaması varsa bu iki uygulama aynı PIN’i paylaşır. Kullanıcı, _A_ uygulamasına odaklanmıştır (uygulama ön plandadır) ve _B_ uygulaması simge durumuna küçültülmüştür. **(dakika) sonra erişim gereksinimlerini yeniden denetle** süresi geçtikten sonra kullanıcı _B_ uygulamasına geçerse PIN gerekir.

  >[!NOTE]
  > Kullanıcının erişim gereksinimlerini (örneğin PIN istemini) daha sık doğrulamak için “(dakika) sonra erişim gereksinimlerini yeniden denetle” ayarındaki değeri azaltmanız önerilir.

**Outlook ve OneDrive için yerleşik uygulama PIN 'leri**<br>
Intune PIN 'i, etkin olmama tabanlı bir zamanlayıcıya ( **dakika sonra erişim gereksinimlerini yeniden denetle**değeri) göre çalışmaktadır. Bu sebeple Intune PIN istemleri, genelde varsayılan olarak uygulama başlatmasına bağlı olan Outlook ve OneDrive için yerleşik uygulama PIN’lerinden bağımsız olarak çalışır. Kullanıcı iki PIN istemini de aynı anda alırsa, beklenen davranış Intune PIN’inin öncelik kazanmasıdır.

**Intune PIN güvenliği**<br>
PIN, uygulamadaki kuruluş verilerine yalnızca doğru kullanıcının erişmesine izin verir. Bu nedenle son kullanıcıların, Intune uygulama PIN’lerini ayarlamak veya sıfırlamak için iş veya okul hesaplarında oturum açmaları gerekir. Bu kimlik doğrulaması, güvenli belirteç değişimi aracılığıyla Azure Active Directory tarafından işlenir ve [Intune SDK 'sı](../developer/app-sdk.md)tarafından saydam değildir. Güvenlik açısından, iş veya okul verilerini korumanın en iyi yolu verileri şifrelemektir. Şifreleme, uygulama PIN'i ile ilişkili değildir; ayrı bir uygulama koruma ilkesidir.

**Deneme yanılma saldırılarına karşı koruma ve Intune PIN 'ı**<br>
Uygulama PIN’i ilkesinin parçası olarak BT yöneticisi, bir kullanıcının uygulama kilitlenmeden önce PIN’ini doğrulamayı en fazla kaç kez deneyebileceğini belirleyebilir. Deneme sayısı karşılandıktan sonra, [ıNTUNE SDK](../developer/app-sdk.md) uygulamadaki "Kurumsal" verileri silebilir.

**Intune PIN ve seçmeli silme**<br>
İOS 'ta uygulama düzeyi PIN bilgileri, tüm birinci taraf Microsoft uygulamaları gibi aynı yayımcıya sahip uygulamalar arasında paylaşılan anahtarlıkta saklanır. Bu PIN bilgileri ayrıca bir son kullanıcı hesabına bağlıdır. Bir uygulamanın seçmeli Temizleme işlemi, farklı bir uygulamayı etkilememelidir. 

Örneğin, oturum açmış kullanıcı için Outlook için bir PIN kümesi, paylaşılan bir anahtarlıkta saklanır. Kullanıcı OneDrive 'da oturum açtığında (Microsoft tarafından yayımlandığında), aynı paylaşılan anahtarlığı kullandığından bu PIN Outlook ile aynı PIN 'i görür. Outlook oturumunu kapatma veya Outlook 'taki Kullanıcı verilerini silme işlemi yaparken, OneDrive bu PIN 'ı hala kullanıyor olabileceğinden Intune SDK 'Sı bu anahtarlığı temizlemez. Bu nedenle, seçmeli wpes, PIN 'ı de içeren paylaşılan anahtarlığı temizlemez. Bu davranış, cihazda yalnızca bir yayımcı tarafından tek bir uygulama mevcut olsa bile aynı kalır. 

PIN, aynı yayımcıya sahip uygulamalar arasında paylaşıldığından, silme işlemi tek bir uygulamaya geçtiğinde, cihazda aynı yayımcıya sahip başka bir uygulama olup olmadığını, Intune SDK 'Sı bilmez. Bu nedenle, Intune SDK diğer uygulamalar için hala kullanılabilir olduğundan PIN 'ı temizlemez. Bunun beklentisi, bu yayımcının son uygulaması, bazı işletim sistemi temizlemesinin bir parçası olarak kaldırılacak şekilde uygulama PIN 'inin silinmesine neden olur.
 
PIN 'in bazı cihazlarda temizlenmiş olduğunu gözlemlerseniz, şunlar olasıdır: PIN bir kimliğe bağlı olduğundan, Kullanıcı silme işleminden sonra farklı bir hesapla oturum açmışsa, yeni bir PIN girmesi istenir. Ancak, önceden var olan bir hesapla oturum açtıklarında, anahtarlıkta depolanan bir PIN, oturum açmak için zaten kullanılabilir.

**Aynı yayımcıdaki uygulamalarda iki kez bir PIN mi ayarlanıyor?**<br>
MAM (iOS üzerinde) Şu anda, [iOS Için Intune SDK 'sını](../developer/app-sdk-ios.md)bütünleştirmek için uygulamaların (örneğin WXP, Outlook, Managed Browser, Yammer) katılımını gerektiren alfasayısal ve özel karakterler (' geçiş kodu ' olarak adlandırılır) ile uygulama düzeyinde PIN 'e izin verir. Bu olmadan geçiş kodu ayarları, hedeflenmiş uygulamalar için doğru şekilde zorlanır. Bu, iOS için Intune SDK'sı 7.1.12 sürümünde kullanıma sunulmuş olan bir özellikti.

Bu özelliği desteklemek ve iOS için Intune SDK'sının önceki sürümleriyle geriye dönük uyumluluğu güvence altına almak için, 7.1.12+ sürümlerinde tüm PIN'ler (sayısal veya geçiş kodu) SDK'nın önceki sürümlerindeki sayısal PIN'den ayrı işlenir. Bu nedenle, cihazda aynı yayımcının iOS için Intune SDK'sının 7.1.12 öncesi VE 7.1.12 sonrası sürümlerini içeren uygulamalar varsa, iki PIN ayarlamaları gerekir. İki PIN (her uygulama için) herhangi bir şekilde ilişkili değildir (yani, uygulamaya uygulanan uygulama koruma ilkesine uyması gerekir). Bu nedenle, *yalnızca* A ve B uygulamaları aynı ilkelerin uygulanmış olması durumunda (PIN 'e göre), Kullanıcı aynı PIN 'i iki kez ayarlayabilir. 

Bu davranış Intune Mobil Uygulama Yönetimi'nin etkinleştirildiği iOS uygulamalardaki PIN’e özgüdür. Zaman içinde, uygulamalar iOS için Intune SDK'sının daha yeni sürümlerini benimsedikçe aynı yayımcıdan gelen uygulamalarda iki kez PIN ayarlama gereği sorun olmaktan çıkar. Örnek görmek için lütfen aşağıdaki nota bakın.

  >[!NOTE]
  > Örneğin, aynı yayımcının A uygulaması 7.1.12 öncesi bir sürümle oluşturulduysa ve B uygulaması 7.1.12 ile veya sonraki bir sürümle oluşturulduysa, iOS cihazında her iki uygulamanın da yüklü olması durumunda son kullanıcının A ve B için ayrı PIN'ler ayarlaması gerekir.
  > SDK sürümü 7.1.9 olan bir uygulama cihazda yüklüyse, aynı PIN 'ı App A ile paylaşır. 7.1.14 ile oluşturulan bir uygulama, B uygulamasıyla aynı PIN 'ı paylaşır.  
  > Cihazda yalnızca A ve C uygulamaları yüklüyse, tek bir PIN'in ayarlanması yeterli olur. Cihazda yalnızca B ve D uygulamaları yüklü olduğunda da aynı durum geçerlidir.

### <a name="app-data-encryption"></a>Uygulama veri şifrelemesi
BT yöneticileri uygulama verilerinin şifrelenmesini gerektiren bir uygulama koruma ilkesi dağıtabilir. İlkenin bir parçası olarak BT yöneticisi, içeriğin ne zaman şifreleneceğini de belirtebilir.

**Intune veri şifreleme işlemi nasıl yapılır?**<br> Şifreleme uygulama koruma ilkesi ayarı hakkında ayrıntılı bilgi için [Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md) ve [iOS uygulama koruma ilkesi ayarlarına](app-protection-policy-settings-ios.md) bakın.

**Şifrelenen veriler**<br>
BT yöneticisinin uygulama koruma ilkesine uygun şekilde, yalnızca “kurumsal” olarak işaretlenen veriler şifrelenir. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Intune, Office uygulamalarında şunları iş konumları olarak değerlendirir:

- E-posta (Exchange) 
- Bulut depolama (OneDrive Iş hesabı ile OneDrive uygulaması)

[Intune uygulaması sarmalama aracı](../developer/apps-prepare-mobile-application-management.md)tarafından yönetilen iş kolu uygulamaları için tüm uygulama verileri "Kurumsal" olarak kabul edilir.

### <a name="selective-wipe"></a>Seçmeli temizleme

**Verileri uzaktan silme**<br>
Intune, uygulama verilerini üç farklı yolla temizleyebilir: 
- Tam cihaz Temizleme
- MDM için seçmeli Temizleme 
- MAM seçmeli silme

MDM için uzaktan silme hakkında daha fazla bilgi için bkz. [Silme veya kullanımdan kaldırma işlemlerini kullanarak cihaz kaldırma](../remote-actions/devices-wipe.md). MAM kullanarak seçmeli silme hakkında daha fazla bilgi için bkz. [Kullanımdan kaldırma eylemi](../remote-actions/devices-wipe.md#retire) ve [Uygulamalardan yalnızca şirket verilerini silme](apps-selective-wipe.md).

[Tam cihaz temizleme](../remote-actions/devices-wipe.md) , cihazı fabrika varsayılan ayarlarına geri yükleyerek **cihazdaki** tüm Kullanıcı verilerini ve ayarlarını kaldırır. Cihaz Intune’dan kaldırılır.

  >[!NOTE]
  > Tam cihaz temizleme ve MDM için seçmeli Temizleme yalnızca Intune mobil cihaz yönetimi (MDM) ile kaydedilen cihazlarda sağlanabilir.

**MDM için seçmeli Temizleme**<br>
Şirket verilerini kaldırma hakkında bilgi edinmek için [Cihaz kaldırma - kullanımdan kaldırma](../remote-actions/devices-wipe.md#retire) bölümüne bakın.

**MAM için seçmeli Temizleme**<br>
MAM için seçmeli temizleme, şirket uygulama verilerini uygulamadan kaldırır. Intune Azure portalı kullanarak istek başlatılır. Bir silme isteği başlatma hakkında bilgi edinmek için bkz. [Uygulamalardan yalnızca şirket verilerini temizleme](apps-selective-wipe.md).

Seçmeli Temizleme başlatıldığında Kullanıcı uygulamayı kullanıyorsa, [Intune SDK 'sı](../developer/app-sdk.md) , Intune MAM hizmetinden seçmeli silme isteği için her 30 dakikada bir denetler. Ayrıca kullanıcı uygulamayı ilk kez başlattığında ve iş veya okul hesabı ile oturum açtığında da seçmeli temizleme isteği olup olmadığı denetlenir.

**Şirket Içi hizmetler (Şirket Içi) Hizmetleri Intune korumalı uygulamalarla çalışmazsa**<br>
Intune uygulama koruması, uygulama ve [ıNTUNE SDK](../developer/app-sdk.md)arasında tutarlı olması için kullanıcının kimliğine bağlıdır. Bunu garanti etmenin tek yolu modern kimlik doğrulaması yapmaktır. Uygulamaların bir şirket içi yapılandırma ile çalışabileceği senaryolar vardır, ancak bunlar tutarlı değildir ve garanti edilmez.

**Yönetilen uygulamalardan Web bağlantıları açmak için güvenli yol**<br>
BT yöneticisi, Microsoft Intune tarafından geliştirilen ve Intune ile kolayca yönetilebilen bir web tarayıcısı olan [Intune Managed Browser uygulamasını](app-configuration-managed-browser.md) dağıtabilir ve bunun için uygulama koruma ilkesi ayarlayabilir. BT yöneticisi, Intune ile yönetilen tüm uygulamalardaki web bağlantılarının Managed Browser uygulaması kullanılarak açılmasını gerekli kılabilir.

## <a name="app-protection-experience-for-ios-devices"></a>İOS cihazları için uygulama koruma deneyimi

### <a name="device-fingerprint-or-face-ids"></a>Cihaz parmak izi veya yüz kimlikleri 
Intune uygulama koruma ilkeleri, yalnızca Intune lisanslı kullanıcılara uygulama erişimi denetimi verir. Uygulamaya erişimi denetleme yollarından biri, desteklenen cihazlarda Apple’ın Touch ID veya Face ID özelliğini gerekli kılmaktır. Intune, cihazın biyometrik veritabanında bir değişiklik olduğunda ve etkin olmama zaman aşımı değeri karşılandığında kullanıcıdan PIN isteyen bir davranış uygular. Biyometrik verilerdeki değişikliklere parmak izi veya yüz kimliği eklenmesi veya kaldırılması dahildir. Intune kullanıcısı bir PIN ayarlamamışsa, Intune PIN’i ayarlamak üzere yönlendirilir.
 
Bu işlemin amacı, kuruluşunuzun uygulama içindeki verilerinin güvenli ve uygulama düzeyinde korunmasını sürdürmeye devam etmek için kullanılır. Bu özellik yalnızca iOS için kullanılabilir ve iOS, sürüm 9.0.1 veya üzeri için Intune SDK 'sını tümleştiren uygulamaların katılımını gerektirir. Hedeflenen uygulamalarda davranışın zorlanabilmesi için SDK tümleştirmesi gereklidir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Katılan uygulamalardan bazıları WXP, Outlook, Managed Browser ve Yammer’dır.
  
### <a name="ios-share-extension"></a>iOS Share uzantısı
Veri Aktarım İlkesi **yalnızca yönetilen uygulamalar** veya **uygulama olmadan**ayarlanmış olsa bile, yönetilmeyen uygulamalarda iş veya okul verilerini açmak için iOS Share uzantısını kullanabilirsiniz. Intune uygulama koruma ilkesi, cihaz yönetilmeden iOS paylaşım uzantısını denetleyemez. Bu nedenle, Intune _**“kurumsal” verileri veriler uygulama dışında paylaşılmadan önce şifreler**_ . Yönetilen uygulama dışında bir "Kurumsal" dosya açmaya çalışırken bu şifreleme davranışını doğrulayabilirsiniz. Bu dosya şifrelenmiş olmalı ve yönetilen bir uygulama dışında açılamamalıdır.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Aynı uygulama ve kullanıcı kümesi için birden çok Intune uygulama koruma erişimi ayarı
Erişim için Intune uygulama koruma ilkeleri, hedeflenen bir uygulamaya kurumsal hesabından erişmeyi denediğinde Son Kullanıcı cihazlarında belirli bir sırada uygulanır. Genel olarak öncelik temizlemededir; ardından engelleme, sonra da kapatılabilen uyarı gelir. Örneğin, belirli bir kullanıcı/uygulama için uygunsa, kullanıcıyı iOS sürümünü güncelleştirmesi için uyaran en düşük iOS işletim sistemi ayarı, kullanıcının erişimini engelleyen en düşük iOS işletim sistemi ayarından sonra uygulanacaktır. Dolayısıyla, BT yöneticisinin en düşük iOS işletim sistemi olarak 11.0.0.0 ve en düşük iOS işletim sistemi (yalnızca Uyarı) olarak 11.1.0.0'ı ayarladığı bir senaryoda, uygulamaya erişmeye çalışan cihazın işletim sistemi iOS 10 olduğunda, son kullanıcı erişimin engellenmesine yol açan en düşük iOS işletim sistemi sürümüne yönelik daha kısıtlayıcı ayar temel alınarak engellenebilir.

Farklı ayar türleriyle ilgilenirken, bir Intune SDK sürümü gereksinimi öncelikli olarak bir uygulama sürümü gereksinimini ve ardından iOS işletim sistemi sürümü gereksinimini alır. Ardından, tüm ayarlar türlerine yönelik uyarılar aynı sırada denetlenir. Intune SDK sürümü gereksiniminin, yalnızca Intune ürün ekibinden önemli engelleme senaryoları için rehberlik sağlandığında yapılandırılmasını öneririz.

## <a name="app-protection-experience-for-android-devices"></a>Android cihazlar için uygulama koruma deneyimi

### <a name="company-portal-app-and-intune-app-protection"></a>Şirket Portalı uygulaması ve Intune uygulama koruması
Uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı _gerekli değildir_. Kayıt olmadan mobil uygulama yönetimi için son kullanıcının cihazda Şirket Portalı uygulamasının yüklü olması gerekir.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Aynı uygulama ve kullanıcı kümesi için birden çok Intune uygulama koruma erişimi ayarı
Erişim için Intune uygulama koruma ilkeleri, hedeflenen bir uygulamaya kurumsal hesabından erişmeyi denediğinde Son Kullanıcı cihazlarında belirli bir sırada uygulanır. Genel olarak öncelik engellemededir; ardından kapatılabilen uyarı gelir. Örneğin, belirli bir kullanıcı/uygulama için uygunsa, kullanıcıyı bir yama yükseltmesi alması için uyaran en düşük Android yama sürümü ayarı, kullanıcının erişimini engelleyen en düşük Android yama sürümü ayarından sonra uygulanacaktır. Dolayısıyla, BT yöneticisinin en düşük Android yama sürümü olarak 2018-03-01 ve en düşük Android yama sürümü (yalnızca Uyarı) olarak 2018-02-01'i ayarladığı bir senaryoda, uygulamaya erişmeye çalışan cihazın yama sürümü 2018-01-01 olduğunda, son kullanıcı erişimin engellenmesine yol açan en düşük Android yama sürümüne yönelik daha kısıtlayıcı ayar temel alınarak engellenebilir. 

Farklı ayar türleriyle ilgilenirken, uygulama sürümü gereksinimi önceliklidir ve bunu Android işletim sistemi sürümü gereksinimi ile Android yama sürümü gereksinimi izler. Ardından, tüm ayarlar türlerine yönelik uyarılar aynı sırada denetlenir.

### <a name="intune-app-protection-policies-and-googles-safetynet-attestation-for-android-devices"></a>Android cihazlar için Intune uygulama koruma ilkeleri ve Google 'ın SafetyNet kanıtı 
Intune uygulama koruma ilkeleri, yöneticilerin, Son Kullanıcı cihazların Android cihazları için Google 'ın SafetyNet kanıtlamasını geçmesini gerektirmesini sağlar. Yeni bir Google Play hizmeti belirleme, Intune hizmeti tarafından belirlenen bir aralıkta BT yöneticisine bildirilir. Yükleme nedeniyle hizmet çağrısının ne sıklıkta azaltıldı, bu nedenle bu değer dahili olarak korunur ve yapılandırılamaz. Google SafetyNet kanıtlama ayarı için herhangi bir BT Yöneticisi yapılandırılmış eylemi, koşullu başlatma sırasında Intune hizmetine yönelik son bildirilen sonuca göre alınacaktır. Hiçbir veri yoksa, başka hiçbir koşullu başlatma denetimi başarısız olmasına bağlı olarak erişime izin verilir ve kanıtlama sonuçlarını belirlemek için Google Play hizmeti "gidiş dönüş", arka uçta başlayacaktır ve cihaz başarısız olursa kullanıcının zaman uyumsuz olarak sorulması istenir. Eski veriler varsa, son bildirilen sonuca bağlı olarak erişim engellenir veya izin verilir ve benzer şekilde, kanıtlama sonuçlarını belirlemek için bir Google Play hizmeti "gidiş dönüş" işlemi başlar ve cihaz başarısız olursa kullanıcıyı zaman uyumsuz olarak uyarır.

### <a name="intune-app-protection-policies-and-googles-verify-apps-api-for-android-devices"></a>Intune uygulama koruma ilkeleri ve Google 'ın Android cihazları için uygulamaları doğrulama API 'SI
Intune Uygulama Koruması Ilkeleri, yöneticilerin Android cihazları için Google 'ın uygulamaları doğrula API 'SI aracılığıyla Son Kullanıcı cihazların sinyal göndermesini gerektirmek için yetenek sağlar. Bunun nasıl yapılacağı hakkında yönergeler cihaz tarafından biraz farklılık gösterir. Genel işlem, Google Play Store gidip **uygulamalarıma & oyunlarına**tıklayarak, son uygulama taramasının sonucunu tıklayarak, yürütme koruması menüsüne gidecektir. **Tarama cihazını güvenlik tehditlerine** karşı değiştirme seçeneğinin açık olduğundan emin olun.

### <a name="googles-safetynet-attestation-api"></a>Google 'ın SafetyNet kanıtlama API 'SI 
Intune, kayıtlı olmayan cihazlar için mevcut kök algılama denetimlerimize eklemek üzere SafetyNet API 'Lerini koruma Google Play kullanır. Google, Android uygulamalarının köklü cihazlarda çalıştırılmasını istemediklerinde benimsemesini sağlamak üzere bu API kümesini geliştirmiştir ve yaşmıştır. Android ödeme uygulaması bu şekilde eklenmiştir. Google, oluşan kök algılama denetimlerinden tamamen ortak bir şekilde paylaşmadığı sürece, bu API 'Lerin cihazlarını barındıran kullanıcıları algılamasını bekledik. Bu kullanıcıların, ilke etkin uygulamalarından daha sonra erişimine veya şirket hesaplarına erişimi engellenebilir. **Temel bütünlüğü denetle** , cihazın genel bütünlüğünü söyler. Köklü cihazlar, Öykünücüler, sanal cihazlar ve değişiklik işaretlerine sahip cihazlar temel bütünlüğü başarısız oluyor. **& Sertifikalı cihazların temel bütünlüğünü kontrol edin** ve bu, cihazın Google 'ın hizmetleriyle uyumluluğunu söyler. Yalnızca Google tarafından sertifikalı değiştirilmemiş cihazlar bu denetimi geçirebilir. Başarısız olacak cihazlar şunları içerir:

- Temel bütünlük başarısız olan cihazlar
- Kilidi açılmış bir önyükleme yükleyicisine sahip cihazlar
- Özel bir sistem görüntüsü/ROM içeren cihazlar
- Üretici, Google sertifikası için uygulanan veya geçirilecek cihazların
- Doğrudan Android açık kaynak program kaynak dosyalarından oluşturulan sistem görüntüsü olan cihazlar
- Beta/Geliştirici Önizleme sistem görüntüsü olan cihazlar

Teknik Ayrıntılar için, bkz. [Google 'ın SafetyNet kanıtlama hakkındaki belgeleri](https://developer.android.com/training/safetynet/attestation) .

### <a name="safetynet-device-attestation-setting-and-the-jailbrokenrooted-devices-setting"></a>SafetyNet cihaz kanıtlama ayarı ve ' jailbreak uygulanmış/kökü belirtilmiş cihazlar ' ayarı
Google Play korunmamıza sonra, son kullanıcının çevrimiçi olmasını, en azından kanıtlama sonuçlarının belirlenmesi için "gidiş dönüş" sırasında geçen sürenin süresini Son Kullanıcı çevrimdışıysa, BT Yöneticisi yine de **jailbreak uygulanmış/kökü belirtilmiş cihazlar** ayarından Zorlanmış bir sonuç bekleyebilir. Bu, Son Kullanıcı çok uzun süredir çevrimdışı ise, **çevrimdışı yetkisiz kullanım süresi** değeri yürütmeye gelir ve ağ erişimi kullanılabilir olana kadar iş veya okul verilerine yapılan tüm erişimler Bu Zamanlayıcı değerine ulaşıldığında engellenir. Her iki ayarı da açmak, son kullanıcılar mobil cihazlarda iş veya okul verilerine erişirken önemli olan Son Kullanıcı cihazlarını sağlıklı tutmaya yönelik katmanlı bir yaklaşım sağlar.

### <a name="google-play-protect-apis-and-google-play-services"></a>API 'Leri ve Google Play Hizmetleri koruma Google Play
Google Play koruma API 'Lerinden yararlanan uygulama koruma ilkesi ayarları Google Play Hizmetleri çalışmasını gerektirir. Hem **SafetyNET cihaz kanıtlama**hem de **uygulamalar için tehdit taraması** , Google Play hizmetleri Google tarafından belirlenen sürümünün düzgün şekilde çalışmasını gerektirir. Bunlar güvenlik alanına denk gelen ayarlar olduğundan, Son Kullanıcı bu ayarlarla hedeflendiyse ve uygun Google Play Hizmetleri veya Google Play Hizmetleri erişimi olmayan bir sürüme güvenmemişse engellenir.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)

[Microsoft Intune ile kullanılabilir Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md)

[Microsoft Intune ile kullanılabilir iOS uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md)

## <a name="see-also"></a>Ayrıca bkz:
Salesforce mobil uygulaması gibi üçüncü taraf uygulamalar, Intune ile özel şekillerde çalışarak şirket verilerini korur. Doğrudan Salesforce uygulamasının Intune ile nasıl çalıştığını (MDM uygulama yapılandırma ayarları dahil) öğrenmek için bkz. [Salesforce Uygulaması ve Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
