---
title: Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme
titlesuffix: Microsoft Intune
description: iOS uygulaması çalıştırıldığında uygulamaya yapılandırma verilerini sağlamak için uygulama yapılandırma ilkelerini kullanmayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/12/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ac095eadbca5702ce3ff73e9e5ce1c77fac71eb3
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57400101"
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir iOS uygulamasına özel yapılandırma ayarları sağlamak için Microsoft Intune’daki uygulama yapılandırma ilkelerini kullanın. Bu yapılandırma ayarları, uygulamanın sağlayıcı yönünde özelleştirilebilmesini sağlar. Bu yapılandırma ayarlarını (anahtarlar ve değerleri) uygulama sağlayıcısından almanız gerekir. Uygulamayı yapılandırmak için ayarları, anahtarlar ve değerler olarak veya anahtarlar ve değerler içeren bir XML olarak belirtin. Ayrıca bu yapılandırma ilkelerini kullanıcılara ve cihazlara doğrudan atamayın. Bunun yerine, yapılandırma ilkesini bir uygulamayla ilişkilendirin ve bu uygulamayı atayın. Yapılandırma ilkesi ayarları, uygulama tarafından denetim gerçekleştirildiğinde, genellikle de uygulama ilk defa çalıştırıldığında kullanılır.

Bir uygulama yapılandırma ilkesini ekledikten sonra bu uygulama yapılandırma ilkesi için atamaları ayarlayabilirsiniz. İlke için atamaları ayarladıktan sonra ilkenin uygulandığı kullanıcı gruplarını dahil etmeyi veya dışlamayı seçebilirsiniz. Bir veya daha fazla grubu dahil etmeyi seçtiğinizde, belirli grupları dahil etmeyi veya yerleşik grupları kullanmayı seçebilirsiniz. Yerleşik gruplar **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklindedir. 

>[!NOTE]
>Intune size kolaylık sağlamak adına konsolda önceden oluşturulmuş ve yerleşik iyileştirmeleri bulunan **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarını sağlar. Tüm kullanıcı ve cihazları hedeflemek için kendi oluşturacağınız “Tüm kullanıcılar” veya “Tüm cihazlar” grupları yerine bu grupları kullanmanızı kesinlikle öneririz.<p></p>
>Microsoft Intune yöneticisi olarak yönetilen cihazlarda hangi kullanıcı hesaplarının Microsoft Office uygulamalarına eklendiğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. Destekleyen uygulamalar, uygulama yapılandırmasını işler ve onaylanmamış hesapları kaldırıp engeller.

Uygulama yapılandırma ilkenize dahil edilen grupları seçtikten sonra, dışlamak üzere de belirli grupları seçebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).

> [!TIP]
> Bu ilke türü şu anda yalnızca iOS 8.0 ve üzeri sistemleri çalıştıran cihazlar için kullanılabilir. Aşağıdaki uygulama yükleme türlerini destekler:
>
> -   **Uygulama mağazasından yönetilen iOS uygulaması**
> -   **iOS için uygulama paketi**
>
> Uygulama yükleme türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Uygulama yapılandırma ilkesi oluşturma

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **İstemci uygulamaları** iş yükünü seçin.
4. **Yönet** grubunda bulunan **Uygulama yapılandırma ilkeleri**’ni seçip **Ekle**’ye tıklayın.
5. Aşağıdaki bilgileri ayarlayın:
    - **Ad** - Azure portalında görünen profil adı.
    - **Açıklama** - Azure portalında görünen profil açıklaması.
    - **Cihaz kayıt türü** - **Yönetilen uygulamalar**’ı seçin.
6. **Platform** için **iOS**’u seçin.
7.  **İlişkili uygulama**’yı seçin. Daha sonra **İlişkili uygulama** bölmesinde yapılandırmayı uygulamak istediğiniz yönetilen uygulamayı ve ardından **Tamam**’ı seçin.
8.  **Yapılandırma ilkesi ekle** bölmesinde **Yapılandırma ayarları**’nı seçin.
9. **Yapılandırma ayarları biçimi**’ni seçin. XML bilgileri eklemek için aşağıdakilerden birini seçin:
    - **Yapılandırma tasarımcısını kullanma**
    - **XML verileri girme**<br><br>
    Yapılandırma tasarımcısını kullanma hakkında ayrıntılar için bkz. [Yapılandırma tasarımcısını kullanma](#use-configuration-designer). XML verileri girme hakkında ayrıntılar için bkz. [XML verileri girme](#enter-xml-data). 
10. XML bilgilerinizi ekledikten sonra **Tamam**’ı seçin ve yapılandırma ilkesini eklemek üzere **Ekle**’yi seçin. Yapılandırma ilkesi için genel bakış bölmesi görüntülenir.
11. **Atamalar**’ı seçerek dahil etme ve dışlama seçeneklerini görüntüleyin. 

    ![İlke atamaları Ekle sekmesinin ekran görüntüsü](./media/app-config-policy01.png)
12. **Dahil Et** sekmesinde **Tüm Kullanıcılar**’ı seçin.

    ![İlke atamaları - Tüm Kullanıcılar açılan seçeneğinin ekran görüntüsü](./media/app-config-policy02.png)
13. **Dışla** sekmesini seçin. 
14. İlgili bölmeyi görüntülemek için **Dışlanacak grupları seçin**’e tıklayın.

    ![İlke atamaları - Dışlanacak grupları seçin dikey penceresinin ekran görüntüsü](./media/app-config-policy03.png)
15. Dışlamak istediğiniz grupları seçin ve **Seç**’e tıklayın.

    >[!NOTE]
    >Bir grup eklerken, herhangi bir atama türü için başka bir grup önceden dahil edilmişse bu grup, diğer dahil etme atama türleri için önceden seçili ve değiştirilemez bir biçimde görüntülenir. Dolayısıyla bu grup zaten kullanılmıştır ve dışlanmış bir grup olarak kullanılamaz.
16. **Kaydet**’e tıklayın.

## <a name="use-configuration-designer"></a>Yapılandırma tasarımcısı kullanma

Microsoft Intune, bir uygulamaya özgü yapılandırma ayarları sağlar. Microsoft Intune’a kaydedilen veya kaydedilmeyen cihazlardaki uygulamalar için yapılandırma tasarımcısını kullanabilirsiniz. Tasarımcı, temel alınan XML dilini oluşturmanıza yardımcı olan belirli yapılandırma anahtarları ve değerlerini yapılandırmanıza imkan tanır. Ayrıca her bir değer için veri türünü belirtmeniz gerekir. Uygulamalar yüklendiğinde bu ayarlar uygulamalara otomatik olarak sağlanır.

### <a name="add-a-setting"></a>Ayar Ekle

1. Yapılandırmadaki her bir anahtar ve değer için şunları ayarlayın:
   - **Yapılandırma anahtarı** - Belirli ayar yapılandırmalarını benzersiz olarak tanımlayan anahtar.
   - **Veri türü** - Yapılandırma değerinin veri türü. Türler Tamsayı, Gerçek, Dize ve Boole değerlerini içerir.
   - **Yapılandırma değeri** - Yapılandırmanın değeri.
2. Yapılandırma ayarlarınızı yapmak için **Tamam**’a tıklayın.

### <a name="delete-a-setting"></a>Bir ayarı silme

1. Ayarların yanındaki üç nokta simgesini (**...**) seçin.
2. **Sil**’i seçin.

\{\{ ve \}\} karakterleri yalnızca belirteç türleri tarafından kullanılır ve başka bir amaçla kullanılmamalıdır.

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Çok kimlikli uygulamalarda yalnızca yapılandırılmış kuruluş hesaplarına izin verme 

İOS cihazları için aşağıdaki anahtar/değer çiftleri kullanın:

| **Anahtar** | IntuneMAMAllowedAccountsOnly |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Değerler** | <ul><li>**Etkin**: İzin verilen tek hesap tarafından tanımlanan yönetilen kullanıcı hesabıdır [Intunemamupn](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm) anahtarı.</li><li>**Devre dışı bırakılmış** (veya büyük küçük harfe duyarlı bir eşleşme değil herhangi bir değer **etkin**): Herhangi bir hesaba izin verilir.</li></ul> |.

   > [!NOTE]
   > İOS 10.34 veya üzeri OneDrive ve Outlook 2.99.0 iOS için kullanmanız gerekir ya da daha sonra ve uygulama ile hedeflenmelidir [Intune uygulama koruma ilkeleri](app-protection-policy.md) ne zaman izin vererek yalnızca yapılandırılan kuruluş hesapları ile birden çok kimliği.

## <a name="enter-xml-data"></a>XML verilerini girme

Intune’a kaydedilmiş cihazlar için uygulama yapılandırma ayarlarını içeren bir XML özellik listesi girebilir veya yapıştırabilirsiniz. XML özellik listesinin biçimi, yapılandırdığınız uygulamaya bağlı olarak değişir. Kullanılacak tam biçim hakkında ayrıntılı bilgi için uygulamanın sağlayıcısına başvurun.

Intune XML biçimini doğrular. Ancak Intune, XML özellik listesinin (PList) hedef uygulama ile çalışıp çalışmayacağını denetlemez.

XML özellik listeleri hakkında daha fazla bilgi edinmek için:

  -  iOS Geliştirici Kitaplığı’nda [XML Özellik Listelerini anlama](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) konusuna bakın.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Uygulama yapılandırma XML dosyası için örnek biçim

Uygulama yapılandırma dosyasını oluşturduğunuzda, bu biçimi kullanarak aşağıdaki değerlerden birini veya daha fazlasını belirtebilirsiniz:

```xml
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
  <key>aaddeviceid</key>
  <string>{{aaddeviceid}}</string>
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
- \{\{aaddeviceid\}\}—örneğin **ab0dc123-45d6-7e89-aabb-cde0a1234b56**

## <a name="monitor-ios--app-configuration-status-per-device"></a>Cihaz başına iOS uygulama yapılandırma durumunu izleme 
Yapılandırma ilkesi atandıktan sonra, yönetilen her cihaz için iOS uygulama yapılandırma durumunu izleyebilirsiniz. Azure portalında **Microsoft Intune**'dan **Cihazlar** > **Tüm cihazlar**'ı seçin. Yönetilen cihaz listesinden belirli bir cihazı seçerek o cihazın dikey penceresini görüntüleyin. Cihaz dikey penceresinde **Uygulama yapılandırması**'nı seçin.  

## <a name="next-steps"></a>Sonraki adımlar

Uygulamayı [atamaya](apps-deploy.md) ve [izlemeye](apps-monitor.md) devam edin.
