---
title: "Apple MDM Anında İletme sertifikası alma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: iOS cihazlarını Intune’la yönetmek için Apple MDM Anında İletme sertifikası alma adımlarını öğrenin."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: c0884ded1c8c55bb1b7968e483864b42f5bd6bde


---

# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM Anında İletme sertifikası alma 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune iPad’ler, iPhone’lar ve Mac OS X cihazları için mobil uygulama yönetimini (MDM) etkinleştirir ve kullanıcılara şirket e-postası ve uygulamalarına erişim izni sağlar. Intune’un iOS ve Mac cihazlarını yönetebilmesi için Apple Anında İletim Bildirimi hizmeti (APNs) sertifikası gerekir. Sertifikayı Intune’a ekledikten sonra, kullanıcılarınız cihazlarını kaydetmek için Şirket Portalı uygulamasını yükleyebilir veya şirketinize ait iOS cihazı yönetimini ayarlayabilirsiniz.

**MDM Anında İletme sertifikası almak için:**<br>

Azure Portal’da **Diğer Hizmetler**’i seçin, metin kutusuna **Intune** girin ve sonra **Diğer** > **Intune**’u seçin. Intune dikey penceresinde **Cihazları kaydet** > **Apple MDM Anında İletme Sertifikası**’nı seçin ve ardından, Azure Portal’da bulunan ve aşağıda da gösterilen numaralandırılmış adımları izleyin.

**1. Adım. Apple MDM anında iletme sertifikası oluşturmak için gereken Intune sertifika imzalama isteğini indirin.**<br>
**CSR’nizi indirin** öğesini seçerek .csr dosyasını indirin ve yerel olarak kaydedin. .csr dosyası Apple Anında İletilen Bildirim Sertifikaları Portalı'ndan bir güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. Apple MDM anında iletme sertifikası oluşturun.**<br>
Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. .csr dosyasını kullanarak anında iletme sertifikasını oluşturmak için şirketinizin Apple kimliğiyle oturum açın. Apple’ın Anında İletme Sertifikası Portalı’nda **Karşıya Yükle**’yi seçtikten sonra bir .json dosyası alırsınız. Anında iletme sertifikası için mutlaka bu dosyayı kullanın. İndirme işlemini tamamlayın, Üçüncü Taraf Sunucular için Sertifikalar için Apple Anında İletme Sertifikaları Portalı’na dönün ve **İndir**’i seçin. Anında iletme sertifikasını (.pem dosyası) indirin ve yerel olarak kaydedin.
Not

**3. Adım. Apple MDM anında iletme sertifikanızı oluşturmak için kullandığınız Apple kimliğini girin.**

**4. Adım. Karşıya yüklemek için Apple MDM anında iletme sertifikanıza gidin.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.



<!--HONumber=Feb17_HO1-->


