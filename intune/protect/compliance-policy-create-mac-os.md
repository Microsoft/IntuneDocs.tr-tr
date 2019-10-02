---
title: Microsoft Intune - Azure’daki macOS cihazı uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da macOS cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Apple'ın sistem bütünlüğü korumasını gerekli kılın, parola kısıtlaması belirleyin, güvenlik duvarı kullanılmasını gerekli kılın, ağ geçidi denetleyicisine izin verin ve çok daha fazlasını yapın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 22bd3dd50f6c2cbeba59aad4dd00683d52668f72
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729789"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz macOS ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede Intune'daki macOS cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Bu ayarları mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak kullanarak işletim sistemi için alt veya üst sınır belirleyebilir, parolaların kullanım süresini kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Mac OS

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **macOS**’u seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir**: MacOS cihazlarınızın [sistem bütünlüğü koruması](https://support.apple.com/HT204899) (Apple 'ın Web sitesini açar) etkin olmasını **gerektir** . **Yapılandırılmadı** (varsayılan) ayarını belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **En yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemi sürümüne izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.
- **En düşük işletim sistemi derleme sürümü**: Apple güvenlik güncelleştirmeleri yayımladığında, işletim sistemi sürümü değil, derleme numarası genellikle güncellenir. Bu özelliği kullanarak cihazda izin verilen en düşük işletim sistemi derleme sürümünü girebilirsiniz.
- **En yüksek işletim sistemi derleme sürümü**: Apple güvenlik güncelleştirmeleri yayımladığında, işletim sistemi sürümü değil, derleme numarası genellikle güncellenir. Bu özelliği kullanarak cihazda izin verilen en yüksek işletim sistemi derleme sürümünü girebilirsiniz.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.
- **Paroladaki alfasayısal olmayan karakter sayısı**: parolada olması gereken `&`, `#`, `%`, `!` vb. gibi en az özel karakter sayısını girin.

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)** : Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılmasını önleyen önceki parola sayısı**: daha önce kullanılan parolaların sayısını girin.

    > [!IMPORTANT]
    > Bir macOS cihazda parola gerekliliği değiştirildiğinde, kullanıcı parolasını değiştirene kadar bu değişiklik gerçekleşmez. Örneğin parola uzunluğu sekiz basamakla kısıtlıyken macOS cihazın altı basamaklı bir parolası varsa, kullanıcı cihazda şifresini güncelleştirene kadar cihaz uyumlu kalır.

### <a name="encryption"></a>Şifreleme

- **Bir cihazda veri deposu şifreleme**: Cihazlarınızda veri deposunu şifrelemek için **Gerektir**’i seçin.

### <a name="device-security"></a>Cihaz Güvenliği

Güvenlik Duvarı, cihazları yetkisiz erişimine karşı korur. Güvenlik Duvarı'nı kullanarak uygulama başına bağlantıları denetleyebilirsiniz. 

- **Güvenlik duvarı**: cihazların yetkisiz erişime karşı korunmasına yardımcı olmak için **Etkinleştir** ' i seçin. Bu özelliği etkinleştirdiğinizde gelen İnternet bağlantılarını işleyebilir ve gizli modu kullanabilirsiniz. **Yapılandırılmamış** (varsayılan), güvenlik duvarını devre dışı bırakır ve ağ trafiğine izin verilir (engellenmedi).
- **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel Internet Hizmetleri için gereken bağlantılar dışındaki tüm gelen ağ bağlantılarını **engelleyin** . Bu ayarlar ekran paylaşımı, uzaktan erişim, iTunes müzik paylaşımı gibi tüm paylaşım hizmetlerini engeller. **Yapılandırılmamış** (varsayılan) gelen bağlantılara ve paylaşım hizmetlerine izin verir.
- **Gizli mod**: cihazların yoklama isteklerine yanıt vermesini engellemek için gizli modu **etkinleştirin** ve bu, kötü amaçlı Kullanıcılarım haline getirilebilir. Etkinleştirildiğinde, cihaz yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder. **Yapılandırılmamış** (varsayılan) gizli modu devre dışı bırakır.

### <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

Daha fazla bilgi için bkz. [macOS üzerinde ağ geçidi denetleyicisi](https://support.apple.com/HT202491) (Apple web sitesini açar).

**Şu konumlardan indirilen uygulamalara izin ver**: Desteklenen uygulamaların farklı konumlardan cihazlarınıza yüklenmesine izin verir. Konum seçenekleriniz:

- **Yapılandırılmadı**: Varsayılan seçenektir. Ağ geçidi denetleyicisi seçeneğinin uyumluluk veya uyumsuzluk üzerinde herhangi bir etkisi yoktur. 
- **Mac App Store**: Yalnızca Mac uygulama mağazası uygulamaları yüklenebilir. Üçüncü taraf veya tanımlı geliştirici uygulamaları yüklenemez. Bir kullanıcı, Gatekeeper’ı Mac App Store dışından uygulama yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Mac App Store ve tanımlı geliştiriciler**: Mac uygulama mağazası ve tanımlı geliştirici uygulamalarını yükler. macOS, geliştiricilerin kimliğini denetler ve uygulama bütünlüğünü doğrulamak için başka denetimler de gerçekleştirir. Bir kullanıcı, Gatekeeper’ı bu seçenekler haricindeki uygulamaları yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Her yerden**: Herhangi bir yerden, herhangi bir geliştiriciye ait uygulamalar yüklenebilir. Bu, güvenliği en düşük olan seçenektir.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [iOS cihazları için uyumluluk ilkesi ayarları](compliance-policy-create-ios.md).