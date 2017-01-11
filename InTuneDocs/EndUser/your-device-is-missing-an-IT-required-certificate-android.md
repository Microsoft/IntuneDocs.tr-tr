---
title: "Cihazınızda bir sertifika eksik | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6fcfac7c8bd469f5163ec9b4017ae8c3d486428
ms.openlocfilehash: 88770ba06718a767f8229e1b5aa4d543c87bc852

---

# <a name="your-android-device-is-missing-a-certificate-required-by-your-it-admin"></a>Android cihazınızda, BT yöneticinizin gerekli kıldığı bir sertifika eksik

Cihazınız Intune’a kayıtlı değilse ve BT yöneticiniz tarafından gerekli kılınan bir sertifika cihazınızda bulunmuyorsa, Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Bu sorunu düzeltmek ve gerekli sertifikayı almak için uygulamanız gereken iki temel adım vardır:

- Bir şirket veya okul bilgisayarına bakarak eksik sertifikayı belirleyin.
- Cihazınızı kullanarak eksik sertifikayı İnternet’ten indirin.

## <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a>Bir şirket veya okul bilgisayarına bakarak eksik sertifikayı belirleme

1. Bir bilgisayarda Internet Explorer’ı açın. Bu amaçla kullanabileceğiniz bir bilgisayarınız yoksa, BT yöneticinize başvurun. BT yöneticinizin iletişim bilgileri için [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) bakın.

2. [Şirket Portalı web sitesine](http://portal.manage.microsoft.com) gidin ve iş veya okul kimlik bilgilerinizle oturum açın.

3. Tarayıcı adres çubuğunun sağ ucunda, aşağıdaki ekran görüntüsünde gösterildiği gibi asma kilide benzeyen simgeyi seçin.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    Asma kilit simgesini görmüyorsanız, durun ve BT yöneticinize başvurun. Kilit simgesi güvenli oturum açtığınız anlamına gelir; dolayısıyla bu simgeyi görmüyorsanız devam etmemelisiniz.

4. **Sertifikaları görüntüle**’yi seçin.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. **Sertifika** iletişim kutusunda **Sertifika yolu** sekmesini seçin ve ardından İnternet’ten almanız gereken sertifikayı belirleyin. Size gereken sertifikanın adı, önceki örnek ekran görüntüsünde vurgulanan sertifikayla aynı konumda olacaktır.

## <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a>Eksik sertifikayı Android mobil cihazınıza indirme ve yükleme

1. Bing veya Google gibi bir arama motoru kullanarak, önceki bölümde belirlediğiniz eksik sertifikanın adını arayın. Sertifika, “.crt” veya “.pem” gibi farklı "uzantılarla" bitiyor olabilir.

2. Web sitesinden kök sertifikayı indirin.

3. Sertifika indirildikten sonra, cihazınızda en üstten aşağı doğru sürükleyerek bildirimlerinizi açın ve bildirimler listesinde sertifikanın adına dokunun.

4. Aşağıdaki ekran görüntüsünde gösterilen **Sertifikayı Adlandır** iletişim kutusunda varsayılan sertifika adını kabul edin.

5. **Kimlik Bilgisi Kullanımı**’nın **VPN ve uygulamalar için kullanılır** olarak ayarlandığından emin olun ve **Tamam**’a dokunun.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Şirket Portalı uygulamasını kapatın.

7. Şirket Portalı uygulamasını yeniden açın. Artık Şirket Portalı uygulamasında oturum açabilmeniz gerekir. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin.

Az önce gösterilenle aynı "eksik sertifika" iletisini görüyorsanız ve yordamı zaten izlediyseniz, büyük olasılıkla BT yöneticinizin yüklemenize yardımcı olması gereken bir sertifika daha vardır. Yardım için [Şirket Portalı web sitesinde](http://portal.manage.microsoft.com) bulunan iletişim bilgilerini kullanarak BT yöneticinize başvurun.



<!--HONumber=Jan17_HO1-->


