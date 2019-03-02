---
title: Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme
titlesuffix: Microsoft Intune
description: Kullanıcılar bir Android iş profili uygulamasını çalıştırdığında ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a04a7cda7e8baa680a43d2c009d5145807eee34
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238702"
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android iş profili uygulamalarına ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Uygulama için yapılandırma ayarlarını belirtmek adına uygulama geliştiricisinin Android yönetilen uygulama yapılandırma ayarlarını kullanıma sunması gerekir. Ayarların uygulanmasını istediğiniz kullanıcı grubuna uygulama yapılandırma ilkesini atayın.  İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde, genellikle ilk çalıştırıldığında kullanılır.

> [!Note]  
> Tüm uygulamalar, uygulama yapılandırmasını desteklemez. Uygulamanın, uygulama yapılandırma ilkelerini destekleyecek şekilde oluşturulup oluşturulmadığını öğrenmek için uygulamanın geliştiricisine başvurun.

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **İstemci uygulamaları** iş yükünü seçin.
4. **Yönet** grubunda bulunan **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad** - Azure portalında görünecek profil adı.
    - **Açıklama** - Azure portalında görünecek profil açıklaması.
    - **Cihaz kayıt türü** - **Yönetilen uygulamalar**’ı seçin.
6. **Platform** için **Android**’i seçin.
7. Bir uygulama yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin. Onayladığınız ve Intune ile eşitlenmiş Android iş profili uygulamaları listesinden seçim yapın.
8. **İzinler**’i seçin. Yapılandırmaları ayarlamak için şunları kullanabilirsiniz:
    - [Yapılandırma tasarımcısı](#use-the-configuration-designer)
    - [JSON düzenleyicisi](#enter-the-json-editor)
9. **Tamam**’ı ve daha sonra **Ekle**’yi seçin.

## <a name="use-the-configuration-designer"></a>Yapılandırma tasarımcısını kullanma

Uygulama yapılandırma ayarları desteklemek için tasarlanan Android uygulamaları için yapılandırma tasarımcısını kullanabilirsiniz. Yapılandırma, Intune’a kayıtlı cihazlarda uygulanır. Tasarımcı, bir uygulamanın kullanıma sunduğuna kıyasla daha ayrıntılı yapılandırma değerleri yapılandırmanıza imkan tanır.

**Ekle**’yi seçerek uygulama için belirtmek istediğiniz yapılandırma ayarları listesini seçin.  
Yapılandırmadaki her bir anahtar ve değer için şunları ayarlayın:

  - **Değer türü**  
    Yapılandırma değerinin veri türü. Dize değer türleri için isteğe bağlı olarak bir değişken veya sertifika profili seçebilirsiniz.
  - **Yapılandırma değeri**  
    Yapılandırmanın değeri. Değer türü için bir değişken veya sertifika seçerseniz açılan yapılandırma değeri penceresindeki değişken veya sertifika profili listesinden seçim yapabilirsiniz.  Bir sertifika seçerseniz cihaza dağıtılan sertifikanın sertifika diğer adı, çalışma zamanında doldurulur.
    
### <a name="supported-variables-for-configuration-values"></a>Yapılandırma değerleri için desteklenen değişkenler

Yapılandırma değeri olarak değişken seçerseniz şunlar arasından seçim yapabilirsiniz:

| Seçenek | Örnek |
|----|----|
| Mail | john@contoso.com |
| Kullanıcı asıl adı | john@contoso.com |
| Kısmi UPN | John |
| Etki Alanı | contoso.com |
| Kullanıcı adı | John Doe |
| Hesap kimliği | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| Kullanıcı Kimliği | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Cihaz kimliği | b9841cd9-9843-405f-be28-b2265c59ef97 |

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Çok kimlikli uygulamalarda yalnızca yapılandırılmış kuruluş hesaplarına izin verme 

Android cihazlarda aşağıdaki anahtar/değer çiftlerini kullanın:

| **Anahtar** | com.microsoft.intune.mam.AllowedAccountUPNs |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Değerler** | <ul><li>Bir veya daha fazla <code>;</code> ile sınırlandırılmış UPN.</li><li>Yalnızca bu anahtar ile tanımlanan yönetilen kullanıcı hesaplarına izin verilir.</li><li> Intune'a kayıtlı cihazlar için <code>{{userprincipalname}}</code> belirteci kayıtlı kullanıcı hesabını temsil etmek için kullanılabilir.</li></ul> |

   > [!NOTE]
   > Çoklu kimlik ile yalnızca yapılandırılmış kuruluş hesaplarına izin vermek için Android için Outlook 2.2.222 veya üzeri sürümleri kullanmanız gerekir.<p></p>
   > Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. Destekleyen uygulamalar, uygulama yapılandırmasını işler ve onaylanmamış hesapları kaldırıp engeller.<p></p>
   > Microsoft Word, Microsoft Excel, Microsoft PowerPoint için 16.0.9327.1000 ve üzeri uygulama sürümlerini kullanmanız gerekir. 

## <a name="enter-the-json-editor"></a>JSON düzenleyicisini girme

Uygulamalardaki (örneğin, Paket türleri içerenler) bazı yapılandırma ayarları yapılandırma tasarımcısı ile yapılandırılamaz. Bu değerler için JSON düzenleyicisini kullanmanız gerekir. Uygulama yüklendiğinde ayarlar uygulamalara otomatik olarak sağlanır.

1. **Yapılandırma ayarları biçimi** için **JSON düzenleyicisine gir**’i seçin.
2. Düzenleyicide, yapılandırma ayarları için JSON değerlerini tanımlayabilirsiniz. Örnek bir dosya indirip ardından yapılandırmak için **JSON şablonu indir**’i seçebilirsiniz.
3. **Tamam**’ı ve daha sonra **Ekle**’yi seçin.

İlke oluşturulur ve ilke listesi dikey penceresinde görüntülenir.

Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Uygulamalar için izin verme durumunu önceden yapılandırma

Uygulamaların Android cihaz özelliklerine erişmesi iznini de önceden yapılandırabilirsiniz. Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister. Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir.

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **İstemci uygulamaları**’nı seçin.
3. **Yönet** altında, **Uygulama yapılandırma ilkelerini** seçip **Ekle**’ye tıklayın.
4. Aşağıdaki bilgileri ayarlayın:
    - **Ad**. Azure portalında görünecek profil adı.
    - **Açıklama**. Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**. **Yönetilen cihazlar**’ı seçin.
    - **Platform**. **Android**’i seçin.
5. Bir yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçmek için **İlişkili Uygulama**’yı seçin. Onayladığınız ve Intune ile eşitlenmiş Android iş profili uygulamaları listesinden seçim yapın.
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

