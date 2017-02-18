---
title: "Uyarıları yönetme | Microsoft Docs"
description: "Kuruluşunuzdaki cihazların genel durumunu değerlendirmek için Intune’da Uyarılar çalışma alanını kullanın."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pbala
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 67a7e25c8365970eb108b2529692a6f67c5de054


---

# <a name="manage-alerts-in-microsoft-intune"></a>Microsoft Intune’da uyarıları yönetme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Kuruluşunuzdaki cihazların genel durumunu değerlendirmek ve sorunları belirlemek için Intune yönetim konsolundaki **Uyarılar** çalışma alanını kullanın.

## <a name="view-active-alerts"></a>Etkin uyarıları görüntüleme

Etkin uyarılar hakkındaki genel bilgilere ve özet verilerine bakın.

#### <a name="to-view-active-alerts"></a>Etkin uyarılar görüntülemek için

Intune yönetici konsolunda, şu adım dizilerinden birini izleyin:

-  En önemli üç uyarı ve etkin uyarıların toplam sayısı dahil olmak üzere **uyarılarla ilgili genel bilgileri görüntülemek için** **Sisteme Genel Bakış**'ı seçin. Ayrıntılı bilgi görmek için bu uyarılardaki bağlantıları seçin.

-  **Uyarılarla ilgili özet bilgileri görüntülemek için**, **Uyarılar** > **Genel Bakış**’ı seçin. **Uyarılara Genel Bakış** sayfasındaki **Uyarı Türü Özeti** alanında uyarıların özetini görebilirsiniz. Kritik uyarılar önce listelenir. Ayrıntılı bilgi görmek için bu uyarılardaki bağlantıları seçin.

        > [!NOTE]
        > In some cases, an alert type might appear more than once in the **Alerts Type Summary** list.
        >
        > For example, two instances of the Logical Free Disk Space alert type might be listed:
        >
        > -   3 Logical Free Disk Space
        > -   2 Logical Free Disk Space
        >
        > This occurs when the same alert type is generated for different devices that run different operating systems. In the example, the 3 Logical Free Disk Space alert type might have been generated by a computer that runs Windows 7. The 2 Logical Free Disk Space alert type might have been generated by a computer that runs Windows Vista.

-   **Tüm etkin uyarıları görüntülemek için**, **Uyarılar** > **Tüm Uyarılar**’ı seçin. **Uyarılar** sayfasında, tüm etkin uyarıların listesini görebilirsiniz. Sayfada şu sütunlar vardır:

    -   **Ad**. Uyarıyı üreten uyarı türünün adıdır.

    -   **Kaynak**. Bu sütunda uyarının kaynağına yönelik bir bağlantı vardır. Uyarı türünün görüntüleme eşiği **Tümünü Görüntüle** olarak ayarlanırsa, bu bağlantı tek bir cihazı gösterir. Uyarı türünün görüntüleme eşiği bir değere ayarlanırsa, bu bağlantı bu uyarıdan etkilenen cihazların listesini gösterir.

    -   **Son Güncelleştirme**. Uyarının en son değiştirildiği zamanı gösterir. Bir uyarı kapatıldıysa, uyarının kapatıldığı zaman gösterilir.

    -   **Önem Derecesi**. Bu sütun uyarının önem derecesini gösterir.

## <a name="view-notice-board-alerts"></a>İlan tahtası uyarılarını görüntüleme
İlan tahtası uyarıları, önemli hizmet duyuruları sağlar. Bunlar, yaklaşan hizmet yükseltmesi, bakım zamanlaması veya kesinti durumu hakkında bilgi sağlayabilir.

#### <a name="to-view-and-manage-notice-board-alerts"></a>İlan tahtasındaki uyarıları görüntülemek ve yönetmek için

1.  Intune yönetici konsolunda **Sisteme Genel Bakış**’ı seçin.

2.  Önemli hizmet duyuruları varsa, bunlar **İlan Tahtası** alanında gösterilir.

3.  İlan tahtasındaki uyarıyı bir virgülle ayrılmış değer (CSV) veya HTML dosyası olarak dışarı aktarmak istiyorsanız, Intune yönetim konsolunda **Uyarılar** > **Tüm Uyarılar** >    **Bildirimler**'i seçin. Bir bildirim seçin, **Listeyi Dışarı Aktar** simgesini seçin ve gösterilen yönergeleri izleyin.

## <a name="review-intune-system-status"></a>Intune sistem durumunu gözden geçirme
**Sisteme Genel Bakış** çalışma alanında, bir an önce dikkat etmenizi gerektiren sorunları saptayıp öncelik belirlemenize yardımcı olmak için sunulan Endpoint Protection, Güncelleştirmeler, Aracı Sistem Durumu, İlke ve Yazılım kategorilerine ilişkin **Sistem Durumu** özetlerini görüntüleyebilirsiniz. Sistem kesintiye uğradığında oluşturulan hata iletileri, **Hizmet Durumu** özetine bağlantı verir. **Hizmet Durumu** özetinde, her konumdaki sorunun ayrıntıları ve durum özetinin son güncelleştirildiği tarih gösterilir.

#### <a name="to-view-the-status-of-your-subscription"></a>Aboneliğinizin durumunu görüntülemek için

1.  Intune yönetici konsolunda **Sisteme Genel Bakış**’ı seçin.

2.  Farklı Microsoft Intune bileşenlerinin durumu için **Sistem Durumu** alanını inceleyin.

  Birçok öğenin bağlantıları vardır ve daha fazla bilgi görebilirsiniz. Örneğin, **Endpoint Protection** bölümünde örnek sayısını seçerseniz, algılanan kötü amaçlı yazılımların bir listesiyle birlikte **Endpoint Protection** çalışma alanını görebilirsiniz. Cihaz sayısını seçerseniz, kötü amaçlı yazılım bulunan cihazların listesiyle birlikte **Gruplar** çalışma alanını görebilirsiniz.

## <a name="close-and-reactivate-alerts"></a>Uyarıları kapatma ve yeniden etkinleştirme
Intune uyarıları, şu olaylardan biri gerçekleşene kadar etkin kalır:

-   Uyarının oluşturulmasına neden olan sorun çözüldüğünde.

-   Uyarı el ile kapatıldığında.

-   Uyarının oluşturulmasının üzerinden beş gün geçtiğinde. Uyarının süresi dolduktan ve otomatik olarak kapatıldıktan 45 gün sonra.

Kapatıldı olarak işaretlenen uyarılar 90 gün sonra kalıcı olarak silinir.

#### <a name="to-manually-close-an-alert"></a>Bir uyarıyı el ile kapatmak için

Intune yönetici konsolunda, şu adım dizilerinden birini izleyin:

- **Uyarılar listesinde bir uyarıyı kapatmak için**, **Uyarılar** > **Tüm Uyarılar**’ı seçin. Bir uyarı seçin ve sonra da **Uyarıyı Kapat**'ı seçin.

- **Belirli bir cihazda uyarıyı kapatmak için**, **Gruplar** > **Tüm Cihazlar**’ı seçin. Bir cihaz seçin ve sonra da **Özellikleri Görüntüle**'yi seçin. Ardından, **Uyarılar** sekmesinde bir uyarı seçin ve sonra da **Uyarıyı Kapat**'ı seçin.

- **Bir ilan tahtası uyarısını kapatmak için**, **Sisteme Genel Bakış**'ı seçin. İlan tahtasındaki uyarının yanındaki **X** işaretini seçin.

#### <a name="to-view-and-reactivate-closed-alerts"></a>Kapatılan uyarıları görüntülemek ve yeniden etkinleştirmek için

1.  Intune yönetici konsolunda **Uyarılar** > **Tüm Uyarılar**’ı seçin.

2.  **Filtreler** listesinde **Kapalı**’yı seçin.

    Adları ve uyarılarla ilgili ek bilgileri yönetim listesi bölmesinde görebilirsiniz. Seçilen uyarıyla ilgili ayrıntıları önizleme bölmesinde görebilirsiniz.

3.  Seçili uyarıyı yeniden etkinleştirmek için **Uyarıyı Yeniden Etkinleştir**'i seçin.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune uyarıları ile bildirim alma](../deploy-use/get-notified-by-alerts.md)



<!--HONumber=Dec16_HO2-->

