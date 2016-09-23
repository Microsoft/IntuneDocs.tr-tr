---
title: "Azure AD kullanarak çok faktörlü kimlik doğrulaması | Microsoft Intune"
description: "Azure AD’de cihaz kaydı için çok faktörlü kimlik doğrulaması isteme."
keywords: 
author: nbigman
manager: angerobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: a7cced90c482498b5f5af424165f8dcf77b79b75
ms.openlocfilehash: ccd55cc8637ebccfdbddd05c4f6b182c7923a2ab


---

# Microsoft Intune için Multi-Factor Authentication

Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak üzere cihaz kaydı için Azure AD Multi-Factor Authentication (MFA) özelliğini tümleştirir. MFA, kullanıcı adları ve parolaların yanı sıra metin kimlik doğrulaması gibi kimlik doğrulama faktörleri de gerektirir. Bu, iOS, Android, Windows 8.1 veya üstü, Windows Phone 8.1 veya üstü cihazlar için desteklenir.

> [!NOTE]
>
> Configuration Manager’ın eski sürümlerinde (1610 sürümü öncesi), Configuration Manager Yönetici konsolunda MFA ayarını görmeye devam edersiniz. Configuration Manager yönetici konsolunda MFA'yı yapılandırmak işe yaramaz; bu yüzden bunu denemeyin. MFA’yı bu konuda açıklandığı şekilde yapılandırın.

### Intune’u cihaz kaydında çok faktörlü kimlik doğrulama isteyecek şekilde yapılandırma
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



<!--HONumber=Sep16_HO4-->


