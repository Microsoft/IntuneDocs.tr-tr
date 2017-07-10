---
title: "iOS cihazları için Intune e-posta ayarları"
titleSuffix: Intune on Azure
description: "iOS cihazlarında e-posta bağlantılarını yapılandırmak için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dcac410ae5c20b5942bf37f5eaa9a46205a4cc07
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazları için e-posta profili ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



- **E-posta sunucusu** - Exchange sunucunuzun konak adı.
- **Hesap adı** - E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.
- **AAD’den kullanıcı adı özniteliği** - Bu öznitelik, bu e-posta profili için kullanıcı adını oluşturmak üzere kullanılacak Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** için **user1@contoso.com** gibi bir değer seçin veya **Kullanıcı Asıl Adı**’nı (**kullanıcı1** veya **user1@contoso.com** gibi) belirtin.
- **AAD’den e-posta adresi özniteliği** - E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**’ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**’nı seçin.
- **Kimlik doğrulama yöntemi** - E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
    - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılacak, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL** - E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME** - S/MIME imzalama kullanarak giden e-posta gönderin.
    - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılacak, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **Eşitlenecek e-posta miktarı** - Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postayı eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına izin ver** - Kullanıcıların, e-posta iletilerini cihazlarında yapılandırdıkları farklı hesaplara taşımasına izin verir.
- **Üçüncü taraf uygulamalarından e-posta gönderilmesine izin ver** - Kullanıcının, bu profili e-posta göndermek için varsayılan hesap olarak seçmesini sağlayın ve üçüncü taraf uygulamalarının, yerel e-posta uygulamasında e-postayı açmasına izin verin (örneğin e-postaya dosya eklemek için).
- **Son kullanılan e-posta adreslerini eşitle** - Bu özellik, kullanıcıların cihazda son kullanılan e-posta adreslerinin listesini sunucuyla eşitlemesine olanak tanır.
