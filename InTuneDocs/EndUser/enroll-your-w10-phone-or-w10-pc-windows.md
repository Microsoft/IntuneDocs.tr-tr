---
title: "Windows 10 cihazınızı Intune’a kaydetme | Microsoft Intune"
description: "Windows 10 mobil veya masaüstü cihazının Intune’a nasıl kaydedildiği açıklanır."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bff97f79c6e88bbf55c2c3a259891bb6206b690b
ms.openlocfilehash: fb950108f3232af8049e90af977b0f3f9f2b3576


---


# Windows 10 Mobile veya Windows 10 masaüstü cihazınızı Intune'a kaydetme

Şirketinizde veya okulunuzda Microsoft Intune kullanılıyorsa, şirket e-postasına, dosyalarına ve diğer kaynaklarına erişmek için cihazlarınızı kaydedebilirsiniz. Cihazlarınızın kaydedilmesi kuruluşunuzda şirket verilerinin güvenli tutulabilmesini sağlar. Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklerseniz ve cihazınızı Intune’a kaydederseniz ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) ve [BT yöneticinizin cihazınızda görebilecekleri ve göremeyecekleri](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).


Windows 10 Mobile veya Windows 10 masaüstü cihazınızı kaydetmek için:

1.  Windows **Ayarları**’na gidin, sonra **Hesaplar**’a dokunun.

    ![Windows Ayarları](./media/w10-enroll-rs1-settings-accounts.png)

2.  Sonraki iki ekrana bakarak kendi cihazınızda gördüğünüze benzeyeni bulun. Cihazınızda gördüğünüz ekrana uyan adımları uygulayın.

    Bu ekranı görürseniz, [İşe veya okula Erişim seçeneğini görüyorsanız izlenecek adımlar](#steps-to-follow-if-you-see-access-work-or-school) kısmındaki yönergeleri izleyin.

    ![İşe veya okula bağlan](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Bu ekranı görürseniz, [Hesabınızı görüyorsanız uygulanacak adımlar](#steps-to-follow-if-you-see-your-account) bölümündeki adımları uygulayın.

    ![Hesabınız](./media/w10-enroll-2-accounts-your-account.png)

## İşe veya okula erişim seçeneğini görüyorsanız izlenecek adımlar

1.  **İşe veya okula erişim**’e tıklayın.

    ![İş okul hesabına Erişime dokunun](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  İş veya okul e-posta adresinizi girin ve sonra **İleri**’ye dokunun.

    ![İş veya okul hesabınızı girme](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. İş veya okul hesabınız ile Intune’da oturum açın.

    ![İş veya okul hesabı ekle](./media/w10-enroll-rs1-enter-your-credentials.png)

    Şirketinizin veya okulunuzun cihazını kaydettiğini belirten bir mesaj görürsünüz.

4. **Tamamen hazırsınız!** ekranını gördüğünüzde **Kapat**’a dokunun. İşlem tamamlandı.

  !["Tamamen hazırsınız!" ekranında Kapat’a dokunun](./media/w10-enroll-rs1-youre-all-set.png)

5. Bağlantınızın doğru olup olmadığını bir kez daha kontrol etmek isterseniz, artık iş veya okul hesabınızın listelenmesi gereken **Ayarlar**’a geri dönün.

    ![Bağlantının düzgün biçimde ayarlandığını doğrulama](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Önceki adımları uygulamanıza rağmen iş veya okul e-posta hesabınıza ve dosyalarınıza erişemiyorsanız, [İşe veya okula erişim görüyorsanız izlenecek sorun giderme adımları](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school) bölümündeki adımları uygulayın.


## Hesabınızı görüyorsanız uygulanacak adımlar

1.  Windows **Ayarlar**’ına gidin ve ardından **Hesaplar**’a dokunun.

    ![Ayarlar ve Hesaplar’a gidin](./media/W10-enroll-1-settings-accounts.png)

2.  **Hesabınız**’a dokunun.

    ![Hesabınıza dokunun](./media/W10-enroll-2-accounts-your-account.png)

3.  **İş veya okul hesabı ekle**’ye dokunun.

    ![İş veya okul hesabı ekle’ye dokunun](./media/w10-enroll-3-add-work-school-acct.png)

4.  İş veya okul kimlik bilgilerinizle oturum açın.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Yukarıdaki adımları uygulamanıza rağmen iş veya okul e-posta adresinize, dosyalarınıza veya diğer verilerinize erişemiyorsanız, [Hesabınızı görüyorsanız izlenecek sorun giderme adımları](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) bölümündeki yönergeleri deneyin.

Ayrıca sizinle ve rolünüzle ilgili olan şirket uygulamalarını kolayca belirleyip edinmenizi sağlayan Şirket Portalı uygulamasını yüklemenizi öneririz. Şirketinizin Intune’u nasıl yapılandırdığına göre, Şirket Portalı uygulaması kayıt sürecinizin parçası olarak yüklenmiş olabilir.

Uygulamanın sizde olup olmadığını doğrulamak için uygulama listenizde **Şirket Portalı**’nı arayın. Uygulama listenizde Şirket Portalı’nı görmüyorsanız, yüklemek için aşağıdaki adımları izleyin.

1.  **Başlat** &gt; **Mağaza**’ya dokunun.

2.  **Ara**’ya dokunun, sonra **şirket portalı** yazın.

3.  Sonuçlar listesinde **Şirket Portalı** &gt; **Yükle**’ye dokunun.

4.  **Yükle** veya **Ücretsiz**’e dokunun. Gösterilen seçenek, şirketinizin uygulamayı nasıl yapılandırdığına bağlıdır.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.





<!--HONumber=Sep16_HO3-->


