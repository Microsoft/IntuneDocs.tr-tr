---
title: Microsoft Intune - Azure’da SCEP ve PKCS sertifikalarını kaldırma | Microsoft Docs
titleSuffix: ''
description: Yöneticiler, Microsoft Intune’dan sertifika kaldırmak için silme veya devre dışı bırakma eylemlerini kullanabilirler. Bir cihaz kaydının silinmesi veya bir uyumluluk ilkesinin kaldırılması gibi, sertifikaların otomatik olarak kaldırıldığı bazı senaryolar da vardır. Intune lisansının kaybolması veya kaldırılması gibi, sertifikaların otomatik olarak cihazda kaldığı bazı senaryolar da vardır. Android, Android Kurumsal, iOS, macOS ve Windows cihazlara yönelik farklı yöntemlere göz atın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 977e7006d39ae76516d5b06019e463d1018aaa79
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229267"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma

Microsoft Intune cihazlara Basit sertifika kayıt Protokolü (SCEP) ve ortak anahtar şifreleme standartları (PKCS) sertifika ekleyebilirsiniz. Bu sertifikalar cihazı [sildiğinizde](devices-wipe.md#wipe) veya [devre dışı bıraktığınızda](devices-wipe.md#retire) da kaldırılabilir. 

Sertifikaların otomatik olarak kaldırıldığı veya cihazda kaldığı bazı diğer senaryolar da vardır. Bu makalede bazı yaygın senaryolar ve bu senaryoların PKCS ve SCEP sertifikaları üzerindeki etkisi listelenmiştir.

> [!NOTE]
> Kaldırın ve yüklenmekte olan bir kullanıcı için sertifikaları iptal etmek için şirket içi Active Directory veya Azure Active Directory (Azure AD) kaldırılır, bu adımları sırasıyla izleyin:
>
> 1. Silme veya kullanıcının cihazı devre dışı.
> 2. Kullanıcı, şirket içi Active Directory veya Azure AD kaldırın.

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


## <a name="ios-devices"></a>iOS cihazları

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

