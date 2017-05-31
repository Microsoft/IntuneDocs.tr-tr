---
title: "iOS kullanıcılarınız uygulamalarını nasıl alır | Microsoft Docs"
description: "iOS uygulamalarını son kullanıcılara sağlama yöntemleri"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 044723afa95fe1b739570239c81311804617199b
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---


# <a name="how-your-ios-users-get-their-apps"></a>iOS kullanıcılarınız uygulamalarını nasıl alır

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune aracılığıyla dağıttığınız uygulamaları son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın.

**Gerekli uygulamalar**--Platforma bağlı olarak yönetici tarafından gerekli kılınan ve en düşük kullanıcı katılımıyla cihaza yüklenen uygulamalar.

**Kullanılabilir uygulamalar**--Şirket Portalı uygulama listesinde sağlanan ve kullanıcıların isteğe bağlı olarak yüklemeyi seçebileceği uygulamalar.

**Yönetilen uygulamalar**--İlkeler aracılığıyla yönetilebilen ve Intune tarafından “sarmalanmış” veya Intune Mobil Uygulama Yönetimi (MAM) Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalar. Bu uygulamalar Intune tarafından yönetilebilir ve uygulama ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar**--İlkeler aracılığıyla yönetilebilen ve Intune tarafından sarmalanmamış veya Intune MAM SDK’sini içermeyen uygulamalar. Uygulama ilkeleri bu uygulamalara uygulanamaz.

Apple kısıtlamaları, iş kolu ve yönetilen App Store uygulamalarının Şirket Portalı uygulamasında listelenmesini yasaklar. Bu sorunu aşmak amacıyla iOS için Şirket Portalı uygulamasındaki kutucuklar, kullanıcıları tüm uygulamalarda farklı görünümle tek konuma, yani Şirket Portalı web sitesine yönlendirir.

Kayıtlı kullanıcılar, Şirket Portalı uygulamasının Uygulamalar ekranında aşağıdaki kutucuklara dokunarak uygulamalarını alabilir:

- **Tüm Uygulamalar**, [Şirket Portalı web sitesinin](https://portal.manage.microsoft.com) TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirir.

- **Öne Çıkan Uygulamalar**, kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKAN sekmesine götürür.

- **Kategoriler**, Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir.


![iOS Şirket Portalı uygulaması ekranı](./media/ios-cp-app-main-apps-screen.png)

Uygulamaların nasıl ekleneceği ve bu kutucuklara nasıl yerleştirileceği hakkında bilgiler için bkz. [Kaydolmuş cihazlar için Intune’a uygulamalar ekleme](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Ayrıca bkz.
[Android kullanıcılarınız uygulamalarını nasıl alır](how-your-android-users-get-their-apps.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](how-your-windows-users-get-their-apps.md)
