---
title: "Microsoft Intune’da Android cihaz uyumluluk ilkesi oluşturma"
titleSuffix: 
description: "Android cihazlarına Microsoft Intune cihaz uyumluluk ilkesi oluşturarak cihazın uyumlu olabilmesi için karşılaması gereken gereksinimleri belirtebilirsiniz."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2539ff1703809f5f89183a9d0cfd448f2e57fd64
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Intune'da Android cihazları için cihaz uyumluluk ilkesi oluşturma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android için Intune cihaz uyumluluk ilkesi Android cihazlarının uyumlu kabul edilmek için uymak zorunda olduğu kuralları ve ayarları belirtir. Bu ilkeleri koşullu erişimle birlikte kullanarak şirket kaynaklarına erişime izin verebilir veya erişimi engelleyebilirsiniz; ayrıca cihaz raporları ve uyumsuzlukla ilgili önlemler alabilirsiniz. Her platform için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir. Uyumluluk ilkeleri hakkında daha fazla bilgi edinmek ve uyumluluk ilkesi oluşturmadan önce ilgilenmeniz gereken önkoşulları öğrenmek için, [Cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md) konusuna bakın.

## <a name="to-create-a-device-compliance-policy"></a>Cihaz uyumluluk ilkesi oluşturmak için

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
1. **Intune** bölmesinde **Cihaz uyumluluğu**’nu seçin. **Yönet**’in altında, **İlkeler**'i ve **İlke oluştur**'u seçin.
3. Burada **Sistem Güvenliği**, **Cihaz Sistem Durumu** ve **Cihaz Özellikleri** ayarlarını belirtmek için **Ayarları Yapılandırma**’yı seçin. İşiniz bittiğinde **Tamam**’ı seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

## <a name="to-assign-user-groups"></a>Kullanıcı gruplarını atamak için

Kullanıcılara uyumluluk ilkesi atamak için, yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz uyumluluğu - İlkeler** bölmesinde bulunabilir.

1. İlkeyi, sonra da **Atamalar**’ı seçin. Bu işlem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölmeyi açar.
2. Azure AD güvenlik gruplarının görüntülendiği bölmeyi açmak için **Seçilen gruplar**’ı seçin. Burada Azure Active Directory’deki güvenlik gruplarını bulabilirsiniz.  Bu ilkenin geçerli olmasını istediğiniz kullanıcı gruplarını seçin ve sonra da ilkeyi kullanıcılara dağıtmak için **Kaydet**'i seçin.

İlkeyi kullanıcılara uyguladınız.  İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenecek.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Cihaz sistem durumu ve güvenlik ayarları

- **Cihaza jailbreak uygulanmamış veya kök erişim izni verilmemiş olmaması gerekir**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazların bilinmeyen kaynaklardan uygulama yüklemeyi önlemesini iste (Android 4.0 veya üzeri)** Üzerinde **Güvenlik**  >  **Bilinmeyen kaynaklar** etkinleştirilmiş cihazları engellemek için bu ayarı etkinleştirin ve **Evet** olarak işaretleyin.

### <a name="important"></a>Önemli

Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklar** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorlayın.

- **USB hata ayıklamanın devre dışı bırakılmasını iste (Android 4.2 veya üzeri)**: Bu ayar, cihazdaki USB hata ayıklama seçeneğinin etkin olup olmadığının algılanması gerektiğini belirtir.
- **Cihazların güvenlik tehditleri için taramayı etkinleştirmesini isteyin (Android 4.2-4.4)**: Bu ayar, **Uygulamaları doğrula** özelliğinin cihazda etkinleştirilmesinin gerektiğini belirtir.
- **En düşük Android güvenlik düzeltme eki düzeyi (Android 6.0 veya sonrası)**: En düşük Android düzeltme eki düzeyini belirtmek için bu ayarı kullanın. En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarih GG-AA-YYYY biçiminde belirtilmelidir.
- **Cihaz tehdit korumasının etkinleştirilmesini iste**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin. Bu düzey aşağıdakilerden biri olabilir:
  - **Hiçbiri (güvenli)**: Bu en güvenli ayardır. Bu, cihazda herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz, uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Yüksek**: Bu en az güvenli seçenektir. Temelde bu, tüm tehdit düzeylerine izin verir. Bu seçenek, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola iste:** Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini istemek için bunu **Evet** olarak ayarlayın.
- **En düşük parola uzunluğu**: Kullanıcı parolasının içermesi gereken en az rakam veya karakter sayısını belirtin.
- **Parola kalitesi:** Bu ayar, belirttiğiniz parola gereksinimlerinin cihazda ayarlanıp ayarlanmadığını algılar. Android cihazlarda kullanıcıların belirli parola gereksinimlerini karşılamasını gerekli hale getirmek için bu ayarı etkinleştirin. Aşağıdakilerden birini seçin:
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **En az alfabetik**
  - **En az alfasayısal**
  - **Simgelerle alfasayısal**
- **Parola istenmeden önce herhangi bir işlem yapılmadan geçecek dakika cinsinden süre**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.
- **Parola kullanım süresi (gün):** Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Parola geçmişini anımsama:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.
- **Önceki parolaların yeniden kullanılmasını önleme:** **Parola geçmişini anımsa** seçeneğini belirlediyseniz, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.
- **Cihaz boşta durumundan çıkarken parola iste:** Bu ayarı, **Parola istenmeden önce herhangi bir işlem yapılmadan geçecek dakika cinsinden süre** ayarıyla birlikte kullanın. **Parola istenmeden önce herhangi bir işlem yapılmadan geçecek dakika cinsinden süre** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için kullanıcıdan bir parola girmesi istenir.

### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme iste:** Cihazın kaynaklara bağlanma amacıyla şifrelenmesini istemek için bunu **Evet** olarak ayarlayın. **Mobil cihazların kilidini açmak için parola iste** ayarını seçtiğinizde cihazlar şifrelenir.

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.
- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kurallarda işletim sistemine izin veren bir değişiklik oluncaya kadar, bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

## <a name="how-noncompliant-settings-work-with-conditional-access-policies"></a>Uyumlu olmayan ayarlar, koşullu erişim ilkeleriyle birlikte nasıl çalışır?

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

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
