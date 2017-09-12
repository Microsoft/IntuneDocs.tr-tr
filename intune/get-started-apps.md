---
title: "Uygulamaları kullanmaya başlama"
titlesuffix: Azure portal
description: "Çalışanlarınızın işlerini yapabilmeleri için uygulamalar bulun ve bunları cihazlara ekleyin."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28bc8547d56073a2175ca57e03dbd9b94fc03ba9
ms.sourcegitcommit: fa6aaf12611c3e03e38e467806fc30b1d0255e88
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2017
---
# <a name="get-started-with-adding-apps"></a>Uygulama eklemeye başlama

Intune, kurumsal cihazlarınıza uygulama dağıtmanın birkaç farklı yolunu destekler:

* **Yazılım yükleyiciler**: kullanıcılarınızın cihazlarına indirilen bir dosyayı karşıya yüklersiniz
* __Dış bağlantılar__: genel bir uygulama mağazasında bir uygulamanız veya bir web uygulamanız olduğunda
* **Yönetilen uygulamalar**: App Store’da mevcut olan uygulamalarda ek mobil uygulama yönetimine gerek duyduğunuz iOS cihazları için

Genel bir mağaza uygulaması atayarak daha hızlı bir uygulama dağıtım yöntemlerinden birini göreceksiniz.

## <a name="how-do-i-assign-a-public-store-app"></a>Bir ortak mağaza uygulamasını nasıl atarım?

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Kaynak ara**'yı kullanarak **Intune**'u arayın.
3. **Mobil Uygulamalar**'ı, sonra **Uygulamalar**'ı seçin.
4. **Ekle**'yi, sonra **Uygulama türü** olarak **iOS mağaza uygulaması**'nı seçin.
5. Metin kutusunda cihaza atayacak bir uygulama arayın. Uygulamayı, sonra **Tamam**'ı seçin.
6. **Uygulama ekle** dikey penceresinde **Uygulama bilgileri**'ni seçin, sonra tüm uygulama bilgilerinin doldurulduğundan emin olun. Bu uygulamayı düzenlemenize yardımcı olacak **Sahibi**, **Notlar**, **Geliştirici** gibi isteğe bağlı başka ayrıntılar ve şirketinizin gizlilik ilkesi için bir **Gizlilik URL'si** ekleyebilirsiniz.
7. Bunu Şirket Portalı'nda öne çıkan bir uygulama olarak görüntülemek için Evet'i seçtiğinizden emin olun, sonra Tamam'ı seçin.
8. Uygulamayı eklemek için **Ekle**'yi seçin. Bu, sizi uygulamanın **Genel Bakış**'ına yönlendirir. **Atamalar**'ı seçin, sonra sınama grubunuza atamak için **Grup seç**'e tıklayın. Uygulamayı indirebilmek için **Kullanılabilir** yapın. Uygulama artık sınama cihazınızda **Öne Çıkan Uygulama** olarak görünür.

## <a name="learn-more"></a>Daha fazlasını öğrenin

* [Intune ile uygulama yönetimi nedir?](app-management.md)
* [Uygulama yaşam döngüsüne genel bakış](app-lifecycle.md)
* [Uygulama koruma ilkeleri nedir?](app-protection-policy.md)
