---
title: "iOS için uyumluluk ilkesi oluşturma"
titleSuffix: Azure portal
description: "iOS cihazları için uyumluluk ilkesi oluşturmayı öğrenin.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b0fdb06b072c325d30b3e5ee72f1982c5f61849
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a>Intune'da iOS cihazları için cihaz uyumluluk ilkesi oluşturma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Uyumluluk ilkeleri her platform için oluşturulur.  Uyumluluk ilkesini Azure Portal’da oluşturabilirsiniz. Uyumluluk ilkesinin ne olduğu hakkında daha fazla bilgi edinmek için, [uyumluluk ilkesi nedir](device-compliance.md) konusuna bakın. Uyumluluk ilkesi oluşturmadan önce ilgilenmeniz gereken önkoşullar hakkında bilgi edinmek için, [Cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md) konusuna bakın.

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

-------------------------------


| **İlke ayarı** | **iOS 8.0 ve üzeri** |
| --- | --- |
| **PIN veya Parola yapılandırması** | Çözümlendi |   
| **Cihaz şifrelemesi** | Çözümlendi (PIN ayarlanarak) |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Karantinaya Alındı (ayar değil)
| **E-posta profili** | Karantinaya Alındı |
|**En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı |  
| **Windows durum kanıtlama** | Uygulanamaz |  
----------------------------


**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihazlar uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Azure Portal’da uyumluluk ilkesi oluşturma

1. **Intune** dikey penceresinde **Cihaz uyumluluğunu ayarla**’yı seçin. **Yönet**’in altında **Tüm cihaz uyumluluk ilkeleri**’ni ve sonra da **Oluştur**’u seçin.
2. Ad ve açıklama yazın, bu ilkenin uygulanmasını istediğiniz platformu seçin.
3. Burada **Güvenlik**, **Cihaz durumu** ve **Cihaz özelliği** ayarlarını belirtmek için **Uyumluluk gereksinimleri**’ni seçin. Bitirdiğinizde, **Tamam**’ı seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

Kullanıcılara uyumluluk ilkesi atamak için, yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Uyumluluk – ilkeler** dikey penceresinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Bu işlem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz dikey pencereyi açar.
2. Azure AD güvenlik gruplarının görüntülendiği dikey pencereyi açmak için **Grupları seçin** öğesini seçin.  **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

İlkeyi kullanıcılara uyguladınız.  İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenecek.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek üzere bir parola girmelerini gerektirmek için bunu **Evet** olarak ayarlayın. Parola kullanılan iOS cihazları şifrelenir.
- **Basit parolalara izin ver**: Kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarına izin vermek için bunu **Evet** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını belirtin.
- **Gerekli parola türü**: Kullanıcıların oluşturacağı parolanın **Alfasayısal** mı, yoksa **Sayısal** mı olacağını belirtin.
- **Karakter kümesi sayısı alt sınırı**: **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa, bu ayar, parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtir. Dört karakter kümesi şunlardır:
  - Küçük harfler
  - Büyük harfler
  - Simgeler
  - Sayılar

Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

iOS cihazları için bu ayar, parolaya eklenmesi gereken özel karakterlerin (örneğin, **!** , **#**, **&amp;**) sayısını gösterir.

- **Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.
- **Parola kullanım süresi (gün)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Parola geçmişini anımsa**: Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını engelle** ile birlikte kullanın.
- **Önceki parolaların yeniden kullanılmasını engelle**: **Parola geçmişini anımsa** seçeneğini belirttiyseniz, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.
- **Cihaz boşta durumundan çıkarken parola iste**: Bu ayarı, **Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı** ayarıyla birlikte kullanın. **Parola istenmeden önce herhangi bir işlem yapılmadan geçecek dakika cinsinden süre** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için kullanıcıdan bir parola girmesi istenir.

### <a name="email-profile"></a>E-posta profili

- **E-posta hesabı Intune tarafından yönetilmelidir**: Bu seçenek **Evet** olarak ayarlandığında, cihazın kendisine dağıtılan e-posta profilini kullanması gerekir. Aşağıdaki durumlarda cihaz uyumsuz olarak kabul edilir:
  - E-posta profili, uyumluluk ilkesi tarafından hedeflenen kullanıcı grubu dışındaki bir kullanıcı grubuna dağıtılır.
  - Kullanıcı, cihaza dağıtılan Intune e-posta profiliyle eşleşen bir e-posta hesabını cihazda zaten ayarlamıştır. Intune, kullanıcı tarafından sağlanan profilin üzerine yazamaz ve bu nedenle yönetemez. Uyumluluğu güvence altına almak için kullanıcının mevcut e-posta ayarlarını kaldırması gerekir. Ardından, Intune yönetilen e-posta profilini yükleyebilir.
- **Intune tarafından yönetilmesi gereken e-posta profilini seçin**: **E-posta hesabı Intune tarafından yönetilmelidir** ayarı seçildiyse, Intune e-posta profilini belirtmek için **Seç** öğesini seçin. E-posta profili cihazda mevcut olmalıdır.

E-posta profili hakkında ayrıntılı bilgi için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health-settings"></a>Cihaz durumu ayarları

- **Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalıdır**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumlu olmaz.

## <a name="device-properties"></a>Cihaz özellikleri

- **Gerekli en düşük işletim sistemi**: Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Kullanıcı cihazını yükseltmeyi seçebilir. Bundan sonra, şirket kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
