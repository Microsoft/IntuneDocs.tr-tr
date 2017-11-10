---
title: "Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme | Microsoft Docs"
titlesuffix: Azure portal
description: "Android for Work uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e56aff30b353a2c98eb7effbec3e02bde066804f
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılar bir Android for Work uygulamasını çalıştırdığında ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde, genellikle ilk çalıştırıldığında kullanılır.

> [!Note]  
> Tüm uygulamalar, uygulama yapılandırmasını desteklemez. Uygulamanın, uygulama yapılandırma ilkelerini destekleyecek şekilde oluşturulup oluşturulmadığını öğrenmek için uygulamanın geliştiricisine başvurun.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Mobil uygulamalar** iş yükünü seçin.
4. **Yönet** grubunda, **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad**  
      Azure portalında görünecek profil adı.
    - **Açıklama**  
      Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**  
      **Yönetilen cihazlar**’ı seçin.
6. **Platform** için **Android**’i seçin.
7. Bir uygulama yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin.  Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın.
8. **Yapılandırma ayarlarını** seçin. Yapılandırmaları ayarlamak için şunları kullanabilirsiniz:
    - [Yapılandırma tasarımcısı](#Use-the-configuration-designer)
    - [JSON düzenleyicisini girme](#Use-the-JSON-editor)
9. **Tamam**’a ve **Ekle**’ye tıklayın.

## <a name="use-the-configuration-designer"></a>Yapılandırma tasarımcısını kullanma

Intune’a kaydedilen veya kaydedilmeyen cihazlardaki uygulamalar için yapılandırma tasarımcısını kullanabilirsiniz. Tasarımcı, belirli yapılandırma anahtarları ve değerlerini yapılandırmanıza olanak sağlar. Ayrıca her bir değer için veri türünü belirtmeniz gerekir.

Yapılandırmadaki her bir anahtar ve değer için şunları ayarlayın:

  - **Yapılandırma anahtarı**  
     Bu, belirli ayar yapılandırmalarını benzersiz olarak tanımlamak için kullanılır.
  - **Değer Türü**  
    Yapılandırma değerinin veri türü. Türler Tamsayı, Gerçek, Dize ve Boole değerlerini içerir.
  - **Yapılandırma değeri**  
    Yapılandırmanın değeri. 

## <a name="enter-the-json-editor"></a>JSON düzenleyicisini girme

Uygulamalardaki (örneğin, Paket türleri içerenler) bazı yapılandırma ayarları yapılandırma tasarımcısı ile yapılandırılamaz.  Bu değerler için JSON düzenleyicisini kullanmanız gerekir. Uygulama yüklendiğinde ayarlar uygulamalara otomatik olarak sağlanır.

1. **Yapılandırma ayarları biçimi** için **JSON düzenleyicisine gir**’i seçin.
2. Düzenleyicide, yapılandırma ayarları için JSON değerlerini tanımlayabilirsiniz. Örnek bir dosya indirip ardından yapılandırmak için **JSON şablonu indir**’i seçebilirsiniz.
3. İşiniz bittiğinde **Tamam**’ı seçip **Ekle**’ye tıklayın.

İlke oluşturulur ve ilke listesi dikey penceresinde görüntülenir.

Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Uygulamalar için izin verme durumunu önceden yapılandırma

Uygulamaların Android cihaz özelliklerine erişmesi iznini de önceden yapılandırabilirsiniz. Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister. Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Mobil uygulamalar**’ı seçin. **Yönet** altında, Uygulama yapılandırma ilkelerini seçip **Ekle**’ye tıklayın.
4. Aşağıdaki bilgileri ayarlayın:
    - **Ad** - Azure portalında görünecek profil adı
    - **Açıklama** - Azure portalında görünecek profil açıklaması
    - **Platform** - **Android**’i seçin
    - **Cihaz kayıt türü** - *Yönetilen cihazlar** sizin için önceden seçilmiştir.
5. Bir yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin.  Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın.
6. **İzinler** ve ardından **Ekle**’yi seçin.
7. Kullanılabilir uygulama izinleri listesinden seçim yapın ve ardından **Tamam**’ı seçin.
8. Bu ilkeyle verilecek her izin için bir seçenek belirleyin:
    - **Sor** - Kullanıcıdan kabul etmesini veya reddetmesini isteme.
    - **Otomatik olarak izin ver** - Kullanıcıya bildirmeden otomatik olarak onaylama.
    - **Otomatik olarak reddet** - Kullanıcıya bildirmeden otomatik olarak reddetme.
9. Uygulama yapılandırma ilkesi atamak için uygulama yapılandırma ilkesini seçin, **Atama**’yı ve ardından **Grupları Seç**’i seçin.
10. Atanacak kullanıcı gruplarını seçin ve **Seç**’i seçin.
11. İlkeyi atamak için **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Uygulamayı [atamaya](apps-deploy.md) ve [izlemeye](apps-monitor.md) devam edin.

