---
title: "Şirket Portalı uygulamasında oturum açma | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 2e27bdcb6af7d81ed87aa113b11affbff695b808
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Şirket Portalı uygulamasında nasıl oturum açarım? <!--User Story 1132123-->

> [!IMPORTANT]
> Bu özellik piyasaya sunulma sürecindedir. Deneyiminiz farklı olabilir. Piyasaya çıkış tamamlandığında bu bildirimi kaldıracağız.

E-posta ve iş uygulamaları gibi şirket kaynaklarına erişmek için Şirket Portalı uygulamasını kullanırsınız. Şirket Portalı uygulamasında oturum açmanız için iki temel yol vardır:

* İş e-posta adresiniz ve parolanızı kullanarak oturum açma
* Başka bir cihazdan oturum açma

Aşağıdaki resimler iOS için olsa da Android ve Windows cihazlar için de süreç temel olarak aynıdır.

## <a name="signing-in-with-your-email-address-and-password"></a>E-posta adresi ve parolanızla oturum açma

1. Cihazınızda Şirket Portalı uygulamasını açın ve **Oturum Aç**’a dokunun.

  ![Şirket Portalı oturum açma sayfasında, bir web sitesinin grafik temsili önünde bir kişi simgesi. Altındaki ise "Oturum aç" düğmesidir. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](/intune/media/cp_ios_aad_signin_after_1704_001.png)

  Şirket Portalı uygulamanız yok mu? Uygulamayı [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) ve [Android](install-the-company-portal-app-android.md) için nasıl indirip yükleyeceğinizi öğrenin.

2. **İş veya okul hesabınızı** girin.

  ![Kullanıcı aynı ekranda hem e-posta adresini hem de parolasını girmek yerine yalnızca kendi e-posta adresini girer.](/intune/media/cp_ios_aad_signin_after_1704_002.png)

3. E-posta adresiniz onaylanırken biraz bekleyin, daha sonra parolanızı girin.

  ![E-posta adresi kabul edildikten sonra kullanıcıdan parolası istenir.](/intune/media/cp_ios_aad_signin_after_1704_003.png)

4. Şirket Portalı, oturum açma bilgilerinizi kabul ettikten sonra oturumunuzu açar ve siz de şirket kaynaklarınıza erişebilirsiniz.   

  ![Kimlik doğrulama işleminden sonra, Şirket Portalı uygulaması oturum açar ve bunu bir yükleme çubuğuyla belirtir.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="signing-in-from-another-device"></a>Başka bir cihazdan oturum açma

Şirket kaynaklarınıza erişmek için parola kullanmıyorsanız doğru erişim düzeyine sahip doğru kişi olduğunuzu onaylamak için başka bir cihaz kullanabilirsiniz. Şirketiniz, bilgisayarlara erişim için akıllı kartlar kullanıyorsa o halde büyük olasılıkla başka bir cihaz kullanarak oturum açmanız gerekiyordur.

1. E-posta adresinizi girmek yerine, e-posta metin kutusunun altındaki **Başka bir cihazdan oturum aç** bağlantısını seçin.

  ![Şirket Portalı oturum açma sayfasında, bir web sitesinin grafik temsili önünde bir kişi simgesi. Altındaki ise "Oturum aç" düğmesidir. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

2. Şirket Portalı’nda oturum açmak için benzersiz, tek seferlik bir kod alacaksınız.

  ![İş bilgisayarınızdan benzersiz bir geçiş kodu ile aka.ms/devicelogin sayfasına gidip oturum açmak için bu kodu kullanmaya ilişkin yönergeler sağlanır.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

3. Diğer cihazınızda tarayıcıyı açın ve kodu girmek için [https://aka.ms/devicelogin](https://aka.ms/devicelogin) adresine gidin.

  ![Kullanıcının Şirket Portalı uygulamasındaki tarayıcı yerine iş bilgisayarındaki tarayıcısının bir resmi. Görüntülenen "Cihaz oturum açma" sayfası kullanıcıdan Şirket Portalı uygulamasından aldığı kodu girmesini ister.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. **Cihazla Oturum Açma** sayfası kodunuzu doğruladığında __Devam__’a tıklayarak Şirket Portalı’nın diğer cihazınızda oturum açmasını sağlayın.

  ![Kullanıcı kendi benzersiz kodunu alana girmiştir ve "Cihaz oturum açma" sitesi Intune Şirket Portalı’nın oturum açmak üzere yetkilendirilecek doğru uygulama olup olmadığının doğrulanmasını istemiştir.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Kod doğrulandığında pencereyi kapatabilirsiniz.

  ![Bir onay sayfası, kullanıcının kendi cihazında Şirket Portalı uygulamasında oturum açtığını ve bu sayfanın artık kapatılabileceğini belirtir.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Asıl cihazınızda Şirket Portalı oturum açmaya başlar.

  ![Kimlik doğrulama işleminden sonra Şirket Portalı, ilerlemeyi gösteren bir çubuk ile oturum açar.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.
