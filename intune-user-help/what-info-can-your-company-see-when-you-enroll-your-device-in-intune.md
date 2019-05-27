---
title: Cihazınızı kaydederken şirketiniz hangi bilgileri görebilir?
description: BT'nin yönetilen cihazınızda ne görüp göremeyeceğini açıklar.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 12655728-a1af-4d89-97bc-925fe36c0dc4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7f47d7e238bc810db9057a4a7c86dbfa523b0e7b
ms.sourcegitcommit: 0f771585d3556c0af14500428d5c4c13c89b9b05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174219"
---
# <a name="what-information-can-my-organization-see-when-i-enroll-my-device"></a>Cihazımı kaydettiğimde kuruluşum hangi bilgileri görebilir?

Bir cihazı Microsoft Intune’a kaydettiğinizde kuruluşunuz kişisel bilgilerinizi göremez. Bir cihaz kaydettiğinizde kuruluşunuza cihazınızdaki cihaz modeli ve seri numarası gibi bazı bilgileri görüntüleme izni vermiş olursunuz. Kuruluşunuz, cihazdaki şirket bilgilerini korumaya yardımcı olması için bu bilgileri kullanır.

**Kuruluşunuzun asla göremeyeceği şeyler:**

- Arama ve web tarama geçmişi
- E-posta ve kısa mesajlar
- Kişiler
- Takvim
-   Parolalar
- Fotoğraflar uygulamasında veya film rulosunda yer alanları da içeren resimler
- Dosyalar

**Kuruluşunuzun her zaman görebileceği şeyler:**

- Google Pixel gibi cihaz modeli
- Cihaz üreticisi, örneğin Microsoft
- İşletim sistemi ve sürümü, örneğin iOS 12.0.1
- Uygulama envanteri ve uygulama adları, Microsoft Word gibi. Kişisel cihazlarda, kuruluşunuzun yalnızca, yönetilen uygulama envanteri görebilirsiniz. Şirkete ait cihazlarda kuruluşunuz tüm uygulama envanterinizi görebilir.
- Cihaz sahibi
- Cihaz adı
- Cihaz seri numarası
- IMEI

**Kuruluşunuzun görme olasılığı olan şeyler:**

-  Telefon numarası: İçin **Kurumsal**-ait cihazlarda tam telefon numaranız görülebilir. **Kişisel** cihazlarda ise numaranızın yalnızca son dört hanesi kuruluşunuz tarafından görülebilir. Tüm cihazlarda **Cihaz Ayrıntıları** sayfasını açarak cihazın **Sahiplik Türü**’nü görebilirsiniz.
- Cihaz depolama alanı: Gerekli bir uygulama yükleyemezse, kuruluşunuzun alanı çok az olup olmadığını için cihazınızın depolama alanı görünebilir.  
-  Konum: Kayıp, denetimli iOS cihaz kurtarmak gerekli olmadıkça kuruluşunuz asla cihazınızın konumunu görebilirsiniz. Ziyaret [Apple iOS belgeleri](https://go.microsoft.com/fwlink/?linkid=853816) denetlenen cihazlar hakkında daha fazla bilgi edinmek için.  
- Uygulama envanteri ayrıntıları: Kuruluşunuzun mobil tehdit savunması kullanıyorsa iOS cihazınızdaki uygulamalar hakkında ayrıntıları görüntülemek mümkün olacaktır. [Mobil Tehdit Savunması](you-are-prompted-to-install-mtd-ios.md) hakkında daha fazla bilgi edinin.
- Ağ bilgileri: Android cihazlar için ağ bağlantılarıyla ilgili bazı bilgiler kuruluş destek için kullanılabilir. Örneğin kuruluşunuz cihazların belli bir bina içerisinde kalmasını gerektiriyorsa cihazınız, bağlı olduğu şebekeyi tanımlar. 
