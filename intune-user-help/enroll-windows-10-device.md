---
title: Intune şirket Portalı'nda Windows 10 Cihazınızı kaydetme | Microsoft Docs
description: Intune şirket Portalı'nda Windows 10 cihazlarını kaydetme adımları
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/11/2019
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
ms.openlocfilehash: 4eb5dbb150559de7ad30a598fb78a4fa78033c42
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61497906"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Intune Şirket portalı ile Windows 10 cihazlarını kaydetme

Windows 10 Cihazınızı kuruluşunuzun yönetim altında kaydetmek için Intune şirket Portalı'nı kullanın. Bu makalede, Windows 10 sürüm 1607 ve üzeri ve Windows 10 sürüm 1511 ve öncesi ile cihazları ıntune'a nasıl kaydedildiği açıklanır. Başlamadan önce emin olun [cihazınızdaki sürümünü doğrulayın](windows-enrollment-company-portal.md#find-windows-10-version-number) doğru adımları izleyebilirsiniz.  

Windows 10 Masaüstü, telefon ve tablet gibi çeşitli cihaz türleri arasında desteklenir. Kayıt adımları, kullanmakta olduğunuz cihazı üzerinde aynıdır. Ancak, ekranınızın bu makalede gösterilen resimlerden biraz farklı görünebilir.  

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]  

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Windows 10 sürüm 1607 ve üzeri cihaz kaydetme 
Bu adımlar Windows 10, sürüm 1607 ve üzeri çalıştıran bir cihazın nasıl kaydedileceği açıklanmaktadır.  

1. **Başlat**'a gidin. Bir Windows 10 Mobile cihazda varsa, devam **tüm uygulamalar** listesi.

2. Açık **ayarları** uygulama. Uygulama, uygulamalar listesinde kullanılabilir değilse, arama çubuğu ve türü "ayarlar" gidin

3. **Hesaplar** > **İş veya okula erişim** > **Bağlan**’ı seçin.  


    ![İş veya okul hesabına erişimi seçme](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. İş veya okul e-posta adresinizi girin ve sonra **İleri**’yi seçin.  


   ![İş veya okul hesabınızı girme](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. İş veya okul hesabınız ile Intune’da oturum açın.  


    ![İş veya okul hesabı ekle](./media/w10-enroll-rs1-enter-your-credentials.png)  

    Sonuçta, şirketiniz veya okulunuz, cihazınız kaydediliyor bir ileti görürsünüz.

6. Kuruluşunuzda bir PIN için Windows Hello'yu ayarlama gerekiyorsa, bir doğrulama kodu girmeniz istenir. Kodu girin ve aracılığıyla devam ekrandaki bir PIN oluşturmak için adımlar.  

7. Üzerinde **tamamen hazırsınız!** ekranını görünce **Bitti**’yi seçin. Cihazınız artık kaydedilmiştir.  

8. Bağlantınızı denetleyin geri gidin **ayarları** > **hesapları** > **işe veya okula erişim**.  Hesabınız artık listelenmelidir.  


    ![Bağlantının düzgün biçimde ayarlandığını doğrulama](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

İş veya okul e-postalarınıza, dosyalarınıza veya diğer verilerinize hâlâ erişemiyor musunuz? Bilgi edinmek için nasıl [hesabı sorunlarını giderme](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Windows 10 sürüm 1511 ve önceki cihaz kaydetme  
Bu adımlar Windows 10 sürüm 1511 ve öncesi çalışan bir cihazın nasıl kaydedileceği açıklanmaktadır.  

1. **Başlat**'a gidin. Bir Windows 10 Mobile cihazda varsa, devam **tüm uygulamalar** listesi.

2. Açık **ayarları** uygulama. Uygulama, uygulamalar listesinde kullanılabilir değilse, arama çubuğu ve türü "ayarlar" gidin

3. Seçin **hesapları** > **hesabınızı**.  


    ![Hesabınızı seçme](./media/W10-enroll-2-accounts-your-account.png)  

5. **İş veya okul hesabı ekle**’yi seçin.  


    ![İş veya okul hesabı ekle’yi seçme](./media/w10-enroll-3-add-work-school-acct.png)  

6. İş veya okul kimlik bilgilerinizle oturum açın.  


    ![Oturum aç](./media/W10-enroll-4-sign-in.png)  

İş veya okul e-postalarınıza, dosyalarınıza veya diğer verilerinize hâlâ erişemiyor musunuz? Bilgi edinmek için nasıl [hesabı sorunlarını giderme](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).   

## <a name="next-steps"></a>Sonraki adımlar  

Yardım almak için şirketinizin destek birimi ile iletişime geçin. Kuruluşunuzun bulabilirsiniz BT bilgi [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980). Site iş veya Okul hesabınızla oturum açın.  

 

