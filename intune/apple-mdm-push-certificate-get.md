---
title: "Apple MDM Anında İletme sertifikası alma"
titlesuffix: Azure portal
description: "iOS cihazlarını Intune’la yönetmek için Apple MDM Anında İletme sertifikası alma adımlarını öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8d05199359f7e4ca2c41415c0db13e339c66c162
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikası alma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune iPad'ler, iPhone'lar ve Mac bilgisayarları için mobil uygulama yönetimi (MDM) sağlar ve kullanıcılara şirket e-postası ve uygulamalarına erişim izni tanır. Intune’un iOS ve Mac cihazlarını yönetebilmesi için bir MDM Anında İletme Sertifikası gerekir. Sertifikayı Intune’a ekledikten sonra, kullanıcılarınız cihazlarını kaydetmek için Şirket Portalı uygulamasını yükleyebilir. Ayrıca, örneğin Apple’ın Aygıt Kayıt Programı ile şirketinize ait iOS cihazı yönetimini ayarlayabilir veya Apple Configurator kullanarak cihaz kaydedebilirsiniz. Kaydolma seçenekleri hakkında daha fazla bilgi için bkz. [iOS cihazlarının nasıl kaydedileceğini belirleme](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Sertifikanızı almak için adımlar
Azure portalında **Cihaz kaydı** > **Apple Kaydı** **Apple MDM Anında İletme Sertifikası**’nı seçin, ardından Azure portalında aşağıdaki adımları izleyin.

**1. Adım. Apple MDM anında iletme sertifikası oluşturmak için gereken Intune sertifika imzalama isteğini indirin.**<br>
**CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.

  ![MDM Anında İletme Sertifikası ekranında MDM Anında İletme’nin ayarlanmadığını gösteren ekran görüntüsü.](./media/create-mdm-push-certificate.png)

**2. Adım. Apple MDM anında iletme sertifikası oluşturun.**<br>
Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Şirket Apple kimliğinizle oturum açın ve daha sonra **Sertifika Oluştur**’a tıklayın. **Dosya Seç**’e tıklayın ve sertifika imzalama isteğine göz atın, daha sonra **Karşıya Yükle**’yi seçin. Onay sayfasında **İndir**’e tıklayarak sertifika (.pem) dosyasını indirin ve yerel olarak kaydedin.

> [!NOTE]
> Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. En iyi uygulama, yönetim görevleri için bir şirket Apple Kimliği kullanmaktır. Hiçbir zaman kişisel bir Apple Kimliği kullanmayın.

**3. Adım. Apple MDM anında iletme sertifikanızı oluşturmak için kullandığınız Apple kimliğini girin.**<br>
Bu sertifikayı yenilemeniz gerektiğinde kullanmak üzere bu kimliği kaydedin.

**4. Adım. Karşıya yüklemek için Apple MDM anında iletme sertifikanıza gidin.**<br>
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikası ile Intune, Apple cihazları kaydedebilir ve yönetebilir.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikasını yenileme
Apple MDM anında iletme sertifikası bir yıl için geçerlidir ve iOS ve macOS cihaz yönetimini sürdürmek için yıllık olarak yenilenmelidir. Sertifikanızın süresi dolarsa kayıtlı Apple cihazlara ulaşamazsınız.

Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. MDM anında iletme sertifikasını oluştururken kullandığınız Apple Kimliği ile sertifikayı yenileyin.

1. Azure portalında **Cihaz Kaydı** > **Apple Kaydı**’nı, ardından **Apple MDM Anında İletme Sertifikası**’nı seçin.
2. **CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.
3. Yenilemek istediğiniz sertifikayı bulun ve **Yenile**’yi seçin.
4. **Anında İletme Sertifikasını Yenileme** ekranında, ileride sertifikayı tanımanıza yardımcı olacak notlar sağlayın, indirdiğiniz yeni istek dosyasına gözatmak için **Dosya Seç**’e tıklayın ve **Karşıya Yükle**’yi seçin.
5. **Onay** ekranında **İndir**’i seçin ve .pem dosyasını yerel olarak kaydedin.
6. Azure portalında **Apple MDM anında iletme sertifikası** göz atma simgesini ve ardından Apple’dan indirilen .pem dosyasını seçin ve **Karşıya Yükle**’yi seçin.

Apple MDM anında iletme sertifikanız artık **Etkin** olarak görünür ve süresinin dolmasına 365 gün vardır.
