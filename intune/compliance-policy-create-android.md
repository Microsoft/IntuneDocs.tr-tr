---
title: Microsoft Intune - Azure’da Android cihaz uyumluluk ilkesi oluşturma | Microsoft Docs
description: Android cihazlar için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Jailbreak uygulanmış cihazlara izin vermek, kabul edilebilir tehdit düzeyi ayarlamak, Google Play’i denetlemek, en düşük ve en yüksek işletim sistemi sürümü girmek, parola gereksinimlerinizi seçmek ve uygulamaları dışarıdan yüklemeye izin vermek için ilkeler yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ed2dcda510c455be1ad532228bfbcbeb898d971a
ms.sourcegitcommit: b7789fd2f34528275c13a717699cf53a289ed04e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48891038"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Intune’da Android cihazlar için cihaz uyumluluk ilkesi ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android için Intune cihaz uyumluluk ilkesi Android cihazlarının uyumlu kabul edilmek için uymak zorunda olduğu kuralları ve ayarları belirtir. Şirket kaynaklarına erişime izin vermek veya bunu engellemek için bu ilkeleri koşullu erişimle birlikte kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz. Her platform için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir. Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

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

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. **Platform** olarak **Android**’i seçin. **Ayarları Yapılandır**’ı seçin ve **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını girin. İşiniz bittiğinde **Tamam**’ı ve **Oluştur**’u seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

<!---##  Compliance policy settings--->

## <a name="device-health"></a>Device health

- **Kök erişim izni verilmiş cihazlar**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazın Cihaz Tehdit Düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin:
  - **Güvenli**: Cihazda hiçbir tehdit olmamasını gerektirdiği için bu seçenek en güvenlisidir. Herhangi bir tehdit düzeyi algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazda mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
- **Google Play Hizmetleri yapılandırıldı**: Google Play hizmetleri uygulamasının yüklenmiş ve etkinleştirilmiş olmasını gerektirin. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır.
- **Güncel güvenlik sağlayıcısı**: Güncel bir güvenlik sağlayıcısının cihazları bilinen güvenlik açıklarına karşı korumasını gerektirin.
- **Uygulamalarda tehdit taraması**: Android **Uygulamaları Doğrula** özelliğinin etkinleştirilmesini gerektirin.

  > [!NOTE]
  > Eski Android platformunda bu özellik bir uyumluluk ayarıdır. Intune yalnızca bu ayarın cihaz düzeyinde etkinleştirilip etkinleştirilmediğini denetleyebilir. Android iş profilleri olan cihazlarda bu ayar, bir yapılandırma ilkesi ayarı olarak bulunabilir. Bu, yöneticilerin ayarı cihaz için etkinleştirmesine olanak tanır.

  Kuruluşunuzda Android iş profilleri kullanılıyorsa, kayıtlı cihazlarınız için **Uygulamalarda tehdit taraması**’nı etkinleştirebilirsiniz. Bir cihaz profili oluşturun ve sistem güvenlik ayarının gerekli olmasını sağlayın. Daha fazla bilgi için bkz. [Intune’da Android iş profili cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **En düşük işletim sistemi sürümü**: Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltmenin nasıl gerçekleştirileceği hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in.
- **En düşük parola uzunluğu**: Kullanıcı parolasında bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşacağını seçin. Aşağıdakilerden birini seçin:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal**
  - **Sayısal karmaşık**: Yinelenen veya ardışık numaralara (“1111” veya “1234” gibi) izin verilmez.
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi sonu (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

### <a name="encryption"></a>Şifreleme

- **Bir cihazda veri deposu şifreleme** (Android 4.0 ve üzeri veya KNOX 4.0 ve üzeri): Cihazlarınızda veri deposunu şifrelemek için **Gerektir**’i seçin. **Mobil cihazların kilidini açmak için parola iste** ayarını seçtiğinizde cihazlar şifrelenir.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamalar engelle**: “Güvenlik > Bilinmeyen Kaynaklar” etkin kaynaklara sahip cihazları engellemeyi seçin (Android 4.0 - Android 7.x. Android 8.0 ve sonraki sürümlerde desteklenmez). Uygulamaları dışarıdan yüklemek için bilinmeyen kaynaklara izin verilmesi gerekir. Cihazlara dışarıdan Android uygulaması yüklemiyorsanız bu uyumluluk ilkesini etkinleştirmeyin.

  > [!IMPORTANT]
  > Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklardan gelen uygulamaları engelle** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorlayın.

- **Şirket Portalı uygulaması çalışma zamanı bütünlüğü**: Şirket Portalı uygulamasında varsayılan çalışma zamanı ortamının yüklü olup olmadığını, doğru şekilde oturum açılıp açılmadığını ve uygulamanın bilinen bir kaynaktan indirilip indirilmediğini denetler.
- **Cihazda USB hata ayıklamayı engelle** (Android 4.2 ve sonrası): Cihazların USB hata ayıklama özelliğini kullanmalarını engellemeyi seçin.
- **En düşük güvenlik düzeltme eki düzeyi** (Android 6.0 ve sonrası): Bir cihazda olabilecek en eski güvenlik düzeltme eki düzeyini seçin. En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarihin `YYYY-MM-DD` biçiminde girilmesi gerekir.

## <a name="locations"></a>Konumlar

İlkenizde, mevcut konumlar arasından seçim yapın. Henüz bir konumunuz yok mu? [Intune'da Konumları (ağ yalıtımı) kullanma](use-network-locations.md) başlığı altında bazı yönergeler sağlanır.

1. **Konumları seç** öğesini seçin.
2. Listeden konumunuzu bulun ve **Seç**'i kullanın.
3. İlkeyi **kaydedin**.
4. **Uyumsuzluğa yönelik eylemler**'i seçin. Varsayılan eylem cihazı hemen uyumsuz olarak işaretler. Bu eylem, en az bir konum seçtiğinizde ve cihaz seçili konumlara bağlı olmadığından uygulanır.

  Cihaz uyumsuz olarak işaretlendiğinde, zamanlamayı güncelleştirmek (örneğin, bir gün sonraya) için bu eylemi değiştirebilirsiniz. Ayrıca, cihaz artık konumlarınızla uyumlu olmadığında kullanıcıya e-posta gönderen ikinci bir eylem de yapılandırabilirsiniz.

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

1. Yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi, sonra da **Atamalar**’ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenir.

## <a name="next-steps"></a>Sonraki adımlar
[Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme](actions-for-noncompliance.md)  
[Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)
