---
title: "iOS için Intune uygulama yapılandırma ilkelerini kullanma"
titleSuffix: Intune on Azure
description: "iOS uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>iOS için Microsoft Intune uygulama yapılandırma ilkelerini kullanma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılar bir iOS uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

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
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
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

## <a name="create-a-mam-targeted-configuration-policy"></a>MAM hedeflenen bir yapılandırma ilkesi oluşturma
MAM'ı hedefleyen yapılandırma, bir uygulamanın Intune Uygulama SDK'sı aracılığıyla yapılandırma verileri almasını sağlar. Bu verilerin biçimi ve çeşitleri, uygulamanın sahibi/geliştiricisi tarafından tanımlanmalı ve Intune müşterilerine anlatılmalıdır. Intune yöneticileri, yapılandırma verilerini Intune Azure konsolu aracılığıyla hedefleyip dağıtabilir. MAM hedeflenen yapılandırma verileri MAM hizmetinden MAM-WE etkin uygulamalara sağlanabilir. Örneğin, [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser)’ın izin verilen/engellenen url listesi var. Uygulama yapılandırma verileri MDM kanalı yerine uygulamaya doğrudan MAM Hizmetimiz aracılığıyla iletilir. [MDM uygulama yapılandırma ilkeleri](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy), MDM aracılığıyla yerel çözümdür. MAM hedeflenen yapılandırmayla olan en önemli farkı, uygulamanın çalıştığı cihazın MDM-kayıtlı olma gereksinimi olmamasıdır. MAM hedeflenen yapılandırma, iOS ve Android’de kullanılabilir. iOS için bu uygulama, iOS için Intune Uygulama SDK’sını (sürüm 7.0.1) kullanmalı ve uygulama yapılandırma ayarlarında yer almalıdır. MAM hedeflenen yapılandırma ilkesi oluşturmak için adımlar aşağıdaki gibidir: 

1. **Azure portalında** oturum açın.

2. **Intune > Mobil uygulamalar - Uygulama yapılandırma ilkeleri**’ni seçin.

3. **Uygulama yapılandırma ilkeleri** dikey penceresinde, **Ekle**’yi seçin.

4. Uygulama yapılandırma ayarları için bir **Ad** ve isteğe bağlı bir **Açıklama** girin ve ardından **Intune’a kayıtlı değil**’i seçin.

5. **Gerekli uygulamaları seç**’i seçin ve ardından **Hedeflenen** uygulamalar dikey penceresinde, düşündüğünüz platformlar için uygulamaları seçin. <br>
**Not:** LOB uygulamaları için **Daha fazla uygulama**’yı seçin. Uygulamanız için paket kimliğini girin.

6. **Tamam**’ı seçerek **Uygulama yapılandırması ekle** dikey penceresine dönün.

7. **Yapılandırmayı tanımla**’yı seçin. **Yapılandırma** dikey penceresinde, yapılandırmaları sağlamak için anahtar ve değer çiftlerini tanımlayın.

8. İşiniz bittiğinde **Tamam**’ı seçin.

9. **Uygulama yapılandırması ekle** dikey penceresinde, **Oluştur**’u seçin.

Yeni yapılandırma oluşturulur ve Uygulama yapılandırması dikey penceresinde görüntülenir.

Sonra, normal yollarla uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.

Atanan uygulama (Intune Uygulama SDK’sı ile tümleşik) bir cihazda çalıştırıldığında, MAM hedeflenen yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır. Atanan uygulamanın, Intune Uygulama SDK'sının desteklenen sürümüyle tümleşik olması gerekir. MAM Hedeflenen Yapılandırma ilkelerini kullanmak için uygulama geliştirme gereksinimleri hakkında daha fazla bilgi için bkz. [iOS Intune Uygulama SDK'sı Tümleştirmesi Kılavuzu](https://docs.microsoft.com/intune/app-sdk-ios).

Grafik API'sinin MAM hedeflenen yapılandırma değerlerine göre özellikleri hakkında daha fazla bilgi için bkz. [Grafik API'si Başvurusu MAM Hedeflenen Yapılandırma](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

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
