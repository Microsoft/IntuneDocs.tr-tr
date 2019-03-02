---
title: iOS kullanıcılarınız uygulamalarını nasıl alır
description: iOS uygulamalarını son kullanıcılara sağlama yöntemleri
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/28/2016
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1928af6db94993cd385faa01473cacc6cab7fd2b
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236713"
---
# <a name="how-your-ios-users-get-their-apps"></a>iOS kullanıcılarınız uygulamalarını nasıl alır

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Microsoft Intune aracılığıyla dağıttığınız uygulamaları son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın.

**Gerekli uygulamalar**--Platforma bağlı olarak yönetici tarafından gerekli kılınan ve en düşük kullanıcı katılımıyla cihaza yüklenen uygulamalar.

**Kullanılabilir uygulamalar**--Şirket Portalı uygulama listesinde sağlanan ve kullanıcıların isteğe bağlı olarak yüklemeyi seçebileceği uygulamalar.

**Yönetilen uygulamalar**--İlkeler aracılığıyla yönetilebilen ve Intune tarafından “sarmalanmış” veya Intune Uygulama Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalardır. Bu uygulamalar Intune tarafından yönetilebilir ve bunlara uygulama koruma ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar**--İlkeler aracılığıyla yönetilebilen ve Intune tarafından sarmalanmamış veya Intune Uygulama SDK’sını içermeyen uygulamalardır. Uygulama ilkeleri bu uygulamalara uygulanamaz.

Apple kısıtlamaları, iş kolu ve yönetilen App Store uygulamalarının Şirket Portalı uygulamasında listelenmesini yasaklar. Bu sorunu aşmak amacıyla iOS için Şirket Portalı uygulamasındaki kutucuklar, kullanıcıları tüm uygulamalarda farklı görünümle tek konuma, yani Şirket Portalı web sitesine yönlendirir.

Kayıtlı kullanıcılar, Şirket Portalı uygulamasının Uygulamalar ekranında aşağıdaki kutucuklara dokunarak uygulamalarını alabilir:

- **Tüm Uygulamalar**, [Şirket Portalı web sitesinin](https://portal.manage.microsoft.com) TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirir.

- **Öne Çıkan Uygulamalar**, kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKAN sekmesine götürür.

- **Kategoriler**, Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir.


![iOS Şirket Portalı uygulaması ekranı](./media/ios-cp-app-main-apps-screen.png)

Uygulama ekleme hakkında bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

### <a name="see-also"></a>Ayrıca bkz.
[Android kullanıcılarınız uygulamalarını nasıl alır](end-user-apps-android.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](end-user-apps-windows.md)
