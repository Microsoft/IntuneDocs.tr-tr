---
title: "Android for Work için Intune uygulama yapılandırma ilkelerini kullanma"
titleSuffix: Intune on Azure
description: "Android for Work uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9ea697cafa0f277c176e55443250d32ca378dbb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Android for Work için Microsoft Intune uygulama yapılandırma ilkelerini kullanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılar bir Android for Work uygulamasını çalıştırdığında kullanılabilecek ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Uygulama yapılandırmasını tüm uygulamalar desteklemez. Uygulamanın, uygulama yapılandırma ilkelerini destekleyecek şekilde oluşturulup oluşturulmadığını görmek için uygulamanın geliştiricisine danışın.

Uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce kullanıcılarınız için kullanılabilir uygulama ayarlarını önceden yapılandırmanıza yardımcı olabilir. Bazı Android uygulamaları, Intune konsolunda [yapılandırma tasarımcısı](#use-configuration-designer) ile yapılandırabileceğiniz yönetilen yapılandırma seçeneklerini destekler. Uygulamalardaki (örneğin, Paket türleri içerenler) bazı yapılandırma ayarları yapılandırma tasarımcısı ile yapılandırılamaz.  Bu değerler için [JSON düzenleyici](#use-json-editor) kullanmanız gerekir.   Uygulama yüklendiğinde ayarlar uygulamalara otomatik olarak sağlanır.

Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde, genellikle ilk çalıştırıldığında kullanılır).

## <a name="use-configuration-designer"></a>Yapılandırma tasarımcısı kullanma

1. Intune portalında **Mobil uygulamalar**’ı seçin. **Yönet** altında, **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
2. Aşağıdaki bilgileri ayarlayın:
    - **Ad** - Intune konsolunda görünecek profil adı
    - **Açıklama** - Intune konsolunda görünecek profil açıklaması
    - **Platform** - **Android**’i seçin
    - **Cihaz kayıt türü** - **Intune'a Kayıtlı** sizin için önceden seçilmiştir.
3. Bir yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin.  Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın
4. **Yapılandırma ayarlarını** seçin.
5. **Yapılandırma ayarları biçimi** için **Yapılandırma tasarımcısını kullan**’ı seçin.
6. **Ekle**’yi seçin. Kullanılabilir yapılandırma ayarlarının listesi görüntülenir. Liste şunları içerir:
    - **Yapılandırma anahtarları** - Ayarın adı.
    - **Değer türü** - Yapılandırılabilir ayar, örneğin **Boolean** veya **Dize**.
    - **Açıklama** - Yapılandırma ayarının açıklaması.
7. Bu profille yapılandırmak istediğiniz ayarların onay kutularını işaretleyip **Tamam**’a tıklayın.
8. Seçtiğiniz ayarların listesi kullanılabilir **Yapılandırma değeri** ile birlikte görüntülenir. Her ayar için bir değer belirtin ve ardından **Tamam**’a tıklayın.

## <a name="use-json-editor"></a>JSON düzenleyicisini kullanma

1. Intune portalında **Mobil uygulamalar**’ı seçin. **Yönet** altında, **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
2. Aşağıdaki bilgileri ayarlayın:
    - **Ad** - Intune konsolunda görünecek profil adı
    - **Açıklama** - Intune konsolunda görünecek profil açıklaması
    - **Platform** - **Android**’i seçin
    - **Cihaz kayıt türü** - **Intune'a Kayıtlı** sizin için önceden seçilmiştir.
3. Bir yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin.  Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın.
5. **Yapılandırma Ayarları**’nı seçin.
6. **Yapılandırma ayarları biçimi** için **JSON düzenleyicisine gir**’i seçin.
7. Düzenleyicide, yapılandırma ayarları için JSON değerlerini tanımlayabilirsiniz. Örnek bir dosya indirip ardından yapılandırmak için **JSON şablonu indir**’i seçebilirsiniz.
8. İşiniz bittiğinde **Tamam**’ı seçip **Ekle**’ye tıklayın.

İlke oluşturulur ve ilke listesi dikey penceresinde görüntülenir.

Sonra, normal yollarla uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.

Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Uygulamalar için izin verme durumunu önceden yapılandırma

Uygulamaların Android cihaz özelliklerine erişmesi iznini de önceden yapılandırabilirsiniz. Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister. Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir.

1. Intune portalında **Mobil uygulamalar**’ı seçin. **Yönet** altında, **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
2. Aşağıdaki bilgileri ayarlayın:
    - **Ad** - Intune konsolunda görünecek profil adı
    - **Açıklama** - Intune konsolunda görünecek profil açıklaması
    - **Platform** - **Android**’i seçin
    - **Cihaz kayıt türü** - **Intune'a Kayıtlı** sizin için önceden seçilmiştir.
3. Bir yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin.  Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın.
5. **İzinler** ve ardından **Ekle**’yi seçin.
6. Kullanılabilir uygulama izinleri listesinden seçim yapın ve ardından **Tamam**’ı seçin.
7. Bu ilkeyle verilecek her izin için bir seçenek belirleyin:
    - **Sor** - Kullanıcıdan kabul etmesini veya reddetmesini isteme.
    - **Otomatik olarak izin ver** - Kullanıcıya bildirmeden otomatik olarak onaylama.
    - **Otomatik olarak reddet** - Kullanıcıya bildirmeden otomatik olarak reddetme.
8. Uygulama yapılandırma ilkesi atamak için uygulama yapılandırma ilkesini seçin, **Atama**’yı ve ardından **Grupları Seç**’i seçin.
9. Atanacak kullanıcı gruplarını seçin ve **Seç**’i seçin.
10. İlkeyi atamak için **Kaydet**’i seçin.
