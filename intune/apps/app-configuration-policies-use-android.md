---
title: Yönetilen Android Kurumsal cihazları için uygulama yapılandırma ilkeleri ekleme
titleSuffix: Microsoft Intune
description: Kullanıcılar yönetilen bir Google Play uygulamasını çalıştırdığınızda ayarları sağlamak için Microsoft Intune 'de uygulama yapılandırma ilkeleri kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d31126a259274a2c75f933428632e274d8710aa6
ms.sourcegitcommit: b8127c7a62d9ac4d0f768980fa1424567bb58733
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72350021"
---
# <a name="add-app-configuration-policies-for-managed-android-enterprise-devices"></a>Yönetilen Android Kurumsal cihazları için uygulama yapılandırma ilkeleri ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune içindeki uygulama yapılandırma ilkeleri, yönetilen Android kurumsal cihazlarda yönetilen Google Play uygulamalar için ayarları sağlar. Uygulama geliştiricisi, Android tarafından yönetilen uygulama yapılandırma ayarlarını gösterir. Intune, yöneticinin uygulama için özellikleri yapılandırmasına izin vermek için bu sunulan ayarı kullanır. Uygulama yapılandırma ilkesi Kullanıcı gruplarınıza atanır. İlke ayarları, uygulama tarafından, genellikle uygulama ilk kez çalıştırıldığında kullanılır.

> [!NOTE]  
> Tüm uygulamalar, uygulama yapılandırmasını desteklemez. Uygulamanın uygulama yapılandırma ilkelerini destekleyip desteklemediğini görmek için uygulama geliştiricisine danışın.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'Da, **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** >  **Ekle**' yi seçin.
2. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir ilke adı **tüm şirket Için Android kurumsal dokuz iş uygulaması ilkesidir**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Cihaz kayıt türü**: **yönetilen cihazlar**' ı seçin.
    - **Platform**: **Android**' i seçin.

3. **Ilişkili uygulama**' yı seçin. Bir uygulama yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçin. Onaylanan ve Intune ile eşitlenen yönetilen Google Play uygulamalar listesinden seçim yapın.
4. **İzinler**’i seçin. Yapılandırmaları ayarlamak için şunları kullanabilirsiniz:

    - [Yapılandırma tasarımcısı](#use-the-configuration-designer)
    - [JSON düzenleyicisi](#enter-the-json-editor)

5. **Tamam** > **Ekle**' yi seçin.

## <a name="use-the-configuration-designer"></a>Yapılandırma tasarımcısını kullanma

Uygulama yapılandırma ayarlarını destekleyecek şekilde tasarlandıysa, yönetilen Google Play uygulamalar için yapılandırma tasarımcısını kullanabilirsiniz. Yapılandırma, Intune 'a kayıtlı cihazlar için geçerlidir. Tasarımcı, uygulama tarafından sunulan ayarlar için belirli yapılandırma değerlerini yapılandırmanızı sağlar.

1. **Ekle**’yi seçin. Uygulama için girmek istediğiniz yapılandırma ayarları listesini seçin.

    E-posta uygulamanız için GMail veya dokuz Iş kullanıyorsanız, bu ayarlarla ilgili daha fazla bilgi için [e-postayı yapılandırmak üzere Android kurumsal cihaz ayarları](../email-settings-android-enterprise.md) ' na bakın.

2. Yapılandırmadaki her bir anahtar ve değer için şunları ayarlayın:

    - **Değer türü**: yapılandırma değerinin veri türü. Dize değer türleri için isteğe bağlı olarak bir değişken veya sertifika profili seçebilirsiniz.
    - **Yapılandırma değeri**: yapılandırmanın değeri. **Değer türü**için değişken veya sertifika ' yı seçerseniz, bir değişken veya sertifika profili listesinden öğesini seçin. Bir sertifika seçerseniz, cihaza dağıtılan sertifikanın sertifika diğer adı çalışma zamanında doldurulur.

### <a name="supported-variables-for-configuration-values"></a>Yapılandırma değerleri için desteklenen değişkenler

Yapılandırma değeri olarak değişken seçerseniz şunlar arasından seçim yapabilirsiniz:

| Seçenek | Örnek |
|----|----|
| Mail | john@contoso.com |
| Kullanıcı asıl adı | john@contoso.com |
| Kısmi UPN | john |
| Etki Alanı | Contoso.com |
| Kullanıcı adı | John Doe |
| Hesap kimliği | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| Kullanıcı KIMLIĞI | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Cihaz Kimliği | b9841cd9-9843-405f-be28-b2265c59ef97 |

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Çok kimlikli uygulamalarda yalnızca yapılandırılmış kuruluş hesaplarına izin verme 

Android cihazlarda aşağıdaki anahtar/değer çiftlerini kullanın:

| **Anahtar** | com.microsoft.intune.mam.AllowedAccountUPNs |
|---|---|
| **Deðerler** | <ul><li>Bir veya daha fazla <code>;</code> ile sınırlandırılmış UPN.</li><li>Yalnızca bu anahtar ile tanımlanan yönetilen kullanıcı hesaplarına izin verilir.</li><li> Intune'a kayıtlı cihazlar için <code>{{userprincipalname}}</code> belirteci kayıtlı kullanıcı hesabını temsil etmek için kullanılabilir.</li></ul> |

   > [!NOTE]
   > Yalnızca birden çok kimliği olan yapılandırılmış kuruluş hesaplarına izin verirken Android 2.2.222 ve üzeri, Word, Excel, Android 16.0.9327.1000 ve üzeri ya da OneDrive for Android 5,28 ve üzeri için Outlook 'U kullanmanız gerekir.<p></p>
   > Microsoft Intune Yöneticisi olarak, yönetilen cihazlarda Microsoft Office uygulamalarına hangi kullanıcı hesaplarının ekleneceğini denetleyebilirsiniz. Erişimi yalnızca izin verilen kullanıcı hesaplarıyla sınırlayabilecek ve kayıtlı cihazlarda kişisel hesapları engelleyebilirsiniz. Destekleyen uygulamalar, uygulama yapılandırmasını işler ve onaylanmamış hesapları kaldırıp engeller.<p></p>

## <a name="enter-the-json-editor"></a>JSON düzenleyicisini girme

Uygulamalarda bazı yapılandırma ayarları (örneğin, paket türlerine sahip uygulamalar) yapılandırma Tasarımcısı ile yapılandırılamaz. Bu değerler için JSON düzenleyicisini kullanın. Uygulama yüklendiğinde ayarlar uygulamalara otomatik olarak sağlanır.

1. **Yapılandırma ayarları biçimi** için **JSON düzenleyicisine gir**’i seçin.
2. Düzenleyicide, yapılandırma ayarları için JSON değerlerini tanımlayabilirsiniz. Örnek bir dosya indirip ardından yapılandırmak için **JSON şablonu indir**’i seçebilirsiniz.
3. **Tamam**’ı ve daha sonra **Ekle**’yi seçin.

İlke oluşturulur ve listede gösterilir.

Atanan uygulama bir cihazda çalıştırıldığında, uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Uygulamalar için izin verme durumunu önceden yapılandırma

Ayrıca, Android cihaz özelliklerine erişmek için uygulama izinlerini önceden yapılandırabilirsiniz. Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinleri gerektiren Android Uygulamaları, kullanıcılardan izinleri kabul etmesini veya reddetmesini ister.

Örneğin, bir uygulama cihazın mikrofonunu kullanır. Kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'Da, **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** >  **Ekle**' yi seçin.
2. Aşağıdaki özellikleri girin:

    - **Ad**: ilke için açıklayıcı bir ad girin. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir ilke adı, **tüm şirket Için Android kurumsal istem izinleri uygulama ilkesidir**.
    - **Açıklama**. Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Cihaz kayıt türü**: **yönetilen cihazlar**' ı seçin.
    - **Platform**: **Android**' i seçin.

3. **Ilişkili uygulama**' yı seçin. Yapılandırma ilkesi tanımlamak istediğiniz uygulamayı seçin. Onaylanan ve Intune ile eşitlenen Android iş profili uygulamaları listesinden seçim yapın.
4. @No__t **izinleri**seçin-1**Ekle**. Listeden, kullanılabilir uygulama izinlerini seçin > **Tamam**' ı seçin.
5. Bu ilkeyle verilecek her izin için bir seçenek belirleyin:
    - **Sor**. Kullanıcıdan kabul etmesini veya reddetmesini isteme.
    - **Otomatik olarak izin ver**. Kullanıcıya bildirmeden otomatik olarak onayla.
    - **Otomatik olarak reddet**. Kullanıcıya bildirmeden otomatik olarak reddet.
6. Uygulama yapılandırma ilkesini atamak için uygulama yapılandırma ilkesi > **atama** > **Grup Seç**' i seçin. Atanacak Kullanıcı gruplarını seçin > **seçin**.
7. İlkeyi atamak için **Kaydet**’i seçin.

## <a name="additional-information"></a>Ek bilgiler

- [Android kurumsal cihazlara yönetilen Google Play uygulaması atama](apps-add-android-for-work.md#assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices)
- [İOS ve Android uygulama yapılandırma ayarları için Outlook dağıtımı](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune)

## <a name="next-steps"></a>Sonraki adımlar

Uygulamayı [atamaya](apps-deploy.md) ve [izlemeye](apps-monitor.md) devam edin.
