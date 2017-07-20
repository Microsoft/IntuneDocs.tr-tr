---
title: "iOS cihazınızı Intune’a kaydetme | Microsoft Docs"
description: "iOS cihazının Intune’a nasıl kaydedildiği açıklanır"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 4d7ad138a8aa59ceeff00866469e59e2e1d19520
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2017
---
# <a name="enroll-your-ios-device-in-intune"></a>iOS cihazınızı Intune'a kaydetme

Şirketinizde veya okulunuzda Microsoft Intune kullanılıyorsa, şirket e-postasına, dosyalarına ve diğer kaynaklarına erişmek için iOS cihazınızı kaydedebilirsiniz. Cihazlarınızı kaydettiğinizde, BT departmanınız bu iş veya okul kaynaklarını yönetebilir, bunların güvenli kalmasını sağlayabilir ve size işlerinizi tamamlamak için tercih ettiğiniz cihazı kullanma özgürlüğünü tanıyabilir. Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklerseniz ve cihazınızı Intune’a kaydederseniz ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
> MacBook Pro veya iMac gibi bir macOS cihazı kaydetmek istiyorsanız [buradaki yönergeleri deneyin](enroll-your-device-in-intune-macos.md).

**Başlamadan önce:**

- Adımları başlattıktan sonra kaydetme işlemini tamamladığınızdan emin olun. Birkaç dakikadan uzun bir süre duraklatmak genellikle işlemi durdurur ve yeniden başlatmanızı gerektirir.
- Herhangi bir nedenle kaydolamazsanız yeniden denemek için Şirket Portalı uygulamasına dönmeniz gerekir.
- Wi-Fi ağınızın çalışır durumda olduğundan emin olun. Aksi durumda kayıt başarısız olur.
- Cihazınızda Safari engellenmişse, engeli kaldırın. Cihaz kayıt işleminin bir parçası olarak Safari kullanılır.


**iOS cihazınızı kaydetmek için:**

1.  [Intune Şirket Portalı uygulamasını yükleme ve uygulamada oturum açma](install-and-sign-in-to-the-intune-company-portal-app-ios.md) başlığı altında verilen adımları izleyin.

2. **Şirket Erişimi Kurulumu** sayfasında, **Başla**’ya dokunun.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. **Cihazınızı neden kaydetmelisiniz?** ekranında, cihazınızı kaydettiğinizde neler yapabileceğinizi okuyun ve sonra **Devam**’a dokunun.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

  > [!NOTE]
  > Sarı üçgenler herhangi bir hata olduğu anlamına gelmez. Bu simgeler, kayıt işleminde hala tamamlanması gereken adımlar olduğunu gösterir.

4. BT yöneticinizin kayıtlı cihazınızda neleri görebileceğini ve neleri göremeyeceğini içeren listeyi gözden geçirip **Devam**’a dokunun.

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  **Sıradaki** ekranında, kayıt sırasında ne olduğunu okuyun ve **Kaydet**’e dokunun.

    ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  **Yükleme Profili** ekranında **Yükle**’ye dokunun ve istenirse geçiş kodunuzu girin.

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  **Yükle**’ye dokunun.

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  Uyarıyı okuduğunuzu belirtmek için **Yükle**’ye dokunun.

    ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  **Güven**’e dokunun.

    ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  Ekran değişerek profilin yüklenmesinin tamamlandığını gösterdiğinde, **Bitti**’ye dokunun.

    ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    Ekranda bir "Cihaz kaydediliyor" iletisi görünür.

11.  Sayfayı Şirket Portalı’nda açmak isteyip istemediğiniz sorulan bir ileti görüntülendiğinde, **Aç**’a dokunun.

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

12. **Şirket Erişimi Kurulumu** ekranında, **Devam**’a dokunun. Bu ekranda, cihazınızı uyumlu hale getirmek için bir parola ayarlamak gibi karşılamanız gereken diğer gereksinimler gösterilir. Tüm uyumluluk gereksinimlerine uyana kadar ekrandaki yönergeleri izleyin. İşiniz bittiğinde Şirket Erişimi Kurulum ekranına dönersiniz. **Devam**’a dokunun.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. **Bitti**’ye dokunun.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Cihazınız artık Intune'a kaydedilmiştir ve sonra Şirket Portalı uygulamasına geri götürülürsünüz.

> [!Note]
> Cihazınız tamamen kurulmadan önce birkaç adım daha kaldı. [Telekom gider yönetimini kullanarak cihazınızı kaydetme](enroll-your-device-with-telecom-expense-management-ios.md) hakkında daha fazla bilgi edinin. Kuruluşunuz Apple’ın Aygıt Kayıt Programı’nı kullanıyorsa [buraya](enroll-your-device-dep-ios.md) tıklayarak daha fazla bilgi edinebilirsiniz.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.
