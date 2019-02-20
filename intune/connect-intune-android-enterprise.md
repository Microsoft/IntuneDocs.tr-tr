---
title: Yönetilen Google Play hesabınıza Intune hesabınıza bağlanın.
titlesuffix: Microsoft Intune
description: Yönetilen Google Play hesabınıza Intune hesabınıza bağlanmayı öğreneceksiniz.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0a886359c9a7d789b06851cde7a5c1857b6fd282
ms.sourcegitcommit: 67e4e66e8c05b36c0897fb2955ef68666d22b094
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56427020"
---
# <a name="connect-your-intune-account-to-your-managed-google-play-account"></a>Yönetilen Google Play hesabınıza Intune hesabınıza bağlanın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Desteklemek için [Android kurumsal iş profili](android-work-profile-enroll.md), [tam olarak yönetilen Android Enterprise](android-fully-managed-enroll.md), ve [Android Kurumsal adanmış cihazlar](android-kiosk-enroll.md), Intune kiracınıza bağlanmanız gerekir Yönetilen Google Play hesabınıza hesap.  

> [!NOTE]
> Google ve Microsoft etki alanları arasındaki etkileşim nedeniyle tarayıcı ayarlarınızı değiştirmeniz gerekebilir.  “portal.azure.com” ve “play.google.com” adreslerinin tarayıcınızda aynı güvenlik bölgesinde olduğundan emin olun.

1. Henüz yapmadıysanız, [mobil cihaz yönetimi yetkilisini](mdm-authority-set.md) **Microsoft Intune** olarak ayarlayarak mobil cihaz yönetimine hazırlanın.
2. [Azure portalında Intune](https://aka.ms/intuneportal)’da oturum açın, **Cihaz kaydı** > **Android kaydı** > **Yönetilen Google Play**’i seçin.  Özel bir Intune yönetici rolü kullanıyorsanız bu seçeneğe erişim, Kuruluş Okuma ve Güncelleştirme izinlerini gerektirir.
   
   ![Android kurumsal kayıt ekranı](./media/android-work-bind.png)

3. **Kabul ediyorum**’u seçerek Microsoft’un [Google’a kullanıcı ve cihaz bilgilerini göndermesine](data-intune-sends-to-google.md) izin verin. 
   
4. **Bağlanmak için Google’ı şimdi başlat**’ı seçerek Yönetilen Google Play web sitesini açın. Web sitesi, tarayıcınızda yeni bir sekmede açılır.
  
5. Google'nın oturum açma sayfasında, bu Kiracı için tüm Android kuruluş yönetimi görevleri ile ilişkilendirilecek Google hesabını girin. Bu, şirketinizdeki BT yöneticilerinin Google Play konsolunda uygulama yönetmek ve yayımlamak için paylaştığı Google hesabıdır. Mevcut bir Google hesabını kullanabilir veya yeni bir tane oluşturabilirsiniz. Seçtiğiniz hesabın bir G-Suite etki alanıyla ilişkilendirilmemiş olması gerekir.
    
    > [!Note]
    > Microsoft Edge tarayıcı kullanıyorsanız, sağ üst köşedeki **Oturum aç**’a tıklayarak Google hesabınızda oturum açın.

6. Şirketinizin adını **Kuruluş adı** alanına girin. **Kurumsal mobil yönetim (EMM) sağlayıcısı** alanında **Microsoft Intune** görüntülenmelidir.

7. Android sözleşmesini kabul edin ve **Onayla**’ya tıklayın. İsteğiniz işlenir.

## <a name="disconnect-your-android-enterprise-administrative-account"></a>Android Kurumsal Yönetici hesabınızın bağlantısını kes

Android Kurumsal kaydını ve yönetim kapatabilirsiniz. Bunu yapmak için önce tüm kayıtlı Android kurumsal iş profili cihazları devre dışı bırakmanız gerekir. Ardından, **Bağlantıyı Kes** Android kurumsal iş profili cihazları ve adanmış cihazların kaydını Intune yönetiminde tümünü kaldırmak için konsol kayıtlı. Bu, yönetilen Google Play hesabı ile Intune arasındaki ilişkiyi de kaldırır.

1. Bir Intune yöneticisi olarak [Azure portalında](https://portal.azure.com) **Tüm Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
2. **Cihaz kaydı** > **Android kaydı** > **Yönetilen Google Play** > **Bağlantıyı kes**’i seçin.
3. **Evet**’i seçerek tüm Android kurumsal cihazların Intune bağlantısını kesin ve cihazları yönetimden kaldırın.

## <a name="next-steps"></a>Sonraki adımlar

Yönetilen Google Play hesabınıza bağlandıktan sonra aşağıdakileri yapabilirsiniz [Android kurumsal iş profili cihazları ayarlama](android-work-profile-enroll.md) ve [Android Kurumsal ayrılmış cihazları ayarlama](android-kiosk-enroll.md).
