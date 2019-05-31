---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: c4a17abdb518daba30fbdf339090f7e24c8c26d5
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412141"
---
Bu bildirimler önemli yardımcı olabilecek bilgiler, gelecekteki Intune değişiklikler ve özellikler için hazırlama belirtin. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android Şirket portalı uygulamanızı en son sürüme güncelleştirin <!--4536963-->
Intune, Android Şirket portalı uygulaması için güncelleştirmeleri düzenli olarak serbest bırakır. Kasım 2018'de Google'nın değişiklik, mevcut bildirim platform için Google Firebase Cloud Messaging (FCM) hazırlamak için bir arka uç anahtar dahil bir şirket portalı güncelleştirmesi yayımladık. Var olan Google denemeler, Google play store ile iletişim kurmaya devam için bildirim platformu ve FCM, son kullanıcıların şirket portalı uygulamasının en az Kasım 2018 güncelleştirilmiş gerekecektir taşır bırakın.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bizim telemetri 5.0.4269.0'den önceki bir şirket portalı sürümünü cihazlarla sahip gösterir. Bu sürüm veya daha sonra Şirket portalı uygulamasının yüklü BT pro başlatılan cihaz eylemler gibi temizleme, parola sıfırlama, gerekli ve kullanılabilir uygulamasını yükler ve sertifika kaydı beklendiği gibi çalışmayabilir. Ardından cihazlarınızı ıntune'a MDM, Şirket portalı sürümleri ve kullanıcıların istemci uygulamaları – bulunan uygulamalara giderek görebilirsiniz. Şirket portalı'nın önceki sürümlerini seçerek, son kullanıcıların şirket portalı güncellendikten olmayan cihazlara sahip görmek izin verir.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Son kullanıcıların şirket portalı üzerinden Google güncelleştirilecek güncelleştirmediğiniz Android cihazlarının play isteyin. Bir kullanıcı Şirket portalı uygulamasını otomatik güncelleştirme tutulan değil durumunda Yardım masanıza bildirin. Daha fazla açık Google'nın FCM platform için ek bilgi bağlantısına bakın ve değiştirin.

#### <a name="additional-information"></a>Ek Bilgi
https://firebase.google.com/docs/cloud-messaging/
