---
title: "Uyarılarla bilgi edinin | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e929a95d95b71e22d46e124f1a423af7046b0539
ms.openlocfilehash: f1dd166b7b1278003ac8785b8be07c29396dfe8c


---

# Microsoft Intune Uyarıları ile bilgi edinin
Uyarılar, Microsoft Intune’da olup bitenlerden haberdar olmanızı sağlar.

Örneğin, uyarılar aşağıdaki olaylar hakkında sizi bilgilendirebilir:

-   Exchange Connector ile ilgili, mobil cihaz yönetimini etkileyen bir sorun

-   Bir bilgisayarda kötü amaçlı yazılım bulunması

-   İki Intune ilkesi arasında bir çakışma algılanması


## Uyarılar nasıl çalışır?
Uyarılar, Intune içinde yerleşik olarak bulunan önceden yapılandırılmış bir kural kümesi olan **uyarı türlerine** göre oluşturulur. Örneğin, **Bulut depolamada %10 veya daha az boş alan var** uyarı türü, uygulamalarınızı bulutta depolamak için kullandığınız alan bitmeye yaklaştığında sizi uyarır. Her uyarı türünü etkinleştirebilir veya devre dışı bırakabilir ve uyarı türlerinin özelliklerini yapılandırabilirsiniz. Örneğin, yukarıdaki uyarı türünü kullanarak şunları yapılandırabilirsiniz:

-   **Durum:** Bu uyarı türünün etkin veya devre dışı olduğu

-   **Önem:** Bu uyarı ne kadar ciddi?


|Önem Derecesi|Ayrıntılar|
|--------|-------|
    |![Kritik uyarı](../media/Critical-Alert.jpg)|Bir an önce incelemeniz gereken ciddi bir sorun (örneğin, bir bilgisayarda kötü amaçlı yazılım algılanması) olduğunu gösterir.|
    |![Uyarı bildirimi](../media/Warning-Alert.jpg)|Şu anda ciddi olmayan, ancak ilgilenmezseniz önemli hale gelebilecek bir sorun (örneğin, güvenlik güncelleştirmelerinin yüklenmesi bekleniyor) olduğunu gösterir.|
    |![Bilgilendirme uyarısı](../media/Informational-Alert.jpg)|İşlemleriniz için kritik olmayan bilgileri (örneğin, Exchange Connector’ın yeni bir sürümünün kullanılabilir olduğu) gösterir.|

Diğer uyarı türleri, bir uyarı oluşturulmadan önce etkilenmesi gereken cihazların yüzdesi gibi yapılandırabileceğiniz farklı öğeler içerebilir.

**Bir uyarı türündeki ölçütler karşılandığında, Intune yönetim konsolunda bir uyarı oluşturulur ve görüntülenir.**

Ayrıca, Intune’u, bir uyarı oluşturulduğunda sizi e-posta ile bilgilendirmek üzere yapılandırabilirsiniz

## Uyarıları yapılandırma
[Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetim** &gt; **Uyarılar ve Bildirimler**’i seçin ve sonra da aşağıdaki yapılandırma görevlerinden birini seçin:

|Görev|Açıklama|
|--------|---------------|
|**Uyarı Türleri**|Yapılandırmak istediğiniz uyarı türünü seçin, ardından aşağıdakilerden birini yapın:<br /><br />**Yapılandır**’ı seçin. **Uyarı Türünü Yapılandır** iletişim kutusunda istediğiniz ayarları yapılandırın ve ardından **Tamam**’ı seçin.<br /><br />Uyarı için **Etkinleştir** veya **Devre Dışı Bırak** seçeneğini belirleyin.<br /><br />Yalnızca belirli bir kategorideki uyarı türlerini görüntülemek için **Uyarı Türleri** düğümünü genişletin ve bir kategori seçin.|
|**Alıcılar**|Yapılandırdığınız e-posta bildirimlerini alacak yeni bir e-posta adresi eklemek için **Ekle**’yi seçin.<br /><br />Ayrıca, mevcut alıcıları **Düzenleyebilir** veya **Silebilirsiniz** .<br /><br />Bildirimleri almak için bu e-posta adresini **Bildirim Kuralları** bölümünde bir alıcı olarak da eklemelisiniz.|
|**Bildirim Kuralları**|Bir e-posta uyarısının kime gönderileceğini tanımlayan kuralları yapılandırır. Şunlardan birini yapabilirsiniz:<br /><br />**Mevcut kuralı seçme** - Bir kural seçin ve sonra da **Alıcıları Seç**’i seçin. Daha sonra, bu kurala uygun bir uyarı oluşturulduğunda bir e-posta alacak tüm alıcıları seçebilirsiniz.<br /><br />**Yeni kural oluşturma** - kural için bir ad girin, kurallar için geçerli olan uyarı kategorilerini ve uyarı önem derecesini seçin, kuralın geçerli olacağı cihaz gruplarını belirleyin ve bir uyarı oluşturulduğunda e-posta alacak kullanıcıları seçin.<br /><br />Ayrıca, mevcut bir kuralı **Etkinleştirebilir**, **Devre dışı bırakabilir**, **Düzenleyebilir**veya **Silebilirsiniz** .|

## Uyarılarla çalışma
Intune Yönetim Konsolu'nda uyarılar üzerine çalışmanıza yardımcı olan aşağıdaki seçenekleri kullanın.

|Seçenek|Açıklama|
|----------|---------------|
|**Etkin uyarıları görüntüleme**|Aşağıdakilerden birini seçin:<br /><br />**Uyarı özetini görüntüleme**: **Pano** çalışma alanındaki Uyarılar bölmesinde en önemli hatalar görüntülenir. Daha ayrıntılı bilgi için bölmeyi seçin.<br /><br />Ayrıca, **Uyarılar** çalışma alanının **Genel Bakış** sayfasında uyarıların bir özetini görüntüleyebilirsiniz.<br /><br />**Tüm uyarıları görüntüleme** - **Uyarılar** çalışma alanında **Tüm Uyarılar**’ı seçin.|
|**Bildirimleri görüntüleme**|Aşağıdakilerden birini seçin:<br /><br />**Pano** çalışma alanında **Bildirimler**’i seçin.<br /><br />**Uyarılar** çalışma alanında **Tüm Uyarılar** &gt; **Bildirimler**’i seçin.|
|**Bir uyarıyı kapatma**|Uyarı listesinden kapatılacak uyarıyı seçin ve sonra da **Uyarıyı Kapat**’ı seçin.<br /><br />Kapatılan uyarılar 90 gün sonra kalıcı olarak silinir.|
|**Kapatılan bir uyarıyı yeniden etkinleştirme**|Uyarı listesindeki **Filtreler** açılır menüsünü **Kapalı** olarak ayarlayın.<br /><br />Kapatılan uyarılar listesinde yeniden etkinleştirmek istediğiniz uyarıyı seçin ve sonra da **Uyarıyı Yeniden Etkinleştir**’i seçin.|
Intune uyarıları şu durumlara kadar etkin kalır:

-   Uyarıya neden olan sorun çözüldüğünde

-   Uyarıyı kendiniz kapattığınızda

-   Uyarının oluşturulmasının üzerinden 45 gün geçtiğinde

> [!TIP]
> Farklı işletim sistemleri çalıştıran cihazlarda aynı uyarı oluşturulduysa, uyarılar listesinde aynı uyarının birden fazla sürümünü görebilirsiniz.

### Ayrıca bkz.
[Microsoft Intune ile izleme ve raporlama](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


