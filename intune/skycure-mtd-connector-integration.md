---
title: "Intune ile Skycure tümleştirmesini kurma"
titleSuffix: Intune Azure preview
description: "Microsoft Intune ile Skycure tümleştirmesini kurun."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3d21f440ee6806b545d2b346559d6516993a9cbf
ms.openlocfilehash: 7740f9748e2d3ece6223fddc0bdf0ba6ee897cad
ms.contentlocale: tr-tr
ms.lasthandoff: 06/14/2017


---

# <a name="set-up-the-skycure-integration-with-intune"></a>Intune ile Skycure tümleştirmesini kurma

Çoklu Oturum Açma özelliklerini kullanabilmek için Azure AD’ye Skycure uygulamalarını eklemelisiniz.

## <a name="before-you-begin"></a>Başlamadan önce

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Intune ile Skycure’u tümleştirmek için kullanılan Azure AD hesabı

-   Skycure Temel kurulum işlemine başlamadan önce, [Skycure Yönetim konsolunda](https://aad.skycure.com) Azure AD hesabınızın düzgün yapılandırıldığından emin olun.

### <a name="full-integration-vs-read-only"></a>Tam tümleştirme - Salt okunur

Skycure, Intune ile iki tümleştirme modunu destekler:

-   **Salt okunur tümleştirme (Temel kurulum):** Yalnızca Azure Active Directory’den cihazların envanterini çıkarır ve Skycure konsolunu bunlarla doldurur.
<br>
    -   Skycure Yönetim konsolunda **Cihazların durumunu ve riskini Intune’a raporla** ve **Güvenlik olaylarını da Intune’a raporla** kutuları seçili değilse tümleştirme salt okunur moddadır ve dolayısıyla Intune’da cihazların durumunu (uyumlu veya uyumsuz) asla değiştirmez.
<br></br>
-   **Tam tümleştirme:** Skycure’un riskli cihazları ve güvenlik olayı ayrıntılarını Intune’a raporlamasına olanak tanır; bu da, iki bulut hizmeti arasında çift yönlü bir iletişim oluşturur.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Skycure uygulamaları Azure AD ve Intune’la birlikte nasıl kullanılır?

-   **iOS uygulaması:** Son kullanıcıların iOS uygulaması kullanarak Azure AD’de oturum açmasına olanak tanır.

-   **Android uygulaması:** Son kullanıcıların Android uygulaması kullanarak Azure AD’de oturum açmasına olanak tanır.

-   **Yönetim uygulaması:** Bu, Intune ile hizmetler arası iletişime olanak tanıyan Skycure Azure AD çok kiracılı uygulamasıdır.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Intune ile Skycure arasında salt okunur tümleştirme ayarlamak için

> [!IMPORTANT]
> Skycure yönetici kimlik bilgileri, Azure Active Directory’de geçerli bir kullanıcıya ait olması gereken bir e-postadır; böyle olmazsa, oturum açılamaz. Skycure, Çoklu Oturum Açma (SSO) kullanarak yöneticisinin kimliğini doğrulamak için Azure Active Directory kullanır.

1.  [Skycure Yönetim Konsolu](https://aad.skycure.com)’na gidin.

2.  **Skycure yönetici kimlik bilgilerinizi** girin ve **Devam**’a tıklayın.

3.  **Ayarlar**’a gidin, **Intune Tümleştirmesi**’nin altında **Temel Kurulum**’u seçin.

4.  **iOS Uygulaması** etiketinde **Active Directory’ye Ekle**’ye tıklayın.

    ![Skycure Yönetim konsolunda iOS uygulaması](./media/skycure-setup-1.png)

5.  Oturum açma sayfası açılır; Intune kimlik bilgilerinizi girin ve **Kabul Et**’e tıklayın.

    ![iOS uygulaması Intune oturum açma istemi](./media/skycure-setup-2.png)

6.  Uygulama Azure AD’ye eklendikten sonra, Skycure Yönetim konsolunda uygulamanın Azure AD’ye başarıyla eklendiğine ilişkin bir gösterge görebilirsiniz.

    ![iOS uygulaması tamamlanma ekranı](./media/skycure-setup-3.png)

> [!NOTE]
> **Skycure Android** ve **Yönetim** uygulamaları için de ayrı işlemi yineleyin.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Skycure’a Azure AD Güvenlik grubu ekleme

Skycure çalıştıran tüm cihazları yer aldığı Azure AD güvenlik grubunu eklemelisiniz.

1.  Skycure çalıştıran cihazların tüm güvenlik gruplarını girin ve seçin, ardından **Değişiklikleri uygula**’ya tıklayın.

    ![Skycure Yönetim konsolu güvenlik grubunu yapılandırma](./media/skycure-setup-4.png)

Skycure, Mobile Threat Defense hizmetini çalıştıran cihazları Azure AD güvenlik gruplarıyla eşitler.

![Skycure yönetim konsolunda güvenlik grubu yapılandırması tamamlandı](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Intune ile Skycure arasında tam tümleştirmeyi ayarlama

1.  [Skycure Yönetim Konsolu](https://aad.skycure.com)’na gidin.

2.  **Skycure yönetici kimlik bilgilerinizi** girin ve **Devam**’a tıklayın.

3.  **Ayarlar**’a gidin, **Intune Tümleştirmesi**’nin altında **Tam Tümleştirme**’yi seçin.

4.  Aşağıdaki ayarları denetleyin:

    a.  Cihazların durumunu ve riskini Intune’a raporla

    b.  Güvenlik olaylarını da Intune'a raporla

5.  **Değişiklikleri uygula**’ya tıklayın.

    ![Skycure tam tümleştirmesi tamamlandı](./media/skycure-setup-6.png)

## <a name="next-steps"></a>Sonraki adımlar

[Intune’da Skycure Mobile Threat Defense’i etkinleştirme](skycure-mtd-connector-enable.md)

