---
# required metadata

title: Windows bilgisayarı yazılımları için lisans sözleşmelerini yönetme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Windows bilgisayarı yazılımları için lisans sözleşmelerini yönetme
Microsoft Intune, Microsoft Toplu Lisanslama sözleşmeleriyle satın alınmış yazılımlar ve diğer yöntemlerle satın alınmış Microsoft ya da Microsoft olmayan yazılımlar için lisans anlaşması bilgilerini eklemenizi ve yönetmenizi sağlar. Ayrıca bu bilgileri mantıksal gruplar halinde düzenleyebilirsiniz.

> [!IMPORTANT]
> Bu özellik yalnızca kolaylık sağlamak için sunulmuştur ve doğruluğu garanti edilmez. Microsoft Toplu Lisanslama sözleşmeleri ile uyumluluğu buna dayanarak doğrulamamalısınız. Microsoft, bizimle yaptığınız lisans sözleşmelerinin olası ihlal veya uyumunu araştırmak için toplanan verilerden hiçbirini kullanmaz.
> 
> Intune’a eklediğiniz lisanslar, yazılımınızı kullanma yetkilendirmelerinizi veya lisans sözleşmelerinizi etkilemez.  Örneğin, Intune’dan bir lisans/anlaşma çifti silindiğinde, sizinle Microsoft arasındaki lisans sözleşmeleri silinmez veya iptal edilmez.

Intune yönetim konsolunun **Lisanslar** çalışma alanında şunları yapabilirsiniz:

-   Microsoft Toplu Lisanslama sözleşmelerini ekleme ve düzenleme

-   Diğer yazılım lisansı anlaşmalarını ekleme ve düzenleme

-   Lisansları ve grupları yönetme

-   Intune tarafından Toplu Lisanslama Hizmeti Merkezi’nden (VLSC) alınan yetkilendirme bilgilerini, yönetilen Windows bilgisayarlarında Intune tarafından algılanan Microsoft yazılım envanteri ile karşılaştırın.

Buna ek olarak, yazılım başlıkları için yükleme ve lisans sayılarını gösteren lisans raporları da oluşturabilirsiniz. Lisans raporları, Microsoft yazılımı ve Microsoft olmayan yazılım başlıkları için tam lisans konumunuzu değerlendirmenize yardımcı olabilir.

> [!TIP] **Lisanslar** çalışma alanının yönetici konsolunda gösterilmesi için, Intune Windows bilgisayar istemcisiyle en az bir Windows bilgisayarını yönetmeniz gerekir.

## Microsoft Toplu Lisanslama sözleşmelerini ekleme
Intune Toplu Lisans sözleşmeleri, Microsoft Toplu Lisanslama sözleşmeleri ile satın alınan yazılımlar için lisans bilgileri sağlar. Eşleşen anlaşma numarası çiftleri sağlayarak Intune’a Microsoft Toplu Lisanslama anlaşmaları ekleyebilirsiniz. Sözleşme veya yetkilendirme sayıları, doğru lisans ya da kayıt sayılarıyla eşleşmelidir. [Toplu Lisanslama Hizmet Merkezi (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842)içinden lisans sözleşmelerini satın aldığınızda anlaşma numarası çiftleri elde edilir.

1.  [Microsoft Intune yönetici konsolunda](https://account.manage.microsoft.com/admin/default.aspx) **Lisanslar**’a tıklayın.

2.  **Anlaşma Ekle** sayfasındaki **Anlaşma Türünü Seç**’in altında **Toplu Lisanslama anlaşması**’nı seçin.

3.  **Anlaşma Ayrıntıları Ekle** bölümünde aşağıdakilerden birini seçin:

    -   **Anlaşma ayrıntılarını içeren CSV dosyası yükle** - Gözat’a tıklayın ve karşıya yüklemek istediğiniz CSV dosyasını seçin.

        -   Dosya iki veya üç sütun içerebilir. yalnızca sözleşmesi çiftleri için iki tane veya her bir sözleşme çifti için kolay ad eklemek istiyorsanız üç tane.

        -   Bir anlaşma numarası çiftindeki toplam karakter sayısı 16 ASCII karakterden uzun olamaz.

        -   Yalnızca ASCII karakterleri desteklenir.

        -   Anlaşma adında şu karakterlere izin verilmez: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Adda boşluklara izin verilir.

        -   Dosya adı 128 karakterden uzun olmamalıdır.

        -   Dosya en az bir sözleşme çifti içermelidir ve 5.000'den fazla sözleşme çifti içeremez.

        **Dosya için biçimlendirme**

        VLSC’ye kaydettiğiniz kuruluş türüne bağlı olarak aşağıdaki biçimlerden birinde bir düz metin belgesine anlaşma çiftlerinizi ekleyerek bu dosyayı oluşturabilirsiniz. Her satırda tek bir anlaşma numarası çifti belirtin.

        -   **Open Value Müşterileri:** *Anlaşma numarası*, *tekrar anlaşma numarası*, *anlaşma adı*

        -   **Open Müşterileri:** *Yetkilendirme numarası*, *ilgili lisans numarası*, *anlaşma adı*

        -   **Select ve Enterprise Müşterileri:** *Anlaşma numarası*, *ilgili kayıt numarası*, *anlaşma adı*

        **Anlaşma Ekle** formunda, yeni bir anlaşma eklediğinizde bu dosyaya göz atmanız istenir.

        Aşağıda, Açık Değer müşterisi için .csv dosyası içeriğine bir örnek verilmiştir.

        `01-07001, 01-07001, Office agreements`

    -   **Anlaşma ayrıntılarını el ile ekle** - Aşağıdaki bilgileri sağlayın ve **Yetkilendirme/Anlaşma numarası** ve **Lisans/Kayıt/Müşteri numarası** kutularına anlaşma numarası çiftlerini yazın. Her iki numarayı da yazdıktan sonra **Çift ekle** simgesine tıklayarak numaralarınızı kaydedin ve isteğe bağlı olarak yeni bir çift ekleyin.

        -   **Anlaşma adı** - Anlaşma için benzersiz bir ad belirtin.

            Anlaşma adı en fazla 256 karakterden oluşabilir ve şu karakterleri içeremez: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Adda boşluklara izin verilir.

        -   **Yetkilendirme/Anlaşma numarası** - Lisans çiftinin yetkilendirme/anlaşma numarasını girin.

        -   **Lisans/Kayıt/Müşteri numarası** - Lisans çiftinin lisans/kayıt/müşteri numarasını girin.

        > [!NOTE] Birkaç anlaşma numarası çifti eklerseniz, Intune belirttiğiniz adla tek bir anlaşma oluşturur ve eklediğiniz tüm çiftler bu anlaşmanın bir parçası olur.

    Başka bir anlaşma numarası çift eklemek için **+** öğesine veya daha önce girdiğiniz bir anlaşma numarası çiftini kaldırmak için **-** öğesine tıklayabilirsiniz.

4.  **Lisans Grubu Seç** alanında aşağıdakilerden birini yapın:

    -   **Anlaşmaları Atanmamış Anlaşmalar grubuna ekle** Lisans grubuna yeni anlaşmalar eklemek istemiyorsanız bunu seçin.

    -   **Anlaşmaları yeni bir lisans grubuna ekle** - Yeni lisans grubu için bir ad sağlayın.

    -   **Anlaşmaları var olan bir lisans grubuna ekle** - **Grup adı** listesinde, anlaşmaları eklemek istediğiniz lisans grubunu seçin.

5.  **Tamam**'ı tıklatın.

**Tüm Anlaşmalar** görünümü gösterilir ve Intune, sağladığınız anlaşma numarası çiftlerini doğrulamak için Microsoft Toplu Lisanslama Hizmeti Merkezi’ne bağlanır.

Intune’da lisans sözleşmelerini ekledikten sonra toplu lisans bilgilerini güncelleştirmek için, **Lisanslara Genel Bakış** sayfasında **Şimdi Yenile**‘ye tıklayın. Bu eylem, [Microsoft Toplu Lisanslama Hizmet Merkezi (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842)içinden geçerli lisans bilgilerini alır.

> [!IMPORTANT] Toplu lisanslama bilgilerini yenileyinceye kadar, **Anlaşmalara Genel Bakış** sayfasında yetkilendirme bilgilerini ve anlaşma listesinde farklı bilgiler görebilirsiniz.

Toplu lisans bilgilerini yeniledikten sonra lisans bilgilerini, **Uygulamalar** çalışma alanındaki algılanan Microsoft yazılımınızla karşılaştırabilirsiniz. Aşağıdaki lisans raporlarını da çalıştırabilirsiniz:

-   **Lisan Satın Alma Raporları** - Kapsamın açıklarını bulmanıza yardımcı olmak için, seçtiğiniz lisans gruplarındaki lisanslı yazılımları görüntülemenizi sağlar.

-   **Lisans Yükleme Raporları** - Lisans sözleşmenizin kapsamının yeterli olup olmadığını saptamanıza yardımcı olur.

> [!NOTE] Tüm Microsoft Toplu Lisans anlaşmaları için görüntülenen **Ürün Başlığı** **Kullanılamaz** sözcüğüdür.

## Diğer yazılım lisansı anlaşmalarını ekleme ve düzenleme
Intune’a, Microsoft Toplu Lisanslama sözleşmelerinin yanı sıra, başka türlerde lisans sözleşmeleri de ekleyebilirsiniz. Bu sözleşmeler, bir perakendeciden satın alınan Microsoft olmayan yazılımları veya Microsoft yazılımlarını içerebilir.

> [!IMPORTANT]
> Sözleşme ekleyebilmeniz için önce Intune’a en az bir Windows bilgisayarınız kayıtlı olmalıdır.  Ayrıca, en az bir kayıtlı bilgisayarda, lisans sözleşmesi eklemek istediğiniz, lisanslanabilir bir yazılım paketi de yüklemiş olmalıdır.

### Diğer yazılım anlaşmalarını eklemek için

1.  [Microsoft Intune yönetici konsolunda](https://account.manage.microsoft.com/admin/default.aspx) **Lisanslar**’a tıklayın.

2.  **Diğer Yazılım Lisanslama Anlaşmaları** bölümünde **Anlaşma Ekle** ‘ye tıklayın.

3.  **Anlaşma Ekle** sayfasının **Anlaşma Türünü Seç** bölümünde **Diğer yazılım lisanslama anlaşması** öğesini seçin.

4.  **Anlaşma Ayrıntıları Ekle** alanında şunları belirtin:

    -   **Anlaşma adı** (gerekli). Anlaşma adı en fazla 256 karakterden oluşabilir ve şu karakterleri içeremez: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Adda boşluklara izin verilir.

    -   **Yayımcı** (gerekli). Bir yayımcı adı yazmaya başladığınızda hizmet yazdığınız harfleri içeren tüm yayımcı adlarını getirir. Örneğin, "soft" yazarsanız hizmet, adında “soft” geçen tüm yayımcı adlarını getirir; örneğin, “Microsoft" ve "Microsoft Research". Yayımcı adları, Yazılım Varlığı Kataloğundan alınır. Ürün başlığını girebilmeniz için önce yayımcıyı seçmeniz gerekir.

        > [!IMPORTANT]
        > Eklemek istediğiniz şirket bu listede gösterilmiyor olabilir. Yalnızca yazılım varlık kataloğunda zaten var olan şirketler için yazılım anlaşmaları ekleyebilirsiniz. Bununla birlikte, Microsoft en popüler yazılım başlıklarını eklemek için sürekli çalışmaktadır. Bir şirketin bu listeye eklenmesine yönelik bir istek göndermek isterseniz, [Intune Uservoice sitesinde](https://microsoftintune.uservoice.com/)bunu yapabilirsiniz.

    -   **Ürün başlığı** (zorunlu). Bir ürün başlığı yazmaya başladığınızda hizmet yazdığınız harfleri içeren tüm ürün başlıklarını getirir. Bir **Ürün başlığı** belirtebilmeniz için önce bir **Yayımcı**belirtmeniz gerekir.

    -   **Lisans sayısı** (zorunlu). Satın alınan lisans sayısını girin.

    -   **Lisans başlangıç tarihi**. Lisans kapsamı başlangıç tarihini girin.

    -   **Lisans bitiş tarihi**. Lisans kapsamı bitiş tarihini girin.

    -   **Anlaşma ayrıntıları**. İsteğe bağlı olarak, kişi bilgilerini, kayıt anahtarlarını ve diğer bilgileri belirtebilirsiniz.

5.  **Lisans Grubu Seç** alanında aşağıdakilerden birini yapın:

    -   Yeni veya varolan bir lisans grubuna yeni anlaşmalar eklemek istemiyorsanız **Anlaşmaları Atanmamış Anlaşmalar grubuna ekle** öğesini seçin. İstediğiniz zaman kullanıcı tanımlı lisans gruplarına anlaşmalar ekleyebilirsiniz.

    -   Yeni lisans grubuna yeni anlaşmalar eklemek için **Anlaşmaları yeni bir lisans grubuna ekle** öğesini seçin. Yeni lisans grubu için bir ad sağlamanız istenir.

    -   Yeni anlaşmaları varolan bir lisans grubuna eklemek için **Anlaşmaları var olan bir lisans grubuna ekle** öğesini seçin. **Grup adı** listesinde, anlaşmaları eklemek istediğiniz lisans grubunu seçin.

6.  **Tamam**'ı tıklatın.

**Tüm Anlaşmalar** liste görünümü görüntülenir.

## Lisans anlaşmalarını yönetme
Yazılım lisanslama anlaşmaları, lisans gruplarına eklenebilir. Lisans sözleşmelerinizi kuruluşunuz için mantıksal birimler halinde düzenlemek için lisans gruplarını kullanabilirsiniz. Buna ek olarak, daha önce oluşturmuş olduğunuz lisans sözleşmelerini silebilirsiniz.

|||
|-|-|
|Görev|Ayrıntılar|
|Lisans grubu oluşturma|**Lisanslar** çalışma alanının **Genel Bakış** sayfasındaki **Görevler** menüsünde **Lisans Grubu Oluştur** ’a tıklayın. **Not:** Toplamda en fazla 500 lisans grubu oluşturabilirsiniz.|
|Lisans grubunu yeniden adlandırma|**Lisanslar** çalışma alanında bir lisans grubu seçin ve ardından **Görevler** menüsünde **Lisans Grubunu Düzenle** ’ye tıklayın.|
|Lisans grubunu silme|**Lisanslar** çalışma alanında bir lisans grubu seçin ve ardından **Görevler** menüsünde **Lisans Grubunu Sil** ’e tıklayın. **İpucu:** Silinen grubun içindeki tüm lisanslar **Atanmamış anlaşmalar** lisans grubuna taşınır.|
|Lisans sözleşmesini silme|**Lisanslar** çalışma alanında bir anlaşma seçin ve sonra da **Sil**’e tıklayın. **İpucu:** Toplu Lisanslama anlaşmalarını sildikten sonra, lisans bilgilerini güncelleştirmek için, belirli bir lisans grubu için **Genel** sekmesinde veya **Lisanslara Genel Bakış** sayfasında **Şimdi Yenile**‘ye tıklayın.|





<!--HONumber=May16_HO2-->


