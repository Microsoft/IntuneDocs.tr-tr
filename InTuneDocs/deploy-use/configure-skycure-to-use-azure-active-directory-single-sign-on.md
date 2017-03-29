---
title: "Skycure’u Azure Active Directory Çoklu Oturum Açma kullanacak şekilde yapılandırma | Microsoft Docs"
description: "Skycure’u Azure Active Directory Çoklu Oturum Açma (SSO) kullanacak şekilde yapılandırma"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 228cecad4dc459e18d10e95253118943197bc55d
ms.lasthandoff: 03/22/2017


---

# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Skycure’u Azure Active Directory Çoklu Oturum Açma (SSO) kullanacak şekilde yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune’u Skycure ile tümleştirdiğinizde, Azure AD SSO kullanılır. Başlıca avantajları şunlardır:

-   **Yöneticiler**, Microsoft portallarında (Intune, Azure) ve Skycure Yönetim konsolundaki her oturum açma ve kapatma işleminde yeniden yazmak zorunda kalmadan aynı kimlik bilgilerini kullanabilir.

-   **Son kullanıcılar**, Skycure uygulamalarındaki her oturum açma ve kapatma işleminde yeniden yazmak zorunda kalmadan aynı Azure AD kimlik bilgilerini kullanabilir.

Aşağıda, Skycure’u Azure Active Directory Çoklu Oturum Açma (SSO) ile tümleştirme adımları verilmiştir.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Azure Active Directory Kiracı Kimliğini almak için

Azure AD Kiracı Kimliğini almanız gerekir.

1.  [Azure portalına](https://portal.azure.com/) gidin ve kimlik bilgilerinizle oturum açın.

2.  **Pano**’yu görebilirsiniz, **Azure Active Directory**’yi seçin.

![Azure AD Panosu](../media/mtp/skycure-sso-1.png)

1.  **Azure Active Directory** dikey penceresi açılır, **Özellikler**’i seçin.

![Azure AD Özellikler dikey penceresi](../media/mtp/skycure-sso-2.png)

1.  **Azure Active Directory Özellikler** dikey penceresindeki **Kiracı Dizin Kimliği**’nin altında **Kopyala simgesine** tıklayın.

> Kopyalanan Dizin Kimliği değerini daha sonra kullanmak üzere bir metin dosyasına yapıştırın. Dizin Kimliği değeri, daha sonra Skycure ile Intune’u tümleştirme işleminde gerekecektir.

![Azure AD Panosu](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Skycure’un Azure Active Directory ile iletişim kurmasını sağlama

1.  Aşağıdaki URL’yi tarayıcınıza girin. **DIRECTORY_ID** değeri yerine, daha önce metin dosyasına kopyalamış olduğunuz Azure Active Directory Kiracı Kimliğinizi girin.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Azure Active Directory kimlik bilgilerinizi kullanarak oturum açmalısınız. Devam etmek için **Kabul Et**’e tıklayın.

![Azure AD oturum açma sayfası](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Skycure için Azure AD Güvenlik grubu oluşturma (isteğe bağlı)

Skycure çalıştıran kullanıcıları içeren özel bir kullanıcı grubu oluşturmak isteyebilirsiniz (örneğin, Skycure kullanıcıları). Raporlar aracılığıyla Skycure etkinliğini çözümlerken bu yararlı olabilir.

-   [Azure AD’de grup oluşturma ve üyeleri ekleme](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) hakkında daha fazla bilgi edinin.

> [!NOTE] 
> Ayrıca, var olan bir Azure AD güvenlik grubunu da kullanabilirsiniz.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Intune’u Skycure ile tümleştirmek için Azure AD hesabını yapılandırma

1.  [Skycure Yönetim Konsolu](https://aad.skycure.com/)’nda, daha önce metin dosyasına kaydedilmiş olan Azure Active Directory Kiracı Kimliğini girin.

![Skycure Yönetim konsolu Azure AD Kiracı Kimliği alanı](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> Skycure, Azure AD’yi sorgulayarak Azure AD Kiracı Kimliğinin mevcut olduğunu doğrular; Skycure kimliği bulduğunda, yönetici sonraki adıma (Temel kurulum adımı) devam edebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Skycure iOS uygulaması yapılandırma ilkesini indirme](https://docs.microsoft.com/intune/deploy-use/download-skycure-ios-app-configuration-policy)

