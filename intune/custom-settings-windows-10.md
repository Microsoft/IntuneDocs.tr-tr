---
title: "Windows 10 cihazlar için Intune özel ayarları"
titlesuffix: Azure portal
description: "Bir Windows 10 özel profilinde kullanabileceğini ayarlar hakkında bilgi edinin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 03dd17d1ef6cde7514720c063cef7da4c3c7db3d
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 cihazları için özel cihaz ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel** profilini kullanın. Windows 10, örneğin [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok CSP ayarını kullanıma sunar.
Belirli bir ayarı arıyorsanız, [Windows 10 cihaz kısıtlama profilinin](device-restrictions-windows-10.md) Intune’da yerleşik olarak bulunan birçok ayarı içerdiğini ve özel değerler belirlemenize gerek olmadığını aklınızda bulundurun.

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
5. Bitirdiğinizde, **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.
Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="example"></a>Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows belge kitaplığındaki [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusunda, Windows 10’un desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP) tam listesini bulabilirsiniz.

Tüm ayarlar, Windows 10 sürümlerinin tümüyle uyumlu değildir. Windows başlıklı tabloda, her CSP için hangi sürümlerin desteklendiğini gösterir.

Buna ek olarak, Intune konu başlığı altında listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için, ilgili ayarın konusunu açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.


