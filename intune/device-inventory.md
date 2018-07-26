---
title: Microsoft Intune - Azure ile cihaz ayrıntılarını görüntüleme | Microsoft Docs
description: İşletim sistemleri, depolama alanı, üretim ve modeli içeren cihaz ayrıntılarınızı görüntüleyin. Azure'da Microsoft Intune ile yüklü uygulamaların bir listesini alın, uyumluluk ilkelerini denetleyin ve TeamViewer'ı ayarlayın. Bu, yönettiğiniz cihazların envanterini görüntülemeye benzer.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b8067610e21652a40cb87302d8f1f3d05de342
ms.sourcegitcommit: f5998019bbb4769fb50a7ea9bf424199516eb9ee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2018
ms.locfileid: "39117931"
---
# <a name="see-device-details-in-intune"></a>Intune'da cihaz ayrıntılarına bakın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Cihazlar** özelliği, yönettiğiniz cihazlarla ilgili olarak donanım ve yüklü uygulamalar gibi ek ayrıntılar sağlar.

Bu makalede, tüm cihazlarınızı ve özelliklerini Azure portalında nasıl görüntüleyeceğiniz gösterilir.

## <a name="view-the-device-details"></a>Cihaz ayrıntılarını görüntüleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar** > **Tüm cihazlar**’a gidin ve listelenen cihazlarınızdan birini seçip ayrıntılarını görüntüleyin:

   - **Genel Bakış**, cihazın adını gösterir ve kendi cihazını getir (KCG) cihazı olup olmadığı, ne zaman iade edildiği gibi bazı temel özellikleri listeler. **Diğer**’i seçerek yapabilecekleriniz şu şekildedir:
     - Şirket verilerini kaldırma
     - Cihazı silme
     - Cihazı uzaktan kilitleme
     - Silme
     - Uzaktan yardım oturumu başlatma
   - **Özellikler**’i kullanarak [oluşturduğunuz bir cihaz kategorisini](device-group-mapping.md) atayabilir ve cihazın sahipliğini kişisel veya şirket olarak değiştirebilirsiniz.
   - **Donanımda** cihaz hakkında pek çok bilgi bulunur. Örneğin cihaz kimliği, işletim sistemi ve sürümü, depolama alanı, model ve üretici, koşullu erişim ayarları vb.
   - **Bulunan uygulamalar**, Intune’un cihazda yüklü olduğunu bulduğu tüm uygulamaları ve uygulama sürümlerini listeler. Uygulama listesini bir .csv dosyası olarak **Dışarı Aktarabilirsiniz**.
   - **Cihaz uyumluluğu**, atanmış tüm uyumluluk ilkelerini ve cihazın uyumlu olup olmadığını listeler.
   - **Cihaz yapılandırması**, cihaza atanmış tüm yapılandırma ilkelerini ve ilkenin başarılı olup olmadığını gösterir.

Intune, yalnızca şirkete ait cihazlarda uygulama listesi toplar. Kişisel cihazlarda uygulamalar denetlenmez. Windows 10 bilgisayarlarda, şirkete ait cihazlar için yalnızca modern uygulamalar listelenir. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz. Cihazlarda kullanılan operatöre bağlı olarak, tüm uygulamalar toplanamayabilir.

|Platform|Kişiye Ait Cihazlar İçin|Şirkete Ait Cihazlar İçin|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (Configuration Manager istemcisi olmadan)|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|
|Windows 8.1 (Configuration Manager istemcisi olmadan)|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|Windows Phone 8|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|Windows RT|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|iOS|Yalnızca yönetilen uygulamalar|Cihazda yüklü tüm uygulamalar|
|Mac OS|Cihazda yüklü tüm uygulamalar|Cihazda yüklü tüm uygulamalar|  
|Android|Yalnızca yönetilen uygulamalar|Cihazda yüklü tüm uygulamalar|  

## <a name="hardware-device-details"></a>Donanım cihazı durumu

### <a name="windows-and-ios-device-details"></a>Windows ve iOS cihaz ayrıntıları:
|Ayrıntı|Description|  
|--------------|----------------------|  
|Ad|Cihazın adı.|
|Yönetim adı|Yalnızca konsolda kullanılan cihaz adı. Bu adın değiştirilmesi, cihazdaki adı değiştirmez.|
|UDID|Cihazın Benzersiz Cihaz tanımlayıcısı.|
|Intune Cihaz Kimliği|Cihazı benzersiz şekilde tanımlayan GUID.|
|Seri numarası|Üreticisinden cihazın seri numarası.|
|Paylaşılan cihaz|**Evet** ise cihaz birden fazla kullanıcı tarafından paylaşılır.|
|Kullanıcı onaylı kayıt|**Evet** ise cihazda yöneticilerin belirli cihaz güvenlik ayarlarını yönetmesini sağlayan kullanıcı onaylı kayıt vardır.|
|İşletim sistemi|Cihazda kullanılan işletim sistemi.|
|İşletim sistemi sürümü|Cihazdaki işletim sistemi sürümü.|
|İşletim sistemi dili|Cihazdaki işletim sisteminin dil kümesi.|
|Toplam depolama alanı|Cihazdaki toplam depolama alanı (gigabayt olarak).|
|Boş depolama alanı|Cihazdaki kullanılmayan depolama alanı (gigabayt olarak).|


### <a name="windows-ios-and-macos-device-details"></a>Windows, iOS ve macOS cihaz ayrıntıları
|Ayrıntı|Description|  
|--------------|----------------------|  
|IMEI|Cihazın Uluslararası Mobil Ekipman Tanımlayıcısı.|
|MEID|Cihazın mobil ekipman tanımlayıcısı.|
|Üretici|Cihazın üreticisi.|
|Model|Cihazın modeli.|
|Telefon numarası|Cihaza atanan telefon numarası.|
|Abone operatör|Cihazın kablosuz operatörü.|
|Hücresel teknoloji|Cihaz tarafından kullanılan radyo sistemi.|
|Wi-Fi MAC|Cihazın Ortam Erişim Denetimi adresi.|
|ICCID|Entegre Devre Kart Tanımlayıcısı, yani bir SIM kartın benzersiz kimlik numarası.|
|Kaydolma tarihi|Cihazın Intune’a kaydedildiği tarih ve saat.|
|Son iletişim|Cihazın Intune’a son bağlandığı tarih ve saat.|
|Etkinleştirme kilidi atlama kodu|Etkinleştirme kilidini atlamak için kullanılabilecek kod.|
|Azure AD kayıtlı|**Evet** ise cihaz Azure Directory’ye kayıtlıdır.|
|Uyumluluk|Cihazın uyumluluk durumu.|
|EAS etkin|**Evet** ise cihaz Exchange posta kutusu ile eşitlenir.|
|EAS etkinleştirme kimliği|Cihazın Exchange ActiveSync tanımlayıcısı.|
|Denetimli|**Evet** ise yöneticiler cihaz üzerinde gelişmiş denetime sahiptir.|
|Şifreli|**Evet** ise cihazda depolanan veriler şifrelenir.|



## <a name="next-steps"></a>Sonraki adımlar
Intune ile [cihazlarınızı yönetmek](device-management.md) için başka neler yapabileceğinizi görün.