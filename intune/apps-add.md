---
title: "Microsoft Intune’a uygulama ekleme"
titlesuffix: 
description: "Uygulamaları kullanıcılara ve cihazlara atayabilmeniz için Microsoft Intune'a nasıl uygulama ekleyeceğinizi öğrenin. Intune,çok çeşitli uygulama türlerini destekler."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91762eafbba5f96ce04f3ffd4d83f63434a3ac74
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Microsoft Intune’a uygulama ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. Intune,çok çeşitli uygulama türlerini destekler. Her bir uygulama türü için kullanılabilir seçenekler farklılık gösterir.

Intune aşağıdaki uygulama türlerini eklemenize ve atamanıza izin verir:
| Uygulama Türü                                  | Yükleme                                                                  | Güncelleştirmeler                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| Web’deki uygulamalar                           | Intune, cihaz giriş ekranında web uygulaması için bir kısayol oluşturur          | Uygulama güncelleştirmeleri otomatik olarak yapılır     |
| Şirket içinde yazılan (iş kolu) uygulamalar  | Intune uygulamayı cihaza yükler (yükleme dosyasını siz sağlarsınız)    | Uygulamayı güncelleştirmeniz gerekir       |
| Mağazadan uygulamalar                       | Intune uygulamayı cihaza yükler                                       | Uygulama güncelleştirmeleri otomatik olarak yapılır     |
| Yerleşik uygulamalar                        | Intune uygulamayı cihaza yükler                                       | Uygulama güncelleştirmeleri otomatik olarak yapılır     |


Web uygulamalarının yanı sıra Intune, mağaza uygulamaları ve LOB uygulamaları için aşağıdaki belirli platformları da destekler:
- Mağaza uygulamaları
    - Android mağaza uygulamaları
    - iOS mağaza uygulamaları
    - Windows Phone 8.1 mağaza uygulamaları
    - Windows mağazası uygulamaları
    - Android for Work uygulamaları
    - Windows için Office 365 uygulamaları
    - macOS için Office 365 uygulamaları
- Uygulamanızı derleyin - İş kolu (LOB)
    - Android iş kolu (LOB) uygulamaları
    - iOS iş kolu (LOB) uygulamaları
    - Windows Phone iş kolu (LOB) uygulamaları (.xap dosyaları)
    - Windows iş kolu (LOB) uygulamaları (yalnızca .msi dosyaları)
- Yerleşik uygulamalar    

>[!TIP]
> İş kolu (LOB) uygulaması, bir uygulama yükleme dosyasından eklediğiniz bir uygulamadır. Örneğin bir iOS LOB uygulaması yüklemek için, **Uygulama ekle** dikey penceresinde **Uygulama türü** olarak **İş kolu uygulaması**’nı seçerek uygulamayı eklersiniz. Ardından uygulama paket dosyası uzantısını (.ipa) seçersiniz. Bu tür uygulamalar genellikle şirket içinde yazılanlardır.

## <a name="assess-application-requirements"></a>Uygulama gereksinimlerini değerlendirme 
BT yöneticisi olarak yalnızca grubunuzun hangi uygulamaları kullanacağına karar vermeniz değil, her bir grup ve alt grup için gereken yetenekleri de belirlemeniz gerekir. Her bir uygulama için gereken platformları, uygulamaya ihtiyacı olan kullanıcı gruplarını, bu gruplara uygulanacak yapılandırma ilkelerini ve uygulanacak koruma ilkelerini belirlemeniz gerekir.  

Ayrıca, Mobil Cihaz Yönetimi’ne (MDM) veya yalnızca Mobil Uygulama Yönetimi’ne (MAM) odaklanmak gerekip gerekmediğini belirlemeniz gerekir. Cihazı yönetmek için Intune kullanmak (Mobil cihaz Yönetimi), şu durumlarda yararlı olur:
- Kullanıcıların verimli olmaları için bir WiFi veya VPN şirket bağlantı profiline ihtiyacı olduğunda.
- Kullanıcıların cihazlarına bir uygulama kümesi gönderilmesine ihtiyacı olduğunda.
- Kuruluşunuzun, güvenlik veya şifreleme gibi belirli Mobil Cihaz Yönetimi (MDM) denetimlerini ilgilendiren düzenleyici ilkeler veya diğer ilkelere uyum sağlaması gerektiğinde.

Cihazı yönetmeden uygulamaları yönetmek için Intune kullanmak (Mobil Uygulama Yönetimi), şu durumlarda yararlı olur:
- Kullanıcıların kendi cihazlarını kullanmalarına izin vermek istediğinizde (KCG).
- Kullanıcılara MAM korumalarının etkin olduğunu bildirmek için cihaz düzeyinde sürekli bildirim yerine tek seferlik bir açılır öğe sağlamak istediğinizde.
- Kişisel cihazlarda daha az yönetim özelliği gerektiren ilkelere uyumlu sağlamak istediğinizde. Örneğin, tüm cihaz yerine yalnızca uygulamalar için şirket verilerini yönetmek istiyorsunuz.

Daha fazla bilgi için bkz. [MDM ve MAM karşılaştırması](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Uygulamayı kimin kullanacağını belirleme
Bir uygulamayı Intune’a ekledikten sonra, bunu kullanabilecek bir kullanıcı grubu atarsınız. Önce, uygulamanın içerdiği verilerin hassasiyetine bağlı olarak uygulamaya erişmesi uygun olan grubu belirlemelisiniz. Kuruluşunuzdaki belirli rolleri dahil etmeniz veya hariç tutmanız gerekebilir. Örneğin, satış grubunuzun yalnızca belirli LOB uygulamalarına ihtiyacı varken mühendislik, finans, insan kaynakları veya hukuki işlemlere odaklı kişilerin LOB uygulamalarını kullanmasına gerek olmayabilir. Ayrıca satış grubunuz, mobil cihazlarında dahili şirket hizmetlerine erişirken ilave veri korumasına da ihtiyaç duyabilir. Bu grubun uygulamayı kullanarak kaynaklara nasıl bağlanacağını belirlemeniz gerekir. Uygulamanın eriştiği veriler bulutta mı yoksa şirket içinde mi barınıyor? Ayrıca kullanıcılar bu uygulamayı kullanarak kaynaklara nasıl bağlanacak? Intune bir iş kolu uygulama sunucusu gibi şirket içi verilere güvenli erişim gerektiren mobil uygulamalara erişim sağlamayı da destekler. Bu erişim türü genel olarak, erişim denetimi için [Intune tarafından yönetilen sertifikaları](certificates-configure.md) çevredeki standart bir VPN ağ geçidi veya ara sunucusuyla, örneğin Microsoft Azure Active Directory Uygulama Ara Sunucusu’yla birlikte kullanarak gerçekleştirilir. Erişilen verilerin iş kolu uygulamanız içinde tutulmasına ve böylelikle şirket verilerinin tüketici uygulamalarına veya hizmetlerine geçirilememesine yardımcı olmak için Intune’un [Uygulama Kaydırma Aracı ve Uygulama SDK’sı](apps-prepare-mobile-application-management.md) kullanılabilir.

Her bir kullanım örneği ve alt kullanım örneği uygulama senaryosu ile ilişkili kuruluşsal grupları belirlemenize yardımcı olması için [Intune dağıtım planlama, tasarlama ve uygulama kılavuzunu](planning-guide.md) kullanın. Uygulamaları gruplara atama hakkında ayrıntılar için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md). 

### <a name="determine-the-type-of-app-for-your-solution"></a>Çözümünüz için uygulama türünü belirleme
Aşağıdaki uygulama türleri arasında seçim yapabilirsiniz:
- **Web uygulamaları** - Web uygulaması, istemci-sunucu uygulamasıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Ayrıca modern web barındırma platformları çoğu zaman güvenlik, yük dengeleme ve diğer yararlar da sunar. Bu tür bir uygulama Web’de ayrı olarak korunur. Bu uygulama türüne ulaşmak için Intune kullanırsınız. Bu uygulamaya erişebilecek kullanıcı gruplarını da atarsınız. Android’in web uygulamalarını desteklemediğini hatırlatırız.
- **Şirket içinde yazılmış uygulamalar (iş kolu)** - Şirket içinde yazılmış uygulamalar, iş kolu uygulamalarıdır. Bu uygulama türünün işlevselliği; Windows, iOS veya Android gibi Intune tarafından desteklenen platformlardan biri için oluşturulmuştur. Kuruluşunuz, güncelleştirmeleri ayrı bir dosya olarak oluşturur ve size gönderir. Siz de Intune aracılığıyla güncelleştirmeleri ekleyerek ve dağıtarak, bunları kullanıcılara gönderirsiniz. 
- **Mağazadan uygulamalar** - Mağaza uygulaması; Windows Mağazası, iOS mağazası veya Android mağazasına yüklenmiş bir uygulamadır. Uygulama sağlayıcı, uygulama güncelleştirmeleriyle ilgilenir ve bunları sağlar. Uygulamayı mağaza listesinden seçer ve Intune aracılığıyla bunu kullanıcılarınız için kullanılabilir uygulama olarak eklersiniz.

Kuruluşunuz için gereken uygulamaları belirlerken bu uygulamaların bulut hizmetleriyle tümleşme durumuna, hangi verilere eriştiğine, KCG kullanıcıları için kullanılabilir olup olmadığına ve internet erişimi gerektirip gerektirmediğine dikkat edin.

Kuruluşunuz için gereken uygulamaları belirleme hakkında daha fazla bilgi için [Bir tasarım oluştur](planning-guide-design.md#feature-requirements)’un **Özellik gereksinimleri** bölümündeki **Uygulamalar**’a bakın.

### <a name="understanding-app-management-and-protection-policies"></a>Uygulama yönetim ve koruma ilkelerini anlama
Intune, şirketinizin uyumluluk ve güvenlik ilkeleriyle uyum sağlaması için dağıttığınız uygulamaların işlevlerini değiştirmenize olanak verir. Böylece şirket verilerinizin nasıl korunduğunu belirleyebilirsiniz. Intune ile yönetilen uygulamalarda zengin bir mobil uygulama koruma ilkesi yelpazesi mevcuttur, örneğin:

- Kopyala ve yapıştır ve farklı kaydet işlevlerini kısıtlama
- Web bağlantılarını Intune Managed Browser’da açılacak şekilde yapılandırma
- Çoklu kimlik kullanımı ve uygulama düzeyinde koşullu erişimi etkinleştirme

Intune ile yönetilen uygulamalar ayrıca kayıt gerekmeksizin uygulama korumasını etkinleştirebilir, böylece kullanıcının cihazını yönetmeden veri kaybını önleme ilkelerini uygulama seçeneğine sahip olursunuz. Buna ek olarak, Intune Uygulama Yazılım Geliştirme Seti ve Uygulama Sarmalama Aracı kullanarak mobil uygulama yönetimini mobil ve iş kolu uygulamalarınızla birleştirebilirsiniz. Bu araçlar hakkında daha fazla bilgi için bkz. [Intune Uygulama SDK’sına genel bakış](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Lisanslı uygulamaları anlama
Web uygulamaları, mağaza uygulamaları ve LOB uygulamalarına ek olarak toplu satın alma programı uygulamaları ve lisanslı uygulamalar hakkında da bilgi sahibi olmalısınız, örneğin:     
- **İş için Apple Toplu Satın Alma Programı (iOS ve macOS)** - iOS uygulama deposu, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak sağlar. Birden fazla kopya satın almak, şirketinizdeki uygulamaları etkili bir şekilde yönetmenize yardımcı olur. Daha fazla bilgi için bkz. [iOS toplu satın alınan uygulamaları yönetme](vpp-apps-ios.md).
- **Android for Work (Android)** - Android for Work cihazlara uygulama atama işlemi, standart Android cihazlara atamaktan farklı bir yolla yapılır. Android for Work için yüklediğiniz tüm uygulamalar Google Play for Work mağazasından gelir. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız. Ardından uygulama, Azure portalının Lisanslı uygulamalar düğümünde görüntülenir. Buradan, uygulamanın atamasını, herhangi başka bir uygulamanın atamasıyla aynı şekilde yönetebilirsiniz.
- **İş için Microsoft Mağazası (Windows 10)** - İş için Microsoft Mağazası, kuruluşunuz için tek tek veya toplu olarak uygulamaları bulabileceğiniz ve satın alabileceğiniz bir yer sağlar. Mağazayı Microsoft Intune’a bağlayarak toplu satın alınan uygulamaları Azure portalından yönetebilirsiniz. Daha fazla bilgi için bkz. [İş İçin Microsoft Mağazası’ndan uygulamaları yönetme](windows-store-for-business.md). 

## <a name="before-you-start"></a>Başlamadan önce
Uygulamaları eklemeye ve atamaya başlamadan önce aşağıdaki noktaları göz önünde bulundurun.

- Bir mağazadan uygulama eklediğinizde ve atadığınızda, son kullanıcıların uygulamayı yükleyebilmesi için o mağazada bir hesapları olması gerekir.
- Atadığınız uygulama veya öğelerden bazıları yerleşik iOS uygulamalarına bağlı olabilir. Örneğin, iOS mağazasından bir kitap atarsanız cihazda iBooks uygulaması olmalıdır. Yerleşik iBooks uygulamasını kaldırdıysanız, yeniden devreye sokmak için Intune'u kullanamazsınız.

## <a name="cloud-storage-space"></a>Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak oluşturduğunuz tüm uygulamalar (örneğin, bir iş kolu uygulaması) paketlenir ve Intune bulut depolama alanına yüklenir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Tam abonelik 20 GB depolama alanı içerir.

Orijinal satın alma metodunuzu kullanarak Intune için ek depolama alanı satın alabilirsiniz.  Fatura veya kredi kartıyla ödeme yaptıysanız [Abonelik Yönetim portalını](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions) ziyaret edin.  Başka bir satın alma yöntemi kullandıysanız iş ortağınız veya satış yardımcınızla iletişime geçin.

Bulut depolama alanı gereksinimleri aşağıda belirtilmiştir:

-   Tüm uygulama yükleme dosyaları aynı klasörde olmalıdır.
-   Karşıya yüklediğiniz her dosya için dosya boyutu üst sınırı 2 GB'dir.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Uygulamalar için kategorileri oluşturma ve düzenleme

Uygulama kategorileri, kullanıcıların uygulamaları şirket portalında daha kolay bulabilmeleri için sıralamanıza yardımcı olabilir. Uygulamaya, **Geliştirici uygulamaları** veya **İletişim uygulamaları** gibi bir veya birden çok kategori atayabilirsiniz.
Uygulamayı Intune’a eklediğinizde, size istediğiniz kategoriyi belirtme seçeneği sağlanır. Uygulama eklemek ve kategorileri atamak için, platforma özgü konu başlıklarını kullanın. Kendi kategorilerinizi oluşturmak ve düzenlemek için aşağıdaki yordamı kullanın:

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Kurulum** > **Uygulama kategorileri**’ni seçin.
5. **Uygulama kategorileri** dikey penceresinde geçerli kategorilerin listesi gösterilir. Aşağıdaki eylemlerden birini seçin:
    - **Kategori oluştur** - **Kategori oluştur** dikey penceresini görüntülemek için **Ekle**’yi seçin ve yeni kategori için bir ad girin. Adlar tek bir dilde girilebilir ve Intune tarafından bunların çevirisi yapılmaz. İşiniz bittiğinde **Oluştur**’a tıklayın.
    - **Kategori düzenle** - Listedeki herhangi bir kategori için, '**...**' düğmesini seçin. Bu seçenek, kategoride **Panoya sabitle** veya **Sil** işlemleri yapmanıza imkan veren bir açılır menü görüntüler.

## <a name="apps-added-automatically-by-intune"></a>Intune tarafından otomatik olarak eklenen uygulamalar

Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Geri bildirimlerinize dayanarak bu liste kaldırıldı, artık yerleşik uygulamaları görmeyeceksiniz.
Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu cihazları gerektiği gibi atamaya devam edebilirsiniz.
Sonraki bir sürümde, Azure portalında yerleşik uygulama seçme ve atama için daha kolay bir yöntem eklemeyi planlıyoruz.

## <a name="next-steps"></a>Sonraki adımlar

Her platform için Intune’a uygulamaların nasıl eklendiğini öğrenmek için aşağıdaki konulardan birini seçin:

- [Android mağaza uygulamaları](store-apps-android.md)
- [Android LOB uygulamaları](lob-apps-android.md)
- [iOS Store uygulamaları](store-apps-ios.md)
- [iOS LOB uygulamaları](lob-apps-ios.md)
- [Web uygulamaları (tüm platformlar için)](web-app.md)
- [Windows Phone 8.1 mağaza uygulamaları](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB uygulamaları](lob-apps-windows-phone.md)
- [Windows Mağazası uygulamaları](store-apps-windows.md)
- [Windows LOB uygulaması](lob-apps-windows.md)
- [ Windows 10 için Office 365 uygulamaları](apps-add-office365.md)
- [Yerleşik uygulamalar](apps-add-built-in.md)

