---
title: Microsoft Intune - Azure’da SCEP ve PKCS sertifikalarını kaldırma | Microsoft Docs
titleSuffix: ''
description: Yöneticiler, Microsoft Intune’dan sertifika kaldırmak için silme veya devre dışı bırakma eylemlerini kullanabilirler. Bir cihaz kaydının silinmesi veya bir uyumluluk ilkesinin kaldırılması gibi, sertifikaların otomatik olarak kaldırıldığı bazı senaryolar da vardır. Intune lisansının kaybolması veya kaldırılması gibi, sertifikaların otomatik olarak cihazda kaldığı bazı senaryolar da vardır. Android, Android Kurumsal, iOS, macOS ve Windows cihazlara yönelik farklı yöntemlere göz atın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: lacranda
ms.openlocfilehash: 6a1280ca2a78853ae188ad68620f0b82846a365a
ms.sourcegitcommit: 9daaeba9a960c50efcc951856234fbfec3635737
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231756"
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

