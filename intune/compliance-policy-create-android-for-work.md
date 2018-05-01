---
title: Microsoft Intune - Azure’da Android for Work uyumluluk ilkesi oluşturma | Microsoft Docs
description: Android for Work cihazlar için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Jailbreak uygulanmış cihazlara izin vermek, kabul edilebilir tehdit düzeyi ayarlamak, Google Play’i denetlemek, en düşük ve en yüksek işletim sistemi sürümü girmek, parola gereksinimlerinizi seçmek ve uygulamaları dışarıdan yüklemeye izin vermek için ilkeler yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 74fe0897764957e84e5a13944305221cc85bd8c7
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Intune’daki Android for Work cihazlarına yönelik uyumluluk ilkesi ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android for Work için Intune cihaz uyumluluk ilkesi, bu cihazların uyumlu kabul edilmek için uymak zorunda olduğu kuralları ve ayarları belirtir. Şirket kaynaklarına erişime izin vermek veya bunu engellemek için bu ilkeleri koşullu erişimle birlikte kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz. Farklı platformlar için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir. Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

--------------------------

|**ilke ayarı**| **Android for Work** |
| --- | --- |
| **PIN veya Parola yapılandırması** |  Karantinaya Alındı |
| **Cihaz şifrelemesi** |  Karantinaya Alındı |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Karantinaya Alındı (ayar değil) |
| **e-posta profili** | Geçerli değil |
| **En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı |
| **Windows durum kanıtlama** |Geçerli değil |

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)+

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. **Platform** olarak **Android for Work**’ü seçin. **Ayarları Yapılandır**’ı seçin ve **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını girin. İşiniz bittiğinde **Tamam**’ı ve **Oluştur**’u seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="device-health"></a>Device health

- **Kök erişim izni verilmiş cihazlar**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazın Cihaz Tehdit Düzeyinde veya bunun altında olmasını gerektir**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin:
  - **Güvenli**: Bu seçenek en güvenlisidir ve cihazda hiçbir tehdit olmaması anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz, uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
- **Google Play Hizmetleri yapılandırıldı**: Google Play hizmetleri uygulamasının yüklenmiş ve etkinleştirilmiş olmasını gerektirin. Google Play hizmetleri, güvenlik güncelleştirmelerine olanak sağlar ve sertifikalı Google cihazlarında birçok güvenlik özelliği için temel düzeyde bir bağımlılıktır.
- **Güncel güvenlik sağlayıcısı**: Güncel bir güvenlik sağlayıcısının cihazları bilinen güvenlik açıklarına karşı korumasını gerektirin.
- **SafetyNet cihaz kanıtı**: Uyulması gereken [SafetyNet kanıtı](https://developer.android.com/training/safetynet/attestation.html) düzeyini ayarlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Temel bütünlük denetimi**
  - **Temel bütünlük ve sertifikalı cihaz denetimi**

#### <a name="threat-scan-on-apps"></a>Uygulamalarda tehdit taraması

İş profilleri olan cihazlarda (Android for Work), **Uygulamalarda tehdit taraması** ayarı bir yapılandırma ilkesi ayarı olarak bulunabilir. Yöneticiler, bu ayarı bir cihaz için etkinleştirebilirler.

Kuruluşunuzda Android iş profilleri kullanılıyorsa, kayıtlı cihazlarınız için **Uygulamalarda tehdit taraması**’nı etkinleştirebilirsiniz. Bir cihaz profili oluşturun ve sistem güvenlik ayarının gerekli olmasını sağlayın. Daha fazla bilgi için bkz. [Intune’da Android for Work cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **En düşük işletim sistemi sürümü**: Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükselttikten sonra şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Ve kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in.
- **En düşük parola uzunluğu**: Kullanıcı parolasında bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Gerekli parola türü**: Parolanın yalnızca sayısal karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından mı oluşması gerektiğini seçin. Aşağıdakilerden birini seçin:
  - **Cihaz Varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal**
  - **Sayısal karmaşıklık**
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.

### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir**: Android for Work cihazlarda şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

### <a name="device-security"></a>Cihaz Güvenliği

- **Bilinmeyen kaynaklardan gelen uygulamaları engelle**: Android for Work cihazlar bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığı için bu Android ayarını yapılandırmanız gerekmez.
- **Şirket Portalı uygulaması çalışma zamanı bütünlüğü**: Şirket Portalı uygulamasında varsayılan çalışma zamanı ortamının yüklü olup olmadığını, doğru şekilde oturum açılıp açılmadığını ve uygulamanın bilinen bir kaynaktan indirilip indirilmediğini denetler.
- **Cihazda USB hata ayıklamayı engelle**: İş için Android cihazlarında USB hata ayıklama zaten devre dışı olduğundan bu ayarları devre dışı bırakmanız gerekmez.
- **En düşük güvenlik düzeltme eki düzeyi**: Bir cihazda olabilecek en eski güvenlik düzeltme eki düzeyini seçin. En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarihin `YYYY-MM-DD` biçiminde girilmesi gerekir.

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

1. Yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi, sonra da **Atamalar**’ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenir.

## <a name="next-steps"></a>Sonraki adımlar
[Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme](actions-for-noncompliance.md)  
[Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)