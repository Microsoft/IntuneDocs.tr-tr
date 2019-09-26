---
title: Intune için bir Apple MDM anında iletme sertifikası alma
titleSuffix: ''
description: İOS cihazlarını ıntune'la yönetmek için Apple MDM anında iletme sertifikası alın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a7b661c3c7c4b84b8e016e057b020dce590b96e
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71305385"
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikası alma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune’un iOS ve macOS cihazları yönetebilmesi için bir Apple MDM Anında İletme Sertifikası gerekir. Siz sertifikayı Intune’a ekledikten sonra, kullanıcılarınız şunları kullanarak cihazlarını kaydedebilir:

- Şirket Portalı uygulaması.

- Apple Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator gibi Apple toplu kayıt yöntemleri.

Kaydolma seçenekleri hakkında daha fazla bilgi için bkz. [iOS cihazlarının nasıl kaydedileceğini belirleme](enrollment-method-choose-ios.md).

Bir anında iletme sertifikasının süresi dolduğunda bunu yenilemeniz gerekir. Sertifikayı yenilerken, anında iletme sertifikasını oluştururken kullandığınız aynı Apple kimliğini kullandığınızdan emin olun.


## <a name="steps-to-get-your-certificate"></a>Sertifikanızı almak için adımlar
[Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihaz kaydı** > **Apple kaydı** > **Apple MDM anında iletme sertifikası**' nı seçin ve ardından [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da bu adımları izleyin.

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>1\.Adım Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin
**Kabul ediyorum**’u seçerek Microsoft’un Apple’a veri göndermesine izin verin.

![MDM Anında İletme Sertifikası ekranında MDM Anında İletme’nin ayarlanmamış hali.](./media/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>Adım 2. Apple MDM anında iletme sertifikası oluşturmak için gereken Intune sertifika imzalama isteğini indirin
**CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.

### <a name="step-3-create-an-apple-mdm-push-certificate"></a>Adım 3. Apple MDM anında iletme sertifikası oluşturun
Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Şirket Apple kimliğinizle oturum açın ve daha sonra **Sertifika Oluştur**’a tıklayın. **Dosya Seç**’e tıklayın ve sertifika imzalama isteğine göz atın, daha sonra **Karşıya Yükle**’yi seçin. Onay sayfasında **İndir**’e tıklayarak sertifika (.pem) dosyasını indirin ve yerel olarak kaydedin.

> [!NOTE]
> Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. En iyi uygulama olarak, yönetim görevleri için bir şirket Apple Kimliği kullanın ve posta kutusunun bir dağıtım listesinde olduğu gibi birden fazla kişi tarafından izlendiğinden emin olun. Hiçbir zaman kişisel bir Apple Kimliği kullanmayın.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>4\. adımı. Apple MDM anında iletme sertifikanızı oluşturmak için kullandığınız Apple kimliğini girin
Bu sertifikayı yenilemeniz gerektiğinde kullanmak üzere bu kimliği kaydedin.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>5\. adımı. Karşıya yüklemek üzere Apple MDM anında iletme sertifikanıza gidin
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikası ile Intune, Apple cihazları kaydedebilir ve yönetebilir.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikasını yenileme
Apple MDM anında iletme sertifikası bir yıl için geçerlidir ve iOS ve macOS cihaz yönetimini sürdürmek için yıllık olarak yenilenmelidir. Sertifikanızın süresi dolarsa kayıtlı Apple cihazlara ulaşamazsınız.

Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. MDM anında iletme sertifikasını oluştururken kullandığınız Apple Kimliği ile sertifikayı yenileyin.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihaz kaydı** > **Apple kaydı**' nı seçin ve ardından Ayrıntılar alanında **Apple MDM anında iletme sertifikası** kutucuğunu seçin.
2. **CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.
3. Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Yenilemek istediğiniz sertifikayı bulun ve **Yenile**’yi seçin.
4. **Anında İletme Sertifikasını Yenileme** ekranında, ileride sertifikayı tanımanıza yardımcı olacak notlar sağlayın, indirdiğiniz yeni istek dosyasına gözatmak için **Dosya Seçin**’e tıklayın ve **Karşıya Yükle**’yi seçin.
   > [!TIP]
   > Bir Sertifika, UID’si ile tanımlanabilir. UID’nin GUID kısmını bulmak için sertifika ayrıntılarında **Konu Kimliği**’ni inceleyin. Veya kayıtlı bir iOS cihazda **Ayarlar** > **Genel** > **Cihaz** **Yönetim** > **Yönetim Profili** > **Daha Fazla Ayrıntı** > **Yönetim Profili**’ne gidin. İkinci satırdaki **Konu** öğesi, Apple Anında İletme Sertifikaları portalındaki sertifikayla eşleştirebileceğiniz benzersiz GUID’i barındırır.
 
6. **Onay** ekranında **İndir**’i seçin ve .pem dosyasını yerel olarak kaydedin.
7. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'DA **Apple MDM anında iletme sertifikası** araştır simgesini seçin, Apple 'dan indirilen. PEZ dosyasını seçin ve **karşıya yükle**' yi seçin.

Apple MDM anında iletme sertifikanız artık **Etkin** olarak görünür ve süresinin dolmasına 365 gün vardır.
