---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: ffcef5b4d78856709f8563ee1f667ec7e5d993b3
ms.sourcegitcommit: d2e04a38e024b0f5afb0ca202823227de9da3ad1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65732594"
---
Bu bildirimler önemli yardımcı olabilecek bilgiler, gelecekteki Intune değişiklikler ve özellikler için hazırlama belirtin. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Kurulum Yardımcısı ile kimlik doğrulaması Kurumsal iOS cihazlarında Intune Şirket portalı ile iş akışı kayıt Değiştir <!-- 1927359 -->
Kurulum kullanırken iOS cihazlarını Apple'nın Kurumsal cihaz kayıt yöntemleri - Apple Configurator, Apple İşletme Yöneticisi, Apple School Manager veya Apple aygıt kayıt programı (DEP) aracılığıyla iş akışı yaklaşan bir değişiklik olduğunu Kimlik Doğrulama Yardımcısı. Bu değişiklik, yalnızca kullanıcı benzeşimi ile kaydedilen cihazlar için geçerlidir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu değişiklik kullanıma sunulduğunda, Azure portalında ıntune'da kayıt profilleri, cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız güncelleştirilecektir. Yukarıda listelenen yöntemleri aracılığıyla iOS cihazlarını kaydetmek için Gelişmiş bir iş akışı olacaktır. 

- Ne zaman yeni cihaz kaydetmek ve Kurulum Yardımcısı ile kimlik doğrulaması, size Şirket portalı uygulamasını otomatik olarak dağıtmak depolamamayı mümkün olacaktır. Son kullanıcılar, artık "Aygıtınızı" ekran ve kayıt akışını "Onayla Cihazınızı" ekran görürsünüz.  
- Koşullu erişimi etkinleştirmek istiyorsanız Kurulum Yardımcısı ile Apple'nın Kurumsal cihaz kayıt yöntemleri biri aracılığıyla kayıtlı cihazlar üzerinde eylem atmanız gerekir. Zorunda kalırsınız [bir uygulama yapılandırma ilkesi yapılandırma](https://aka.ms/enrollment_setup_assistant) Şirket portalı bu cihazlara yayar göndermek için belirli bir xml ile.  Bu şekilde Şirket portalı göndermeyi seçerseniz, son kullanıcılar artık "Aygıtınızı" ekran ve kayıt akışını "Onayla Cihazınızı" ekran görürsünüz. 
- Şirket portalı'yla dağıtmadıysanız, bu değişiklik, alındıktan sonra son kullanıcıların yükleme uygulamayı Şirket portalı uygulamasından depolamak, oturum açabilirsiniz ancak gerekir ve uygulama yapılandırma profili yukarıda belirtilen bir hata iletisi alırsınız. Bunlar, uygulama için koşullu erişim kullanmanın mümkün olmayacaktır. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Değiştirilen iş akışı kullanmayı planlıyorsanız, göstermek için son kullanıcı rehberinizi güncelleştirmek isteyebilirsiniz:

- Son kullanıcılar artık kayıt akışta Yukarıdaki iki ekran görür. 
- Otomatik olarak dağıtıldığında, şirket portalında oturum açın ve uygulama Mağazası'ndan indirilmemesi gerekir. 

Bir uygulama yapılandırma İlkesi artık gerekirse, bu değişikliğin hazırlık oluşturmayı seçebilirsiniz. Bu yeni iş akışı dağıtıldığında, güncelleştirilmiş kayıt profilleri konsolunda görürsünüz. Biz de bu piyasaya çıkma ileti merkezi yoluyla sizi bilgilendirmek. Ardından, son kullanıcılar, Kurulum Yardımcısı ile kimlik doğrulaması yaparak DEP aracılığıyla kaydedebilir ve koşullu erişim için şirket portalını kullanabilir, eylemi gerçekleştirmek gerekir.

#### <a name="additional-information"></a>Ek Bilgi 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android Şirket portalı uygulamanızı en son sürüme güncelleştirin <!--4536963-->
Intune, Android Şirket portalı uygulaması için güncelleştirmeleri düzenli olarak serbest bırakır. Kasım 2018'de Google'nın değişiklik, mevcut bildirim platform için Google Firebase Cloud Messaging (FCM) hazırlamak için bir arka uç anahtar dahil bir şirket portalı güncelleştirmesi yayımladık. Var olan Google denemeler, Google play store ile iletişim kurmaya devam için bildirim platformu ve FCM, son kullanıcıların şirket portalı uygulamasının en az Kasım 2018 güncelleştirilmiş gerekecektir taşır bırakın.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bizim telemetri 5.0.4269.0'den önceki bir şirket portalı sürümünü cihazlarla sahip gösterir. Bu sürüm veya daha sonra Şirket portalı uygulamasının yüklü BT pro başlatılan cihaz eylemler gibi temizleme, parola sıfırlama, gerekli ve kullanılabilir uygulamasını yükler ve sertifika kaydı beklendiği gibi çalışmayabilir. Ardından cihazlarınızı ıntune'a MDM, Şirket portalı sürümleri ve kullanıcıların istemci uygulamaları – bulunan uygulamalara giderek görebilirsiniz. Şirket portalı'nın önceki sürümlerini seçerek, son kullanıcıların şirket portalı güncellendikten olmayan cihazlara sahip görmek izin verir.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Son kullanıcıların şirket portalı üzerinden Google güncelleştirilecek güncelleştirmediğiniz Android cihazlarının play isteyin. Bir kullanıcı Şirket portalı uygulamasını otomatik güncelleştirme tutulan değil durumunda Yardım masanıza bildirin. Daha fazla açık Google'nın FCM platform için ek bilgi bağlantısına bakın ve değiştirin.

#### <a name="additional-information"></a>Ek Bilgi
https://firebase.google.com/docs/cloud-messaging/