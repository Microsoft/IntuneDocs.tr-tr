---
title: Microsoft Intune - Azure'da Android Kurumsal uyumluluk ayarları | Microsoft Docs
description: Android Kurumsal cihazlarınız için Uyumluluk Intune ayarlarken kullanabileceğiniz tüm ayarları bir listesini görürsünüz. Parola kuralları ayarla, minimum veya maksimum işletim sistemi sürümünü seçin, belirli uygulamaları kısıtlarsınız, yeniden kullanma parola ve daha fazlasını engelle.
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
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16db0acab84a1095c40e9a92648c75c2581187cd
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423569"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Cihazları uyumlu veya uyumsuz Intune kullanan olarak işaretlemek için android Kurumsal ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve ıntune Android Kurumsal cihazlarda yapılandırabileceğiniz farklı uyumluluk ayarları açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek, izin verilen tehdit düzeyini ayarlamak, Google Play Protect ve daha fazlasını etkinleştirmek için kullanın.

Bu özellik şu platformlarda geçerlidir:

- Android Kurumsal

Bir Intune Yöneticisi olarak, Kurumsal kaynaklarınızı korumaya yardımcı olmak için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri hakkında daha fazla, hangi bilgi edinmek için bkz [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). İçin **Platform**seçin **Android Kurumsal**.

## <a name="device-health"></a>Device health

- **Köklü cihazlar**: Seçin **blok** kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek için. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak bu ayarı kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu seçenek en az güvenli olduğu gibi tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

### <a name="google-play-protect"></a>Google Play koruması

- **Google Play Hizmetleri yapılandırıldı**: **Gerekli** Google Play uygulaması Hizmetleri yüklü ve etkin. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: **Gerekli** bir cihaz güncel güvenlik sağlayıcısı tarafından bilinen güvenlik açıklarına karşı koruyabilir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **SafetyNet cihaz kanıtlama**: Düzeyini [SafetyNet cihaz kanıtlama](https://developer.android.com/training/safetynet/attestation.html) uyulması gereken. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış** (varsayılan): Ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

> [!NOTE]
> Android Kurumsal cihazlarda **uygulamalarda tehdit taraması** bir cihaz yapılandırma ilkesi. Bir yapılandırma İlkesi'ni kullanarak, Yöneticiler bir cihazdaki ayarını etkinleştirebilirsiniz. Bkz. [Android için Intune cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Cihaz özellikleri ayarları

- **En düşük işletim sistemi sürümü**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükselttikten sonra şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Bir cihaz işletim sistemi sürümü kuralda belirtilenden sonraki kullanırken, şirket kaynaklarına erişimi engellenir. Ve kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayar cihaz düzeyinde uygulanır. İş profili düzeyinde bir parola gerektir gerekiyorsa, bir yapılandırma İlkesi'ni kullanın. Bkz: [Android Kurumsal cihaz yapılandırma ayarları](device-restrictions-android-for-work.md).
- **Minimum parola uzunluğu**: En az kaç rakam veya kullanıcı parolasının içermesi gereken karakter girin.
- **Gerekli parola türü**: Parola yalnızca sayısal karakter veya sayı bir karışımını ve diğer karakterler içermelidir, seçin. Seçenekleriniz şunlardır:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal** (varsayılan)
  - **Sayısal karmaşıklık**
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**

- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir tane oluşturmanız gerekir önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamayacak yeni parola sayısını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

### <a name="encryption"></a>Şifreleme

- **Cihazdaki veri depolamasının şifrelenmesi**: Seçin **gerektiren** cihazlarınızda veri deposunu şifrelemek için. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. 

  Android Kurumsal cihazlarda şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamaları engelle**: Tercih **blok** cihazlarla "Güvenlik > bilinmeyen kaynaklar" etkin kaynakları (Android 4.0 – Android 7.x desteklenir; değil desteklenen Android 8.0 ve üzeri). **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın. 

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

  Android Kurumsal cihazların bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığı olarak bu ayarı yapılandırmanız gerekmez.

- **Şirket portalı uygulaması çalışma zamanı bütünlüğü**: Seçin **gerektiren** şirket Portalı'nı onaylamak için uygulama aşağıdaki tüm gereksinimleri karşılayan:

  - Varsayılan çalışma zamanı ortamı yüklü
  - Doğru şekilde imzalanmış
  - Hata ayıklama modunda değil
  - Bilinen bir kaynaktan yüklenmiş

  **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda blok USB hata ayıklamasını**: Seçin **blok** cihazların USB hata ayıklama özelliğini kullanmalarını engellemek üzere. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  USB hata ayıklama zaten Android Kurumsal cihazlarda devre dışı olduğundan bu ayarı yapılandırmanız gerekmez.

- **En düşük güvenlik düzeltme eki düzeyi**: Cihazın sahip olabileceği en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin *YYYY-AA-GG* biçiminde girilmesi gerekir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlar için Eylemler ekleme](actions-for-noncompliance.md) ve [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).
- [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md).
- Bkz: [Android için Uyumluluk İlkesi ayarları](compliance-policy-create-android.md) cihazlar.
