---
title: Microsoft Intune’da iOS uygulama sağlama profilleri
titleSuffix: ''
description: Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profilini önceden atamak için araçlar sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba51f3eaead4f44d3725f1939a6ece5daec5a7f7
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507371"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Uygulamalarınızın süresinin dolmasını engellemek için iOS uygulama sağlama profillerini kullanma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

## <a name="introduction"></a>Giriş

iPhone ve iPad’lere atanan Apple iOS iş kolu uygulamaları, dahili bir sağlama profili ve sertifikayla imzalanan bir kodla oluşturulur. Uygulama çalıştırıldığında iOS, uygulamanın bütünlüğünü onaylar ve sağlama profili tarafından tanımlanan ilkeleri zorunlu kılar. Aşağıdaki doğrulamalar yapılır:

- **Yükleme dosyası bütünlüğü** - iOS, uygulama ayrıntılarını kurumsal imzalama sertifikasının ortak anahtarıyla karşılaştırır. Bunlar farklıysa, uygulamanın içeriği değişmiş olabilir ve uygulamanın çalıştırılmasına izin verilmez.
- **Özellikleri zorunlu kılma** - iOS, uygulama yükleme (.ipa) dosyasındaki kurumsal sağlama profilinden (bireysel geliştirici sağlama profilleri değil) uygulama özelliklerini zorunlu kılma girişiminde bulunur.


Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi genellikle 3 yıldır. Öte yandan, bir yıl sonra sağlama profilinin süresi dolar. Sertifika hala geçerli durumdayken, Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profilini önceden atamak için araçlar verir.
Sertifikanın süresi dolduktan sonra, uygulamayı yeni bir sertifikayla tekrar imzalamanız ve yeni sertifikanın anahtarıyla yeni bir sağlama profili eklemeniz gerekir.

Yönetici olarak, iOS uygulama sağlama yapılandırmasını atamak için güvenlik grupları dahil edebilir veya hariç tutabilirsiniz. Örneğin bir iOS uygulama sağlama yapılandırmasını Tüm Kullanıcılara atayabilir ve bir yönetici grubunu hariç tutabilirsiniz.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>iOS mobil uygulama sağlama profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
1. **İstemci uygulamaları** iş yükünde **Yönet** > **iOS uygulama sağlama profilleri** seçeneğini belirleyin.
2. Profil listesi bölmesinde **Profil oluştur**’u seçin.
3. **Profil oluştur** bölmesinde aşağıdakileri değerleri yapılandırın:
    - **Ad** - Bu mobil sağlama profiline bir ad verin.
    - **Açıklama** - İsteğe bağlı olarak, ilke için bir açıklama sağlayın.
    - **Profili dosyasını karşıya yükleme** - **Aç** simgesini seçin ve ardından [Apple Developer web sitesinden](https://developer.apple.com/) indirdiğiniz Apple Mobil Yapılandırma dosyasını (`.mobileprovision` uzantısına sahip) seçin.
4. İşiniz bittiğinde **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

Profili gerekli iOS cihazlara atayın. Daha fazla bilgi için [Cihaz profillerini atama](../device-profile-assign.md) kısmındaki adımları kullanın.
