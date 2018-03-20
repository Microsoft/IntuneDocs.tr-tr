---
title: "Microsoft Intune’da macOS cihazı uyumluluk ilkesi oluşturma"
titleSuffix: 
description: "macOS cihazlarına Microsoft Intune cihaz uyumluluk ilkesi oluşturarak cihazın uyumlu olabilmesi için karşılaması gereken gereksinimleri belirtebilirsiniz."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7703b8ea26d6ce53b82e806a78c788d14ae05b4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>Intune ile macOS cihazlar için cihaz uyumluluk ilkesi oluşturma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

macOS için Intune cihaz uyumluluk ilkesi, macOS cihazlarının uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlar. Bu ilkeleri koşullu erişimle birlikte kullanarak şirket kaynaklarına erişime izin verebilir veya erişimi engelleyebilirsiniz; ayrıca cihaz raporları ve uyumsuzlukla ilgili önlemler alabilirsiniz. Her platform için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir.

## <a name="before-you-begin"></a>Başlamadan önce

Yeni bir cihaz uyumluluk ilkesi oluşturmadan önce Intune cihaz uyumluluk ilkesi kavramlarına göz atın.

- Cihaz uyumluluk ilkeleri hakkında daha fazla bilgi için bkz. [cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance.md).

> [!IMPORTANT]
> Her platform için cihaz uyumluluk ilkeleri oluşturmanız gerekir. Intune cihaz uyumluluk ilkeleri, platform işlevlerine bağlıdır. Bu işlevler ise MDM protokolüyle ortaya çıkan ayarlardır.

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır:


| İlke ayarı | macOS 10.11 ve üzeri |
| --- | --- |
| **PIN veya Parola yapılandırması** | Çözümlendi |   
| **Cihaz şifrelemesi** | Çözümlendi (PIN ayarlanarak) |
| **E-posta profili** | Karantinaya Alındı |
|**En düşük işletim sistemi sürümü** | Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı |  


**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="macos-compliance-policy-settings"></a>MacOS uyumluluk ilke ayarları

Intune ile yeni bir cihaz uyumluluk ilkesi oluştururken, farklı kategorilerdeki farklı ayarlar arasından seçim yapabilirsiniz:

- Cihaz Sistem Durumu

- Cihaz Özellikleri

- Sistem Güvenliği

### <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir** : Bunu **Gerektir** şeklinde ayarlayarak, macOS cihazlarınızda sistem bütünlüğü korumasının etkin olup olmadığını kontrol edin.

### <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü** - Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Kullanıcı cihazını yükseltmeyi seçebilir. Bundan sonra, şirket kaynaklarına erişebilir.

- **En yüksek işletim sistemi sürümü** - Cihaz, kuralda belirtilenin üzerinde bir işletim sistemi sürümünü kullandığında, cihazın şirket kaynaklarına erişimi engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

#### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir** - Bunu **Gerektir** şeklinde ayarlayarak, kullanıcılardan cihazlarına erişebilmeleri için bir parola girmelerini isteyin.

- **Basit parolalar** - Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmasının önüne geçin.

- **Minimum parola uzunluğu** - Parolada bulunması gereken rakam veya karakter sayısı alt sınırını belirtin.

- **Parola türü** - Kullanıcıların oluşturacağı parolanın **Alfasayısal** veya **Sayısal** parola olması gerektiğini belirtin.

- **Paroladaki alfasayısal olmayan karakter sayısı** - **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa bu ayarı kullanarak parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtin. 

    > [!NOTE]
    > Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

    > [!IMPORTANT]
    > MacOS cihazlar için bu ayar, parolaya eklenmesi gereken özel karakterlerin (örneğin, **!** , **#**, **&amp;**) sayısını gösterir.

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı** - Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi belirtin.

- **Parola kullanım süresi (gün)** - Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını (1-250 gün arasında) seçin.

- **Yeniden kullanılması engellenen eski parola sayısı** - Önceki parolalardan kaç tanesinin yeniden kullanılamayacağını belirtin.

    > [!IMPORTANT]
    > Bir macOS cihazda parola gerekliliği değiştirildiğinde, kullanıcı parolasını değiştirene kadar bu değişiklik gerçekleşmez. Örneğin parola uzunluğu sekiz basamakla kısıtlıyken macOS cihazın altı basamaklı bir parolası varsa, kullanıcı cihazda şifresini güncelleştirene kadar cihaz uyumlu kalır.

## <a name="to-create-a-device-compliance-policy"></a>Cihaz uyumluluk ilkesi oluşturmak için

1. [Azure portalı](https://portal.azure.com)’na gidin ve Intune kimlik bilgilerinizle oturum açın.

2. Başarılı bir şekilde oturum açtığınızda **Azure Panosu**’nu görebilirsiniz.

3. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

4. **Intune**’u seçin, **Intune Panosu**’nu görebilirsiniz.

5. **Cihaz uyumluluğu** ve daha sonra **Yönet** altında **İlkeler**’i seçin.

6. **İlke oluştur**’u seçin.

7. Ad ve açıklama yazın ve bu ilkenin uygulanmasını istediğiniz platformu seçin.

8. **Mac uyumluluk ilkesi** bölmesi açılır; burada **Sistem Güvenliği**, **Cihaz Durumu** ve **Cihaz Özellikleri** uyumluluk ayarı kategorilerini seçerek ayarlarınızı belirtin.

10. Ayarlarınızı seçmeyi bitirdiğinizde her bir cihaz uyumluluk ayarı kategorisinin altında **Tamam**’ı seçin.

11. **Tamam**’ı ve daha sonra **Oluştur**’u seçin.

## <a name="assign-user-groups"></a>Kullanıcı gruplarını atama

Kullanıcılara uyumluluk ilkesi atamak için, yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz uyumluluğu - İlkeleri** bölmesinde bulunabilir.

1. Kullanıcılara atamak istediğiniz cihaz uyumluluk ilkesini seçin ve sonra **Atamalar**’ı seçin. Bu işlem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölmeyi açar.

2. Azure AD güvenlik gruplarının görüntülendiği bölmeyi açmak için **Seçilen gruplar**’ı seçin.

3. Cihaz uyumluluk ilkesini Azure AD güvenlik gruplarına atamak için **Kaydet**’i seçin.

4. Cihaz uyumluluk ilkesini gruplarınıza atamayı bitirdiğinizde **Atamalar** bölmesini kapatabilirsiniz.

    > [!TIP]
    > Cihazlar, varsayılan olarak her sekiz saatte bir uyumluluk denetimi yapar ancak kullanıcılar, Intune şirket portalı uygulaması aracılığıyla bu işlemi zorlayabilir.

## <a name="next-steps"></a>Sonraki adımlar

[Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)
