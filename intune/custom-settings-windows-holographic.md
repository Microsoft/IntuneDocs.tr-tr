---
title: "Windows Holographic for Business cihazlar için Intune özel ayarları"
titlesuffix: Azure portal
description: "Bir Windows Holographic for Business özel profilinde kullanabileceğiniz ayarlar hakkında bilgi edinin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows Holographic for Business cihazlar için özel cihaz ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows Holographic for Business için Microsoft Intune **özel** profilini kullanın. Windows Holographic for Business, pek çok yapılandırma hizmet sağlayıcıları (CSP’ler) ayarını kullanılabilir hale getirir. CSP’ye genel bakış için bkz. [BT uzmanları için yapılandırma hizmet sağlayıcılarına (CSP’ler) giriş](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Windows Holographic tarafından desteklenen belirli CSP’ler için bkz. [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Belirli bir ayarı arıyorsanız, [Windows Holographic for Business cihaz kısıtlama profilinin](device-restrictions-windows-holographic.md) pek çok yerleşik ayarı içerdiğini ve özel değerler belirlemeyi gerektirmediğini aklınızda bulundurun.

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** dikey penceresinde **Ayarlar**’ı seçin.
3. **Özel OMA-URI Ayarları** dikey penceresinde, yeni değer eklemek için **Ekle**’ye tıklayın. Ayrıca, virgülle ayrılmış değerler (.csv) dosyasında yapılandırdığınız tüm değerlerin listesini oluşturmak için **Dışarı Aktar**’a da tıklayabilirsiniz.
4. Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu konu başlığı altındaki listeyi kullanın:
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
5. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**'a tıklayın.
Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="supported-custom-settings"></a>Desteklenen özel ayarlar

Windows Holographic for Business, aşağıdaki özel ayarları destekler:


|Ayar adı|OMA URI|Veri türü  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Tamsayı (0 - izin verilmez, 1 - izin verilir)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Tamsayı (0 - izin verilmez, 1 - izin verilir)|



## <a name="how-to-find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows Holographic’in desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP’ler) tam listesini [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens) bölümünde bulabilirsiniz. Tüm ayarlar, Windows Holographic sürümlerinin tümüyle uyumlu değildir. Windows başlıklı tabloda, her CSP için hangi sürümlerin desteklendiğini gösterir.

Buna ek olarak, Intune konu başlığı altında listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için, ilgili ayarın konusunu açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.


