---
title: iOS cihazları için Microsoft Intune e-posta ayarları
titleSuffix: ''
description: iOS çalıştıran cihazlarda e-posta ayarlarını yapılandırmak için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 5/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe791dce88878fdbde7c62e59452a53ac08ef06b
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190494"
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>iOS çalıştıran cihazlar için Microsoft Intune'da e-posta profili ayarları 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, iOS çalıştıran cihazlarınız için yapılandırabileceğiniz e-posta profili ayarları gösterilmektedir.

## <a name="email-settings"></a>E-posta ayarları

- **E-posta sunucusu** - Exchange sunucunuzun konak adı.
- **Hesap adı** - E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.
- **AAD’den kullanıcı adı özniteliği** - Bu öznitelik, bu e-posta profili için kullanıcı adını oluşturmak üzere kullanılan Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** için **user1@contoso.com** gibi bir değer seçin veya **Kullanıcı Asıl Adı**’nı (**kullanıcı1** veya **user1@contoso.com** gibi) belirtin.
- **AAD’den e-posta adresi özniteliği** - E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**’ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**’nı seçin.
- **Kimlik doğrulama yöntemi** - E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin (**Not**: Azure Multi-Factor Authentication desteklenmez).
    - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılan, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL** - E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME** - S/MIME imzalama kullanarak giden e-posta gönderin.
    - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz bir PKCS sertifika profilini seçin.
- **Eşitlenecek e-posta miktarı** - Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postayı eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına izin ver** - Kullanıcıların, e-posta iletilerini cihazlarında yapılandırdıkları farklı hesaplara taşımasına izin verir.
- **Üçüncü taraf uygulamalarından e-posta gönderilmesine izin ver** - Kullanıcının, bu profili e-posta göndermek için varsayılan hesap olarak seçmesini sağlayın ve üçüncü taraf uygulamalarının, yerel e-posta uygulamasında e-postayı açmasına izin verin (örneğin e-postaya dosya eklemek için).
- **Son kullanılan e-posta adreslerini eşitle** - Bu özellik, kullanıcıların cihazda son kullanılan e-posta adreslerinin listesini sunucuyla eşitlemesine olanak tanır.
