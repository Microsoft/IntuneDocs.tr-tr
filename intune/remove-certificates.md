---
title: Microsoft Intune - Azure’da SCEP ve PKCS sertifikalarını kaldırma | Microsoft Docs
titleSuffix: ''
description: Yöneticiler, Microsoft Intune’dan sertifika kaldırmak için silme veya devre dışı bırakma eylemlerini kullanabilirler. Bir cihaz kaydının silinmesi veya bir uyumluluk ilkesinin kaldırılması gibi, sertifikaların otomatik olarak kaldırıldığı bazı senaryolar da vardır. Intune lisansının kaybolması veya kaldırılması gibi, sertifikaların otomatik olarak cihazda kaldığı bazı senaryolar da vardır. Android, Android Kurumsal, iOS, macOS ve Windows cihazlara yönelik farklı yöntemlere göz atın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: lacranda
ms.openlocfilehash: de2f201e6a7d0181847db5d212625c9eed9ea698
ms.sourcegitcommit: 9c06d8071b9affeda32e367bfe85d89bc524ed0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67413782"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma

Microsoft Intune Basit sertifika kayıt Protokolü (SCEP) ve ortak anahtar şifreleme standartları (PKCS) sertifika profilleri cihazlara sertifika eklemek için kullanabilirsiniz. 

Bu sertifikalar olabilir ne zaman kaldırıldı, [silme](devices-wipe.md#wipe) veya [devre dışı bırakma](devices-wipe.md#retire) cihaz. Ayrıca vardır burada sertifikaları otomatik olarak kaldırılır senaryosunu ve burada sertifikalar cihazda kalır. Bu makalede bazı yaygın senaryolar ve bu senaryoların PKCS ve SCEP sertifikaları üzerindeki etkisi listelenmiştir.

> [!NOTE]
> Kaldırın ve yüklenmekte olan bir kullanıcı için sertifikaları iptal etmek için şirket içi Active Directory veya Azure Active Directory (Azure AD) kaldırılır, bu adımları sırasıyla izleyin:
>
> 1. Silme veya kullanıcının cihazı devre dışı.
> 2. Kullanıcı, şirket içi Active Directory veya Azure AD kaldırın.

## <a name="manually-deleted-certificates"></a>El ile silinmiş sertifikaları  

Bir sertifikayı el ile silinmesini platformları ve SCEP veya PKCS sertifika profilleri tarafından sağlanan sertifikalar arasında geçerli bir senaryodur. Örneğin, bir sertifika ilkesi tarafından hedeflenen cihaz kaldığında bir kullanıcı bir CİHAZDAN bir sertifika silebilir.  

Sertifika silindikten sonra bu senaryoda, cihazı Intune hizmetine giriş denetlediğinde beklenen sertifika eksik olarak uyumsuz olduğu anlaşıldığında. Intune daha sonra cihaz uyumluluk için geri yüklemek için yeni bir sertifika verir. Sertifikayı geri yüklemek için ek Eylem gerekmiyor.  


## <a name="windows-devices"></a>Windows cihazları

#### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.
- Cihaz, bir Azure AD grubundan kaldırılır.
- Bir sertifika profili grubu atamadan kaldırılır.

Bir SCEP sertifikası şu durumlarda iptal edilir:
- Bir yönetici, değiştirir veya SCEP profili güncelleştirir.

Kök Sertifikanın kaldırıldığı zaman:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

SCEP sertifikaları *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

Kök Sertifikanın kaldırıldığı zaman:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

PKCS sertifikalarını *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.
- Bir yönetici, değiştirir veya PKCS profilini güncelleştirir.
- Bir sertifika profili grubu atamadan kaldırılır.


## <a name="ios-devices"></a>iOS aygıtları:

#### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.
- Cihaz Azure AD grubundan kaldırılır.
- Bir sertifika profili grubu atamadan kaldırılır.

Bir SCEP sertifikası şu durumlarda iptal edilir:
- Bir yönetici, değiştirir veya SCEP profili güncelleştirir.

Kök Sertifikanın kaldırıldığı zaman:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

SCEP sertifikaları *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

Bir PKCS sertifikası şu durumlarda kaldırılır:
- Bir sertifika profili grubu atamadan kaldırılır.
  
Kök Sertifikanın kaldırıldığı zaman:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

PKCS sertifikalarını *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.
- Bir yönetici, değiştirir veya PKCS profilini güncelleştirir.

## <a name="android-knox-devices"></a>Android KNOX cihazları

#### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.

Bir SCEP sertifikası şu durumlarda iptal edilir:
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.
- Cihaz, bir Azure AD grubundan kaldırılır.
- Bir sertifika profili grubu atamadan kaldırılır.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.
- Bir yönetici, değiştirir veya SCEP profili güncelleştirir.

Kök Sertifikanın kaldırıldığı zaman:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

SCEP sertifikaları *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

Kök Sertifikanın kaldırıldığı zaman:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici çalıştırır [silme](devices-wipe.md#wipe) eylem.
- Bir yönetici çalıştırır [devre dışı bırakma](devices-wipe.md#retire) eylem.

PKCS sertifikalarını *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.
- Bir yönetici, değiştirir veya PKCS profilini güncelleştirir.
- Bir sertifika profili grubu atamadan kaldırılır.
  
  
> [!NOTE]
> Android for Work cihazlar için yukarıdaki senaryoların doğrulanmaz. Eski Android cihazlar (Samsung olmayan, olmayan iş profili cihazları herhangi) sertifika kaldırma için etkin değil. 

## <a name="macos-certificates"></a>macOS sertifikaları

#### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:
- Bir kullanıcının bağlı kalmayı.
- Bir yönetici olarak çalışan bir [devre dışı bırakma](devices-wipe.md#retire) eylem.
- Cihaz, bir Azure AD grubundan kaldırılır.
- Bir sertifika profili grubu atamadan kaldırılır.

Bir SCEP sertifikası şu durumlarda iptal edilir:
- Bir yönetici, değiştirir veya SCEP profili güncelleştirir.

SCEP sertifikaları *kalın* (sertifikalar iptal veya kaldırılır) cihaz üzerinde zaman:
- Bir kullanıcının Intune lisansı kaybeder.
- Bir yönetici, Intune lisansı çeker.
- Bir yönetici kullanıcıyı veya grubu, Azure AD'den kaldırır.

> [!NOTE]
> macOS cihazlarda fabrika sıfırlaması yapmak için [silme](devices-wipe.md#wipe) eyleminin kullanımı desteklenmez.

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

macOS’da PKCS sertifikaları desteklenmez.

