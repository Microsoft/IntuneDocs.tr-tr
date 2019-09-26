---
title: Intune hesabınızı Yönetilen Google Play hesabınıza bağlayın.
titleSuffix: Microsoft Intune
description: Intune hesabınızı Yönetilen Google Play hesabınıza bağlamayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bebf4e6fa5ed9e37937be6e7d25b6bd7a6523c23
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71303969"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Intune hesabınızı Yönetilen Google Play hesabınıza bağlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[Android Kurumsal iş profili](android-work-profile-enroll.md), [Android Kurumsal tam olarak yönetilen](android-fully-managed-enroll.md) ve [Android Kurumsal ayrılmış cihazlar](android-kiosk-enroll.md) için destek sunmak istiyorsanız Intune kiracı hesabınızı Yönetilen Google Play hesabınıza bağlamanız gerekir.  

Android kurumsal yönetimini yapılandırıp kullanmanızı kolaylaştırmak için Google Play 'e bağlandıktan sonra Intune, Intune yönetim konsoluna dört ortak Android kurumsal ilgili uygulamayı otomatik olarak ekler. Dört Android kurumsal uygulaması şunlardır:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** -Android kurumsal tam olarak yönetilen senaryolar için kullanılır.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** -iki öğeli doğrulama kullanırsanız hesaplarınızda oturum açmanıza yardımcı olur.
- **[Intune şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** -uygulama koruma ILKELERI (uygulama) ve Android kurumsal iş profili senaryoları için kullanılır.
- [Yönetilen giriş ekranı](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise) -Android kurumsal adanmış/bilgi noktası senaryolarında kullanılır.

> [!NOTE]
> Google ve Microsoft etki alanları arasındaki etkileşim nedeniyle tarayıcı ayarlarınızı değiştirmeniz gerekebilir.  “portal.azure.com” ve “play.google.com” adreslerinin tarayıcınızda aynı güvenlik bölgesinde olduğundan emin olun.

1. Henüz yapmadıysanız, [mobil cihaz yönetimi yetkilisini](mdm-authority-set.md) **Microsoft Intune** olarak ayarlayarak mobil cihaz yönetimine hazırlanın.
2. [Azure portalında Intune](https://aka.ms/intuneportal)’da oturum açın, **Cihaz kaydı** > **Android kaydı** > **Yönetilen Google Play**’i seçin.  Özel bir Intune yönetici rolü kullanıyorsanız bu seçeneğe erişim, Kuruluş Okuma ve Güncelleştirme izinlerini gerektirir.
   
   ![Android kurumsal kayıt ekranı](./media/android-work-bind.png)

3. **Kabul ediyorum**’u seçerek Microsoft’un [Google’a kullanıcı ve cihaz bilgilerini göndermesine](data-intune-sends-to-google.md) izin verin. 
   
4. **Bağlanmak için Google’ı şimdi başlat**’ı seçerek Yönetilen Google Play web sitesini açın. Web sitesi, tarayıcınızda yeni bir sekmede açılır.
  
5. Google’ın oturum açma sayfasında, bu kiracı için tüm Android Kurumsal yönetim görevleriyle ilişkilendirilecek Google hesabını girin. Bu, şirketinizdeki BT yöneticilerinin Google Play konsolunda uygulama yönetmek ve yayımlamak için paylaştığı Google hesabıdır. Mevcut bir Google hesabını kullanabilir veya yeni bir tane oluşturabilirsiniz. Seçtiğiniz hesabın bir G-Suite etki alanıyla ilişkilendirilmemiş olması gerekir.
    
    > [!Note]
    > Microsoft Edge tarayıcı kullanıyorsanız, sağ üst köşedeki **Oturum aç**’a tıklayarak Google hesabınızda oturum açın.

6. Şirketinizin adını **Kuruluş adı** alanına girin. **Kurumsal mobil yönetim (EMM) sağlayıcısı** alanında **Microsoft Intune** görüntülenmelidir.

7. Android sözleşmesini kabul edin ve **Onayla**’ya tıklayın. İsteğiniz işlenir.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Android Kurumsal yönetici hesabınızın bağlantısını kesme

Android Kurumsal kaydı ve yönetimini kapatabilirsiniz. Bunu yapmak için, önce iş profili aygıtları, adanmış cihazlar ve tam olarak yönetilen cihazlar dahil tüm kayıtlı Android kurumsal cihazlarını devre dışı bırakmanız gerekir. Ardından, kayıtlı tüm Android kurumsal iş profili cihazlarını, adanmış cihazları ve tam olarak yönetilen cihazları kayıttan kaldırmak için Intune yönetim konsolunda **bağlantıyı kes** ' i seçin. Bu işlem Yönetilen Google Play hesabı ile Intune arasındaki ilişkiyi de kaldırır.

1. Bir Intune Yöneticisi olarak [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz kaydı** > **Android kaydı** > **Yönetilen Google Play** > **Bağlantıyı kes**’i seçin.
3. **Evet**’i seçerek tüm Android kurumsal cihazların Intune bağlantısını kesin ve cihazları yönetimden kaldırın.

## <a name="next-steps"></a>Sonraki adımlar

Yönetilen Google Play hesabına bağlandıktan sonra, [Android kurumsal iş profili cihazlarını ayarlayabilir](android-work-profile-enroll.md), [Android kurumsal adanmış cihazları ayarlayabilir](android-kiosk-enroll.md) ve [Android kurumsal tam yönetilen cihazları ayarlayabilirsiniz](android-kiosk-enroll.md)
