---
title: Microsoft Intune - Azure ile cihaz ayrıntılarını görüntüleme | Microsoft Docs
description: İşletim sistemleri, depolama alanı, üretim ve modeli içeren cihaz ayrıntılarınızı görüntüleyin. Azure'da Microsoft Intune ile yüklü uygulamaların bir listesini alın, uyumluluk ilkelerini denetleyin ve TeamViewer'ı ayarlayın. Bu, yönettiğiniz cihazların envanterini görüntülemeye benzer.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c22822f34f426897549383df5e9c71b21b497a7e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57391208"
---
# <a name="see-device-details-in-intune"></a>Intune'da cihaz ayrıntılarına bakın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Cihazlar** özelliği, yönettiğiniz cihazlarla ilgili olarak donanım ve yüklü uygulamalar gibi ek ayrıntılar sağlar.

Bu makalede, tüm cihazlarınızı ve özelliklerini Azure portalında nasıl görüntüleyeceğiniz gösterilir.

## <a name="view-the-device-details"></a>Cihaz ayrıntılarını görüntüleme

1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar** > **Tüm cihazlar**’a gidin ve listelenen cihazlarınızdan birini seçip ayrıntılarını görüntüleyin:

   - **Genel Bakış**, cihazın adını gösterir ve kendi cihazını getir (KCG) cihazı olup olmadığı, ne zaman iade edildiği gibi bazı temel özellikleri listeler. Cihazda aşağıdaki işlemleri yapabilirsiniz:
      - [Devre Dışı Bırak](devices-wipe.md#retire)
        - [Silme](devices-wipe.md#wipe)
        - [Uzaktan kilitleme](device-remote-lock.md)
        - [Cihazı eşitleme](device-sync.md)
        - [Geçiş Kodunu Sıfırla](device-passcode-reset.md)
        - [Yeniden başlatma](device-restart.md) (yalnızca Windows)
        - [Yeni Başlangıç](device-fresh-start.md) (yalnızca Windows)
     - Uzaktan yardım oturumu başlatma
   - **Özellikler**’i kullanarak [oluşturduğunuz bir cihaz kategorisini](device-group-mapping.md) atayabilir ve cihazın sahipliğini kişisel veya şirket olarak değiştirebilirsiniz.
   - **Donanımda** cihaz hakkında pek çok bilgi bulunur. Örneğin cihaz kimliği, işletim sistemi ve sürümü, depolama alanı, model ve üretici, koşullu erişim ayarları vb.
   - **Bulunan uygulamalar**, Intune’un cihazda yüklü olduğunu bulduğu tüm uygulamaları ve uygulama sürümlerini listeler. Uygulama listesini bir .csv dosyası olarak **Dışarı Aktarabilirsiniz**. Bu liste, 7 günde bir güncelleştirilir.
   - **Cihaz uyumluluğu**, atanmış tüm uyumluluk ilkelerini ve cihazın uyumlu olup olmadığını listeler.
   - **Cihaz yapılandırması**, cihaza atanmış tüm yapılandırma ilkelerini ve ilkenin başarılı olup olmadığını gösterir.

Intune, yalnızca şirkete ait cihazlarda uygulama listesi toplar. Kişisel cihazlarda uygulamalar denetlenmez. Windows 10 bilgisayarlarda, şirkete ait cihazlar için yalnızca modern uygulamalar listelenir. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz. Cihazlarda kullanılan operatöre bağlı olarak, tüm uygulamalar toplanamayabilir.

|Platform|Kişiye ait cihazlar için|Şirketinize ait cihazlar için|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (Configuration Manager istemcisi olmadan)|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|
|Windows 8.1 (Configuration Manager istemcisi olmadan)|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|Windows Phone 8|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|Windows RT|Yalnızca yönetilen uygulamalar|Yalnızca yönetilen uygulamalar|  
|iOS|Yalnızca yönetilen uygulamalar|Cihazda yüklü tüm uygulamaları|
|Mac OS|Cihazda yüklü tüm uygulamaları|Cihazda yüklü tüm uygulamaları|  
|Android|Yalnızca yönetilen uygulamalar|Cihazda yüklü tüm uygulamaları|  
|Android Kurumsal|Yalnızca yönetilen uygulamalar|Yalnızca iş profilinde yüklü uygulamalar|  

## <a name="hardware-device-details"></a>Donanım cihazı durumu
Cihazlar tarafından kullanılan operatöre bağlı olarak, tüm ayrıntıları toplanabilir

|Ayrıntı|Açıklama|Platform| 
|--------------|----------------------|----|  
|Name|Cihazın adı.|Windows, iOS|
|Yönetim adı|Yalnızca konsolda kullanılan cihaz adı. Bu adın değiştirilmesi, cihazdaki adı değiştirmez.|Windows, iOS|
|UDID|Cihazın Benzersiz Cihaz tanımlayıcısı.|Windows, iOS|
|Intune Cihaz Kimliği|Cihazı benzersiz şekilde tanımlayan GUID.|Windows, iOS|
|Seri numarası|Üreticisinden cihazın seri numarası.|Windows, iOS|
|Paylaşılan cihaz|**Evet** ise cihaz birden fazla kullanıcı tarafından paylaşılır.|Windows, iOS|
|Kullanıcı onaylı kayıt|**Evet** ise cihazda yöneticilerin belirli cihaz güvenlik ayarlarını yönetmesini sağlayan kullanıcı onaylı kayıt vardır.|Windows, iOS|
|İşletim sistemi|Cihazda kullanılan işletim sistemi.|Windows, iOS|
|İşletim sistemi sürümü|Cihazdaki işletim sistemi sürümü.|Windows, iOS|
|İşletim sistemi dili|Cihazdaki işletim sisteminin dil kümesi.|Windows, iOS|
|Toplam depolama alanı|Cihazdaki toplam depolama alanı (gigabayt olarak).|Windows, iOS|
|Boş depolama alanı|Cihazdaki kullanılmayan depolama alanı (gigabayt olarak).|Windows, iOS|
|IMEI|Cihazın Uluslararası Mobil Ekipman Tanımlayıcısı.|Windows, iOS, Android|
|MEID|Cihazın mobil ekipman tanımlayıcısı.|Windows, iOS, Android|
|Üretici|Cihazın üreticisi.|Windows, iOS, Android|
|Model|Cihazın modeli.|Windows, iOS, Android|
|Telefon numarası|Cihaza atanan telefon numarası.|Windows, iOS, Android|
|Abone operatör|Cihazın kablosuz operatörü.|Windows, iOS, Android|
|Hücresel teknoloji|Cihaz tarafından kullanılan radyo sistemi.|Windows, iOS, Android|
|Wi-Fi MAC|Cihazın Ortam Erişim Denetimi adresi.|Windows, iOS, Android|
|ICCID|Entegre Devre Kart Tanımlayıcısı, yani bir SIM kartın benzersiz kimlik numarası.|Windows, iOS, Android|
|Kaydolma tarihi|Cihazın Intune’a kaydedildiği tarih ve saat.|Windows, iOS, Android|
|Son iletişim|Cihazın Intune’a son bağlandığı tarih ve saat.|Windows, iOS, Android|
|Etkinleştirme kilidi atlama kodu|Etkinleştirme kilidini atlamak için kullanılabilecek kod.|Windows, iOS, Android|
|Azure AD kayıtlı|**Evet** ise cihaz Azure Directory’ye kayıtlıdır.|Windows, iOS, Android|
|Uyumluluk|Cihazın uyumluluk durumu.|Windows, iOS, Android|
|EAS etkin|**Evet** ise cihaz Exchange posta kutusu ile eşitlenir.|Windows, iOS, Android|
|EAS etkinleştirme kimliği|Cihazın Exchange ActiveSync tanımlayıcısı.|Windows, iOS, Android|
|Denetimli|**Evet** ise yöneticiler cihaz üzerinde gelişmiş denetime sahiptir.|Windows, iOS, Android|
|Şifreli|**Evet** ise cihazda depolanan veriler şifrelenir.|Windows, iOS, Android|



## <a name="next-steps"></a>Sonraki adımlar
Intune ile [cihazlarınızı yönetmek](device-management.md) için başka neler yapabileceğinizi görün.
