---
title: Cihazınızda bir sertifika eksik | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 25ec84946aec9562aedce12b4199269f8de06f76
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72500021"
---
# <a name="install-missing-certificate-required-by-your-organization"></a>Kuruluşunuz için gereken eksik sertifikayı yükler  

Cihazınız Intune 'a kayıtlı değilse ve gerekli bir sertifika eksikse, Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Gerekli sertifikayı indirmeyi ve cihazınızın kaydedilmesini sağlamak için kullanabileceğiniz iki seçenek vardır. 

- Şirket Portalı uygulamasında tarayıcı erişimini etkinleştirin.
- Şirket veya okul bilgisayarında eksik sertifikayı belirler. Ardından, eksik sertifikayı indirmek için internet 'te arama yapın. 

Önce tarayıcı erişimini etkinleştirme adımlarını izleyin. Bundan sonra cihazınızı kaydedemeye devam ediyorsanız, sertifikayı Internet 'te bulmak için adımları izleyin. 

## <a name="enable-browser-access"></a>Tarayıcı erişimini etkinleştir
Tarayıcı erişimini etkinleştirmek için bu adımları izleyin. Erişimi etkinleştirdikten sonra, Şirket Portalı uygun sertifikayı yükleyecek ve kayıt işlemine devam edecektir.    

1. Şirket Portalı uygulamasında sağ köşeye gidin ve menüyü seçin.  
2. **Ayarlar**’ı seçin.  
3. **Tarayıcı erişimini etkinleştir** ' ın yanında **Etkinleştir**' i seçin.  
4. Cihaz Yöneticisi ekranında **Etkinleştir**' i seçin. 

## <a name="identify-and-download-the-missing-certificate-through-web-search"></a>Web araması aracılığıyla eksik sertifikayı tanımla ve indir
Sertifikayı cihazınızda el ile tanımlamak ve yüklemek için bu adımları uygulayın.  

1. Bir bilgisayarda Internet Explorer’ı açın. Bu amaçla kullanabileceğiniz bir bilgisayarınız yoksa, şirketinizin destek birimine başvurun. Şirketinizin destek biriminin iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.

2. [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) gidin ve iş veya okul kimlik bilgilerinizle oturum açın.

3. Tarayıcı adres çubuğunun sağ ucunda, aşağıdaki ekran görüntüsünde gösterildiği gibi asma kilide benzeyen simgeyi seçin.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    Asma kilit simgesini görmüyorsanız, devam etmeyin ve şirketinizin destek birimine başvurun. Kilit simgesi güvenli oturum açtığınız anlamına gelir; dolayısıyla bu simgeyi görmüyorsanız devam etmemelisiniz.

4. **Sertifikaları görüntüle**’yi seçin.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. **Sertifika yolu** sekmesini seçin ve ardından Internet 'ten almanız gereken sertifikayı belirleyin. Size gereken sertifikanın adı, önceki örnek ekran görüntüsünde vurgulanan sertifikayla aynı konumda olacaktır.

6. Bing veya Google gibi bir arama motoru kullanarak, önceki bölümde belirlediğiniz eksik sertifikanın adını arayın. Sertifika, “.crt” veya “.pem” gibi farklı "uzantılarla" bitiyor olabilir.

7. Web sitesinden kök sertifikayı indirin.

8. Sertifika indirildikten sonra, cihazınızda en üstten aşağı doğru sürükleyerek bildirimlerinizi açın ve bildirimler listesinde sertifikanın adına dokunun.

4. Aşağıdaki ekran görüntüsünde gösterilen **Sertifikayı Adlandır** iletişim kutusunda varsayılan sertifika adını kabul edin.

5. **Kimlik Bilgisi Kullanımı**’nın **VPN ve uygulamalar için kullanılır** olarak ayarlandığından emin olun ve **Tamam**’a dokunun.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Şirket Portalı uygulamasını kapatın.

7. Şirket Portalı uygulamasını yeniden açın. Artık Şirket Portalı uygulamasında oturum açabilmeniz gerekir. Yardıma ihtiyacınız olursa şirketinizin destek birimiyle iletişime geçin.

Önceki gösterilenle aynı “eksik sertifika” iletisini görüyorsanız ve yordamı zaten izlediyseniz, büyük olasılıkla şirketinizin destek biriminin yüklemenize yardımcı olması gereken bir sertifika daha vardır. Yardım için [Şirket Portalı web sitesinde](https://go.microsoft.com/fwlink/?linkid=2010980) bulunan iletişim bilgilerini kullanarak şirketinizin destek birimine başvurun.

## <a name="next-steps"></a>Sonraki adımlar  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.  
