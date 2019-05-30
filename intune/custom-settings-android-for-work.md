---
title: Microsoft Intune - Azure’da Android Kurumsal cihazlara özel ayarlar ekleme | Microsoft Docs
description: Microsoft Intune’da Android Kurumsal cihazlara bir özel profil ekleme veya oluşturma
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b5f1b4c0fd0c9d8cfdc443b2af3c6f90a6f32756
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373632"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Microsoft Intune’da Android Kurumsal cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, bir “özel profil” kullanan Android Kurumsal cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Android Kurumsal özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak Android Kurumsal cihazlardaki özellikleri denetler. Bu ayarlar normalde mobil cihaz üreticileri tarafından bu özellikleri denetlemek için kullanılır.

Intune, sınırlı sayıda Android özel profilini destekler.

Bu makale, Android Kurumsal cihazlar için özel profil oluşturma işlemini gösterir. Ayrıca kopyalama ve yapıştırmayı engelleyen bir özel profil örneği sağlar.

## <a name="create-the-profile"></a>Profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için bir ad girin `android enterprise custom profile`
    - **Açıklama**: Profil için bir açıklama girin
    - **Platform**: Seçin **Android Kurumsal**
    - **Profil türü**: Seçin **özel**

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

## <a name="example"></a>Örnek

Bu örnekte, Android Kurumsal cihazlarda iş uygulamaları ve kişisel uygulamalar arasında kopyalama ve yapıştırma eylemlerini kısıtlayan bir özel profil oluşturacaksınız.

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için bir ad girmeniz `android ent block copy paste custom profile`.
    - **Açıklama**: Profil için açıklama girin.
    - **Platform**: Seçin **Android Kurumsal**.
    - **Profil türü**: Seçin **özel**.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Aşağıdaki gibi girin `Block copy and paste`.
    - **Açıklama**: Aşağıdaki gibi girin `Blocks copy/paste between work and personal apps`.
    - **OMA-URI**: Girin `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste`.
    - **Veri türü**: Seçin **Boole** bu OMA-URI değeri, bu nedenle **True** veya **False**.
    - **Değer**: Seçin **True**.

5. Ayarları girdikten sonra ortamınız, aşağıdakine benzer bir şekilde görünecektir:

    ![Android iş profili için kopyalama ve yapıştırmayı engelleyin.](./media/custom-policy-afw-copy-paste.png)

Bu profili yönettiğiniz Android Kurumsal cihazlara atadığınızda, kopyalama ve yapıştırma eylemleri iş uygulamaları ve kişisel profiller arasında engellenir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

Bkz. [Android cihazlarda profil oluşturma](custom-settings-android.md).
