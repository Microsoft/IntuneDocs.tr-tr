---
title: "iOS için Intune uygulama yapılandırma ilkelerini kullanma"
titleSuffix: Intune on Azure
description: "iOS uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a9d56a2f570c0332b394b03f25deb6351b6ba67
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>iOS için Microsoft Intune uygulama yapılandırma ilkelerini kullanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılar bir iOS uygulamasını çalıştırdığında kullanılan ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

-   Özel bağlantı noktası numarası.

-   Dil ayarları.

-   Güvenlik ayarları.

-   Bir şirket logosu gibi marka ayarları.

Kullanıcılar, bu ayarları hatalı şekilde girerse yardım masanız üzerindeki yük artabilir ve yeni uygulamaların benimsenmesi yavaşlayabilir.

Uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları bir ilke ile kullanıcılara atamanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez. Uygulamalar, uygulama yapılandırmaları kullanımını desteklemek üzere yazılmış olmalıdır. Daha fazla bilgi için uygulama satıcınıza başvurun.

Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından ilke denetimi gerçekleştirildiğinde (genellikle ilk çalıştırıldığında) kullanılır.

> [!TIP]
> Bu ilke türü şu anda yalnızca iOS 8.0 ve üzeri sistemleri çalıştıran cihazlar için kullanılabilir. Aşağıdaki uygulama yükleme türlerini destekler:
>
> -   **Uygulama mağazasından yönetilen iOS uygulaması**
> -   **iOS için uygulama paketi**
>
> Uygulama yükleme türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Uygulama yapılandırma ilkesi oluşturma
1.  Azure Portal’da oturum açın.
2.  **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3.  **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4.  **Mobil uygulamalar** iş yükünde **Yönet** > **Tüm Uygulama Yapılandırma İlkeleri**’ni seçin.
5.  İlke listesi dikey penceresinde **Ekle**’yi seçin.
6.  **Yapılandırma İlkesi Ekle** dikey penceresinde, uygulama yapılandırma ilkesi için **Ad** ve isteğe bağlı bir **Açıklama** sağlayın.
7.  **Cihaz kayıt türü** için şunlardan birini seçin:
    - **Intune’a kaydedilmiş** - Intune tarafından yönetilen uygulamalar için.
    - **Intune’a kaydedilmemiş** - Intune tarafından yönetilmeyen veya başka bir çözüm tarafından yönetilen uygulamalar için.
8.  **Platform** için **iOS**’u seçin (yalnızca Intune’a kaydedilmiş cihazlar için)
9.  **İlişkili Uygulama**’yı seçin ve ardından **İlişkili Uygulama** dikey penceresinde, yapılandırmayı uygulamak istediğiniz yönetilen uygulamayı seçin.
10. **Yapılandırma İlkesi Ekle** dikey penceresinde **Yapılandırma ayarları**’nı seçin
11. **Yapılandırma Ayarları** dikey penceresinde, yapılandırma profilini oluşturan XML değerlerini nasıl belirtmek istediğinizi seçin:
    - **XML verisi gir** (yalnızca Intune’a kaydedilmiş cihazlar için) - İstediğiniz uygulama yapılandırma ayarlarını içeren XML özellik listesini girin veya yapıştırın. XML özellik listesinin biçimi, yapılandırdığınız uygulamaya bağlı olarak değişir. Kullanılacak tam biçim hakkında ayrıntılı bilgi için uygulamanın sağlayıcısına başvurun.
Intune, girdiğiniz XML kodunun geçerli bir biçimde olup olmadığını denetler. XML özellik listesinin ilişkilendirildiği uygulama ile çalışıp çalışmayacağını denetlemez.
XML özellik listeleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [XML Özellik Listelerini Anlama](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) konusuna bakın.
    - **Yapılandırma tasarımcısını kullan** (cihazın Intune’a kaydedilmiş olup olmamasından bağımsız olarak) - XML anahtar ve değer çiftlerini doğrudan portalda belirtmenize olanak tanır.
11. Bitirdiğinizde, **Yapılandırma İlkesi Ekle** dikey penceresine gidin ve **Oluştur**’a basın.

İlke oluşturulur ve ilke listesi dikey penceresinde görüntülenir.



>[!Note]
>Cihazın Intune’a kaydedilmiş olup olmamasından bağımsız olarak, iş kolu uygulamalarını Intune uygulama koruma ilkeleri ve uygulama yapılandırma ilkeleri tarafından yönetilmeye hazırlamak için [Intune Uygulama SDK’sini](https://docs.microsoft.com/intune/app-sdk-ios) kullanabilirsiniz. Örneğin [Intune Managed Browser](app-configuration-managed-browser.md)’da izin verilen ve engellenen URL’leri yapılandırmak için bir uygulama yapılandırma ilkesi kullanabilirsiniz. Bir uygulama bu ilkelerle uyumlu hale geldiğinde, bir ilke kullanarak bu ilkeleri yapılandırabilirsiniz.


Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.
Bir veya daha fazla uygulama yapılandırma ilkesi çakıştığında ne olacağı hakkında bilgi için yapılandırdığınız uygulamaya ait belgelere bakın.

>[!Tip]
>Ayrıca bu görevleri tamamlamak için Grafik API’si de kullanabilirsiniz. Ayrıntılar için bkz. [Grafik API’si Başvurusu MAM Hedefli Yapılandırma](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).


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

## <a name="next-steps"></a>Sonraki adımlar

Normal yollarla, uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.