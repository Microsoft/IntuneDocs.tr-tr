---
title: Microsoft Intune - Azure’daki Android cihazı uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da Android cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Parola kurallarını ayarlayın, en düşük veya en yüksek işletim sistemi sürümünü seçin, belirli uygulamaları kısıtlayın, parolaların yeniden kullanılmasını engelleyin ve çok daha fazlasını yapın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: efff117ca79e4fa9a00fd8d9a4be792e246f1a86
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810167"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz Android ayarları

Bu makalede Intune'daki Android cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları kullanabilir ve bu sayede kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumlu değil olarak işaretleyebilir, izin verilen tehdit düzeyi belirleyebilir, Google Play Koruması'nı etkinleştirebilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Android Cihaz Yöneticisi

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform**için **Android Cihaz Yöneticisi**' ni seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Kök erişim izni verilmiş cihazlar**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Block** -root (Jailbreak uygulanmış) cihazlarını uyumsuz olarak işaretle. 

- **Cihazın Cihaz Tehdit Düzeyinde veya bu düzeyin altında olmasını gerekli kıl**:  
  Bu ayarı, bağlı bir mobil tehdit savunma hizmetinden bir uyumluluk koşulu olarak risk değerlendirmesi almak için kullanın. 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez. 
  - **Güvenli** -Bu seçenek, cihazın herhangi bir tehdit sahibi olmadığı için en güvenli seçenektir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük** -cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta** -cihazdaki mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek** -Bu seçenek en az güvenlidir ve tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

### <a name="google-play-protect"></a>Google Play Koruması

- **Google Play Hizmetleri yapılandırıldı**:  
  Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır.
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.  
  - **Gerektir** -Google Play Services uygulamasının yüklü ve etkin olmasını gerektirir.  

- **Güncel güvenlik sağlayıcısı**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.  
  - **Gerektir** -güncel bir güvenlik sağlayıcısının bir cihazı bilinen güvenlik açıklarına karşı koruyabilmesini gerektir. 

- **Uygulamalarda tehdit taraması**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.  
  - **Gerektir** -Android **uygulamaları doğrula** özelliğinin etkinleştirilmesini gerektirir.  
  > [!NOTE]
  > Eski Android platformunda bu özellik bir uyumluluk ayarıdır. Intune yalnızca bu ayarın cihaz düzeyinde etkinleştirilip etkinleştirilmediğini denetleyebilir.

- **SafetyNet cihaz kanıtı**:  
  Karşılanması gereken [SafetyNET kanıtlama](https://developer.android.com/training/safetynet/attestation.html) düzeyini girin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

> [!NOTE]
> Uygulama koruma ilkelerini kullanarak Google Play Koruması ayarlarını yapılandırmak için bkz. [Android için Intune uygulama koruması ilkesi ayarları](../apps/app-protection-policy-settings-android.md#conditional-launch).

## <a name="device-properties"></a>Cihaz Özellikleri

### <a name="operating-system-version"></a>İşletim Sistemi Sürümü 

- **En düşük işletim sistemi sürümü**:  
  Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltmenin nasıl gerçekleştirileceği hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.

   *Varsayılan olarak, sürüm yapılandırılmaz*.

- **En yüksek işletim sistemi sürümü**:  
  Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. Bir kural, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar bu cihaz şirket kaynaklarına erişemez.

  *Varsayılan olarak, sürüm yapılandırılmaz*.

## <a name="system-security"></a>Sistem Güvenliği

### <a name="password"></a>Parola
<!-- - **Minimum password length**: Enter the minimum number of digits or characters that the user's password must have.   


- **Maximum minutes of inactivity before password is required**: Enter the idle time before the user must reenter their password. When you choose **Not configured** (default), this setting isn't evaluated for compliance or non-compliance.

- **Password expiration (days)**: Select the number of days before the password expires and the user must create a new password.

- **Number of previous passwords to prevent reuse**: Enter the number of recent passwords that can't be reused. Use this setting to restrict the user from creating previously used passwords.

-->

- **Mobil cihazların kilidini açmak için bir parola iste**: 
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -kullanıcıların cihazına erişebilmeleri için önce bir parola girmesi gerekir.  

- **Gerekli parola türü**:  
  Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı** -parola uyumluluğunu değerlendirmek Için, **cihaz varsayılanı**dışında bir parola gücü seçtiğinizden emin olun.
  - **Düşük güvenlik biyometriği**
  - **En az sayısal** 
  - `1111` veya `1234`gibi **sayısal karmaşık** yinelenen veya ardışık sayıların kullanımına izin verilmez.
  - **En az alfabetik** 
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**


### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**:  
  *Android 4,0 ve üzeri sürümlerde veya KNOX 4,0 ve üzeri sürümlerde desteklenir.*  
  <br>
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez. 'Yu 
  - , Cihazlarınızda veri depolamayı **ister** . **Mobil cihazların kilidini açmak için parola iste** ayarını seçtiğinizde cihazlar şifrelenir.  

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan uygulamaları engelleme**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Blok** - **Güvenlik > bilinmeyen kaynakların** etkinleştirildiği kaynakları engelleyin (Android*4,0 üzerinden Android 7. x aracılığıyla desteklenir). Android 8,0 ve üzeri sürümlerde desteklenmez.* ).  

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın. 

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

- **Şirket Portalı uygulaması çalışma zamanı bütünlüğü**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.  
  - **Gerektir** -Şirket portalı uygulamanın, aşağıdaki tüm gereksinimleri karşıladığından emin olmak *için gerektir ' i seçin:*
    - Varsayılan çalışma zamanı ortamı yüklü
    - Doğru şekilde imzalanmış
    - Hata ayıklama modunda değil
    - Bilinen bir kaynaktan yüklenmiş

- **CIHAZDA USB hata ayıklamayı engelle** *(Android 4,2 veya üzeri)* :  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Engelle** -cihazların USB hata ayıklama özelliğini kullanmasını engelleyin.  

- **En düşük güvenlik düzeltme eki düzeyi** *(Android 6,0 veya üzeri)* :  
  Bir cihazda olabilecek en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin `YYYY-MM-DD` biçiminde girilmesi gerekir.

  *Varsayılan olarak, bir tarih yapılandırılmaz*.

- **Kısıtlı uygulamalar**:  
  Kısıtlanması gereken uygulamalar için **uygulama adı** ve **uygulama paketi kimliği** ' ni girin ve ardından **Ekle**' yi seçin. Kısıtlı uygulamalardan en az birinin yüklü olduğu cihaz uyumsuz olarak işaretlenir.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [Android Kurumsal cihazlar için uyumluluk ilkesi ayarları](compliance-policy-create-android-for-work.md).
