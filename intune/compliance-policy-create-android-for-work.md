---
title: Microsoft Intune - Azure’da Android Kurumsal uyumluluk ilkesi oluşturma | Microsoft Docs
description: Android Kurumsal veya iş profili cihazları için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Jailbreak uygulanmış cihazlara izin vermek, kabul edilebilir tehdit düzeyi ayarlamak, Google Play’i denetlemek, en düşük ve en yüksek işletim sistemi sürümü girmek, parola gereksinimlerinizi seçmek ve uygulamaları dışarıdan yüklemeye izin vermek için ilkeler yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2965a3559817d9fa3cda4225b08b8887dcb2e76f
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392624"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Intune’daki Android Kurumsal cihazları için uyumluluk ilkesi ekleme

Intune’un kuruluşunuzun kaynaklarını korumaya yönelik kullanımında cihaz uyumluluk ilkeleri en önemli özelliklerdendir. Intune’da cihazların uyumlu olarak değerlendirilmesi için uyması gereken parola uzunluğu gibi kurallar ve ayarlar oluşturabilirsiniz. Cihaz uyumlu değilse [koşullu erişimi](conditional-access.md) kullanarak veri ve kaynaklara erişimi engelleyebilirsiniz. 

Ayrıca cihaz raporları alabilir ve uyumsuzluğa yönelik, kullanıcıya bildirim göndermek gibi önlemler alabilirsiniz. Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

Bu makale, Android Kurumsal çalıştıran cihazlar için bir uyumluluk ilkesinde kullanabileceğiniz ayarları listeler.

## <a name="non-compliance-and-conditional-access"></a>Uyumsuzluk ve koşullu erişim

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

--------------------------

|**ilke ayarı**| **Android Kurumsal profili** |
| --- | --- |
| **PIN veya Parola yapılandırması** |  Karantinaya Alındı |
| **Cihaz şifrelemesi** |  Karantinaya Alındı |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Karantinaya Alındı (ayar değil) |
| **e-posta profili** | Geçerli değil |
| **En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı |
| **Windows durum kanıtlama** |Geçerli değil |

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.

**Karantinaya alındı** = Cihazın işletim sistemi, uyumluluğu zorunlu kılmaz. Örneğin Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz. Cihaz uyumsuz olduğunda aşağıdaki işlemler yapılır:

  - Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
  - Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. **Platform** olarak **Android kurumsal**’ı seçin. 
5. **Ayarları Yapılandır**’ı seçin. **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını bu makalede açıklandığı gibi girin.

## <a name="device-health"></a>Device health

- **Köklü cihazlar**: Seçin **blok** kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek için. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak bu ayarı kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu seçenek en az güvenli olduğu gibi tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
- **Google Play Hizmetleri yapılandırıldı**: **Gerekli** Google Play uygulaması Hizmetleri yüklü ve etkin. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: **Gerekli** bir cihaz güncel güvenlik sağlayıcısı tarafından bilinen güvenlik açıklarına karşı koruyabilir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **SafetyNet cihaz kanıtlama**: Düzeyini [SafetyNet cihaz kanıtlama](https://developer.android.com/training/safetynet/attestation.html) uyulması gereken. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış** (varsayılan): Ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

#### <a name="threat-scan-on-apps"></a>Uygulamalarda tehdit taraması

Android Kurumsal cihazlardaki **Uygulamalarda tehdit taraması** ayarı, bir yapılandırma ilkesidir. Bkz. [Android için Intune cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

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

  Android iş profili cihazlarında şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamaları engelle**: Tercih **blok** cihazlarla "Güvenlik > bilinmeyen kaynaklar" etkin kaynakları (Android 4.0 – Android 7.x desteklenir; değil desteklenen Android 8.0 ve üzeri). **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın. 

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

  Android iş profili cihazları bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığından, bu ayarı yapılandırmanız gerekmez.

- **Şirket portalı uygulaması çalışma zamanı bütünlüğü**: Seçin **gerektiren** şirket Portalı'nı onaylamak için uygulama aşağıdaki tüm gereksinimleri karşılayan:

  - Varsayılan çalışma zamanı ortamı yüklü
  - Doğru şekilde imzalanmış
  - Hata ayıklama modunda değil
  - Bilinen bir kaynaktan yüklenmiş

  **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda blok USB hata ayıklamasını**: Seçin **blok** cihazların USB hata ayıklama özelliğini kullanmalarını engellemek üzere. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Android iş profili cihazlarında USB hata ayıklama zaten devre dışı olduğundan bu ayarı yapılandırmanız gerekmez.

- **En düşük güvenlik düzeltme eki düzeyi**: Cihazın sahip olabileceği en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin *YYYY-AA-GG* biçiminde girilmesi gerekir.

İşiniz bittiğinde değişikliklerinizi kaydetmek için **Tamam** > **Tamam**’ı seçin.

## <a name="actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler

**Uyumsuzluğa yönelik eylemler**'i seçin. Varsayılan eylem cihazı hemen uyumsuz olarak işaretler.

Cihazın uyumsuz olarak işaretlenme zamanlamasını değiştirebilirsiniz (örneğin, bir gün sonra olarak). Ayrıca, cihaz uyumlu olmadığında kullanıcıya e-posta gönderen ikinci bir eylem de yapılandırabilirsiniz.

[Uyumsuz cihazlar için eylem ekleme](actions-for-noncompliance.md) makalesinde, kullanıcılarınıza e-posta ile gönderilecek bir bildirim oluşturma da dahil olmak üzere daha fazla bilgi sağlanmıştır.

## <a name="scope-tags"></a>Kapsam etiketleri

Satış, Mühendislik, İK gibi belirli gruplara ilke atamanın ideal bir yolu olarak kapsam etiketlerini kullanabilirsiniz. Uyumluluk ilkelerine kapsam etiketleri ekleyebilirsiniz. Bkz. [İlke filtrelemek için kapsam etiketleri kullanma](scope-tags.md). 

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

Oluşturulan ilke, atanana kadar herhangi bir eylem gerçekleştirmez. İlkeyi atamak için: 

1. Yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi, sonra da **Atamalar**’ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için değerlendirilir.

## <a name="next-steps"></a>Sonraki adımlar
[Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme](actions-for-noncompliance.md)  
[Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)  
[Android için uyumluluk ilkesi ayarları](compliance-policy-create-android.md)
