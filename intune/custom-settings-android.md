---
title: Microsoft Intune - Azure’da Android cihazlara özel ayarlar ekleme | Microsoft Docs
description: Microsoft Intune'da önceden paylaşılmış bir anahtarla WiFi profili oluşturmak, uygulama başına VPN profili oluşturmak veya Samsung Knox Standard cihazlarında uygulamalara izin vermek/engellemek için, Android cihazlarına bir özel profil ekleyin veya oluşturun
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e4f94ead5ecc42f8ac67c596fc9424b112c2065
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048598"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, bir “özel profil” kullanan Android cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Android özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak Android cihazlardaki farklı özellikleri yapılandırır. Bu ayarlar normalde mobil cihaz üreticileri tarafından bu özellikleri denetlemek için kullanılır.

Özel profil kullanarak, aşağıdaki Android ayarlarını yapılandırabilir ve atayabilirsiniz. Aşağıdaki ayarlar Intune’da yerleşik olarak bulunmaz:

- [Önceden paylaşılan anahtar ile Wi-Fi profili oluşturma](/intune/wi-fi-profile-shared-key)
- [Uygulama başına VPN profili oluşturma](/intune/android-pulse-secure-per-app-vpn)
- [Samsung Knox Standard cihazlarında uygulamalara izin verme veya bunları engelleme](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Yalnızca listelenen ayarlar bir özel profil tarafından yapılandırılabilir. Android cihazları, yapılandırabileceğiniz OMA-URI ayarlarının tam bir listesini sunmaz. Diğer ayarları görmek istiyorsanız, [Intune Uservoice sitesinde](https://microsoftintune.uservoice.com/forums/291681-ideas) diğer ayarlar için oy verin.

Bu makale, Android cihazlar için özel profil oluşturma işlemini gösterir.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için bir ad girmeniz `android custom profile`.
    - **Açıklama**: Profil için açıklama girin.
    - **Platform**: Seçin **Android**.
    - **Profil türü**: Seçin **özel**.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Sizi kolayca bulabilmesi için OMA-URI ayarı için benzersiz bir ad girin.
    - **Açıklama**: Ayar ve diğer önemli ayrıntıları genel bakışını veren bir açıklama girin.
    - **OMA-URI**: Bir ayarı olarak kullanmak istediğiniz OMA-URI'yi girin.
    - **Veri türü**: Bu OMA-URI ayarı için kullanacağınız veri türünü seçin. Seçenekleriniz şunlardır:

      - Dize
      - Dize (XML dosyası)
      - Tarih ve saat
      - Tamsayı
      - Kayan nokta
      - Boole
      - Base64 (dosya)

    - **Değer**: Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz veri değeri girin. Değer, seçtiğiniz veri türüne bağlıdır. Örneğin **Tarih ve saat**’i seçtiğinizde, değeri tarih seçiciden belirleyin.

    Bazı ayarları ekledikten sonra **Dışarı Aktar**’ı seçebilirsiniz. **Dışarı Aktar**, virgülle ayrılmış değerler (.csv) dosyasına eklediğiniz tüm değerlerin listesini oluşturur.

5. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Gerekirse diğer ayarları eklemeye devam edin. 
6. İşiniz bittiğinde, Intune profilini oluşturmak için **Tamam** > **Oluştur**’u seçin. Profiliniz oluşturulduğunda **Cihaz yapılandırması - Profiller** listesinde görünür.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

Bkz. [Android Kurumsal cihazlarda profil oluşturma](custom-settings-android-for-work.md).
