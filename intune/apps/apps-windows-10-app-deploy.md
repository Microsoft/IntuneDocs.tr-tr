---
title: Microsoft Intune kullanarak Windows 10 uygulama dağıtımı
titleSuffix: ''
description: Microsoft Intune ile kullanılabilen Windows 10 uygulama dağıtım senaryoları hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/25/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 88867e76df3d77aefc96a30c7e198f9d36950c25
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856077"
---
# <a name="windows-10-app-deployment-by-using-microsoft-intune"></a>Microsoft Intune kullanarak Windows 10 uygulama dağıtımı 

Microsoft Intune, Windows 10 cihazlarında çeşitli uygulama türlerini ve dağıtım senaryolarını destekler. Intune’a bir uygulama ekledikten sonra uygulamayı kullanıcılara ve cihazlara atayabilirsiniz. Bu makalede desteklenen Windows 10 senaryoları hakkında daha ayrıntılı bilgi sağlanır ve ayrıca Windows 'a uygulama dağıttığınızda göz önünde bulunan önemli ayrıntıları ele alınmaktadır. 

Windows 10 cihazlarında desteklenen uygulama türleri İş kolu (LOB) uygulamaları ve İş için Microsoft Store uygulamalarıdır. Windows uygulamaları için dosya uzantıları. msi,. appx ve. appxdemeti içerir.  

> [!Note]
> Modern uygulamaları dağıtmak için en azından şunlar gerekir:
> - Windows 10 1803 için [23 Mayıs 2018—KB4100403 (İşletim Sistemi Derlemesi 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Windows 10 1709 için [21 Haziran 2018 — KB4284822 (İşletim Sistemi Derlemesi 16299.522)](https://support.microsoft.com/help/4284822).
>
> Yalnızca Windows 10 1803 ve üzeri, ilişkili birincil kullanıcı olmadığında uygulamaları yüklemeyi destekler.
>
> Windows 10 Home Edition çalıştıran cihazlarda LOB uygulama dağıtımı desteklenmez.

## <a name="supported-windows-10-app-types"></a>Desteklenen Windows 10 uygulama türleri

Belirli uygulama türleri, kullanıcılarınızın çalıştırdığı Windows 10 sürümüne göre desteklenir. Aşağıdaki tabloda, uygulama türü ve Windows 10 Supportability sağlanmaktadır.

| Uygulama türü | Giriş | Pro | İş | Enterprise | Eğitim | S modu | HoloLens<sup>1 | Surface Hub | WCOS | Mobil |
|----------------|------|-----|----------|------------|-----------|--------|-----------|------------|------|--------|
|  . DEFTERI | Hayır | Evet | Evet | Evet | Evet | Hayır | Hayır | Hayır | Hayır | Hayır |
| . Intunewin | Hayır | Evet | Evet | Evet | Evet | 19H2 + | Hayır | Hayır | Hayır | Hayır |
| Office C2R 'NDA | Hayır | Evet | Evet | Evet | Evet | RS4 + | Hayır | Hayır | Hayır | Hayır |
| LOB: APPX/MALTı | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet |
| MSFB çevrimdışı | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet |
| MSFB çevrimiçi | Evet | Evet | Evet | Evet | Evet | Evet | RS4 + | Hayır | Evet | Evet |
| Web Apps | Evet | Evet | Evet | Evet | Evet | Evet | Evet<sup>2 | Evet<sup>2 | Evet | Evet<sup>2 |
| Mağaza bağlantısı | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet | Evet |
| Microsoft Edge | Hayır | Evet | Evet | Evet | Evet | 19H2 +<sup>3 | Hayır | Hayır | Hayır | Hayır |

<sup>1</sup> uygulama yönetiminin kilidini açmak Için, Hololens cihazınızı [holographic for Business](../fundamentals/windows-holographic-for-business.md)'a yükseltin.<br />
yalnızca Şirket Portalı <sup>2</sup> ' den başlatın.<br />
<sup>3</sup> Edge uygulamasının başarıyla yüklenmesi Için cihazlara S-Mode ilkesi atanması gerekir.

> [!NOTE]
> Tüm Windows uygulama türleri kayıt gerektirir.

## <a name="windows-10-lob-apps"></a>Windows 10 LOB uygulamaları

Windows 10 LOB uygulamalarını imzalayabilir ve Intune yönetim konsoluna yükleyebilirsiniz. Bunlar, Evrensel Windows Platformu (UWP) uygulamaları ve Windows uygulama paketleri (AppX) gibi modern uygulamaların yanı sıra basit Microsoft yükleyicisi paket dosyaları (MSI) gibi Win 32 uygulamaları da içerebilir. Yöneticinin LOB uygulamalarının güncelleştirmelerini el ile yüklemesi ve dağıtması gerekir. Bu güncelleştirmeler, uygulamayı yüklemiş olan Kullanıcı cihazlarına otomatik olarak yüklenir. Kullanıcı müdahalesi gerekli değildir ve kullanıcının güncelleştirmeler üzerinde denetimi yoktur. 

## <a name="microsoft-store-for-business-apps"></a>İş İçin Microsoft Mağazası uygulamaları

Iş uygulamaları için Microsoft Store, Microsoft Store for Business yönetici portalından satın alınan modern uygulamalardır. Daha sonra yönetim için Microsoft Intune için eşitlenir. Uygulamalar çevrimiçi lisanslanmış ya da çevrimdışı lisanslanabilir. Microsoft Store, yönetici tarafından hiçbir ek eylem gerekmeden güncelleştirmeleri doğrudan yönetir. Ayrıca, özel bir Tekdüzen Kaynak tanımlayıcısı (URI) kullanarak belirli uygulamalara yönelik güncelleştirmeleri engelleyebilirsiniz. Daha fazla bilgi için bkz. [Kurumsal uygulama yönetimi - Uygulamaların otomatik güncelleştirmeleri almasını engelleme](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Kullanıcı aynı zamanda cihazdaki tüm Iş uygulamaları için Microsoft Store güncelleştirmelerini devre dışı bırakabilir. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Iş uygulamaları için Microsoft Store kategorilere ayırın 
Iş uygulamalarına yönelik Microsoft Store kategorilere ayırmak için: 

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** > **uygulamalar** ' ı seçin. 
3. Iş için bir Microsoft Store seçin. Ardından > **Özellikler** ' i seçerek **uygulama bilgileri** > **kategorisini**seçin. 
4. Bir kategori seçin.

## <a name="install-apps-on-windows-10-devices"></a>Windows 10 cihazlarına uygulama yüklemesi
Uygulama türüne bağlı olarak, uygulamayı iki şekilde bir Windows 10 cihazına yükleyebilirsiniz:

- **Kullanıcı bağlamı**: bir uygulama kullanıcı bağlamında dağıtıldığında, Kullanıcı cihazda oturum açtığında, yönetilen uygulama cihazdaki bu kullanıcı için yüklenir. Kullanıcı cihazda oturum açana kadar uygulama yüklemesinin başarılı olamayacağını unutmayın. 
  - Modern LOB uygulamaları ve Iş uygulamaları için Microsoft Store (hem çevrimiçi hem de çevrimdışı), kullanıcı bağlamında dağıtılabilir. Uygulamalar hem gerekli hem de kullanılabilir amaçları destekler.
  - Kullanıcı modu veya Ikili mod olarak oluşturulan Win32 uygulamaları, kullanıcı bağlamında dağıtılabilir ve hem gerekli hem de kullanılabilir amaçları destekler. 
- **Cihaz bağlamı**: bir uygulama cihaz bağlamında dağıtıldığında, yönetilen uygulama doğrudan cihaza Intune tarafından yüklenir.
  - Cihaz bağlamında yalnızca modern LOB uygulamaları ve çevrimdışı lisanslı Microsoft Store Kurumsal uygulamalar dağıtılabilir. Bu uygulamalar yalnızca gerekli amacı destekler.
  - Makine modu veya Ikili mod olarak oluşturulan Win32 uygulamaları cihaz bağlamında dağıtılabilir ve yalnızca gerekli amacı destekleyebilir.

> [!NOTE]
> Çift modlu uygulamalar olarak oluşturulan Win32 uygulamaları için, uygulamanın bu örnekle ilişkili tüm atamalar için Kullanıcı modu veya makine modu uygulaması olarak işlev görür olması gerekir. Dağıtım bağlamı atama başına değiştirilemez.  

Uygulamalar yalnızca cihaz ve Intune uygulama türü tarafından desteklenerek cihaz bağlamına yüklenebilir. Aşağıdaki uygulama türlerini cihaz bağlamına yükleyebilir ve bu uygulamaları bir cihaz grubuna atayabilirsiniz:

- Win32 uygulamaları
- Iş uygulamaları için çevrimdışı lisanslı Microsoft Store
- LOB uygulamaları (MSI, APPX ve MALTı)
- Office 365 ProPlus

Cihaz bağlamına yüklemeyi seçtiğiniz Windows LOB uygulamaları (özellikle APPX ve MSIX) ve Microsoft Store Iş uygulamalarının (çevrimdışı uygulamalar) bir cihaz grubuna atanması gerekir. Bu uygulamalardan biri kullanıcı bağlamında dağıtıldığında yükleme başarısız olur. Yönetim konsolunda aşağıdaki durum ve hata görüntülenir:
  - Durum: Başarısız.
  - Hata: bir Kullanıcı, cihaz bağlamı yüklemesi ile hedeflenmiyor.

> [!IMPORTANT]
> Bir Autopilot White with sağlama senaryosu ile birlikte kullanıldığında, bir cihaz grubunu hedeflemek üzere cihaz bağlamında dağıtılan Iş uygulamalarına yönelik LOB uygulamaları ve Microsoft Store için gereksinim yoktur. Daha fazla bilgi için bkz. [Windows Autopilot White and Deployment](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove).

> [!Note]
> Belirli bir dağıtıma sahip bir uygulama atamasını kaydettikten sonra, modern uygulamalar haricinde, bu atamanın bağlamını değiştiremezsiniz. Modern uygulamalar için, bağlamı Kullanıcı bağlamından cihaz bağlamına dönüştürebilirsiniz. 

Tek bir kullanıcı veya cihazdaki ilkelerde çakışma varsa, aşağıdaki öncelikler geçerlidir:
- Cihaz bağlamı ilkesi, kullanıcı bağlamı ilkesinden daha yüksek önceliklidir. 
- Yükleme ilkesi, kaldırma ilkesinden daha yüksek önceliklidir.

Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md). Intune'daki uygulama türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md)
- [Uygulamaları izleme](apps-monitor.md)
