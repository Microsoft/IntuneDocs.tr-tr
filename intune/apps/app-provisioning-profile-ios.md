---
title: Microsoft Intune iOS/ıpados uygulama sağlama profilleri
titleSuffix: ''
description: Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profilini önceden atamak için araçlar sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
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
ms.openlocfilehash: 184209573be3a63a1317df702782d4935383c6d9
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781368"
---
# <a name="use-ios-app-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Uygulamalarınızın süresinin dolmasını engellemek için iOS uygulama sağlama profillerini kullanma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

## <a name="introduction"></a>Giriş

IPhone ve Ipad 'lere atanan Apple iOS/ıpados iş kolu uygulamaları, dahil edilen bir sağlama profili ve bir sertifikayla imzalanmış kodla oluşturulmuştur. Uygulama çalıştırıldığında, iOS/ıpados, iOS/ıpados uygulamasının bütünlüğünü onaylar ve sağlama profili tarafından tanımlanan ilkeleri zorlar. Aşağıdaki doğrulamalar yapılır:

- **Yükleme dosyası bütünlüğü** -IOS/ıpados, uygulamanın ayrıntılarını kurumsal imzalama sertifikasının ortak anahtarıyla karşılaştırır. Bunlar farklıysa, uygulamanın içeriği değişmiş olabilir ve uygulamanın çalıştırılmasına izin verilmez.
- **Yetenekler zorlaması** -IOS/ıpados, uygulama yükleme (. ipa) dosyasındaki kurumsal sağlama profilinden (bireysel geliştirici sağlama profilleri değil) uygulamanın yeteneklerini zorunlu kılmaya çalışır.


Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi genellikle 3 yıldır. Öte yandan, bir yıl sonra sağlama profilinin süresi dolar. Sertifika hala geçerli durumdayken, Intune size süresi dolmak üzere olan uygulamaların bulunduğu cihazlara yeni sağlama profilini önceden atamak için araçlar verir.
Sertifikanın süresi dolduktan sonra, uygulamayı yeni bir sertifikayla tekrar imzalamanız ve yeni sertifikanın anahtarıyla yeni bir sağlama profili eklemeniz gerekir.

Yönetici olarak, iOS/ıpados uygulama sağlama yapılandırmasını atamak için güvenlik gruplarını dahil edebilir ve dışlayabilirsiniz. Örneğin, tüm kullanıcılara iOS/ıpados uygulaması sağlama yapılandırması atayabilirsiniz, ancak bir yönetim grubunu dışlayabilirsiniz.

## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>iOS mobil uygulama sağlama profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluştur** > **iOS uygulama sağlama profilleri** > **uygulamalar** ' ı seçin.
3. **Temel bilgiler** sayfasında, aşağıdaki değerleri ekleyin:
    - **Ad** - Bu mobil sağlama profiline bir ad verin.
    - **Açıklama** - İsteğe bağlı olarak, ilke için bir açıklama sağlayın.
    - **Profili dosyasını karşıya yükleme** - **Aç** simgesini seçin ve ardından `.mobileprovision`Apple Developer web sitesinden[ indirdiğiniz Apple Mobil Yapılandırma dosyasını (](https://developer.apple.com/) uzantısına sahip) seçin.

   **Sona erme tarihi** , yukarıda eklediğiniz Apple mobil yapılandırma profili dosyasındaki bir değerden doldurulur.<br>

   <img alt="Create profile - Basics" src="~/apps/media/app-provisioning-profile-ios/app-provisioning-profile-ios-01.png">

4. Ileri ' ye tıklayın **: kapsam etiketleri**.<br>
   **Kapsam etiketleri** sayfasında, Intune 'da IOS/ıpados uygulama sağlama profilini kimlerin görebileceğini belirleyebilmek için isteğe bağlı olarak kapsam etiketlerini yapılandırabilirsiniz. Kapsam etiketleri hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](../fundamentals/scope-tags.md).
5. **İleri: atamalar**' a tıklayın.<br>
   **Atamalar** sayfası, profili kullanıcılara ve cihazlara atamanıza olanak tanır. Cihazın Intune tarafından yönetilip yönetilmediği bir cihaza profil atayabileceğinizi unutmayın.
6. Ileri ' ye tıklayın, profil için girdiğiniz değerleri gözden geçirmek için **+ Oluştur** ' a tıklayın.
7. İşiniz bittiğinde, Intune 'da iOS/ıpados uygulama sağlama profili oluşturmak için **Oluştur** ' a tıklayın. 

## <a name="next-steps"></a>Sonraki adımlar

Profili gerekli iOS/ıpados cihazlarına atayın. Daha fazla bilgi için [Cihaz profillerini atama](../device-profile-assign.md) kısmındaki adımları kullanın.
