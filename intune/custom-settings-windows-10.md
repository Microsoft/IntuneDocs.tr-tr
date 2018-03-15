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
ms.openlocfilehash: 156d37874529b4ae5a8176d7e9a8873cf440c32c
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Windows 10 çalıştıran cihazlar için Microsoft Intune özel cihaz ayarları 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel** profilini kullanın. Windows 10, örneğin [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok Yapılandırma Hizmeti Sağlayıcı (CSP) ayarını kullanıma sunar.
Belirli bir ayarı arıyorsanız, [Windows 10 cihaz kısıtlama profilinin](device-restrictions-windows-10.md) Intune’da yerleşik olarak bulunan birçok ayarı içerdiğini ve özel değerler belirlemenize gerek olmadığını aklınızda bulundurun.

## <a name="configure-custom-settings"></a>Özel ayarları yapılandırma

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** sayfasında **Ayarlar**’ı seçin.
3. **Özel OMA-URI Ayarları** sayfasında, yeni değer eklemek için **Ekle**’ye tıklayın. Ayrıca, virgülle ayrılmış değerler (.csv) dosyasında yapılandırdığınız tüm değerlerin listesini oluşturmak için **Dışarı Aktar**’a da tıklayabilirsiniz.
4. Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu makaledeki listeyi kullanın:
    - **Ayar adı** - Ayar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.
    - **Ayar açıklaması** - İsterseniz ayar için bir açıklama girin.
    - **Veri türü** - Aşağıdakilerden birini seçin:
        - **Dize**
        - **Dize (XML)**
        - **Tarih ve saat**
        - **Tamsayı**
        - **Kayan nokta**
        - **Boole değeri**
    - **OMA-URI (büyük/küçük harfe duyarlı)** - Bir ayarını girmek istediğiniz OMA-URI’yi belirtin.
    - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.
5. Bitirdiğinizde **Profil Oluştur** sayfasına dönün ve **Oluştur**’a basın.
Profil oluşturulur ve profil listesi sayfasında görüntülenir.

## <a name="example"></a>Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows belge kitaplığındaki [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusunda, Windows 10’un desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP) tam listesini bulabilirsiniz.

Tüm ayarlar, Windows 10 sürümlerinin tümüyle uyumlu değildir. Windows makalesindeki tablo, her CSP için hangi sürümlerin desteklendiğini bildirir.

Buna ek olarak Intune, makalede listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.


