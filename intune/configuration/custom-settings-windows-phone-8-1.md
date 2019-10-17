---
title: Microsoft Intune - Azure’da Windows Phone 8.1 cihazlara özel ayarlar ekleme | Microsoft Docs
titleSuffix: ''
description: Microsoft Intune’da Windows Phone 8.1 çalıştıran cihazlar için OMA-URI ayarlarını kullanmak üzere özel bir profil ekleyin veya oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a1362f6c6453569d1c306cd16397cc9a7f83736e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72495337"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Intune’da Windows Phone 8.1 cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, “özel profiller” kullanan Windows Phone 8.1 cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Windows Phone 8.1 özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak farklı özellikleri yapılandırır. Bu ayarlar normalde mobil cihaz üreticileri tarafından cihazdaki özellikleri denetlemek için kullanılır. [Windows Phone 8,1 MDM Protokolü belgeleri](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-phone/dn499787(v=technet.10)) ayarları listeler.

Bu makale, Windows Phone 8.1 cihazlar için özel profil oluşturma işlemini gösterir. 

## <a name="create-the-profile"></a>Profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için `windows phone custom profile` gibi bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin.
    - **Platform**: **Windows Phone 8.1**’i seçin.
    - **Profil türü**: **Özel**’i seçin.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve profili bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama girin.
    - **OMA-URI**  (büyük/küçük harfe duyarlı): Ayar olarak kullanmak istediğiniz OMA-URI’yi girin.
    - **Veri türü**: Bu OMA-URI ayarı için kullanacağınız veri türünü girin. Seçenekleriniz şunlardır:

        - Dize
        - Dize (XML dosyası)
        - Tarih ve saat
        - Tamsayı
        - Kayan nokta
        - Boole değeri
        - Base64 (dosya)

    - **Değer**: Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz veri değerini girin. Değer, seçtiğiniz veri türüne bağlıdır. Örneğin **Tarih ve saat**’i seçtiğinizde, değeri tarih seçiciden belirleyin.

    Bazı ayarları ekledikten sonra **Dışarı Aktar**’ı seçebilirsiniz. **Dışarı Aktar**, virgülle ayrılmış değerler (.csv) dosyasına eklediğiniz tüm değerlerin listesini oluşturur.

5. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Gerekirse diğer ayarları eklemeye devam edin.
6. İşiniz bittiğinde, Intune profilini oluşturmak için **Tamam** > **Oluştur**’u seçin. Profiliniz oluşturulduğunda **Cihaz yapılandırması - Profiller** listesinde görünür.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, Windows 8.1 telefon cihazlarının taşıyıcı kapsam alanı dışında seyahat edildiğinde hücresel ağları değiştirmesi engellenir.

- **Ad**: hücresel veri dolaşımına izin ver
- **Açıklama**: hücresel veri dolaşımına izin ver veya izin verme
- **OMA-URI** (büyük/küçük harfe duyarlı):./Vendor/MSFT/PolicyManager/My/connectivity/AllowCellularDataRoaming
- **Veri türü**: tamsayı
- **Değer**: 0

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

[Windows 10 cihazlarda](../custom-settings-windows-10.md) bir özel profili nasıl oluşturacağınızı görün.
