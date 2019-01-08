---
title: Microsoft Intune’a uygulama ekleme
titlesuffix: ''
description: Uygulamaları kullanıcılara ve cihazlara atayabilmeniz için Microsoft Intune'a nasıl uygulama ekleyeceğinizi öğrenin. Intune, çok çeşitli uygulama türlerini destekler.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 95f41985f11803e6e1a474b38a2af6a891ddafcb
ms.sourcegitcommit: bf1549eb59adc31ead8601e40253a7024b22853c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2019
ms.locfileid: "54067491"
---
# <a name="add-apps-to-microsoft-intune"></a>Microsoft Intune’a uygulama ekleme 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Microsoft Intune’a eklemelisiniz.

Şirketinizdeki uygulama ve cihaz kullanıcılarının (şirketinizin iş gücü) çeşitli uygulama gereksinimleri olabilir. Intune'a uygulama eklemeden ve bunları iş gücünüze sunmadan önce, uygulamalara ilişkin birkaç temel bilgiyi değerlendirip anlamanız gerekir. Intune’da kullanılabilen çeşitli uygulama türlerini anlamanız gerekir. İş gücünüzün ihtiyaç duyduğu platformlar ve yetenekler gibi uygulama gereksinimlerini değerlendirmeniz gerekir. Cihazları (uygulamalar dahil) yönetmek için Intune kullanılıp kullanılmayacağını veya Intune’un cihazları yönetmeden uygulamaları yönetip yönetmeyeceğini belirlemeniz gerekir. Son olarak, iş gücünüzün ihtiyacı olan uygulama ve yetenekleri ve bunlara kimin ihtiyaç duyduğunu belirlemeniz gerekir. Bu makaledeki bilgiler, başlamanıza yardımcı olacaktır.

## <a name="app-types-in-microsoft-intune"></a>Microsoft Intune’da uygulama türleri

Intune, çok çeşitli uygulama türlerini destekler. Her bir uygulama türü için kullanılabilir seçenekler farklılık gösterir. Intune aşağıdaki uygulama türlerini eklemenize ve atamanıza izin verir:

| Uygulama türleri | Yükleme | Güncelleştirmeler |
|---|---|---|
| Mağazadan uygulamalar (mağaza uygulamaları) | Intune uygulamayı cihaza yükler.  | Uygulama güncelleştirmeleri otomatik olarak yapılır.   |
| Şirket içinde yazılan (iş kolu) uygulamalar  | Intune uygulamayı cihaza yükler (yükleme dosyasını siz sağlarsınız).     | Uygulamayı güncelleştirmeniz gerekir.  |
| Yerleşik olan uygulamalar (yerleşik uygulamalar)    | Intune uygulamayı cihaza yükler.  | Uygulama güncelleştirmeleri otomatik olarak yapılır.  |
| Web’deki uygulamalar (web bağlantısı) | Intune, cihaz giriş ekranında web uygulaması için bir kısayol oluşturur.  | Uygulama güncelleştirmeleri otomatik olarak yapılır.    |

### <a name="specific-app-type-details"></a>Belirli uygulama türü ayrıntıları
 
Aşağıdaki tablo, belirli uygulama türlerini ve bunları Intune’daki **Uygulama ekle** bölmesinde nasıl ekleyebileceğinizi listeler:

| **Uygulamaya özel tür** | **Genel tür** | **Uygulamaya özel yordamlar** |
| --- | --- | --- |
| Android mağaza uygulamaları  | Mağaza uygulaması  | **Uygulama türü** olarak **Android**’i seçin ve uygulamanın Google Play mağaza URL’sini girin. |
| iOS mağaza uygulamaları  | Mağaza uygulaması  | **Uygulama türü** olarak **iOS**’u seçin, Intune’da uygulama için arama yapın ve uygulamayı seçin. |
| Windows Phone 8.1 mağaza uygulamaları  | Mağaza uygulaması  | **Uygulama türü** olarak **Windows Phone 8.1**’i seçin ve uygulamanın Microsoft mağaza URL’sini girin. |
| Microsoft mağaza uygulamaları  | Mağaza uygulaması  | **Uygulama türü** olarak **Windows**’u seçin ve uygulamanın Microsoft mağaza URL’sini girin. |
| Android iş profili uygulamaları | Mağaza uygulaması  | Yönetilen Google Play mağazasından Android iş profili uygulamasını bulun ve onaylayın.  |
| Windows 10 için Office 365 uygulamaları  | Mağaza uygulaması (Office 365) | **Uygulama türü** olarak **Office 365 Paketi** altında **Windows 10**’u, ardından da yüklemek istediğiniz Office 365 uygulamasını seçin.  |
| macOS için Office 365 uygulamaları | Mağaza uygulaması (Office 365) | **Uygulama türü** olarak **Office 365 Paketi** altında **macOS**’u, ardından da Office 365 uygulama paketini seçin. |
| Android iş kolu (LOB) uygulamaları | LOB uygulaması | **Uygulama türü** olarak **İş kolu uygulaması**’nı seçin, **Uygulama paketi dosyası**’nı seçin ve **.apk** uzantısına sahip bir Android yükleme dosyası girin.  |
| iOS LOB uygulamaları | LOB uygulaması | **Uygulama türü** olarak **İş kolu uygulaması**’nı seçin, **Uygulama paketi dosyası**’nı seçin ve **.ipa** uzantısına sahip bir iOS yükleme dosyası girin.  |
| Windows Phone LOB uygulamaları | LOB uygulaması | **Uygulama türü** olarak **İş kolu** uygulamasını seçin, **Uygulama paketi dosyasını** seçin ve **.xap** uzantısına sahip bir Windows Phone yükleme dosyası girin.  |
| Windows LOB uygulaması | LOB uygulaması | Uygulama türü olarak **İş kolu** uygulamasını seçin, **Uygulama paketi dosyasını** seçin ve **.msi**, **.appx**, **.appxbundle**, **.msix** veya **.msixbundle** uzantılı bir Windows yükleme dosyası girin. |
| Yerleşik iOS uygulaması  | Yerleşik uygulama | **Uygulama türü** olarak **Yerleşik uygulama**’yı seçin ve sağlanan uygulamalar listesinde yerleşik uygulama seçeneğine tıklayın.  |
| Yerleşik Android uygulaması  | Yerleşik uygulama | **Uygulama türü** olarak **Yerleşik uygulama**’yı seçin ve sağlanan uygulamalar listesinde yerleşik uygulama seçeneğine tıklayın.  |
| Web uygulamaları  | Web uygulaması  | **Uygulama türü** olarak **Web bağlantısı**’nı seçin ve ardından web uygulamasına bağlantı sağlayan geçerli bir URL girin.  |
| Windows uygulaması (Win32)  | LOB uygulaması  | **Uygulama türü** olarak **Windows uygulaması (Win32)** seçeneğini belirleyin, **Uygulama paketi dosyası**'nı seçin, ardından **.intunewin** uzantılı bir yükleme dosyası seçin.  |

Microsoft Intune’da, **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Uygulama ekle** bölmesi görüntülenir ve **Uygulama türü**’nü seçmenize olanak tanır. 

>[!TIP]
> LOB uygulaması, bir uygulama yükleme dosyasından eklediğiniz bir uygulamadır. Örneğin bir iOS LOB uygulaması yüklemek için **Uygulama ekle** bölmesinde **Uygulama türü** olarak **İş kolu uygulaması**’nı seçersiniz. Ardından uygulama paket dosyası uzantısını (.ipa) seçersiniz. Bu tür uygulamalar genellikle şirket içinde yazılanlardır.

## <a name="assess-app-requirements"></a>Uygulama gereksinimlerini değerlendirme
BT yöneticisi olarak yalnızca grubunuzun hangi uygulamaları kullanacağına karar vermeniz değil, her bir grup ve alt grup için gereken yetenekleri de belirlemeniz gerekir. Her bir uygulama için gereken platformları, uygulamaya ihtiyacı olan kullanıcı gruplarını, bu gruplara uygulanacak yapılandırma ilkelerini ve koruma ilkelerini belirlersiniz.  

Ayrıca, Mobil Cihaz Yönetimi’ne (MDM) veya yalnızca Mobil Uygulama Yönetimi’ne (MAM) odaklanmak gerekip gerekmediğini belirlemeniz gerekir. 

MDM ile cihazı yönetmek için Intune kullanmak, şu durumlarda yararlı olur:
- Kullanıcıların verimli olmaları için bir Wi-Fi veya VPN şirket bağlantı profiline ihtiyacı olduğunda.
- Kullanıcıların cihazlarına bir uygulama kümesi gönderilmesine ihtiyacı olduğunda.
- Kuruluşunuzun, güvenlik veya şifreleme gibi belirli MDM denetimlerini ilgilendiren düzenleyici ilkeler veya diğer ilkelere uyum sağlaması gerektiğinde.

MAM ile cihazı yönetmeden uygulamaları yönetmek için Intune kullanmak şu durumlarda yararlı olur:
- Kullanıcıların kendi cihazlarını kullanmalarına izin vermek istediğinizde (KCG).
- Kullanıcılara MAM korumalarının etkin olduğunu bildirmek için cihaz düzeyinde sürekli bildirim yerine tek seferlik bir açılır ileti sağlamak istediğinizde.
- Kişisel cihazlarda daha az yönetim yeteneği gerektiren ilkelerle uyumluluk sağlamak istediğinizde. Örneğin, tüm cihaz yerine yalnızca uygulamalar için şirket verilerini yönetmek istiyorsunuz.

Daha fazla bilgi için bkz. [MDM ve MAM karşılaştırması](byod-technology-decisions.md).

### <a name="determine-who-will-use-the-app"></a>Uygulamayı kimin kullanacağını belirleme

İş gücünüzün hangi uygulamalara ihtiyaç duyduğunu belirlerken çeşitli kullanıcı gruplarını ve bunların kullandığı çeşitli uygulamaları göz önünde bulundurun. Bu grupları bilmek, bir uygulamayı ekledikten sonra da yararlıdır. Bir uygulamayı ekledikten sonra, bunu kullanabilecek bir kullanıcı grubu atarsınız. 

Önce uygulamanın içerdiği verilerin hassasiyetine bağlı olarak hangi grubun uygulamaya erişmesi gerektiğini belirlemelisiniz. Kuruluşunuzdaki belirli rolleri dahil etmeniz veya hariç tutmanız gerekebilir. Örneğin satış grubunuzun yalnızca belirli LOB uygulamalarına ihtiyacı varken mühendislik, finans, insan kaynakları veya hukuki işlemlere odaklı kişilerin LOB uygulamalarını kullanmasına gerek olmayabilir. Ayrıca satış grubunuz, mobil cihazlarında dahili şirket hizmetlerine erişirken ilave veri korumasına da ihtiyaç duyabilir. Bu grubun uygulamayı kullanarak kaynaklara nasıl bağlanacağını belirlemeniz gerekir. Uygulamanın eriştiği veriler bulutta mı yoksa şirket içinde mi barınıyor? Ayrıca kullanıcılar bu uygulamayı kullanarak kaynaklara nasıl bağlanacak? 

Intune bir iş kolu uygulama sunucusu gibi şirket içi verilere güvenli erişim gerektiren istemci uygulamalara erişim sağlamayı da destekler. Bu erişim türünü genelde, erişim denetimi için [Intune tarafından yönetilen sertifikaları](certificates-configure.md), çevredeki standart bir VPN ağ geçidi veya ara sunucu ile (örneğin Azure Active Directory Uygulama Ara Sunucusu) birlikte kullanarak sağlarsınız. Erişilen verilerin iş kolu uygulamanız içinde tutulmasına ve böylelikle şirket verilerinin tüketici uygulamalarına veya hizmetlerine geçirilememesine yardımcı olmak için Intune [Uygulama Sarmalama Aracı ve Uygulama SDK’sı](apps-prepare-mobile-application-management.md) kullanılabilir.

Her bir kullanım örneği ve alt kullanım örneği uygulama senaryosu ile ilişkili kuruluşsal grupları belirlemenize yardımcı olması için [Intune dağıtım planlama, tasarlama ve uygulama kılavuzunu](planning-guide.md) kullanın. Uygulamaları gruplara atama hakkında bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

### <a name="determine-the-type-of-app-for-your-solution"></a>Çözümünüz için uygulama türünü belirleme

Aşağıdaki uygulama türlerinden birini seçebilirsiniz:
- **Mağazadan uygulamalar**: Microsoft mağazası, iOS mağazası veya Android mağazası için yüklenmiş uygulamalar mağaza uygulamalardır. Bir mağaza uygulamasının sağlayıcısı, uygulama güncelleştirmeleriyle ilgilenir ve bunları sağlar. Uygulamayı mağaza listesinden seçer ve Intune aracılığıyla bunu kullanıcılarınız için mevcut bir uygulama olarak eklersiniz.
- **Şirket içi (satır iş kolu) yazılmış uygulamalar**: Şirket içinde oluşturulan satır iş kolu (LOB) uygulamaları uygulamalardır. Bu uygulama türünün işlevselliği; Windows, iOS veya Android gibi Intune tarafından desteklenen platformlardan biri için oluşturulmuştur. Kuruluşunuz, güncelleştirmeleri ayrı bir dosya olarak oluşturur ve size gönderir. Siz de Intune aracılığıyla güncelleştirmeleri ekleyerek ve dağıtarak, bunları kullanıcılara gönderirsiniz.
- **Web uygulamaları**: Web apps, istemci-sunucu uygulamalarıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Ayrıca modern web barındırma platformları çoğu zaman güvenlik, yük dengeleme ve diğer yararlar da sunar. Bu tür bir uygulama web’de ayrı olarak korunur. Bu uygulama türüne ulaşmak için Intune kullanırsınız. Bu uygulamaya erişebilecek kullanıcı gruplarını da atarsınız. Android’in web uygulamalarını desteklemediğini hatırlatırız.

Kuruluşunuz için gereken uygulamaları belirlerken bu uygulamaların bulut hizmetleriyle tümleşme durumuna, hangi verilere eriştiğine, KCG kullanıcıları için mevcut olup olmadığına ve İnternet erişimi gerektirip gerektirmediğine dikkat edin.

Kuruluşunuzun ihtiyacı olan uygulamaları belirleme hakkında daha fazla bilgi için [Bir tasarım oluştur](planning-guide-design.md#feature-requirements)’un “Özellik gereksinimleri” bölümündeki “Uygulamalar” kısmına bakın.

### <a name="understanding-app-management-and-protection-policies"></a>Uygulama yönetim ve koruma ilkelerini anlama
Intune, şirketinizin uyumluluk ve güvenlik ilkeleriyle uyum sağlaması için dağıttığınız uygulamaların işlevlerini değiştirmenize olanak verir. Böylece şirket verilerinizin nasıl korunduğunu belirleyebilirsiniz. Intune ile yönetilen uygulamalarda zengin bir mobil uygulama koruma ilkesi yelpazesi mevcuttur, örneğin:

- Kopyala ve yapıştır ve farklı kaydet işlevlerini kısıtlama.
- Web bağlantılarını Intune Managed Browser’da açılacak şekilde yapılandırma.
- Çoklu kimlik kullanımı ve uygulama düzeyinde koşullu erişimi etkinleştirme.

Intune ile yönetilen uygulamalar ayrıca kayıt gerekmeksizin uygulama korumasını etkinleştirebilir, böylece kullanıcının cihazını yönetmeden veri kaybını önleme ilkelerini uygulama seçeneğine sahip olursunuz. Buna ek olarak, Intune Uygulama SDK’sı ve Uygulama Sarmalama Aracı’nı kullanarak mobil uygulama yönetimini mobil ve iş kolu uygulamalarınızla birleştirebilirsiniz. Bu araçlar hakkında daha fazla bilgi için bkz. [Intune Uygulama SDK’sına genel bakış](app-sdk.md).

### <a name="understanding-licensed-apps"></a>Lisanslı uygulamaları anlama
Web uygulamaları, mağaza uygulamaları ve LOB uygulamalarını anlamaya ek olarak toplu satın alma programı uygulamalarının hedefi ve lisanslı uygulamalar hakkında da bilgi sahibi olmalısınız, örneğin: 
- **Apple Volume Purchasing Program (iOS) iş**: İOS App Store, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak tanır. Birden fazla kopya satın almak, şirketinizdeki uygulamaları etkili bir şekilde yönetmenize yardımcı olur. Daha fazla bilgi için bkz. [iOS toplu satın alınan uygulamaları yönetme](vpp-apps-ios.md).
- **Android iş profili**: Android iş profili cihazlarına uygulama atama işlemi, standart Android cihazlara uygulama atamaktan farklıdır. Android iş profili için yüklediğiniz tüm uygulamalar Yönetilen Google Play mağazasından gelir. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız. Daha sonra uygulama, Azure portalının **Lisanslı uygulamalar** düğümünde görünür ve uygulamanın atamasını diğer uygulamalarda olduğu gibi yaparsınız.
- **(Windows 10) iş için Microsoft Store**: İş için Microsoft Store, bulmak ve kendi Kurumunuz için uygulamaları tek tek veya toplu satın alma için bir yer sağlar. Mağazayı Microsoft Intune’a bağlayarak toplu satın alınan uygulamaları Azure portalında yönetebilirsiniz. Daha fazla bilgi için bkz. [İş İçin Microsoft Mağazası’ndan uygulamaları yönetme](windows-store-for-business.md).

    > [!NOTE]
    > Windows uygulamaları için dosya uzantıları **.msi**, **.appx**, **.appxbundle**, **.msix** ve **.msixbundle**'dır.  

## <a name="before-you-add-apps"></a>Uygulamaları eklemeden önce
Uygulamaları eklemeye ve atamaya başlamadan önce aşağıdaki noktaları göz önünde bulundurun:

- Bir mağazadan uygulama eklediğinizde ve atadığınızda, kullanıcılarınızın uygulamayı yükleyebilmesi için o mağazada bir hesapları olması gerekir.
- Atadığınız uygulama veya öğelerden bazıları yerleşik iOS uygulamalarına bağlı olabilir. Örneğin, iOS mağazasından bir kitap atarsanız cihazda iBooks uygulaması olmalıdır. Yerleşik iBooks uygulamasını kaldırdıysanız, yeniden devreye sokmak için Intune'u kullanamazsınız.

> [!IMPORTANT]
> Uygulamayı dağıttıktan ve yükledikten sonra Intune Azure portalı aracılığıyla uygulamanın adını değiştirirseniz, uygulama artık komutlar kullanılarak hedeflenemez.

## <a name="cloud-storage-space"></a>Bulut depolama alanı
Yazılım yükleyicisi yükleme türünü kullanarak oluşturduğunuz tüm uygulamalar (örneğin, bir iş kolu uygulaması) paketlenir ve Intune bulut depolama alanına yüklenir. Intune deneme aboneliği, yönetilen uygulamaları ve güncelleştirmeleri depolamak için kullanılan 2 gigabayt (GB) bulut tabanlı depolama alanı içerir. Tam abonelik, toplam depolama alanı miktarını sınırlamaz.

Bulut depolama alanı gereksinimleri aşağıda belirtilmiştir:

- Tüm uygulama yükleme dosyaları aynı klasörde olmalıdır.
- Karşıya yüklediğiniz her dosya için boyut üst sınırı 8 GB’tır.

## <a name="create-and-edit-categories-for-apps"></a>Uygulamalar için kategorileri oluşturma ve düzenleme

Uygulama kategorileri, kullanıcıların uygulamaları şirket portalında daha kolay bulabilmeleri için sıralamanıza yardımcı olabilir. Uygulamaya, *Geliştirici uygulamaları* veya *İletişim uygulamaları* gibi bir veya birden çok kategori atayabilirsiniz.

Uygulamayı Intune’a eklediğinizde, size istediğiniz kategoriyi belirtme seçeneği sağlanır. Uygulama eklemek ve kategorileri atamak için, platforma özgü konu başlıklarını kullanın. Kendi kategorilerinizi oluşturmak ve düzenlemek için aşağıdaki yordamı kullanın:

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükünde, **Kurulum** altında **Uygulama kategorileri**’ni seçin.  
    **Uygulama kategorileri** bölmesi, mevcut kategoriler listesini görüntüler. 
5. Aşağıdakilerden birini yapın:
    - Bir kategori eklemek için **Kategori ekle** bölmesinde **Ekle**’yi seçin ve kategori için bir ad girin.  
    Adlar tek bir dilde girilebilir ve Intune tarafından çevrilmez.
    - Bir kategoriyi düzenlemek için kategorinin yanındaki üç nokta simgesini (**...**) seçin ve daha sonra **Panoya sabitle** veya **Sil**’e tıklayın.
6. **Oluştur**’u seçin.

## <a name="apps-that-are-added-automatically-by-intune"></a>Intune tarafından otomatik olarak eklenen uygulamalar

Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Intune müşteri geri bildirime dayanarak bu listeyi kaldırdık, yerleşik uygulamalar artık görüntülenmiyor. Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Uygulamaları gerektiği gibi atamaya devam edebilirsiniz.

> [!NOTE]
> İş Kolu uygulaması dışındaki gerekli uygulamaların yüklemesinde, uygulamanın algılanmaması ve uygulama yükleme durumunun *Yükleme Bekletiliyor* olmaması koşuluyla, Intune cihaz her iade edildiğinde bir yükleme komutu göndererek uygulamayı yüklemeyi dener.

## <a name="installing-updating-or-removing-required-apps"></a>Gerekli uygulamaları yükleme, güncelleştirme veya kaldırma

Intune, 7 günlük yeniden değerlendirme döngüsünü beklemek yerine 24 saat içerisinde gerekli bir uygulamayı otomatik olarak tekrar yükler, güncelleştirir veya kaldırır.

Intune bu işlemi şu koşullara dayalı olarak gerçekleştirir:
- Bir son kullanıcı, cihazında yüklü olmasını gerekli kıldığınız bir uygulamayı kaldırırsa Intune, bu zamanlama geçtikten sonra uygulamayı otomatik olarak yeniden yükler.
- Gerekli bir uygulamanın yüklemesi başarısız olursa veya uygulama bir şekilde cihazda bulunmuyorsa Intune, uyumluluğu değerlendirir ve bu zamanlama geçtikten sonra uygulamayı yeniden yükler.  
- Yönetici, bir uygulamayı bir kullanıcı grubuna hedefler ve son kullanıcı bunu cihazda Şirket Portalı’ndan yükler. Daha sonra yönetici, uygulamayı v1’den v2’ye güncelleştirir. Bu durumda Intune, cihazda uygulamanın önceki herhangi bir sürümü mevcutsa bu zamanlama geçtikten sonra uygulamayı güncelleştirir.
- Yönetici kaldırma amacını dağıttığı halde uygulama cihazda mevcut olup kaldırılamamışsa Intune, uyumluluğu değerlendirir ve bu zamanlama geçtikten sonra uygulamayı kaldırır.   

## <a name="app-installation-errors"></a>Uygulama yükleme hataları

Intune uygulama yükleme hatalarının ayrıntıları için bkz. [Uygulama yükleme hataları](troubleshoot-app-install.md#app-installation-errors).

## <a name="next-steps"></a>Sonraki adımlar

Intune’da tüm platformlar için uygulama eklemeyi öğrenmek için bkz.:

- [Android mağaza uygulamaları](store-apps-android.md)
- [Android LOB uygulamaları](lob-apps-android.md)
- [iOS Store uygulamaları](store-apps-ios.md)
- [iOS LOB uygulamaları](lob-apps-ios.md)
- [Web uygulamaları (tüm platformlar için)](web-app.md)
- [Windows Phone 8.1 mağaza uygulamaları](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB uygulamaları](lob-apps-windows-phone.md)
- [Microsoft mağazası uygulamaları](store-apps-windows.md)
- [Windows LOB uygulaması](lob-apps-windows.md)
- [ Windows 10 için Office 365 uygulamaları](apps-add-office365.md)
- [macOS için Office 365 uygulamaları](apps-add-office365-macos.md)
- [Yerleşik uygulamalar](apps-add-built-in.md)
- [Win32 uygulamaları](apps-win32-app-management.md) 
