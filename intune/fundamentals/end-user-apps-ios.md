---
title: iOS kullanıcılarınız uygulamalarını nasıl alır
description: iOS uygulamalarını son kullanıcılara sağlama yöntemleri
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc298691ea3df923d1804005be61217325f52112
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510276"
---
# <a name="how-your-ios-users-get-their-apps"></a>iOS kullanıcılarınız uygulamalarını nasıl alır

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Microsoft Intune aracılığıyla dağıttığınız uygulamaları son kullanıcılarınızın nasıl ve nereden alacağını anlamak için bu bilgileri kullanın.

**Gerekli uygulamalar**--Platforma bağlı olarak yönetici tarafından gerekli kılınan ve en düşük kullanıcı katılımıyla cihaza yüklenen uygulamalar.

**Kullanılabilir uygulamalar**--Şirket Portalı uygulama listesinde sağlanan ve kullanıcıların isteğe bağlı olarak yüklemeyi seçebileceği uygulamalar.

**Yönetilen uygulamalar**--İlkeler aracılığıyla yönetilebilen ve Intune tarafından “sarmalanmış” veya Intune Uygulama Yazılım Geliştirme Seti (SDK) ile oluşturulmuş uygulamalardır. Bu uygulamalar Intune tarafından yönetilebilir ve bunlara uygulama koruma ilkeleri uygulanabilir.

**Yönetilmeyen uygulamalar**--kullanıcıların Intune uygulama SDK 'sı ile tümleştirilen IOS App Store 'dan indirebileceği uygulamalar. Intune, bu uygulamaların dağıtım, yönetim veya seçmeli silme üzerinde herhangi bir denetime sahip değildir.  

Apple kısıtlamaları, iş kolu ve yönetilen App Store uygulamalarının Şirket Portalı uygulamasında listelenmesini yasaklar. Bu sorunu aşmak amacıyla iOS için Şirket Portalı uygulamasındaki kutucuklar, kullanıcıları tüm uygulamalarda farklı görünümle tek konuma, yani Şirket Portalı web sitesine yönlendirir.

Kayıtlı kullanıcılar, Şirket Portalı uygulamasının Uygulamalar ekranında aşağıdaki kutucuklara dokunarak uygulamalarını alabilir:

- **Tüm Uygulamalar**, [Şirket Portalı web sitesinin](https://portal.manage.microsoft.com) TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirir.

- **Öne Çıkan Uygulamalar**, kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKAN sekmesine götürür.

- **Kategoriler**, Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir.


![iOS Şirket Portalı uygulaması ekranı](./media/end-user-apps-ios/ios-cp-app-main-apps-screen.png)

Uygulama ekleme hakkında bilgi için bkz. [Microsoft Intune’a uygulama ekleme](../apps/apps-add.md).

## <a name="see-also"></a>Ayrıca bkz:
[Android kullanıcılarınız uygulamalarını nasıl alır](end-user-apps-android.md)

[Windows kullanıcılarınız uygulamalarını nasıl alır](end-user-apps-windows.md)
