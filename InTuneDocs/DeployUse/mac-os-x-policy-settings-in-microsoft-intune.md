---
# required metadata

title: Microsoft Intune’da Mac OS X ilke ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Mac OS X yapılandırma ilkesi ayarları

## Genel yapılandırma ilkesi ayarları

Microsoft Intune **Mac OS X genel yapılandırma ilkesini** kullanarak aşağıdaki ayarları yapılandırabilirsiniz:

-   **Cihaz güvenliği ayarları**: Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini gösterir. Uyumlu Olmayan Uygulamalar Raporu’yla, listede belirttiğiniz uygulamalarla kullanıcıların yüklediği uygulamalar karşılaştırılarak uyumlu olup olmadığı görüntülenebilir (ancak uygulamanın yüklenmesi engellenemez).

Aradığınız özellik bu listede görünmüyorsa, Apple Configurator Aracını kullanarak oluşturduğunuz ayarları içeri aktarmanızı sağlayan bir Mac OS X özel ilkesi kullanarak bu özelliği oluşturabilirsiniz. Daha fazla bilgi için, bu konunun devamındaki **Özel ilke ayarları** bölümüne bakın.

### Parola ayarları

|Ayar adı|Ayrıntılar|
|----------------|---------------|
|**Cihazların kilidini açmak için parola gerektir**|Kullanıcının Mac bilgisayarına erişmek için parola kullanmasının gerekip gerekmediğini belirtir. **Önemli**: iOS cihazlarından farklı olarak, Mac OS X cihazlarında bu ayarla uyumluluğu korumak için parolasını güncelleştirmesi gerektiği kullanıcıya hemen bildirilmez.|
|**Gerekli parola türü**|Kullanılan parolanın yalnızca Sayısal olabileceğini ya da **Alfasayısal** (harfler ve sayılar içeren) olması gerektiğini belirtir. **Önemli**: Bu ayar yalnızca Mac OS X sürüm 10.10.3 ve üzerinde desteklenir.|
|**Parolada gerekli karmaşık karakter sayısı**|Parolada kullanılması gereken karmaşık karakterlerin sayısını (**0** - **4** arasında) belirtir).<br /><br />Karmaşık karakterler '**?** gibi simgelerdir.'|
|**Minimum parola uzunluğu**|Parola uzunluğu alt sınırını belirtir **4** ile **14** karakter arasında).|
|**Basit parolalara izin ver**|'**0000**' veya '**1234**' gibi basit parolaların kullanımına izin verir.'.|
|**Parola gerekmeden önce etkin olmama süresi (dakika)**|Bilgisayar ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtir.|
|**Parola geçerlilik süresi (gün)**|Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtir (**1** - **255** gün arasında).|
|**Parola geçmişini anımsa**|Bu ayar, kullanıcının önceden kullanılmış bir parolayı kullanmasını engellemeye yöneliktir. Ayarlandığında, önceden kullanılmış olan parolalardan yeniden kullanılamayacak olanların sayısını belirtmek için **Önceki parolaların yeniden kullanılmasını engelle** seçeneğini de ayarlayabilirsiniz (**1** - **24** arasında).).|
|**Ekran koruyucu etkinleştirilmeden önce işlem yapılmadan geçen süre**|Ekran koruyucu etkinleştirilmeden önce bilgisayarın boşta bekleyeceği süreyi belirtir.|

### Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Mac OS X için Uyumlu Olan ve Olmayan Uygulamalar** listesinde, **Cihazlar için yönetilen ayarlar**’ı etkinleştirin ve sonra aşağıdaki bilgileri kullanarak uyumlu veya uyumsuz uygulamalar listesini belirtin:

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.
> 
> Intune, uyumsuz uygulamalar içeren cihazları raporlamanızı sağlar. Yüklemeyi engellemez veya uyumsuz uygulamaları kaldırmaz.

|Ayar adı|Ayrıntılar|
|----------------|---------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Kullanıcıların yüklemesine izin verilmeyen Mac OS X uygulamalarını listeler. Kullanıcılar bu uygulamalardan herhangi birini yüklerse, bu uygulama **Uyumsuz Uygulamalar Raporları**’nda bildirilir..|
|**Kullanıcılar listelenmeyen uygulamaları yüklediğinde uyumsuzluğu bildir**|Kullanıcıların yüklemesine izin verilen Mac OS X uygulamalarını listeler. Kullanıcılar başka herhangi bir uygulamayı yüklerse, bu uygulama **Uyumsuz Uygulamalar Raporları**’nda bildirilir..|
|**Ekle**|Seçili listeye bir uygulama ekler. Tercih ettiğiniz bir adı, (isteğe bağlı olarak) uygulama yayımcısını ve uygulamanın paket kimliğini belirtin. **İpucu:** Uygulamanın paket kimliğini bulmak için, uygulamanın yüklendiği Mac bilgisayarda aşağıdaki adımları izleyin:<ol><li>Uygulamanın yüklendiği klasörü açın (örneğin, **/Uygulamalar**)</li><li>*&lt;Uygulama Adı&gt;***.app** paketini seçin ve **Paket İçeriğini Göster**’i seçin.</li><li> **Info.plist** dosyasını açın</li><li> **CFBundleIdentifier**anahtarıyla ilişkilendirilmiş değeri denetleyin</li></ol>Paket kimliği, **com.contoso.uygulamaadı**biçiminde olur|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış bir değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarır. Dosyadaki biçimi, uygulama adını, yayımcıyı ve uygulama paketi kimliğini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve uygulama paket kimliğini düzenlemenize olanak tanır.|
|**Sil**|Seçilen uygulamayı listeden siler.|
> [!TIP]
> Intune raporları hakkında daha fazla bilgi için bkz. [Raporları kullanarak Microsoft Intune işlemlerini anlama](understand-microsoft-intune-operations-by-using-reports.md)..

> [!IMPORTANT]
> Mac OS X cihazı Uyku modundayken, ilkeler ve profiller teslim edilemez veya envantere kaydedilemez. Sonuç olarak, cihazın Uyku modundan bir sonraki çıkarılışına kadar Intune konsolu geçici olarak **Hatalı ilke ayarları** durumunu görüntüleyebilir.

### Uyumlu ve uyumsuz uygulamaları izle
 **Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak, belirtilen uygulamaların uyumluluğunu görüntüleyin.

#### Raporu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Raporlar** &gt; **Uyumsuz Uygulamalar Raporları** öğesine tıklayın..

2.  Denetlenmesini istediğiniz cihaz gruplarını seçin, uyumlu uygulamaları mı, uyumsuz uygulamaları mı yoksa her ikisini birden mi denetlemek istediğinizi seçin ve sonra da **Raporu Görüntüle**'ye tıklayın..

## Microsoft Intune’da Mac OS X özel ilke ayarları
[Apple Configurator aracını](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kullanarak oluşturduğunuz ayarları Mac OS X cihazlarına dağıtmak için Microsoft Intune **Mac OS X özel yapılandırma ilkesini** kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune Mac OS X özel ilkesine aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara dağıtabilirsiniz.

Bu özellik, Intune Mac OS X genel yapılandırma ilkesiyle, yapılandırılabilir olmayan Mac OS X ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.

### Önkoşullar
Başlamadan önce, Apple Configurator’ı yüklemiş ve kullanıcılara veya cihazlara dağıtmak istediğiniz ayarları içeren bir yapılandırma dosyası oluşturmuş olmanız gerekir. [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)‘dan Apple Configurator’ı indirebilir ve Apple Configurator hakkında bilgi edinebilirsiniz.

> [!NOTE]
> Intune, bir Mac OS X özel ilkesindeki tek tek ayarların uyumluluğunu raporlamaz. Ancak, ilkenin genel uyumluluğu raporlanır.

### Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için Mac OS X özel ilkesi için benzersiz bir ad girin.|
    |**Açıklama**|Mac OS X özel ilkesine genel bakış sağlayacak ve onu bulmanıza yardımcı olacak diğer uygun bilgilerin yer aldığı bir açıklama girin.|


### Özel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Özel yapılandırma profili adı (kullanıcılara gösterilir)**|Cihazda ve Intune ilke raporlarında görüntülenecek şekilde ilke için bir ad sağlayın.|
    |**Yapılandırma profili dosyası**| **İçeri aktar**‘a tıklayın, ardından Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline göz atın. **İpucu:** Yapılandırma profilini oluştururken yardımcı olması için, bu konunun [Yapılandırma profili dosyası oluşturma](#BKMK_Prof) bölümüne bakın.|
    |**Yapılandırma profili ayrıntıları**|İçeri aktardığınız yapılandırma profili için xml kodunu görüntüler.|



### Bir yapılandırma profili dosyası oluşturma
Özel ilke tarafından kullanılan yapılandırma profili dosyasını iki yolla oluşturabilirsiniz:

-   Dosyaya ( **.mobileconfig**uzantılı dosya) Apple Configurator aracından dışarı aktarın.

-   [Apple Yapılandırma Profili Anahtar Başvurusu](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html) belgesinden uygun şemayı kullanarak dosyayı kendiniz yazın..


> [!IMPORTANT]
> Mac OS X cihazı Uyku modundayken, ilkeler ve profiller teslim edilemez veya envantere kaydedilemez. Sonuç olarak, cihazın Uyku modundan bir sonraki çıkarılışına kadar Intune konsolu geçici olarak **Hatalı ilke ayarları** durumunu görüntüleyebilir.

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


