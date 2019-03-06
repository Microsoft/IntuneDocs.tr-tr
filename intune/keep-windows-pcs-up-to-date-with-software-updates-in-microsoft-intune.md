---
title: Windows bilgisayarları için yazılım güncelleştirmeleri
titlesuffix: Microsoft Intune
description: Intune, en son düzeltme eklerinin ve yazılım güncelleştirmelerinin hızla yüklenmesini sağlayarak yönetilen bilgisayarlarınızı güncel tutmanıza yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 48e9c41a-d2de-424e-9610-cfd1ad514210
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 381802de52f63cd4d7c836dbabe25167c0370ee5
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57460683"
---
# <a name="keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune"></a>Microsoft Intune’da yazılım güncelleştirmeleri ile Windows bilgisayarlarını güncel tutma

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Microsoft Intune, en son düzeltme eki ve yazılım güncelleştirmelerinin hızla yüklenmesini sağlayan yazılım güncelleştirmelerinin yönetilmesi de dahil olmak üzere çeşitli yollarla yönetilen bilgisayarlarınızı korumanıza yardımcı olabilir.

Intune istemcisini bilgisayarlarınıza henüz yüklemediyseniz, bkz. [Microsoft Intune ile Windows bilgisayarı istemcisini yükleme](install-the-windows-pc-client-with-microsoft-intune.md).

Microsoft Update'te kullanılabilir yeni güncelleştirmeler olduğunda veya üçüncü taraf bir güncelleştirme oluşturduğunuzda ve bunlar yönetilen bilgisayarlarınız için geçerli olduğunda, **Güncelleştirmeler** çalışma alanının **Genel Bakış** sayfasında bir bildirim görüntülenir. Bu bildirim bağlantısını seçtikten sonra, güncelleştirme hakkında daha fazla bilgi görüntüleme, güncelleştirmeyi onaylama veya reddetme ve güncelleştirme onaylanırsa güncelleştirmenin yükleneceği bilgisayarları görüntüleme gibi çeşitli işlemler gerçekleştirebilirsiniz.

> [!IMPORTANT]
> **Güncelleştirmeler** çalışma alanı, istemciyi yükleyene ve en az bir bilgisayar istemcisini başarıyla yönetene kadar yönetici konsolunda görüntülenmez.

Güncelleştirmeler onaylanıp yüklendiği sırada, Intune konsolunun **Güncelleştirmeler** çalışma alanında yüklemenin başarılı olup olmadığını inceleyebilirsiniz.

Aşağıdaki bölümler, yönetilen bilgisayarlarınızdaki yazılımları güncel tutmanıza yardımcı olur.

## <a name="before-you-start"></a>Başlamadan önce
Yazılım güncelleştirmeleri oluşturmaya ve onaylamaya başlamadan önce, güncelleştirmelerin ne zaman ve nasıl yükleneceğini denetleyen ilkeler yapılandırın ve bilgisayarlarınıza dağıtın.

### <a name="to-configure-update-policy-settings"></a>Güncelleştirme ilkesi ayarlarını yapılandırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **İlke** &gt; **Genel Bakış** &gt; **İlke Ekle**’yi seçin.

2.  Güncelleştirme ayarları için bir **Microsoft Intune Aracısı Ayarları** ilkesi yapılandırın ve dağıtın. Önerilen ayarları kullanabilir veya ayarları özelleştirebilirsiniz. İlke oluşturma ve dağıtma hakkında daha fazla bilgi için, bkz. [Microsoft Intune bilgisayar istemcisi ile genel Windows bilgisayarı yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

Aşağıdaki tabloda, ilkede yapılandırabileceğiniz değerlerin yanı sıra, ilkeyi özelleştirmezseniz kullanılacak önerilen değerler gösterilmektedir. Bu ayarları **Güncelleştirmeler** bölümünde bulabilirsiniz.

  |İlke ayarı|Ayrıntılar|
    |------------------|--------------------|
    |**Güncelleştirme ve uygulama algılama sıklığı (saat)** |Intune’un yeni güncelleştirme ve uygulamaları ne sıklıkta (8-22 saat) denetleyeceğini belirtir.<br /><br />Önerilen değer: **8** saat.|
    |**Uygulamaları ve güncelleştirmeleri otomatik olarak veya istendiğinde yükleme** |Güncelleştirmelerin otomatik olarak mı yükleneceğini yoksa yüklenmeden önce kullanıcıya sorulup sorulmayacağını belirtir. Ek olarak, bu ayar, güncelleştirmelerin ve uygulamaların yüklenmesini zamanlamanıza imkan sağlar.<br /><br />**Güncelleştirmeleri ve uygulamaları zamanlamaya göre otomatik yükle** seçeneği, güncelleştirmeleri ve uygulamaları belirtilen zamanlamayı kullanarak yükler.<br /><br />Bağımlı bir ilke ayarı olarak **Windows bilgisayarları için Otomatik Bakım'ı Kullan**  seçeneği, güncelleştirmelerin ve uygulamaların Windows Otomatik bakım penceresi sırasında yükleneceğini belirtir.<br /><br />**Yükleme için kullanıcıya sor** seçeneği, güncelleştirmeler hazır olduğunuzda bunların yüklenip yüklenmeyeceğini kullanıcıya sorar.<br /><br />Önerilen değerler:<br /><br />**Güncelleştirmeleri ve uygulamaları zamanlamaya göre otomatik yükle** seçili<br /><br />**Zamanlanan gün: Her gün**<br /><br />**Zamanlanan saat: 3: 00'DA**<br /><br />**Windows bilgisayarları için Otomatik Bakım'ı kullan** seçili|
    |**Windows'u kesintiye uğratmayan güncelleştirmelerin hemen yüklemesine izin ver** |**İzin ver** seçeneği, Windows'u kesintiye uğratacak veya yeniden başlatacak güncelleştirmeler dışındaki güncelleştirmeleri indirildikten hemen sonra yükler. Bu güncelleştirmeler, **Güncelleştirmelerin otomatik veya istendiğinde yüklenmesi** ayarının yapılandırmasına göre yüklenir.<br /><br />**İzin verme** seçeneği, güncelleştirmeleri **Güncelleştirmelerin otomatik veya istendiğinde yüklenmesi** ayarının yapılandırmasına göre yükler.<br /><br />Önerilen değer: **İzin ver** |
    |**Zamanlanmış güncelleştirmeler ve uygulamalar yüklendikten sonra Windows'u yeniden başlatmayı geciktir (dakika)** |Zamanlanmış güncelleştirmeler ve uygulamalar yüklendikten sonra Windows'u yeniden başlatmak için beklenecek süreyi (1-30 dakika arasında) belirtir.<br /><br />Önerilen değer: **15 dakika** |
    |**Windows yeniden başlatıldıktan sonra kaçırılan zamanlanmış güncelleştirme ve uygulamaların yüklenmeye başlamasını geciktir (dakika)** |Zamanlanmış bir güncelleştirmenin kaçırılması durumunda, Windows yeniden başlatıldıktan sonra güncelleştirme ve uygulamaların yüklenmeye başlaması için ne kadar bekleneceğini (1-60 dakika arasında) belirtir.<br /><br />Önerilen değer: **5 dakika**|
    |**Zamanlanan güncelleştirmeler ve uygulamalar yüklendikten sonra oturum açan kullanıcının Windows'un yeniden başlatılmasını denetlemesine izin ver** |Oturum açan kullanıcının Windows'un yeniden başlatılmasını geciktirip geciktiremeyeceğini (**Evet** olarak ayarlanırsa) veya otomatik Windows yeniden başlatma işleminin kullanıcıya bildirilip bildirilmeyeceğini (**Hayır** olarak ayarlandıysa) belirtir. Güncelleştirmelerin ve uygulamaların zamanlanan yüklemesi tamamlandığında oturum açmış bir kullanıcı yoksa, Windows gerektiğinde otomatik olarak yeniden başlatılır. **Hayır**olarak ayarlandığında, varsayılan olarak, Windows yeniden başlatılmadan önce geçecek süre 5 dakika olarak ayarlanmıştır.<br /><br />Önerilen değer: **Evet**|
    |**Intune istemci aracısı zorunlu güncelleştirmeleri sırasında kullanıcının Windows'u yeniden başlatmasını iste** |Intune istemci aracısı zorunlu güncelleştirmesi Windows'un yeniden başlatılmasını gerektirdiğinde, oturum açmış kullanıcılardan Windows'u yeniden başlatmalarının istenip istenmeyeceğini belirtir.<br /><br />Önerilen değer: **Evet**|
    |**Microsoft Intune istemci aracısı zorunlu güncelleştirmeleri yükleme zamanlaması** |İstemci güncelleştirmelerinin ne zaman yükleneceğini zamanlar.<br /><br />Önerilen değer: yapılandırılmadı|
    |**Zamanlanmış güncelleştirmeler ve uygulamalar yüklendikten sonra Windows'u yeniden başlatma istekleri arasındaki gecikme (dakika)** |Windows'un yeniden başlatılmasını gerektiren bir zamanlanan güncelleştirme veya uygulama yüklendiğinde ve kullanıcı yeniden başlatmayı geciktirdiğinde, Windows'un yeniden başlatılmasının kullanıcıya ne sıklıkla (1-1440 dakika arasında) sorulacağını belirtir.<br /><br />Önerilen değer: **30 dakika** |

## <a name="update-software-made-by-microsoft"></a>Microsoft tarafından oluşturulan yazılımları güncelleştirme
Microsoft yazılımlarını güncelleştirme, sizin çok az şey yapmanızı gerektirir. Ancak, başlamadan önce yapılandırmanız gereken iki ayar vardır:

-   **Ürün kategorileri ve güncelleştirme sınıflandırmaları** – Bilgisayarlar için kullanılabilir hale getirmek istediğiniz güncelleştirme kategorilerini ve sınıflandırmalarını tanımlar. Örneğin, yalnızca Microsoft Office için kritik güncelleştirmelerin yüklenmesini tercih edebilirsiniz.

-   **Otomatik onay kuralları** – Bu kurallar, belirtilen türdeki güncelleştirmeleri otomatik olarak onaylar ve yönetim yükünüzü azaltır. Örneğin, tüm kritik yazılım güncelleştirmelerini otomatik olarak onaylamak isteyebilirsiniz.

Yazılım güncelleştirmelerini kullanmaya hazırlanmanıza yardımcı olacak şu iki yordamı kullanın:

### <a name="configure-the-product-categories-and-update-classifications-you-want-to-make-available-to-managed-computers"></a>Yönetilen bilgisayarlar için kullanılabilir hale getirmek istediğiniz ürün kategorilerini ve güncelleştirme sınıflandırmalarını yapılandırın

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Yönetici**&gt;**Güncelleştirmeler**’i seçin.

2.  Üzerinde **hizmet ayarları: Güncelleştirmeleri** sayfasında **ürün kategorisi** listesinden, bilgisayarlar için kullanılabilir hale getirmek istediğiniz güncelleştirme kategorilerini seçin. En yaygın güncelleştirmelerin varsayılan olarak seçildiğini unutmayın.

    > [!IMPORTANT]
    > Bilgisayarların yönetici tarafından onaylanan güncelleştirmeleri aldığından emin olmak için Windows Server Update Services (WSUS) Grup İlkesi ayarı olan **Intranet Microsoft güncelleştirme hizmeti konumunu belirtin** ayarının Intune’a kaydedilen bilgisayarlara uygulanmadığından emin olun.

3.  **Güncelleştirme Sınıflandırması** listesinde, yönetilen bilgisayarlar için kullanılabilir hale getirmek istediğiniz güncelleştirme sınıflarını seçin. Burada da en yaygın seçenekler varsayılan olarak seçilidir.

4.  Seçimlerinizi depolamak için **Kaydet**’i seçin.

### <a name="to-configure-automatic-approval-rules-for-software-updates"></a>Yazılım güncelleştirmeleri için otomatik onay kurallarını yapılandırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Yönetici**&gt;**Güncelleştirmeler**’i seçin.

2.  İçinde **otomatik onaylama kuralları** bölümünü **sunucu ayarları: Güncelleştirmeleri** sayfasında **yeni**.

3.  Otomatik Onay Kuralı Oluştur Sihirbazı'nın **Genel** sayfasında, kural için bir ad ve isteğe bağlı bir açıklama belirtin.

4.  **Ürün Kategorileri** sayfasında, hangi ürünler için güncelleştirmelerin otomatik olarak onaylanmasını istediğinizi seçin.

5.  **Güncelleştirme Sınıflandırmaları** sayfasında, otomatik olarak onaylanmasını istediğiniz güncelleştirme sınıflandırmalarını belirtin.

6.  **Dağıtım** sayfasında, aşağıdakileri yapın:

    -   Yeni kuralı dağıtmak istediğiniz bilgisayar gruplarını seçin ve sonra da **Ekle**'yi seçin.

    -   Güncelleştirmeler için bir yükleme son tarihi belirlemek üzere **Bu güncelleştirmeler için bir son yükleme tarihi zorla** onay kutusunu seçin ve ardından **Son yükleme tarihi** listesinde, son yükleme tarihini seçin.

        > [!NOTE]
        > Bir son yükleme tarihi belirtirseniz, son tarih aralığı geçtikten sonra yönetilen bilgisayarın bir veya birden çok kez yeniden başlatılması gerekebilir.

    -   İşiniz bittiğinde **İleri**’yi seçin.

7.  **Özet** sayfasında, yeni kuralın ayarlarını gözden geçirin ve ardından **Son**'u seçin.

Yeni kural **otomatik onaylama kuralları** bölümünü **hizmet ayarları: Güncelleştirmeleri** sayfası.

> [!NOTE]
> Bir otomatik onay kuralı oluşturduğunuzda, kural yalnızca gelecekteki güncelleştirmeleri onaylar ve Intune’da önceden var olan güncelleştirmeleri otomatik olarak onaylamaz. Bu güncelleştirmeleri onaylamak için otomatik onay kuralını çalıştırmanız gerekir.


### <a name="to-edit-run-or-delete-an-automatically-approved-update-rule"></a>Bir otomatik onaylı güncelleştirme kuralını düzenlemek, çalıştırmak veya silmek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Yönetici**&gt;**Güncelleştirmeler**’i seçin.

2.  **Otomatik Onaylama Kuralları** bölümünde, bir kural seçin ve aşağıdakilerden birini yapın:

    -   Kuralı düzenlemek için **Düzenle**'yi seçin ve sonra **Güncelleştirme Otomatik Onay Kuralı Sihirbazı**'nda kuralın parametrelerini değiştirin.

    -   Kuralı çalıştırmak için **Seçileni Çalıştır**'ı seçin.

    -   Kural silmek için **Sil**'i seçin.

        > [!NOTE]
        > Bir kuralın silinmesi, silinen kural tarafından onaylanan önceki güncelleştirmeleri etkilemez.

## <a name="update-software-not-made-by-microsoft"></a>Microsoft tarafından oluşturulmayan yazılımları güncelleştirme
Microsoft tarafından yapılmayan yazılım güncelleştirmelerini dağıtabilirsiniz. Bunu **Karşıya Güncelleştirme Yükle** sihirbazını kullanarak güncelleştirmeyi Bulut Depolama alanınıza aktarıp daha sonra tıpkı Microsoft yazılımında olduğu gibi kabul ederek veya reddederek yapabilirsiniz.

### <a name="to-upload-and-configure-a-third-party-update"></a>Üçüncü taraf bir güncelleştirmeyi karşıya yüklemek ve yapılandırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Güncellemeler** &gt; **Genel Bakış** &gt; **Karşıya yükle**’ye tıklayın.

2.  **Güncelleştirme dosyaları** sayfasında, güncelleştirme paketini yüklemek için gereken kurulum dosyalarını seçmek için **Gözat**'ı seçin. Dosya bir Windows Installer (.msi) dosyası, Windows Installer düzeltme eki (.msp) dosyası veya .exe program dosyası olabilir. Ayrıca, kurulum dosyası ile aynı klasörde olan ek dosya veya klasörleri de ekleyebilirsiniz.

    Karşıya yüklenmek üzere seçilen dosyaların toplam boyutu görüntülenir. Bu boyutun, yükleme dosyalarının sıkıştırılmamış veya genişletilmiş boyutlarını içermediğini unutmayın.

3.  Kurulum dosyalarını belirttikten sonra, **Güncelleştirme açıklaması** sayfasında Intune tarafından yazılım kurulum dosyalarından ayıklanan yazılım bilgileri için ad, açıklama ve sınıflandırma görüntülenir. Dağıttığınız güncelleştirmenin türünü (Güncelleştirmeler, Kritik Güncelleştirmeler, Güvenlik Güncelleştirmeleri, Güncelleştirme Paketleri veya Hizmet Paketleri) etiketlemek için bir sınıflandırma seçebilirsiniz. Bitirdiğinizde **İleri**’yi seçin.

4.  Sihirbazın **Gereksinimler** sayfasında mimariyi (32 bit, 64 bit veya her ikisi de) ve bu güncelleştirmenin geçerli olacağı tüm yönetilen bilgisayarların işletim sistemlerini seçin.

5.  **Algılama Kuralları** sayfasında, Intune tarafından güncelleştirmenin yönetilen bilgisayarlarda zaten var olup olmadığının nasıl belirleneceğini belirtin. Varsayılan seçenek olan **Varsayılan algılama kurallarını kullan**seçeneğini kullanırsanız, Intune güncelleştirme paketini hedeflenen bilgisayarlarda her zaman tek bir kez yükler.

    > [!NOTE]
    > Belirttiğiniz güncelleştirme kurulum dosyası bir Windows Installer veya .msp dosyası ise sihirbazın **Algılama kuralları** sayfası görünmez. Bunun nedeni, Windows Installer ve .msp dosyalarının önceki güncelleştirme yüklemelerini algılamak için kendi yönergelerini içermesidir.

    Güncelleştirmenin yönetilen bilgisayarlarda yüklü olup olmadığını belirlemek için aşağıdaki kurallardan birini veya daha fazlasını seçin:

    -   **Dosya var**

    -   **MSI ürün kodu var**

    -   **Kayıt defteri anahtarı var**

6.  Algılama kuralının yapılandırılması için bir dosya yolu ve adı, Windows Installer ürün kodu veya bir kayıt defteri anahtarı gibi ek bilgileri sağlayın ve ardından **İleri**'yi seçin.

7.  Sihirbazın **Önkoşullar** sayfasında, bu güncelleştirme yüklenmeden önce yüklü olması gereken bir yazılım varsa bu yazılımı belirtirsiniz. **Hiçbiri**'ni belirtip zaten Intune’a eklenmiş olan ve Intune tarafından yönetilen bir yazılım paketi seçebilir veya yazılımı açıklamak için aşağıdaki kurallardan birini belirtebilirsiniz:

    -   **Dosya var**

    -   **MSI ürün kodu var**

    -   **Kayıt defteri anahtarı var**

8.  Algılama kuralının yapılandırılması için bir dosya yolu ve adı, Windows Installer ürün kodu veya bir kayıt defteri anahtarı gibi ek bilgileri sağlayın ve ardından **İleri**'yi seçin.

9. Sihirbazın **Komut satırı bağımsız değişkenleri** sayfasında kurulum dosyasının davranışını değiştirmek için yükleme komut satırına tüm gerekli yükleme özelliklerini ekleyebilirsiniz. Örneğin, bazı yazılımlar **/q** özelliğinin sessiz yüklemeyi etkinleştirmesini destekler. Desteklenen tüm komut satırı bağımsız değişkenleri hakkında bilgi edinmek için yazılım paketinize yönelik belgelere bakın. İhtiyacınız olan tüm komut satırı bağımsız değişkenlerini belirtin ve ardından **İleri**'yi seçin.

    > [!NOTE]
    > Güncelleştirme sessiz yüklemeyi desteklemiyorsa, güncelleştirmeyi Intune kullanarak yükleyemezsiniz.

10. Sihirbazın **Dönüş kodları** sayfasında, güncelleştirme kurulumundan gelen dönüş kodlarının nasıl yorumlanacağını belirtebilirsiniz. Varsayılan olarak, Intune bir güncelleştirme paketinin başarıyla yüklenip yüklenmediğini raporlamak için endüstri standardı dönüş kodlarını kullanır. Sağlanan dönüş kodları şunlardır:

|Dönüş kodu|Ayrıntılar|
|---------------|------------------|
|**0**|Başarılı|
|**3010**|Yeniden başlatma ile başarılı|

11. Listede olmayan herhangi bir geri dönüş kodu bir hata olarak kabul edilir.
Bazı güncelleştirmeler, dönüş kodları için standart olmayan yorumlar kullanır. Bu durumda, kendi dönüş kodu yorumlarınızı belirtebilirsiniz.

12. Gerekli dönüş kodlarını belirtin veya düzenleyin ve ardından **İleri**'yi seçin.

13. Sihirbazın **Özet** sayfasında, gerçekleştirilecek eylemleri gözden geçirin ve ardından **Karşıya yükle**'yi seçerek sihirbazı tamamlayın.

Karşıya yüklenen güncelleştirme, Intune bulut depolama alanınızda depolanır. Güncelleştirme paketini karşıya yüklemek için yeterli boş alanınız yoksa bu durum karşıya yükleme işlemi sırasında size bildirilir. Sıkıştırılmış yükleme dosyaları açıldığında daha fazla alan gerektirdiğinden, Intune karşıya yükleme işlemi başlayana kadar yeterli boş alan olup olmadığını belirleyemez.

Güncelleştirme Intune’a yüklendikten sonra, **Tüm Güncelleştirmeler** bölmesinin **Güncelleştirmeler** çalışma alanında üçüncü taraf bir güncelleştirme görüntülenir. Ardından, güncelleştirmeyi onaylayabilir ve dağıtabilirsiniz. Daha fazla bilgi için, aşağıdaki "Güncelleştirmeleri onaylama ve reddetme" bölümüne bakın.

## <a name="approve-and-decline-updates"></a>Güncelleştirmeleri onaylama ve reddetme
Güncelleştirmeler yüklenmeye hazır olduğunda, **Güncelleştirmeler** çalışma alanındaki **Güncelleştirmelere Genel Bakış** sayfasının **Güncelleştirme Durumu**bölümünde bir ileti gösterilir. Hangi güncelleştirmelerin onaya hazır olduğunu görmek için, bu iletiyi seçerek **Tüm Güncelleştirmeler** sayfasını açın.

Güncelleştirmeleri bulmayı kolaylaştırmak için **Filtreler** listesini kullanabilirsiniz. Örneğin, yalnızca başarısız güncelleştirmeleri veya değiştirilen güncelleştirmeleri görüntüleyebilirsiniz.

Listeden bir güncelleştirme seçtiğinizde, aşağıdaki tabloda gösterildiği gibi güncelleştirmeleri yönetmenize imkan sağlayan daha fazla komut bulabilirsiniz:

|Görev|Ayrıntılar|
|--------|--------------------|
|**Özellikleri Görüntüle**|Kaç bilgisayar için geçerli olduğu da dahil olmak üzere güncelleştirme hakkında ayrıntılı bilgi görüntüler.|
|**Düzenle**|Yalnızca Microsoft dışı güncelleştirmeler için. Güncelleştirmenin özelliklerini düzenlemenize olanak sağlar.|
|**Onayla**|Seçilen güncelleştirmeyi onaylar ve güncelleştirmenin hangi gruplara dağıtılacağını yapılandırmanıza olanak sağlar. Daha fazla bilgi için bu konuda başlığı altındaki **Güncelleştirmeleri onaylamak için** yordamına bakın.|
|**Reddet**|Güncelleştirme için önceki tüm onayları kaldırır ve güncelleştirmeyi varsayılan görünümlerden gizler. Ayrıca, güncelleştirme için tüm rapor verileri kaldırılır.<br /><br />Reddedilen bir güncelleştirmeyi daha sonra bulmak isterseniz, **Tüm Güncelleştirmeler** sayfasındaki filtreyi **Reddedildi**olarak ayarlayın. Daha sonra bu güncelleştirmeyi gerektiği gibi onaylayabilirsiniz.<br /><br />Bir güncelleştirme Microsoft Update'te süresi dolduğu için reddedildiyse, bu güncelleştirme Intune yönetim konsolunda onaylanamaz.<br /><br />Bilgisayarlara dağıtılan bir güncelleştirme İlkesini silerseniz, bu güncelleştirme ilkesi ayarlarının değerleri, bilgisayarlarda yüklü işletim sistemi için varsayılan duruma sıfırlanır.|
|**Silme**|Yalnızca Microsoft dışı güncelleştirmeler için. Seçili güncelleştirmeyi siler.|
|**Karşıya yükle**|Dağıtmak istediğiniz Microsoft dışı güncelleştirmeleri karşıya yüklemenize olanak sağlayan **Güncelleştirmeyi Karşıya Yükle** sihirbazını başlatır.|

### <a name="to-approve-updates"></a>Güncelleştirmeleri onaylamak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/), **Güncellemeler** &gt; **Genel Bakış** &gt; **Onaylanacak yeni güncellemeler**’i seçin.

    **Güncelleştirmeler** çalışma alanında, **Genel bakış** &gt; **Onaylanacak yeni güncelleştirmeler**'i seçin.

    > [!NOTE]
    > **Onaylanacak yeni güncelleştirmeler** bağlantısı, **Güncelleştirme Durumu** alanında, yalnızca güncelleştirme onayı gereken en az bir yönetilen bilgisayar olduğunda görünür.

2.  Bir güncelleştirme seçin, güncelleştirmeyi onaylamak istediğinizden emin olmak için sayfanın altındaki güncelleştirme özelliklerini gözden geçirin ve ardından **Onayla**'yı seçin. Her bir öğeyi seçerken **CTRL** tuşunu basılı tutarak birden çok güncelleştirme seçebilirsiniz.

3.  **Grup Seç** sayfasında, güncelleştirmeleri dağıtmak istediğiniz bir grup seçin ve ardından **Ekle**'yi seçin. Grupları belirtmeyi tamamladığınızda **İleri**'yi seçin.

4.  **Dağıtım Eylemi** sayfasında, listedeki her grup için aşağıdakileri yapın:

    -   **Onay** listesinde, aşağıdakilerden birini seçin:

        -   **Gerekli Yükleme** - Güncelleştirmeyi belirtilen gruptaki bilgisayarlara yükler.

        -   **Yükleme** - Yalnızca uygulanabilirliği raporlar ve güncelleştirmeyi yüklenmez.

        -   **Kullanılabilir Yükleme** – Kullanıcı, uygulamayı isteğe bağlı olarak Şirket Portalı'ndan yükleyebilir.

        -   **Kaldır** - Hedeflenen gruptaki bilgisayarlardan güncelleştirmeleri kaldırır.

            > [!IMPORTANT]
            > Güncelleştirme, Intune tarafından yüklenmemiş olsa bile kaldırılır.

    -   **Son Tarih** listesinde, aşağıdakilerden birini seçin:

        -   **Hiçbiri** - Güncelleştirme yüklenmesi için zorlanan bir son tarih olmadığını ve kullanıcıların güncelleştirmeyi sürekli olarak reddedebileceğini belirtir.

        -   **En kısa sürede** - Güncelleştirmeyi bir sonraki fırsatta hedef bilgisayarlara yükler.

        -   **Özel** - Onaylanan güncelleştirmelerin yükleneceği saat ve tarihi belirtir.

        -   **Bir hafta**, **İki hafta**, **Bir ay** – Güncelleştirmeyi belirtilen süre içinde yükler.

5.  Ayarları kaydetmek için **Son**'u seçin veya ayarları atıp güncelleştirmeler listesine dönmek için **İptal**'i seçin.

    > [!IMPORTANT]
    > Bir alt grup için açıkça **Yükleme**, **Gerekli Yükle**veya **Kaldır** eylemi yapılandırılmadığı sürece, üst grup için yapılandırılan bir eylem tüm alt gruplar tarafından devralınır.

6.  Güncelleştirme hakkında anımsatma iletileri için **Tüm Güncelleştirmeler** sayfasının altındaki ayrıntılar bölmesini denetleyebilirsiniz.


### <a name="see-also"></a>Ayrıca bkz.
[Windows bilgisayarlarını koruma ilkeleri](policies-to-protect-windows-pcs-in-microsoft-intune.md)
