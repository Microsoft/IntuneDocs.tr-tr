---
# required metadata

title: Raporları kullanarak işlemlerini anlayın | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Raporları kullanarak Microsoft Intune işlemlerini anlayın
Kuruluşunuzdaki yazılım, donanım ve yazılım lisansları hakkında bilgi sağlayan Microsoft Intune raporlarını oluşturma ve yönetmenize yardımcı olması için bu konudaki bilgileri kullanın.

## Raporları Kullanma
Intune raporları, kuruluşunuzdaki yazılımlar, donanımlar ve yazılım lisansları hakkında bilgi sağlar. Raporlar, geçerli gereksinimleri doğrulamanıza ve gelecekteki harcamaları tahmin etmenize yardımcı olabilir.  **Raporlar** çalışma alanı, raporları oluşturmak ve yönetmek için gerekli araçları sağlar. Raporlar hakkında daha fazla bilgi için bkz. [Raporları kullanarak Microsoft Intune işlemlerini anlayın](understand-microsoft-intune-operations-by-using-reports.md).

### Rapor türleri

|Rapor türü|Açıklama|
|---------------|---------------|
|**Güncelleştirme raporları**|Kuruluşunuzdaki bilgisayarlarda başarılı olan yazılım güncelleştirmelerinin yanı sıra başarısız olan, bekleyen veya gerekli güncelleştirmeleri gösterir. Yazılım güncelleştirmeleri hakkında daha fazla bilgi için bkz. [Microsoft Intune'da yazılım güncelleştirmeleri ile Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Algılanan Yazılım raporları**|Kuruluşunuzdaki bilgisayarlarda yüklü yazılımları gösterir ve yazılım sürümlerini içerir. Görüntülenen bilgileri yazılım yayımcısına ve yazılım kategorisine göre filtreleyebilirsiniz. Liste öğesinin yanındaki yön okuna tıklayarak daha fazla ayrıntı (örneğin yüklü olduğu bilgisayarlar) göstermek için listedeki güncelleştirmeleri genişletebilirsiniz.<br /><br />Intune’da hizmetinde bilgisayarları devre dışı bıraktığınızda veya grup üyeliklerini değiştirdiğinizde, bu değişikliklerin algılanan yazılım raporuna yansıtılması birkaç dakika sürebilir. En doğru yazılım envanteri verileri için bilgisayarları kullanımdan kaldırdıktan veya bilgisayarların grup üyeliklerini değiştirdikten sonra, bu bilgisayarları içeren bir algılanan yazılım raporu çalıştırmadan önce birkaç dakika bekleyin.|
|**Bilgisayar Envanteri raporları**|Kuruluşunuzdaki yönetilen bilgisayarlar hakkında bilgi gösterir. Donanım satın almayı planlamak ve kuruluşunuzdaki kullanıcıların donanım gereksinimlerini daha iyi anlamak için bu raporu kullanın. Yönetilen bilgisayarlarla çalışma hakkında daha fazla bilgi için bkz. [Microsoft Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md).|
|**Mobil Cihaz Envanteri raporları**|Kuruluşunuzdaki mobil cihazlarla ilgili bilgileri gösterir. Görüntülenen bilgileri gruplara, cihazın engellemeleri kaldırılmış veya kök erişim izni verilmiş olup olmadığına ve işletim sistemine göre filtreleyebilirsiniz.|
|**Lisans Satın Alma raporları**|Seçilen lisans gruplarında, tüm lisanslı yazılımlar için lisans sözleşmelerine göre yazılım başlıklarını göster. Yazılım lisans bilgileri 24 saatten uzun bir süre boyunca yenilenmezse, bir lisans raporu oluşturduğunuz sırada yenilenir. Lisans raporu, kullanılmakta olan yazılım başlıklarının tam bir hesabını veya sözleşmelerle uyumluluk kanıtı oluşturmaz. Rapor, kuruluşunuz için lisans kararları almanıza yardımcı olmak için kullanılan bir araçtır. Intune, Microsoft toplu lisanslaması olabilecek bazı ürünleri algılayamayabilir. Kullanılabilir filtreleri şunlardır:<br /><br />**Tüm sözleşmeler**, Intune tarafından yönetilen tüm lisanslı yazılım ürünlerini gösterir.<br /><br />**Toplu lisans sözleşmeleri** yalnızca VLSC yazılım ürünlerini gösterir.<br /><br />**Diğer yazılım lisansı sözleşmeleri**, VLSC dışında yönetilen yazılım ürünlerini gösterir.|
|**Lisans yükleme raporları**|Kuruluşunuzdaki bilgisayarlarda yüklü yazılımları, Toplu Lisanslama Hizmeti Merkezi'ne (VLSC) göre geçerli lisans sözleşmenizin kapsamı ile karşılaştırın. Filtreler aşağıdakileri içerir:<br /><br />**Tüm sözleşmeler**, Intune tarafından yönetilen tüm lisanslı yazılım ürünlerini gösterir.<br /><br />**Toplu lisans sözleşmeleri** yalnızca VLSC yazılım ürünlerini gösterir.<br /><br />**Diğer yazılım lisansı sözleşmeleri**, VLSC dışında yönetilen yazılım ürünlerini gösterir.|
|**Hüküm ve Koşullar raporları**|Hüküm ve koşullarınızı kullanıcıların kabul edip etmediğini ve hangi sürümü kabul ettiklerini gösterir. Kendilerine dağıtılan hüküm ve koşulları kabul edip etmediklerini görmek üzere 10’a kadar kullanıcı belirtebilir veya bunlara dağıtılan belirli bir hükmün kabul edilme durumunu gösterebilirsiniz.|
|**Uyumsuz Uygulamalar raporları**|Uyumlu ve uyumsuz uygulamalar listelerinizdeki uygulamaları yükleyen kullanıcılar hakkında bilgi gösterir. Şirket uygulama ilkeleriniz ile uyumlu olmayan kullanıcıları ve cihazları bulmak için bu raporu kullanın.|
|**Sertifika Uyumluluğu raporları**|SCEP veya PKCS #12 (.PFX) aracılığıyla kullanıcılara ve cihazlara hangi sertifikaların verildiğini gösterir. Verilen, süresi dolan ve iptal edilen sertifikaları bulmak için bu raporu kullanın.|
|**Cihaz Geçmişi raporları**|Kullanımdan kaldır, temizle ve sil eylemlerinin geçmişe dönük bir günlüğünü gösterir. Geçmişte cihazda eylemleri kimin başlattığını görmek için bu raporu kullanın.|
|**Mac OS X Donanım Raporu**|Seçtiğiniz gruplarda kayıtlı olan tüm Mac OS X cihazları için donanım ayrıntılarını görüntüler. Bu cihazlardan toplanan donanım envanteri hakkında bilgi için bkz. [Microsoft Intune’da envanterle cihazlarınızı anlama](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Mac OS X Yazılım Raporu**|Seçtiğiniz gruplardaki tüm Mac OS X cihazlarında yüklü yazılımları görüntüler. Raporda yazılım adı (paket kimliği olarak), kısa sürüm adı (veya kolay ad), sürüm ve yazılımın yüklü olduğu cihaz sayısı listelenir.|

#### Bir rapor oluşturmak için

1.  Intune yönetim konsolunda **Raporlar**'a tıklayın ve ardından, yukarıdaki tabloda açıklandığı gibi oluşturmak istediğiniz rapor türüne tıklayın.

2.   **Yeni Rapor Oluştur** sayfasında, varsayılan değerleri kabul edin veya raporun döndüreceği sonuçlara filtre uygulamak için değerleri özelleştirin. Örneğin, algılanan yazılım raporunda yalnızca Microsoft tarafından yayımlanan yazılımların görüntülenmesini seçebilirsiniz.

3.  Raporu yeni bir pencerede açmak için **Raporu Görüntüle** 'ye tıklayın.

Raporu görüntülenen sütunlardan herhangi birine göre sıralamak için sütun başlığına tıklayın. Ayrıca, bazı raporlar daha fazla ayrıntı göstermek için listedeki öğeleri genişletmenize izin verir.

## Daha fazla rapor eylemi
Ayrıca, raporları aşağıdaki eylemleri destekler:

|Eylem|Daha fazla bilgi|
|----------|--------------------|
|**Yazdırma**|Açık bir raporda yazdırma simgesine tıklayın ve yönergeleri izleyin.|
|**Dışarı aktarma**|Açık bir raporda dışarı aktarma simgesine tıklayın ve yönergeleri izleyin. Bir raporu virgülle ayrılmış değerler (.csv) veya HTML biçiminde dışarı aktarabilirsiniz.|
|**Kaydet**| **Yeni Rapor Oluştur** sayfasında, her kullanıcı 100'e kadar rapor kaydedebilir. Rapor parametrelerini gereksinimlerinize göre yapılandırın ve ardından **Kaydet**'e veya farklı bir ad kullanmak istiyorsanız **Farklı Kaydet** 'e tıklayın.|
|**Yükleme**|Daha önceden kaydedilen tüm rapor parametreleri kümelerini almak için **Yeni Rapor Oluştur** sayfasında **Yükle** 'ye tıklayın.|
|**Sil**| **Raporlar** çalışma alanında, istenen rapor türü seçin, **Yükle**'ye tıklayın ve ardından rapor listesinde, raporun yanındaki sil (x) simgesine tıklayın.|

## Ayrıca Bkz.
[Microsoft Intune ile izleme ve raporlama](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO2-->


