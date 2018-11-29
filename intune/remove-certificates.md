---
title: Microsoft Intune - Azure’da SCEP ve PKCS sertifikalarını kaldırma | Microsoft Docs
titleSuffix: ''
description: Yöneticiler, Microsoft Intune’dan sertifika kaldırmak için silme veya devre dışı bırakma eylemlerini kullanabilirler. Bir cihaz kaydının silinmesi veya bir uyumluluk ilkesinin kaldırılması gibi, sertifikaların otomatik olarak kaldırıldığı bazı senaryolar da vardır. Intune lisansının kaybolması veya kaldırılması gibi, sertifikaların otomatik olarak cihazda kaldığı bazı senaryolar da vardır. Android, Android Kurumsal, iOS, macOS ve Windows cihazlara yönelik farklı yöntemlere göz atın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 06b568ee7cc2dc55a8d44cf04b96078b47d8c4b3
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579175"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma

Microsoft Intune’da cihazlara SCEP ve PKCS sertifikaları ekleyebilirsiniz. Bu sertifikalar cihazı [sildiğinizde](devices-wipe.md#wipe) veya [devre dışı bıraktığınızda](devices-wipe.md#retire) da kaldırılabilir. Sertifikaların otomatik olarak kaldırıldığı veya cihazda kaldığı bazı diğer senaryolar da vardır.

Bu makalede bazı yaygın senaryolar ve bu senaryoların PKCS ve SCEP sertifikaları üzerindeki etkisi listelenmiştir.

> [!NOTE]
> Active Directory’den (AD) veya Azure Active Directory’den kaldırılmakta olan bir kullanıcıya ait sertifikaları kaldırmak ve iptal etmek için aşağıdaki adımları verilen sırayla takip ettiğinizden emin olun:
>
>    1. Kullanıcının cihazını devre dışı bırakma veya silme
>    2. Kullanıcıyı AD’den veya Azure AD’den kaldırma

## <a name="windows-devices"></a>Windows cihazları

#### <a name="scep-certificates"></a>SCEP sertifikaları

- Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında
  - Cihaz Azure Active Directory (AD) grubundan kaldırıldığında
  - Sertifika profili Grup ataması kaldırıldı

- Bir SCEP sertifikası şu durumlarda iptal edilir:
  - Yönetici, SCEP profilini değiştirdiğinde veya güncelleştirdiğinde

- Kök sertifika şu durumlarda kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- SCEP sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

- Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- Kök sertifika şu durumlarda kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- PKCS sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında
  - Yönetici, PKCS profilini değiştirdiğinde veya güncelleştirdiğinde
  - Sertifika profili Grup ataması kaldırıldı


## <a name="ios-devices"></a>iOS cihazları

#### <a name="scep-certificates"></a>SCEP sertifikaları

- Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında
  - Cihaz Azure Active Directory (AD) grubundan kaldırıldığında
  - Sertifika profili Grup ataması kaldırıldı

- Bir SCEP sertifikası şu durumlarda iptal edilir:
  - Yönetici, SCEP profilini değiştirdiğinde veya güncelleştirdiğinde

- Kök sertifika şu durumlarda kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- SCEP sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

- Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- Bir PKCS sertifikası şu durumlarda kaldırılır:
  - Sertifika profili Grup ataması kaldırıldı
  
- Kök sertifika şu durumlarda kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- PKCS sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında
  - Yönetici, PKCS profilini değiştirdiğinde veya güncelleştirdiğinde

## <a name="android-knox-devices"></a>Android KNOX cihazları

#### <a name="scep-certificates"></a>SCEP sertifikaları

- Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında

- Bir SCEP sertifikası şu durumlarda iptal edilir:
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında
  - Cihaz Azure Active Directory (AD) grubundan kaldırıldığında
  - Sertifika profili Grup ataması kaldırıldı
  - Yönetici, kullanıcıyı veya grubu Azure Active Directory’den (AD) kaldırdığında
  - Yönetici, SCEP profilini değiştirdiğinde veya güncelleştirdiğinde

- Kök sertifika şu durumlarda kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- SCEP sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

- Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- Kök sertifika şu durumlarda kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [silme](devices-wipe.md#wipe) eylemini çalıştırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında

- PKCS sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında
  - Yönetici, PKCS profilini değiştirdiğinde veya güncelleştirdiğinde
  - Sertifika profili Grup ataması kaldırıldı
  
  
> [!NOTE]
> Yukarıdaki senaryolar, Android for work cihazları için geçerli değildir. Eski Android cihazlarında (Samsung olmayan, iş profili olmayan herhangi bir cihaz) sertifika kaldırma etkin değildir. 

## <a name="macos-certificates"></a>macOS sertifikaları

#### <a name="scep-certificates"></a>SCEP sertifikaları

- Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:
  - Bir son kullanıcı kaydını kaldırdığında
  - Yönetici [devre dışı bırakma](devices-wipe.md#retire) eylemini çalıştırdığında
  - Cihaz Azure Active Directory (AD) grubundan kaldırıldığında
  - Sertifika profili Grup ataması kaldırıldı

- Bir SCEP sertifikası şu durumlarda iptal edilir:
  - Yönetici, SCEP profilini değiştirdiğinde veya güncelleştirdiğinde

- SCEP sertifikaları şu durumlarda cihazda **kalır** (iptal edilmez veya kaldırılmaz):
  - Bir son kullanıcı Intune lisansını kaybettiğinde
  - Yönetici Intune lisansını geri aldığında
  - Yönetici, kullanıcıyı veya grubu Azure AD’den kaldırdığında

> [!NOTE]
> macOS cihazlarda fabrika sıfırlaması yapmak için [silme](devices-wipe.md#wipe) eyleminin kullanımı desteklenmez.

#### <a name="pkcs-certificates"></a>PKCS sertifikaları

macOS’da PKCS sertifikaları desteklenmez.

