---
title: "Cihazınızda gerekli bir sertifika eksik | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ms.reviewer: arnab
ms.suite: ems
ms.sourcegitcommit: 0bb435b87c937ea118a0794c8332b9a8f268d36e
ms.openlocfilehash: 6e887d226228d073dc136b50ba9320ada996a6cd


---


# Cihazınızda gerekli bir sertifika eksik
Android cihazınız Intune’a kayıtlı değilse ve genellikle telefonunuzda yüklü olarak gelen sertifika, cihazınızda bulunmuyorsa, Android Şirket Portalı uygulamasında oturum açamazsınız. Oturum açmaya çalıştığınızda şu iletiyi görürsünüz:

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

Bu sorunu gidermek ve gerekli sertifikayı edinmek için:

1.  Bir tarayıcıda bu [Digicert sertifika sayfasına](https://www.digicert.com/digicert-root-certificates.htm) gidin.

2.  Baltimore CyberTrust Kök sertifikasını (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) bulun ve indirin.

3.  Bildirimlerinizi açmak için ekranın üst kısmından aşağıya doğru çekin ve bildirim listesinde **BaltimoreCyberTrustRoot.crt**’ye dokunun.

4.  **Sertifikayı Adlandır** iletişim kutusunda varsayılan sertifika adını kabul edin.

5. **Kimlik Bilgisi Kullanımı**’nın **VPN ve uygulamalar için kullanılır** olarak ayarlandığından emin olun ve **Tamam**’a dokunun.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Web tarayıcısını ve Şirket Portalı uygulamasını kapatın.

7. Şirket Portalı uygulamasını yeniden açın. Artık Şirket Portalı uygulamasında oturum açabilmeniz gerekir. Yardıma ihtiyacınız olursa BT yöneticinizle iletişime geçin.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.


<!--HONumber=Jun16_HO4-->


