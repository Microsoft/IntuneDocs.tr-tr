---
title: Cihaz kayıt yöneticisi hesabı kullanarak cihazları kaydetme
titlesuffix: Microsoft Intune
description: Intune'a cihaz kaydetmek için cihaz kayıt yöneticisi hesabını kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: be348840df2e1d7864b0c1c57efbb7abcb698392
ms.sourcegitcommit: 6f2f2fa70f4e47fa5ad2f3c536ba7116e1bd1d05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55199396"
---
# <a name="enroll-devices-in-intune-by-using-a-device-enrollment-manager-account"></a>Bir cihaz kayıt yöneticisi hesabı kullanarak cihazları ıntune'a kaydetme

Bir cihaz kayıt yöneticisi (DEM) hesabı kullanarak tek bir Azure Active Directory hesabıyla 1.000 adede kadar mobil cihaz kaydedebilirsiniz. DEM, bir AAD kullanıcı hesabına uygulanabilen ve kullanıcının 1.000 adede kadar cihaz kaydetmesine imkan veren bir Intune iznidir. DEM hesapları, cihazların kullanıcılarına teslim edilmeden önce kaydedilip hazırlandığı senaryolarda kullanışlıdır.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Bir DEM hesabıyla kaydedilen cihazların kısıtlamaları

DEM kullanıcı hesapları ve bir DEM kullanıcı hesabıyla kaydedilen cihazlarda aşağıdaki kısıtlamalar söz konusudur:

  - Silme işlemi Şirket Portalı’ndan yapılamaz. DEM kullanıcı hesabı tarafından kaydedilen bir cihazı silme işlemi, Azure portalında Intune’dan yapılamaz.
  - Şirket Portalı uygulamasında veya web sitesinde yalnızca yerel cihaz görünür.
  - DEM kullanıcı hesapları, uygulama yönetimi için kullanıcı başına Apple Kimliği gereksinimlerinden dolayı Apple Volume Purchase Program (VPP) uygulamalarını Apple VPP lisanslarıyla kullanamaz.
  - Cihazlar, Apple VPP cihaz lisansına sahipse VPP uygulamalarını yükleyebilir.
  - Cihazların Windows 10 1803 + hariç olmak üzere koşullu erişim engellenir
  - Bir DEM hesabıyla kaydedilen her bir cihaz kendi Intune cihaz lisansı olması gerekir.


## <a name="add-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisi ekleme

1.  [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı** > **Cihaz kayıt yöneticileri**’ni seçin.

2.  **Add (Ekle)** seçeneğini belirleyin.

3.  **Kullanıcı Ekle** dikey penceresinde, DEM kullanıcısı için bir kullanıcı asıl adı girin ve **Ekle**’yi seçin. DEM kullanıcısı, DEM kullanıcıları listesine eklenir.

## <a name="permissions-for-dem"></a>DEM izinleri

Tüm DEM kullanıcılarını görmek amacıyla bir Azure AD kullanıcı hesabına
- DEM izni atamak için Genel Yönetici veya Intune hizmet yöneticisi
- Azure AD rolleri gereklidir

Kullanıcıya Genel Yönetici veya Intune Hizmet Yöneticisi rolü atanmadıysa ancak Cihaz Kayıt Yöneticileri rolü için okuma izinleri etkinleştirildiyse kullanıcı, yalnızca kendi oluşturduğu DEM kullanıcılarını görebilir.


## <a name="remove-device-enrollment-manager-permissions"></a>Cihaz kayıt yöneticisi izinlerini kaldırma

Cihaz kayıt yöneticisinin kaldırılması, kayıtlı cihazları etkilemez.

**Cihaz kayıt yöneticisi kaldırmak için**

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da **Cihaz kaydı**’nı ve ardından **Cihaz kayıt yöneticileri**’ni seçin.
2. **Cihaz kayıt yöneticileri** dikey penceresinde DEM kullanıcısını ve **Sil**’i seçin.

