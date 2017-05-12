---
title: "Apple MDM Anında İletme sertifikası alma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS cihazlarını Intune’la yönetmek için Apple MDM Anında İletme sertifikası alma adımlarını öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 91c6b063fbc17cf92aab50c4911e4bb33b76deb9
ms.contentlocale: tr-tr
ms.lasthandoff: 05/10/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikası alma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune iPad'ler, iPhone'lar ve Mac bilgisayarları için mobil uygulama yönetimi (MDM) sağlar ve kullanıcılara şirket e-postası ve uygulamalarına erişim izni tanır. Intune’un iOS ve Mac cihazlarını yönetebilmesi için bir MDM Anında İletme Sertifikası gerekir. Sertifikayı Intune’a ekledikten sonra, kullanıcılarınız cihazlarını kaydetmek için Şirket Portalı uygulamasını yükleyebilir. Ayrıca, örneğin Apple’ın Aygıt Kayıt Programı ile şirketinize ait iOS cihazı yönetimini ayarlayabilir veya Apple Configurator kullanarak cihaz kaydedebilirsiniz. Kaydolma seçenekleri hakkında daha fazla bilgi için bkz. [iOS cihazlarının nasıl kaydedileceğini belirleme](choose-ios-enrollment-method.md).

## <a name="steps-to-get-your-certificate"></a>Sertifikanızı almak için adımlar
Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Intune dikey penceresinde **Cihazları kaydet** > **Apple Kaydı** **Apple MDM Anında İletme Sertifikası**’nı seçin ve sonra Azure portalında bulunan ve aşağıda da gösterilen numaralandırılmış adımları izleyin.

**1. Adım. Apple MDM anında iletme sertifikası oluşturmak için gereken Intune sertifika imzalama isteğini indirin.**<br>
**CSR’nizi indirin** öğesini seçerek .csr dosyasını indirin ve yerel olarak kaydedin. .csr dosyası Apple Anında İletilen Bildirim Sertifikaları Portalı'ndan bir güven ilişkisi sertifikası istemek için kullanılır.

**2. Adım. Apple MDM anında iletme sertifikası oluşturun.**<br>
Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. .csr dosyasını kullanarak anında iletme sertifikasını oluşturmak için şirketinizin Apple kimliğiyle oturum açın. Apple’ın Anında İletme Sertifikası Portalı’nda **Karşıya Yükle**’yi seçtikten sonra bir .json dosyası alırsınız. Anında iletme sertifikası için mutlaka bu dosyayı kullanın. İndirme işlemini tamamlayın, Üçüncü Taraf Sunucular için Sertifikalar için Apple Anında İletme Sertifikaları Portalı’na dönün ve **İndir**’i seçin. Anında iletme sertifikasını (.pem dosyası) indirin ve yerel olarak kaydedin.
Not

**3. Adım. Apple MDM anında iletme sertifikanızı oluşturmak için kullandığınız Apple kimliğini girin.**

**4. Adım. Karşıya yüklemek için Apple MDM anında iletme sertifikanıza gidin.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikasıyla, Intune ilkeyi kayıtlı mobil cihazlara ileterek iOS cihazları kaydedebilir ve yönetebilir.

