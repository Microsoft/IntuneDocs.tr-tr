---
title: Şirket Portalı uygulamasında oturum açma | Microsoft Docs
description: Birden çok platformdaki Şirket Portalı uygulamasında oturum açmayı öğrenin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0b61771385923af05c656f04e4257176b72ee35
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61504069"
---
# <a name="sign-in-to-company-portal"></a>Şirket portalında oturum açın  

Şirket portalı uygulamasında oturum açmak için üç yolu vardır:

* İş e-posta adresinizi ve parolanızı bilgilerinizle oturum açın.  
* Sertifika tabanlı kimlik bilgilerinizle oturum açın.  
* Başka bir CİHAZDAN oturum açın.    


## <a name="sign-in-with-your-email-address-and-password"></a>E-posta adresi ve parolanızla oturum açın
Aşağıdaki adımlar, iOS için şirket Portalı'ndan ekran görüntüleri gösterir.  

1. Dokunma ve cihaz uygulamasını açın **oturum**.  

   ![Şirket Portalı oturum açma sayfasında, bir web sitesinin grafik temsili önünde bir kişi simgesi. Metni "şirket kaynaklarına ve bunları güvende tutun Get erişim" ve "Oturum Aç" düğmesi olmasıdır. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](/intune-user-help/media/cp_ios_aad_signin_after_1804_001.png)



2. **İş veya okul hesabınızı** girin ve **İleri**’ye dokunun.

   ![Kullanıcı aynı ekranda hem e-posta adresini hem de parolasını girmek yerine yalnızca kendi e-posta adresini girer.](/intune-user-help/media/cp_ios_aad_signin_after_1804_002.png)

3. Parolanızı girin ve **Oturum Aç**’a dokunun.

   ![E-posta adresi kabul edildikten sonra kullanıcıdan parolası istenir.](/intune-user-help/media/cp_ios_aad_signin_after_1804_003.png)

4. Uygulama, kimlik bilgilerinizi doğrular. İşiniz bittiğinde, kuruluşunuzun kaynaklarına erişmek ve kullanılabilir uygulamaları yüklemesi.  

   ![Kimlik doğrulama işleminden sonra Şirket portalı uygulaması oturum açar ve bir yükleme çubuğu gösterilir.](/intune-user-help/media/cp_ios_aad_signin_after_1804_004.png)

## <a name="sign-in-with-certificate-based-authentication"></a>Sertifika tabanlı kimlik doğrulaması ile oturum

1.  Cihazınızda Şirket Portalı uygulamasını açın.  

2.  **İş veya okul hesabınızı** girin.  

3.  **Sertifika ile oturum açma** bağlantısına dokunun.  

4.  Sertifikayı kullanmak için **Devam**’a dokunun.  

## <a name="sign-in-from-another-device"></a>Başka bir CİHAZDAN oturum aç

Şirketiniz, bilgisayarlara erişim için akıllı kartlar kullanıyorsa, başka bir CİHAZDAN oturum açma ile kimlik doğrulaması yapması olasıdır.  

1. Cihazınızda Şirket Portalı uygulamasını açın. İş kaynaklarınıza erişmek için kullanacaklardır cihaz olduğundan emin olun.       

1. Seçin **başka bir CİHAZDAN oturum aç**.  

   ![Şirket portalı oturum açma sayfasında e-posta adresi kullanıcıya sorar.  "Oturum açmak için başka bir CİHAZDAN." "İleri" düğmesi ve bir bağlantı gösterir. Ayrıca bir “Hesabınıza erişemiyor musunuz?” bağlantısı da vardır. Aşağıdaki bir bağlantı Microsoft Gizlilik ve Tanımlama bilgilerine yönlendirir.](/intune-user-help/media/cp_ios_aad_signin_after_1804_005.png)

2. Şirket Portalı’nda oturum açmak için benzersiz, tek seferlik bir kod alacaksınız. Kodu kopyalayın.

   ![İş bilgisayarınızdan benzersiz bir geçiş kodu ile https://microsoft.com/devicelogin sayfasına gidip oturum açmak için bu kodu kullanmaya ilişkin yönergeler sağlanır.](/intune-user-help/media/cp_ios_aad_signin_after_1804_006.png)

3. Diğer Cihazınızda (kimlik doğrulaması için kullandığınız bir), tarayıcınızı açın ve gidin [ https://microsoft.com/devicelogin ](https://microsoft.com/devicelogin). Kodu yapıştırın veya girin.  

   ![Kullanıcının Şirket Portalı uygulamasındaki tarayıcı yerine iş bilgisayarındaki tarayıcısının bir resmi. Görüntülenen "Cihaz oturum açma" sayfası kullanıcıdan Şirket Portalı uygulamasından aldığı kodu girmesini ister.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Seçin __devam__ iş Cihazınızda oturum açmak Şirket portalı izin vermek için.   

   ![Kullanıcı kendi benzersiz kodunu alana girmiştir ve "Cihaz oturum açma" sitesi Intune Şirket Portalı’nın oturum açmak üzere yetkilendirilecek doğru uygulama olup olmadığının doğrulanmasını istemiştir.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Kod doğrulandığında pencereyi kapatabilirsiniz.  

   ![Bir onay sayfası, kullanıcının kendi cihazında Şirket Portalı uygulamasında oturum açtığını ve bu sayfanın artık kapatılabileceğini belirtir.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Şirket portalı uygulaması, iş Cihazınızda oturum açıyor.  

   ![Kimlik doğrulama işleminden sonra Şirket Portalı, ilerlemeyi gösteren bir çubuk ile oturum açar.](/intune-user-help/media/cp_ios_aad_signin_after_1804_007.png)

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.  
