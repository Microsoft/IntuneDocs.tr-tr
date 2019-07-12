---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: d907c5256469e86410c9916d117d3e322d43cfc3
ms.sourcegitcommit: 2614d1b08b8a78cd792aebd2ca9848f391df8550
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67812487"
---
Bu bildirimler, gelecekteki Intune değişiklik ve özelliklerine hazırlanmanıza yardımcı olabilecek önemli bilgiler sağlar. 

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android Şirket Portalı uygulamanızı en son sürüme güncelleştirme <!--4536963-->
Intune, güncelleştirmeleri düzenli aralıklarla Android Şirket Portalı uygulamasına yayınlar. Kasım 2018 ' de, Google 'ın mevcut bildirim platformundan Google 'ın Firebase bulut mesajlaşmasına (FCM) değişikliğini hazırlamaya yönelik bir arka uç anahtarı içeren bir şirket portalı güncelleştirmesi yayımladık. Google Play Store ile iletişim kurmaya devam etmek için, son kullanıcıların kendi şirket portalı uygulamalarını en az Kasım 2018 sürümüne güncelleştirmiş olması gerekir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Telemetrimiz, 5.0.4269.0 ' den önceki Şirket Portalı sürüme sahip cihazlarınız olduğunu gösterir. Şirket portalı uygulamasının bu sürümü veya üzeri yüklü değilse, BT uzmanı Temizleme, parola sıfırlama, kullanılabilir ve gerekli uygulama yüklemeleri ve sertifika kaydı beklendiği gibi çalışmayabilir. Cihazlarınız Intune 'A kaydedildiyse, Şirket portalı sürümlerini ve kullanıcılarını Istemci uygulamalar – bulunan uygulamalar ' a giderek görebilirsiniz. Şirket Portalı önceki sürümlerinin seçilmesi, son kullanıcıların şirket portalını güncelleştirilmemiş cihazlara sahip olduğunu görmenizi sağlar.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Google Play aracılığıyla şirket portalı 'nı güncelleştirmek üzere güncelleştirilmemiş son Android cihaz kullanıcılarına sorun. Bir kullanıcının şirket portalı uygulamasının otomatik olarak güncelleştirilmesini tutmamaları durumunda yardım masasına bildirin. Google 'ın FCM platformu ve değişikliği hakkında daha fazla bilgi için bağlantıya bakın.

#### <a name="additional-information"></a>Ek bilgiler
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Intune 'a gelen yeni tam ekran deneyimi <!--4593669-->
Azure portal Intune 'a güncelleştirilmiş Kullanıcı arabirimi deneyimlerini oluşturma ve düzenleme hakkında bilgi alırız. Bu yeni deneyim, bir dikey pencerede sıkıştırılmış bir sihirbaz stili biçimi kullanarak mevcut iş akışlarını basitleştirir. Bu güncelleştirme "dikey pencere genişlemesine" ya da derin dikey pencerenin ayrıntılarına gidebilmeniz için akış oluştur ve Düzenle akışları ile çalışır. İş akışları oluşturma, atamaları içerecek şekilde da güncelleştirilecektir (uygulama ataması hariç).

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Tam ekran deneyimi, portal.azure.com ve devicemanagement.microsoft.com ' de bir sonraki birkaç aya göre Intune 'a alınacaktır. Kullanıcı arabirimine yönelik bu güncelleştirme, var olan ilkelerinizin ve profillerinizin işlevlerini etkilemez, ancak biraz değiştirilen bir iş akışı görürsünüz. Örneğin, yeni ilkeler oluşturduğunuzda, ilkeyi oluşturduktan sonra bunu yapmak yerine, bu akışın bir parçası olarak bazı atamalar ayarlayabileceksiniz. Yeni deneyimin konsolda nasıl görüneceğine ilişkin ekran görüntüleri hakkında ek bilgi için blog gönderisine bakın.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanıza gerek yoktur, ancak gerekirse BT uzmanı kılavuzunuzu güncellemeyi göz önüne alabilirsiniz. Bu deneyim Azure portal Intune 'daki çeşitli dikey pencerelere yaptığı için belgelerimizi güncelleştireceğiz.

#### <a name="additional-information"></a>Ek bilgiler 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Değişiklik planı: Intune, Eylül ayının iOS 11 ve üstünü desteklemeye taşınıyor <!-- 4665342-->
Eylül ayında, iOS 13 ' ün Apple tarafından Yayınlanma bekliyor. Intune kaydı, Şirket Portalı ve Managed Browser iOS 13 sürümünden kısa bir süre sonra iOS 11 ve sonraki sürümleri destekleyecek şekilde hareket edecektir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
O365 mobil uygulamalarının iOS 11,0 ve üzeri sürümlerde desteklendiğinden, bu durum sizi etkilemeyebilir; büyük olasılıkla işletim sistemini veya cihazlarınızı zaten yükseltdiniz. Ancak, aşağıda listelenen bir cihaz varsa veya aşağıda listelenen cihazların herhangi birini kaydetmeyi seçerseniz, aşağıdaki cihazların iOS 10 ' dan büyük bir işletim sistemini desteklemediğini öğrenin. Bu cihazların, iOS 11 veya üstünü destekleyen bir cihaza yükseltilmesi gerekir:

- iPhone 5
- iPhone 5c
- iPad (4. nesil)

Temmuz 'dan itibaren, iOS 10 ile MDM 'ye kayıtlı cihazlar ve Şirket Portalı işletim sistemini veya cihazını yükseltmek için bir istem alır. Uygulama koruma Ilkeleri (uygulama) kullanıyorsanız, "En düşük iOS işletim sistemi (yalnızca uyarı) ıste" Erişim ayarını da ayarlayabilirsiniz.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Hangi cihazların veya kullanıcıların etkilendiğini görmek için Intune Raporlama ' yı denetleyin. **Cihazlar** > **tüm cihazlar** ' a gidin ve işletim sistemine göre filtreleyin. Kuruluşunuzdaki kimlerin iOS 10 çalıştıran cihazlara sahip olduğunu belirlemenize yardımcı olması için ek sütunlar ekleyebilirsiniz. Son kullanıcılarınızın Eylül 'den önce cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmesini isteyin.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Değişiklik planı: İOS için Intune uygulama SDK 'sının sürüm 8.1.1 ve üzeri desteği <!-- 3586942-->
Intune, 2019 Eylül 'den başlayarak Intune uygulama SDK 'Sı 8.1.1 ve üzeri ile iOS uygulamalarını destekleyecek şekilde hareket edecektir. SDK sürümleri 8.1.1 'dan oluşturulan uygulamalar artık desteklenmeyecektir. Bu değişiklik, Apple 'ın, Eylül ayında gelmesi beklenen ve MC181399 ' de duyurulacak olan iOS 13 sürümü ile etkili olacak.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Intune uygulama SDK 'Sı veya uygulama sarmalama tümleştirmesiyle, veri şifrelemesi aracılığıyla onaylanmamış uygulamalardan ve kullanıcılardan Şirket verilerini koruyabilirsiniz. İOS için Intune uygulama SDK 'Sı, şifreleme Intune Uygulama Koruması Ilkeleri (uygulama) tarafından etkinleştirildiğinde varsayılan olarak 256 bitlik şifreleme anahtarlarını kullanacaktır. Bu değişiklikten sonra, 128-bit şifreleme anahtarları kullanan 8.1.1 ' den önceki SDK sürümlerindeki iOS uygulamaları, artık SDK 8.1.1 ile tümleştirilmiş uygulamalarla veya 256 bit anahtarları kullanarak verileri paylaşamaz. Korunan veri paylaşımına izin vermek için tüm iOS uygulamalarının bir SDK sürümü 8.1.1 veya daha yüksek olması gerekir.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Microsoft, üçüncü taraf ve iş kolu (LOB) uygulamalarınızı kontrol edin. Intune uygulamasıyla korunan tüm uygulamalarınızın SDK sürüm 8.1.1 veya üstünü kullandığından emin olmanız gerekir.

- LOB uygulamaları için: SDK sürümü 8.1.1 veya üzeri ile tümleştirilmiş uygulamalarınızı yeniden yayımlamanız gerekebilir. En son SDK sürümünü öneririz. LOB uygulamalarınızı uygulama koruma ilkelerine hazırlama hakkında daha fazla bilgi için bkz. [iş kolu uygulamalarını uygulama koruma ilkeleri Için hazırlama](../apps-prepare-mobile-application-management.md).
- Microsoft/üçüncü taraf uygulamaları için: Bu uygulamaların en son sürümünü kullanıcılarınıza dağıttığınızdan emin olun.

Ayrıca, bu değişikliği SDK desteği 'ne dahil etmek için geçerliyse belgelerinizi veya geliştirici kılavuzunuzu da güncelleştirmeniz gerekir.

#### <a name="additional-information"></a>Ek bilgiler
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Değişiklik planı: Intune 'da yeni Windows güncelleştirmeleri ayarları <!-- 4464404 -->
Intune hizmetine veya 1908 Ağustos sürümünden başlayarak, "kullanıcının yeniden başlatılmasına Izin ver (bağlı yeniden başlatma)" ayarlarını yerine yapılandırabileceğiniz yeni "son tarih ayarları" na ekleniyoruz. 1909 veya Eylül güncelinizdeki Kullanıcı arabirimindeki etkin yeniden başlatma ayarlarını devre dışı bırakmayı planlıyoruz ve ardından bunları Ekim sonuna doğru konsolundan tamamen kaldırdık. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Windows 10 cihazlarını ortamınızda yönetiyorsanız: 
- Intune güncelleştirmesi veya 1908 ile, yeni son tarih ayarlarını, eski denetimli yeniden başlatma ayarlarına ek olarak konsolunda görürsünüz.
- Bu eski ve yeni ayarların her ikisi de yapılandırıldığında, son tarih ayarı değerleri, bağlı yeniden başlatma ayarı değerlerini geçersiz kılar.
- Son tarih ayarları, 1910 güncelleştirmesinin konsolunda bulunan "kullanıcının yeniden başlatılmasına Izin ver (yeniden başlatma) seçeneği yerine geçecek.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
İstenen değerlerle yapılandırarak 1908 içindeki son tarih ayarlarını kullanmaya başlayın. Bunu yaptıktan sonra, Ekim 'de konsolundan kaldırılmalarını hazırlamak için, bağlı yeniden başlatma ayarını "Yapılandırılmadı" olarak ayarlayabilirsiniz.

Belgelerinizi ve gerekirse otomasyon komut dosyalarını güncelleştirin. 

Çalışmaya devam eden yeniden başlatma ayarlarını kaldırmadan önce, Ileti merkezine güncelleştirdiğimiz ve bir anımsatıcı göndereceğiz.
