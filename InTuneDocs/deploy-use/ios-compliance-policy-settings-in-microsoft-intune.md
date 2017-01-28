---
title: "iOS cihazları için uyumluluk ilkesi ayarı | Microsoft Docs"
description: "Bu konuda, iOS cihazları için uyumluluk ilkesinde belirleyebileceğiniz ayarlar açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: f4867d18634add8cb6ffc61a4413618b1bea5a4b


---


# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazları için uyumluluk ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altında açıklanan ilke ayarları iOS 8.0 ve üstünü çalıştıran cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birine bakın:
> [!div class="op_single_selector"]
- [Android cihazları için uyumluluk ilkesi ayarları](android-compliance-policy-settings-in-microsoft-intune.md)
- [Android for Work için uyumluluk ilkesi ayarları](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Sistem güvenliği ayarları
### <a name="password"></a>Parola
- **Mobil cihazların kilidini açmak için parola gerektir:** Kullanıcıların cihazlarına erişebilmek üzere bir parola girmelerini gerektirmek için bunu **Evet** olarak ayarlayın. Parola kullanılan iOS cihazları şifrelenir.

- **Basit parolalara izin ver:** Kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarına izin vermek için bunu **Evet** olarak ayarlayın.

-  **En düşük parola uzunluğu:** Kullanıcı parolasının içermesi gereken en düşük rakam veya karakter sayısını belirtin.

- **Gerekli parola türü:** Kullanıcıların oluşturacağı parolanın **Alfasayısal** mı, yoksa **Sayısal** mı olacağını belirtin.

- **Karakter kümesi sayısı alt sınırı:** **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa, bu ayar, parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtir. Dört karakter kümesi şunlardır:
  -   Küçük harfler
  -   Büyük harfler
  -   Simgeler
  -   Sayılar

  Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

  iOS cihazları için bu ayar, parolaya eklenmesi gereken özel karakterlerin (örneğin, **!**, **#**, **&amp;**) sayısını gösterir.

- **Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.

- **Parola kullanım süresi (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.

- **Parola geçmişini anımsa:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.

- **Önceki parolaların yeniden kullanılmasını önleme:** **Parola geçmişini anımsa** seçeneğini belirlediyseniz, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.

- **Cihaz boşta durumundan çıkarken parola iste:** Bu ayarı, **Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı** ayarıyla birlikte kullanın. **Parola istenmeden önce herhangi bir işlem yapılmadan geçecek dakika cinsinden süre** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için kullanıcıdan bir parola girmesi istenir.

### <a name="email-profile"></a>E-posta profili
- **E-posta hesabı Intune tarafından yönetilmelidir:** Bu seçenek **Evet** olarak ayarlandığında, cihazın kendisine dağıtılan e-posta profilini kullanması gerekir. Aşağıdaki durumlarda cihaz uyumsuz olarak kabul edilir:
  - E-posta profili, uyumluluk ilkesi tarafından hedeflenen kullanıcı grubu dışındaki bir kullanıcı grubuna dağıtılır.
  - Kullanıcı, cihaza dağıtılan Intune e-posta profiliyle eşleşen bir e-posta hesabını cihazda zaten ayarlamıştır. Intune, kullanıcı tarafından sağlanan profilin üzerine yazamaz ve bu nedenle yönetemez. Uyumluluğu güvence altına almak için kullanıcının mevcut e-posta ayarlarını kaldırması gerekir. Ardından, Intune yönetilen e-posta profilini yükleyebilir.

- **Intune tarafından yönetilmesi gereken e-posta profilini seçin**: **E-posta hesabı Intune tarafından yönetilmelidir** ayarı seçildiyse, Intune e-posta profilini belirtmek için **Seçin**’i işaretleyin. E-posta profili cihazda mevcut olmalıdır.

     E-posta profilleri hakkında ayrıntılı bilgi için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="device-health-settings"></a>Cihaz durumu ayarları

- **Cihaza jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalıdır:** Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumlu olmaz.

##  <a name="device-properties"></a>Cihaz özellikleri
- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumlu değil olarak bildirilir.
Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Kullanıcı cihazını yükseltmeyi seçebilir. Bundan sonra, şirket kaynaklarına erişebilir.

- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.



<!--HONumber=Jan17_HO4-->


