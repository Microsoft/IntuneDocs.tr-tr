---
title: "Windows Phone 8.1 için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune on Azure
description: "Windows Phone 8.1 cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e425b8a3c93c2f5dc73fbe9c75aa9adf49c5cdc8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows Phone 8.1 cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Genel
-   **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.
-   **Kamera** - Cihazın kamerasını etkinleştirir veya engeller.
-   **Kopyala ve yapıştır** - Cihazda kopyalama ve yapıştırma işlevlerini etkinleştirir veya engeller.
-   **Çıkarılabilir depolama** - Cihazın SD kartları gibi çıkarılabilir depolama birimleri kullanmasına olanak tanır.
-   **Coğrafi konum** - Cihazın konum bilgilerini kullanmasına olanak tanır.
-   **Microsoft hesabı** - Kullanıcının cihaza bir Microsoft hesabı bağlamasını etkinleştirin veya engelleyin.
-   **Ekran yakalama** - Kullanıcının ekran içeriğini resim dosyası olarak yakalamasına olanak tanır.
-   **Tanılama verisi gönderme** - Cihazın Microsoft’a tanılama bilgileri göndermesini etkinleştirir.
-   **Özel e-posta hesapları eşitleme** - Cihazın Microsoft olmayan e-posta hesaplarına bağlanmasına olanak tanır.

## <a name="password"></a>Parola
-   **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.
-   **Parola gerekli** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Gerekli parola türü** - Gerekli parola türünü belirtir (alfasayısal veya yalnızca sayısal gibi).
    -   **En az parola uzunluğu** - Parolada bulunması gereken karakter sayısı alt sınırını belirtir.
    -   **Basit parolalar** - ‘0000’ ve ‘1234’ gibi basit parolaların kullanılabileceğini belirtir.
    -   **Cihaz silinmeden önceki oturum açma hatası sayısı** - Cihaz temizlenmeden önce kullanıcının kaç kez hatalı parola girilebileceğini belirtir.
    -   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Ekran otomatik olarak kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.
    -   **Parola süresinin sonu (gün)** - Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.
    -   **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış olan kaç parolanın anımsanacağını belirtir.
-   **Şifreleme** - Desteklenen mobil cihazlarda verilerin şifrelenmesini zorunlu tutar.

## <a name="app-store"></a>Uygulama Mağazası
-   **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.
-   **Uygulama mağazası** - Kullanıcıların cihazdan uygulama mağazasına bağlanmasına olanak tanır.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

-   **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

**Engellenen uygulamalar** listesi - Intune tarafından yönetilmeyen, kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.
**İzin verilen uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra da tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Mağazadaki uygulamanın URL’sini belirtme

İzin verilen veya engellenen uygulamalar listesinde bir uygulama URL'si belirtmek için aşağıdaki biçimi kullanın:

[Windows Phone Mağazası](https://www.microsoft.com/store/apps/windows-phone) sayfasında, kullanmak istediğiniz uygulamayı arayın.

Uygulamanın sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu izin verilen veya engellenen uygulamalar listesinde URL olarak kullanabilirsiniz.

Örnek: Mağazada Skype uygulamasını arayın. Kullandığınız URL **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51** olacaktır.



### <a name="additional-options"></a>Ek seçenekler

Ayrıca, **İçeri Aktar**’a tıklayarak listeyi <*uygulama url’si*>, <*uygulama adı*>, <*uygulama yayımcısı*> biçimindeki bir csv dosyasından doldurabilir veya **Dışarı Aktar**’a tıklayarak kısıtlı uygulama listesinin içeriğiyle, aynı biçimde bir csv dosyası oluşturabilirsiniz.


## <a name="browser"></a>Tarayıcı
-   **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.
-   **Web tarayıcısı** - Cihazlarda yerleşik web tarayıcısını etkinleştirir veya engeller.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı
-   **Tüm ayarları yalnızca Windows Phone 8.1’e uygula** - Bu, klasik Intune portalında yapılandırabileceğiniz bir ayardır. Azure Portal’da bu ayar değiştirilemez. **Yapılandırıldı** olarak ayarlanırsa, tüm ayarlar yalnızca Windows Phone 8.1 cihazlarına uygulanır. **Yapılandırılmadı** olarak ayarlanırsa, bu ayarlar Windows 10 Mobile cihazlarına da uygulanır.
-   **Wi-Fi** - Cihazda Wi-Fi işlevselliğini etkinleştirir veya devre dışı bırakır.
-   **Wi-Fi paylaşımı** - Cihazda Wi-Fi paylaşımının kullanımını etkinleştirir.
-   **Wi-Fi etkin noktalarına otomatik bağlanma** - Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve tüm kullanım koşullarını otomatik olarak kabul etmesine olanak tanır.
-   **Wi-Fi etkin nokta raporlama** - Kullanıcının yakındaki bağlantıların keşfetmesine yardımcı olmak için Wi-Fi bağlantıları hakkında bilgi gönderir.
-   **NFC** - Bu özelliği destekleyen cihazlarda yakın alan iletişimini kullanan işlemleri etkinleştirir veya devre dışı bırakır.
-   **Bluetooth** - Cihazda Bluetooth işlevselliğini etkinleştirir veya devre dışı bırakır.
