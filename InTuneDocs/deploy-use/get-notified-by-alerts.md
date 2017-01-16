---
title: "Uyarılarla bilgi edinin | Microsoft Docs"
description: "Uyarıların, Microsoft Intune’da olup bitenlerden haberdar olmanızı nasıl sağladığını öğrenin."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: efad781dca4a759335b67126026bf4fed127380e


---

# <a name="get-notified-by-microsoft-intune-alerts"></a>Microsoft Intune Uyarıları ile bilgi edinin

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Uyarılar, Microsoft Intune’da olup bitenlerden haberdar olmanızı sağlar.

Örneğin, uyarılar aşağıdaki olaylar hakkında sizi bilgilendirebilir:

-   Exchange Connector ile ilgili, mobil cihaz yönetimini etkileyen bir sorun

-   Bir bilgisayarda kötü amaçlı yazılım bulunması

-   İki Intune ilkesi arasında bir çakışma algılanması


## <a name="how-alerts-work"></a>Uyarılar nasıl çalışır?
Uyarılar, Intune içinde yerleşik olarak bulunan önceden yapılandırılmış bir kural kümesi olan **uyarı türlerine** göre oluşturulur. Örneğin, **Bulut depolama alanında %10 veya daha az boş alan var** uyarı türü, uygulamalarınızı bulutta depolamak için kullandığınız alan bitmeye yaklaştığında sizi uyarır. Uyarı türlerini etkinleştirebilir veya devre dışı bırakabilir ve her uyarı türünün özelliklerini yapılandırabilirsiniz. Örneğin, yukarıdaki uyarı türünü kullanarak şunları yapılandırabilirsiniz:

-   **Durum:** Bu uyarı türünün etkin veya devre dışı olduğu

-   **Önem:** Bu uyarı ne kadar ciddi?


|Önem Derecesi|Ayrıntılar|
|--------|-------|
    |![Kritik uyarı](../media/Critical-Alert.jpg)|Bir an önce incelemeniz gereken ciddi bir sorun (örneğin, bir bilgisayarda kötü amaçlı yazılım algılanması) olduğunu gösterir.|
    |![Uyarı bildirimi](../media/Warning-Alert.jpg)|Şu anda ciddi olmayan, ancak ilgilenmezseniz önemli hale gelebilecek bir sorun (örneğin, güvenlik güncelleştirmelerinin yüklenmesi bekleniyor) olduğunu gösterir.|
    |![Bilgilendirme uyarısı](../media/Informational-Alert.jpg)|İşlemleriniz için kritik olmayan bilgileri (örneğin, Exchange Connector’ın yeni bir sürümünün kullanılabilir olduğu) gösterir.|

Diğer uyarı türlerinde, bir uyarı oluşturulmadan önce etkilenmesi gereken cihazların yüzdesi gibi, yapılandırabileceğiniz farklı öğeler bulunabilir.

**Uyarı türündeki ölçütler karşılandığında, Intune yönetici konsolunda bir uyarı oluşturulur ve gösterilir.**

Ayrıca, Intune’u, bir uyarı oluşturulduğunda sizi e-posta ile bilgilendirmek üzere yapılandırabilirsiniz

## <a name="set-up-alerts"></a>Uyarıları ayarlama
[Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Yönetim** &gt; **Uyarılar ve Bildirimler**’i seçin ve sonra da aşağıdaki görevlerden birini seçin:

|Görev|Açıklama|
|--------|---------------|
|**Uyarı Türleri**|Yapılandırmak istediğiniz uyarı türünü seçin ve aşağıdakilerden birini yapın:<br /><br />**Yapılandır**’ı seçin. **Uyarı Türünü Yapılandır** iletişim kutusunda istediğiniz ayarları yapılandırın ve ardından **Tamam**’ı seçin.<br /><br />Uyarı için **Etkinleştir** veya **Devre Dışı Bırak** seçeneğini belirleyin.<br /><br />Yalnızca belirli bir kategorideki uyarı türlerini görüntülemek için, **Uyarı Türleri** düğümünü genişletin ve o kategoriyi seçin.|
|**Alıcılar**|Ayarladığınız e-posta bildirimlerini alacak yeni bir e-posta adresi eklemek için **Ekle**’yi seçin.<br /><br />Ayrıca, mevcut alıcıları **Düzenleyebilir** veya **Silebilirsiniz** .<br /><br />Bildirimleri almak için bu e-posta adresini **Bildirim Kuralları** bölümünde bir alıcı olarak da eklemelisiniz.|
|**Bildirim Kuralları**|Bir e-posta uyarısının kime gönderileceğini tanımlayan kuralları yapılandırır. Şunlardan birini yapabilirsiniz:<br /><br />**Mevcut kuralı seçme** - Bir kural seçin ve sonra da **Alıcıları Seç** öğesini seçin. Daha sonra, bu kurala uygun bir uyarı oluşturulduğunda bir e-posta alacak tüm alıcıları seçebilirsiniz.<br /><br />**Yeni kural oluşturma** - kural için bir ad girin, kurallar için geçerli olan uyarı kategorilerini ve uyarı önem derecesini seçin, kuralın geçerli olacağı cihaz gruplarını belirleyin ve bir uyarı oluşturulduğunda e-posta alacak kullanıcıları seçin.<br /><br />Ayrıca, mevcut bir kuralı **Etkinleştirebilir**, **Devre dışı bırakabilir**, **Düzenleyebilir**veya **Silebilirsiniz** .|

## <a name="working-with-alerts"></a>Uyarılarla çalışma
Intune Yönetim Konsolu'nda uyarılar üzerine çalışmanıza yardımcı olan aşağıdaki seçenekleri kullanın.

|Seçenek|Açıklama|
|----------|---------------|
|**Etkin uyarıları görüntüleme**|Aşağıdakilerden birini seçin:<br /><br />**Uyarı özetini görüntüleme** - **Pano** çalışma alanındaki Uyarılar bölmesinde en önemli hatalar gösterilir. Daha ayrıntılı bilgi için bölmeyi seçin.<br /><br />Ayrıca, **Uyarılar** çalışma alanının **Genel Bakış** sayfasında uyarıların bir özetini görüntüleyebilirsiniz.<br /><br />**Tüm uyarıları görüntüleme** - **Uyarılar** çalışma alanında **Tüm Uyarılar**’ı seçin.|
|**Bildirimleri görüntüleme**|Aşağıdakilerden birini seçin:<br /><br />**Pano** çalışma alanında **Bildirimler**’i seçin.<br /><br />**Uyarılar** çalışma alanında **Tüm Uyarılar** &gt; **Bildirimler**’i seçin.|
|**Bir uyarıyı kapatma**|Uyarı listesinden kapatılacak uyarıyı seçin ve sonra da **Uyarıyı Kapat**’ı seçin.<br /><br />Kapatılan uyarılar 90 gün sonra kalıcı olarak silinir.|
|**Kapatılan bir uyarıyı yeniden etkinleştirme**|Uyarı listesindeki **Filtreler** açılır menüsünü **Kapalı** olarak ayarlayın.<br /><br />Kapatılan uyarılar listesinde yeniden etkinleştirmek istediğiniz uyarıyı seçin ve sonra da **Uyarıyı Yeniden Etkinleştir**’i seçin.|
Intune uyarıları şu durumlara kadar etkin kalır:

-   Uyarıya neden olan sorun çözüldüğünde

-   Uyarıyı kendiniz kapattığınızda

-   Uyarının oluşturulmasının üzerinden 45 gün geçtiğinde

> [!TIP]
> Farklı işletim sistemleri çalıştıran cihazlarda aynı uyarı oluşturulduysa, uyarılar listesinde aynı uyarının birden fazla sürümünü görebilirsiniz.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile izleme ve raporlar](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


