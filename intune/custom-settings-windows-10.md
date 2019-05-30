---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için özel ayarlar ekleme | Microsoft Docs
description: Microsoft Intune’da Windows 10 çalıştıran cihazlar için OMA-URI ayarlarını kullanmak üzere özel bir profil ekleyin veya oluşturun. Özel ayarları eklemek için özel bir profil kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e9d07b2d46e5128d96a578e9a000e17c2aca7cec
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373981"
---
# <a name="use-custom-settings-for-windows-10-devices-in-intune"></a>Intune’da Windows 10 cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, “özel profiller” kullanan Windows 10 cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Windows 10 özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak farklı özellikleri yapılandırır. Bu ayarlar normalde mobil cihaz üreticileri tarafından cihazdaki özellikleri denetlemek için kullanılır. 

Windows 10, [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) gibi pek çok Yapılandırma Hizmeti Sağlayıcısı (CSP) ayarını kullanıma sunar.

Belirli bir ayarı arıyorsanız [Windows 10 cihaz kısıtlama profilinde](device-restrictions-windows-10.md) yerleşik olarak pek çok ayar bulunduğunu unutmayın. Bu sayede, özel değerler girmeniz gerekmeyebilir.

Bu makale:

- Windows 10 cihazlarda özel profil oluşturmayı gösterir
- Önerilen OMA-URI ayarlarının bir listesini içerir
- VPN bağlantısı açan özel profile yönelik bir örnek sunar

## <a name="create-the-profile"></a>Profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için bir ad girmeniz `windows 10 custom profile`.
    - **Açıklama**: Profil için açıklama girin.
    - **Platform**: Seçin **Windows 10 ve üzeri**.
    - **Profil türü**: Seçin **özel**.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.
    - **Açıklama**: Ayar ve diğer önemli ayrıntıları genel bakışını veren bir açıklama girin.
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

## <a name="example"></a>Örnek

Aşağıdaki örnekte, **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu ayar, bir Windows 10 cihazın hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

[Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusunda, Windows 10’un desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP) tam listesi bulunur.

Tüm ayarlar, Windows 10 sürümlerinin tümüyle uyumlu değildir. [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference), her bir CSP için hangi sürümlerin desteklendiğini açıklar.

Ayrıca Intune, [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusundaki tüm ayarları desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfası, desteklediği işlemi gösterir. Intune ile çalışacak biçimde ayarı desteklemelidir **Ekle**, **değiştirin**, ve **alma** operations. Tarafından döndürülen değer, **alma** işlemi tarafından sağlanan değer eşleşmiyor **Ekle** veya **değiştirin** işlemleri, ardından Intune raporları bir uyumluluk hatası.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).
