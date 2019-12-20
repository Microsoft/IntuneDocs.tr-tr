---
title: Microsoft Intune - Azure’da Android Kurumsal cihazlara özel ayarlar ekleme | Microsoft Docs
description: Microsoft Intune’da Android Kurumsal cihazlara bir özel profil ekleme veya oluşturma
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1bd6e2d5ceebd23e87f464d15376594d1764c5b8
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206814"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Microsoft Intune’da Android Kurumsal cihazlar için özel ayarlar kullanma

Microsoft Intune kullanarak, "özel profil" kullanarak Android kurumsal Iş profili cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Android Kurumsal özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak Android Kurumsal cihazlardaki özellikleri denetler. Bu ayarlar normalde mobil cihaz üreticileri tarafından bu özellikleri denetlemek için kullanılır.

Intune, aşağıdaki sınırlı sayıda Android kurumsal özel profili destekler:

- ./Vendor/MSFT/WiFi/Profile/SSID/Settings: [önceden paylaşılan anahtarla bir Wi-Fi profili oluşturma](wi-fi-profile-shared-key.md) bazı örneklere sahiptir.
- ./Vendor/MSFT/VPN/Profile/Name/PackageList: [uygulama BAŞıNA VPN profili oluşturma](android-pulse-secure-per-app-vpn.md) bazı örneklere sahiptir.
- ./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste: Bu makaledeki [örneğe](#example) bakın. Bu ayar Kullanıcı arabiriminde da kullanılabilir. Daha fazla bilgi için bkz. [özelliklere izin vermek veya erişimi kısıtlamak Için Android kurumsal cihaz ayarları](device-restrictions-android-for-work.md).

Ek ayarlara ihtiyacınız varsa bkz. [Android Için Oemconfig Enterprise](android-oem-configuration-overview.md).

Bu makale, Android Kurumsal cihazlar için özel profil oluşturma işlemini gösterir. Ayrıca kopyalama ve yapıştırmayı engelleyen bir özel profil örneği sağlar.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı, **Android kurumsal özel profilidir**.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Android kurumsal**' i seçin.
    - **Profil türü**: **özel**' i seçin.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Kolayca bulabilmek için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve diğer önemli ayrıntıları veren bir açıklama girin.
    - **OMA-URI**: Ayar olarak kullanmak istediğiniz OMA-URI’yi girin.
    - **Veri türü**: Bu OMA-URI ayarı için kullanacağınız veri türünü seçin. Seçenekleriniz şunlardır:

      - Dize
      - Dize (XML dosyası)
      - Tarih ve saat
      - Tamsayı
      - Kayan nokta
      - Boole değeri
      - Base64 (dosya)

    - **Değer**: Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz veri değerini girin. Değer, seçtiğiniz veri türüne bağlıdır. Örneğin, **Tarih ve saat**' i seçerseniz, bir tarih seçicisinden değeri seçin.

    Bazı ayarları ekledikten sonra **Dışarı Aktar**’ı seçebilirsiniz. **Dışarı Aktar**, virgülle ayrılmış değerler (.csv) dosyasına eklediğiniz tüm değerlerin listesini oluşturur.

5. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Gerekirse diğer ayarları eklemeye devam edin.
6. İşiniz bittiğinde, Intune profilini oluşturmak için **tamam** > **Oluştur** ' u seçin. Bu tamamlandığında, profiliniz **cihazlar-yapılandırma profilleri** listesinde gösterilir.

## <a name="example"></a>Örnek

Bu örnekte, Android Kurumsal cihazlarda iş uygulamaları ve kişisel uygulamalar arasında kopyalama ve yapıştırma eylemlerini kısıtlayan bir özel profil oluşturacaksınız.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, **Android ENT blok kopyalama özel profil Yapıştır**' ı girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: **Android kurumsal**' i seçin.
    - **Profil türü**: **özel**' i seçin.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: `Block copy and paste` gibi bir ad girin.
    - **Açıklama**: `Blocks copy/paste between work and personal apps` gibi bir açıklama girin.
    - **OMA-URI**: `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste` girin.
    - **Veri türü**: Bu OMA-URI değeri **true** veya **false**olacak şekilde **Boolean** seçin.
    - **Değer**: **true**seçeneğini belirleyin.

5. Ayarları girdikten sonra ortamınız, aşağıdakine benzer bir şekilde görünecektir:

    ![Android iş profili için kopyalama ve yapıştırmayı engelleyin.](./media/custom-settings-android-for-work/custom-policy-afw-copy-paste.png)

Bu profili yönettiğiniz Android Kurumsal cihazlara atadığınızda, kopyalama ve yapıştırma eylemleri iş uygulamaları ve kişisel profiller arasında engellenir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Android cihazlarda özel bir profil](../custom-settings-android.md)oluşturun.
