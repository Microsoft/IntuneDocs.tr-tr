---
title: Zimperium MTD’yi Microsoft Intune ile tümleştirme
titleSuffix: ''
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Microsoft Intune ile Zimperium Mobile Threat Defense (MTD) çözümünü kurma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 68896a363cab37aabe9a597872da0fe75c44c473
ms.sourcegitcommit: 3903f20cb5686532ccd8c36aa43c5150cee7cca2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2018
ms.locfileid: "52267246"
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium'u Intune ile tümleştirme

Zimperium Mobil Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Aşağıdaki adımlar tamamlanmalıdır olan [Zimperium MTD konsolunda](https://sso.zimperium.com/signon/aad/).

Zimperium'u Intune ile tümleştirme sürecini başlatmadan önce aşağıdaki abonelik ve kimlik bilgilerine sahip olduğunuzdan emin olun:

-   Microsoft Intune aboneliği

-   Şu izinleri vermek için Azure Active Directory yönetici kimlik bilgileri:

    -   Oturum açma ve kullanıcı profilini okuma

    -   Oturum açmış kullanıcı olarak dizine erişim

    -   Dizin verilerini okuma

    -   Intune’a cihaz bilgilerini gönderme

-   Zimperium MTD konsoluna erişmek için yönetici kimlik bilgileri.

### <a name="zimperium-app-authorization"></a>Zimperium uygulama yetkilendirmesi

Zimperium uygulama yetkilendirme işlemi şöyledir:

-   Zimperium hizmetine Intune'a cihazın sistem durumuyla ilgili bilgi iletme izni verme.

-   Zimperium, cihazının veritabanını doldurmak için Azure Active Directory (AD) Kayıt Grubu üyeliğini eşitler.

-   Zimperium yönetim konsoluna Azure AD Çoklu Oturum Açma (SSO) kullanımına izin verme.

-   Zimperium uygulamasına Azure AD SSO kullanarak oturum açma izni verme.

## <a name="to-set-up-zimperium-integration"></a>Zimperium tümleştirmesini ayarlamak için

1.  Git [Zimperium MTD konsolunda](https://sso.zimperium.com/signon/aad/) ve kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **Yönetim**'i seçin.

3.  Seçin **MDM ayarları** sekmesi.

4.  **MDM Ekle**'yi, sonra **MDM sağlayıcı** listesinden **Microsoft Intune**'u seçin.

5.  MDM hizmeti olarak Microsoft Intune sonra **Microsoft Intune Yapılandırması** penceresi açılır öğesini **Azure Active Directory Ekle** her seçeneği:  **Zimperium zConsole**, **Zıps iOS ve Android uygulamaları** Intune ve Azure AD ile Azure AD çoklu oturum açma ile iletişim kurma yetkisi vermek için.

    > [!IMPORTANT]
    > Intune ile tümleştirme sürecini tamamlamak için Zimperium zConsole, zIPS iOS ve Android uygulamalarını eklemelisiniz.

6.  Seçin **kabul** Zimperium uygulamasına Intune ve Azure Active Directory ile iletişim kurma yetkisi vermek için.

7.  **Zimperium zConsole** ve **zIPS iOS ve Android** uygulamaları, Azure AD'ye eklendikten sonra Azure AD güvenlik gruplarını ekleyin. Bu işlem, Zimperium'un Azure AD güvenlik grubunu kendi hizmetiyle eşitleyebilmesini sağlar.

8.  Seçin **son** yapılandırmasını kaydetmek ve İlk Azure AD güvenlik grubu eşitlemesini başlatmak için.

## <a name="next-steps"></a>Sonraki adımlar

-   [Zimperium uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
