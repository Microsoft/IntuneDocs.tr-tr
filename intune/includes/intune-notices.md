---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 1073a38da8a5b2467b1ff8c97b32b93f92e34e4c
ms.sourcegitcommit: f90cba0b2c2672ea733052269bcc372a80772945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66454135"
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


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Intune'da kullanıma sunulacak yeni ekran deneyimi <!--4593669-->
Güncelleştirilmiş bölgelerimizde kullanıma sunuyoruz oluşturun ve Azure portalında ıntune'a kullanıcı Arabirimi deneyimlerini düzenleyin. Bu yeni deneyim, mevcut iş akışları bir dikey pencerede sıkıştırılmış bir Sihirbazı stili biçimi kullanılarak basitleştirecektir. Bu güncelleştirme hemen "dikey penceresinde genişlemesi" veya herhangi bir oluşturma ile yapın ve derin dikey yolculuklarından detaya gitmek ihtiyacınız olan akış düzenleyin. Oluşturma iş akışları da atamaları (uygulama ataması hariç) içerecek şekilde güncelleştirilir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Tam ekran deneyimi ıntune'a hem portal.azure.com ve devicemanagement.microsoft.com önümüzdeki birkaç ay içinde kullanıma sunulacak. Bu güncelleştirme için kullanıcı Arabiriminde, mevcut ilkeleri ve profilleri işlevselliğini etkilemez, ancak biraz değiştirilmiş bir iş akışı görürsünüz. Örneğin, yeni bir ilke oluşturduğunuzda, bu akış, ilkeyi oluşturduktan sonra bunu yerine bir parçası olarak bazı atamaları ayarlayabilirsiniz olacaktır. Yeni deneyimi konsolda nasıl görüneceğini, ekran görüntüleri için ek bilgilere blog gönderisine bakın.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanız gerekmez ancak gerekirse, BT pro rehberi güncelleştirme düşünebilirsiniz. Azure portalında ıntune çeşitli dikey pencereleri için bu deneyim gönderilirken belgelerimize güncelleştireceğiz.

#### <a name="additional-information"></a>Ek Bilgi 
https://aka.ms/intune_fullscreen
