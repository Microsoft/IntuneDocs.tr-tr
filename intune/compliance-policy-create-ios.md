---
title: Microsoft Intune - Azure'da iOS cihaz uyumluluk ilkesi oluşturma | Microsoft Docs
description: E-posta hesabı girmek, jailbreak uygulanmış cihazları denetlemek, en düşük ve en yüksek işletim sistemini denetlemek ve parola uzunluğu ile cihazda işlem yapılmayan süre de dahil olmak üzere parola kısıtlamalarını ayarlamak için iOS cihazlarında Microsoft Intune cihaz uyumluluk ilkesi ayarlayın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b05eb725adb61ae47a24ca884d0e73ffe0dd269f
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/23/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Intune'da iOS cihazları için cihaz uyumluluk ilkesi ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune iOS cihaz uyumluluk ilkesi, iOS cihazlarının uyumlu olmak için uyması gereken kuralları ve ayarları tanımlar. Cihaz uyumluluk ilkelerini koşullu erişimle birlikte kullandığınızda, şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz. Her platform için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir. Uyumluluk ilkeleri hakkında daha fazla bilgi edinmek ve uyumluluk ilkesi oluşturmadan önce karşılamanız gereken önkoşulları öğrenmek için, [Cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md) konusuna bakın.

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

| **İlke ayarı** | **iOS 8.0 ve üzeri** |
| --- | --- |
| **PIN veya Parola yapılandırması** | Çözümlendi |
| **Cihaz şifrelemesi** | Çözümlendi (PIN ayarlanarak) |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Karantinaya Alındı (ayar değil)
| **E-posta profili** | Karantinaya Alındı |
|**En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı |
| **Windows durum kanıtlama** | Geçerli değil |

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal’da uyumluluk ilkesi oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz uyumluluğu** > **İlkeler** > **İlke Oluştur**'u seçin.
4. Ad ile açıklama girin ve bu ilkenin uygulanmasını istediğiniz platformu seçin.
5. **E-posta**, **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını girmek için **Ayarlar**'ı seçin. İşiniz bittiğinde **Tamam**’ı seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

Kullanıcılara uyumluluk ilkesi atamak için, yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz uyumluluğu - İlkeler** bölmesinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz bir bölme açılır.
2. Azure AD güvenlik gruplarının görüntülendiği sayfayı açmak için **Seçilen gruplar**’ı seçin.  **Kaydet**  öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

İlkeyi kullanıcılara uyguladınız.  İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenir.

<!---## Compliance policy settings--->

## <a name="email"></a>E-posta

- **E-posta hesabı Intune tarafından yönetilmelidir:** Bu seçenek **Evet** olarak ayarlandığında, cihazın kendisine dağıtılan e-posta profilini kullanması gerekir. Aşağıdaki durumlarda cihaz uyumsuz olarak kabul edilir:
  - E-posta profili, uyumluluk ilkesi tarafından hedeflenen kullanıcı grubu dışındaki bir kullanıcı grubuna dağıtılır.
  - Kullanıcı, cihaza dağıtılan Intune e-posta profiliyle eşleşen bir e-posta hesabını cihazda zaten ayarlamıştır. Intune, kullanıcı tarafından sağlanan profilin üzerine yazamaz ve bu nedenle yönetemez. Uyumluluğu güvence altına almak için kullanıcının mevcut e-posta ayarlarını kaldırması gerekir. Ardından, Intune yönetilen e-posta profilini yükleyebilir.
- **Intune tarafından yönetilmesi gereken e-posta profilini seçin**: **E-posta hesabı Intune tarafından yönetilmelidir** ayarı seçildiyse, Intune e-posta profilini belirtmek için **Seçin**’i işaretleyin. E-posta profili cihazda mevcut olmalıdır.

E-posta profili hakkında ayrıntılı bilgi için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health"></a>Device health

- **Jailbreak uygulanmış cihazlar**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumlu kabul edilmez.
- **Cihazın Cihaz Tehdit Düzeyinde veya bu düzeyin altında olmasını gerekli kıl**: Cihazları uyumsuz olarak işaretlemek için maksimum tehdit düzeyini seçin. Örneğin tehdit düzeyini **Orta** olarak ayarlarsanız, orta, düşük veya güvenli düzeydeki cihazlar uyumlu olur. Tehdit düzeyi yüksek olan cihazları uyumsuzdur.

## <a name="device-properties"></a>Cihaz özellikleri

- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Kullanıcı cihazını yükseltmeyi seçebilir. Bundan sonra, şirket kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>Parola

> [!NOTE]
> iOS cihazına uyumluluk veya yapılandırma ilkesi uygulandıktan sonra her 15 dakikada bir kullanıcılardan bir geçiş kodu ayarlamaları istenir. Geçiş kodu ayarlanana kadar kullanıcılara sürekli bu istem gönderilir.

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek üzere bir parola girmelerini gerektirmek için **Evet** olarak ayarlayın. Parola kullanılan iOS cihazları şifrelenir.
- **Basit parolalar**: Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmasına izin vermek için **Evet** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Gerekli parola türü**: Kullanıcıların oluşturacağı parolanın **Alfasayısal** mı, yoksa **Sayısal** mı olacağını girin.
- **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada bulunması gereken simge karakterleri (&, #, %, !, vb.) sayısı alt sınırını girin.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün):** Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
