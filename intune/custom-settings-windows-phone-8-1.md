---
title: Microsoft Intune - Azure’da Windows Phone 8.1 cihazlara özel ayarlar ekleme | Microsoft Docs
titleSuffix: ''
description: Microsoft Intune’da Windows Phone 8.1 çalıştıran cihazlar için OMA-URI ayarlarını kullanmak üzere özel bir profil ekleyin veya oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 487115938ad334d1cefb2a6ecfc8d64ac6688a45
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565902"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Intune’da Windows Phone 8.1 cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, “özel profiller” kullanan Windows Phone 8.1 cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Windows Phone 8.1 özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak farklı özellikleri yapılandırır. Bu ayarlar normalde mobil cihaz üreticileri tarafından cihazdaki özellikleri denetlemek için kullanılır.

Bu makale, Windows Phone 8.1 cihazlar için özel profil oluşturma işlemini gösterir. 

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için bir ad girmeniz `windows phone custom profile`.
    - **Açıklama**: Profil için bir açıklama girin.
    - **Platform**: Seçin **Windows Phone 8.1**.
    - **Profil türü**: Seçin **özel**.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.
    - **Açıklama**: Ayar ve diğer ilgili bilgileri profili bulmanıza yardımcı olmak için genel bakışını veren bir açıklama girin.
    - **OMA-URI** (büyük/küçük harfe duyarlı): Bir ayarı olarak kullanmak istediğiniz OMA-URI'yi girin.
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

[Windows 10 cihazlarda](custom-settings-windows-10.md) bir özel profili nasıl oluşturacağınızı görün.
