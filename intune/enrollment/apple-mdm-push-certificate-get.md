---
title: Intune için Apple MDM Anında İletme sertifikası alma
titleSuffix: ''
description: Intune ile iOS/ıpados cihazlarını yönetmek için bir Apple MDM anında Iletme sertifikası alın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 673f63194b46ca7e4dbf1206d363cbe70c6e6098
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414420"
---
# <a name="get-an-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikası alma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune 'un iOS/ıpados ve macOS cihazlarını yönetmesi için bir Apple MDM anında Iletme sertifikası gereklidir. Siz sertifikayı Intune’a ekledikten sonra, kullanıcılarınız şunları kullanarak cihazlarını kaydedebilir:

- Şirket Portalı uygulaması.

- Apple Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator gibi Apple toplu kayıt yöntemleri.

Kayıt seçenekleri hakkında daha fazla bilgi için bkz. [iOS/ıpados cihazlarının nasıl kaydedileceğini seçme](ios-enroll.md).

Bir anında iletme sertifikasının süresi dolduğunda bunu yenilemeniz gerekir. Sertifikayı yenilerken, anında iletme sertifikasını oluştururken kullandığınız aynı Apple kimliğini kullandığınızdan emin olun.


## <a name="steps-to-get-your-certificate"></a>Sertifikanızı almak için adımlar
[Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın, **cihazlar** > **Apple kayıt** > **Apple MDM anında iletme sertifikası** ** > cihazları seçin** ve ardından bu adımları izleyin.

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>Adım 1. Microsoft’un Apple’a kullanıcı ve cihaz bilgilerini göndermesine izin verin
**Kabul ediyorum**’u seçerek Microsoft’un Apple’a veri göndermesine izin verin.

![MDM Anında İletme Sertifikası ekranında MDM Anında İletme’nin ayarlanmamış hali.](./media/apple-mdm-push-certificate-get/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>Adım 2. Apple MDM anında iletme sertifikası oluşturmak için gereken Intune sertifika imzalama isteğini indirin
**CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.

### <a name="step-3-create-an-apple-mdm-push-certificate"></a>Adım 3: Apple MDM anında iletme sertifikası oluşturun
Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Şirket Apple kimliğinizle oturum açın ve daha sonra **Sertifika Oluştur**’a tıklayın. **Dosya Seç**’e tıklayın ve sertifika imzalama isteğine göz atın, daha sonra **Karşıya Yükle**’yi seçin. Onay sayfasında **İndir**’e tıklayarak sertifika (.pem) dosyasını indirin ve yerel olarak kaydedin.

> [!NOTE]
> Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. En iyi uygulama olarak, yönetim görevleri için bir şirket Apple Kimliği kullanın ve posta kutusunun bir dağıtım listesinde olduğu gibi birden fazla kişi tarafından izlendiğinden emin olun. Hiçbir zaman kişisel bir Apple Kimliği kullanmayın.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>4\. Adım Apple MDM anında iletme sertifikanızı oluşturmak için kullandığınız Apple kimliğini girin
Bu sertifikayı yenilemeniz gerektiğinde kullanmak üzere bu kimliği kaydedin.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>5\. Adım. Karşıya yüklemek üzere Apple MDM anında iletme sertifikanıza gidin
Sertifika (.pem) dosyasına gidin, **Aç**’ı ve sonra da **Karşıya Yükle**’yi seçin. Anında iletme sertifikası ile Intune, Apple cihazları kaydedebilir ve yönetebilir.

## <a name="renew-apple-mdm-push-certificate"></a>Apple MDM anında iletme sertifikasını yenileme
Apple MDM anında iletme sertifikası bir yıl boyunca geçerlidir ve iOS/ıpados ve macOS cihaz yönetiminin korunması için yıllık olarak yenilenmelidir. Sertifikanızın süresi dolarsa kayıtlı Apple cihazlara ulaşamazsınız.

Sertifika, onu oluşturmak için kullanılan Apple Kimliği ile ilişkilidir. MDM anında iletme sertifikasını oluştururken kullandığınız Apple Kimliği ile sertifikayı yenileyin.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın **, > cihazları** > **Apple kayıt** > **Apple MDM anında iletme sertifikası** **Kaydet** ' i seçin.
2. **CSR’nizi indirin** öğesini seçerek istek dosyasını indirin ve yerel olarak kaydedin. Bu dosya, Apple Anında İletme Sertifikaları Portalı’ndan bir güven ilişkisi sertifikası istemek için kullanılır.
3. Apple Anında İletme Sertifikası Portalı’na gitmek için **MDM Anında İletme Sertifikanızı oluşturun** öğesini seçin. Yenilemek istediğiniz sertifikayı bulun ve **Yenile**’yi seçin.
4. **Anında İletme Sertifikasını Yenileme** ekranında, ileride sertifikayı tanımanıza yardımcı olacak notlar sağlayın, indirdiğiniz yeni istek dosyasına gözatmak için **Dosya Seçin**’e tıklayın ve **Karşıya Yükle**’yi seçin.
   > [!TIP]
   > Bir Sertifika, UID’si ile tanımlanabilir. UID’nin GUID kısmını bulmak için sertifika ayrıntılarında **Konu Kimliği**’ni inceleyin. Ya da kayıtlı bir iOS/ıpados cihazında **ayarlar** > **genel** > **cihaz** **yönetimi** > **Yönetim profili** > **daha fazla ayrıntı** > **Yönetim**profili ' ne gidin. İkinci satırdaki **Konu** öğesi, Apple Anında İletme Sertifikaları portalındaki sertifikayla eşleştirebileceğiniz benzersiz GUID’i barındırır.
 
6. **Onay** ekranında **İndir**’i seçin ve .pem dosyasını yerel olarak kaydedin.
7. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'DA **Apple MDM anında iletme sertifikası** araştır simgesini seçin, Apple 'dan indirilen. PEZ dosyasını seçin ve **karşıya yükle**' yi seçin.

Apple MDM anında iletme sertifikanız artık **Etkin** olarak görünür ve süresinin dolmasına 365 gün vardır.
