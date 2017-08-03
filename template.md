---
title: "MAKALE BAŞLIĞI | HİZMET ADI"
description: 
keywords: 
author: GITHUB USERNAME
manager: ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: GET ONE FROM guidgenerator.com
ms.openlocfilehash: 68090a038cec49009b6bd0ce0515a075f62483b8
ms.sourcegitcommit: 02fb1274ae0dc11288f8bd9cd4799af144b8feae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2017
---
# <a name="metadata-and-markdown-template"></a>Meta Veriler ve Markdown Şablonu

Bu docs.ms şablonu, markdown söz dizimi örneklerinin yanı sıra meta verileri ayarlama yönergeleri içerir. Her bir EM Pilot deposunun kök dizininde (örneğin, ~/Azure-RMSDocs-pr /template.md) bulunur ve bir markdown dosyası olarak okunacak şekilde tasarlanmıştır. Ancak, [yayımlanmış sürümüne](https://stage.docs.microsoft.com/en-us/rights-management/template) başvurarak markdown örneklerinin nasıl işlendiğine bakabilirsiniz.

Markdown dosyası oluştururken şablonu yeni bir dosyaya kopyalamanız, meta verileri aşağıda belirtilen şekilde doldurmanız, H1 başlığını üst kısımda makalenin başlığı olarak ayarlamanız ve içeriği silmeniz gerekir. 


## <a name="metadata"></a>Meta veriler 

Tüm meta veriler bloğu, gerekli ve isteğe bağlı alanlara bölünmüş halde üst kısımdadır. Daha fazla bilgi edinmek için bkz. [İşlem meta verileri hızlı başvuru sayfası](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data). Bazı önemli notlar:

- İki nokta (:) işareti ve meta veri öğesinin değeri arasında bir boşluk bulunması **gereklidir**.
- İsteğe bağlı bir meta veri öğesi için bir değer yoksa, # karakterini kullanarak öğeyi açıklama satırı yapın (boş bırakmayın veya “na” kullanmayın); açıklama satırı yapılmış bir öğe için bir değer ekliyorsanız, # karakterini kaldırmayı unutmayın.
- Değer (ör. bir başlık) içerisindeki iki nokta işaretleri meta veri ayrıştırıcısını durdurur. Bunun yerine, &#58; karakterine ait HTML kodlamasını kullanın; (ör. "başlık: Azure Rights Management&#58; temeller | Azure RMS").
- **başlık**: Bu başlık, arama motoru sonuçlarında görünür. Başlık bir dikey çizgi (|) ile bitmeli ve ardından hizmetin adı gelmelidir (bir örneği için yukarıya bakın). Başlık, H1 başlığınızda yer alan başlığın aynısı olmak zorunda değildir (aynısı olmaması daha iyi olabilir). Yaklaşık 65 karakter uzunluğunda olmalıdır (| HİZMET ADI kısmı dahil olmak üzere).
- **yazar**, **yönetici**, **gözden geçiren**: Yazar alanı, yazarın diğer adını değil **Github kullanıcı adını** içermelidir.  Öte yandan, “yönetici” ve “gözden geçiren” alanları, diğer adlar içermelidir. ms.reviewer, makale veya hizmetle ilişkili proje yöneticisinin adını belirtir.
- **ms.assetid**: Makalenin CAPS’ten gelen GUID’idir. Yeni bir markdown dosyası oluştururken, [https://www.guidgenerator.com](https://www.guidgenerator.com) adresinden bir GUID alın. 
- **ms.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: Bu öğeler için olası değerler [burada](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default) bulunabilir.

## <a name="basic-markdown-and-gfm"></a>Temel Markdown ve GFM

Tüm temel ve Github özellikli markdown’lar desteklenir. Bunlar hakkında daha fazla bilgi edinmek için aşağıdaki makalelere bakın:

- [Temel markdown söz dizimi](https://daringfireball.net/projects/markdown/syntax)
- [Github özellikli markdown (GFM) belgeleri](https://guides.github.com/features/mastering-markdown)

## <a name="headings"></a>Başlıklar

Birinci ve ikinci düzey başlık örnekleri yukarıda görülebilir. 

Konunuzda yalnızca bir adet birinci düzey başlık **bulunmalıdır**. Bu başlık, sayfa üzerindeki başlık olarak görüntülenir.  

İkinci düzey başlıklar, sayfa üzerindeki başlığın altında yer alan "Bu makaledekiler" bölümünde görünen sayfa üzerindeki İçindekiler listesini oluşturur.

### <a name="third-level-heading"></a>Üçüncü düzey başlık
#### <a name="fourth-level-heading"></a>Dördüncü düzey başlık
##### <a name="fifth-level-heading"></a>Beşinci düzey başlık
###### <a name="sixth-level-heading"></a>Altıncı düzey başlık

## <a name="text-styling"></a>Metin stili oluşturma

*İtalik* 

**Kalın** 

~~Üstü çizili~~



## <a name="links"></a>Links

Aynı depodaki bir markdown dosyasına bağlantı sağlamak için [göreli bağlantıları](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2) kullanın. 

- Örnek: [Azure Rights Management nedir?](./understand-explore/what-is-azure-rights-management.md)

Aynı markdown dosyasındaki bir üst bilgiye bağlantı sağlamak için, yayımlanan makalenin kaynağını görüntüleyerek üst bilginin kimliğini bulun (ör. `id="blockquote"`) ve # + kimlik şeklinde kullanarak bağlantıyı oluşturun (ör. `#blockquote`).

- Örnek: [Alıntı Blokları](#blockquote)

Aynı depoda bulunan bir markdown dosyasındaki bir üst bilgiye bağlantı sağlamak için, göreli bağlantı sağlama ve diyez etiketli bağlantı sağlamayı birlikte kullanın.

- Örnek: [kaydolma işlemine teknik genel bakış](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)

Harici bir dosyaya bağlantı sağlamak için bağlantı olarak tüm URL'yi kullanın.

- Örnek: [Github](http://www.github.com)

Markdown dosyasında bir URL görünürse, bu URL tıklanabilir bir bağlantıya dönüştürülür.

- Örnek: http://www.github.com

## <a name="lists"></a>Listeler

### <a name="ordered-lists"></a>Sıralı listeler

1. Bu 
1. Bir
1. Adet
1. Sıralı
1. Liste  


#### <a name="ordered-list-with-an-embedded-list"></a>İçinde katıştırılmış bir liste bulunan sıralı liste

1. İşte
1. bir
1. adet
1. katıştırılmış
    1. Deniz Acar
    1. Turgay Elmas
1. sıralı
1. liste


### <a name="unordered-lists"></a>Sırasız listeler

- Bu
- bir
- madde
- madde işaretli
- liste


##### <a name="unordered-list-with-an-embedded-lists"></a>İçinde katıştırılmış bir liste bulunan sırasız liste

- Bu 
- madde işaretli 
- liste
    - Emel Mert
    - Murat Arslan
- içerir  
- listeler
    1. Abdullah Kurt
    1. Merve Demir
- içeriyor


## <a name="horizontal-rule"></a>Yatay çizgi

---

## <a name="tables"></a>Tablolar

| Tablolar        | Bir           | Harikadır  |
| ------------- |:-------------:| -----:|
| 3. sütun      | sağa hizalı | $1600 |
| 2. sütun      | ortalanmış      |   $12 |
| 1. sütun varsayılan olarak | sola hizalı     |    $1 |


## <a name="code"></a>Kod

### <a name="codeblock"></a>Kod bloğu

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a>Satır içi kod

Bu bir `in-line code` örneğidir.

## <a name="blockquotes"></a>Alıntı Blokları

> Kuraklık on milyon yıldır devam ediyordu ve korkunç sürüngenlerin saltanatı biteli uzun zaman olmuştu. Ekvator’un üzerinde, bir gün Afrika olarak bilinecek bu kıtada, var olma savaşının vahşeti yeni bir doruğa ulaşmıştı ve kazanan henüz belli değildi. Bu çorak ve kurumuş topraklarda başarılı olmanın hatta hayatta kalabilmenin tek yolu küçük, hızlı veya vahşi olmaktı.

## <a name="images"></a>Görüntüler

### <a name="static-image"></a>Statik Görüntü

![bu alternatif metindir](./media/AzRMS_elements.png)

### <a name="linked-image"></a>Bağlantılı Görüntü

[![bağlantılı görüntü için alternatif metin](./media/AzRMS_elements.png)](https://azure.microsoft.com) 

### <a name="animated-gif"></a>Animasyonlu gif

![animasyonlu gif](./media/hololens.gif)

## <a name="alerts"></a>Uyarılar

### <a name="note"></a>Not

> [!NOTE]
> Bu, NOT örneğidir

### <a name="warning"></a>Uyarı

> [!WARNING]
> Bu, UYARI örneğidir

### <a name="tip"></a>İpucu

> [!TIP]
> Bu, İPUCU örneğidir

### <a name="important"></a>Önemli

> [!IMPORTANT]
> Bu, ÖNEMLİ örneğidir

## <a name="videos"></a>Videolar

### <a name="channel-9"></a>Kanal 9

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <a name="youtube"></a>YouTube

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <a name="docsms-extentions"></a>docs.ms uzantıları

### <a name="button"></a>Düğme

> [!div class="button"]
[düğme bağlantıları](/rights-management)

### <a name="selector"></a>Seçici

> [!div class="op_single_selector"]
- [foo](/rights-management/template.md)
- [bar](/rights-management/scratch.md)

### <a name="step-by-step"></a>Adım Adım

>[!div class="step-by-step"]
[Önceki](https://www.example.com)
[Sonraki](https://www.example.com)