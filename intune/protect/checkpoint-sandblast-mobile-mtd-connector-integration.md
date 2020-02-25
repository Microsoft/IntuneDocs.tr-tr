---
title: Denetim noktası SandBlast MTD tümleştirin
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için CheckPoint SandBlast Mobile Threat Defense’i (MTD) Intune ile ayarlama.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f543d38b6688b03126e8fb7d5666c1383b2fc0f
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576488"
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a>Check Point SandBlast’ı Intune ile tümleştirme

Check Point SandBlast Mobile Threat Defense çözümünü Intune ile bütünleştirmek için aşağıdaki adımları izleyin.

> [!NOTE]
> Bu mobil tehdit savunma satıcısı, kayıtlı olmayan cihazlar için desteklenmez.

## <a name="before-you-begin"></a>Başlamadan önce

Bu makaledeki yönergeler [Check Point SandBlast Mobile konsolunda](https://intune-4.eu1.locsec.net/)yapılır. 

Check Point SandBlast’ı Intune ile tümleştirme işlemine başlamadan önce, aşağıdakileri sağladığınızdan emin olun:

- Microsoft Intune aboneliği

- Şu izinleri vermek için Azure Active Directory yönetici kimlik bilgileri:

  - Oturum açma ve kullanıcı profilini okuma

  - Oturum açmış kullanıcı olarak dizine erişim

  - Dizin verilerini okuma

  - Intune’a cihaz bilgilerini gönderme

- Check Point SandBlast Mobile MTD konsoluna erişmek için yönetici kimlik bilgileri.

### <a name="check-point-sandblast-app-authorization"></a>Check Point SandBlast uygulama yetkilendirme

Check Point SandBlast uygulama yetkilendirme işlemi aşağıdaki gibidir:

- Check Point SandBlast Mobile hizmetinin, cihaz sistem durumuyla ilgili bilgileri Intune’a iletmesine izin verin.

- Check Point SandBlast Mobile, cihazının veritabanını doldurmak için Azure AD Kayıt Grubu üyeliğiyle eşitlenir.

- Check Point SandBlast yönetici konsolunun, Azure AD Çoklu Oturum Açma (SSO) özelliğini kullanmasına izin verin.

- Check Point SandBlast yönetici konsolunun, Azure AD SSO ile oturum açmasına izin verin.

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a>Check Point SandBlast Mobile tümleştirmesini ayarlamak için

1. [Check Point SandBlast Mobile MTD konsoluna](https://intune-4.eu1.locsec.net/) gidin ve kimlik bilgilerinizle oturum açın.

2. **Ayarlar** sekmesine tıklayın.

3. **Cihaz yönetimi**’ni ve **Ayarlar**’ı seçin.

4. Açılan **MDM Hizmeti** listesinden **Microsoft Intune**’u seçin.

5. MDM hizmeti olarak Microsoft Intune ayarladıktan sonra, **Microsoft Intune yapılandırma** penceresi açılır ve Intune ve Azure AD ile iletişim kurmak üzere Check Point SandBlast Mobile 'ı yetkilendirmek için, her cihaz platformu için **kuruluşuma Ekle** ' yi seçin: iOS/ıpados, Android ve Windows.

    ![Check Point MTD Intune yapılandırmasını gösteren resim](./media/checkpoint-sandblast-mobile-mtd-connector-integration/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > Bir sonraki adıma ilerlemek için tüm cihaz platformlarını eklemeniz gerekir.

6. Check Point SandBlast Mobile uygulamasının Intune ile Azure Active Directory aracılığıyla iletişim kurmasına izin vermek için **Kabul et**’i seçin.

7. Tüm cihaz platformlarını etkinleştirdikten sonra Azure AD güvenlik grubunu girmeniz gerekir.

8. **Doğrula**’yı seçin, Azure Ad güvenlik grubu başarıyla doğrulandığında ise **Kaydet**’e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

- [Denetim Noktası SandBlast Mobil uygulamaları ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
