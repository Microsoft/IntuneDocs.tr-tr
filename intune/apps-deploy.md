---
title: Microsoft Intune’da uygulamaları gruplara atama
titleSuffix: ''
description: Microsoft Intune'u kullanarak Intune uygulamasını kullanıcı veya cihaz gruplarına atamayı öğrenin.
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
ms.openlocfilehash: 1db613f93e50caa377297e3873f6817a39714fe7
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59900630"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları gruplara atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune’a [bir uygulama ekledikten](apps-add.md) sonra uygulamayı kullanıcılara ve cihazlara atayabilirsiniz. Unutmayın; cihaz Intune tarafından yönetiliyor olsa da olmasa da uygulamayı cihaza atayabilirsiniz.

> [!NOTE]
> Kullanılabilir dağıtım amacı yalnızca kullanıcı grupları için desteklenir, cihaz grupları için desteklenmez.

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

## <a name="assign-an-app"></a>Uygulama atama

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** menüsünde **İstemci uygulamaları**’nı seçin.
4. Menünün **Yönet** bölümünde **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde atamak istediğiniz uygulamayı seçin.
6. Menünün **Yönet** bölümünde **Atamalar**’ı seçin.
7. Uygulamayla ilgili **Grup ekle** bölmesini açmak için **Grup Ekle**'yi seçin.
8. Belirli bir uygulama için **atama türü** seçin:
   - **Kayıtlı cihazlar için bulunur**: Uygulamayı, Şirket Portalı uygulamasından veya web sitesinden yükleyebilecek kullanıcı grubuna atayın.
   - **Kayıtlı veya kayıtsız olarak kullanılabilir**: Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın. Kullanıcılara Intune lisansı atanmış olmalıdır, bkz. [Intune Lisansları](licenses.md).
   - **Gerekli**: Uygulama, seçili gruplardaki cihazlara yüklenir. Bazı platformlarda yükleme başlamadan önce son kullanıcıya ek sorular ve bilgiler sunulabilir.
   - **Kaldır**: Intune'un uygulamayı cihaza bir "Kayıtlı cihazlar için bulunur" veya "Gerekli" ataması aracılığıyla ve aynı dağıtımı kullanarak yüklemiş olması halinde uygulama, seçilen gruplardaki cihazlardan kaldırılır. Dağıtım sonrasında web bağlantıları kaldırılamaz.

     > [!NOTE]
     > **Yalnızca iOS uygulamaları için**: Uygulamaya göre VPN ayarlarını barındıran bir iOS VPN profili oluşturduysanız **VPN**'nin altında VPN profilini seçebilirsiniz. Uygulamayı çalıştırdığınızda VPN bağlantısı açılır. Daha fazla bilgi için bkz. [iOS cihazlar için VPN ayarları](vpn-settings-ios.md).
     >
     > **Yalnızca Android uygulamaları için**: **Kayıtlı veya kayıtsız olarak kullanılabilir** atamasıyla dağıttığınız Android uygulamalarında raporlama durumu yalnızca kayıtlı cihazlarda kullanılabilir.

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

## <a name="managed-google-play-app-deployment-to-unmanaged-devices"></a>Yönetilmeyen cihazlara Yönetilen Google Play uygulaması dağıtımı
Kayıtlı olmayan Kayıt Olmadan Uygulama Koruma İlkesi (APP-WE) dağıtım senaryosundaki Android cihazlar için Yönetilen Google Play'i kullanarak kullanıcılara mağaza ve iş kolu (LOB) uygulamaları dağıtabilirsiniz. **Kayıtlı veya kayıtsız olarak kullanılabilir** olarak hedeflenene Yönetilen Google Play uygulamaları, son kullanıcının cihazında Şirket Portalı uygulamasında değil Play Store uygulamasında görünür. Bu sayede son kullanıcı Play uygulamasına dağıtılan uygulamalara göz atabilir ve bunları yükleyebilir. Uygulamalar yönetilen Google Play'den yüklendiği için son kullanıcının bilinmeyen kaynaklardan uygulama yüklenmesine izin verme amacıyla cihaz ayarlarını değiştirmesi gerekmez ve bu sayede cihaz daha güvenli olur. Uygulama geliştiricisinin, kullanıcının cihazına yüklenen uygulama için Play'de yeni bir sürüm yayımlaması durumunda uygulama Play tarafından otomatik olarak güncelleştirilir. 

Yönetilmeyen cihazlara Yönetilen Google Play uygulaması atama adımları:

1. Intune kiracınızı yönetilen Google Play'e bağlayın. Android Kurumsal iş profili, ayrılmış veya tam olarak yönetilen cihaz yönetimi amacıyla bunu daha önce yaptıysanız tekrar yapmanıza gerek yoktur.
2. Yönetilen Google Play'deki uygulamaları Intune konsolunuza ekleyin.
3. Yönetilen Google Play uygulamalarını istediğiniz kullanıcı grubu için **Kayıtlı veya kayıtsız olarak kullanılabilir** olarak hedefleyin. **Gerekli** ve **Kaldır** ile uygulama hedefleme, kayıtlı olmayan cihazlar için desteklenmez.
4. Kullanıcı grubuna bir Uygulama Koruma İlkesi atayın.
5. Artık son kullanıcı Şirket Portalı uygulamasını açtığında Play Store uygulamasında kullanabileceği uygulamalar olduğunu belirten bir ileti görecektir.  Kullanıcı, bu bildirime dokunarak doğrudan Play uygulamasına gidebilir ve şirket uygulamalarını görebilir veya ana menüden Play Store uygulamasına girebilir.
6. Son kullanıcı, Play Store uygulamasındaki bağlam menüsünü genişleterek kişisel Google hesaplarıyla (kişisel uygulamalarının bulunduğu) iş hesapları (kendilerini hedefleyen mağaza ve iş kolu uygulamalarının bulunduğu) arasında geçiş yapabilir. Son kullanıcılar, Play Store uygulamasında Yükle'ye dokunarak uygulamaları yükleyebilir.

Intune konsolundan uygulamaya özgü bir silme işlemi başlatıldığında iş hesabı Play Store uygulamasından otomatik olarak kaldırılır ve bu işlemden sonra son kullanıcı Play Store uygulama kataloğunda iş uygulamalarını göremez. İş hesabı bir cihazdan kaldırıldığında Play Store'dan yüklenen uygulamalar cihazda yüklü şekilde kalır ve kaldırılmaz. 

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izleme hakkında daha fazla bilgi edinmek için bkz. [Uygulamaları izleme](apps-monitor.md).
