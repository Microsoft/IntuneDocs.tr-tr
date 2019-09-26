---
title: Windows 10 cihazını Intune Şirket Portalı kaydetme | Microsoft Docs
description: Intune Şirket Portalı Windows 10 cihazlarını kaydetme adımları
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2e4def9f0e4e91f7db9e0a81e2ad55852df524f7
ms.sourcegitcommit: 0d1a02fb3d2a801a95c2244e9ef13ecf22be2eb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/26/2019
ms.locfileid: "71302455"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Windows 10 cihazlarını Intune Şirket Portalı kaydetme

Windows 10 cihazınızı kuruluşunuzun yönetimi altına kaydetmek için Intune Şirket Portalı kullanın. Bu makalede, Windows 10 sürüm 1607 ve üzeri ve Windows 10 sürüm 1511 ve öncesiyle cihazların nasıl kaydedileceğini açıklanmaktadır. Başlamadan önce, doğru adımları izleyebilmeniz için [cihazınızdaki sürümü doğruladığınızdan](windows-enrollment-company-portal.md#find-windows-10-version-number) emin olun.  

Windows 10 Masaüstü, telefon ve tablet gibi çeşitli cihaz türleri arasında desteklenir. Kayıt adımları, kullanmakta olduğunuz cihaz ile aynıdır. Ancak, ekranınızda Bu makalede gösterilen görüntülerden biraz farklı görünebilir.  
</br>
> [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Windows 10 sürüm 1607 ve üzeri bir cihaz Kaydet 
Bu adımlar, Windows 10, sürüm 1607 ve üzeri sürümlerde çalışan bir cihazın nasıl kaydedileceğini açıklamaktadır.  

1. **Başlat**'a gidin. Windows 10 Mobile cihazında çalışıyorsanız **tüm uygulamalar** listesine devam edin.

2. **Ayarlar** uygulamasını açın. Uygulama, uygulamalar listenizde hazır değilse, arama çubuğuna gidin ve "Ayarlar" yazın.

3. **Hesaplar** > **İş veya okula erişim** > **Bağlan**’ı seçin.  


    ![İş veya okul hesabına erişimi seçme](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Kuruluşunuzun Intune oturum açma sayfasına ulaşmak için iş veya okul e-posta adresinizi girin. Ardından **İleri**' yi seçin.  


   ![İş veya okul hesabınızı girme](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. İş veya okul hesabınız ile Intune’da oturum açın.  


    ![İş veya okul hesabı ekle](./media/w10-enroll-rs1-enter-your-credentials.png)  

    Son olarak, şirketinizin veya okulunuzun cihazınızı kaydettiğini belirten bir ileti görürsünüz.

6. Kuruluşunuz Windows Hello için bir PIN ayarlamanızı gerektiriyorsa, bir doğrulama kodu girmeniz istenir. Kodu girin ve bir PIN oluşturmak için ekrandaki adımlarla devam edin.  

7. **Her şey hazırsınız!** ekranını görünce **Bitti**’yi seçin. Cihazınız artık kaydedilmiştir.  

8. Bağlantınızı iki kez denetlemek için **Ayarlar** > **hesaplar** > **iş veya okula erişim**bölümüne dönün.  Hesabınız artık listelenmelidir.  


    ![Bağlantının düzgün biçimde ayarlandığını doğrulama](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

İş veya okul e-postalarınıza, dosyalarınıza veya diğer verilerinize hâlâ erişemiyor musunuz? [Hesap sorunlarını nasıl giderebileceğinizi](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school)öğrenin.  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Windows 10 sürüm 1511 ve önceki bir cihaz kaydetme  
Bu adımlar, Windows 10, sürüm 1511 ve önceki sürümlerde çalışan bir cihazın nasıl kaydedileceğini açıklamaktadır.  

1. **Başlat**'a gidin. Windows 10 Mobile cihazında çalışıyorsanız **tüm uygulamalar** listesine devam edin.

2. **Ayarlar** uygulamasını açın. Uygulama, uygulamalar listenizde hazır değilse, arama çubuğuna gidin ve "Ayarlar" yazın.

3. **Hesabınızı seçin**. >   


    ![Hesabınızı seçme](./media/W10-enroll-2-accounts-your-account.png)  

5. **İş veya okul hesabı ekle**’yi seçin.  


    ![İş veya okul hesabı ekle’yi seçme](./media/w10-enroll-3-add-work-school-acct.png)  

6. İş veya okul kimlik bilgilerinizle oturum açın.  


    ![Oturum aç](./media/W10-enroll-4-sign-in.png)  

İş veya okul e-postalarınıza, dosyalarınıza veya diğer verilerinize hâlâ erişemiyor musunuz? Kayıt sırasında [hesap ile ilgili sorunların nasıl giderileceği](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) hakkında bilgi edinin.  

## <a name="it-administrator-support"></a>BT yöneticisi desteği   

BT yöneticisiyseniz ve cihazları kaydederken sorun yaşıyorsanız, bkz. [Microsoft Intune Windows cihaz kaydı sorunlarını giderme](https://support.microsoft.com/help/4469913). Bu makalede, sık karşılaşılan hatalar, nedenler ve bunları çözmeye yönelik adımlar listelenir. 

## <a name="next-steps"></a>Sonraki adımlar  
Şirket Portalı veya kayıt ile ilgili yardıma ihtiyacınız varsa kuruluşunuzun BT destek ekibine başvurun. [Şirket portalı Web sitesinde](https://go.microsoft.com/fwlink/?linkid=2010980)iletişim bilgilerini bulacaksınız. İş veya okul hesabınızla sitede oturum açın.  

 

