---
title: Microsoft Intune’da uygulamaları gruplara atama
titlesuffix: ''
description: Microsoft Intune'a uygulama ekledikten sonra, bu uygulamayı kullanıcı veya cihaz gruplarına atamak isteyeceksiniz.”
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de95f5516298e8ade9e394fab8b05fc056651b0c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları gruplara atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir uygulamayı Microsoft Intune’a ekledikten sonra kullanıcılara ve cihazlara atayabilirsiniz.

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
|Intune’dan uygulama güncelleştirmelerini alma|Evet|Hayır|
|Son kullanıcıların Şirket Portalı uygulamasından kullanılabilir uygulamaları yüklemesi|Evet|Hayır|
|Son kullanıcıların web tabanlı Şirket Portalı’ndan kullanılabilir uygulamaları yüklemesi|Evet|Evet|

> [!NOTE]
> Şu anda, iOS ve Android uygulamalarını (hem iş kolu uygulamaları hem de mağazadan satın uygulamalar), Intune’a kaydedilmeyen cihazlara atayabilirsiniz.<br></br><br></br>
> Intune'da kayıtlı olmayan cihazlarda uygulama güncelleştirmeleri almak için, cihaz kullanıcılarının kendi şirket portallarına gitmeleri ve uygulama güncelleştirmelerini el ile yüklemeleri gerekir.

## <a name="how-to-assign-an-app"></a>Uygulama atama

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükündeki **Yönet** bölümünden **Uygulamalar**’ı seçin.
5. Uygulama listesi dikey penceresinde, atamak istediğiniz uygulamaya tıklayın.
6. Uygulamaya özgü **Genel Bakış** dikey penceresinde, **Yönet** bölümünden **Atamalar**’ı seçin.
7. **Grup Ekle**’yi seçerek uygulamayla ilgili **Grup ekle** dikey penceresinin görüntülenmesini sağlayın.
8. Belirli uygulama için, **atama türü** olarak aşağıdakilerden birini seçin:
   - **Kayıtlı cihazlar için kullanılabilir** - Kullanıcılar, Şirket Portalı uygulamasından veya web sitesinden uygulamayı yükler.
   - **Kayıtlı veya kayıtsız kullanılabilir** - Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın. **Android for Work** türünün bu seçeneği desteklemediğini aklınızda bulundurun. 
   - **Gerekli** - Uygulama, seçili gruplardaki cihazlara yüklenir.
   - **Kaldırma** - Uygulama, seçilen gruplardaki cihazlardan kaldırılır.

     > [!NOTE]
     > **Yalnızca iOS uygulamalar için** - Uygulamaya göre VPN ayarları barındıran bir iOS VPN profili oluşturduysanız **VPN** altında bu profili seçebilirsiniz. Uygulamayı çalıştırdığınızda VPN bağlantısı açılır. Daha fazla bilgi için bkz. [iOS cihazlar için VPN ayarları](vpn-settings-ios.md).

9. Bu uygulama atamasından etkilenecek kullanıcı gruplarını seçmek için **Dahil Edilen Gruplar**’ı seçin.
10. Dahil etmek üzere bir veya daha fazla grup seçtikten sonra **Seçin**’e tıklayın.
11. Dahil edilen grup bölümünü tamamlamak için **Ata** dikey penceresinde **Tamam**’a tıklayın.
12. Herhangi bir kullanıcı grubunun bu uygulama atamasından etkilenmesini istemiyorsanız **Grupları Dışla**’ya tıklayın.
13. Herhangi bir grubu dışlamayı seçtiyseniz **Grupları seçin** dikey penceresinde **Seçin**’e tıklayın.
14. **Grup ekle** dikey penceresinde **Tamam**’a tıklayın.
15. Atamalarınızı kaydetmek için uygulama **Atamalar** dikey penceresinde **Kaydet**’e tıklayın.

Uygulama artık seçtiğiniz gruplara atanır. Uygulama atamalarını dahil etme ve dışlama hakkında daha fazla bilgi için bkz. [Uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).

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
>Yalnızca yönetilen iOS mağazası uygulamalarını Microsoft Intune’a ekleyip **Gerekli** olarak atadığınızda bu uygulamalar, hem **Gerekli** hem de **Kullanılabilir** amaçlarıyla otomatik olarak oluşturulur.

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).
