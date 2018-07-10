---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için özel ayarlar | Microsoft Docs
description: Microsoft Intune’da özel bir profil kullanarak Windows 10 çalıştıran cihazlarda OMA-URI özel ayarlarını yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232835"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Windows 10 cihazlar için özel OMA-URI ayarları - Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarlarını dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel** profilini kullanın. Bu ayarlar, cihazlarda özellik denetlemek için kullanılır. Windows 10, [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) gibi pek çok Yapılandırma Hizmeti Sağlayıcısı (CSP) ayarını kullanıma sunar.

Belirli bir ayarı arıyorsanız [Windows 10 cihaz kısıtlama profilinin](device-restrictions-windows-10.md) Intune’da yerleşik olarak bulunan birçok ayarı içerdiğini ve özel değerler gerektirmediğini aklınızda bulundurun.

## <a name="configure-custom-settings"></a>Özel ayarları yapılandırma

1. **Özel** profil türünü kullanarak yeni bir yapılandırma profili oluşturun. [Özel cihaz ayarlarını yapılandırma](custom-settings-configure.md), adımları listeler.
2. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçerek yeni bir ayar oluşturun. Ayrıca, virgülle ayrılmış değerler (.csv) dosyasında yapılandırdığınız tüm değerlerin listesini oluşturmak için **Dışarı Aktar**’a da tıklayabilirsiniz.
3. Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin:

- **Ad**: Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
- **Açıklama**: İsterseniz ayar için bir açıklama girin.
- **OMA-URI (büyük/küçük harfe duyarlı)**: Bir ayarını sağlamak istediğiniz OMA-URI’yi girin.
- **Veri türü**: Aşağıdakilerden birini seçin:
  - **Dize**
  - **Dize (XML)**
  - **Tarih ve saat**
  - **Tamsayı**
  - **Kayan nokta**
  - **Boole değeri**
  - **Base64**
- **Değer**: Girdiğiniz OMA-URI ile ilişkilendirilecek değeri veya dosyayı girin.

4. İşiniz bittiğinde **Tamam**’ı seçin. **Profil Oluştur**’da **Oluştur**’u seçin. Profil oluşturulur ve profiller listesinde gösterilir.

## <a name="example"></a>Örnek
Aşağıdaki örnekte, **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu ayar, bir Windows 10 cihazın hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

[Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusunda, Windows 10’un desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP) tam listesini bulabilirsiniz.

Tüm ayarlar, Windows 10 sürümlerinin tümüyle uyumlu değildir. [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference), her bir CSP için hangi sürümlerin desteklendiğini açıklar.

Ayrıca Intune, listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.
