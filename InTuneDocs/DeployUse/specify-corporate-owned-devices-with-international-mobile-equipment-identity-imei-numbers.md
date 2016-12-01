---
title: "IMEI numaralarını belirtme | Microsoft Intune"
description: "Microsoft Intune, şirkete ait mobil cihazları tanımaya yardımcı olmak için yöneticilerin mobil cihaz platformu IMEI numaralarını içeri aktarmasına izin verir"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: 040413b59c81c20cf579660a83acebc494c0a1b9


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Uluslararası mobil donanım kimliği (IMEI) numaralarıyla şirkete ait cihazları belirtme
Microsoft Intune, yöneticilerin şirkete ait mobil cihazları tanımlamasına yardımcı olmak üzere IMEI numaraları kullanarak mobil cihazlar için uluslararası mobil donanım kimliği (IMEI) numaralarını içeri aktarmasını sağlar. Cihazlar Intune'a kaydedildikten sonra, **Gruplar** > **Genel Bakış** > **Tüm Cihazlar** altında içeri aktarılmış IMEI numarası olan cihazları görebilirsiniz. **Cihaz grubu**, içeri aktarılmış IMEI numarası olan cihazları **Sahip** sütununda **Şirket** olarak listeler.

1. [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Kurumsal Ön Kayıtlı Cihazlar** &gt; **IMEI’ye Göre (Tüm platformlar)** öğesine gidin ve ardından **Cihaz ekle…** öğesini seçin. İki yolla cihaz ekleyebilirsiniz:

    -   **Seri numaraları olan bir .csv dosyası yükleme** – Üst bilgi içermeyen, iki sütunlu, virgülle ayrılmış değer (.csv) listesini oluşturun ve .csv dosyası başına 5.000 cihaz veya 5 MB ile sınırlayın.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
        |&lt;IMEI 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|
        Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Cihaz ayrıntılarını el ile ekle** - En fazla 15 cihazın IMEI numarasını ve cihaz ayrıntılarını girin.

   *Ayrıntılar*, bir cihazın ilişkilendirildiği IMEI numarasını belirleyebilmeniz için yönetim kullanımına yöneliktir. Bu bilgiler cihaza gönderilmez, ancak Intune konsolunda görünür.

2.   **İleri**’yi seçin.
3.  **Cihazları Gözden Geçir** bölmesinde, içeri aktarılan cihaz IMEI numaralarını onaylayabilirsiniz. Ayrıca, yeniden içeri aktarılmakta olan IMEI numaraları için **Ayrıntılar**’ın üzerine yazıp yazmayacağınıza karar verebilirsiniz. Geçerli ayrıntıları korumak için **Üzerine Yaz** kutusunun işaretini kaldırabilirsiniz. IMEI numaralarını içeri aktarmak için **Son**’u seçin.
4.  İçeri aktarılan IMEI numaraları ve açıklamalar **IMEI’ye Göre (Tüm platformlar)** listesine eklenir.

IMEI numarasına sahip cihaz Intune’a kaydedilirken, genellikle bir kullanıcı Şirket Portalı uygulamasını yükleyip kayıt işlemini tamamladığında, cihaz şirkete ait olarak etiketlenir ve **IMEI Cihazları** grubunda kayıtlı olarak görünür.



<!--HONumber=Nov16_HO2-->


