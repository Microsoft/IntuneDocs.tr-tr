---
title: Apple MDM Anında İletme sertifikası alma
titlesuffix: Microsoft Intune
description: iOS cihazlarını Intune’la yönetmek için Apple MDM Anında İletme sertifikası alma adımlarını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28eb86a1924dc72df4c77cc3f8a05aacd61e0fbd
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikası alma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune iPad'ler, iPhone'lar ve Mac bilgisayarları için mobil uygulama yönetimi (MDM) sağlar ve kullanıcılara şirket e-postası ve uygulamalarına erişim izni tanır. Intune’un iOS ve macOS cihazları yönetebilmesi için bir Apple MDM Anında İletme Sertifikası gerekir. Siz sertifikayı Intune’a ekledikten sonra, kullanıcılarınız şunları kullanarak cihazlarını kaydedebilir:

- Şirket Portalı uygulaması.

- Apple Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator gibi Apple toplu kayıt yöntemleri.

Kaydolma seçenekleri hakkında daha fazla bilgi için bkz. [iOS cihazlarının nasıl kaydedileceğini belirleme](enrollment-method-choose-ios.md).

Bir anında iletme sertifikasının süresi dolduğunda bunu yenilemeniz gerekir. Sertifikayı yenilerken, anında iletme sertifikasını oluştururken kullandığınız aynı Apple kimliğini kullandığınızdan emin olun.


## <a name="steps-to-get-your-certificate"></a>Sertifikanızı almak için adımlar
[Azure portalında](https://portal.azure.com), **Cihaz kaydı** > **Apple Kaydı** > **Apple MDM Anında İletme Sertifikası**’nı seçin ve ardından [Azure portalında](https://portal.azure.com) aşağıdaki adımları izleyin.

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>1. Adım Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin
**Kabul ediyorum**’u seçerek Microsoft’un Apple’a veri göndermesine izin verin.

![MDM Anında İletme Sertifikası ekranında MDM Anında İletme’nin ayarlanmamış hali.](./media/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>2. Adım Apple MDM anında iletme sertifikası oluşturmak için gereken Intune sertifika imzalama isteğini indirin
**CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.

  ### <a name="step-3-create-an-apple-mdm-push-certificate"></a>3. Adım. Apple MDM anında iletme sertifikası oluşturun
Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Şirket Apple kimliğinizle oturum açın ve daha sonra **Sertifika Oluştur**’a tıklayın. **Dosya Seç**’e tıklayın ve sertifika imzalama isteğine göz atın, daha sonra **Karşıya Yükle**’yi seçin. Onay sayfasında **İndir**’e tıklayarak sertifika (.pem) dosyasını indirin ve yerel olarak kaydedin.

> [!NOTE]
> Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. En iyi uygulama olarak, yönetim görevleri için bir şirket Apple Kimliği kullanın ve posta kutusunun bir dağıtım listesinde olduğu gibi birden fazla kişi tarafından izlendiğinden emin olun. Hiçbir zaman kişisel bir Apple Kimliği kullanmayın.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>Adım 4. Apple MDM anında iletme sertifikanızı oluşturmak için kullandığınız Apple kimliğini girin
Bu sertifikayı yenilemeniz gerektiğinde kullanmak üzere bu kimliği kaydedin.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>Adım 5. Karşıya yüklemek üzere Apple MDM anında iletme sertifikanıza gidin
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikası ile Intune, Apple cihazları kaydedebilir ve yönetebilir.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikasını yenileme
Apple MDM anında iletme sertifikası bir yıl için geçerlidir ve iOS ve macOS cihaz yönetimini sürdürmek için yıllık olarak yenilenmelidir. Sertifikanızın süresi dolarsa kayıtlı Apple cihazlara ulaşamazsınız.

Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. MDM anında iletme sertifikasını oluştururken kullandığınız Apple Kimliği ile sertifikayı yenileyin.

1. [Azure portalında](https://portal.azure.com), **Cihaz Kaydı** > **Apple Kaydı**’nı seçin ve ardından ayrıntılar alanında **Apple MDM Anında İletme Sertifikası** kutucuğunu seçin.
2. **CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.
3. Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Yenilemek istediğiniz sertifikayı bulun ve **Yenile**’yi seçin.
4. **Anında İletme Sertifikasını Yenileme** ekranında, ileride sertifikayı tanımanıza yardımcı olacak notlar sağlayın, indirdiğiniz yeni istek dosyasına gözatmak için **Dosya Seçin**’e tıklayın ve **Karşıya Yükle**’yi seçin.
   > [!TIP]
   > Bir Sertifika, UID’si ile tanımlanabilir. UID’nin GUID kısmını bulmak için sertifika ayrıntılarında **Konu Kimliği**’ni inceleyin. Veya kayıtlı bir iOS cihazda **Ayarlar** > **Genel** > **Cihaz** **Yönetim** > **Yönetim Profili** > **Daha Fazla Ayrıntı** > **Yönetim Profili**’ne gidin. İkinci satırdaki **Konu** öğesi, Apple Anında İletme Sertifikaları portalındaki sertifikayla eşleştirebileceğiniz benzersiz GUID’i barındırır.
 
6. **Onay** ekranında **İndir**’i seçin ve .pem dosyasını yerel olarak kaydedin.
7. [Azure portalında](https://portal.azure.com) **Apple MDM anında iletme sertifikası** gözatma simgesini ve ardından Apple’dan indirilen .pem dosyasını seçin ve **Karşıya Yükle**’yi seçin.

Apple MDM anında iletme sertifikanız artık **Etkin** olarak görünür ve süresinin dolmasına 365 gün vardır.
