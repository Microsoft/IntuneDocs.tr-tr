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
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 63595e9905a220c326c315f5932379a9b743d3de
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Android cihazınızda, genellikle telefonunuzda yüklü olarak gelen bir sertifika eksik

Cihazınız Intune’a kayıtlı değilse ve genellikle telefonunuzda yüklü olarak gelen sertifika, cihazınızda bulunmuyorsa Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Bu sorunu [Digicert'in sertifika sayfasından](https://www.digicert.com/digicert-root-certificates.htm) gerekli sertifikayı alarak düzeltebilirsiniz.

1. __Baltimore CyberTrust Root__ sertifikasını bulun ve indirin. Ayrıca doğrudan [buradan](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) indirebilirsiniz.

2. Son bildirimlerinizin listesini görüntülemek için ekranın üst kısmından aşağıya doğru çekin ve **BaltimoreCyberTrustRoot.crt**’ye dokunun.

3. Cihazınız sizden **Sertifikayı Adlandırmanızı** ister. Görüntülenen varsayılan sertifika adını değiştirmeyin.

4. **Kimlik Bilgisi Kullanımı**’nın **VPN ve uygulamalar için kullanılır** olarak ayarlandığından emin olun ve **Tamam**’a dokunun.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. Tarayıcınızı ve Şirket Portalı uygulamasını kapatın.

6. Şirket Portalı uygulamasını yeniden açın. Artık Şirket Portalı uygulamasında oturum açabilmeniz gerekir. Şirket Portalı uygulamasını hâlâ kullanamıyorsanız, daha fazla yönerge için [Şirket Portalı web sitesinde](http://portal.manage.microsoft.com) sağlanan bilgileri kullanarak BT yöneticinize başvurun.

>[!NOTE]
> Bu sertifikayı yüklemek sorunu çözmezse ve farklı bir “eksik sertifika” hatası alırsanız, [eksik sertifikayı yüklemek için](your-device-is-missing-an-IT-required-certificate-android.md) ek adımlar uygulamanız gerekir.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

