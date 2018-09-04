---
title: Microsoft Intune kullanarak Windows 10 uygulaması dağıtımı
titlesuffix: ''
description: Microsoft Intune ile sağlanan Windows 10 uygulaması senaryoları hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7508f2c2eca06ceacf203103ab2cad53abc39a65
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347441"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Microsoft Intune kullanarak Windows 10 uygulaması dağıtımı 

Microsoft Intune şu anda Windows 10 cihazlarında çeşitli uygulama türlerini ve dağıtım senaryolarını destekler. Intune’a bir uygulama ekledikten sonra uygulamayı kullanıcılara ve cihazlara atayabilirsiniz. Aşağıdaki bilgiler, desteklenen Windows 10 senaryolarıyla ilgili daha fazla ayrıntı sağlar. Buna ek olarak, aşağıdaki bilgilerde uygulamaları Windows'a dağıtırken dikkat edilecek önemli ayrıntılar da sağlanır. 

Windows 10 cihazlarında desteklenen uygulama türleri İş kolu (LOB) uygulamaları ve İş için Microsoft Store uygulamalarıdır.

> [!Note]
> Uygulamaları cihaz bağlamında dağıtmak için gereken en düşük Windows 10 güncelleştirmesi: [23 Mayıs 2018—KB4100403 (İşletim Sistemi Derlemesi 17134.81)](https://support.microsoft.com/en-us/help/4100403/windows-10-update-kb4100403).

## <a name="windows-10-line-of-business-apps"></a>Windows 10 İş kolu uygulamaları

Windows 10 LOB uygulamaları imzalanır ve Intune yönetim konsoluna yüklenir. Bunlar hem Evrensel Windows Platformu (UWP) uygulamaları ve Windows Uygulama Paketleri (AppX) gibi modern uygulamaları hem de basit Microsoft Installer paket dosyaları (MSI) gibi Win 32 uygulamalarını içerebilir. LOB uygulamalarının güncelleştirmeleri her seferinde yönetici tarafından el ile karşıya yüklenmeli ve dağıtılmalıdır. Dağıtılan güncelleştirmeler, uygulamayı yüklemiş olan son kullanıcı cihazlarına kullanıcı müdahalesine gerek kalmadan otomatik olarak yüklenir. Kullanıcının güncelleştirmeler üzerinde hiçbir denetimi yoktur. 

## <a name="microsoft-store-for-business-apps"></a>İş uygulamaları için Microsoft Mağazası

İş için Microsoft Store uygulamaları, İş için Microsoft Store yönetim portalından satın alınan ve ardından yönetim için Microsoft Intune üzerinden eşitlenen modern uygulamalardır. Uygulamalar **çevrimiçi lisanslanabileceği** gibi **çevrimdışı da lisanslanabilir**. İş için Microsoft Store güncelleştirmeleri doğrudan Microsoft Store tarafından yönetilir; yöneticinin ek işlemler yapması gerekmez. Yönetici ayrıca özel Tekdüzen Kaynak Tanımlayıcısı (URI) kullanarak belirli uygulamalarda güncelleştirme yapılmasını engelleyebilir. Daha fazla bilgi için bkz. [Kurumsal uygulama yönetimi - Uygulamaların otomatik güncelleştirmeleri almasını engelleme](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Cihazda, son kullanıcı cihazdaki tüm İş için Microsoft Store uygulamalarında da güncelleştirmeleri devre dışı bırakabilir. 

## <a name="installing-apps-on-windows-10-devices"></a>Windows 10 cihazlarına uygulamaları yükleme
Uygulama türüne bağlı olarak, uygulama Windows 10 cihazına iki yoldan biriyle yüklenebilir:

- **Kullanıcı Bağlamı**: Uygulama kullanıcı bağlamında dağıtılırsa, kullanıcı cihazda oturum açtığında yönetilen uygulama cihaza o kullanıcı için yüklenir. Kullanıcı cihazda oturum açana kadar uygulama yükleme işleminin başarılı olmayacağını unutmayın. 
    - Modern iş kolu uygulamaları ve İş için Microsoft Store uygulamaları (hem çevrimiçi hem de çevrimdışı) kullanıcı bağlamında dağıtılabilir ve hem Gerekli hem de Kullanılabilir amacını destekler.
- **Cihaz Bağlamı**: Uygulama cihaz bağlamında dağıtılırsa, yönetilen uygulama Intune tarafından doğrudan cihaza yüklenir.
    - Yalnızca modern iş kolu uygulamaları ve İş için Microsoft Store uygulamaları cihaz bağlamında dağıtılabilir ve yalnızca Gerekli amacını destekler.

> [!Note]
> Cihaz bağlamında MDM üzerinde MSI dağıtımı yapılması Windows 10 cihazlarında henüz desteklenmiyor.

Bir uygulama cihaz bağlamında dağıtıldığında, yüklemenin başarılı olması için cihaz bağlamını destekleyen bir cihazın hedeflenmesi gerekir. Buna ek olarak, cihaz bağlamında dağıtım aşağıdaki koşulları destekler:
- Uygulama cihaz bağlamında dağıtılıyorsa ve bir kullanıcıyı hedefliyorsa, yükleme işlemi başarısız olur ve yönetici konsolunda şu durum ve hata görüntülenir:
    - Durum: Başarısız.
    - Error: Cihaz bağlamı yüklemesinde kullanıcı hedeflenemez.
- Uygulama cihaz bağlamında dağıtılıyorsa ama cihaz bağlamını desteklemeyen bir cihazı hedefliyorsa, yükleme işlemi başarısız olur ve yönetici konsolunda şu durum ve hata görüntülenir:
    - Durum: Başarısız.
    - Hata: Bu platform cihaz bağlamı yüklemelerini desteklemiyor. 

> [!Note]
> Uygulama ataması belirli bir dağıtımla kaydedildikten sonra, modern uygulamalar dışında bu atama için bağlam değiştirilemez. Modern uygulamalar söz konusu olduğunda, bağlam değiştirilip kullanıcı bağlamından cihaz bağlamına geçilebilir. 

Tek bir kullanıcı/cihaz üzerinde ilkelerde çalışma olması durumunda, son ilkeyi saptamak için aşağıdaki ilke öncelikleri kullanılacaktır:
- Cihaz bağlamı ilkesi, kullanıcı bağlamı ilkesinden daha yüksek önceliklidir. 
- Yükleme ilkesi, kaldırma ilkesinden daha yüksek önceliklidir.

Microsoft Intune kullanarak uygulama atama hakkında daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md) ve [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md). Intune'daki uygulama türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).

## <a name="next-steps"></a>Sonraki adımlar

- Uygulamaları gruplara atama hakkında daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).
- Uygulama atamalarını izleme hakkında daha fazla bilgi edinmek için bkz. [Uygulamaları izleme](apps-monitor.md).
