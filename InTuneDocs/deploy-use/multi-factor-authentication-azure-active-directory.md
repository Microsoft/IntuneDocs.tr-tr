---
title: "Intune cihaz kaydı için çok faktörlü kimlik doğrulaması | Microsoft Docs"
description: "Azure AD’de cihaz kaydı için çok faktörlü kimlik doğrulaması isteme."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 7768013a1cc764b6dfbf4b7d22be4f5cf95f50bf
ms.openlocfilehash: dba070ef76de8015b347e760b424a5e28ce6ddec
ms.lasthandoff: 02/18/2017


---

# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Intune cihaz kayıtları için çok faktörlü kimlik doğrulaması

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak üzere cihaz kaydı için Azure AD Multi-Factor Authentication (MFA) özelliğini tümleştirir.

MFA, aşağıdaki doğrulama yöntemlerinden herhangi ikisini veya daha fazlasını zorunlu tutar: 

- Bildiğiniz bir şey (genellikle parola veya PIN).
- Sahip olduğunu bir şey (telefon gibi kopyalaması kolay olmayan güvenilir bir cihaz).
- Kendinizde bulunan bir şey (biyometri).

MFA; iOS, Android, Windows 8.1 veya üstü, Windows Phone 8.1 veya üstü cihazlar için desteklenir.

> [!NOTE]
> Configuration Manager’ın eski sürümlerinde (1610 sürümü öncesi), Configuration Manager Yönetici konsolunda MFA ayarını görmeye devam edersiniz. Configuration Manager yönetici konsolunda MFA'yı yapılandırmak işe yaramaz; bu yüzden bunu denemeyin. MFA’yı bu konuda açıklandığı şekilde yapılandırın.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune'u cihaz kaydında çok faktörlü kimlik doğrulama isteyecek şekilde yapılandırma
Bir cihaz kaydedildiğinde MFA istemek için şu adımları izleyin:

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

