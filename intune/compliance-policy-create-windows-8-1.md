---
title: Windows 8.1 uyumluluk ayarları Microsoft Intune - Azure | Microsoft Docs
description: Windows 8.1 ve Windows Phone 8.1 cihazları için Uyumluluk Intune ayarlarken kullanabileceğiniz tüm ayarları bir listesini görürsünüz. En düşük ve en yüksek işletim sistemi, parola kısıtlamaları ve uzunluğu, uyumluluk denetimi ve veri depolama şifrelemesini sağlar.
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
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59425338"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Cihazları uyumlu veya uyumsuz Intune kullanan olarak işaretlemek için Windows 8.1 ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve ıntune'da Windows 8.1 cihazlarında yapılandırabileceğiniz farklı uyumluluk ayarları açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları basit parolaları engelle, en az ve en yüksek işletim sistemi sürümü ve daha fazla ayarlamak için kullanın.

Bu özellik şu platformlarda geçerlidir:

- Windows Phone 8.1
- Windows 8.1 ve üzeri

Bir Intune Yöneticisi olarak, Kurumsal kaynaklarınızı korumaya yardımcı olmak için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri hakkında daha fazla, hangi bilgi edinmek için bkz [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). İçin **Platform**seçin **Windows Phone 8.1** veya **Windows 8.1 ve üzeri**.

## <a name="device-properties"></a>Cihaz özellikleri

- **Gerekli en düşük işletim sistemi**: İzin verilen düşük sürümü girin. Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında, ile uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü**: Sürüm izin verilen üst sınırı girin. Bir cihaz girilen kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, şirket kaynaklarına erişimi engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. Cihaz, işletim sistemine izin veren kuralın değiştirene kadar kuruluş kaynaklarına erişemez.

Windows 8.1 bilgisayarları **3** sürümünü döndürür. İşletim sistemi sürüm kuralı Windows için Windows 8.1 için ayarlanmış ise, Windows 8.1 cihaz sahip olsa bile sonra cihaz uyumsuz olarak raporlanır.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin.
- **Basit parolalar**: Kümesine **blok** kullanıcılar gibi basit parolalar oluşturamıyor **1234** veya **1111**. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: En düşük rakam veya karakter bulunması gereken sayısını girin.

  Windows çalıştıran ve bir Microsoft hesabı ile erişilen cihazlarda uyumluluk ilkesi, şu durumlarda doğru değerlendirme yapamaz:
  - En düşük parola uzunluğu sekiz karakterden fazlaysa
  - Veya en düşük karakter kümesi sayısı ikiden fazlaysa

- **Parola türü**: Parola yalnızca olması gerekip gerekmediğini seçin **sayısal** karakter veya sayı ve diğer karakterlerin bir karışımı yoksa (**alfasayısal**).
  
  - **Paroladaki alfasayısal olmayan karakter sayısı**: **Gerekli parola türü** **Alfasayısal** olarak ayarlanırsa bu ayar parolanın içermesi gereken en az karakter kümesi sayısını belirtir. Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir. Bir Microsoft hesabı ile güvenliği sağlanan cihazlar için Uyumluluk İlkesi düzgün değerlendirme yapamaz:

    - En düşük parola uzunluğu sekiz karakterden fazlaysa
    - Veya minimum karakter kümesi sayısı ikiden ise

- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir tane oluşturmanız gerekir önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamaz önceden kullanılmış parola sayısını girin.

### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir**: **Gerekli** veri deposu kaynaklarına bağlanmak için şifrelenmesini cihaz.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlar için Eylemler ekleme](actions-for-noncompliance.md) ve [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).
- [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md).
- Bkz: [uyumluluk İlkesi ayarları Windows 10 ve üzeri için](compliance-policy-create-windows.md) cihazlar.