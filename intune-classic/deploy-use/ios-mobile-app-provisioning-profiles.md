---
title: Uygulama sağlama profilleri
description: Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden dağıtmak için araçlar verir.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cadd7070e8e3c7c0c5aca42324635af627f91e14
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Uygulamalarınızın süresinin dolmasını engellemek için iOS mobil sağlama profili ilkelerini kullanma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

iPhone ve iPad’lere dağıtılan Apple iOS iş kolu uygulamaları, dahili bir sağlama profili ve sertifikayla imzalanan bir kodla oluşturulur. Uygulama çalıştırıldığında iOS, uygulamanın bütünlüğünü onaylar ve sağlama profili tarafından tanımlanan ilkeleri zorunlu kılar. Aşağıdaki doğrulamalar yapılır:

- **Yükleme dosyası bütünlüğü** - iOS, uygulama ayrıntılarını kurumsal imzalama sertifikasının ortak anahtarıyla karşılaştırır. Bunlar farklıysa, uygulamanın içeriği değişmiş olabilir ve uygulamanın çalıştırılmasına izin verilmez.
- **Özellikleri zorunlu kılma** - iOS, uygulama yükleme (.ipa) dosyasındaki kurumsal sağlama profilinden (bireysel geliştirici sağlama profilleri değil) uygulama özelliklerini zorunlu kılma girişiminde bulunur.


Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi genellikle 3 yıldır. Öte yandan, bir yıl sonra sağlama profilinin süresi dolar. Sertifika hala geçerli durumdayken, Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profili ilkesini önceden dağıtmak için araçlar verir.
Sertifikanın süresi dolduktan sonra, uygulamayı yeni bir sertifikayla tekrar imzalamanız ve yeni sertifikanın anahtarıyla yeni bir sağlama profili eklemeniz gerekir.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>İş kolu uygulamasının süresinin ne zaman dolacağını bulma

1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Uygulamalar** > **Uygulamalar**’ı seçin.
2. Uygulamanın süre sonu tarihini görmek için, uygulamalar listesinin **Sona erme tarihi** sütununa bakın. Ayrıca, yalnızca işlem yapmanız gereken uygulamaları görmek için **Filtreler** açılan listesinde **Süresi doldu/dolmak üzere** ayarını da kullanabilirsiniz.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>iOS mobil sağlama profili ilkesi oluşturma


1. [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **Genel bakış** > **İlke Ekle**’yi seçin.
2. **Yeni İlke Oluştur** iletişim kutusunda, **iOS** > **Mobil Sağlama Profili İlkesi**’ni, sonra da **İlke Oluştur**’u seçin.
3. **Genel** sayfasında, aşağıdaki değerleri yapılandırın:
    - **Ad** - Bu mobil sağlama profili ilkesine bir ad verin.
    - **Açıklama** - İsteğe bağlı olarak, ilke için bir açıklama sağlayın.
    - **Yapılandırma profili dosyası** - **İçeri Aktar**’a tıklayın, sonra da Apple Developer web sitesinden indirdiğiniz bir Apple Mobil Yapılandırma Profili dosyasını (uzantısı **.mobileprovision** olmalı) seçin.
4. İşiniz bittiğinde **İlkeyi Kaydet**’i seçin.
5. Şimdi, ilkeyi gerekli iOS cihazlarına dağıtın. Daha fazla bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
