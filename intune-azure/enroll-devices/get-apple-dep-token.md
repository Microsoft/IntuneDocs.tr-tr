---
title: "Intune için Apple DEP sertifikası alma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune’da Apple cihazlarını yönetmenin önkoşulu olan bir MDM anında iletme sertifikası yapılandırma ve karşıya yükleme yönergeleri. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: b2c79e92f6378825bdaac03d2d9be699bdaca95b
ms.lasthandoff: 02/15/2017

---

# <a name="get-an-apple-dep-certificate"></a>Apple DEP sertifikası alma 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Şirketin sahibi olduğu iOS cihazlarını DEP ile kaydedebilmeniz için bir Apple DEP belirtecine ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un Kayıt Profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

Şirkete ait iOS cihazlarının Apple Aygıt Kayıt Programı (DEP) ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir: https://deploy.apple.com. Programın sağladığı avantajlar arasında, her cihazı bir USB kablosu ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

> [!NOTE]
> Bu notu yalnızca, Intune yönetim konsolundan Azure Portal’a geçirilmiş olan müşteriler okumalıdır. Geçiş döneminde Intune yönetim konsolundan bir Apple DEP belirteci sildiyseniz, DEP belirtecinin Intune hesabınıza geri yüklendiğini fark edebilirsiniz. Böyle bir durumda, Azure Portal’dan DEP belirtecini doğrudan silin. 

**Apple DEP sertifikası almak için**</br>
Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Intune dikey penceresinde **Cihazları kaydet** > **Apple DEP Belirteci**’ni seçin ve ardından, Azure Portal’da bulunan ve aşağıda da gösterilen numaralandırılmış adımları izleyin.

**1. Adım. Apple DEP belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtar sertifikanızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. İlgili Apple web sitesinden bir Apple DEP belirteci indirin.**<br>
[Apple Dağıtım Programları aracılığıyla DEP belirteci oluşturun](https://deploy.apple.com) öğesini seçin (https://deploy.apple.com) ve şirket Apple kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanmanız gerekir.

   1.  [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’nda, **Cihaz Kayıt Programı** &gt; **Sunucuları Yönet**’e gidin ve **MDM Sunucusu Ekle**'ye tıklayın.

   2.  **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

   3.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusu açılır. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

   4.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı gösterilir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**'yi seçin.

    Bu sertifika (.p7m) dosyası Intune ile Apple'ın Cihaz Kayıt Programı sunucuları arasında bir güven ilişkisi oluşturmak için kullanılır.

**3. Adım. Apple DEP belirtecinizi oluşturmak için kullanılan Apple kimliğini girin. Bu kimlik Apple DEP belirtecinizi yenilemek için kullanılabilir.**

**4. Adım. Karşıya yüklenecek Apple DEP belirtecine gidin. Intune, DEP hesabınızı otomatik olarak eşitleyecektir.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.

