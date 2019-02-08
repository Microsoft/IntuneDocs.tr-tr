---
title: Microsoft Intune’da uygulamaları gruplara atama
titlesuffix: ''
description: Intune uygulama kullanıcı ya da Microsoft Intune kullanarak cihazları gruplara öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ff89d1776d71dc24ea675de167f3fd22d6bdf04
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838776"
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

## <a name="android-enterprise-app-we-app-deployment"></a>Android Kurumsal uygulama-BİZ uygulama dağıtımı
Bir kayıtlı olmayan uygulama koruma İlkesi kayıt olmadan Android cihazlar için (APP-BİZ) dağıtım senaryosu, artık yönetilen Google Play mağazası uygulamalarını dağıtma ve LOB uygulamaları kullanıcılara için kullanabilirsiniz. Özellikle, son kullanıcıların cihazlarında güvenlik duruşunu bilinmeyen kaynaklardan yüklemeleri vererek çözmek, son kullanıcılar artık gerektiren bir uygulama kataloğu ve yükleme deneyimi ile sağlayabilir. Ayrıca, bu dağıtım senaryosu bir geliştirilmiş son kullanıcı deneyimi sağlar. Uygulama atama adımları için bkz [bir uygulamayı atar](apps-deploy.md#assign-an-app).

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izleme hakkında daha fazla bilgi edinmek için bkz. [Uygulamaları izleme](apps-monitor.md).
