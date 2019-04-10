---
title: Microsoft Intune - Azure'da macOS cihaz uyumluluk ayarları | Microsoft Docs
description: MacOS cihazları için Uyumluluk Intune ayarlarken kullanabileceğiniz tüm ayarları bir listesini görürsünüz. Apple'nın sistem bütünlüğü koruması gerektir, parola kısıtlamalarını ayarlamak, bir güvenlik duvarı gerektir, ağ geçidi ve daha fazla izin verilir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3224e7400ad56f971488aba53bb073a0d33bb9d
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423654"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>cihazları uyumlu veya uyumsuz Intune kullanan olarak işaretlemek için macOS ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve ıntune'da macOS cihazlarında yapılandırabileceğiniz farklı uyumluluk ayarları açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, en az veya en yüksek işletim sistemi sürümü, süresi dolacak şekilde kümesi parolalar ve daha fazla ayarlamak için bu ayarları kullanın.

Bu özellik şu platformlarda geçerlidir:

- Mac OS

Bir Intune Yöneticisi olarak, Kurumsal kaynaklarınızı korumaya yardımcı olmak için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri hakkında daha fazla, hangi bilgi edinmek için bkz [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **macOS**’u seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir**: **Gerekli** için macOS cihazlarınızda [sistem bütünlüğü koruması](https://support.apple.com/HT204899) (Apple web sitesini açar) etkin. Ayarlandığında **yapılandırılmadı** (varsayılan), bu ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.

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
- **Paroladaki alfasayısal olmayan karakter sayısı**: En az özel karakter sayısını girin `&`, `#`, `%`, `!`ve benzeri Parolada olması gerekir.

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

- **Güvenlik Duvarı**: Seçin **etkinleştirme** cihazları yetkisiz erişime karşı korunmasına yardımcı olmak için. Bu özelliği etkinleştirdiğinizde gelen İnternet bağlantılarını işleyebilir ve gizli modu kullanabilirsiniz. **Yapılandırılmamış** (varsayılan), güvenlik duvarını devre dışı bırakır ve ağ trafiğine izin verilir (engellenmedi).
- **Gelen bağlantıları**: **Blok** gelen tüm ağ bağlantıları olması dışında DHCP, Bonjour ve IPSec gibi temel internet Hizmetleri için gereken bağlantılar. Bu ayar, ayrıca ekran paylaşımı, uzaktan erişim, iTunes müziği paylaşımı ve daha fazlası dahil olmak üzere tüm paylaşım hizmetlerini engeller. **Yapılandırılmamış** (varsayılan) gelen bağlantılara ve paylaşım hizmetlerine izin verir.
- **Gizli mod**: **Etkinleştirme** cihazların kötü amaçlı kullanıcılar yapılan istekleri, yoklama isteklerine yanıt vermesini önlemek için gizli modu. Etkinleştirildiğinde, cihaz yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. **Yapılandırılmamış** (varsayılan) gizli modu devre dışı bırakır.

### <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

Daha fazla bilgi için [macOS üzerinde ağ geçidi](https://support.apple.com/HT202491) (Apple web sitesini açar).

**Bu konumlardan indirilen uygulamalara izin ver**: Desteklenen uygulamaların farklı konumlardan cihazlarınızda yüklenmesi için izin verir. Konum seçenekleriniz:

- **Yapılandırılmamış**: Varsayılan. Ağ geçidi seçeneği, uyumluluk veya uyumsuzluk herhangi bir etkisi yoktur. 
- **Mac App Store**: Yalnızca Mac app store uygulamaları yükleyin. Üçüncü taraf veya tanımlı geliştirici uygulamaları yüklenemez. Bir kullanıcı, Gatekeeper’ı Mac App Store dışından uygulama yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Mac App Store ve tanımlanan geliştiriciler**: İçin Mac app store ve tanımlanan geliştiriciler uygulamalarını yükleyin. macOS, geliştiricilerin kimliğini denetler ve uygulama bütünlüğünü doğrulamak için başka denetimler de gerçekleştirir. Bir kullanıcı, Gatekeeper’ı bu seçenekler haricindeki uygulamaları yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Her yerden**: Uygulamalar her yerden ve herhangi bir geliştirici tarafından gelen yüklenebilir. Bu, güvenliği en düşük olan seçenektir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlar için Eylemler ekleme](actions-for-noncompliance.md) ve [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).
- [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md).
- Bkz: [iOS için Uyumluluk İlkesi ayarları](compliance-policy-create-ios.md) cihazlar.