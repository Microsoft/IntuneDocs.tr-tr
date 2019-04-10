---
title: Microsoft Intune - Azure'da iOS cihaz uyumluluk ayarları | Microsoft Docs
description: İOS cihazları için Uyumluluk Intune ayarlarken kullanabileceğiniz tüm ayarları bir listesini görürsünüz. E-posta gerektirir, jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda denetleyin, izin verilen en düşük ve en yüksek işletim sistemi, parola uzunluğu ile cihazda işlem yapılmayan süre de dahil olmak üzere, herhangi bir parola kısıtlamalarını ayarlamak, uygulamaları ve diğer kısıtlayın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ec071622a2e0d49068864f8bfb47954f54c8ba4
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423620"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>cihazları uyumlu veya uyumsuz Intune kullanan olarak işaretlemek için iOS ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve ıntune'da iOS cihazlarda yapılandırabileceğiniz farklı uyumluluk ayarları açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları gerektiren bir e-posta, kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek, izin verilen bir tehdit süresi dolacak şekilde düzeyi, ayarlanmış parolaları ayarlamanız ve daha fazlasını kullanın.

Bu özellik şu platformlarda geçerlidir:

- iOS

Bir Intune Yöneticisi olarak, Kurumsal kaynaklarınızı korumaya yardımcı olmak için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri hakkında daha fazla, hangi bilgi edinmek için bkz [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **iOS**’u seçin.

## <a name="email"></a>Email

- **Mobil cihazların yönetilen e-posta profili olmasını gerektir**: Ayarlandığında **gerektiren**, Intune tarafından yönetilen bir e-posta profili olmayan cihazları olarak kabul edilir değil uyumlu. Bir cihaz doğru hedeflenmediğinde veya kullanıcı cihazdaki e-posta hesabını el ile ayarlamanız durumunda, bir yönetilen e-posta profili sahip olamaz. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Cihaz aşağıdaki durumlarda uyumlu olarak kabul edilir:

  - E-posta profili uyumluluk ilkesinin hedeflediği kullanıcı grubuyla değerinden farklı bir kullanıcı grubuna atanır.
  - Kullanıcı cihazda cihaza dağıtılan Intune e-posta profiliyle eşleşen bir e-posta hesabı zaten ayarlayın. Intune kullanıcı tarafından yapılandırılan profilin üzerine yazamaz ve Intune yönetemez. Uyumlu olması için son kullanıcı mevcut e-posta ayarları kaldırmanız gerekir. Ardından, Intune yönetilen e-posta profilini yükleyebilir.

- **Intune tarafından yönetilmesi gereken e-posta profili seçin**: Varsa **e-posta hesabı Intune tarafından yönetilmelidir** ayarı seçildiyse, **seçin** için Intune e-posta profili girin. E-posta profili cihazda mevcut olmalıdır.

E-posta profilleri hakkında daha fazla ayrıntı için bkz: [Intune ile e-posta profilleri kullanarak kuruluş e-postasına erişimi yapılandırma](email-settings-configure.md).

## <a name="device-health"></a>Device health

- **Jailbreak uygulanmış cihazlar**: Seçin **blok** kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek için. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir** (iOS 8.0 ve üzeri): Risk değerlendirmesini uyumluluk koşulu olarak bu ayarı kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi ile algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu olmayan olarak belirledi.
  - **Yüksek**: Bu seçenek en az güvenli olduğu gibi tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

## <a name="device-properties"></a>Cihaz özellikleri

- **Gerekli en düşük işletim sistemi** (iOS 8.0 ve üzeri): Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında, ile uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçebilir. Bundan sonra kuruluş kaynaklarına erişim sağlayabilir.
- **İzin verilen en yüksek işletim sistemi sürümü** (iOS 8.0 ve üzeri): Bir cihaz bir işletim sistemi sürümünü kuralda belirtilenden sonraki kullanır, kuruluş kaynaklarına erişim engellenir. Son kullanıcı kendi BT yöneticisine başvurması istenir. Cihaz, işletim sistemine izin veren bir kural olana kadar kuruluş kaynaklarına erişemez.
- **En düşük işletim sistemi derleme sürümü** (iOS 8.0 ve üzeri): Apple güvenlik güncelleştirmeleri yayımlarken, yapı numarası genellikle güncelleştirilir, işletim sistemi sürümü. Cihazda bir izin verilen en düşük yapı numarası girmek için bu özelliği kullanın.
- **En yüksek işletim sistemi derleme sürümü** (iOS 8.0 ve üzeri): Apple güvenlik güncelleştirmeleri yayımlarken, yapı numarası genellikle güncelleştirilir, işletim sistemi sürümü. Cihazda bir izin verilen en fazla yapı numarası girmek için bu özelliği kullanın.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

> [!NOTE]
> iOS cihazına uyumluluk veya yapılandırma ilkesi uygulandıktan sonra her 15 dakikada bir kullanıcılardan bir geçiş kodu ayarlamaları istenir. Geçiş kodu ayarlanana kadar kullanıcılara sürekli bu istem gönderilir.

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin. Parola kullanılan iOS cihazları şifrelenir.
- **Basit parolalar**: Kümesine **blok** kullanıcılar gibi basit parolalar oluşturamıyor **1234** veya **1111**. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: En düşük rakam veya karakter bulunması gereken sayısını girin.
- **Gerekli parola türü**: Parola yalnızca olması gerekip gerekmediğini seçin **sayısal** karakter veya sayı ve diğer karakterlerin bir karışımı yoksa (**alfasayısal**).
- **Paroladaki alfasayısal olmayan karakter sayısı**: En az özel karakter sayısını girin `&`, `#`, `%`, `!`ve benzeri Parolada olması gerekir.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir tane oluşturmanız gerekir önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamaz önceden kullanılmış parola sayısını girin.

### <a name="device-security"></a>Cihaz güvenliği

- **Kısıtlı uygulamalar**: Uygulamaların paket kimliklerini ilkeye ekleyerek bunları kısıtlayabilirsiniz. Uygulamasının yüklü olduğu bir cihazı varsa cihaz uyumsuz olarak işaretlenir.

  - **Uygulama adı**: Paket kimliğini tanımlamanıza yardımcı olacak bir kolay ad girin
  - **Uygulama paketi kimliği**: Uygulama sağlayıcısı tarafından atanmış benzersiz paket grubu tanımlayıcısı girin. Paket Kimliğini bulmak için bkz: [paket Kimliğini bulmak için bir iOS uygulamasını nasıl](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (başka bir Microsoft web sitesini açar).  

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlar için Eylemler ekleme](actions-for-noncompliance.md) ve [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).
- [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md).
- Bkz: [macOS için Uyumluluk İlkesi ayarları](compliance-policy-create-mac-os.md) cihazlar.
