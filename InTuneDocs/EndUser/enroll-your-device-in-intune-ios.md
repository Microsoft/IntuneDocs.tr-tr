---
title: "iOS cihazınızı Intune’a kaydetme | Microsoft Docs"
description: "iOS cihazının Intune’a nasıl kaydedildiği açıklanır"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- Company Portal
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 58295c0e27c6c74a1efb9771e0fe8fb917c6cca6


---


# <a name="enroll-your-ios-device-in-intune"></a>iOS cihazınızı Intune'a kaydetme

Şirketinizde veya okulunuzda Microsoft Intune kullanılıyorsa, şirket e-postasına, dosyalarına ve diğer kaynaklarına erişmek için iOS cihazınızı kaydedebilirsiniz. Cihazlarınızı kaydettiğinizde, BT departmanınız bu iş veya okul kaynaklarını yönetebilir, bunların güvenli kalmasını sağlayabilir ve size işlerinizi tamamlamak için tercih ettiğiniz cihazı kullanma özgürlüğünü tanıyabilir. Kayıt hakkında daha fazla bilgi edinmek için bkz. [Şirket Portalı uygulamasını yüklerseniz ve cihazınızı Intune’a kaydederseniz ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

Bir Mac OS cihazı kaydetmeye çalışıyorsanız, bkz. [Mac OS cihazınızı Intune'a kaydetme](enroll-your-device-in-intune-macos.md).

**Başlamadan önce:**

- Adımları başlattıktan sonra kaydetme işlemini tamamladığınızdan emin olun. Başlatırsanız ancak tamamlamazsanız, tekrar denediğinizde kayıt çalışmayabilir.
- Wi-Fi ağınızın çalışır durumda olduğundan emin olun. Aksi durumda kayıt başarısız olur.
- Cihazınızda Safari engellenmişse, engeli kaldırın. Kaydetmek için Safari kullanmanız gerekir.


**iOS cihazınızı kaydetmek için:**

1.  [Intune Şirket Portalı uygulamasını yükleme ve uygulamada oturum açma](install-and-sign-in-to-the-intune-company-portal-app-ios.md) başlığı altında verilen adımları izleyin.

2. **Şirket Erişimi Kurulumu** sayfasında, **Başla**’ya dokunun.

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. **Cihazınızı neden kaydetmelisiniz?** ekranında, cihazınızı kaydettiğinizde neler yapabileceğinizi okuyun ve sonra **Devam**’a dokunun.

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

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

12. **Şirket Erişimi Kurulumu** ekranında, **Devam**’a dokunun. BT yöneticiniz, parola belirleme ihtiyacı gibi ek güvenlik gereksinimleri ayarlarsa, tüm uyum gereksinimlerini karşılayana ve Şirket Erişimi Kurulumu ekranına geri döndürülene kadar ekrandaki yönergeleri izleyin ve sonra **Devam**’a dokunun.

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. **Bitti**’ye dokunun.

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

Cihazınız artık Intune'a kaydedilmiştir ve sonra Şirket Portalı uygulamasına geri götürülürsünüz.


Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Dec16_HO2-->


