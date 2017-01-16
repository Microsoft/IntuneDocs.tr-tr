---
title: "Raporları kullanarak işlemleri anlama | Microsoft Docs"
description: "Kuruluşunuzdaki yazılımlar, donanımlar ve yazılım lisansları hakkında raporlar oluşturun ve bu raporları yönetin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 3400a49feaca9ef34bcffcc176bc496310d4c357



---

# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Raporları kullanarak Microsoft Intune işlemlerini anlayın

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Kuruluşunuzdaki yazılım, donanım ve yazılım lisansları hakkında bilgi sağlayan Microsoft Intune raporlarını oluşturma ve yönetmenize yardımcı olması için bu konudaki bilgileri kullanın.

## <a name="using-reports"></a>Raporları kullanma
Intune raporları, kuruluşunuzdaki yazılımlar, donanımlar ve yazılım lisansları hakkında bilgi sağlar. Raporlar, geçerli gereksinimleri doğrulamanıza ve gelecekteki harcamaları tahmin etmenize yardımcı olabilir. **Raporlar** çalışma alanı, raporları oluşturmak ve yönetmek için gerekli araçları sağlar. 

### <a name="report-types"></a>Rapor türleri

|Rapor türü|Açıklama|
|---------------|---------------|
|**Güncelleştirme Raporları**|Kuruluşunuzda başarılı olan yazılım güncelleştirmelerini gösterir. Ayrıca başarısız, bekleyen veya gerekli güncelleştirmeleri de gösterir. Yazılım güncelleştirmeleri hakkında daha fazla bilgi için bkz. [Microsoft Intune'da yazılım güncelleştirmeleri ile Windows bilgisayarlarını güncel tutun](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Algılanan Yazılım raporları**|Kuruluşunuzdaki bilgisayarlarda yüklü yazılımı gösterir. Yazılım sürümleri dahil edilir. Görüntülenen bilgileri yazılım yayımcısına ve yazılım kategorisine göre filtreleyebilirsiniz. Liste öğesinin yanındaki yön okunu seçerek (bir güncelleştirmenin yüklü olduğu bilgisayarlar gibi) daha fazla ayrıntı göstermek için listedeki güncelleştirmeleri genişletebilirsiniz.<br /><br />Intune’da bilgisayarları devre dışı bıraktığınızda veya grup üyeliklerini değiştirdiğinizde, bu değişikliklerin Algılanan Yazılım raporuna yansıtılması birkaç dakika sürebilir. En doğru yazılım envanteri verileri için bilgisayarları kullanımdan kaldırdıktan veya bilgisayarların grup üyeliklerini değiştirdikten sonra, bu bilgisayarları içeren bir algılanan yazılım raporu çalıştırmadan önce birkaç dakika bekleyin.|
|**Bilgisayar Envanteri Raporları**|Kuruluşunuzdaki yönetilen bilgisayarlar hakkında bilgi gösterir. Donanım satın almayı planlamak ve kuruluşunuzdaki kullanıcıların donanım gereksinimlerini daha iyi anlamak için bu raporu kullanın. Yönetilen bilgisayarlarla çalışma hakkında daha fazla bilgi için bkz. [Microsoft Intune ile Windows bilgisayarlarını yönetme](manage-windows-pcs-with-microsoft-intune.md).|
|**Mobil Cihaz Envanteri Raporları**|Kuruluşunuzdaki mobil cihazlarla ilgili bilgileri gösterir. Görüntülenen bilgileri gruplara, cihazın engellemeleri kaldırılmış veya kök erişim izni verilmiş olup olmadığına ve işletim sistemine göre filtreleyebilirsiniz.|
|**Lisans Satın Alma Raporları**|Seçilen lisans gruplarında, tüm lisanslı yazılımlar için lisans sözleşmelerine göre yazılım başlıklarını göster. Yazılım lisans bilgileri 24 saatten uzun bir süre boyunca yenilenmezse, bir lisans raporu oluşturduğunuz sırada yenilenir. Lisans raporu, kullanılmakta olan yazılım başlıklarının tam bir hesabını veya sözleşmelerle uyumluluk kanıtı oluşturmaz. Rapor, kuruluşunuz için lisans kararları almanıza yardımcı olmak için kullanılan bir araçtır. Intune, Microsoft toplu lisanslaması olabilecek bazı ürünleri algılayamayabilir. Kullanılabilir filtreleri şunlardır:<br /><br />**Tüm sözleşmeler**, Intune tarafından yönetilen tüm lisanslı yazılım ürünlerini gösterir.<br /><br />**Toplu lisanslama sözleşmeleri** yalnızca Toplu Lisanslama Hizmeti Merkezi (VLSC) yazılım ürünlerini gösterir.<br /><br />**Diğer yazılım lisanslama sözleşmeleri**, VLSC dışında yönetilen yazılım ürünlerini gösterir.|
|**Lisans Yükleme Raporları**|Kuruluşunuzdaki bilgisayarlarda yüklü yazılımları, VLSC’ye göre geçerli lisans sözleşmenizin kapsamı ile karşılaştırır. Filtreler aşağıdakileri içerir:<br /><br />**Tüm sözleşmeler**, Intune tarafından yönetilen tüm lisanslı yazılım ürünlerini gösterir.<br /><br />**Toplu lisans sözleşmeleri** yalnızca VLSC yazılım ürünlerini gösterir.<br /><br />**Diğer yazılım lisanslama sözleşmeleri**, VLSC dışında yönetilen yazılım ürünlerini gösterir.|
|**Hükümler ve Koşullar Raporları**|Dağıtım yaptığınız kullanıcıların hüküm ve koşulları kabul edip etmediklerini ve hangi sürümü kabul ettiklerini gösterir. Dağıtımı yapılmış herhangi bir hüküm veya koşulun 10 adede kadar kullanıcı tarafından kabul edilip edilmediğini veya bu kişilere dağıtılmış belirli bir hükmün kabul durumunu gösterebilirsiniz.|
|**Uyumlu Olmayan Uygulama Raporları**|Uyumlu ve uyumsuz uygulamalar listelerinizdeki uygulamaları yükleyen kullanıcılar hakkında bilgi gösterir. Şirket uygulama ilkeleriniz ile uyumlu olmayan kullanıcıları ve cihazları bulmak için bu raporu kullanın.|
|**Sertifika Uyumluluğu Raporları**|SCEP veya PKCS #12 (.PFX) aracılığıyla kullanıcılara ve cihazlara hangi sertifikaların verildiğini gösterir. Verilen, süresi dolan ve iptal edilen sertifikaları bulmak için bu raporu kullanın.|
|**Cihaz Geçmişi Raporları**|Kullanımdan kaldır, temizle ve sil eylemlerinin geçmişe dönük bir günlüğünü gösterir. Geçmişte cihazda eylemleri kimin başlattığını görmek için bu raporu kullanın.|
|**Sistem Durumu Kanıtlama Raporları**|Mobil cihazların durumunu gösterir.|
|**Mac OS X Donanım Raporu**|Seçtiğiniz gruplarda kayıtlı olan tüm Mac OS X cihazları için donanım ayrıntılarını görüntüler. Bu cihazlardan toplanan donanım envanteri hakkında bilgi için bkz. [Microsoft Intune’da envanterle cihazlarınızı anlama](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Mac OS X Yazılım Raporu**|Seçtiğiniz gruplardaki tüm Mac OS X cihazlarında yüklü olan yazılımı gösterir. Raporda yazılım adı (paket kimliği olarak), kısa sürüm adı (veya kolay ad), sürüm ve yazılımın yüklü olduğu cihaz sayısı listelenir.|

#### <a name="to-create-a-report"></a>Bir rapor oluşturmak için

1.  Intune yönetici konsolunda **Raporlar**’ı seçin. Ardından, önceki tabloda açıklandığı gibi oluşturmak için istediğiniz rapor türünü seçin.

2.  **Yeni Rapor Oluştur** sayfasında, varsayılan değerleri kabul edin veya raporun döndüreceği sonuçlara filtre uygulamak için değerleri özelleştirin. Örneğin, Algılanan Yazılım raporunda yalnızca Microsoft tarafından yayımlanan yazılımların görüntülenmesini seçebilirsiniz.

3.  Raporu yeni bir pencerede açmak için **Raporu Görüntüle**'yi seçin.

Raporu görüntülenen sütunlardan birine göre sıralamak için sütunun başlığına tıklayın. Ayrıca, bazı raporlar daha fazla ayrıntı göstermek için listedeki öğeleri genişletmenize izin verir.

## <a name="more-report-actions"></a>Daha fazla rapor eylemi
Ayrıca, raporları aşağıdaki eylemleri destekler:

|Eylem|Daha fazla bilgi|
|----------|--------------------|
|**Yazdırma**|Açık bir raporda yazdırma simgesini seçin ve yönergeleri izleyin.|
|**Dışarı aktarma**|Açık bir raporda dışarı aktarma simgesini seçin ve yönergeleri izleyin. Bir raporu virgülle ayrılmış değerler (.csv) veya HTML biçiminde dışarı aktarabilirsiniz.|
|**Kaydetme**|**Yeni Rapor Oluştur** sayfasında, her kullanıcı 100'e kadar rapor kaydedebilir. Rapor parametrelerini gereksinimlerinize göre yapılandırın ve ardından **Kaydet**'e veya (farklı bir ad kullanmak istiyorsanız) **Farklı Kaydet** 'e tıklayın.|
|**Yükleme**|Daha önceden kaydedilen tüm rapor parametre kümelerini almak için **Yeni Rapor Oluştur** sayfasında **Yükle**'yi seçin.|
|**Sil**|**Raporlar** çalışma alanında, istenen rapor türünü ve **Yükle**’yi seçin. Ardından, raporlar listesinde, raporun yanındaki sil (x) simgesini seçin.|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile izleme ve raporlar](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


