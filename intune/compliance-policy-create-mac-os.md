---
title: Microsoft Intune - Azure’da macOS cihaz uyumluluk ilkesi oluşturma | Microsoft Docs
description: Sistem Bütünlük Koruması kullanmak, en düşük ve en yüksel işletim sistemi sürümü ayarlamak, parola gereksinimlerinizi seçmek ve veri deposunu şifrelemek amacıyla macOS cihazları için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a797c68ca43a6173a4bac70e914d3f763ce5e6d0
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Intune ile macOS cihazlara cihaz uyumluluk ilkesi ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune macOS cihaz uyumluluk ilkesi, macOS cihazlarının uyumlu olmak için uyması gereken kuralları ve ayarları tanımlar. Cihaz uyumluluk ilkelerini koşullu erişimle birlikte kullandığınızda, şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz. Her platform için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir. Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır:

---------------------------

| İlke ayarı | macOS 10.11 ve üzeri |
| --- | --- |
| **PIN veya Parola yapılandırması** | Çözümlendi |   
| **Cihaz şifrelemesi** | Çözümlendi (PIN ayarlanarak) |
| **E-posta profili** | Karantinaya Alındı |
|**En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı |

---------------------------

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. **Platform** olarak **macOS**’u seçin. **Ayarları Yapılandır**’ı seçin ve **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını girin. İşiniz bittiğinde **Tamam**’ı ve **Oluştur**’u seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir**: macOS cihazlarınızda [Sistem Bütünlüğü Koruması](https://support.apple.com/HT204899)’nın etkin olmasını **gerektir**in.

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.
- **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada bulunması gereken simge karakterleri (&, #, %, !, vb.) sayısı alt sınırını girin.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin.

    > [!IMPORTANT]
    > Bir macOS cihazda parola gerekliliği değiştirildiğinde, kullanıcı parolasını değiştirene kadar bu değişiklik gerçekleşmez. Örneğin parola uzunluğu sekiz basamakla kısıtlıyken macOS cihazın altı basamaklı bir parolası varsa, kullanıcı cihazda şifresini güncelleştirene kadar cihaz uyumlu kalır.

### <a name="encryption"></a>Şifreleme

- **Bir cihazda veri deposu şifreleme**: Cihazlarınızda veri deposunu şifrelemek için **Gerektir**’i seçin.

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

1. Yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi, sonra da **Atamalar**’ı seçin. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

> [!TIP]
> Varsayılan olarak cihazlar, her sekiz saatte bir uyumluluğu denetler. Ancak kullanıcılar, Intune Şirket Portalı uygulamasından bu işlemi zorlayabilirler.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenir.

## <a name="next-steps"></a>Sonraki adımlar
[Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme](actions-for-noncompliance.md)  
[Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)