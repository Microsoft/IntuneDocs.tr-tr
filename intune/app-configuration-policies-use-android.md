---
title: "Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme"
titlesuffix: Microsoft Intune
description: "Kullanıcılar bir Android for Work uygulamasını çalıştırdığında ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a448c33e8324492c68d509a12d5901f41ed4873a
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılar bir Android for Work uygulamasını çalıştırdığında ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde, genellikle ilk çalıştırıldığında kullanılır.

> [!Note]  
> Tüm uygulamalar, uygulama yapılandırmasını desteklemez. Uygulamanın, uygulama yapılandırma ilkelerini destekleyecek şekilde oluşturulup oluşturulmadığını öğrenmek için uygulamanın geliştiricisine başvurun.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Mobil uygulamalar** iş yükünü seçin.
4. **Yönet** grubunda bulunan **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad**  
      Azure portalında görünecek profil adı.
    - **Açıklama**  
      Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**  
      **Yönetilen cihazlar**’ı seçin.
6. **Platform** için **Android for Work**’u seçin.
7. Bir uygulama yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin. Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın.
8. **Yapılandırma ayarlarını** seçin. Yapılandırmaları ayarlamak için şunları kullanabilirsiniz:
    - [Yapılandırma tasarımcısı](#Use-the-configuration-designer)
    - [JSON düzenleyicisi](#Enter-the-JSON-editor)
9. **Tamam**’ı ve daha sonra **Ekle**’yi seçin.

## <a name="use-the-configuration-designer"></a>Yapılandırma tasarımcısını kullanma

Intune’a kaydedilen veya kaydedilmeyen cihazlardaki uygulamalar için yapılandırma tasarımcısını kullanabilirsiniz. Tasarımcı, belirli yapılandırma anahtarları ve değerleri yapılandırmanıza imkan tanır. Ayrıca her bir değer için veri türünü belirtmeniz gerekir.

Yapılandırmadaki her bir anahtar ve değer için şunları ayarlayın:

  - **Yapılandırma anahtarı**  
     Belirli ayar yapılandırmalarını benzersiz olarak tanımlayan anahtar.
  - **Değer türü**  
    Yapılandırma değerinin veri türü. Türler Tamsayı, Gerçek, Dize ve Boole değerlerini içerir.
  - **Yapılandırma değeri**  
    Yapılandırmanın değeri. 

## <a name="enter-the-json-editor"></a>JSON düzenleyicisini girme

Uygulamalardaki (örneğin, Paket türleri içerenler) bazı yapılandırma ayarları yapılandırma tasarımcısı ile yapılandırılamaz. Bu değerler için JSON düzenleyicisini kullanmanız gerekir. Uygulama yüklendiğinde ayarlar uygulamalara otomatik olarak sağlanır.

1. **Yapılandırma ayarları biçimi** için **JSON düzenleyicisine gir**’i seçin.
2. Düzenleyicide, yapılandırma ayarları için JSON değerlerini tanımlayabilirsiniz. Örnek bir dosya indirip ardından yapılandırmak için **JSON şablonu indir**’i seçebilirsiniz.
3. **Tamam**’ı ve daha sonra **Ekle**’yi seçin.

İlke oluşturulur ve ilke listesi dikey penceresinde görüntülenir.

Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Uygulamalar için izin verme durumunu önceden yapılandırma

Uygulamaların Android cihaz özelliklerine erişmesi iznini de önceden yapılandırabilirsiniz. Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister. Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Mobil uygulamalar**’ı seçin.
3. **Yönet** altında, **Uygulama yapılandırma ilkelerini** seçip **Ekle**’ye tıklayın.
4. Aşağıdaki bilgileri ayarlayın:
    - **Ad**. Azure portalında görünecek profil adı.
    - **Açıklama**. Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**. **Yönetilen cihazlar**’ı seçin.
    - **Platform**. **Android for Work**’u seçin.
5. Bir yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin. Onayladığınız ve Intune ile eşitlenmiş Android for Work uygulamaları listesinden seçim yapın.
6. **İzinler** ve ardından **Ekle**’yi seçin.
7. Kullanılabilir uygulama izinleri listesinden seçim yapın ve ardından **Tamam**’ı seçin.
8. Bu ilkeyle verilecek her izin için bir seçenek belirleyin:
    - **Sor**. Kullanıcıdan kabul etmesini veya reddetmesini isteme.
    - **Otomatik olarak izin ver**. Kullanıcıya bildirmeden otomatik olarak onayla.
    - **Otomatik olarak reddet**. Kullanıcıya bildirmeden otomatik olarak reddet.
9. Uygulama yapılandırma ilkesi atamak için uygulama yapılandırma ilkesini seçin, **Atama**’yı ve ardından **Grupları Seç**’i seçin.
10. Atanacak kullanıcı gruplarını seçin ve **Seç**’i seçin.
11. İlkeyi atamak için **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Uygulamayı [atamaya](apps-deploy.md) ve [izlemeye](apps-monitor.md) devam edin.

