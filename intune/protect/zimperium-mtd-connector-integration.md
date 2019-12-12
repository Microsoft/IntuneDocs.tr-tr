---
title: Zimperium MTD’yi Microsoft Intune ile tümleştirme
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Microsoft Intune ile Zimperium Mobile Threat Defense (MTD) çözümünü kurma.
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
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d843cf707cf182655d0044dde289caca730ccd6b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72810306"
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium'u Intune ile tümleştirme

Zimperium Mobil Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.

## <a name="before-you-begin"></a>Başlamadan önce

Aşağıdaki adımlar [zmıium MTD konsolunda](https://www.zimperium.com/platform) yapılır ve hem Intune 'a kayıtlı cihazlar (cihaz uyumluluğu kullanılarak) hem de kayıtlı olmayan cihazlar (uygulama koruma ilkeleri kullanılarak) Için Gevvizğun hizmetine bir bağlantı sağlar.

Zimperium'u Intune ile tümleştirme sürecini başlatmadan önce aşağıdaki abonelik ve kimlik bilgilerine sahip olduğunuzdan emin olun:

- Microsoft Intune aboneliği

- Aşağıdaki izinleri vermek için genel yönetici Yöneticisi kimlik bilgilerini Azure Active Directory:

  - Oturum açma ve kullanıcı profilini okuma

  - Oturum açmış kullanıcı olarak dizine erişim

  - Dizin verilerini okuma

  - Intune’a cihaz bilgilerini gönderme

- Zimperium MTD konsoluna erişmek için yönetici kimlik bilgileri.

### <a name="zimperium-app-authorization"></a>Zimperium uygulama yetkilendirmesi

Zimperium uygulama yetkilendirme işlemi şöyledir:

- Cihaz sistem durumu ile ilgili bilgileri Intune 'a geri bildirmek için Zlaium hizmeti izinleri verin. Bu izinleri vermek için genel yönetici kimlik bilgilerini kullanmanız gerekir. İzin verilmesi tek seferlik bir işlemdir. İzinler verildikten sonra, günlük işlem için genel yönetici kimlik bilgileri gerekli değildir.

- Zimperium, cihazının veritabanını doldurmak için Azure Active Directory (AD) Kayıt Grubu üyeliğini eşitler.

- Zimperium yönetim konsoluna Azure AD Çoklu Oturum Açma (SSO) kullanımına izin verme.

- Zimperium uygulamasına Azure AD SSO kullanarak oturum açma izni verme.

İzin ve Azure Active Directory uygulamalar hakkında daha fazla bilgi için, *Azure Active Directory v 2.0 uç noktasındaki Azure Active Directory makale izinleri ve onayı*içindeki [Dizin yöneticisinden izinleri isteme](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) konusuna bakın.


## <a name="to-set-up-zimperium-integration"></a>Zimperium tümleştirmesini ayarlamak için

1. [Zimperium MTD konsolu](https://www.zimperium.com/platform)'na gidin ve kimlik bilgilerinizle oturum açın. Zkusuren IUM tümleştirme kurulum işlemini gerçekleştirmek için, genel yönetici rolüne sahip bir Azure Active Directory kullanıcıyla oturum açmanız gerekir. Bu tek seferlik kurulum işlemi, kuruluşunuzda, Zkusuren IUM uygulamalarının Intune ile iletişim kurması için izin vermek üzere genel yönetici haklarını kullanır. 

2. Soldaki menüden **Yönetim**'i seçin.

3. **MDM ayarları** sekmesini seçin.

4. **MDM Ekle**'yi, sonra **MDM sağlayıcı** listesinden **Microsoft Intune**'u seçin.

5. MDM hizmeti olarak Microsoft Intune belirlendikten sonra, **Microsoft Intune Yapılandırması** penceresi açılır; burada, Zimperium'a Intune ve Azure AD Çoklu Oturum Açma ile iletişim kurma yetkisi vermek için **Zimperium zConsole**, **zIPS iOS ve Android uygulamaları** seçeneklerinde **Azure Active Directory Ekle**'yi işaretleyin.

    > [!IMPORTANT]  
    > Intune ile tümleştirme işlemini gerçekleştirmek için Zıium zConsole, ZIP iOS ve Android uygulamalarını eklemeniz gerekir.

6. Zimperium uygulamasına Intune ve Azure Active Directory ile iletişim kurma yetkisi vermek için **Kabul Et**'i işaretleyin.

7. **Zıium zConsole** ve **ZIP iOS ve ANDROID** uygulamalarını Azure AD 'ye ekledikten sonra Azure AD güvenlik gruplarını ekleyin. Bu işlem, Zimperium'un Azure AD güvenlik grubunu kendi hizmetiyle eşitleyebilmesini sağlar.

8. Yapılandırmayı kaydetmek ve ilk Azure AD güvenlik grubu eşitlemesini başlatmak için **Sonlandır**'ı seçin.

9. Zmıium MTD konsolunun oturumunu kapatın.

## <a name="next-steps"></a>Sonraki adımlar

- [Kayıtlı cihazlar için Zkusuri uygulamalar ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Kayıtlı olmayan cihazlar için Zlaium uygulamalar ayarlama](~/protect/mtd-add-apps-unenrolled-devices.md)
