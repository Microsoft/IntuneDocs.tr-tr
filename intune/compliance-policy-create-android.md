---
title: Microsoft Intune - Azure'da Android cihaz uyumluluk ayarları | Microsoft Docs
description: Android cihazları için Uyumluluk Intune ayarlarken kullanabileceğiniz tüm ayarları bir listesini görürsünüz. Parola kuralları ayarla, minimum veya maksimum işletim sistemi sürümünü seçin, belirli uygulamaları kısıtlarsınız, yeniden kullanma parola ve daha fazlasını engelle.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7670af46657fed048bfe10b8659eae6d45db7620
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423586"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Cihazları uyumlu veya uyumsuz Intune kullanan olarak işaretlemek için android ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve ıntune'da Android cihazlarda yapılandırabileceğiniz farklı uyumluluk ayarları açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek, izin verilen tehdit düzeyini ayarlamak, Google Play Protect ve daha fazlasını etkinleştirmek için kullanın.

Bu özellik şu platformlarda geçerlidir:

- Android

Bir Intune Yöneticisi olarak, Kurumsal kaynaklarınızı korumaya yardımcı olmak için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri hakkında daha fazla, hangi bilgi edinmek için bkz [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Android**’i seçin.

## <a name="device-health"></a>Device health

- **Köklü cihazlar**: Seçin **blok** kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek için. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak bu ayarı kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en çok, güvenli, cihazda hiçbir tehdit olmaması gibi. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu seçenek en az güvenli seçenektir ve tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

### <a name="google-play-protect"></a>Google Play koruması

- **Google Play Hizmetleri yapılandırıldı**: **Gerekli** Google Play uygulaması Hizmetleri yüklü ve etkin. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: **Gerekli** bir cihaz güncel güvenlik sağlayıcısı tarafından bilinen güvenlik açıklarına karşı koruyabilir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Uygulamalarda tehdit taraması**: **Gerekli** , Android **uygulamaları doğrula** özelliği etkinleştirilir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  > [!NOTE]
  > Eski Android platformunda bu özellik bir uyumluluk ayarıdır. Intune yalnızca bu ayarın cihaz düzeyinde etkinleştirilip etkinleştirilmediğini denetleyebilir.

- **SafetyNet cihaz kanıtlama**: Düzeyini [SafetyNet cihaz kanıtlama](https://developer.android.com/training/safetynet/attestation.html) uyulması gereken. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış** (varsayılan): Ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

> [!NOTE]
> Uygulama koruma ilkelerini kullanarak Google Play Koruması ayarlarını yapılandırmak için bkz [Intune uygulama koruma İlkesi ayarları](app-protection-policy-settings-android.md#conditional-launch) Android.

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **En düşük işletim sistemi sürümü**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltmenin nasıl gerçekleştirileceği hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Bir cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, şirket kaynaklarına erişimi engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Minimum parola uzunluğu**: En düşük rakam veya kullanıcı parolasının içermesi gereken karakter sayısını girin.
- **Gerekli parola türü**: Parola yalnızca sayısal karakter veya sayı bir karışımını ve diğer karakterler içermelidir, seçin. Seçenekleriniz şunlardır:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal** (varsayılan)
  - **Sayısal karmaşık**: Yinelenen veya ardışık rakamları gibi `1111` veya `1234`, izin verilmez.
  - **En az alfabetik** 
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**

- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir parola oluşturacağı önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamayacak yeni parola sayısını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

### <a name="encryption"></a>Şifreleme

- **Bir cihazdaki veri depolamasının şifrelenmesi** (Android 4.0 ve üzeri veya KNOX 4.0 ve üstü): Seçin **gerektiren** cihazlarınızda veri deposunu şifrelemek için. **Mobil cihazların kilidini açmak için parola iste** ayarını seçtiğinizde cihazlar şifrelenir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamaları engelle**: Tercih **blok** cihazlarla "Güvenlik > bilinmeyen kaynaklar" etkin kaynakları (Android 4.0 – Android 7.x desteklenir; değil desteklenen Android 8.0 ve üzeri). **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın. 

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

- **Şirket portalı uygulaması çalışma zamanı bütünlüğü**: Seçin **gerektiren** şirket Portalı'nı onaylamak için uygulama aşağıdaki tüm gereksinimleri karşılayan:

  - Varsayılan çalışma zamanı ortamı yüklü
  - Doğru şekilde imzalanmış
  - Hata ayıklama modunda değil
  - Bilinen bir kaynaktan yüklenmiş

  **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda blok USB hata ayıklamasını** (Android 4.2 veya üzeri): Seçin **blok** cihazların USB hata ayıklama özelliğini kullanmalarını engellemek üzere. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **En düşük güvenlik düzeltme eki düzeyi** (Android 6.0 veya üzeri): Cihazın sahip olabileceği en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin `YYYY-MM-DD` biçiminde girilmesi gerekir.
- **Kısıtlı uygulamalar**: Girin **uygulama adı** ve **uygulama paket kimliği** sınırlandırılmalıdır uygulamalar için. Seçin **ekleme**. Kısıtlı uygulamalardan en az birinin yüklü olduğu cihaz uyumsuz olarak işaretlenir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="locations"></a>Konumlar

İlkenizde, cihazın konumunu göre uyumluluk zorlayabilirsiniz. Mevcut konumlardan seçin. Henüz bir konumunuz yok mu? [(Ağ sınırı) konumlarını kullanın](use-network-locations.md) Intune'da rehberlik sağlar.

1. Seçin **konumları** > **konumları seçin**.
2. Listeden konumunuz denetleyin > **seçin**.
3. İlkeyi **kaydedin**.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlar için Eylemler ekleme](actions-for-noncompliance.md) ve [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).
- [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md).
- Bkz: [Android Enterprise için Uyumluluk İlkesi ayarları](compliance-policy-create-android-for-work.md) cihazlar.
