---
title: "Windows 10 cihazınızı Intune’a kaydetme | Microsoft Intune"
description: "Windows 10 mobil veya masaüstü cihazının Intune’a nasıl kaydedildiği açıklanır."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 06/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 02287eb01598c28906045fd8def9e8b4660e3da5
ms.openlocfilehash: 8806231f8d02885a192053a35559694a8984d2f5


---


# Windows 10 Mobile veya Windows 10 masaüstü cihazınızı Intune'a kaydetme

Şirketinizde veya okulunuzda Microsoft Intune kullanılıyorsa, şirket e-postasına, dosyalarına ve diğer kaynaklarına erişmek için cihazlarınızı kaydedebilirsiniz. Cihazlarınızın kaydedilmesi kuruluşunuzda şirket verilerinin güvenli tutulabilmesini sağlar. Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklerseniz ve cihazınızı Intune’a kaydederseniz ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) ve [BT yöneticinizin cihazınızda görebilecekleri ve göremeyecekleri](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).


Windows 10 Mobile veya Windows 10 masaüstü cihazınızı kaydetmek için:

1.  Windows **Ayarlar**’a gidin ve **Hesaplar**’a dokunun.

    ![settings-accounts](./media/w10-enroll-rs1-settings-accounts.png)

2.  Sonraki iki ekrana bakarak kendi cihazınızda gördüğünüze benzeyeni bulun. Cihazınızda gördüğünüz ekrana uyan ekranın yanında yer alan adımları uygulayın.

    Bu ekranı görürseniz, [İşe veya okula erişim seçeneğini görüyorsanız izlenecek adımlar](#steps-to-follow-if-you-see-access-work-or-school) kısmındaki adımları uygulayın.

    ![connect-to-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Bu ekranı görürseniz, [Hesabınızı görüyorsanız uygulanacak adımlar](#steps-to-follow-if-you-see-your-account) bölümündeki adımları uygulayın.

    ![your-account](./media/w10-enroll-2-accounts-your-account.png)

## İşe veya okula erişim seçeneğini görüyorsanız izlenecek adımlar

1.  **İşe veya okula erişim**’e tıklayın.

    ![tap-access-work-school-account](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  İş veya okul e-postanızı girin ve **İleri**’ye dokunun.

    ![enter-your-work-or-school-account](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. İş veya okul hesabınızı kullanarak Intune’da oturum açın.

    ![add-work-school-account](./media/w10-enroll-rs1-enter-your-credentials.png)

    Şirketinizin veya okulunuzun cihazını kaydettiğini belirten bir mesaj görürsünüz.

4. **Tamamen hazırsınız!** sayfasını gördüğünüzde, **Kapat**’a dokunun. İşlem tamamlandı.

  ![tap-close-on-you-are-all-set-screen](./media/w10-enroll-rs1-youre-all-set.png)

5. Bağlantınızın doğru olup olmadığını bir kez daha kontrol etmek isterseniz, **Ayarlar**’a geri dönerek iş veya okul hesabınızın listelendiğini görebilirsiniz.

    ![validate-that-connection-was-set-up-correctly](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Yukarıdaki adımları uygulamanıza rağmen iş veya okul e-postanıza ve dosyalarınıza erişemiyorsanız, [İşe veya okula erişim görüyorsanız izlenecek sorun giderme adımları](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school) bölümündeki adımları uygulayın.


## Hesabınızı görüyorsanız uygulanacak adımlar

1.  Windows **Ayarlar**’a gidin ve **Hesaplar**’a dokunun.

    ![go-to-settings-accounts](./media/W10-enroll-1-settings-accounts.png)

2.  **Hesabınız**’a dokunun.

    ![tap-your-account](./media/W10-enroll-2-accounts-your-account.png)

3.  **İş veya okul hesabı ekle**’ye dokunun.

    ![add-work-or-school-account](./media/w10-enroll-3-add-work-school-acct.png)

4.  İş veya okul kimlik bilgilerinizle oturum açın.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Yukarıdaki adımları uygulamanıza rağmen iş veya okul e-postanıza, dosyalarınıza ve diğer verilere erişemiyorsanız, [Hesabınızı görüyorsanız izlenecek sorun giderme adımları](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) bölümündeki adımları uygulamayı deneyin.

Ayrıca sizinle ve rolünüzle ilgili olan şirket uygulamalarını kolayca belirleyip edinmenizi sağlayan Şirket Portalı uygulamasını yüklemenizi öneririz. Şirketinizin Intune’u nasıl yapılandırdığına bağlı olarak, Şirket Portalı uygulaması kayıt sürecinizin parçası olarak yüklenmiş olabilir. Uygulamaya sahip olup olmadığınızı denetlemek için uygulama listenizde **Şirket Portalı**’nı arayın. Uygulama listenizde Şirket Portalı’nı görmüyorsanız, yüklemek için aşağıdaki adımları izleyin.

1.  **Başlat** &gt; **Mağaza**’ya dokunun.

2.  **Ara**’ya dokunun ve **şirket portalı** yazın.

3.  Sonuçlar listesinde **Şirket Portalı** &gt; **Yükle**’ye dokunun.

4.  **Yükle** veya **Ücretsiz**’e dokunun. Gösterilen seçenek, şirketinizin uygulamayı nasıl yapılandırdığına bağlıdır.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

### Ayrıca bkz.
[Windows cihazınızı Intune ile kullanma](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO3-->


