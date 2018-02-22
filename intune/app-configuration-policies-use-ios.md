---
title: "Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme | Microsoft Docs"
titlesuffix: Azure portal
description: "iOS uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b64d8b60a4c577acc2f6ef161f6de37ac529e7ac
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Kullanıcılar bir iOS uygulamasını çalıştırdığında ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Bu ilkeleri kullanıcılara ve cihazlara doğrudan atamazsınız. Bunun yerine, ilkeyi bir uygulamayla ilişkilendirir ve uygulamayı atarsınız. İlke ayarları, uygulama tarafından bunlar için her denetim gerçekleştirildiğinde, genellikle ilk çalıştırıldığında kullanılır.

Birtakım dahil etme ve dışlama atamaları kullanarak kullanıcı ve cihaz gruplarına bir uygulama yapılandırma ilkesi atayabilirsiniz. Bir uygulama yapılandırma ilkesini ekledikten sonra bu uygulama yapılandırma ilkesi için atamaları ayarlayabilirsiniz. İlke için atamaları ayarladıktan sonra ilkenin uygulanacağı kullanıcı gruplarını dahil etme veya dışlamayı seçebilirsiniz. Bir veya daha fazla grubu dahil etmeyi seçtiğinizde, belirli grupları dahil etmeyi veya yerleşik grupları kullanmayı seçebilirsiniz. Yerleşik gruplar **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklindedir. 

>[!NOTE]
>Intune size kolaylık sağlamak adına konsolda önceden oluşturulmuş ve yerleşik iyileştirmeleri bulunan **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar. Tüm kullanıcı ve cihazları hedeflemek için kendi oluşturacağınız “Tüm kullanıcılar” veya “Tüm cihazlar” grupları yerine bu grupları kullanmanızı kesinlikle öneririz.

Uygulama yapılandırma ilkenize dahil edilen grupları seçtikten sonra, dışlamak üzere de belirli grupları seçebilirsiniz.

> [!TIP]
> Bu ilke türü şu anda yalnızca iOS 8.0 ve üzeri sistemleri çalıştıran cihazlar için kullanılabilir. Aşağıdaki uygulama yükleme türlerini destekler:
>
> -   **Uygulama mağazasından yönetilen iOS uygulaması**
> -   **iOS için uygulama paketi**
>
> Uygulama yükleme türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Uygulama yapılandırma ilkesi oluşturma

1. Azure portalında oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** + **Intune**’u seçin.
3. **Mobil uygulamalar** iş yükünü seçin.
4. **Yönet** grubunda bulunan **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad**<br>
      Azure portalında görünecek profil adı.
    - **Açıklama**<br>
      Azure portalında görünecek profil açıklaması.
    - **Cihaz kaydı türü**<br>
      **Yönetilen cihazlar**’ı seçin.
6. **Platform** için **iOS**’u seçin.
7.  **İlişkili Uygulama**’yı seçin. Daha sonra **İlişkili Uygulama** dikey penceresinde yapılandırmayı uygulamak istediğiniz yönetilen uygulamayı seçin.
8.  **Yapılandırma İlkesi Ekle** dikey penceresinde **Yapılandırma ayarları**’nı seçin.
9. **Yapılandırma ayarları biçimi**’ni seçin. Aşağıdakilerden birini seçin:
    - **[Yapılandırma tasarımcısını kullanma](#use-configuration-designer)**
    - **[XML Verilerini girme](#enter-xml-data)**
10. XML bilgilerinizi ekledikten sonra **Tamam**’ı seçin ve yapılandırma ilkesini eklemek üzere **Ekle**’yi seçin. Yapılandırma ilkesi için genel bakış dikey penceresi görüntülenir.
11. **Atamalar**’ı seçerek dahil etme ve dışlama seçeneklerini görüntüleyin. 

    ![İlke atamaları](./media/app-config-policy01.png)
12. **Dahil Et** sekmesinde **Tüm Kullanıcılar**’ı seçin.

    ![İlke Atamaları - Tüm Kullanıcılar](./media/app-config-policy02.png)
13. **Dışla** sekmesini seçin. 
14. İlgili dikey pencerede **Dışlanacak grupları seç**’e tıklayın.

    ![İlke atamaları - Dışlanacak grupları seç](./media/app-config-policy03.png)
15. Dışlamak istediğiniz grupları seçin ve **Seç**’e tıklayın.

    >[!NOTE]
    >Bir grup eklerken, herhangi bir atama türü için başka bir grup önceden dahil edilmişse bu grup, diğer dahil etme atama türleri için önceden seçili ve değiştirilemez bir biçimde görüntülenir. Dolayısıyla bu grup zaten kullanılmıştır ve dışlanmış bir grup olarak kullanılamaz.
16. **Kaydet**'e tıklayın.

## <a name="use-configuration-designer"></a>Yapılandırma tasarımcısı kullanma

Intune’a kaydedilen veya kaydedilmeyen cihazlardaki uygulamalar için yapılandırma tasarımcısını kullanabilirsiniz. Tasarımcı, belirli yapılandırma anahtarları ve değerleri yapılandırmanıza imkan tanır. Ayrıca her bir değer için veri türünü belirtmeniz gerekir. Uygulamalar yüklendiğinde ayarlar bunlara otomatik olarak sağlanır.

### <a name="add-a-setting"></a>Ayar ekle

1. Yapılandırmadaki her bir anahtar ve değer için şunları ayarlayın:
   - **Yapılandırma anahtarı**<br>
     Belirli ayar yapılandırmalarını benzersiz olarak tanımlayan anahtar.
   - **Değer türü**<br>
     Yapılandırma değerinin veri türü. Türler Tamsayı, Gerçek, Dize ve Boole değerlerini içerir.
   - **Yapılandırma değeri**<br>
     Yapılandırmanın değeri.
2. Yapılandırma ayarlarınızı yapmak için **Tamam**’a tıklayın.

### <a name="delete-a-setting"></a>Bir ayarı silme

1. Ayarların yanındaki üç nokta simgesini (**...**) seçin.
2. **Sil**’i seçin.

\{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.

## <a name="enter-xml-data"></a>XML verilerini girme

Intune’a kaydedilmiş cihazlar için uygulama yapılandırma ayarlarını içeren bir XML özellik listesi girebilir veya yapıştırabilirsiniz. XML özellik listesinin biçimi, yapılandırdığınız uygulamaya bağlı olarak değişir. Kullanılacak tam biçim hakkında ayrıntılı bilgi için uygulamanın sağlayıcısına başvurun.

Intune XML biçimini doğrular. Ancak Intune, XML özellik listesinin (PList) hedef uygulama ile çalışıp çalışmayacağını denetlemez.

XML özellik listeleri hakkında daha fazla bilgi edinmek için:

  -  [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)’yı okuyun.
  -  iOS Geliştirici Kitaplığı’nda [XML Özellik Listelerini anlama](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) konusuna bakın.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Uygulama yapılandırma XML dosyası için örnek biçim

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
### <a name="supported-xml-plist-data-types"></a>Desteklenen XML PList veri türleri

Intune, bir özellik listesinde aşağıdaki veri türlerini destekler:

- &lt;tamsayı&gt;
- &lt;gerçek&gt;
- &lt;dize&gt;
- &lt;dizi&gt;
- &lt;sözlük&gt;
- &lt;true /&gt; veya &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Özellik listesinde kullanılan belirteçler

Ayrıca, Intune özellik listesinde aşağıdaki belirteç türlerini destekler:
- \{\{userprincipalname\}\}—örneğin, **John@contoso.com**
- \{\{mail\}\}—örneğin, **John@contoso.com**
- \{\{partialupn\}\}—örneğin, **John**
- \{\{accountid\}\}—örneğin, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}—örneğin, **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}—örneğin, **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}—örneğin, **John Doe**
- \{\{serialnumber\}\}—örneğin, **F4KN99ZUG5V2** (iOS cihazlar için)
- \{\{serialnumberlast4digits\}\}—örneğin, **G5V2** (iOS cihazlar için)

## <a name="next-steps"></a>Sonraki adımlar

Normal yollarla, uygulamayı [atama](apps-deploy.md) ve [izleme](apps-monitor.md) işlemlerine devam edin.