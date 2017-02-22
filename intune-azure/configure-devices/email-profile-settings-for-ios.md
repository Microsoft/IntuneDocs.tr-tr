---
title: "iOS cihazları için Intune e-posta ayarları | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: iOS cihazlarında e-posta bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f16c9dfb41cb2cfe07ce473a131dac767dee9c74
ms.openlocfilehash: 255a5e8c8b430e15aba989e1ce805f7d627f0e0c


---

# <a name="email-profile-settings-for-ios-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde iOS cihazları için e-posta profil ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **E-posta sunucusu** - Exchange sunucunuzun konak adı.
- **Hesap adı** - E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.
- **AAD’den kullanıcı adı özniteliği** - Bu öznitelik, bu e-posta profili için kullanıcı adını oluşturmak üzere kullanılacak Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** için **user1@contoso.com** gibi bir değer seçin veya **Kullanıcı Asıl Adı**’nı (**kullanıcı1** veya **user1@contoso.com** gibi) belirtin.
- **AAD’den e-posta adresi özniteliği** - E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**’ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**’nı seçin.
- **Kimlik doğrulama yöntemi** - E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
    - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılacak, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL** - E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME** - Giden e-postaları S/MIME şifrelemesi kullanarak gönderin.
    - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılacak, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **Eşitlenecek e-posta miktarı** - Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postayı eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına izin ver** - Kullanıcıların, e-posta iletilerini cihazlarında yapılandırdıkları farklı hesaplara taşımasına izin verir.
- **Üçüncü taraf uygulamalarından e-posta gönderilmesine izin ver** - Kullanıcının, bu profili e-posta göndermek için varsayılan hesap olarak seçmesini sağlayın ve üçüncü taraf uygulamalarının, yerel e-posta uygulamasında e-postayı açmasına izin verin (örneğin e-postaya dosya eklemek için).
- **Son kullanılan e-posta adreslerini eşitle** - Bu özellik, kullanıcıların cihazda son kullanılan e-posta adreslerinin listesini sunucuyla eşitlemesine olanak tanır.



<!--HONumber=Feb17_HO1-->


