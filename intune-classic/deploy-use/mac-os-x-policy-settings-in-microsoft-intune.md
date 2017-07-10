---
title: "Mac OS X ilke ayarları"
description: "Intune, Mac OS X cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Ayrıca, Intune'dan kullanılamayan özel ayarları oluşturmak için Apple Configurator aracını kullanabilirsiniz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4f1660f93724ee57f2d6567c2ac0f04660f49f8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="mac-os-x-configuration-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Mac OS X yapılandırma ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, Mac OS X cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Ayrıca, Intune'dan kullanılamayan özel ayarları oluşturmak için Apple Configurator aracını kullanabilirsiniz.

## <a name="general-configuration-policy-settings"></a>Genel yapılandırma ilkesi ayarları

Microsoft Intune **Mac OS X genel yapılandırma ilkesini** kullanarak aşağıdaki ayarları yapılandırabilirsiniz:

-   **Cihaz güvenliği ayarları**. Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Uyumlu ve uyumsuz uygulamalar**. Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini belirtin. Uyumsuz Uygulamalar Raporu’yla, listede belirttiğiniz uygulamalarla kullanıcıların yüklediği uygulamalar karşılaştırılarak uyumlu olup olmadığı görüntülenebilir (ancak uygulamanın yüklenmesi engellenemez).

Aradığınız özellik bu listede görünmüyorsa, Apple Configurator aracını kullanarak oluşturduğunuz ayarları içeri aktarmanızı sağlayan bir Mac OS X özel ilkesi kullanarak bu özelliği oluşturabilirsiniz. Daha fazla bilgi için, bu konunun devamındaki “Özel ilke ayarları” bölümüne bakın.

### <a name="password-settings"></a>Parola ayarları

|Ayar adı|Ayrıntılar|
|----------------|---------------|
|**Cihazların kilidini açmak için parola gerektir**|Kullanıcının Mac bilgisayarına erişmek için parola kullanmasının gerekip gerekmediğini belirtin. **Önemli**: iOS cihazlarından farklı olarak, Mac OS X cihazlarında bu ayarla uyumluluğu korumak için parolasını güncelleştirmesi gerektiği kullanıcıya hemen bildirilmez.|
|**Gerekli parola türü**|Parolanın yalnızca **Sayısal** olabileceğini ya da **Alfasayısal** (harfler ve sayılar içeren) olması gerektiğini belirtin. **Önemli**: Bu ayar yalnızca Mac OS X sürüm 10.10.3 ve üzerinde desteklenir.|
|**Parolada gerekli karmaşık karakter sayısı**|Parolada kullanılması gereken karmaşık karakterlerin sayısını belirtin (**0**-**4** karakter).<br /><br />Karmaşık karakterler, **?** gibi simgelerdir.|
|**En düşük parola uzunluğu**|Parola için minimum uzunluğu belirtin (**4**-**14** karakter) .|
|**Basit parolalara izin ver**|**0000** veya **1234** gibi basit parolaların kullanımına izin verin.|
|**Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Bilgisayarın ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtin.|
|**Parola kullanım süresi (gün)**|Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtin (**1**-**255** gün).|
|**Parola geçmişini anımsa**|Kullanıcının daha önce kullanılmış bir parolayı kullanmasını engelleyin. Bu seçenek ayarlandığında, önceden kullanılmış olan parolalardan yeniden kullanılamayacak olanların sayısını belirtmek için **Önceki parolaların yeniden kullanılmasını önle** seçeneğini de ayarlayabilirsiniz (**1**-**24** arası).|
|**Ekran koruyucu etkinleştirilmeden önce işlem yapılmadan geçen süre**|Ekran koruyucu etkinleştirilmeden önce bilgisayarın boşta bekleyeceği süreyi belirtir.|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Mac OS X için Uyumlu ve Uyumsuz Uygulamalar** listesinde, **Cihazlar için yönetilen ayarlar**’ı etkinleştirin ve sonra aşağıdaki bilgileri kullanarak uyumlu veya uyumsuz uygulamalar listesini belirtin.

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların bir listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.
>
> Intune, uyumsuz uygulamalar içeren cihazları raporlamanızı sağlar. Yüklemeyi engellemez veya uyumsuz uygulamaları kaldırmaz.

|Ayar adı|Ayrıntılar|
|----------------|---------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Kullanıcıların yüklemesine izin verilmeyen Mac OS X uygulamalarını gösterir. Kullanıcılar bu uygulamalardan herhangi birini yüklerse, bu uygulama **Uyumsuz Uygulamalar Raporu**’nda bildirilir.|
|**Kullanıcılar listelenmeyen uygulamaları yüklediğinde uyumsuzluğu bildir**|Kullanıcıların yüklemesine izin verilen Mac OS X uygulamalarını gösterir. Kullanıcılar başka bir uygulama yüklerse, bu uygulama **Uyumsuz Uygulamalar Raporu**’nda bildirilir.|
|**Ekle**|Seçili listeye bir uygulama ekleyin. Tercih ettiğiniz bir ad ve isteğe bağlı olarak uygulama yayımcısını ve uygulama paket kimliğini belirtin. **İpucu:** Uygulamanın paket kimliğini bulmak için, uygulamanın yüklendiği Mac bilgisayarda aşağıdaki adımları izleyin:<ol><li>Uygulamanın yüklendiği klasörü açın (örneğin, **/Uygulamalar**).</li><li>*&lt;Uygulama Adı&gt;***.app** paketini ve ardından **Paket İçeriğini Göster**’i seçin.</li><li>**Info.plist** dosyasını açın.</li><li>**CFBundleIdentifier**anahtarıyla ilişkilendirilmiş değeri kontrol edin.</li></ol>Paket kimliği, **com.contoso.uygulamaadı** biçiminde olur.|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış bir değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarın. Dosyada şu biçimi kullanın: uygulama adı, yayımcı ve uygulama paketi kimliği.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve uygulama paket kimliğini düzenleyin.|
|**Sil**|Seçilen uygulamayı listeden silin.|
> [!TIP]
> Intune raporları hakkında daha fazla bilgi için bkz. [Raporları kullanarak Microsoft Intune işlemlerini anlama](understand-microsoft-intune-operations-by-using-reports.md).

> [!IMPORTANT]
> Bir Mac OS X cihazı uyku modundayken ilkeler ve profiller teslim edilemez veya envantere kaydedilemez. Sonuç olarak, cihazın uyku modundan bir sonraki çıkarılışına kadar Intune konsolu geçici olarak **Hatalı ilke ayarları** durumunu gösterebilir.

### <a name="monitor-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumsuz uygulamaları izle
**Uyumsuz Uygulamalar Raporu**'nu kullanarak belirtilen uygulamaların uyumluluğunu görüntüleyin.

#### <a name="to-run-a-report"></a>Bir rapor çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Raporlar** &gt; **Uyumsuz Uygulamalar Raporları**’nı seçin.

2.  Denetlemek istediğiniz cihaz gruplarını seçin, uyumlu uygulamaları mı, uyumsuz uygulamaları mı yoksa her ikisini birden mi denetlemek istediğinizi belirtin ve sonra **Raporu Görüntüle**’yi seçin.

## <a name="mac-os-x-custom-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Mac OS X özel ilke ayarları
[Apple Configurator aracını](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kullanarak oluşturduğunuz ayarları Mac OS X cihazlarına dağıtmak için Microsoft Intune **Mac OS X özel yapılandırma ilkesini** kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune Mac OS X özel ilkesine aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara dağıtabilirsiniz.

Bu özellik, Intune Mac OS X genel yapılandırma ilkesiyle yapılandırılamayan Mac OS X ayarlarını dağıtmanıza olanak tanır.

### <a name="prerequisites"></a>Önkoşullar
Başlamadan önce, Apple Configurator’ı yüklemiş ve kullanıcılara veya cihazlara dağıtmak istediğiniz ayarları içeren bir yapılandırma dosyası oluşturmuş olmanız gerekir. [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)‘dan Apple Configurator’ı indirebilir ve Apple Configurator hakkında bilgi edinebilirsiniz.

> [!NOTE]
> Intune, bir Mac OS X özel ilkesindeki tek tek ayarların uyumluluğunu raporlamaz. Ancak, ilkenin genel uyumluluğu raporlanır.

### <a name="general-settings"></a>Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için Mac OS X özel ilkesi için benzersiz bir ad girin.|
    |**Açıklama**|Mac OS X özel ilkesine genel bakış sağlayacak ve onu bulmanıza yardımcı olacak diğer uygun bilgilerin yer aldığı bir açıklama girin.|


### <a name="custom-settings"></a>Özel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Özel yapılandırma profili adı (kullanıcılara gösterilir)**|İlke için, cihazda ve Intune ilke raporlarında görüntülenecek şekilde bir ad sağlayın.|
    |**Yapılandırma profili dosyası**|**İçeri aktar**’ı seçin ve sonra Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin. **İpucu:** Yapılandırma profilini oluştururken yardımcı olması için, bu konunun "Yapılandırma profili dosyası oluşturma" bölümüne bakın.|
    |**Yapılandırma profili ayrıntıları**|İçeri aktardığınız yapılandırma profili için XML kodunu görüntüleyin.|



### <a name="how-to-create-a-configuration-profile-file"></a>Bir yapılandırma profili dosyası oluşturma
Özel ilke tarafından kullanılan yapılandırma profili dosyasını iki yolla oluşturabilirsiniz:

-   Dosyaya ( **.mobileconfig**uzantılı dosya) Apple Configurator aracından dışarı aktarın.

-   [Apple Yapılandırma Profili Anahtar Başvurusu](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html) belgesinden uygun şemayı kullanarak dosyayı kendiniz yazın.


### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
