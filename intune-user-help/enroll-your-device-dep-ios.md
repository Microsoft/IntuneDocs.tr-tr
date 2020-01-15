---
title: Kuruluş tarafından sağlanan iOS cihazınızı yönetime kaydedin. | Microsoft Docs
description: Kuruluşunuz tarafından satın alınan ve sağlanan bir iOS cihazın Intune’a nasıl kaydedildiğini açıklar
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f4e7d87e-56d1-43e4-8e88-2f62cf0999e2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 6c1b6417489d1443596113a18476b9cbc8f3832e
ms.sourcegitcommit: 8cc3eca2bce847b0c2b40d8531698e21df848878
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75951467"
---
# <a name="enroll-your-organization-provided-ios-device-in-management"></a>Kuruluş tarafından sağlanan iOS cihazınızı yönetime kaydedin

Yeni iOS cihazınızı Intune yönetimine kaydetmeyi öğrenin.  

Size iş veya okul tarafından sağlanan iOS cihazlar genellikle elinize ulaşmadan önce yapılandırılmış olur. Cihazınızı ilk kez açtığınızda ve oturum açtığınızda kuruluşunuz cihaza bu önceden yapılandırılmış ayarları gönderir. Cihazınızın kurulumu tamamlandıktan sonra, iş veya okul kaynaklarınıza erişim elde edersiniz.  

Kuruluma başlamak için cihazınızı açın ve iş veya okul kimlik bilgilerinizle oturum açın. Bu makalenin kalan bölümünde Kurulum Yardımcısı'nda ilerlerken göreceğiniz adımlar ve ekranlar açıklanır.

## <a name="what-is-apple-dep"></a>Apple DEP nedir?

Kuruluşunuz cihazlarını *Apple Aygıt Kayıt Programı* (DEP) adı verilen bir hizmet yoluyla satın almış olabilir. Apple DEP, kuruluşların çok sayıda iOS veya macOS cihaz satın almasına imkan tanır. Ardından kuruluşlar bu cihazları Intune gibi tercih ettikleri bir mobil cihaz yönetim sağlayıcısında yapılandırabilir ve yönetebilir. Yöneticiyseniz ve Apple DEP hakkında daha fazla bilgi edinmek istiyorsanız bkz. [iOS cihazları Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme](/intune/enrollment/device-enrollment-program-enroll-ios).

## <a name="set-up-your-ios-device"></a>iOS cihazınızı ayarlama

Kuruluş tarafından sağlanan bir cihaz yerine kendi iOS cihazınızı kullanıyorsanız, [kişisel cihazlara ve kendi cihazını getir kapsamındaki cihazlara](enroll-your-device-in-intune-ios.md) yönelik adımları izleyin.  

1. iOS cihazınızı başlatın.
2. **Dil** ayarınızı yaptıktan sonra cihazınızı Wi-Fi’a bağlayın.
3. **İOS cihazını ayarla** ekranında **yeni cihaz olarak ayarla**' yı seçin.  
4. Wi-Fi’a bağlandıktan sonra **Yapılandırma** ekranı görünür. Bu ekranda **[Şirketiniz], cihazınızı otomatik olarak yapılandıracaktır** ifadesi yer alır.

   **Yapılandırma [şirketiniz] uygulamasının bu cihazı hava üzerinden yönetmesine olanak tanır. Yönetici, e-posta ve ağ hesapları ayarlamanıza, uygulama yükleyip yapılandırmanıza ve ayarları uzaktan yönetmenize yardımcı olabilir. Bir yönetici özellikleri devre dışı bırakabilir, uygulama yükleyip kaldırabilir, Internet trafiğinizi izleyip kısıtlayabilir ve bu cihazı uzaktan silebilir.**

   **Yapılandırma şunlar tarafından sağlanır: [Şirketinizin] iOS Ekibi [Adres]**

5. Apple kimliğinizle oturum açın. Oturum açmak, Şirket Portalı uygulamasını yüklemenize ve şirketinizin size e-posta ve uygulamalar gibi kaynakların erişimini sağlamasına izin verecek yönetim profilini yüklemenize imkan verir.
6. **Hüküm ve Koşullar**’ı onaylayın ve Apple’a tanılama bilgileri göndermek isteyip istemediğinizi seçin.
7. Kaydınızı tamamladığınızda, cihazınız daha fazla eylem gerçekleştirmenizi isteyebilir. Bu adımlardan bazıları, e-posta erişimi için parolanızı girmek veya bir geçiş kodu ayarlamak olabilir.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
