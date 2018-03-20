---
title: "Windows 10 çalıştıran cihazlar için Microsoft Intune özel ayarları"
titlesuffix: 
description: "Bir Windows 10 özel profilinde yapılandırabileceğiniz özel ayarlar hakkında bilgi edinin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bb86d0f80a4d337e0ab63ae7f90d6c3541462d9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Windows 10 çalıştıran cihazlar için Microsoft Intune özel cihaz ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel** profilini kullanın. Windows 10, örneğin [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok Yapılandırma Hizmeti Sağlayıcı (CSP) ayarını kullanıma sunar.
Belirli bir ayarı arıyorsanız, [Windows 10 cihaz kısıtlama profilinin](device-restrictions-windows-10.md) Intune’da yerleşik olarak bulunan birçok ayarı içerdiğini ve özel değerler belirlemenize gerek olmadığını aklınızda bulundurun.

## <a name="configure-custom-settings"></a>Özel ayarları yapılandırma

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
1. **Özel OMA-URI Ayarları** bölmesinde, yeni değer eklemek için **Ekle**’ye tıklayın. Ayrıca, virgülle ayrılmış değerler (.csv) dosyasında yapılandırdığınız tüm değerlerin listesini oluşturmak için **Dışarı Aktar**’a da tıklayabilirsiniz.
1. Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu makaledeki listeyi kullanın:
    - **Ad** - Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama** - İsterseniz ayar için bir açıklama girin.
    - **OMA-URI (büyük/küçük harfe duyarlı)** - Bir ayarını girmek istediğiniz OMA-URI’yi belirtin.
    - **Veri türü** - Aşağıdakilerden birini seçin:
        - **Dize**
        - **Dize (XML)**
        - **Tarih ve saat**
        - **Tamsayı**
        - **Kayan nokta**
        - **Boole değeri**
        - **Base64**
    - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirilecek değeri veya dosyayı belirtin.
1. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.
Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

## <a name="example"></a>Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows belge kitaplığındaki [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusunda, Windows 10’un desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP) tam listesini bulabilirsiniz.

Tüm ayarlar, Windows 10 sürümlerinin tümüyle uyumlu değildir. Windows makalesindeki tablo, her CSP için hangi sürümlerin desteklendiğini bildirir.

Buna ek olarak Intune, makalede listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.
