---
title: Microsoft Intune - Azure’da Android Kurumsal cihazlara özel ayarlar ekleme | Microsoft Docs
description: Microsoft Intune’da Android Kurumsal cihazlara bir özel profil ekleme veya oluşturma
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 73075ed06e98ca987e87a7cfda70c546127bf881
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179601"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Microsoft Intune’da Android Kurumsal cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, bir “özel profil” kullanan Android Kurumsal cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Android Kurumsal özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak Android Kurumsal cihazlardaki özellikleri denetler. Bu ayarlar normalde mobil cihaz üreticileri tarafından bu özellikleri denetlemek için kullanılır.

Intune, sınırlı sayıda Android özel profilini destekler.

Bu makale, Android Kurumsal cihazlar için özel profil oluşturma işlemini gösterir. Ayrıca kopyalama ve yapıştırmayı engelleyen bir özel profil örneği sağlar.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için `android enterprise custom profile` gibi bir ad girin
    - **Açıklama**: Profil için bir açıklama girin
    - **Platform**: **Android Kurumsal**’ı seçin
    - **Profil Türü**: **Özel**’i seçin

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Kolayca bulabilmek için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve diğer önemli ayrıntıları veren bir açıklama girin.
    - **OMA-URI**: Ayar olarak kullanmak istediğiniz OMA-URI’yi girin.
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

Bu örnekte, Android Kurumsal cihazlarda iş uygulamaları ve kişisel uygulamalar arasında kopyalama ve yapıştırma eylemlerini kısıtlayan bir özel profil oluşturacaksınız.

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için `android ent block copy paste custom profile` gibi bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin.
    - **Platform**: **Android Kurumsal**’ı seçin.
    - **Profil türü**: **Özel**’i seçin.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: `Block copy and paste` gibi bir ad girin.
    - **Açıklama**: `Blocks copy/paste between work and personal apps` gibi bir açıklama girin.
    - **OMA-URI**: `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste` girin.
    - **Veri türü**: Bu OMA-URI değerinin **True** veya **False** olması için **Boole** seçeneğini belirleyin.
    - **Değer**: **True** seçeneğini belirleyin.

5. Ayarları girdikten sonra ortamınız, aşağıdakine benzer bir şekilde görünecektir:

    ![Android iş profili için kopyalama ve yapıştırmayı engelleyin.](./media/custom-policy-afw-copy-paste.png)

Bu profili yönettiğiniz Android Kurumsal cihazlara atadığınızda, kopyalama ve yapıştırma eylemleri iş uygulamaları ve kişisel profiller arasında engellenir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

Bkz. [Android cihazlarda profil oluşturma](custom-settings-android.md).