---
title: "Uygulamaları gruplara ekleme"
titleSuffix: Intune on Azure
description: "Intune'a uygulama ekledikten sonra, bu uygulamayı kullanıcı veya cihaz gruplarına atamak isteyeceksiniz.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a0249fe3ecd82f6382b2625378d6a81d33129069
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları gruplara atama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir uygulamayı Intune'a ekledikten sonra kullanıcılara ve cihazlara atayabilirsiniz.

Uygulamalar, Intune tarafından yönetilip yönetilmediğine bakılmaksızın uygulamalara atanabilir. Uygulamaları kullanıcılara ve cihazlara atamaya yönelik çeşitli seçenekleri anlamanıza yardımcı olması için aşağıdaki tabloyu kullanın:

||||
|-|-|-|-|
|&nbsp;|Intune’a kayıtlı cihazlar|Intune’a kayıtlı olmayan cihazlar|
|Kullanıcılara atama|Evet|Evet|
|Cihazlara atama|Evet|Hayır|
|Sarmalanan uygulamaları veya Intune SDK’sında birleştirilmiş uygulamaları atama (uygulama koruma ilkeleri için)|Evet|Evet|
|Uygulamaları Kullanılabilir olarak atama|Evet|Evet|
|Uygulamalarını Gerekli olarak atama|Evet|Hayır|
|Uygulamaları kaldırma|Evet|Hayır|
|Son kullanıcıların Şirket Portalı uygulamasından kullanılabilir uygulamaları yüklemesi|Evet|Hayır|
|Son kullanıcıların web tabanlı Şirket Portalı’ndan kullanılabilir uygulamaları yüklemesi|Evet|Evet|

> [!NOTE]
> Şu anda, iOS ve Android uygulamalarını (hem iş kolu uygulamaları hem de mağazadan satın uygulamalar), Intune’a kaydedilmeyen cihazlara atayabilirsiniz.

## <a name="how-to-assign-an-app"></a>Uygulama atama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde, **Mobil uygulamalar**’ı seçin.
1. **Mobil Uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
2. Uygulama listesi dikey penceresinde, atamak istediğiniz uygulamaya tıklayın.
3. <*uygulama adı*> - **Genel Bakış** dikey penceresinde **Yönet** > **Atamalar**’ı seçin.
4. **Grup Seç** öğesini seçin, ardından **Grupları seçin** dikey penceresinde uygulamayı atamak istediğiniz Azure AD gruplarını seçin.
5. Seçtiğiniz her uygulama için, **atama türü** olarak aşağıdakilerden birini seçin:
    - **Kullanılabilir** Kullanıcılar Şirket Portalı’ndan veya web sitesinden uygulamayı yükler.
    - **Uygulanamaz** - Uygulama yüklenmez veya Şirket Portalı’nda gösterilmez.
    - **Gerekli** - Uygulama, seçili gruplardaki cihazlara yüklenir.
    - **Kaldırma** - Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
    - **Kayıtlı veya kayıtsız kullanılabilir** - Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın.
6. **Yalnızca iOS uygulamalar için** - Uygulamaya göre VPN ayarları barındıran bir iOS VPN profili oluşturduysanız **VPN** altında bu profili seçebilirsiniz. Uygulamayı çalıştırdığınızda VPN bağlantısı açılır. Daha fazla bilgi için bkz. [iOS cihazlar için VPN ayarları](vpn-settings-ios.md).
6. İşiniz bittikten sonra **Kaydet**’i seçin.

Uygulama artık seçtiğiniz gruplara atanır.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Uygulama amaçları arasındaki çakışmalar nasıl çözümlenir

Bazı durumlarda, aynı uygulama farklı amaçlarla birden çok gruba atanır. Bu durumlarda, ortaya çıkan amacı anlamak için bu tabloyu kullanın.

||||
|-|-|-|
|Grup 1 amacı|Grup 2 amacı|Ortaya çıkan amaç|
|Kullanıcı Gerekli|Kullanıcı Mevcut|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli|Kullanıcı Mevcut Değil|Gerekli|
|Kullanıcı Gerekli|Kullanıcı Kaldır|Gerekli|
|Kullanıcı Mevcut|Kullanıcı Mevcut Değil|Kullanılamıyor|
|Kullanıcı Mevcut|Kullanıcı Kaldır|Kaldır|
|Kullanıcı Mevcut Değil|Kullanıcı Kaldır|Kaldır
|Kullanıcı Gerekli|Cihaz Gerekli|İkisi de mevcut; Ağ geçidi gerekli olanı işler 
|Kullanıcı Gerekli|Cihaz Kaldır|İkisi de mevcut, Ağ geçidi gerekli olanı çözümler 
|Kullanıcı Mevcut|Cihaz Gerekli|İkisi de mevcut, Ağ geçidi gerekli olanı çözümler (Gerekli ve Kullanılabilir)
|Kullanıcı Mevcut|Cihaz Kaldır|İkisi de mevcut, Ağ geçidi Kullanılabilir olanı çözümler.<br>Uygulama, Şirket Portalında görüntülenir.<br>Uygulama zaten yüklüyse (önceki amacıyla gerekli uygulama olarak) kaldırılır.<br>Ancak kullanıcı şirket portalından yüklemeye tıklarsa uygulama yüklenir ve kaldırma amacı yerine getirilmez.|
|Kullanıcı Mevcut Değil|Cihaz Gerekli|Gerekli|
|Kullanıcı Mevcut Değil|Cihaz Kaldır|Kaldır|
|Kullanıcı Kaldır|Cihaz Gerekli|İkisi de mevcut, Ağ geçidi Gerekli olanı çözümler|
|Kullanıcı Kaldır|Cihaz Kaldır|İkisi de mevcut, Ağ geçidi Kaldır işlemini çözümler|
|Cihaz Gerekli|Cihaz Kaldır|Gerekli|
|Kullanıcı Gerekli ve Mevcut|Kullanıcı Mevcut|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Kullanıcı Kaldır|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Kullanıcı Mevcut Değil|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Cihaz Gerekli|İkisi de mevcut: Gerekli ve Mevcut
|Kullanıcı Gerekli ve Mevcut|Cihaz Mevcut Değil|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Cihaz Kaldır|İkisi de mevcut, Ağ geçidi gerekli olanı çözümler. Gerekli + Mevcut
|Kullanıcı Mevcut Değil|Cihaz Mevcut Değil|Kullanılamıyor|
|Kullanıcı Mevcut|Cihaz Mevcut Değil|Kullanılabilir|
|Kullanıcı Gerekli|Cihaz Mevcut Değil|Gerekli|
|Kullanıcı Kayıt Olmadan Mevcut|Kullanıcı Gerekli ve Mevcut|Gerekli ve Kullanılabilir
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Gerekli|Gerekli
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Mevcut Değil|Kullanılamıyor
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Mevcut|Kullanılabilir|
|Kullanıcı kayıt olmadan Mevcut|Cihaz Gerekli|Gerekli ve kayıt olmadan Mevcut|
|Kullanıcı kayıt olmadan Mevcut|Cihaz Mevcut Değil|Kayıt olmadan Mevcut|
|Kullanıcı kayıt olmadan Mevcut|Cihaz Kaldır|Kaldırma ve kayıt olmadan Mevcut.<br>Kullanıcı uygulamayı şirket portalından yüklemediyse kaldırma işlemi yerine getirilir.<br>Kullanıcı uygulamayı şirket portalından yüklerse, yüklemenin kaldırmaya göre önceliği vardır.|

>[!NOTE]
>Yalnızca yönetilen iOS mağazası uygulamalarını Intune’a ekleyip Gerekli olarak atadığınızda bu uygulamalar, hem Gerekli hem de Mevcut amaçlarıyla otomatik olarak oluşturulur.

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).
