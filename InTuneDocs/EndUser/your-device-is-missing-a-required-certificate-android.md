---
title: "Cihazınızda gerekli bir sertifika eksik | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3a2daebdb781ce99aa103e7717ffa1b0297cb3a
ms.openlocfilehash: e10de556babc49d4e2f1ebf6ba9c766291d58efd


---


# Cihazınızda gerekli bir sertifika eksik


## Cihazınızda, çoğunlukla telefonunuzda yüklü olarak gelen bir sertifika eksik
Android cihazınız Intune’a kayıtlı değilse ve genellikle telefonunuzda yüklü olarak gelen sertifika, cihazınızda bulunmuyorsa, Android Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Bu sorunu gidermek ve gerekli sertifikayı edinmek için:

1.  Bir tarayıcıda bu [Digicert sertifika sayfasına](https://www.digicert.com/digicert-root-certificates.htm) gidin.

2.  Baltimore CyberTrust Kök sertifikasını (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) bulun ve indirin.

3.  Bildirimlerinizi açmak için ekranın üst kısmından aşağıya doğru çekin ve bildirim listesinde **BaltimoreCyberTrustRoot.crt**’ye dokunun.

4.  **Sertifikayı Adlandır** iletişim kutusunda varsayılan sertifika adını kabul edin.

5. **Kimlik Bilgisi Kullanımı**’nın **VPN ve uygulamalar için kullanılır** olarak ayarlandığından emin olun ve **Tamam**’a dokunun.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Web tarayıcısını ve Şirket Portalı uygulamasını kapatın.

7. Şirket Portalı uygulamasını yeniden açın. Artık Şirket Portalı uygulamasında oturum açabilmeniz gerekir. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin.

## Cihazınızda, BT yöneticinizin gerektirdiği bir sertifika eksik
Android cihazınız Intune’a kayıtlı değilse ve BT yöneticiniz tarafından gerekli olduğu belirtilen bir sertifika cihazınızda bulunmuyorsa, Android Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Zaten bir "eksik sertifika" iletisi gördüyseniz ve [Cihazınızda, çoğunlukla telefonunuzda yüklü olarak gelen bir sertifika eksik](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone) altında verilen adımları izlediyseniz, sorun değil. O, burada belirtilenden farklı bir ileti ve farklı bir sertifikadır; dolasıyla devam edin ve eksik sertifikayı almak için bu bölümdeki adımları izleyin.

Bu sorunu çözmek ve gerekli sertifikayı almak için, uygulamanız gereken iki ana adım vardır:

- Bir şirket veya okul bilgisayarına bakarak eksik sertifikayı belirleyin.
- Cihazınızı kullanarak eksik sertifikayı İnternet’ten indirin.

### Bir şirket veya okul bilgisayarına bakarak eksik sertifikayı belirleme

1. Bir bilgisayarda Internet Explorer’ı açın. Bu amaçla kullanabileceğiniz bir bilgisayarınız yoksa, BT yöneticinize başvurun. BT yöneticinizin kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

2. [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gidin ve iş veya okul kimlik bilgilerinizle oturum açın.

3. Tarayıcı adres çubuğunun sağ ucunda, aşağıda gösterildiği gibi asma kilide benzeyen simgeye tıklayın. Asma kilit simgesini görmüyorsanız, durun ve BT yöneticinize başvurun. Kilit simgesi güvenli oturum açtığınız anlamına gelir; dolayısıyla bu simgeyi görmüyorsanız devam etmemelisiniz.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

4. **Sertifikaları görüntüle**’ye tıklayın.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. **Sertifika** iletişim kutusunun **Sertifika yolu** sekmesine tıklayın ve ardından İnternet’ten almanız gereken sertifikayı belirleyin. Size gereken sertifikanın adı, yukarıdaki örnek ekran görüntüsünde vurgulanan sertifikayla aynı konumda olacaktır.

### Eksik sertifikayı Android mobil cihazınıza indirme ve yükleme

1. Bing veya Google gibi bir arama motoru kullanarak, önceki bölümde belirlediğiniz eksik sertifikanın adını arayın. Sertifika, “.crt” veya “.pem” gibi farklı "uzantılarla" bitiyor olabilir.

2. Web sitesinden kök sertifikayı indirin.

3. Sertifika indirildikten sonra, cihazınızda en üstten aşağı doğru sürükleyerek bildirimlerinizi açın ve bildirimler listesinde sertifikanın adına dokunun.

4. Aşağıda gösterilen **Sertifikayı Adlandır** iletişim kutusunda varsayılan sertifika adını kabul edin.

5. **Kimlik Bilgisi Kullanımı**’nın **VPN ve uygulamalar için kullanılır** olarak ayarlandığından emin olun ve **Tamam**’a dokunun.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Şirket Portalı uygulamasını kapatın.

7. Şirket Portalı uygulamasını yeniden açın. Artık Şirket Portalı uygulamasında oturum açabilmeniz gerekir. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin.

Yukarıda gösterilenle aynı "eksik sertifika" iletisini görüyorsanız ve yukarıdaki adımları zaten izlediyseniz, bunun anlamı büyük olasılıkla BT yöneticinizin yüklemenize yardımcı olmak için gerekli olduğunu belirttiği bir sertifika daha olduğudur. BT yöneticinize başvurun ve sorunu çözmeye yardımcı olacak adımların bulunduğu bu [bağlantıyı](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) ona verin.

### Ayrıca bkz.
[Windows cihazınızı Intune ile kullanma](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO4-->


