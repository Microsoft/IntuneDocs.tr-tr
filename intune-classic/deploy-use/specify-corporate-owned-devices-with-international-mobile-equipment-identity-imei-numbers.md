---
title: "IMEI numaralarını belirtme | Microsoft Docs"
description: "Microsoft Intune, şirkete ait mobil cihazları tanımaya yardımcı olmak için yöneticilerin mobil cihaz platformu IMEI numaralarını içeri aktarmasına izin verir"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 5d317c837d43d58b9ac4750fa6f0e054fe2ff7da
ms.lasthandoff: 04/24/2017


---

# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Uluslararası mobil donanım kimliği (IMEI) numaralarıyla şirkete ait cihazları belirtme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune, yöneticilerin şirkete ait mobil cihazları tanımlamasına yardımcı olmak üzere IMEI numaraları kullanarak mobil cihazlar için uluslararası mobil donanım kimliği (IMEI) numaralarını içeri aktarmasını sağlar. Cihazlar Intune'a kaydedildikten sonra, **Gruplar** > **Genel Bakış** > **Tüm Cihazlar** altında içeri aktarılmış IMEI numarası olan cihazları görebilirsiniz. **Cihaz grubu**, içeri aktarılmış IMEI numarası olan cihazları **Sahip** sütununda **Şirket** olarak listeler.

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Gruplar** &gt; **Tüm Cihazlar** &gt; **Tüm Kurumsal Ön Kayıtlı Cihazlar** &gt; **IMEI’ye Göre (Tüm platformlar)** öğesine gidin ve ardından **Cihaz ekle…** öğesini seçin. İki yolla cihaz ekleyebilirsiniz:

    -   **Seri numaraları olan bir .csv dosyası yükleme** – Üst bilgi içermeyen, iki sütunlu, virgülle ayrılmış değer (.csv) listesini oluşturun ve .csv dosyası başına 5.000 cihaz veya 5 MB ile sınırlayın. Ayrıntılar alanı 128 karakterle sınırlıdır. 

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
        |&lt;IMEI 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|
        Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

        ```
        01234567890123,device details
        02234567890123,device details
        ```

    -   **Cihaz ayrıntılarını el ile ekle** - En fazla 15 cihazın IMEI numarasını ve cihaz ayrıntılarını girin.

   *Ayrıntılar* alanı yönetimsel kullanım içindir. Donanım kimliğine göre listelenen Şirkete ait cihazlar listesinde cihazı belirlemeye yardımcı olacak ayrıntılar belirtebilirsiniz. Bu bilgiler cihaza gönderilmez, ancak Intune konsolunda görünür.

2.   **İleri**’yi seçin.
3.  **Cihazları Gözden Geçir** bölmesinde, içeri aktarılan cihaz IMEI numaralarını onaylayabilirsiniz. Ayrıca, yeniden içeri aktarılmakta olan IMEI numaraları için **Ayrıntılar**’ın üzerine yazıp yazmayacağınıza karar verebilirsiniz. Geçerli ayrıntıları korumak için **Üzerine Yaz** kutusunun işaretini kaldırabilirsiniz. IMEI numaralarını içeri aktarmak için **Son**’u seçin.
4.  İçeri aktarılan IMEI numaraları ve açıklamalar **IMEI’ye Göre (Tüm platformlar)** listesine eklenir.

> [!IMPORTANT]
> Android cihazlar için IMEI numaraları içeri aktarıyorsanız, bazı Android cihazların birden çok IMEI numarası olduğunu unutmayın. IMEI numarasını içeri aktarıyorsanız, ancak bu numara cihaz tarafından Intune'a bildirilen IMEI numarası değilse, cihaz şirkete ait cihaz olarak değil, kişisel cihaz olarak sınıflandırılır.

IMEI numarasına sahip cihaz Intune’a kaydedilirken, genellikle bir kullanıcı Şirket Portalı uygulamasını yükleyip kayıt işlemini tamamladığında, cihaz şirkete ait olarak etiketlenir ve **IMEI Cihazları** grubunda kayıtlı olarak görünür.

>[!NOTE]
> Kuruluşunuz yakın gelecekte yeni Azure portalına geçiş yaptığında bu özelliğin değişeceğini göreceksiniz. Mevcut Intune yönetici konsolunda yöneticiler yüklenen CSV dosyasından ayrıntıları alabilir ve her donanım tanımlayıcısı için geçerli ayrıntıların üzerine yazabilir. Yeni Azure portalında tüm donanım tanımlayıcıları için otomatik olarak ayrıntıların üzerine yazabilecek veya mevcut tanımlayıcılar için tüm yeni ayrıntıları yoksayabileceksiniz.

Uluslararası Mobil Donanım Kimlikleri (IMEI) hakkındaki ayrıntılı belirtimler için bkz. [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
