---
title: Veri şifreleme ile şirket verilerini koruma
description: Bu kılavuz, mobil uygulamalar üzerinde kullanılan bir ilkeyle geçiş kodu ve veri şifrelemesi uygulamayı zorunlu hale getirerek şirketinizi veri kaybına karşı korumanıza yardımcı olabilir.
keywords: şifreleme, PIN, veri
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/22/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 084da36e9b417e4faee87f33bbd42e0e5f5fa7e2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="quick-start-guide-protect-company-data-with-data-encryption"></a>Hızlı Başlangıç Kılavuzu: Veri şifreleme ile şirket verilerini koruma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune, Office mobil uygulamalarından veri kaybını aşağıdakileri içeren çeşitli yollarla önlemenize yardımcı olabilir:
- iOS ve Android tarafından sağlanan en yüksek düzeyde cihaz şifrelemesi ile kurumsal verileri şifreleyerek.
- Gizlilik veya yasal gereksinimler nedeniyle mobil cihaz yönetimi çözümüne kaydedilemeyen iOS ve Android cihazlarda.

Microsoft Intune ayrıca, Office mobil uygulamalarından ve güvenli Office 365 (O365) verilerinden veri kaybını, iOS veya Android mobil cihazları tam mobil cihaz yönetimine kaydetmeye gerek kalmadan engellemenize yardımcı olabilir. Bu, mobil cihazları yönetmek için bir üçüncü taraf mobil cihaz yönetimi çözümü kullansanız bile geçerlidir.

## <a name="is-this-quick-start-guide-right-for-me"></a>Bu hızlı başlangıç kılavuzu bana uygun mu?
Bu hızlı başlangıç kılavuzu aşağıdaki önkoşulları karşılıyorsanız iyi bir kaynaktır:
- O365 lisansları kullanıyorsunuz veya kullanmak istediğiniz O365 lisanslarınız var ve Office mobil uygulamaları yönetiyorsunuz.
- Office mobil uygulamaları iOS veya Android üzerinde kullanmayı planlıyorsunuz.
- Microsoft veya Microsoft olmayan herhangi bir cihaz yönetimi çözümü kullanıyorsunuz. Tüzük nedeniyle bir mobil cihaz yönetim çözümü kullanamıyorsanız, bu kılavuzdan faydalanabilirsiniz.

> [!NOTE]
> Windows henüz Office mobil uygulamalar için desteklenen bir platform değildir. Kayıt olmadan mobil uygulama yönetimi henüz Exchange veya SharePoint şirket içi ile uyumlu değildir. Yalnızca çevrimiçi sürümlerde barındırılan verileri koruyabilirsiniz.

Bu kılavuz, herhangi bir cihaz yönetimi çözümüne kaydolma gereksinimi olmadan, çalışanlarınızın hassas verilere erişmek için kullandığı mobil uygulamalarda kullanılan ilkelerle geçiş kodları ve veri şifrelemeyi zorunlu hale getirerek şirketinizi veri kaybından korumanıza yardımcı olabilir. Microsoft Intune, [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) ve [Android](https://products.office.com/mobile/office-mobile-apps-for-android) için Office mobil uygulamalarında mobil uygulama yönetimi (MAM) ilkeleri ayarlamanıza olanak tanır. Bu yaklaşım, kullanıcıların cihazlarını bir mobil cihaz yönetimi çözümüne kaydetmelerini gerektirmeden O365 verilerini korurken Office mobil uygulamalarında da çok iyi bir son kullanıcı deneyimi sağlar.

## <a name="how-do-i-do-it"></a>Bunu nasıl yaparım?
1.  [Uygulama verilerinizi nasıl koruyabileceğinizi gözden geçirme](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
2.  [Mobil uygulama yönetimi ilkelerini yapılandırmak için hazırlama](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
3.  [Mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="additional-information"></a>Ek bilgiler:
- [MAM etkin uygulamalar için Microsoft Intune ile son kullanıcı deneyimi hakkında bilgi edinin.](/intune-classic/eploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verin.](/intune/apps-prepare-mobile-application-management)
- [Microsoft Intune uygulaması iş ortaklarının listesini görüntüleme](https://www.microsoft.com/cloud-platform/microsoft-intune-partners)
