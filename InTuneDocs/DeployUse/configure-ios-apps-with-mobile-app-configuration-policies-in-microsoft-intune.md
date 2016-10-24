---
title: "iOS mobil uygulama yapılandırma ilkelerini kullanma | Microsoft Intune"
description: "Kullanıcılar bir iOS uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 360865bcd97230e264ee3439407e8dd3017d0055
ms.openlocfilehash: 1f239270c26a70b161e52c24e94ca5c2cae9ca3a


---

# iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma
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

## Mobil uygulama yapılandırma ilkesi yapılandırma

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

## XML dosya biçimi hakkında bilgi

Intune, bir özellik listesinde aşağıdaki veri türlerini destekler:
    
- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; veya &lt;false /&gt;
     
Veri türleri hakkında daha fazla bilgi için iOS Geliştirici Kitaplığı’ndaki [Özellik Listeleri Hakkında](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) konusuna bakın.

Ayrıca, Intune özellik listesinde aşağıdaki belirteç türlerini destekler:
- \{\{kullanıcıasıladı\}\} - (Örnek: **Ali@contoso.com**)
- \{\{eposta\}\} - (Örnek: **Ali@contoso.com**)
- \{\{kısmiupn\}\} - (Örnek: **Ali**)
- \{\{hesapkimliği\}\} - (Örnek: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{cihazkimliği\}\} - (Örnek: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{kullanıcıkimliği\}\} - (Örnek: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{kullanıcıadı\}\} - (Örnek: **Ali Yılmaz**)
- \{\{serinumarası\}\} - (Örnek: **F4KN99ZUG5V2**) iOS cihazları için
- \{\{serinumarasıson4hane\}\} - (Örnek: **G5V2**) iOS cihazları için
    
\{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.

## Mobil uygulama yapılandırma ilkesini bir uygulamayla ilişkilendirme
Mobil uygulama yapılandırma ilkesini oluşturduktan sonra, bunu ilkedeki ayarların uygulanmasını istediğiniz iOS uygulamasıyla ilişkilendirmeniz gerekir.

Bunu yapmak için [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) ve [Microsoft Intune ile uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md) konularında verilen uygulama dağıtımı oluşturma adımlarını izleyin. Sihirbazın **Mobil Uygulama Yapılandırma** sayfasına ulaştığınızda, **Uygulama Yapılandırma İlkesi** açılır listesinden uygulamayla ilişkilendirmek istediğiniz ilkeyi seçin.

Ardından, uygulamayı her zamanki gibi dağıtma ve izleme aşamasına geçin.

Dağıtılan uygulama bir cihazda çalıştırıldığında, mobil uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

> [!TIP]
> Bir veya daha fazla mobil uygulama yapılandırma ilkeleri arasında çakışma varsa, hiçbir ilke uygulanmaz. Çakışma, Intune yönetim konsolunda **Pano**’ya bildirilir.

## Bir mobil uygulama yapılandırma XML dosyası için örnek biçim

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



<!--HONumber=Sep16_HO3-->


