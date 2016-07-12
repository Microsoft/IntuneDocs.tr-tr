---
title: "iOS uygulamalarını mobil uygulama yapılandırma ilkeleriyle yapılandırma | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 42e21b802fb605c98f688485c3b77703b3950e94
ms.openlocfilehash: a1b2fb7f2938939725465a18efb594dda91d16bd


---

# iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma
Kullanıcı bir uygulama çalıştırdığında gerekebilecek ayarları sağlamak için, Microsoft Intune’daki mobil uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcının şunları belirtmesini gerektirebilir:

-   Çalıştırıldığında özel bir bağlantı noktası numarası

-   Dil ayarları

-   Güvenlik ayarları

-   Bir şirket logosu gibi marka ayarları

Bu ayarlar kullanıcı tarafından hatalı girildiği takdirde, yardım masanız üzerindeki yük artabileceği gibi, yeni uygulamalara geçiş de yavaşlayabilir.

Mobil uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları bir ilke ile kullanıcılara dağıtmanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcının herhangi bir eylem yapması gerekmez.

Bu ilkeleri doğrudan kullanıcılara ve cihazlara dağıtmazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirilir, ardından uygulamayı dağıtırsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde (genellikle ilk çalıştırıldığında) kullanılır.

> [!TIP]
> Bu ilke türü şu anda yalnızca iOS 7.1 ve üzerini çalıştıran cihazlarda desteklenir ve aşağıdaki uygulama yükleme türlerini destekler:
> 
> -   **Uygulama mağazasından yönetilen iOS uygulaması**
> -   **iOS için uygulama paketi**
> 
> Uygulama yükleme türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps.md).

## Mobil uygulama yapılandırma ilkesi yapılandırma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Genel Bakış** &gt; **İlke Ekle**’ye tıklayın.

2.  İlkeler listesinde **iOS**’u genişletin, **Mobil Uygulama Yapılandırma**’ya ve ardından **İlke Oluştur**’a tıklayın.

    > [!TIP]
    > Bu ilke türü için yalnızca özel ayarlar yapılandırabilirsiniz. Önerilen ayarlar kullanılamaz.

3.   **İlke Oluştur** sayfasının **Genel** bölümünde, mobil uygulama yapılandırma ilkesi için bir ad ve isteğe bağlı bir açıklama sağlayın.

4.  Sayfanın **Mobil Uygulama Yapılandırma İlkesi** bölümünde, kutunun içine istediğiniz uygulama yapılandırma ayarlarını girin veya bunları içeren bir XML özellik listesini yapıştırın.

    > [!TIP]
    > XML özellik listeleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [XML Özellik Listelerini Anlama](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) konusuna bakın.
    > 
    > XML özellik listesinin biçimi, yapılandırdığınız uygulamaya bağlı olarak değişir. Kullanılacak tam biçim hakkında ayrıntılı bilgi için uygulamanın sağlayıcısına başvurun.
    > 
    > Intune, bir özellik listesinde aşağıdaki veri türlerini destekler:
    > 
    > &lt;integer&gt;
    > &lt;real&gt;
    > &lt;string&gt;
    > &lt;array&gt;
    > &lt;dict&gt;
    > &lt;true /&gt; veya &lt;false /&gt;
    > 
    > Veri türleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [Özellik Listeleri Hakkında](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) konusuna bakın.
    >
        > Ayrıca, Intune özellik listesinde aşağıdaki belirteç türlerini destekler:
    >    
    > \{\{userprincipalname\}\} - (Örnek: **Ahmet@contoso.com**) \{\{mail\}\} - (Örnek: **Ahmet@contoso.com**) \{\{partialupn\}\} - (Örnek: **Ahmet**) \{\{accountid\}\} - (Örnek: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**) \{\{deviceid\}\} - (Örnek: **b9841cd9-9843-405f-be28-b2265c59ef97**) \{\{userid\}\} - (Örnek: **3ec2c00f-b125-4519-acf0-302ac3761822**) \{\{username\}\} - (Örnek: **Ahmet Kara**) \{\{serialnumber\}\} - (Örnek: **F4KN99ZUG5V2**) iOS cihazları için \{\{serialnumberlast4digits\}\} - (Örnek: **G5V2**) iOS cihazları için
>
> \{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.




5.  Girdiğiniz XML kodunun geçerli bir özellik listesi biçiminde olduğundan emin olmak için **Doğrula** ’ya tıklayın.

    > [!IMPORTANT]
    > **Doğrula**’ya tıkladığınızda, Intune girdiğiniz XML kodunun geçerli bir biçimde olup olmadığını denetler. XML özellik listesinin ilişkilendirildiği uygulama ile çalışıp çalışmayacağını denetlemez.

6.  İşiniz bittiğinde **İlkeyi Kaydet**‘e tıklayın.

Yeni ilke **Yapılandırma İlkeleri** düğümünde görüntülenir.

## Mobil uygulama yapılandırma ilkesini bir uygulamayla ilişkilendirme
Mobil uygulama yapılandırma ilkesini oluşturduktan sonra, bunu ilkedeki ayarların uygulanmasını istediğiniz iOS uygulamasıyla ilişkilendirmeniz gerekir.

Bunu yapmak için [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) ve [Microsoft Intune ile uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md) konularında verilen uygulama dağıtımı oluşturma adımlarını izleyin. Sihirbazın **Mobil Uygulama Yapılandırma** sayfasına ulaştığınızda, **Uygulama Yapılandırma İlkesi** açılır listesinden uygulamayla ilişkilendirmek istediğiniz ilkeyi seçin.

Ardından, uygulamayı her zamanki gibi dağıtma ve izleme aşamasına geçin.

Dağıtılan uygulama bir cihazda çalıştırıldığında, mobil uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

> [!TIP]
> Mobil uygulama yapılandırma ilkelerinden biri veya daha fazlası çakışırsa ilkelerin hiçbiri uygulanmaz ve çakışma, Intune yönetim konsolunun **Pano** bölümünde raporlanır.

## Mobil uygulama yapılandırma XML dosyası için örnek biçim

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





<!--HONumber=Jun16_HO4-->


