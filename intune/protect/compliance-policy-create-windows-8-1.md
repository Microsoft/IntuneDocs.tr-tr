---
title: Microsoft Intune - Azure’daki Windows 8.1 uyumluluk ilkeleri | Microsoft Docs
description: Microsoft Intune'da Windows 8.1 ve Windows Phone 8.1 cihazlarınızda uyumluluk ayarı yaparken kullanabileceğiniz tüm ayarların bulunduğu listeyi inceleyin. İşletim sistemi alt ve üst sınırı uyumluluğunu denetleyin, parola kısıtlamalarını ve uzunluğunu belirleyin, veri depolama alanında şifrelemeyi etkinleştirin ve çok daha fazlasını yapın.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e074d922078a9772ca67a6ebd99948bc3e64601
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813219"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Intune'u kullanarak cihazları uyumlu veya uyumlu değil şeklinde işaretlemek için kullanabileceğiniz Windows 8.1 ayarları

Bu makalede Intune'daki Windows 8.1 cihazları için yapılandırabileceğiniz farklı uyumluluk ayarları listelenmekte ve anlatılmaktadır. Bu ayarları mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak kullanarak basit parola kullanılmasını engelleyebilir, işletim sistemi için alt ve üst sınır belirleyebilir ve çok daha fazlasını yapabilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- WVPN profillerinidows Phone 8.1
- Windows 8.1 ve üzeri

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Windows Phone 8.1** veya **Windows 8.1 ve sonrası**'nı seçin.

## <a name="device-properties"></a>Cihaz Özellikleri

### <a name="operating-system-version"></a>İşletim Sistemi Sürümü

**Windows Phone 8,1 ve üzeri**
- **Mobil cihazlar Için en düşük işletim sistemi sürümü**:  
  İzin verilen en düşük sürümü girin. Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Cihaz kullanıcısı cihazlarını yükseltmeyi seçebilir ve ardından şirket kaynaklarına erişim alabilir.

- **Mobil cihazlar Için en yüksek işletim sistemi sürümü**:  
  İzin verilen en yüksek sürümü girin. Bir cihaz, kurala girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Cihaz kullanıcısına BT yöneticisine başvurması istenir. Cihaz, işletim sistemi sürümüne izin vermek için bir kural olana kadar kuruluş kaynaklarına erişemez.

**Windows 8.1 ve üzeri**
- **En düşük işletim sistemi sürümü**:  
  İzin verilen en düşük sürümü girin. Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Cihaz kullanıcısı cihazlarını yükseltmeyi seçebilir ve ardından şirket kaynaklarına erişim alabilir.

- **En yüksek işletim sistemi sürümü**:  
  İzin verilen en yüksek sürümü girin. Bir cihaz, kurala girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Cihaz kullanıcısına BT yöneticisine başvurması istenir. Cihaz, işletim sistemi sürümüne izin vermek için bir kural olana kadar kuruluş kaynaklarına erişemez.

Windows 8.1 bilgisayarları **3** sürümünü döndürür. Windows için işletim sistemi sürüm kuralı Windows 8.1’e ayarlanırsa, cihaz Windows 8.1’e sahip olsa bile uyumsuz olarak bildirilir.

## <a name="system-security"></a>Sistem Güvenliği

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için bir parola iste**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -kullanıcıların cihazına erişebilmeleri için önce bir parola girmesi gerekir.

- **Basit parolalar**:  
  - **Yapılandırılmadı** (*varsayılan*)-kullanıcılar, **1234** veya **1111**gibi basit parolalar oluşturabilir.
  - **Engelle** -kullanıcılar, **1234** veya **1111**gibi basit parolalar oluşturamaz.  

- **Minimum parola uzunluğu**:  
  Parolanın sahip olması gereken minimum rakam veya karakter sayısını girin.

  Windows çalıştıran ve bir Microsoft hesabı ile erişilen cihazlarda, aşağıdaki koşullardan biri karşılandığında uyumluluk ilkesi doğru şekilde değerlendirilemiyor:  
  - Minimum parola uzunluğu sekiz karakterden fazla
  - En az karakter kümesi sayısı ikiden büyük

- **Parola türü**:  
  Bir parolanın yalnızca **sayısal** karakterleri olması gerekip gerekmediğini veya sayıların ve diğer karakterlerin (**alfasayısal**) bir karışımı olması gerekip gerekmediğini seçin.

  *Alfasayısal*olarak ayarlandığında, aşağıdaki ayar kullanılabilir.  

  - **Paroladaki alfasayısal olmayan karakter sayısı**:  
    *Parola türü* **alfasayısal**olarak ayarlandığında, parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtin. Seçenekler **0** ile **4** küme arasındadır ve varsayılan değer **1**' dir.
    
    Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir. Microsoft hesabı ile erişilen cihazlarda, aşağıdaki koşullardan biri karşılandığında uyumluluk ilkesi doğru şekilde değerlendirilemiyor:

    - Minimum parola uzunluğu sekiz karakterden fazla
    - En az karakter kümesi sayısı ikiden büyük

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**:  
  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.

- **Parola kullanım süresi (gün olarak)** :  
  Parolanın süresi dolmadan önce geçecek gün sayısını seçin ve kullanıcıların yeni bir tane oluşturması gerekir.

- **Yeniden kullanılması önlenecek önceki parola sayısı**:  
  Daha önce kullanılan kaç parolanın kullanılamayacağını belirtir.

### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**:  
  - **Yapılandırılmadı** (*varsayılan*)
  - **Gerektir** -kullanım, cihazlarınızda veri depolamayı şifrelemek için *gerektir* .


<!-- not on phone   
- **Require encryption on mobile device**: **Require** the device to be encrypted to connect to data storage resources.
--> 

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Bkz. [Windows 10 ve üzeri cihazlar için uyumluluk ilkesi ayarları](compliance-policy-create-windows.md).