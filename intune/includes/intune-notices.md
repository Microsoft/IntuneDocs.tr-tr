---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: fab8f2be48a30f6ad058b3eeb6874a44ff04e6ac
ms.sourcegitcommit: 7ceae61e036ccf8b33704751b0b39fee81944072
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744309"
---
Bu bildirimler önemli yardımcı olabilecek bilgiler, gelecekteki Intune değişiklikler ve özellikler için hazırlama belirtin. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android Şirket portalı uygulamanızı en son sürüme güncelleştirin <!--4536963-->
Intune, Android Şirket portalı uygulaması için güncelleştirmeleri düzenli olarak serbest bırakır. Kasım 2018'de Google'nın değişiklik, mevcut bildirim platform için Google Firebase Cloud Messaging (FCM) hazırlamak için bir arka uç anahtar dahil bir şirket portalı güncelleştirmesi yayımladık. Var olan Google denemeler, Google play store ile iletişim kurmaya devam için bildirim platformu ve FCM, son kullanıcıların şirket portalı uygulamasının en az Kasım 2018 güncelleştirilmiş gerekecektir taşır bırakın.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bizim telemetri 5.0.4269.0'den önceki bir şirket portalı sürümünü cihazlarla sahip gösterir. Bu sürüm veya daha sonra Şirket portalı uygulamasının yüklü BT pro başlatılan cihaz eylemler gibi temizleme, parola sıfırlama, gerekli ve kullanılabilir uygulamasını yükler ve sertifika kaydı beklendiği gibi çalışmayabilir. Ardından cihazlarınızı ıntune'a MDM, Şirket portalı sürümleri ve kullanıcıların istemci uygulamaları – bulunan uygulamalara giderek görebilirsiniz. Şirket portalı'nın önceki sürümlerini seçerek, son kullanıcıların şirket portalı güncellendikten olmayan cihazlara sahip görmek izin verir.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Son kullanıcıların şirket portalı üzerinden Google güncelleştirilecek güncelleştirmediğiniz Android cihazlarının play isteyin. Bir kullanıcı Şirket portalı uygulamasını otomatik güncelleştirme tutulan değil durumunda Yardım masanıza bildirin. Daha fazla açık Google'nın FCM platform için ek bilgi bağlantısına bakın ve değiştirin.

#### <a name="additional-information"></a>Ek bilgiler
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Intune'da kullanıma sunulacak yeni ekran deneyimi <!--4593669-->
Güncelleştirilmiş bölgelerimizde kullanıma sunuyoruz oluşturun ve Azure portalında ıntune'a kullanıcı Arabirimi deneyimlerini düzenleyin. Bu yeni deneyim, mevcut iş akışları bir dikey pencerede sıkıştırılmış bir Sihirbazı stili biçimi kullanılarak basitleştirecektir. Bu güncelleştirme hemen "dikey penceresinde genişlemesi" veya herhangi bir oluşturma ile yapın ve derin dikey yolculuklarından detaya gitmek ihtiyacınız olan akış düzenleyin. Oluşturma iş akışları da atamaları (uygulama ataması hariç) içerecek şekilde güncelleştirilir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Tam ekran deneyimi ıntune'a hem portal.azure.com ve devicemanagement.microsoft.com önümüzdeki birkaç ay içinde kullanıma sunulacak. Bu güncelleştirme için kullanıcı Arabiriminde, mevcut ilkeleri ve profilleri işlevselliğini etkilemez, ancak biraz değiştirilmiş bir iş akışı görürsünüz. Örneğin, yeni bir ilke oluşturduğunuzda, bu akış, ilkeyi oluşturduktan sonra bunu yerine bir parçası olarak bazı atamaları ayarlayabilirsiniz olacaktır. Yeni deneyimi konsolda nasıl görüneceğini, ekran görüntüleri için ek bilgilere blog gönderisine bakın.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanız gerekmez ancak gerekirse, BT pro rehberi güncelleştirme düşünebilirsiniz. Azure portalında ıntune çeşitli dikey pencereleri için bu deneyim gönderilirken belgelerimize güncelleştireceğiz.

#### <a name="additional-information"></a>Ek bilgiler 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Değişiklik planı: Intune iOS 11 ve üzeri Eylül'de desteklemek taşıma <!-- 4665342-->
Eylül ayında, iOS Apple tarafından yayımlanacak 13 bekliyoruz. Intune kaydı, Şirket portalı ve Managed Browser, kısa süre içinde iOS 13 yayımlandıktan sonra iOS 11 ve üzeri destekleyecek şekilde taşınır.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
O365 mobil uygulamaları iOS 11.0 ve daha yüksek desteklenen koşuluyla Bu, etkileyebilir değil; büyük olasılıkla zaten işletim sistemi veya cihaz yükseltme yaptınız. Ancak, aşağıda listelenen aygıtlar hiçbirini ya da aşağıda listelenen cihazları kaydetmeye karar verirseniz, aşağıdaki cihazlarda iOS 10 ' büyük bir işletim sistemi desteklemeyen bildirin. Bu cihazlar, iOS 11 veya daha yüksek destekleyen bir cihaz için yükseltilmesi gerekir:

- iPhone 5
- iPhone 5c
- iPad (4. nesil)

Temmuz ayında başlayarak, MDM kayıtlı cihazlara iOS 10 ve Şirket portalı, işletim sistemi veya cihaz yükseltmek için bir ileti alacaksınız. Uygulama koruma ilkelerini (APP) kullanırsanız ayarlama "(yalnızca uyarı) en düşük iOS işletim sistemi gerektirir" erişim de ayarlayabilirsiniz.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Hangi cihazların veya kullanıcıların etkilenebilir görmek için raporlama Intune denetleyin. Git **cihazları** > **tüm cihazlar** ve işletim sistemi için filtre uygulayın. İOS 10 çalıştıran cihazlar, kuruluşunuzda kimlerin belirlemenize yardımcı olması için ek sütunlar ekleyebilirsiniz. Son kullanıcılarınız için desteklenen bir işletim sistemi sürümü cihazlarını Eylül ayından önce yükseltme isteği.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Değişiklik planı: Sürüm 8.1.1 desteği ve iOS için Intune uygulama SDK'sının daha yüksek <!-- 3586942-->
Eylül 2019 ' başlayarak, Intune iOS uygulamalarını Intune uygulama SDK'sı 8.1.1 destekleyecek şekilde hareket eder ve daha yüksek. 8.1.1 değerinden SDK sürümleri ile oluşturulan uygulamalar artık desteklenir. Bu değişikliği iOS 13 Eylül gelmesi beklenen Apple'nın sürümü ile itibaren geçerli olacak ve ayrıca MC181399 Duyurusu yapılan.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Intune uygulama SDK'sı veya uygulama sarmalama tümleştirme sayesinde, onaylanmamış uygulamaları ve veri şifreleme aracılığıyla kullanıcılara şirket verileri koruyabilirsiniz. Intune uygulama koruma ilkelerini (APP) tarafından şifreleme etkin olduğunda iOS için Intune uygulama SDK'sı varsayılan olarak 256 bit şifreleme anahtarları kullanır. Bu değişiklikten sonra tüm iOS uygulamalarına 8.1.1 önce 128 bit şifreleme anahtarlarını kullanmak, SDK sürümleri artık 256 bit anahtar kullanılarak veya 8.1.1 SDK ile tümleştirilmiş uygulamalarla veri paylaşımı mümkün olacaktır. Tüm iOS uygulamaları bir SDK sürümü 8.1.1 ayarlamış olmanız gerekir veya daha yüksek izin vermek için korunan veri paylaşımı.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Microsoft, üçüncü taraf ve satır iş kolu (LOB) uygulamaları denetleyin. Tüm uygulamalarınızı korumalı ile Intune uygulama SDK'sı sürüm 8.1.1 kullanarak emin olmanız gerekir veya üzeri.

- LOB uygulamaları için: Uygulamalarınızı 8.1.1 SDK sürümüyle tümleşik veya sonraki yeniden yayımlamanız gerekebilir. En son SDK sürümü öneririz. Uygulama koruma ilkeleri için iş KOLU uygulamalarınızı hazırlamak nasıl tümleştiriyorsanız bilgi için bkz. [satır iş kolu uygulamalarını uygulama koruma ilkeleri için hazırlama](../apps-prepare-mobile-application-management.md).
- Microsoft/üçüncü taraf uygulamalar için: Kullanıcılarınıza bu uygulamalar en son sürümünü dağıtma emin olun.

Ayrıca, belge veya Geliştirici Kılavuzu varsa desteklemek için SDK bu değişikliği içerecek şekilde güncelleştirmeniz gerekir.

#### <a name="additional-information"></a>Ek bilgiler
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management
