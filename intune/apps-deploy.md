---
title: Microsoft Intune’da uygulamaları gruplara atama
titlesuffix: ''
description: Intune uygulama kullanıcı ya da Microsoft Intune kullanarak cihazları gruplara öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 13c93f2339d47b177ac997c692227a039519bc76
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57391957"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları gruplara atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune’a [bir uygulama ekledikten](apps-add.md) sonra uygulamayı kullanıcılara ve cihazlara atayabilirsiniz. Unutmayın; cihaz Intune tarafından yönetiliyor olsa da olmasa da uygulamayı cihaza atayabilirsiniz.

> [!NOTE]
> Kullanılabilir dağıtım amacı, cihaz grupları için desteklenmiyor, yalnızca kullanıcı gruplarına desteklenir.

Aşağıdaki tabloda uygulamaları kullanıcılara ve cihazlara atamaya yönelik çeşitli seçenekler listelenir:

|   | Intune’a kayıtlı cihazlar | Intune’a kayıtlı olmayan cihazlar |
|-------------------------------------------------------------------------------------------|------------------------------|----------------------------------|
| Kullanıcılara atama | Evet | Evet |
| Cihazlara atama | Evet | Hayır |
| Sarmalanan uygulamaları veya Intune SDK’sını birleştiren uygulamaları atama (uygulama koruma ilkeleri için) | Evet | Evet |
| Uygulamaları Kullanılabilir olarak atama | Evet | Evet |
| Uygulamalarını Gerekli olarak atama | Evet | Hayır |
| Uygulamaları kaldırma | Evet | Hayır |
| Intune’dan uygulama güncelleştirmelerini alma | Evet | Hayır |
| Son kullanıcıların Şirket Portalı uygulamasından kullanılabilir uygulamaları yüklemesi | Evet | Hayır |
| Son kullanıcıların web tabanlı Şirket Portalı’ndan kullanılabilir uygulamaları yüklemesi | Evet | Evet |

> [!NOTE]
> Şu anda, iOS ve Android uygulamalarını (iş kolu uygulamaları ve mağazadan satın alınan uygulamalar), Intune’a kayıtlı olmayan cihazlara atayabilirsiniz.
>
> Intune'da kayıtlı olmayan cihazlarda uygulama güncelleştirmeleri almak için, cihaz kullanıcıları kendi kuruluşlarının Şirket Portalı'na gitmeli ve uygulama güncelleştirmelerini el ile yüklemelidir.

## <a name="assign-an-app"></a>Bir uygulamayı atar

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** menüsünde **İstemci uygulamaları**’nı seçin.
4. Menünün **Yönet** bölümünde **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde atamak istediğiniz uygulamayı seçin.
6. Menünün **Yönet** bölümünde **Atamalar**’ı seçin.
7. Uygulamayla ilgili **Grup ekle** bölmesini açmak için **Grup Ekle**'yi seçin.
8. Belirli bir uygulama için **atama türü** seçin:
   - **Kayıtlı cihazlar için kullanılabilir**: Uygulama, uygulamayı Şirket portalı uygulamasından veya Web sitesinden yükleyebilir kullanıcı gruplarına atayın.
   - **Kayıtlı veya Kayıtsız kullanılabilir**: Bu uygulama, cihazları Intune'a kayıtlı olmayan kullanıcı gruplarına atayın. Kullanıcılar, bir Intune lisansı atanmalıdır bkz [Intune lisanslarını](licenses.md).
   - **Gerekli**: Uygulama seçilen gruplardaki cihazlara yüklenir. Bazı platformlarda son kullanıcının uygulama yükleme başlamadan önce onaylamak için ek istekler olabilir.
   - **Kaldırma**: Intune uygulamayı cihaza aracılığıyla "Kullanılabilir" kayıtlı cihazlar için daha önce yüklendiyse, uygulama seçilen gruplardaki cihazlardan kaldırılır ya da aynı dağıtım kullanarak "Required" atama. Web bağlantıları, dağıtımdan sonra kaldırılamaz.

     > [!NOTE]
     > **Yalnızca iOS uygulamaları için**: Bir iOS uygulama başına VPN ayarları içeren bir VPN profili oluşturduysanız, VPN profili altında seçebileceğiniz **VPN**. Uygulamayı çalıştırdığınızda VPN bağlantısı açılır. Daha fazla bilgi için bkz. [iOS cihazlar için VPN ayarları](vpn-settings-ios.md).
     >
     > **Yalnızca Android uygulamaları için**: Bir Android uygulaması olarak dağıtırsanız **kayıtlı veya Kayıtsız kullanılabilir**, raporlama durumu yalnızca kayıtlı cihazlarda kullanıma sunulacaktır.

9. Bu uygulama atamasından etkilenecek kullanıcı gruplarını belirtmek için, **Dahil Edilen Gruplar**'ı seçin.
10. Dahil etmek üzere bir veya daha fazla grup belirttikten sonra **Seç** düğmesini seçin.
11. Dahil edilen gruplar seçimini tamamlamak için **Ata** bölmesinde **Tamam**'ı seçin.
12. Herhangi bir kullanıcı grubunun bu uygulama atamasından etkilenmesini istemiyorsanız, **Grupları Dışla**'yı seçin.
13. Herhangi bir grubu dışlamayı seçtiyseniz, **Grupları seçin** alanında **Seç** düğmesini seçin.
14. **Grup ekle** bölmesinde **Tamam**’ı seçin.
15. Uygulamanın **Atamalar** bölmesinde **Kaydet**'i seçin.

Uygulama artık seçtiğiniz gruplara atanır. Uygulama atamalarını dahil etme ve dışlama hakkında daha fazla bilgi için bkz. [Uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Uygulama amaçları arasındaki çakışmalar nasıl çözümlenir

Bazı durumlarda, aynı uygulama farklı amaçlarla birden çok gruba atanır. Aşağıdaki tabloda verilen bilgiler, bu durum ortaya çıktığında sonuçta söz konusu olan amacı anlamanıza yardımcı olabilir:

| Grup 1 amacı | Grup 2 amacı | Ortaya çıkan amaç |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Kullanıcı Gerekli|Kullanıcı Mevcut|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli|Kullanıcı Mevcut Değil|Gerekli|
|Kullanıcı Gerekli|Kullanıcı Kaldır|Gerekli|
|Kullanıcı Mevcut|Kullanıcı Mevcut Değil|Kullanılamıyor|
|Kullanıcı Mevcut|Kullanıcı Kaldır|Kaldır|
|Kullanıcı Mevcut Değil|Kullanıcı Kaldır|Kaldır
|Kullanıcı Gerekli|Cihaz Gerekli|İkisi de mevcut, Intune Gerekli olanı işler
|Kullanıcı Gerekli|Cihaz Kaldır|İkisi de mevcut, Intune Gerekli olanı çözümler
|Kullanıcı Mevcut|Cihaz Gerekli|İkisi de mevcut; Intune Gerekli (Gerekli ve Kullanılabilir) olanı çözümler
|Kullanıcı Mevcut|Cihaz Kaldır|İkisi de mevcut, Intune Kullanılabilir olanı çözümler.<br><br>Uygulama, Şirket Portalında görüntülenir.<br><br>Uygulama zaten yüklüyse (önceki amacıyla gerekli bir uygulama olarak) kaldırılır.<br><br>Kullanıcı **Şirket Portalı'ndan yükle**'yi seçerse uygulama yüklenir ve kaldırma amacı yerine getirilmez.|
|Kullanıcı Mevcut Değil|Cihaz Gerekli|Gerekli|
|Kullanıcı Mevcut Değil|Cihaz Kaldır|Kaldır|
|Kullanıcı Kaldır|Cihaz Gerekli|İkisi de mevcut, Intune Gerekli olanı çözümler|
|Kullanıcı Kaldır|Cihaz Kaldır|İkisi de mevcut, Intune Kaldır eylemini çözümler|
|Cihaz Gerekli|Cihaz Kaldır|Gerekli|
|Kullanıcı Gerekli ve Mevcut|Kullanıcı Mevcut|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Kullanıcı Kaldır|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Kullanıcı Mevcut Değil|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Cihaz Gerekli|İkisi de mevcut; Gerekli ve Mevcut
|Kullanıcı Gerekli ve Mevcut|Cihaz Mevcut Değil|Gerekli ve Kullanılabilir|
|Kullanıcı Gerekli ve Mevcut|Cihaz Kaldır|İkisi de mevcut; Intune Gerekli (Gerekli ve Kullanılabilir) olanı çözümler
|Kullanıcı Mevcut Değil|Cihaz Mevcut Değil|Kullanılamıyor|
|Kullanıcı Mevcut|Cihaz Mevcut Değil|Kullanılabilir|
|Kullanıcı Gerekli|Cihaz Mevcut Değil|Gerekli|
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Gerekli ve Mevcut|Gerekli ve Kullanılabilir
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Gerekli|Gerekli
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Mevcut Değil|Kullanılamıyor
|Kullanıcı kayıt olmadan Mevcut|Kullanıcı Mevcut|Kullanılabilir|
|Kullanıcı kayıt olmadan Mevcut|Cihaz Gerekli|Gerekli ve kayıt olmadan Mevcut|
|Kullanıcı kayıt olmadan Mevcut|Cihaz Mevcut Değil|Kayıt olmadan Mevcut|
|Kullanıcı kayıt olmadan Mevcut|Cihaz Kaldır|Kaldırma ve kayıt olmadan Mevcut.<br><br>Kullanıcı uygulamayı Şirket Portalı'ndan yüklemediyse kaldırma işlemi yerine getirilir.<br><br>Kullanıcı uygulamayı Şirket Portalı'ndan yüklerse, yüklemenin kaldırmaya göre önceliği vardır.|

> [!NOTE]
> Yalnızca yönetilen iOS mağazası uygulamalarını Microsoft Intune’a ekleyip **Gerekli** olarak atadığınızda, bu uygulamalar hem **Gerekli** hem de **Kullanılabilir** amaçlarıyla otomatik olarak oluşturulur.<br><br>
> Gerekli amaçla hedefi belirlenmiş iOS Store uygulamaları (iOS VPP uygulamaları değil), cihazı iade etme sırasında cihazda zorunlu tutulur ve Şirket Portalı uygulamasında da gösterilir.

## <a name="managed-google-play-app-deployment-to-unmanaged-devices"></a>Yönetilen Google Play yönetilmeyen cihazlar için uygulama dağıtımı
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, yönetilen Google Play store uygulamaları ve iş kolu (LOB) uygulamalarını kullanıcılara dağıtmak için kullanabilirsiniz. Yönetilen Google Play uygulamaları olarak hedeflenen **kayıtlı veya Kayıtsız kullanılabilir** Play Store uygulaması son kullanıcının cihazında şirket içinde ve Şirket portalı uygulamasında görünür. Son kullanıcı göz atın ve Play uygulamasından bu şekilde dağıtılan uygulamaları yükleyin. Yönetilen Google Play mağazasından uygulamalar yüklü olduğundan, son kullanıcının anlamına cihazların daha güvenli olacak bilinmeyen kaynaklardan uygulama yüklemesine izin vermek için cihaz ayarlarını değiştirmek gerekli değildir. Uygulama geliştiricisi, bir kullanıcının cihazına yüklenen play bir uygulamanın yeni bir sürümünü yayımlar, uygulamayı Play tarafından otomatik olarak güncelleştirilir. 

Bir yönetilen Google Play uygulaması yönetilmeyen cihazlara atamak için adımlar:

1. Intune kiracınız için yönetilen Google Play bağlanın. Bu ayrılmış, Kurumsal Android iş profili ya da tam olarak yönetilen cihazları yönetmek için yapmış olduğunuz, yeniden yapmanız gerekmez.
2. Yönetilen Google Play mağazasından, uygulamaları, Intune konsoluna ekleyin.
3. Yönetilen Google Play uygulamaları olarak hedef **kayıtlı veya Kayıtsız kullanılabilir** istediğiniz kullanıcı grubunu. **Gerekli** ve **kaldırma** uygulama hedefleyen kayıtlı olmayan cihazlar için desteklenmez.
4. Bir uygulama koruma İlkesi, kullanıcı grubuna atayın.
5. Son kullanıcı Şirket portalı uygulamasında bir sonraki açışında uygulamalarını Play Store uygulamasında kendileri için kullanılabilir olduğunu belirten bir ileti görürler.  Kullanıcı Play uygulamaya doğrudan şirket uygulamaları görmek için duruma getirilebilmesi için bu bildirimi dokunabilir veya Play Store uygulaması için ayrı olarak gidebilirsiniz.
6. Son kullanıcı kendi kişisel Google hesabı (burada, kişisel uygulamalarını bakın) ve kendi iş hesabını (burada depolama ve LOB uygulamaları için hedeflenmiş görürler) arasında geçiş yapma ve Play Store uygulaması içinde bağlam menüsü genişletebilirsiniz. Son kullanıcıların, Play Store uygulamasında yükleme dokunarak uygulamalarını yükleyin.

Intune konsolunda bir uygulama seçmeli silme verildiğinde, Play Store uygulamasını iş hesabını otomatik olarak kaldırılır ve kullanıcıdan gelen noktası artık bkz olacak uygulamalar Play Store uygulama Kataloğu'nda çalışır. İş hesabı, bir CİHAZDAN kaldırıldığında, Play Store ' yüklenen uygulamalar cihazda yüklü kalır ve değil kaldırılır. 

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izleme hakkında daha fazla bilgi edinmek için bkz. [Uygulamaları izleme](apps-monitor.md).
