---
title: Microsoft Intune - Azure’da Android Kurumsal uyumluluk ilkesi oluşturma | Microsoft Docs
description: Android Kurumsal veya iş profili cihazları için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Jailbreak uygulanmış cihazlara izin vermek, kabul edilebilir tehdit düzeyi ayarlamak, Google Play’i denetlemek, en düşük ve en yüksek işletim sistemi sürümü girmek, parola gereksinimlerinizi seçmek ve uygulamaları dışarıdan yüklemeye izin vermek için ilkeler yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff1f4f6a728fc041241371a413ce9d2dfdf89605
ms.sourcegitcommit: 5c2a70180cb69049c73c9e55d36a51e9d6619049
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2018
ms.locfileid: "50236467"
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

- **Kök erişim izni verilmiş cihazlar**: Kök erişim izni verilmiş (jailbreak uygulanmış) cihazları uyumsuz olarak işaretlemek için **Engelle**’yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın Cihaz Tehdit Düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda hiçbir tehdit olmaması gerektiği anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz, uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
- **Google Play Hizmetleri yapılandırıldı**: Google Play hizmetleri uygulamasının yüklenmiş ve etkinleştirilmiş olmasını **gerektirir**. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: Güncel bir güvenlik sağlayıcısının cihazları bilinen güvenlik açıklarına karşı korumasını **gerektirir**. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Ayar, uyumluluk veya uyumsuzluk açısından değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

#### <a name="threat-scan-on-apps"></a>Uygulamalarda tehdit taraması

Android Kurumsal cihazlardaki **Uygulamalarda tehdit taraması** ayarı, bir yapılandırma ilkesidir. Bkz. [Android için Intune cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Cihaz özellikleri ayarları

- **En düşük işletim sistemi sürümü**: Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükselttikten sonra şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Ve kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **En az parola uzunluğu**: Kullanıcı parolasında bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Seçenekleriniz şunlardır:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal** (varsayılan)
  - **Sayısal karmaşıklık**
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Parola kullanım süresi (gün)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposu şifreleme**: Cihazlarınızdaki veri deposunu şifrelemek için **Gerekli Kıl**’ı seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. 

  Android iş profili cihazlarında şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamaları engelle**: “Güvenlik > Bilinmeyen Kaynaklar” etkin kaynaklara sahip cihazları **engellemeyi** seçin (Android 4.0 ve Android 7.x sürümlerinde desteklenir; Android 8.0 ve üzeri sürümlerde desteklenmez). **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmek için bu özelliği **Engelle** olarak ayarlayın. 

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorunlu kılın.

  Android iş profili cihazları bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığından, bu ayarı yapılandırmanız gerekmez.

- **Şirket portalı uygulaması çalışma zamanı bütünlüğü**: Şirket Portalı uygulamasının aşağıdaki tüm gereksinimleri karşıladığını onaylamak için **Gerekli Kıl**’ı seçin:

  - Varsayılan çalışma zamanı ortamı yüklü
  - Doğru şekilde imzalanmış
  - Hata ayıklama modunda değil
  - Bilinen bir kaynaktan yüklenmiş

  **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda USB hata ayıklamasını engelle**: Cihazların USB hata ayıklama özelliğini kullanmasını önlemek için **Engelle**’yi seçin. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  Android iş profili cihazlarında USB hata ayıklama zaten devre dışı olduğundan bu ayarı yapılandırmanız gerekmez.

- **En düşük güvenlik düzeltme eki düzeyi**: Bir cihazda olabilecek en eski güvenlik düzeltme eki düzeyini seçin. Bu yama düzeyinin altındaki cihazlar uyumsuz kabul edilir. Tarihin *YYYY-AA-GG* biçiminde girilmesi gerekir.

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