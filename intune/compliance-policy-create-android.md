---
title: Microsoft Intune - Azure’da Android cihaz uyumluluk ilkesi oluşturma | Microsoft Docs
description: Android cihazlar için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Jailbreak uygulanmış cihazlara izin vermek, kabul edilebilir tehdit düzeyi ayarlamak, Google Play’i denetlemek, en düşük ve en yüksek işletim sistemi sürümü girmek, parola gereksinimlerinizi seçmek ve uygulamaları dışarıdan yüklemeye izin vermek için ilkeler yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fc78419f6a8b452f603cdeca24a5d9739dfc542
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842907"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Intune’da Android cihazlar için cihaz uyumluluk ilkesi ekleme

Android için Intune cihaz uyumluluk ilkesi Android cihazlarının uyumlu kabul edilmek için uymak zorunda olduğu kuralları ve ayarları belirtir. Kuruluş kaynaklarına erişime izin vermek veya erişimi engellemek için bu ilkeleri [koşullu erişim](conditional-access.md) ile birlikte kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz. 

Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

Bu konu, Android cihazlar için bir uyumluluk ilkesinde kullanabileceğiniz ayarları listeler.

## <a name="non-compliance-and-conditional-access"></a>Uyumsuzluk ve koşullu erişim

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

--------------------

|**İlke ayarı**| **Android 4.0 ve üzeri, Samsung KNOX Standard 4.0 ve üzeri** |
| --- | ----|
| **PIN veya Parola yapılandırması** |  Karantinaya Alındı |
| **Cihaz şifrelemesi** | Karantinaya Alındı |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Karantinaya Alındı (ayar değil) |
| **e-posta profili** | Geçerli değil |
| **En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** |   Karantinaya Alındı |
| **Windows durum kanıtlama** | Geçerli değil |

--------------------------

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.

**Karantinaya alındı** = Cihazın işletim sistemi, uyumluluğu zorunlu kılmaz. Örneğin Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz. Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

  - Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
  - Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. **Platform** olarak **Android**’i seçin. 
5. **Ayarları Yapılandır**’ı seçin. **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını bu makalede açıklandığı gibi girin.

## <a name="device-health"></a>Device health

- **Köklü cihazlar**: Seçin **blok** kök erişim izni verilmiş (jailbreak uygulanmış) cihazlar uyumlu olarak işaretlemek için. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Cihazın cihaz tehdit düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak bu ayarı kullanın. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu ayarı kullanmak için izin verilen tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en çok, güvenli, cihazda hiçbir tehdit olmaması gibi. Herhangi bir tehdit düzeyi algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu seçenek en az güvenli seçenektir ve tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
- **Google Play Hizmetleri yapılandırıldı**: **Gerekli** Google Play uygulaması Hizmetleri yüklü ve etkin. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Güncel güvenlik sağlayıcısı**: **Gerekli** bir cihaz güncel güvenlik sağlayıcısı tarafından bilinen güvenlik açıklarına karşı koruyabilir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.
- **Uygulamalarda tehdit taraması**: **Gerekli** , Android **uygulamaları doğrula** özelliği etkinleştirilir. **Yapılandırılmadı** (varsayılan) seçeneğini belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  > [!NOTE]
  > Eski Android platformunda bu özellik bir uyumluluk ayarıdır. Intune yalnızca bu ayarın cihaz düzeyinde etkinleştirilip etkinleştirilmediğini denetleyebilir.

- **SafetyNet cihaz kanıtlama**: Düzeyini [SafetyNet cihaz kanıtlama](https://developer.android.com/training/safetynet/attestation.html) uyulması gereken. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış** (varsayılan): Ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

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

İşiniz bittiğinde değişikliklerinizi kaydetmek için **Tamam** > **Tamam**’ı seçin.

## <a name="locations"></a>Konumlar

İlkenizde, mevcut konumlar arasından seçim yapın. Henüz bir konumunuz yok mu? [Intune'da Konumları (ağ yalıtımı) kullanma](use-network-locations.md) başlığı altında bazı yönergeler sağlanır.

1. **Konumlar**’ı seçin.
2. Listeden konumunuzu bulun ve **Seç**'i kullanın.
3. İlkeyi **kaydedin**.

## <a name="actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler

**Uyumsuzluğa yönelik eylemler**'i seçin. Varsayılan eylem cihazı hemen uyumsuz olarak işaretler.

Cihazın uyumsuz olarak işaretlenme zamanlamasını değiştirebilirsiniz (örneğin, bir gün sonra olarak). Ayrıca, cihaz uyumlu olmadığında kullanıcıya e-posta gönderen ikinci bir eylem de yapılandırabilirsiniz.

[Uyumsuz cihazlar için eylem ekleme](actions-for-noncompliance.md) makalesinde, kullanıcılarınıza e-posta ile gönderilecek bir bildirim oluşturma da dahil olmak üzere daha fazla bilgi sağlanmıştır.

Örneğin Konumlar özelliğini kullanıyor ve uyumluluk ilkesinde bir konum ekliyorsunuz. En az bir konum seçtiğinizde uyumsuzluk için varsayılan eylem uygulanır. Cihaz, seçili konumlara bağlı değilse hemen uyumsuz olarak değerlendirilir. Kullanıcılarınıza bir gün gibi bir yetkisiz kullanım süresi tanıyabilirsiniz.

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
[Android Kurumsal için uyumluluk ilkesi ayarları](compliance-policy-create-android-for-work.md)
