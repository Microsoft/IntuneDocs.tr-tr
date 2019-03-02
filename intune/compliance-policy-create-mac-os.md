---
title: Microsoft Intune - Azure’da macOS cihaz uyumluluk ilkesi oluşturma | Microsoft Docs
description: Sistem Bütünlük Koruması kullanmak, en düşük ve en yüksel işletim sistemi sürümü ayarlamak, parola gereksinimlerinizi seçmek ve veri deposunu şifrelemek amacıyla macOS cihazları için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b12c7c650201e521f03b4b9816df2163b6e56d9
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236645"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Intune ile macOS cihazlara cihaz uyumluluk ilkesi ekleme

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
4. **Platform** olarak **macOS**’u seçin. 
5. Seçin **ayarlarını yapılandırma**girin **cihaz sistem durumu**, **cihaz özelliklerini**, ve **sistem güvenliği** ayarları açıklanmıştır Bu makalede. İşiniz bittiğinde **Tamam**’ı ve **Oluştur**’u seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir**: **Gerekli** için macOS cihazlarınızda [sistem bütünlüğü koruması](https://support.apple.com/HT204899) etkin.

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Bir cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, şirket kaynaklarına erişimi engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.
- **En düşük işletim sistemi derleme sürümü**: Apple güvenlik güncelleştirmeleri yayımlarken, yapı numarası genellikle güncelleştirilir, işletim sistemi sürümü. Cihazda bir izin verilen en düşük yapı numarası girmek için bu özelliği kullanın.
- **En yüksek işletim sistemi derleme sürümü**: Apple güvenlik güncelleştirmeleri yayımlarken, yapı numarası genellikle güncelleştirilir, işletim sistemi sürümü. Cihazda bir izin verilen en fazla yapı numarası girmek için bu özelliği kullanın.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin.
- **Basit parolalar**: Kümesine **blok** kullanıcılar gibi basit parolalar oluşturamıyor **1234** veya **1111**. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: En düşük rakam veya karakter bulunması gereken sayısını girin.
- **Parola türü**: Parola yalnızca olması gerekip gerekmediğini seçin **sayısal** karakter veya sayı ve diğer karakterlerin bir karışımı yoksa (**alfasayısal**).
- **Paroladaki alfasayısal olmayan karakter sayısı**: En az özel karakter sayısını girin (&, #, %,!, vb.) bulunması gereken parola.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir tane oluşturmanız gerekir önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamaz önceden kullanılmış parola sayısını girin.

    > [!IMPORTANT]
    > Bir macOS cihazda parola gerekliliği değiştirildiğinde, kullanıcı parolasını değiştirene kadar bu değişiklik gerçekleşmez. Örneğin parola uzunluğu sekiz basamakla kısıtlıyken macOS cihazın altı basamaklı bir parolası varsa, kullanıcı cihazda şifresini güncelleştirene kadar cihaz uyumlu kalır.

### <a name="encryption"></a>Şifreleme

- **Bir cihazdaki veri depolamasının şifrelenmesi**: Seçin **gerektiren** cihazlarınızda veri deposunu şifrelemek için.

### <a name="device-security"></a>Cihaz Güvenliği
Güvenlik Duvarı, cihazları yetkisiz erişimine karşı korur. Güvenlik Duvarı'nı kullanarak uygulama başına bağlantıları denetleyebilirsiniz. 

- **Güvenlik Duvarı**: **Etkinleştirme** cihazları yetkisiz erişime karşı korunmasına yardımcı olmak için. Bu özelliği etkinleştirdiğinizde gelen İnternet bağlantılarını işleyebilir ve gizli modu kullanabilirsiniz. **Yapılandırılmamış** (varsayılan), güvenlik duvarını devre dışı bırakır ve ağ trafiğine izin verilir (engellenmedi).
- **Gelen bağlantıları**: **Blok** DHCP, Bonjour ve IPSec gibi temel internet Hizmetleri için gerekli olanlar dışındaki tüm gelen ağ bağlantıları. Bu ayar, ekran paylaşımı, uzaktan erişim, iTunes müzik paylaşımı gibi tüm paylaşım hizmetlerini engeller. **Yapılandırılmamış** (varsayılan) gelen bağlantılara ve paylaşım hizmetlerine izin verir. 
- **Gizli mod**: **Etkinleştirme** cihaz kötü amaçlı kullanıcılar yapılan istekleri, yoklama isteklerine yanıt vermesini önlemek için gizli modu. Etkinleştirildiğinde, cihaz yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. **Yapılandırılmamış** (varsayılan) gizli modu devre dışı bırakır.

### <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

**Bu konumlardan indirilen uygulamalara izin ver**: Desteklenen uygulamaların farklı konumlardan cihazlarınızda yüklenmesi için izin verir. Konum seçenekleriniz:

- **Yapılandırılmamış**: Varsayılan. Ağ geçidi seçeneği, uyumluluk veya uyumsuzluk herhangi bir etkisi yoktur. 
- **Mac App Store**: Yalnızca Mac app store uygulamaları yükleyin. Üçüncü taraf veya tanımlı geliştirici uygulamaları yüklenemez. Bir kullanıcı, Gatekeeper’ı Mac App Store dışından uygulama yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Mac App Store ve tanımlanan geliştiriciler**: İçin Mac app store ve tanımlanan geliştiriciler uygulamalarını yükleyin. macOS, geliştiricilerin kimliğini denetler ve uygulama bütünlüğünü doğrulamak için başka denetimler de gerçekleştirir. Bir kullanıcı, Gatekeeper’ı bu seçenekler haricindeki uygulamaları yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Her yerden**: Uygulamalar her yerden ve herhangi bir geliştirici tarafından gelen yüklenebilir. Bu, güvenliği en düşük olan seçenektir.

Apple belgelerinde daha fazla ayrıntı için bkz. [macOS üzerinde Gatekeeper](https://support.apple.com/HT202491).

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
