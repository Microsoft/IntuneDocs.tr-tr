---
title: Microsoft Intune - Azure’daki Android cihazı uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da Android cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Parola kurallarını ayarlayın, en düşük veya en yüksek işletim sistemi sürümünü seçin, belirli uygulamaları kısıtlayın, parolaların yeniden kullanılmasını engelleyin ve çok daha fazlasını yapın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4237b54b3ea89fcf75ce5a21f08012f384eed95c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502524"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz Android ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede Intune'daki Android cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları kullanabilir ve bu sayede kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumlu değil olarak işaretleyebilir, izin verilen tehdit düzeyi belirleyebilir, Google Play Koruması'nı etkinleştirebilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Android

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Android**’i seçin.

## <a name="device-health"></a>Device health

- **Kök erişim izni verilmiş cihazlar**: Kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumsuz olarak işaretlemek için **Engelle**’yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya bu düzeyin altında olmasını gerektir**: Bu ayarı, uyumluluk açısından mobil uç nokta güvenlik çözümünden risk değerlendirmesi gerçekleştirmek için kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Cihazda hiçbir tehdit olmamasını gerektirdiği için bu seçenek en güvenlisidir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazda mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

### <a name="google-play-protect"></a>Google Play koruması

- **Google Play Hizmetleri yapılandırıldı**: Google Play hizmetleri uygulamasının yüklenmiş ve etkinleştirilmiş olmasını **gerektirir**. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: Güncel bir güvenlik sağlayıcısının cihazları bilinen güvenlik açıklarına karşı korumasını **gerektirir**. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Uygulamalarda tehdit taraması**: Android **Uygulamaları Doğrula** özelliğinin etkinleştirilmesini **gerektirir**. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  > [!NOTE]
  > Eski Android platformunda bu özellik bir uyumluluk ayarıdır. Intune yalnızca bu ayarın cihaz düzeyinde etkinleştirilip etkinleştirilmediğini denetleyebilir.

- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Ayar, uyumluluk veya uyumsuzluk açısından değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

> [!NOTE]
> Uygulama koruma ilkelerini kullanarak Google Play Koruması ayarlarını yapılandırmak için bkz. [Android için Intune uygulama koruması ilkesi ayarları](../apps/app-protection-policy-settings-android.md#conditional-launch).

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **En düşük işletim sistemi sürümü**: Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltmenin nasıl gerçekleştirileceği hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. Bir kural, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **En düşük parola uzunluğu**: Kullanıcı parolasında bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**: parola uyumluluğunu değerlendirmek Için, **cihaz varsayılanı**dışında bir parola gücü seçtiğinizden emin olun.
  - **Düşük güvenlik biyometriği**
  - **En az sayısal** (varsayılan)
  - **Sayısal karmaşıklık**: `1111` veya `1234` gibi yinelenen ya da ardışık numaralara izin verilmez.
  - **En az alfabetik** 
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Parola kullanım süresi sonu (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

### <a name="encryption"></a>Şifreleme

- **Bir cihazda veri deposu şifreleme** (Android 4.0 ve üzeri veya KNOX 4.0 ve üzeri): Cihazlarınızda veri deposunu şifrelemek için **Gerektir**’i seçin. **Mobil cihazların kilidini açmak için parola iste** ayarını seçtiğinizde cihazlar şifrelenir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamaları engelle**: “Güvenlik > Bilinmeyen Kaynaklar” etkin kaynaklara sahip cihazları **engellemeyi** seçin (Android 4.0 ve Android 7.x sürümlerinde desteklenir; Android 8.0 ve üzeri sürümlerde desteklenmez). **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın. 

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

- **Şirket portalı uygulaması çalışma zamanı bütünlüğü**: Şirket Portalı uygulamasının aşağıdaki tüm gereksinimleri karşıladığını onaylamak için **Gerekli Kıl**’ı seçin:

  - Varsayılan çalışma zamanı ortamı yüklü
  - Doğru şekilde imzalanmış
  - Hata ayıklama modunda değil
  - Bilinen bir kaynaktan yüklenmiş

  **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda USB hata ayıklamasını engelle** (Android 4.2 veya üzeri): Cihazların USB hata ayıklama özelliğini kullanmalarını önlemek için **Engelle**’yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **En düşük güvenlik düzeltme eki düzeyi** (Android 6.0 ve sonrası): Bir cihazda olabilecek en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin `YYYY-MM-DD` biçiminde girilmesi gerekir.
- **Kısıtlı uygulamalar**: Kısıtlanması gereken uygulamalara ait **Uygulama adı** ve **Uygulama paket kimliği** değerlerini girin. **Ekle**’yi seçin. Kısıtlı uygulamalardan en az birinin yüklü olduğu cihaz uyumsuz olarak işaretlenir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="locations"></a>Konumlar

İlkenizde uyumluluk ayarlarının cihazın konumuna göre uygulanmasını sağlayabilirsiniz. Mevcut konumlar arasından seçim yapın. Henüz bir konumunuz yok mu? Intune'da [Konumları (ağ yalıtımı) kullanma](use-network-locations.md) başlığı altında bazı yönergeler sağlanır.

1. **Konumlar** > **Konumları seç**'i belirtin.
2. Listeden konumunuzu bulun ve **Seç**'i belirtin.
3. İlkeyi **kaydedin**.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [Android Kurumsal cihazlar için uyumluluk ilkesi ayarları](compliance-policy-create-android-for-work.md).
