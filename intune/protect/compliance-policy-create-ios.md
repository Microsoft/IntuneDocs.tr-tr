---
title: Microsoft Intune - Azure’daki iOS cihazı uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da iOS cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. E-postayı zorunlu kılın, jailbreak uygulanmış veya kök erişim izni verilmiş cihazları denetleyin, izin verilene işletim sistemi alt ve üst sınırını ayarlayın, parola uzunluğu ve cihaz boş durma süresi dahil olmak üzere parola kısıtlaması ayarlayın, uygulamaları kısıtlayın ve daha fazlasını yapın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5f473e376278b454ca2d173c7c147137226a9fc9
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601501"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz iOS ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede Intune'daki iOS cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları kullanabilir ve bu sayede e-posta kullanılmasını zorunlu kılabilir, kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumlu değil olarak işaretleyebilir, izin verilen tehdit düzeyi belirleyebilir, parolaların kullanım süresini kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- iOS

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **iOS**’u seçin.

## <a name="email"></a>E-posta

- **Mobil cihazların yönetilen bir e-posta profili olmasını gerektir**: **gerekli**olarak ayarlandığında, Intune tarafından yönetilen bir e-posta profili olmayan cihazlar uyumlu değil olarak kabul edilir. Bir cihaz doğru hedeflenmediğinde veya kullanıcı cihazda e-posta hesabını el ile ayarladığında, cihazda yönetilen bir e-posta profili olmaz. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Aşağıdaki durumlarda cihaz uyumsuz olarak kabul edilir:

  - E-posta profili, uyumluluk ilkesi tarafından hedeflenen kullanıcı grubu dışındaki bir kullanıcı grubuna atanmış.
  - Kullanıcı, cihaza dağıtılan Intune e-posta profiliyle eşleşen bir e-posta hesabını cihazda önceden ayarlamış. Intune, kullanıcı tarafından yapılandırılan profilin üzerine yazamaz ve onu yönetemez. Uyumluluk sağlamak için son kullanıcının mevcut e-posta ayarlarını kaldırması gerekir. Ardından, Intune yönetilen e-posta profilini yükleyebilir.

- **Intune tarafından yönetilmesi gereken e-posta profilini seçin**: **e-posta hesabı Intune tarafından yönetilmelidir** ayarı seçildiyse, Intune e-posta profilini girmek için **Seç** ' i seçin. E-posta profili cihazda mevcut olmalıdır.

E-posta profilleri hakkında ayrıntılı bilgi için bkz. [Intune ile e-posta profilleri kullanarak kuruluş e-postasına erişimi yapılandırma](../configuration/email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Jailbreak uygulanmış cihazlar**: kökü belirtilen (Jailbreak uygulanmış) cihazları uyumsuz olarak Işaretlemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya altında olmasını gerektir** (iOS 8,0 ve üzeri): Bu ayarı, risk değerlendirmesini uyumluluk koşulu olarak almak için kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda hiçbir tehdit olmaması gerektiği anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz, uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

## <a name="device-properties"></a>Cihaz özellikleri

- **Gerekli en düşük işletim sistemi** (iOS 8,0 ve üzeri): bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında, uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı cihazını yükseltmeyi seçebilir. Bundan sonra, kuruluş kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü** (iOS 8,0 ve üzeri): bir cihaz kuraldaki sürümden daha sonraki bir işletim sistemi sürümünü kullandığında, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz kuruluş kaynaklarına erişemez.
- **En düşük işletim sistemi derleme sürümü** (iOS 8,0 ve üzeri): Apple güvenlik güncelleştirmeleri yayımladığında, işletim sistemi sürümü değil, derleme numarası genellikle güncellenir. Bu özelliği kullanarak cihazda izin verilen en düşük işletim sistemi derleme sürümünü girebilirsiniz.
- **En yüksek işletim sistemi derleme sürümü** (iOS 8,0 ve üzeri): Apple güvenlik güncelleştirmeleri yayımladığında, işletim sistemi sürümü değil, derleme numarası genellikle güncellenir. Bu özelliği kullanarak cihazda izin verilen en yüksek işletim sistemi derleme sürümünü girebilirsiniz.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>Parola

> [!NOTE]
> iOS cihazına uyumluluk veya yapılandırma ilkesi uygulandıktan sonra her 15 dakikada bir kullanıcılardan bir geçiş kodu ayarlamaları istenir. Geçiş kodu ayarlanana kadar kullanıcılara sürekli bu istem gönderilir. İOS cihazı için bir geçiş kodu ayarlandığında, şifreleme işlemi otomatik olarak başlatılır. Geçiş kodu devre dışı bırakılıncaya kadar cihaz şifreli olarak kalır.

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in. Parola kullanılan iOS cihazları şifrelenir.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Gerekli parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.
- **Paroladaki alfasayısal olmayan karakter sayısı**: parolada olması gereken `&`, `#`, `%`, `!` vb. gibi en az özel karakter sayısını girin.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)** : Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılmasını önleyen önceki parola sayısı**: daha önce kullanılan parolaların sayısını girin.

### <a name="device-security"></a>Cihaz güvenliği

- **Kısıtlı uygulamalar**: Uygulamaların paket kimliklerini ilkeye ekleyerek bunları kısıtlayabilirsiniz. Cihazda bu uygulama yüklüyse cihaz uyumsuz olarak işaretlenir.

  - **Uygulama Adı**: Paket kimliğini ayırt etmenize yardımcı olacak bir kolay ad ekleyin.
  - **Uygulama Paket Kimliği**: Uygulama sağlayıcısı tarafından atanmış benzersiz paket tanımlayıcısını girin. Paket Kimliğini bulmak için bkz. [iOS uygulamalarının paket kimliğini bulma](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (başka bir Microsoft web sitesini açar).  

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [macOS cihazları için uyumluluk ilkesi ayarları](compliance-policy-create-mac-os.md).
