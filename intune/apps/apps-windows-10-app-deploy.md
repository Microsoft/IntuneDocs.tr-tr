---
title: Microsoft Intune kullanarak Windows 10 uygulama dağıtımı
titleSuffix: ''
description: Microsoft Intune ile kullanılabilen Windows 10 uygulama dağıtım senaryoları hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04e943f573fb2485a2ef7f1e3245f08d4222d142
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830554"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Microsoft Intune kullanarak Windows 10 uygulama dağıtımı 

Microsoft Intune Şu anda Windows 10 cihazlarında çeşitli uygulama türlerini ve dağıtım senaryolarını destekler. Bir uygulamayı Intune 'a ekledikten sonra, uygulamayı kullanıcılara ve cihazlara atayabilirsiniz. Aşağıdaki bilgiler, desteklenen Windows 10 senaryolarıyla ilgili daha fazla ayrıntı sağlar. Ayrıca, aşağıdaki bilgiler, Windows 'a uygulama dağıtımında önemli ayrıntılar sağlar. 

İş kolu (LOB) uygulamaları ve Microsoft Store for Business Apps, Windows 10 cihazlarında desteklenen uygulama türleridir. Windows uygulamaları için dosya uzantıları **. msi**, **. appx**ve **. appxdemeti**içerir.  

> [!Note]
> Modern uygulamaları dağıtmak için gereken en düşük Windows 10 güncelleştirmeleri aşağıdaki gibidir:
> - Windows 10 1803 için [23 Mayıs 2018 — KB4100403 (OS Build 17134,81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403)için.
> - Windows 10 1709 için [21 Haziran 2018 — KB4284822 (OS Build 16299,522)](https://support.microsoft.com/help/4284822).
>
> Yalnızca Windows 10 1803 ve üzeri, ilişkili birincil kullanıcı olmadığında uygulamaları yüklemeyi destekler.
>
> Windows 10 Home sürümlerini çalıştıran cihazlarda LOB uygulama dağıtımı desteklenmez.

## <a name="windows-10-line-of-business-apps"></a>Windows 10 iş kolu uygulamaları

Windows 10 LOB uygulamaları imzalanır ve Intune yönetim konsoluna yüklenir ve Evrensel Windows Platformu (UWP) uygulamaları ve Windows uygulama paketleri (AppX) gibi modern uygulamaların yanı sıra, basit Microsoft ınstaller paket dosyaları (MSI) gibi Win 32 uygulamaları da içerebilir. LOB uygulamalarının güncelleştirmeleri yönetici tarafından her seferinde el ile yüklenip dağıtılmalıdır. Dağıtılan güncelleştirmeler, uygulamayı kullanıcı müdahalesi olmadan yükleyen Son Kullanıcı cihazlarına otomatik olarak yüklenir. Kullanıcının güncelleştirmeler üzerinde denetimi yoktur. 

## <a name="microsoft-store-for-business-apps"></a>Iş uygulamaları için Microsoft Store

Iş uygulamaları için Microsoft Store, Microsoft Store Iş Yöneticisi portalından satın alınan modern uygulamalardır ve daha sonra yönetim için Microsoft Intune olarak eşitlenir. Uygulamalar **çevrimiçi lisanslanmış** ya da **çevrimdışı lisanslanabilir**. Iş uygulamaları için Microsoft Store güncelleştirmeleri, sizin tarafınızdan gerekli ek bir işlem olmadan doğrudan Microsoft Store tarafından yönetilir. Ayrıca, özel bir Tekdüzen Kaynak tanımlayıcısı (URI) kullanarak belirli uygulamalara yönelik güncelleştirmeleri engelleyebilirsiniz. Daha fazla bilgi için bkz. [Kurumsal uygulama yönetimi-otomatik güncelleştirmelerden uygulamayı engelle](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Cihazda, Son Kullanıcı cihazdaki tüm Iş uygulamaları Microsoft Store güncelleştirmelerini de devre dışı bırakabilir. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Iş uygulamaları için Microsoft Store kategorilere ayırın 
Iş uygulamalarına yönelik Microsoft Store sınıflandırmak için aşağıdaki adımları kullanın: 

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **İstemci uygulamaları** > **uygulamalar** ' ı seçin > bir Microsoft Store Iş uygulaması > **uygulama bilgileri** > **kategorisi**seçin. 
3. Açılan menüden bir kategori seçin.

## <a name="installing-apps-on-windows-10-devices"></a>Windows 10 cihazlarına uygulama yükleme
Uygulama türüne bağlı olarak, uygulama iki şekilde bir Windows 10 cihazına yüklenebilir:

- **Kullanıcı bağlamı**: bir uygulama kullanıcı bağlamında dağıtıldığında, Kullanıcı cihazda oturum açtığında, yönetilen uygulama cihazdaki bu kullanıcı için yüklenir. Kullanıcı cihazda oturum açana kadar uygulama yüklemesinin başarılı olamayacağını unutmayın. 
  - Modern iş kolu uygulamaları ve iş için Microsoft Mağazası uygulamaları (hem çevrimiçi hem de çevrimdışı) kullanıcı bağlamında dağıtılabilir ve hem gerekli hem de kullanılabilir amacı destekleyecektir.
  - **Kullanıcı modu** veya **ikili mod** olarak oluşturulan Win32 uygulamaları, kullanıcı bağlamında dağıtılabilir ve hem **gerekli** hem de **kullanılabilir** amacı destekleyecektir. 
- **Cihaz bağlamı**: bir uygulama cihaz bağlamına dağıtıldığında, yönetilen uygulama doğrudan cihaza Intune tarafından yüklenir.
  - Yalnızca modern iş kolu uygulamaları ve Iş kolu uygulamaları için çevrimdışı lisanslı Microsoft Store cihaz bağlamına dağıtılabilir ve yalnızca gerekli amacı destekleyecektir.
  - **Makine modu** ya da **ikili mod** olarak oluşturulan Win32 uygulamaları, kullanıcı bağlamında dağıtılabilir ve yalnızca **gerekli** amacı destekler.

> [!NOTE]
> **Çift modlu** uygulamalar olarak oluşturulan Win32 uygulamaları için, uygulamanın bu örnekle ilişkili tüm atamalar Için **Kullanıcı modu** veya **makine modu** uygulaması olarak işlev görür. Dağıtım bağlamı atama başına değiştirilemez.  

Bir uygulama cihaz bağlamına dağıtıldığında, yükleme yalnızca cihaz bağlamını destekleyen bir cihaza hedeflendiğinde başarılı olur. Ayrıca, cihaz bağlamına dağıtmak aşağıdaki koşulları destekler:
- Bir uygulama cihaz bağlamında dağıtılırsa ve bir kullanıcıya hedeflenirse, yükleme aşağıdaki durum ve hata, yönetici konsolunda görüntülenmesiyle başarısız olur:
  - Durum: başarısız oldu.
  - Hata: bir Kullanıcı, cihaz bağlamı yüklemesi ile hedeflenmiyor.
- Bir uygulama cihaz bağlamına dağıtılmışsa ancak cihaz bağlamını desteklemeyen bir cihaza hedeflendiyse, yükleme yönetim konsolunda aşağıdaki durum ve hata ile başarısız olur:
  - Durum: başarısız oldu.
  - Hata: Bu platform cihaz bağlamı yüklemelerini desteklemiyor. 

> [!Note]
> Uygulama ataması belirli bir dağıtımla kaydedildikten sonra, modern uygulamalar dışında bu atama için bağlam değiştirilemez. Modern uygulama durumu için, bağlam Kullanıcı bağlamından cihaz bağlamına değiştirilebilir. 

Tek bir Kullanıcı/cihazdaki ilkelerde bir çakışma olması durumunda, son ilkeyi belirlemede kullanılacak ilke öncelikleri aşağıda verilmiştir:
- Bir cihaz bağlamı ilkesi, bir kullanıcı bağlamı ilkesinden daha yüksek bir önceliktir. 
- Yükleme ilkesi, kaldırma ilkesinden daha yüksek bir önceliktir.

Microsoft Intune kullanarak uygulama atama hakkında daha fazla bilgi için, bkz. [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md) ve [Microsoft Intune uygulama atamalarını dahil etme ve hariç tutma](apps-inc-exl-assignments.md). Intune 'da uygulama türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](apps-add.md).

## <a name="next-steps"></a>Sonraki adımlar

- Gruplara uygulama atama hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md).
- Uygulama atamalarını izleme hakkında daha fazla bilgi için bkz. [uygulamaları izleme](apps-monitor.md).
