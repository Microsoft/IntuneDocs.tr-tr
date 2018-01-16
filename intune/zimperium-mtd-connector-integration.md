---
title: "Zimperium'u Intune ile tümleştirme"
titleSuffix: Intune on Azure
description: "Intune'u Zimperium ile tümleştirme"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 515f99f694a9125d60bb9210becc6722bfb9e24f
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/30/2017
---
# <a name="integrate-zimperium-with-intune"></a>Zimperium'u Intune ile tümleştirme

Zimperium Mobil Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Aşağıdaki adımların [Zimperium MTD konsolunda](https://staging2-console.zimperium.com) tamamlanması gerekir.

Zimperium'u Intune ile tümleştirme sürecini başlatmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

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

-   Cihazının veritabanını doldurmak için Zimperium'un Azure AD Kayıt Grubu üyeliğiyle eşitlenmesi.

-   Zimperium yönetim konsoluna Azure AD Çoklu Oturum Açma (SSO) kullanımına izin verme.

-   Zimperium uygulamasına Azure AD SSO kullanarak oturum açma izni verme.

## <a name="to-set-up-zimperium-integration"></a>Zimperium tümleştirmesini ayarlamak için

1.  [Zimperium MTD konsolu](https://staging2-console.zimperium.com)'na gidin ve kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **Yönetim**'i seçin.

3.  **MDM ayarları** sekmesini seçin.

4.  **MDM Ekle**'yi, sonra **MDM sağlayıcı** listesinden **Microsoft Intune**'u seçin.

5.  MDM hizmeti olarak Microsoft Intune belirlendikten sonra, **Microsoft Intune Yapılandırması** penceresi açılır; burada, Zimperium'a Intune ve Azure AD Çoklu Oturum Açma ile iletişim kurma yetkisi vermek için **Zimperium zConsole**, **zIPS iOS ve Android uygulamaları** seçeneklerinde **Azure Active Directory Ekle**'yi işaretleyin.

    > [!IMPORTANT]
    > Intune ile tümleştirme sürecini tamamlamak için Zimperium zConsole, zIPS iOS ve Android uygulamalarını eklemelisiniz.

6.  Zimperium uygulamasına Intune ve Azure Active Directory ile iletişim kurma yetkisi vermek için **Kabul Et**'i işaretleyin.

7.  **Zimperium zConsole** ve **zIPS iOS ve Android** uygulamaları Azure AD'ye eklendikten sonra Zimperium'un Azure AD güvenlik grubunu kendi hizmetiyle eşitleyebilmesi için Azure AD güvenlik gruplarını ekleyin.

8.  Yapılandırmayı kaydetmek ve ilk Azure AD güvenlik grubu eşitlemesini başlatmak için **Sonlandır**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

-   [Zimperium uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
