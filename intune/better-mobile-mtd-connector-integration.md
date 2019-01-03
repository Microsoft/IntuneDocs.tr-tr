---
title: Intune ile Better Mobile tümleştirmesini ayarlama
titleSuffix: Intune on Azure
description: Intune ile Better Mobile bağlayıcısı tümleştirmesi
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.openlocfilehash: 761605a74e6aeda65d9c6361b18b51e255873ac1
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816540"
---
# <a name="integrate-better-mobile-with-intune"></a>Better Mobile'ı Intune ile tümleştirme

Better Mobile Threat Defense çözümünü Intune ile tümleştirmek için aşağıdaki adımları tamamlayın.

## <a name="before-you-begin"></a>Başlamadan önce

> [!NOTE]
> Aşağıdaki adımların [Better Mobile yönetim konsolunda](https://aad.bmobi.net) tamamlanması gerekir.

Better Mobile'ı Intune ile tümleştirme sürecini başlatmadan önce aşağıdakilere sahip olduğunuzdan emin olun:

-   Microsoft Intune aboneliği

-   Şu izinleri vermek için Azure Active Directory yönetici kimlik bilgileri:

    -   Oturum açma ve kullanıcı profilini okuma

    -   Oturum açmış kullanıcı olarak dizine erişim

    -   Dizin verilerini okuma

    -   Intune’a cihaz bilgilerini gönderme

-   Better Mobile yönetim konsoluna erişmek için yönetici kimlik bilgileri.

### <a name="better-mobile-app-authorization"></a>Better Mobile uygulama yetkilendirmesi

Better Mobile uygulama yetkilendirme işlemi şu şekildedir:

-   Better Mobile hizmetine Intune'a cihazın sistem durumuyla ilgili bilgi iletme izni verme.

-   Cihazının veritabanını doldurmak için Better Mobile'ı Azure AD Kayıt Grubu üyeliğiyle eşitleme.

-   Better Mobile yönetim konsolunun Azure AD Çoklu Oturum Açma (SSO) kullanmasına izin verme.

-   Better Mobile uygulamasının Azure AD SSO kullanarak oturum açmasına izin verme.

## <a name="to-set-up-better-mobile-integration"></a>Better Mobile tümleştirmesini ayarlamak için

1. [Better Mobile yönetim konsoluna](https://aad.bmobi.net) gidin ve kimlik bilgilerinizle oturum açın.
2. **Integration** > **EMM/MDM** > **ADD ACCOUNT** öğesini seçin.

     ![Daha iyi mobil Yönetim konsolunun resmi](media/better_mobile_console.png)
 
3. **Intune**'u seçin.
4. **ACCOUNT NAME** alanının yanına bir tanımlayıcı yazın. 
5. **Microsoft Oturum Açma** penceresinde Intune kimlik bilgilerinizi girin.
6. **İstenen izinler** penceresinde **Kabul Et**'i seçin.
7. Better Mobile'ın cihazları hangi Azure AD Güvenlik gruplarından eşitlemesini istiyorsanız, o gruplar için arama yapın ve listeden bunları seçin. Sonra **Devam**'ı seçin.
8. **Done** (Bitti) öğesini seçin.
9. **Hesap ekle** sayfası yeniden görüntülenir. Sayfayı kapatın. 

## <a name="next-steps"></a>Sonraki adımlar

-   [Daha İyi İstemci Uygulamaları Kurma](mtd-apps-ios-app-configuration-policy-add-assign.md)