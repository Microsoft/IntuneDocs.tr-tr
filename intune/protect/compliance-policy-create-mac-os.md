---
title: Microsoft Intune - Azure’daki macOS cihazı uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da macOS cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. Apple'ın sistem bütünlüğü korumasını gerekli kılın, parola kısıtlaması belirleyin, güvenlik duvarı kullanılmasını gerekli kılın, ağ geçidi denetleyicisine izin verin ve çok daha fazlasını yapın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 518f0b825b71a9773ed66dd480b329e998f919c4
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813510"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz macOS ayarları

Bu makalede Intune'daki macOS cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Bu ayarları mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak kullanarak işletim sistemi için alt veya üst sınır belirleyebilir, parolaların kullanım süresini kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Mac OS

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **macOS**’u seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

- **Sistem bütünlüğü koruması gerektir**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -MacOS cihazlarının [sistem bütünlüğü koruması](https://support.apple.com/HT204899) (Apple 'ın Web sitesini açar) etkin olmasını gerektir.  

## <a name="device-properties"></a>Cihaz Özellikleri

- **Gereken en düşük işletim sistemi**:  
  Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Cihaz kullanıcısı cihazlarını yükseltmeyi tercih edebilir. Bundan sonra, kuruluş kaynaklarına erişebilir.

- **İzin verilen en yüksek işletim sistemi sürümü**:  
  Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, kuruluş kaynaklarına erişim engellenir. Cihaz kullanıcısına BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz kuruluş kaynaklarına erişemez.

- **En düşük işletim sistemi derleme sürümü**:  
  Apple güvenlik güncelleştirmeleri yayımladığında genellikle işletim sistemi sürümü yerine derleme numarası güncelleştirilir. Bu özelliği kullanarak cihazda izin verilen en düşük işletim sistemi derleme sürümünü girebilirsiniz.

- **En yüksek işletim sistemi derleme sürümü**:  
  Apple güvenlik güncelleştirmeleri yayımladığında genellikle işletim sistemi sürümü yerine derleme numarası güncelleştirilir. Bu özelliği kullanarak cihazda izin verilen en yüksek işletim sistemi derleme sürümünü girebilirsiniz.

## <a name="system-security-settings"></a>Sistem güvenliği ayarları

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için bir parola iste**:  
  - **Yapılandırılmadı** (*varsayılan*)
  - **Gerektir** Kullanıcıların cihazlarına erişebilmesi için önce bir parola girmesi gerekir.

- **Basit parolalar**:  
  - **Yapılandırılmadı** (*varsayılan*)-kullanıcılar, **1234** veya **1111**gibi basit parolalar oluşturabilir.
  - **Engelle** -kullanıcılar, **1234** veya **1111**gibi basit parolalar oluşturamaz.

- **Minimum parola uzunluğu**:  
  Parolanın sahip olması gereken minimum rakam veya karakter sayısını girin.

- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.

- **Paroladaki alfasayısal olmayan karakter sayısı**:  
  Parolada olması gereken `&`, `#`, `%`, `!`vb. gibi en az özel karakter sayısını girin.

  Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**:  
  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.

- **Parola kullanım süresi (gün olarak)** :  
  Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.

- **Yeniden kullanılması önlenecek önceki parola sayısı**:  
  Daha önce kullanılan kaç parolanın kullanılamayacağını belirtir.
> [!IMPORTANT]
> Bir macOS cihazda parola gerekliliği değiştirildiğinde, kullanıcı parolasını değiştirene kadar bu değişiklik gerçekleşmez. Örneğin parola uzunluğu sekiz basamakla kısıtlıyken macOS cihazın altı basamaklı bir parolası varsa, kullanıcı cihazda şifresini güncelleştirene kadar cihaz uyumlu kalır.

### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**:  
  - **Yapılandırılmadı** (*varsayılan*)
  - **Gerektir** -kullanım, cihazlarınızda veri depolamayı şifrelemek için *gerektir* .

### <a name="device-security"></a>Cihaz Güvenliği

Güvenlik Duvarı, cihazları yetkisiz erişimine karşı korur. Güvenlik Duvarı'nı kullanarak uygulama başına bağlantıları denetleyebilirsiniz. 

- **Güvenlik Duvarı**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar güvenlik duvarını devre dışı bırakır ve ağ trafiğine izin verilir (engellenmez).
  - **Etkinleştir** -cihazların yetkisiz erişime karşı korunmasına yardımcı olmak için *Etkinleştir* ' i kullanın. Bu özelliği etkinleştirdiğinizde gelen İnternet bağlantılarını işleyebilir ve gizli modu kullanabilirsiniz. 

- **Gelen bağlantılar**:  
  - **Yapılandırılmadı** (*varsayılan*)-gelen bağlantılara ve paylaşım hizmetlerine izin verir.
  - **Engelle** -DHCP, Bonjour ve IPSec gibi temel Internet Hizmetleri için gereken bağlantılar hariç tüm gelen ağ bağlantılarını engelleyin. Bu ayarlar ekran paylaşımı, uzaktan erişim, iTunes müzik paylaşımı gibi tüm paylaşım hizmetlerini engeller.  

- **Gizli Mod**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar gizli mod kapalı bırakır.
  - **Enable** -cihazların, kötü amaçlı Kullanıcılarım haline getirilen yoklama isteklerine yanıt vermesini engellemek için gizli modu etkinleştirin. Etkinleştirildiğinde, cihaz yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder.  

### <a name="gatekeeper"></a>Ağ Geçidi Denetleyicisi

Daha fazla bilgi için bkz. [macOS üzerinde ağ geçidi denetleyicisi](https://support.apple.com/HT202491) (Apple web sitesini açar).

**Şu konumlardan indirilen uygulamalara izin ver**: Desteklenen uygulamaların farklı konumlardan cihazlarınıza yüklenmesine izin verir. Konum seçenekleriniz:

- **Yapılandırılmadı** (*varsayılan*)-ağ geçidi seçeneğinin uyumluluk veya uyumsuzluk üzerinde hiçbir etkisi yoktur.  
- **Mac App Store** -yalnızca Mac App Store için uygulamaları yükler. Üçüncü taraf veya tanımlı geliştirici uygulamaları yüklenemez. Bir kullanıcı, Gatekeeper’ı Mac App Store dışından uygulama yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- **Mac App Store ve tanımlanan geliştiriciler** -Mac App Store ve tanımlanan geliştiricilerden uygulama yükler. macOS, geliştiricilerin kimliğini denetler ve uygulama bütünlüğünü doğrulamak için başka denetimler de gerçekleştirir. Bir kullanıcı, Gatekeeper’ı bu seçenekler haricindeki uygulamaları yüklemesi için seçerse cihaz uyumsuz olarak değerlendirilir.
- Her **yerden** uygulama herhangi bir yerden ve herhangi bir geliştirici tarafından yüklenebilir. Bu, güvenliği en düşük olan seçenektir.
 

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [iOS cihazları için uyumluluk ilkesi ayarları](compliance-policy-create-ios.md).