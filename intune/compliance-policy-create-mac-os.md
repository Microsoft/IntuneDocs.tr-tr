---
title: Microsoft Intune - Azure’daki macOS cihazı uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da macOS cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Apple'ın sistem bütünlüğü korumasını gerekli kılın, parola kısıtlaması belirleyin, güvenlik duvarı kullanılmasını gerekli kılın, ağ geçidi denetleyicisine izin verin ve çok daha fazlasını yapın.
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
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59896669"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz macOS ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede Intune'daki macOS cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Bu ayarları mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak kullanarak işletim sistemi için alt veya üst sınır belirleyebilir, parolaların kullanım süresini kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Mac OS

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **macOS**’u seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir**: Bunu **Gerekli Kıl** şeklinde ayarlayarak, macOS cihazlarınızda [Sistem Bütünlüğü Korumasının](https://support.apple.com/HT204899) (Apple web sitesi açılır) etkin olmasını sağlayın. **Yapılandırılmadı** (varsayılan) ayarını belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.
- **En düşük işletim sistemi derleme sürümü**: Apple güvenlik güncelleştirmeleri yayımladığında genellikle işletim sistemi sürümü yerine derleme numarası güncelleştirilir. Bu özelliği kullanarak cihazda izin verilen en düşük işletim sistemi derleme sürümünü girebilirsiniz.
- **En yüksek işletim sistemi derleme sürümü**: Apple güvenlik güncelleştirmeleri yayımladığında genellikle işletim sistemi sürümü yerine derleme numarası güncelleştirilir. Bu özelliği kullanarak cihazda izin verilen en yüksek işletim sistemi derleme sürümünü girebilirsiniz.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmesi için önce bir parola girmesini **zorunlu tutun**.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolanın sahip olması gereken minimum rakam veya karakter sayısını girin.
- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.
- **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada bulunması gereken `&`, `#`, `%`, `!` gibi özel karakterlerin alt sınırını girin.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola zaman aşımı (gün sayısı)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Daha önce kullanılan kaç parolanın kullanılamayacağını belirtir.

    > [!IMPORTANT]
    > Bir macOS cihazda parola gerekliliği değiştirildiğinde, kullanıcı parolasını değiştirene kadar bu değişiklik gerçekleşmez. Örneğin parola uzunluğu sekiz basamakla kısıtlıyken macOS cihazın altı basamaklı bir parolası varsa, kullanıcı cihazda şifresini güncelleştirene kadar cihaz uyumlu kalır.

### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**: Cihazlarınızda veri deposunun şifrelenmesini sağlamak için **Gerekli Kıl**'ı seçin.

### <a name="device-security"></a>Cihaz Güvenliği

Güvenlik Duvarı, cihazları yetkisiz erişimine karşı korur. Güvenlik Duvarı'nı kullanarak uygulama başına bağlantıları denetleyebilirsiniz. 

- **Güvenlik duvarı**: Cihazları yetkisiz erişimine karşı korumaya yardımcı olmak için **Etkinleştir**'i seçin. Bu özelliği etkinleştirdiğinizde gelen İnternet bağlantılarını işleyebilir ve gizli modu kullanabilirsiniz. **Yapılandırılmamış** (varsayılan), güvenlik duvarını devre dışı bırakır ve ağ trafiğine izin verilir (engellenmedi).
- **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel İnternet hizmetleri için gerekenler dışında tüm gelen ağ bağlantılarını **engelleyin**. Bu ayarlar ekran paylaşımı, uzaktan erişim, iTunes müzik paylaşımı gibi tüm paylaşım hizmetlerini engeller. **Yapılandırılmamış** (varsayılan) gelen bağlantılara ve paylaşım hizmetlerine izin verir.
- **Gizli Mod**: Cihazların kötü niyetli kullanıcılar tarafından oluşturulmuş yoklama isteklerine yanıt vermesini önlemek için gizli modu **etkinleştirin**. Etkinleştirildiğinde, cihaz yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. **Yapılandırılmamış** (varsayılan) gizli modu devre dışı bırakır.

### <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

Daha fazla bilgi için bkz. [macOS üzerinde ağ geçidi denetleyicisi](https://support.apple.com/HT202491) (Apple web sitesini açar).

**Bu konumlardan indirilen uygulamalara izin verin**: Desteklenen uygulamaların farklı konumlardan cihazlarınıza yüklenmesine izin verir. Konum seçenekleriniz:

- **Yapılandırılmadı**: Varsayılan. Ağ geçidi denetleyicisi seçeneğinin uyumluluk veya uyumsuzluk üzerinde herhangi bir etkisi yoktur. 
- **Mac App Store**: Yalnızca Mac uygulama mağazası uygulamaları yüklenebilir. Üçüncü taraf veya tanımlı geliştirici uygulamaları yüklenemez. Bir kullanıcı, Gatekeeper’ı Mac App Store dışından uygulama yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Mac App Store ve tanımlanan geliştiriciler**: Mac uygulama mağazası ve tanımlı geliştirici uygulamalarını yükler. macOS, geliştiricilerin kimliğini denetler ve uygulama bütünlüğünü doğrulamak için başka denetimler de gerçekleştirir. Bir kullanıcı, Gatekeeper’ı bu seçenekler haricindeki uygulamaları yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Her yerden**: Herhangi bir yerden, herhangi bir geliştiriciye ait uygulamalar yüklenebilir. Bu, güvenliği en düşük olan seçenektir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [iOS cihazları için uyumluluk ilkesi ayarları](compliance-policy-create-ios.md).