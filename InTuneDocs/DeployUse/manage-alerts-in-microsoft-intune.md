---
title: "Uyarıları yönetme | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: bfea7213f67b55807045bfd8b29fdb083b841a56


---

# Microsoft Intune’da uyarıları yönetme
Kuruluşunuzdaki cihazların genel durumunu değerlendirmek ve sorunları belirlemek için Intune yönetim konsolundaki **Uyarılar** çalışma alanını kullanın.

#### Etkin uyarılar görüntülemek için

1.  Intune yönetim konsolunda aşağıdakilerden birini yapın:

    -   En önemli üç uyarı ve etkin uyarıların toplam sayısı dahil olmak üzere **Uyarılarla ilgili genel bilgileri görüntülemek için** **Sisteme Genel Bakış**'a tıklayın. Daha ayrıntılı bilgilerle detaya geçmek için bu uyarılardaki bağlantılara tıklayabilirsiniz.

    -   **Uyarılarla ilgili özet bilgileri görüntülemek için**, **Uyarılar &gt; Genel Bakış**’a tıklayın. **Uyarılara Genel Bakış** sayfasındaki **Uyarı Türü Özeti** alanında uyarıların bir özeti görüntülenir. Kritik uyarılar önce görüntülenir. Daha ayrıntılı bilgilerle detaya geçmek için bu uyarılardaki bağlantılara tıklayabilirsiniz.

        > [!NOTE]
        > Bazı durumlarda, bir uyarı türü **Uyarılar Türü Özeti** listesinde birden fazla kez görünebilir.
        > 
        > Örneğin, Mantıksal Boş Disk Alanı uyarı türünün şu örnekleri listede görünebilir:
        > 
        > -   3 Mantıksal Boş Disk Alanı
        > -   2 Mantıksal Boş Disk Alanı
        > 
        > Bu davranış, farklı işletim sistemleri çalıştıran cihazlar için aynı uyarı türü oluşturulduğunda gerçekleşir. Örnekte, Mantıksal Boş Disk Alanı uyarı türünün ilk örneği, yani 3 Mantıksal Boş Disk Alanı, Windows® 7 çalıştıran bilgisayarlar tarafından oluşturulmuş olabilir. Mantıksal Boş Disk Alanı uyarı türünün ikinci örneği, Windows Vista® çalıştıran bilgisayarlar tarafından oluşturulmuş olabilir.

    -   **Tüm etkin uyarıları görüntülemek için**, **Uyarılar &gt; Tüm Uyarılar**’a tıklayın. **Uyarılar** sayfasında, aşağıdaki sütunlarla tüm etkin uyarıların listesi görüntülenir:

        1.  **Ad** – Uyarıyı üreten uyarı türünün adı.

        2.  **Kaynak** – Uyarının kaynağına ait bir bağlantı. Uyarı türünün görüntüleme eşiği **Tümünü Görüntüle** olarak ayarlanırsa, bu bağlantı tek bir cihazı görüntüler. Uyarı türünün görüntüleme eşiği bir değere ayarlanırsa, bu bağlantı, bu uyarı tarafından etkilenen cihazların bir listesini görüntüler.

        3.  **Son Güncelleştirme** – Bu, uyarının son değiştirilme zamanı belirtir. Bir uyarı kapatıldıysa, uyarının kapatıldığı zaman görüntülenir.

        4.  **Önem derecesi**– Uyarının önem derecesini gösterir.

## İlan Tahtası Uyarılarını Görüntüleme
ilan tahtasındaki uyarılar, gelecek hizmet yükseltmesi, bakım veya kesinti gibi önemli hizmet duyuruları sağlar. İlan tahtasındaki uyarıları görüntülemek ve yönetmek için bu yordamı kullanın.

#### İlan tahtasındaki uyarıları görüntülemek ve yönetmek için

1.  Intune yönetim konsolunda **Sisteme Genel Bakış**’a tıklayın.

2.  Önemli hizmet duyuruları varsa, bunlar **İlan Tahtası** alanında görüntülenir.

3.  İlan tahtasındaki uyarıyı bir virgülle ayrılmış değer (.csv) veya HTML dosyası olarak dışarı aktarmak istiyorsanız, Intune yönetim konsolunda **Uyarılar &gt; Tüm Uyarılar &gt; Bildirimler**'e tıklayın. Bir bildirim seçin, listeyi dışarı aktar simgesine tıklayın ve yönergeleri izleyin.

## Intune Durumlarını İnceleme
Bir an önce dikkat etmenizi gerektiren sorunları tanılamanıza ve öncelik sıralamasını belirlemenize yardımcı olması için **Sisteme Genel Bakış** çalışma alanında Endpoint Protection, Güncelleştirmeler, Aracı Durumu, İlke ve Yazılım için Sistem Durumu özetlerini görüntüleyin. **Hizmet Durumu** özetinin bir bağlantısı, sistem kesintiye uğradığında oluşan hata iletilerinde de sağlanır. **Hizmet Durumu** özeti, her bir konumdaki sorunun ayrıntılarını gösterir ve her zaman son güncelleştirildiği tarihi gösterir.

#### Aboneliğinizin durumunu görüntülemek için

1.  Intune yönetim konsolunda **Sisteme Genel Bakış**’a tıklayın.

2.  **Sistem Durumu alanında**, çeşitli Microsoft Intune bileşenlerinin durumunu inceleyebilirsiniz. Öğelerin çoğu, daha fazla bilgi için ayrıntıya geçmenize olanak sağlayan bağlantılar içerir. Örneğin, **Endpoint Protection** bölümünde, örnek sayısının seçilmesi algılanan kötü amaçlı yazılımların bir listesiyle birlikte **Endpoint Protection** çalışma alanını gösterir. Cihaz sayısının seçilmesi, kötü amaçlı yazılım içerdiği belirlenen cihazların listesiyle birlikte **Gruplar** çalışma alanını görüntüler.

## Uyarıları Kapatma ve Yeniden Etkinleştirme
Intune uyarıları, aşağıdaki olaylardan biri gerçekleşene kadar etkin kalır:

-   Uyarının oluşturulmasına neden sorun çözüldüğünde.

-   Uyarı el ile kapatıldığında.

-   Uyarı oluşturulduktan sonra 5 gün geçtiğinde. Uyarının süresi dolduktan ve otomatik olarak kapatıldıktan 45 gün sonra.

Kapatıldı olarak işaretlenen uyarılar 90 gün sonra kalıcı olarak silinir.

#### Bir uyarıyı el ile kapatmak için

1.  Intune yönetim konsolunda aşağıdakilerden birini yapın:

    1.  **Uyarılar listesinde bir uyarıyı kapatmak için** – **Uyarılar &gt; Tüm Uyarılar**’a tıklayın. Bir uyarı seçin ve ardından **Uyarıyı Kapat**'a tıklayın.

    2.  **Belirli bir cihazda uyarıyı kapatmak için** – **Gruplar &gt; Tüm Cihazlar**’a tıklayın. Bir cihaz seçin ve **Özellikleri Görüntüle**'ye tıklayın. Ardından, **Uyarılar** sekmesinde bir uyarı seçin ve **Uyarıyı Kapat**'a tıklayın.

    3.  **Bir ilan tahtası uyarısını kapatmak için** – **Sisteme Genel Bakış**'a tıklayın. İlan tahtasındaki uyarının yanında bulunan **X** işaretine tıklayın.

#### Kapatılan uyarıları görüntülemek ve yeniden etkinleştirmek için

1.  Intune yönetim konsolunda **Uyarılar &gt; Tüm Uyarılar**’a tıklayın.

2.  **Filtreler** listesinde **Kapalı**'ya tıklayın.

    Adlar ve uyarılarla ilgili ek bilgiler yönetim listesi bölmesinde görünür. Seçilen uyarıyla ilgili ayrıntılar önizleme bölmesinde görünür.

3.  Seçili uyarıyı yeniden etkinleştirmek için **Uyarıyı Yeniden Etkinleştir**'e tıklayın.

### Ayrıca bkz.
[Microsoft Intune Uyarıları ile bilgi edinin](get-notified-by-alerts.md)




<!--HONumber=Jun16_HO4-->


