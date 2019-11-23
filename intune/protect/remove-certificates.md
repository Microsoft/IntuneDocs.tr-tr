---
title: Microsoft Intune - Azure’da SCEP ve PKCS sertifikalarını kaldırma | Microsoft Docs
titleSuffix: ''
description: Yöneticiler, Microsoft Intune’dan sertifika kaldırmak için silme veya devre dışı bırakma eylemlerini kullanabilirler. Bir cihaz kaydının silinmesi veya bir uyumluluk ilkesinin kaldırılması gibi, sertifikaların otomatik olarak kaldırıldığı bazı senaryolar da vardır. Intune lisansının kaybolması veya kaldırılması gibi, sertifikaların otomatik olarak cihazda kaldığı bazı senaryolar da vardır. Android, Android Kurumsal, iOS, macOS ve Windows cihazlara yönelik farklı yöntemlere göz atın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: lacranda
ms.openlocfilehash: dbf6d95c8902a95993b972ff7639d4afb4324ac8
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410167"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Microsoft Intune’da SCEP ve PKCS sertifikalarını kaldırma

In Microsoft Intune, you can use Simple Certificate Enrollment Protocol (SCEP) and Public Key Cryptography Standards (PKCS) certificate profiles to add certificates to devices.

These certificates can be removed when you [wipe](../remote-actions/devices-wipe.md#wipe) or [retire](../remote-actions/devices-wipe.md#retire) the device. There are also scenarios where certificates are automatically removed, and scenarios where certificates stay on the device. Bu makalede bazı yaygın senaryolar ve bu senaryoların PKCS ve SCEP sertifikaları üzerindeki etkisi listelenmiştir.

> [!NOTE]
> To remove and revoke certificates for a user who's being removed from on-premises Active Directory or Azure Active Directory (Azure AD), follow these steps in order:
>
> 1. Wipe or retire the user's device.
> 2. Remove the user from on-premises Active Directory or Azure AD.

## <a name="manually-deleted-certificates"></a>Manually deleted certificates

Manual deletion of a certificate is a scenario that applies across platforms and certificates provisioned by SCEP or PKCS certificate profiles. For example, a user might delete a certificate from a device, when the device remains targeted by a certificate policy.

In this scenario, after the certificate is deleted, the next time the device checks in with Intune it's found to be out of compliance as it is missing the expected certificate. Intune then issues a new certificate to restore the device to compliance. No additional action is needed to restore the certificate.

## <a name="windows-devices"></a>Windows cihazları

### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.
- The device is removed from an Azure AD group.
- A certificate profile is removed from the group assignment.

Bir SCEP sertifikası şu durumlarda iptal edilir:

- An administrator changes or updates the SCEP profile.

A root certificate is removed when:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

SCEP certificates *stay* on the device (certificates aren't revoked or removed) when:

- A user loses the Intune license.
- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.

### <a name="pkcs-certificates"></a>PKCS sertifikaları

Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

A root certificate is removed when:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

PKCS certificates *stay* on the device (certificates aren't revoked or removed) when:

- A user loses the Intune license.
- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.
- An administrator changes or updates the PKCS profile.
- A certificate profile is removed from the group assignment.


## <a name="ios-devices"></a>iOS devices

### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.
- The device is removed from the Azure AD group.
- A certificate profile is removed from the group assignment.

Bir SCEP sertifikası şu durumlarda iptal edilir:

- An administrator changes or updates the SCEP profile.

A root certificate is removed when:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

SCEP certificates *stay* on the device (certificates aren't revoked or removed) when:

- A user loses the Intune license.
- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.

### <a name="pkcs-certificates"></a>PKCS sertifikaları

Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

Bir PKCS sertifikası şu durumlarda kaldırılır:

- A certificate profile is removed from the group assignment.

A root certificate is removed when:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

PKCS certificates *stay* on the device (certificates aren't revoked or removed) when:

- A user loses the Intune license.
- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.
- An administrator changes or updates the PKCS profile.

## <a name="android-knox-devices"></a>Android KNOX cihazları

### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.

Bir SCEP sertifikası şu durumlarda iptal edilir:

- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.
- The device is removed from an Azure AD group.
- A certificate profile is removed from the group assignment.
- An administrator removes the user or group from Azure AD.
- An administrator changes or updates the SCEP profile.

A root certificate is removed when:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

SCEP certificates *stay* on the device (certificates aren't revoked or removed) when:

- A user loses the Intune license.
- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.

### <a name="pkcs-certificates"></a>PKCS sertifikaları

Bir PKCS sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

A root certificate is removed when:

- A user unenrolls.
- An administrator runs the [wipe](../remote-actions/devices-wipe.md#wipe) action.
- An administrator runs the [retire](../remote-actions/devices-wipe.md#retire) action.

PKCS certificates *stay* on the device (certificates aren't revoked or removed) when:
- A user loses the Intune license.

- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.
- An administrator changes or updates the PKCS profile.
- A certificate profile is removed from the group assignment.


> [!NOTE]
> Android for Work devices are not validated for the preceding scenarios.
> Android legacy devices (any non-Samsung, non-work profile devices) are not enabled for certificate removal.

## <a name="macos-certificates"></a>macOS sertifikaları

### <a name="scep-certificates"></a>SCEP sertifikaları

Bir SCEP sertifikası şu durumlarda iptal edilir *ve* kaldırılır:

- A user unenrolls.
- An administrator runs a [retire](../remote-actions/devices-wipe.md#retire) action.
- The device is removed from an Azure AD group.
- A certificate profile is removed from the group assignment.

Bir SCEP sertifikası şu durumlarda iptal edilir:

- An administrator changes or updates the SCEP profile.

SCEP certificates *stay* on the device (certificates aren't revoked or removed) when:

- A user loses the Intune license.
- An administrator withdraws the Intune license.
- An administrator removes the user or group from Azure AD.

> [!NOTE]
> macOS cihazlarda fabrika sıfırlaması yapmak için [silme](../remote-actions/devices-wipe.md#wipe) eyleminin kullanımı desteklenmez.

### <a name="pkcs-certificates"></a>PKCS sertifikaları

PKCS certificates aren't supported on macOS.

## <a name="next-steps"></a>Sonraki adımlar

[Use certificates for authentication](certificates-configure.md)