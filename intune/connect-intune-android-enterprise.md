---
title: Intune hesabınızı Yönetilen Google Play hesabınıza bağlayın.
titleSuffix: Microsoft Intune
description: Intune hesabınızı Yönetilen Google Play hesabınıza bağlamayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19efd0821deeac0e76c60ee67e6230da554391a0
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898022"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Intune hesabınızı Yönetilen Google Play hesabınıza bağlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[Android Kurumsal iş profili](android-work-profile-enroll.md), [Android Kurumsal tam olarak yönetilen](android-fully-managed-enroll.md) ve [Android Kurumsal ayrılmış cihazlar](android-kiosk-enroll.md) için destek sunmak istiyorsanız Intune kiracı hesabınızı Yönetilen Google Play hesabınıza bağlamanız gerekir.  

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

Android Kurumsal kaydı ve yönetimini kapatabilirsiniz. Bunu yapmak için, önce tüm kayıtlı Android Kurumsal iş profili cihazlarını devre dışı bırakmanız gerekir. Ardından, tüm Android Kurumsal iş profili ve ayrılmış cihazlarının kaydını kaldırmak için Intune yönetim konsolunda **Bağlantıyı kes**’i seçin. Bu işlem Yönetilen Google Play hesabı ile Intune arasındaki ilişkiyi de kaldırır.

1. Bir Intune yöneticisi olarak [Azure portalında](https://portal.azure.com) **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
2. **Cihaz kaydı** > **Android kaydı** > **Yönetilen Google Play** > **Bağlantıyı kes**’i seçin.
3. **Evet**’i seçerek tüm Android kurumsal cihazların Intune bağlantısını kesin ve cihazları yönetimden kaldırın.

## <a name="next-steps"></a>Sonraki adımlar

Android kurumsal hesabına bağlandıktan sonra [Android Kurumsal iş profili cihazları ayarlayabilir](android-work-profile-enroll.md) ve [Android Kurumsal ayrılmış cihazları ayarlayabilirsiniz](android-kiosk-enroll.md).
