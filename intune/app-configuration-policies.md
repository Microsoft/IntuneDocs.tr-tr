---
title: "Intune uygulama yapılandırma ilkelerini kullanma | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f38313d085f47a7e9c8856ef02328c175a3964c8
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-use-microsoft-intune-app-configuration-policies"></a>Microsoft Intune uygulama yapılandırma ilkelerini kullanma

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Kullanıcılar bir uygulamayı çalıştırdığında gerekebilecek ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

-   Özel bağlantı noktası numarası.

-   Dil ayarları.

-   Güvenlik ayarları.

-   Bir şirket logosu gibi marka ayarları.

Bu ayarlar kullanıcılar tarafından hatalı girildiği takdirde, yardım masanız üzerindeki yük artabilir ve uygulamalara geçiş yavaşlayabilir.

Uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları bir ilke ile kullanıcılara atamanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez.

Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde (genellikle ilk çalıştırıldığında) kullanılır.

> [!TIP]
> Bu ilke türü şu anda yalnızca iOS 8.0 ve üzeri sistemleri çalıştıran cihazlar için kullanılabilir. Aşağıdaki uygulama yükleme türlerini destekler:
>
> -   **Uygulama mağazasından yönetilen iOS uygulaması**
> -   **iOS için uygulama paketi**
>
> Uygulama yükleme türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Uygulama yapılandırma ilkesi oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde, **Mobil uygulamalar**’ı seçin.
1.  **Mobil uygulamalar** iş yükünde **Yönet** > **Tüm Uygulama Yapılandırma İlkeleri**’ni seçin.

2.  İlke listesi dikey penceresinde **Ekle**’yi seçin.

3.  **Yapılandırma İlkesi Ekle** dikey penceresinde, uygulama yapılandırma ilkesi için ad ve isteğe bağlı bir açıklama sağlayın.
4.  **İlişkili Uygulama**’yı seçin ve ardından **İlişkili Uygulama** dikey penceresinde, yapılandırmayı uygulamak istediğiniz yönetilen uygulamayı seçin.
5.  **Yapılandırma İlkesi Ekle** dikey penceresinde **Yapılandırma ayarları**’nı seçin ve ardından Yapılandırma Ayarları dikey penceresinde, yapılandırma profilini oluşturan XML değerlerini nasıl belirtmek istediğinizi seçin:
    - **XML verilerini gir** - İstediğiniz uygulama yapılandırma ayarlarını içeren XML özellik listesini girin veya yapıştırın. XML özellik listesinin biçimi, yapılandırdığınız uygulamaya bağlı olarak değişir. Kullanılacak tam biçim hakkında ayrıntılı bilgi için uygulamanın sağlayıcısına başvurun.
    Intune, girdiğiniz XML kodunun geçerli bir biçimde olup olmadığını denetler. XML özellik listesinin ilişkilendirildiği uygulama ile çalışıp çalışmayacağını denetlemez.
    XML özellik listeleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [XML Özellik Listelerini Anlama](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) konusuna bakın.
    - **Yapılandırma tasarımcısını kullan** - XML anahtar ve değer çiftlerini doğrudan portalda belirtmenize olanak tanır.
8. Bitirdiğinizde, **Yapılandırma İlkesi Ekle** dikey penceresine gidin ve **Oluştur**’a basın.

İlke oluşturulur ve ilke listesi dikey penceresinde görüntülenir.

Sonra, normal yollarla uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.

Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

> [!TIP]
> Bir veya birden çok uygulama yapılandırma ilkesi arasında çakışma varsa, hiçbir ilke uygulanmaz.

## <a name="information-about-the-xml-file-format"></a>XML dosya biçimi hakkında bilgi

Intune, bir özellik listesinde aşağıdaki veri türlerini destekler:

- &lt;tamsayı&gt;
- &lt;gerçek&gt;
- &lt;dize&gt;
- &lt;dizi&gt;
- &lt;sözlük&gt;
- &lt;true /&gt; veya &lt;false /&gt;

Veri türleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [Özellik Listeleri Hakkında](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) konusuna bakın.

Ayrıca, Intune özellik listesinde aşağıdaki belirteç türlerini destekler:
- \{\{userprincipalname\}\} - (Örnek: **John@contoso.com**)
- \{\{mail\}\} - (Örnek: **John@contoso.com**)
- \{\{partialupn\}\} - (Örnek: **John**)
- \{\{accountid\}\} - (Örnek: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (Örnek: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (Örnek: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (Örnek: **John Doe**)
- \{\{serialnumber\}\} - (Örnek: **F4KN99ZUG5V2**) iOS cihazlar için
- \{\{serialnumberlast4digits\}\} - (Örnek: **G5V2**) iOS cihazlar için

\{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.





## <a name="example-format-for-an-app-configuration-xml-file"></a>Uygulama yapılandırma XML dosyası için örnek biçim

Uygulama yapılandırma dosyasını oluşturduğunuzda, bu biçimi kullanarak aşağıdaki değerlerden birini veya daha fazlasını belirtebilirsiniz:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```

