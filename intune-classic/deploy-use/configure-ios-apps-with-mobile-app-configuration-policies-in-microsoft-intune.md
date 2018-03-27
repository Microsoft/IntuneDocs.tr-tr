---
title: iOS mobil uygulama yapılandırma ilkeleri kullanma
description: Kullanıcılar bir iOS uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e0fa9f66ee0338b21e12a27ef60fb0df22d23030
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Kullanıcılar bir iOS uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

-   Özel bağlantı noktası numarası.

-   Dil ayarları.

-   Güvenlik ayarları.

-   Bir şirket logosu gibi marka ayarları.

Bu ayarlar kullanıcılar tarafından hatalı girildiği takdirde, yardım masanız üzerindeki yük artabilir ve uygulamalara geçiş yavaşlayabilir.

Mobil uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları bir ilke ile kullanıcılara dağıtmanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez.

Bu ilkeleri doğrudan kullanıcılara ve cihazlara dağıtmazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı dağıtırsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde (genellikle ilk çalıştırıldığında) kullanılır.

> [!TIP]
> Bu ilke türü şu anda yalnızca iOS 8.0 ve üzeri sistemleri çalıştıran cihazlar için kullanılabilir. Aşağıdaki uygulama yükleme türlerini destekler:
>
> -   **Uygulama mağazasından yönetilen iOS uygulaması**
> -   **iOS için uygulama paketi**
>
> Uygulama yükleme türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps.md).

## <a name="configure-a-mobile-app-configuration-policy"></a>Mobil uygulama yapılandırma ilkesi yapılandırma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **İlke** &gt; **Genel Bakış** &gt; **İlke Ekle**’yi seçin.

2.  İlkeler listesinde **iOS**’u genişletin, **Mobil Uygulama Yapılandırma**’yı ve ardından **İlke Oluştur**’u seçin.

    > [!TIP]
    > Bu ilke türü için yalnızca özel ayarlar yapılandırabilirsiniz. Önerilen ayarlar kullanılamaz.

3.  **İlke Oluştur** sayfasının **Genel** bölümünde, mobil uygulama yapılandırma ilkesi için bir ad ve isteğe bağlı bir açıklama sağlayın.

4.  Sayfanın **Mobil Uygulama Yapılandırma İlkesi** bölümünde, kutunun içine istediğiniz uygulama yapılandırma ayarlarını girin veya bunları içeren bir XML özellik listesini yapıştırın. XML özellik listesinin biçimi, yapılandırdığınız uygulamaya bağlı olarak değişir. Kullanılacak tam biçim hakkında ayrıntılı bilgi için uygulamanın sağlayıcısına başvurun.

    > [!TIP]
    > XML özellik listeleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [XML Özellik Listelerini Anlama](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) konusuna bakın.

5.  Girdiğiniz XML kodunun geçerli bir özellik listesi biçiminde olduğundan emin olmak için **Doğrula** ’ya tıklayın.

    > [!IMPORTANT]
    > **Doğrula**’ya tıkladığınızda, Intune girdiğiniz XML kodunun geçerli bir biçimde olup olmadığını denetler. XML özellik listesinin ilişkilendirildiği uygulama ile çalışıp çalışmayacağını denetlemez.

6.  İşiniz bittiğinde **İlkeyi Kaydet**‘e tıklayın.

Yeni ilke **Yapılandırma İlkeleri** düğümünde görüntülenir.

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

## <a name="associate-a-mobile-app-configuration-policy-with-an-app"></a>Mobil uygulama yapılandırma ilkesini bir uygulamayla ilişkilendirme
Mobil uygulama yapılandırma ilkesini oluşturduktan sonra, bunu ilkedeki ayarların uygulanmasını istediğiniz iOS uygulamasıyla ilişkilendirmeniz gerekir.

Bunu yapmak için [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) ve [Microsoft Intune ile uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md) konularında verilen uygulama dağıtımı oluşturma adımlarını izleyin. Sihirbazın **Mobil Uygulama Yapılandırma** sayfasına ulaştığınızda, **Uygulama Yapılandırma İlkesi** açılır listesinden uygulamayla ilişkilendirmek istediğiniz ilkeyi seçin.

Ardından, uygulamayı her zamanki gibi dağıtma ve izleme aşamasına geçin.

Dağıtılan uygulama bir cihazda çalıştırıldığında, mobil uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

> [!TIP]
> Bir veya daha fazla mobil uygulama yapılandırma ilkeleri arasında çakışma varsa, hiçbir ilke uygulanmaz. Çakışma, Intune yönetim konsolunda **Pano**’ya bildirilir.

## <a name="example-format-for-a-mobile-app-configuration-xml-file"></a>Bir mobil uygulama yapılandırma XML dosyası için örnek biçim

Bir mobil uygulama yapılandırma dosyası oluşturduğunuzda bu biçimi kullanarak aşağıdaki değerlerden birini veya daha fazlasını belirtebilirsiniz:

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
