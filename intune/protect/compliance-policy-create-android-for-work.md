---
title: Microsoft Intune - Azure’daki Android Kurumsal uyumluluk ayarları | Microsoft Docs
description: Microsoft Intune'da Android Kurumsal cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Parola kurallarını ayarlayın, en düşük veya en yüksek işletim sistemi sürümünü seçin, belirli uygulamaları kısıtlayın, parolaların yeniden kullanılmasını engelleyin ve çok daha fazlasını yapın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/16/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be1fbb72821b61566da84d6f98094c9a2f6ffef2
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810252"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz Android Kurumsal ayarları

Bu makalede Intune'daki Android Kurumsal cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları kullanabilir ve bu sayede kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumlu değil olarak işaretleyebilir, izin verilen tehdit düzeyi belirleyebilir, Google Play Koruması'nı etkinleştirebilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Android Kurumsal

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

> [!IMPORTANT]
> Uyumluluk ilkeleri, ayrılmış Android Kurumsal cihazları için de geçerlidir. Bir cihaza uyumluluk ilkesinin atanması durumunda cihaz **Uyumlu değil** şeklinde görünebilir. Koşullu erişim ve uyumluluk zorlama adanmış cihazlarda kullanılamaz. Ayrılmış cihazların atanan ilkelerinizle uyumlu olmasını sağlamak için gerekli görevleri veya eylemleri gerçekleştirdiğinizden emin olun.

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Android Kurumsal**’ı seçin.

## <a name="device-owner"></a>Cihaz sahibi

### <a name="device-health"></a>Cihaz durumu

- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir**: [Mobile Threat Defense hizmetiniz](mobile-threat-defense.md)tarafından değerlendirilen izin verilen maksimum cihaz tehdit düzeyini seçin. Bu tehdit düzeyini aşan cihazlar uyumsuz olarak işaretlenir. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:

  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Güvenli** -Bu seçenek en güvenli seçenektir ve cihazın herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**:-cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta** -cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek** -Bu seçenek, tüm tehdit düzeylerine izin verdiği için en az güvenli seçenektir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
> [!NOTE] 
> Aşağıdaki Mobile Threat Defence (MTD) sağlayıcıları, uygulama yapılandırması kullanılarak Android kurumsal cihaz sahibi dağıtımlarını destekler:
> - Daha iyi mobil 
> - Pradeo
> - Sophos Mobile
> - Zimperium 
>  
>  Intune 'da Android kurumsal cihaz sahibi platformlarını desteklemek için gereken tam yapılandırma için MTD sağlayıcınızla görüşün. Bu liste, Android kurumsal cihaz sahibi senaryolarını destekleyen MTD 'ler olarak güncelleştirilir. 

#### <a name="google-play-protect"></a>Google Play Koruması

- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - Yapılandırılmadı (*varsayılan*)-ayar, uyumluluk veya uyumsuzluk Için **değerlendirilmez** .
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

### <a name="device-properties"></a>Cihaz Özellikleri

#### <a name="operating-system-version"></a>İşletim Sistemi Sürümü

- **En düşük işletim sistemi sürümü**: cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükselttikten sonra kuruluş kaynaklarına erişebilir.

  *Varsayılan olarak, sürüm yapılandırılmaz*.

- **En yüksek işletim sistemi sürümü**: cihaz, kuraldaki sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz kuruluş kaynaklarına erişemez.

  *Varsayılan olarak, sürüm yapılandırılmaz*.

- **En düşük güvenlik düzeltme eki düzeyi**: bir cihazda sahip olabilecek en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin YYYY-AA-GG biçiminde girilmesi gerekir.

  *Varsayılan olarak, bir tarih yapılandırılmaz*.


### <a name="system-security"></a>Sistem Güvenliği

- **Mobil cihazların kilidini açmak için bir parola iste**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -kullanıcıların cihazına erişebilmeleri için önce bir parola girmesi gerekir. 

  Bu ayar cihaz düzeyinde geçerlidir. Yalnızca iş profili düzeyinde parola kullanılmasını istiyorsanız bir yapılandırma ilkesi kullanabilirsiniz. Bkz. [Android için Intune cihaz yapılandırma ayarları](../configuration/device-restrictions-android-for-work.md).

  - **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
    - **Cihaz varsayılanı** -parola uyumluluğunu değerlendirmek Için, **cihaz varsayılanı**dışında bir parola gücü seçtiğinizden emin olun.  
    - **Parola gerekli, kısıtlama yok**
    - **Zayıf biyometrik** - [güçlü ve zayıf Biyometri](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (Android 'in Web sitesini açar)
    - **Sayısal** (*varsayılan*): parola yalnızca sayı olmalıdır, örneğin `123456789`. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - "1111" veya "1234" gibi **sayısal karmaşık** yinelenen veya ardışık sayılara izin verilmez. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - Alfabede **alfabetik** harfler gereklidir. Rakamlar ve simgeler zorunlu tutulmaz. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - **Alfasayısal** -büyük harfler, küçük harfler ve sayısal karakterler içerir. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
    - **Simgelerle alfasayısal** -büyük harfler, küçük harfler, sayısal karakterler, noktalama işaretleri ve semboller içerir. Şunları da girin:
    
    Seçtiğiniz *parola türüne* bağlı olarak, aşağıdaki ayarlar kullanılabilir:  
    - **Minimum parola uzunluğu**: parolanın, 4 ile 16 karakter arasında olması gereken minimum uzunluğu girin.  

    - **Gerekli karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken karakter sayısını girin.

    - **Gereken küçük harfli karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken küçük harfli karakter sayısını girin.

    - **Gerekli olan büyük harfli karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken büyük harfli karakter sayısını girin.

    - **Gerekli harf olmayan karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken harf olmayan karakter sayısını (alfabedeki harfler dışında bir şey) girin.

    - **Gerekli sayısal karakter sayısı**: parolanın 0 ile 16 karakter arasında olması gereken sayısal karakter sayısını (`1`, `2`, `3` vb.) girin.
    
    - **Gerekli simge karakter sayısı**: parolanın 0 ile 16 karakter arasında olması gereken simge karakterlerinin (`&`, `#`, `%`vb.) sayısını girin.
 
- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin. Seçenekler, *Yapılandırılmadı*ve *1 dakikadan* *8 saate*kadar varsayılan değer içerir.

- **Parolanın süresi dolana kadar geçen gün sayısı**: cihaz parolasının değiştirilmesi gereken gün sayısını, 1-365 arasında girin. Örneğin parolanın 60 gün sonra değiştirilmesi için `60` girin. Parola geçerlilik süresi dolduğunda kullanıcıların yeni bir parola oluşturması istenir.

   *Varsayılan olarak, hiçbir değer yapılandırılmaz*.

- **Kullanıcının bir parolayı yeniden kullanabilmesi için gereken parola sayısı**: 1-24 arasında en son kullanılan parola sayısını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.  

    *Varsayılan olarak, sürüm yapılandırılmaz*.

#### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - , Cihazlarınızda veri depolamayı **ister** .  

  Android Kurumsal cihazlarında şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

## <a name="work-profile"></a>İş profili

### <a name="device-health"></a>Cihaz durumu

- **Kök erişim izni verilmiş cihazlar**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Block** -root (Jailbreak uygulanmış) cihazlarını uyumsuz olarak işaretle.  

- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir**: [Mobile Threat Defense hizmetiniz](mobile-threat-defense.md)tarafından değerlendirilen izin verilen maksimum cihaz tehdit düzeyini seçin. Bu tehdit düzeyini aşan cihazlar uyumsuz olarak işaretlenir. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:

  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Güvenli** -Bu seçenek en güvenli seçenektir ve cihazın herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük** -cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta** -cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek** -Bu seçenek, tüm tehdit düzeylerine izin verdiği için en az güvenli seçenektir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

#### <a name="google-play-protect"></a>Google Play Koruması

- **Google Play Hizmetleri yapılandırıldı**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -Google Play Services uygulamasının yüklü ve etkin olmasını gerektirir. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. 
  
- **Güncel güvenlik sağlayıcısı**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -güncel bir güvenlik sağlayıcısının bir cihazı bilinen güvenlik açıklarına karşı koruyabilmesini gerektir. 
  
- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - Yapılandırılmadı (*varsayılan*)-ayar, uyumluluk veya uyumsuzluk Için **değerlendirilmez** .
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

> [!NOTE]
> Android Kurumsal cihazlardaki **Uygulamalarda tehdit taraması**, bir cihaz yapılandırma ilkesidir. Yöneticiler, yapılandırma ilkesini kullanarak bu ayarı cihazlarda etkinleştirebilir. Bkz. [Android Kurumsal cihaz kısıtlama ayarları](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Cihaz Özellikleri

#### <a name="operating-system-version"></a>İşletim Sistemi Sürümü

- **En düşük işletim sistemi sürümü**: cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükselttikten sonra kuruluş kaynaklarına erişebilir.

  *Varsayılan olarak, sürüm yapılandırılmaz*.

- **En yüksek işletim sistemi sürümü**: cihaz, kuraldaki sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz kuruluş kaynaklarına erişemez.

  *Varsayılan olarak, sürüm yapılandırılmaz*.

### <a name="system-security"></a>Sistem güvenliği

- **Mobil cihazların kilidini açmak için bir parola iste**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez. 
  - **Gerektir** -kullanıcıların cihazına erişebilmeleri için önce bir parola girmesi gerekir.  

  Bu ayar cihaz düzeyinde geçerlidir. Yalnızca iş profili düzeyinde parola kullanılmasını istiyorsanız bir yapılandırma ilkesi kullanabilirsiniz. Bkz. [Android için Intune cihaz yapılandırma ayarları](../configuration/device-restrictions-android-for-work.md).

- **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - En **az sayısal** (*varsayılan*): kullanıcının, 4 ile 16 karakter arasında girmesi gereken **Minimum parola uzunluğunu** girin.
  - **Sayısal karmaşık**: kullanıcının, 4 ile 16 karakter arasında girmesi gereken **Minimum parola uzunluğunu** girin.
  - En **azından alfabetik**: kullanıcının, 4 ile 16 karakter arasında girmesi gereken **Minimum parola uzunluğunu** girin.
  - En **az alfasayısal**: kullanıcının, 4 ile 16 karakter arasında girmesi gereken **Minimum parola uzunluğunu** girin.
  - **Semboller ile en az alfasayısal**: bir kullanıcının girmesi gereken **Minimum parola uzunluğunu** 4 ile 16 karakter arasında girin.

  Seçtiğiniz *parola türüne* bağlı olarak, aşağıdaki ayarlar kullanılabilir:  
  - **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin. Seçenekler, *Yapılandırılmadı*ve *1 dakikadan* *8 saate*kadar varsayılan değer içerir.

  - **Parolanın süresi dolana kadar geçen gün sayısı**: cihaz parolasının değiştirilmesi gereken gün sayısını, 1-365 arasında girin. Örneğin parolanın 60 gün sonra değiştirilmesi için `60` girin. Parola geçerlilik süresi dolduğunda kullanıcıların yeni bir parola oluşturması istenir.

  - **Minimum parola uzunluğu**: parolanın, 4 ile 16 karakter arasında olması gereken minimum uzunluğu girin. 
  
  - **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

#### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - , Cihazlarınızda veri depolamayı **ister** .  

  Android Kurumsal cihazlarında şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

#### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan uygulamaları engelleme**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Blok** - **güvenlik** > **Bilinmeyen kaynakların** etkinleştirildiği kaynakları engelleyin (Android*4,0 üzerinden Android 7. x aracılığıyla desteklenir). Android 8,0 ve üzeri tarafından desteklenmez*).  

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın.

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

  Android Kurumsal cihazları bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığından, bu ayarı yapılandırmanız gerekmez.

- **Şirket Portalı uygulaması çalışma zamanı bütünlüğü**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -Şirket portalı uygulamanın, aşağıdaki tüm gereksinimleri karşıladığından emin olmak *için gerektir ' i seçin:*
    - Varsayılan çalışma zamanı ortamı yüklü
    - Doğru şekilde imzalanmış
    - Hata ayıklama modunda değil
    - Bilinen bir kaynaktan yüklenmiş

- **Cihazda USB hata ayıklamasını engelleme**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Engelle** -cihazların USB hata ayıklama özelliğini kullanmasını engelleyin.  

  Android Kurumsal cihazlarında USB hata ayıklama zaten devre dışı olduğundan bu ayarı yapılandırmanız gerekmez.

- **En düşük güvenlik düzeltme eki düzeyi**: bir cihazda sahip olabilecek en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin YYYY-AA-GG biçiminde girilmesi gerekir.

  *Varsayılan olarak, bir tarih yapılandırılmaz*.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [Android cihazları için uyumluluk ilkesi ayarları](compliance-policy-create-android.md).
