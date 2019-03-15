---
title: Microsoft Intune ile Zimperium MTD tümleştirme | Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Microsoft Intune ile Zimperium Mobile Threat Defense (MTD) çözümünü kurma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 594482cc5bfae8c165863ff37cd98502922b9bd8
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57397415"
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium'u Intune ile tümleştirme

Zimperium Mobil Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Aşağıdaki adımlar tamamlanmalıdır olan [Zimperium MTD konsolunda](https://sso.zimperium.com/signon/aad/).

Zimperium'u Intune ile tümleştirme sürecini başlatmadan önce aşağıdaki abonelik ve kimlik bilgilerine sahip olduğunuzdan emin olun:

-   Microsoft Intune aboneliği

-   Aşağıdaki izinleri vermek için azure Active Directory genel Yöneticisi Yönetici kimlik bilgileri:

    -   Oturum açma ve kullanıcı profilini okuma

    -   Oturum açmış kullanıcı olarak dizine erişim

    -   Dizin verilerini okuma

    -   Intune’a cihaz bilgilerini gönderme

-   Zimperium MTD konsoluna erişmek için yönetici kimlik bilgileri.

### <a name="zimperium-app-authorization"></a>Zimperium uygulama yetkilendirmesi

Zimperium uygulama yetkilendirme işlemi şöyledir:

-   Intune'a cihaz sistem durumuyla ilgili bilgiler iletmek için Zimperium hizmet izinleri verin. Bu izinleri vermek için genel yönetici kimlik bilgileri kullanmanız gerekir. İzinleri verme tek seferlik bir işlemdir. Genel yönetici kimlik bilgileri, izinlerin verildiği sonra günlük işlem için gerekli değildir.

-   Zimperium, cihazının veritabanını doldurmak için Azure Active Directory (AD) Kayıt Grubu üyeliğini eşitler.

-   Zimperium yönetim konsoluna Azure AD Çoklu Oturum Açma (SSO) kullanımına izin verme.

-   Zimperium uygulamasına Azure AD SSO kullanarak oturum açma izni verme.

Onay ve Azure Active Directory uygulamaları hakkında daha fazla bilgi için bkz. [bir dizin yönetici izinleri istemek](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#request-the-permissions-from-a-directory-admin) Azure Active Directory makaledeki *izinler ve onay Azure Active Directory v2.0 uç noktası*.


## <a name="to-set-up-zimperium-integration"></a>Zimperium tümleştirmesini ayarlamak için

1.  [Zimperium MTD konsolu](https://sso.zimperium.com/signon/aad/)'na gidin ve kimlik bilgilerinizle oturum açın. Zimperium tümleştirme Kurulum işlemi gerçekleştirmek için genel Yönetici rolüne sahip bir Azure Active Directory kullanıcının oturum açması gerekir. Bu tek seferlik Kurulum işlemi, kuruluşunuzda Intune ile iletişim kurmak Zimperium uygulama izni vermek için genel yönetici hakları kullanır. 

2.  Soldaki menüden **Yönetim**'i seçin.

3.  **MDM ayarları** sekmesini seçin.

4.  **MDM Ekle**'yi, sonra **MDM sağlayıcı** listesinden **Microsoft Intune**'u seçin.

5.  MDM hizmeti olarak Microsoft Intune sonra **Microsoft Intune Yapılandırması** penceresi açılır öğesini **Azure Active Directory Ekle** her seçeneği: **Zimperium zConsole**, **Zıps iOS ve Android uygulamaları** Intune ve Azure AD ile Azure AD çoklu oturum açma ile iletişim kurma yetkisi vermek için.

    > [!IMPORTANT]  
    > Zimperium zConsole, Zıps iOS ve Android uygulamalarını Intune ile tümleştirme sürecini tamamlamak için eklemeniz gerekir.

6.  Zimperium uygulamasına Intune ve Azure Active Directory ile iletişim kurma yetkisi vermek için **Kabul Et**'i işaretleyin.

7.  Siz ekledikten sonra **Zimperium zConsole** ve **Zıps iOS ve Android** uygulamaları Azure AD'ye, Azure AD güvenlik gruplarına ekleyin. Bu işlem, Zimperium'un Azure AD güvenlik grubunu kendi hizmetiyle eşitleyebilmesini sağlar.

8.  Yapılandırmayı kaydetmek ve ilk Azure AD güvenlik grubu eşitlemesini başlatmak için **Sonlandır**'ı seçin.

9.  Dışında Zimperium MTD konsolunda oturum açın.

## <a name="next-steps"></a>Sonraki adımlar

-   [Zimperium uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
