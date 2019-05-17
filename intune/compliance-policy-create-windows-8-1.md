---
title: Microsoft Intune - Azure’daki Windows 8.1 uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da Windows 8.1 ve Windows Phone 8.1 cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. İşletim sistemi alt ve üst sınırı uyumluluğunu denetleyin, parola kısıtlamalarını ve uzunluğunu belirleyin, veri depolama alanında şifrelemeyi etkinleştirin ve çok daha fazlasını yapın.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4ed863378616f8001beab89177c642404287e7d3
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59893898"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz Windows 8.1 ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede Intune'daki Windows 8.1 cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Bu ayarları mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak kullanarak basit parola kullanılmasını engelleyebilir, işletim sistemi için alt ve üst sınır belirleyebilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- Windows Phone 8.1
- Windows 8.1 ve üzeri

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Windows Phone 8.1** veya **Windows 8.1 ve sonrası**'nı seçin.

## <a name="device-properties"></a>Cihaz özellikleri

- **Gereken en düşük işletim sistemi**: İzin verilen en düşük sürümü girin. Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü**: İzin verilen en yüksek sürümü girin. Cihaz kurala girilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği yapılana kadar bu cihaz kuruluş kaynaklarına erişemez.

Windows 8.1 bilgisayarları **3** sürümünü döndürür. Windows için işletim sistemi sürüm kuralı Windows 8.1’e ayarlanırsa, cihaz Windows 8.1’e sahip olsa bile uyumsuz olarak bildirilir.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmesi için önce bir parola girmesini **zorunlu tutun**.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolanın sahip olması gereken minimum rakam veya karakter sayısını girin.

  Windows çalıştıran ve bir Microsoft hesabı ile erişilen cihazlarda uyumluluk ilkesi, şu durumlarda doğru değerlendirme yapamaz:
  - En düşük parola uzunluğu sekiz karakterden fazlaysa
  - Veya en düşük karakter kümesi sayısı ikiden fazlaysa

- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.
  
  - **Paroladaki alfasayısal olmayan karakter sayısı**: **Gerekli parola türü** **Alfasayısal** olarak ayarlanırsa bu ayar parolanın içermesi gereken en az karakter kümesi sayısını belirtir. Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir. Bir Microsoft hesabı ile erişilen cihazlarda uyumluluk ilkesi, şu durumlarda doğru değerlendirme yapamaz:

    - En düşük parola uzunluğu sekiz karakterden fazlaysa
    - Veya en düşük karakter kümesi sayısı ikiden fazlaysa

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola zaman aşımı (gün sayısı)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Daha önce kullanılan kaç parolanın kullanılamayacağını belirtir.

### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir**: Cihazın veri deposu kaynaklarına bağlanmak için şifrelenmesini **gerektirin**.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [Windows 10 ve üzeri cihazlar için uyumluluk ilkesi ayarları](compliance-policy-create-windows.md).