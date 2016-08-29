---
title: "IMEI numaralarını belirtme | Microsoft Intune"
description: "Microsoft Intune, şirkete ait mobil cihazları tanımaya yardımcı olmak için yöneticilerin mobil cihaz platformu IMEI numaralarını içeri aktarmasına izin verir"
keywords: 
author: NathBarn
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
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 4e2092182dbda4523c19afeabc34aa0166962c40


---

# Uluslararası mobil donanım kimliği (IMEI) numaralarıyla şirkete ait cihazları belirtme
Microsoft Intune, yöneticilerin şirkete ait mobil cihazları tanımlamaya yardımcı olmak üzere bir IMEI numarasına sahip mobil cihazlar için uluslararası mobil donanım kimliği (IMEI) numaralarını içeri aktarmasını sağlar. Intune’a kaydolduktan sonra içeri aktarılmış IMEI numarası olan cihazlar **Gruplar** > **Genel Bakış** > **Tüm Cihazlar**’ın altından görüntülenebilir. **Cihaz grubu** listeleri, içeri aktarılmış IMEI numarası olan cihazları **Sahibi** sütununda **Şirket** olarak görüntüler.

1. [Microsoft Intune yönetim konsolunda](http://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Kurumsal Ön Kayıtlı Cihazlar** &gt; **IMEI’ye Göre (Tüm platformlar)** öğesine gidin ve ardından **Cihaz ekle…** öğesini seçin. İki yolla cihaz ekleyebilirsiniz:

    -   **Seri numaraları içeren bir CSV dosyası yükleme** – Üst bilgi içermeyen iki sütunun virgülle ayrılmış değer (.csv) listesini oluşturun ve csv dosyası başına 5000 cihaz veya 5 MB ile sınırlayın.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
        |&lt;IMEI 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|
        Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Cihaz ayrıntılarını el ile ekle** - En fazla beş cihazın IMEI numarasını ve cihaz ayrıntılarını girin

   *Ayrıntılar*, bir cihazın hangi IMEI numarasıyla ilişkili olduğunu belirleyebilmeniz için yönetim kullanımına yöneliktir. Bu bilgiler cihaza gönderilmez, ancak Intune konsolunda görünür.

2.   **İleri**’yi seçin.
3.  **Cihazları Gözden Geçir** bölmesinde hangi cihaz IMEI numaralarının içeri aktarıldığını onaylayabilirsiniz. Ayrıca, yeniden içeri aktarılmakta olan IMEI numaraları için **Ayrıntılar**’ın üzerine yazabilirsiniz. Geçerli ayrıntıları korumak için **Üzerine Yaz** onay kutusunun işaretini kaldırabilirsiniz. IMEI numaralarını içeri aktarmak için **Son**’u seçin.
4.  Eklenen IMEI numaraları ve açıklamalar **IMEI’ye Göre (Tüm platformlar)** listesine eklenir.

İlgili IMEI numarasına sahip cihaz kaydedilirken, genellikle bir kullanıcı Şirket Portalı uygulamasını yükleyip kayıt işlemini tamamladığında, cihaz Şirkete ait olarak etiketlenir ve **IMEI Cihazları** grubunda kayıtlı olarak görünür.



<!--HONumber=Jul16_HO4-->


