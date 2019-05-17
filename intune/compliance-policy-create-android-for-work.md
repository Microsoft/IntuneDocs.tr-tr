---
title: Microsoft Intune - Azure’daki Android Kurumsal uyumluluk ayarları | Microsoft Docs
description: Microsoft Intune'da Android Kurumsal cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Parola kurallarını ayarlayın, en düşük veya en yüksek işletim sistemi sürümünü seçin, belirli uygulamaları kısıtlayın, parolaların yeniden kullanılmasını engelleyin ve çok daha fazlasını yapın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/15/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7a9a5ff686ce3cff8b60c2bd1c0c5d108d58760
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896896"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz Android Kurumsal ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede Intune'daki Android Kurumsal cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları kullanabilir ve bu sayede kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumlu değil olarak işaretleyebilir, izin verilen tehdit düzeyi belirleyebilir, Google Play Koruması'nı etkinleştirebilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Android Kurumsal

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

> [!IMPORTANT]
> Uyumluluk ilkeleri, ayrılmış Android Kurumsal cihazları için de geçerlidir. Bir cihaza uyumluluk ilkesinin atanması durumunda cihaz **Uyumlu değil** şeklinde görünebilir. Koşullu erişim ve uyumluluk zorlama, ayrılmış cihazlarda kullanılamaz. Ayrılmış cihazların atanan ilkelerinizle uyumlu olmasını sağlamak için gerekli görevleri veya eylemleri gerçekleştirdiğinizden emin olun.

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Android Kurumsal**’ı seçin.

## <a name="device-owner"></a>Cihaz sahibi

### <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükselttikten sonra kuruluş kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, kuruluş kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz kuruluş kaynaklarına erişemez.

### <a name="system-security"></a>Sistem güvenliği

- **Mobil cihazların kilidini açmak için bir parola iste**: Kullanıcıların cihazlarına erişebilmesi için önce bir parola girmesini **zorunlu tutun**. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Bu ayar cihaz düzeyinde uygulanır. Yalnızca iş profili düzeyinde parola kullanılmasını istiyorsanız bir yapılandırma ilkesi kullanabilirsiniz. Bkz. [Android için Intune cihaz yapılandırma ayarları](device-restrictions-android-for-work.md).

  - **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
    - **Cihaz varsayılanı**
    - **Parola gerekli, kısıtlama yok**
    - **Zayıf biyometrik**: [Güçlü ile zayıf biyometrik arasındaki farklar](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (Android web sitesinde açılır)
    - **Sayısal**: Parola yalnızca sayı olmalıdır, örneğin: `123456789`. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - **Sayısal karmaşıklık**: Yinelenen veya ardışık sayılara (örneğin "1111" veya "1234") izin verilmez. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - **Alfabetik**: Alfabedeki harflerin kullanılması gerekir. Rakamlar ve simgeler zorunlu tutulmaz. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - **Alfasayısal**: Büyük harfler, küçük harfler ve sayısal karakterleri içerir. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - **Simgelerle alfasayısal**: Büyük harfler, küçük harfler, sayısal karakterler, noktalama işaretleri ve simgeleri içerir. Şunları da girin:

      - **Minimum parola uzunluğu**: Parola uzunluğu alt sınırını girin (4 ile 16 karakter arasında).
      - **Gereken karakter sayısı**: Parolada bulunması gereken karakter sayısını girin (0 ile 16 karakter arasında).
      - **Gereken küçük harf karakter sayısı**: Parolada bulunması gereken küçük harf karakteri sayısını girin (0 ile 16 karakter arasında).
      - **Gereken büyük harf karakter sayısı**: Parolada bulunması gereken büyük harf karakteri sayısını girin (0 ile 16 karakter arasında).
      - **Gereken harf dışı karakter sayısı**: Parolada bulunması gereken harf dışı karakter sayısını (alfabedeki harflerin dışındaki karakterler, 0 ile 16 karakter arasında) girin.
      - **Gereken sayısal karakter sayısı**: Parolada bulunması gereken sayısal karakter sayısını (`1`, `2`, `3` gibi, 0 ile 16 karakter arasında) girin.
      - **Gereken simge karakter sayısı**: Parolada bulunması gereken simge karakter sayısını (`&`, `#`, `%` gibi, 0 ile 16 karakter arasında) girin.

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Parola süresinin dolmasına kalan gün sayısı**: Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını (1 ile 365 arasında) girin. Örneğin parolanın 60 gün sonra değiştirilmesi için `60` girin. Parola geçerlilik süresi dolduğunda kullanıcıların yeni bir parola oluşturması istenir.
- **Kullanıcının bir parolayı yeniden kullanabilmesi için geçmesi gereken parola sayısı**: Yeniden kullanılamayacak parolalar için 1 ile 24 arasında bir sayı girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

- **Cihazda veri deposunun şifrelenmesi**: Cihazlarınızda veri deposunun şifrelenmesini sağlamak için **Gerekli Kıl**'ı seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Android Kurumsal cihazlarında şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="work-profile"></a>İş profili

### <a name="device-health"></a>Device health

- **Kök erişim izni verilmiş cihazlar**: Kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumsuz olarak işaretlemek için **Engelle**’yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın Cihaz Tehdit Düzeyinde veya bu düzeyin altında olmasını gerekli kıl**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda hiçbir tehdit olmaması gerektiği anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz, uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

#### <a name="google-play-protect"></a>Google Play Koruması

- **Google Play Hizmetleri yapılandırıldı**: Google Play hizmetleri uygulamasının yüklenmiş ve etkinleştirilmiş olmasını **gerektirir**. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: Güncel bir güvenlik sağlayıcısının cihazları bilinen güvenlik açıklarına karşı korumasını **gerektirir**. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Ayar, uyumluluk veya uyumsuzluk açısından değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

> [!NOTE]
> Android Kurumsal cihazlardaki **Uygulamalarda tehdit taraması**, bir cihaz yapılandırma ilkesidir. Yöneticiler, yapılandırma ilkesini kullanarak bu ayarı cihazlarda etkinleştirebilir. Bkz. [Android için Intune cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükselttikten sonra kuruluş kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, kuruluş kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz kuruluş kaynaklarına erişemez.

### <a name="system-security"></a>Sistem güvenliği

- **Mobil cihazların kilidini açmak için bir parola iste**: Kullanıcıların cihazlarına erişebilmesi için önce bir parola girmesini **zorunlu tutun**. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayar cihaz düzeyinde uygulanır. Yalnızca iş profili düzeyinde parola kullanılmasını istiyorsanız bir yapılandırma ilkesi kullanabilirsiniz. Bkz. [Android için Intune cihaz yapılandırma ayarları](device-restrictions-android-for-work.md).
- **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal** (varsayılan): Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Sayısal karmaşıklık**: Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **En az alfabetik**: Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **En az alfasayısal**: Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **En az simgeler ile alfasayısal**: Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Parola süresinin dolmasına kalan gün sayısı**: Son kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Yeniden kullanılamayacak parolalar için bir sayı girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

#### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**: Cihazlarınızda veri deposunun şifrelenmesini sağlamak için **Gerekli Kıl**'ı seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. 

  Android Kurumsal cihazlarında şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

#### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan uygulamaları engelleme**: **Güvenlik** > **Bilinmeyen Kaynaklar** etkin kaynaklara sahip cihazları **engellemeyi** seçin (Android 4.0 ve Android 7.x sürümlerinde desteklenir; Android 8.0 ve üzeri sürümlerde desteklenmez). **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın.

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

  Android Kurumsal cihazları bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığından, bu ayarı yapılandırmanız gerekmez.

- **Şirket Portalı uygulaması çalışma zamanı bütünlüğü**: Şirket Portalı uygulamasının aşağıdaki tüm gereksinimleri karşıladığını onaylamak için **Gerekli Kıl**’ı seçin:

  - Varsayılan çalışma zamanı ortamı yüklü
  - Doğru şekilde imzalanmış
  - Hata ayıklama modunda değil
  - Bilinen bir kaynaktan yüklenmiş

  **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda USB hata ayıklamasını engelleme**: Cihazların USB hata ayıklama özelliğini kullanmasını önlemek için **Engelle**’yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Android Kurumsal cihazlarında USB hata ayıklama zaten devre dışı olduğundan bu ayarı yapılandırmanız gerekmez.

- **Minimum güvenlik düzeltme düzeyi**: Bir cihazda olabilecek en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin *YYYY-AA-GG* biçiminde girilmesi gerekir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [Android cihazları için uyumluluk ilkesi ayarları](compliance-policy-create-android.md).
