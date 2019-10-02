---
title: Kuruluşunuzun sunduğu iOS cihazını yönetime kaydedin. | Microsoft Docs
description: Intune 'A, kuruluşunuz tarafından satın alınan ve sunulan bir iOS cihazının nasıl kaydedileceğini açıklar.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f4e7d87e-56d1-43e4-8e88-2f62cf0999e2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: bca7ff55653d12d352b4fb90163f4622a9e573ab
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71720998"
---
# <a name="enroll-your-organization-provided-ios-device-in-management"></a>Kuruluşunuzun sunduğu iOS cihazını yönetime kaydetme

Intune 'da yeni iOS cihazınızı nasıl yönetileceğini öğrenin.  

İş veya okul tarafından size sunulan iOS cihazları, genellikle bunları almadan önce önceden yapılandırılmıştır. Kuruluşunuz, önceden bu ayarları açtıktan sonra, ilk kez oturum açtıktan sonra cihazınıza gönderir. Cihazınız kurulumu tamamladıktan sonra, iş veya okul kaynaklarınıza erişim elde edersiniz.  

Kuruluma başlamak için cihazınızı başlatın ve iş veya okul kimlik bilgilerinizle oturum açın. Bu makalenin geri kalanında, Kurulum Yardımcısı ' na kılavuzluk ettiğiniz için göreceğiniz adımlar ve ekranlar açıklanmaktadır.

## <a name="what-is-apple-dep"></a>Apple DEP nedir?

Kuruluşunuz cihazlarını *Apple aygıt kayıt programı* (DEP) adlı bir şekilde satın almış olabilir. Apple DEP, kuruluşların büyük miktarlarda iOS veya macOS cihazı satın almasını sağlar. Kuruluşlar daha sonra bu cihazları Intune gibi tercih edilen mobil cihaz yönetimi sağlayıcıları içinde yapılandırabilir ve yönetebilir. Yöneticiyseniz ve Apple DEP hakkında daha fazla bilgi istiyorsanız bkz. [apple aygıt kayıt programı iOS cihazlarını otomatik olarak kaydetme](https://docs.microsoft.com/intune/enrollment/device-enrollment-program-enroll-ios.md).  

## <a name="set-up-your-ios-device"></a>İOS cihazınızı ayarlama

Bir kuruluş tarafından sağlanmaktansa kendi iOS cihazınızı kullanıyorsanız, [kişisel ve kendi cihazlarını getir](enroll-your-device-in-intune-ios.md)adımlarını izleyin.  

1. İOS cihazınızı açın.
2. **Dilinizi**seçtikten sonra, cihazınızı Wi-Fi ' a bağlayın.
3. **İOS cihazını ayarla** ekranında, aşağıdakileri yapmak isteyip istemediğinizi seçin:
   - **Yeni cihaz olarak ayarla**
   - **İCloud yedeğinden geri yükle**
   - **İTunes yedeğinden geri yükle**

4. Wi-Fi ' a Bağlandıktan sonra **yapılandırma** ekranı görüntülenir. Bu, **[şirketiniz] tarafından cihazınızı otomatik olarak yapılandıracaksınız.**

   **Yapılandırma [şirketiniz] uygulamasının bu cihazı hava üzerinden yönetmesine olanak tanır. Yönetici, e-posta ve ağ hesapları ayarlamanıza, uygulama yükleyip yapılandırmanıza ve ayarları uzaktan yönetmenize yardımcı olabilir. Bir yönetici özellikleri devre dışı bırakabilir, uygulama yükleyip kaldırabilir, Internet trafiğinizi izleyip kısıtlayabilir ve bu cihazı uzaktan silebilir.**

   **Yapılandırma tarafından sağlanır: [Şirketinizin] iOS ekibi [Adres]**

5. Apple KIMLIĞINIZLE oturum açın. Oturum açma, Şirket Portalı uygulamasını yüklemenize ve şirketinizin e-posta ve uygulamalar gibi kaynaklarına erişmenizi sağlayacak yönetim profilini yüklemenize olanak sağlar.
6. **Hüküm ve koşulları** kabul edin ve Apple 'a tanılama bilgileri göndermek isteyip istemediğinize karar verin.
7. Kaydınız tamamlandıktan sonra cihazınız daha fazla işlem yapmanız istenebilir. Bu adımlardan bazıları e-posta erişimi için parolanızı veya bir geçiş kodu ayarlamayı giriyor olabilir.

Hala yardıma mı ihtiyacınız var? Şirketinizin destek birimine başvurun. İletişim bilgileri için [Şirket portalı Web sitesini](https://go.microsoft.com/fwlink/?linkid=2010980)denetleyin.
