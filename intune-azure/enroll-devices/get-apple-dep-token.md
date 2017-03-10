---
title: "Intune için Apple DEP sertifikası alma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune’da Apple cihazlarını yönetmenin önkoşulu olan bir MDM anında iletme sertifikası yapılandırma ve karşıya yükleme yönergeleri. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8edc42bb86e3856ac6568cc3c1acc5d757978e79
ms.lasthandoff: 02/18/2017

---

# <a name="get-an-apple-dep-certificate"></a>Apple DEP sertifikası alma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Şirketin sahibi olduğu iOS cihazlarını Apple’ın Aygıt Kayıt Programı’na (DEP) kaydedebilmeniz için bir Apple DEP belirtecine ihtiyacınız vardır. Bu belirteç Intune'un şirketinize ait olup DEP'e katılan cihazlar hakkındaki bilgileri eşitlemesini sağlar. Ayrıca Intune'un kayıt profilini Apple'a yüklemesine ve cihazları bu profillere atamasına izin verir.

Şirkete ait iOS cihazlarının DEP ile yönetilmesi için kurumunuzun Apple DEP'e katılması ve cihazları bu program aracılığıyla edinmesi gerekir. Bu işlemin ayrıntıları şurada bulunabilir: https://deploy.apple.com. Programın sağladığı avantajlar arasında, her cihazı bir USB kablosu ile bilgisayara bağlamaya gerek bırakmayan kendiliğinden kurulum olanağı da vardır.

> [!NOTE]
> Bu not yalnızca, Intune yönetim konsolundan Azure portalına geçirilmiş olan müşteriler için geçerlidir. Geçiş döneminde Intune yönetim konsolundan bir Apple DEP belirteci sildiyseniz, DEP belirtecinin Intune hesabınıza geri yüklendiğini fark edebilirsiniz. Böyle bir durumda, Azure Portal’dan DEP belirtecini doğrudan silin.

## <a name="steps-to-get-the-apple-dep-certificate"></a>Apple DEP sertifikası alma adımları
Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Intune dikey penceresinde **Cihazları kaydet** > **Apple DEP Belirteci**’ni seçin ve ardından, Azure Portal’da bulunan ve aşağıda da gösterilen numaralandırılmış adımları izleyin.

**1. Adım. Apple DEP belirteci oluşturmak için gereken Intune ortak anahtar sertifikasını indirin.**<br>
Şifreleme dosyasını (.pem) indirmek ve yerel olarak kaydetmek için **Ortak anahtar sertifikanızı indirin** öğesini seçin. .pem dosyası Apple Cihaz Kayıt Programı portalından güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. İlgili Apple web sitesinden bir Apple DEP belirteci indirin.**<br>
[Apple Dağıtım Programları aracılığıyla DEP belirteci oluşturun](https://deploy.apple.com) öğesini seçin (https://deploy.apple.com) ve şirket Apple kimliğinizle oturum açın. DEP belirtecinizi yenilemek için de bu Apple kimliğini kullanmanız gerekir.

   a.  [Cihaz Kayıt Programı Portalı](https://deploy.apple.com)’nda, **Cihaz Kayıt Programı** &gt; **Sunucuları Yönet**’e gidin ve **MDM Sunucusu Ekle**'ye tıklayın.

   b.  **MDM Sunucu Adı**'nı girin ve ardından **İleri**'yi seçin. Sunucu adı, mobil cihaz yönetimi (MDM) sunucusunu tanımlarken kullanmanız içindir. Microsoft Intune sunucusunun adı veya URL'si değildir.

   c.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusu açılır. **Dosya Seç…** öğesini seçin .pem dosyasını karşıya yükleyin ve ardından **İleri**'yi seçin.

   d.  **&lt;SunucuAdı&gt; Ekle** iletişim kutusunda **Sunucu Belirteciniz** bağlantısı gösterilir. Sunucu belirteci (.p7m) dosyasını bilgisayarınıza indirin ve ardından **Bitti**'yi seçin.

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

**3. Adım. Apple DEP belirtecinizi oluşturmak için kullanılan Apple kimliğini girin. Bu kimlik Apple DEP belirtecinizi yenilemek için kullanılabilir.**

**4. Adım. Karşıya yüklenecek Apple DEP belirtecine gidin. Intune, DEP hesabınızı otomatik olarak eşitleyecektir.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.

