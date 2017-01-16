---
title: "Azure AD kullanarak çok faktörlü kimlik doğrulaması | Microsoft Docs"
description: "Azure AD’de cihaz kaydı için çok faktörlü kimlik doğrulaması isteme."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
translationtype: Human Translation
ms.sourcegitcommit: 85462d6cb5e3dc6ce8e94fe8fd1bc1c1c2b6e4f3
ms.openlocfilehash: 6e20eca60886781ae884107a224245639c5f107c


---

# <a name="multi-factor-authentication-for-microsoft-intune"></a>Microsoft Intune için Multi-Factor Authentication

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak üzere cihaz kaydı için Azure AD Multi-Factor Authentication (MFA) özelliğini tümleştirir. MFA, kullanıcı adları ve parolaların yanı sıra metin kimlik doğrulaması gibi kimlik doğrulama faktörleri de gerektirir. Bu, iOS, Android, Windows 8.1 veya üstü, Windows Phone 8.1 veya üstü cihazlar için desteklenir.

> [!NOTE]
>
> Bu, Intune’daki yeni MFA deneyimidir. Müşterilerin geçiş yaptığı eski deneyim [Windows cihazlarını çok faktörlü kimlik doğrulaması ile koruma](protect-windows-devices-with-multi-factor-authentication.md) kısmında açıklanır.
>
> Configuration Manager’ın eski sürümlerinde (1610 sürümü öncesi), Configuration Manager Yönetici konsolunda MFA ayarını görmeye devam edersiniz. Configuration Manager yönetici konsolunda MFA'yı yapılandırmak işe yaramaz; bu yüzden bunu denemeyin. MFA’yı bu konuda açıklandığı şekilde yapılandırın.

### <a name="configuring-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune’u cihaz kaydında çok faktörlü kimlik doğrulama isteyecek şekilde yapılandırma
Cihaz kaydı sırasında MFA istemek için şu adımları izleyin:

1. Yönetici kimlik bilgilerinizle [Microsoft Azure portalında](https://manage.windowsazure.com) oturum açın.
2. Kiracınızı seçin.
2. **Uygulamalar** sekmesini seçin. Azure AD güvenlik özelliklerini yapılandırabileceğiniz hizmetlerin listesini görürsünüz.
3. **Microsoft Intune kaydı**’nı seçin.
4. **Yapılandır**’ı seçin. 
5. **Çok faktörlü kimlik doğrulaması ve konum tabanlı erişim kuralları** altında şunları yapabilirsiniz:
    
    -  Erişim kurallarını etkinleştirme
    -  Kuralların tüm kullanıcılar için mi yoksa belirli Azure AD güvenlik grupları için mi geçerli olacağını seçme.
    -  Tüm cihazların kaydı için çok faktörlü kimlik doğrulaması isteme.
    -  Cihaz iş yerinde olmadığında kayıt için çok faktörlü kimlik doğrulaması isteme.
    -  Bir cihaz şirket ağına bağlı olmadığında o cihazın kaydolmasını engellemek için **Şirket kaynaklarına erişimi engelle** seçeneğini belirleyin. 
4. Cihaz kaydı için ağ bağlantısı gereksinimlerini yapılandırmak için **iş ağı konumunuzu tanımlama/düzenleme** bağlantısına da tıklayabilirsiniz.

> [!IMPORTANT]
> 
> Microsoft Intune Kaydı için **Cihaz tabanlı erişim kuralları** yapılandırmayın.



<!--HONumber=Dec16_HO3-->


