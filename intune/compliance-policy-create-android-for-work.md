---
title: "Android for Work uyumluluk ilkesi oluşturma"
titleSuffix: Microsoft Intune
description: "Android for Work cihazları için, cihazın uyumlu olabilmek için karşılamak zorunda olduğu gereksinimleri belirtebileceğiniz bir Intune cihaz uyumluluk ilkesi oluşturun."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ca31d4c83ccc6b786933080b96f66953cf1a108
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Intune’daki Android for Work cihazlarına yönelik uyumluluk ilkesi oluşturma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android for Work için Intune cihaz uyumluluk ilkesi Android for Work cihazlarının uyumlu kabul edilmek için uymak zorunda olduğu kuralları ve ayarları belirtir. Bu ilkeleri koşullu erişimle birlikte kullanarak şirket kaynaklarına erişime izin verebilir veya erişimi engelleyebilirsiniz; ayrıca cihaz raporları ve uyumsuzlukla ilgili önlemler alabilirsiniz. Her platform için cihaz uyumluluk ilkelerini Intune Azure portalında oluşturursunuz. Uyumluluk ilkeleri hakkında daha fazla bilgi edinmek ve uyumluluk ilkesi oluşturmadan önce ilgilenmeniz gereken önkoşulları öğrenmek için, [Cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md) konusuna bakın.

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

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal’da uyumluluk ilkesi oluşturma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
1. **Intune** bölmesinde **Cihaz uyumluluğu**’nu seçin. **Yönet**'in altında **İlkeler**'i ve **İlke oluştur**'u seçin.
2. Ad ve açıklama yazın, bu ilkenin uygulanmasını istediğiniz platformu seçin.
3. Burada **Sistem Güvenliği**, **Cihaz Durumu** ve **Cihaz Özellikleri** ayarlarını belirtmek için **Ayarları Yapılandırma**'yı seçin. İşiniz bittiğinde **Tamam**’ı seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

Kullanıcılara uyumluluk ilkesi atamak için, yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz uyumluluğu - İlkeler** bölmesinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Bu işlem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölmeyi açar.
2. Azure AD güvenlik gruplarının görüntülendiği sayfayı açmak için **Seçilen gruplar**’ı seçin.  **Kaydet** seçildiğinde, ilke kullanıcılara dağıtılır.

İlkeyi kullanıcılara uyguladınız.  İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenecek.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola iste:** Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini istemek için bunu **Evet** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolanın içermesi gereken rakam veya karakter sayısı alt sınırını belirtin.
- **Parola kalitesi**: Bu ayar, belirttiğiniz parola gereksinimlerinin cihazda yapılandırılıp yapılandırılmadığını algılar. Android cihazlarda kullanıcıların belirli parola gereksinimleri yapılandırmasını gerekli hale getirmek için bu ayarı etkinleştirin. Aşağıdakilerden birini seçin:
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **En az alfabetik**
  - **En az alfasayısal**
  - **Simgelerle alfasayısal**
- **Parola istenmeden önceki bekleme süresi (dakika)**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtir.
- **Parola kullanım süresi (gün)**: Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Parola geçmişini anımsa:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.
- **Önceki parolaların yeniden kullanılmasını önle:** **Parola geçmişini anımsa** seçeneği belirlenirse, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.
- **Cihaz boşta durumundan çıkarken parola gerektir**: Bu ayar, **Parola istenmeden önceki bekleme süresi (dakika)** ayarıyla birlikte kullanılmalıdır. **Parola gerektirmeden önce işlem yapılmadan geçen süre (dakika)** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için son kullanıcılardan bir parola girmeleri istenir.


### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir**: Android for Work cihazlarda şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.


## <a name="device-health-and-security-settings"></a>Cihaz sistem durumu ve güvenlik ayarları

- **Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalı**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazların bilinmeyen kaynaklardan uygulama yüklemeyi önlemesini gerektir**: Android for Work cihazlar bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığı için bu Android ayarını yapılandırmanız gerekmez.
- **USB hata ayıklamanın devre dışı olmasını gerektir**: İş için Android cihazlarında USB hata ayıklama zaten devre dışı olduğundan bu ayarları devre dışı bırakmanız gerekmez.
- **En düşük Android güvenlik düzeltme eki düzeyi**: En düşük Android düzeltme eki düzeyini belirtmek için bu ayarı kullanın. En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarih GG-AA-YYYY biçiminde belirtilmelidir.
- **Cihaz tehdit korumasının etkinleştirilmesini iste**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin. Bu düzey aşağıdakilerden biri olabilir:
  - **Hiçbiri (güvenli)**: Bu, en güvenli ayardır. Bu, cihazda herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu en az güvenli seçenektir. Temel olarak tüm tehdit düzeylerine izin verir ve yalnızca raporlama amacıyla kullandığınızda yararlı olabilir.

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.
- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
