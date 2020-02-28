---
title: Microsoft Intune - Azure ile cihaz ayrıntılarını görüntüleme | Microsoft Docs
description: İşletim sistemleri, depolama alanı, üretim ve modeli içeren cihaz ayrıntılarınızı görüntüleyin. Azure'da Microsoft Intune ile yüklü uygulamaların bir listesini alın, uyumluluk ilkelerini denetleyin ve TeamViewer'ı ayarlayın. Bu, yönettiğiniz cihazların envanterini görüntülemeye benzer.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: df814abf9cdff3eb4d9fbac8183618461b590adb
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781923"
---
# <a name="see-device-details-in-intune"></a>Intune'da cihaz ayrıntılarına bakın

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

**Cihazlar** özelliği, yönettiğiniz cihazlarla ilgili olarak donanım ve yüklü uygulamalar gibi ek ayrıntılar sağlar.

Bu makalede, tüm cihazlarınızı ve özelliklerini Azure portalında nasıl görüntüleyeceğiniz gösterilir.

## <a name="view-the-device-details"></a>Cihaz ayrıntılarını görüntüleme

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Cihazlar** > **Tüm cihazlar**’a gidin ve listelenen cihazlarınızdan birini seçip ayrıntılarını görüntüleyin:

   - **Genel bakış** , cihaz adını gösterir ve kendi cihazını getir (KCG) cihazı, zaman içinde çek ve daha fazlasını belirtir. Cihazda şunları yapabilirsiniz:
      - [Devre Dışı Bırak](devices-wipe.md#retire)
      - [Silme](devices-wipe.md#wipe)
      - [Sil](devices-wipe.md#delete-devices-from-the-intune-portal)
      - [Uzaktan kilitleme](device-remote-lock.md)
      - [Tablosunun](device-sync.md)
      - [Geçiş Kodunu Sıfırla](device-passcode-reset.md)
      - [Yeniden başlatma](device-restart.md) (yalnızca Windows)
      - [Yeni Başlangıç](device-fresh-start.md) (yalnızca Windows)
      - [Autopilot sıfırlaması]() (yalnızca Windows)
      - [Hızlı tarama](../configuration/device-restrictions-windows-10.md) (yalnızca Windows 10)
      - [Tam tarama](../configuration/device-restrictions-windows-10.md) (yalnızca Windows 10)
       - [Cihazı yeniden adlandırma](device-rename.md)
      - Uzaktan yardım oturumu başlatma
   - **Özellikler**’i kullanarak [oluşturduğunuz bir cihaz kategorisini](../enrollment/device-group-mapping.md) atayabilir ve cihazın sahipliğini kişisel veya şirket olarak değiştirebilirsiniz.
   - **Donanım** cihaz kimliği, işletim sistemi ve sürümü, depolama alanı ve daha fazla ayrıntı gibi cihazla ilgili birçok ayrıntıyı içerir.
   - **Bulunan uygulamalar**, Intune’un cihazda yüklü olduğunu bulduğu tüm uygulamaları ve uygulama sürümlerini listeler. Daha fazla bilgi için bkz. [Intune bulunan uygulamalar](../apps/app-discovered-apps.md).
   - **Cihaz uyumluluğu**, atanmış tüm uyumluluk ilkelerini ve cihazın uyumlu olup olmadığını listeler.
   - **Cihaz yapılandırması**, cihaza atanmış tüm yapılandırma ilkelerini ve ilkenin başarılı olup olmadığını gösterir.

## <a name="hardware-device-details"></a>Donanım cihazı durumu
Cihazlar tarafından kullanılan taşıyıcıya bağlı olarak, tüm ayrıntılar toplanmayabilir

> [!Note]  
> Donanım ve yazılım envanteri, Intune hizmetinde her 7 günde bir yenilenir.

|Ayrıntı|Açıklama|Platfveyam| 
|--------------|----------------------|----|  
|Ad|Cihazın adı.|Windows, iOS|
|Yönetim adı|Yalnızca konsolda kullanılan cihaz adı. Bu adın değiştirilmesi, cihazdaki adı değiştirmez.|Windows, iOS|
|UDID|Cihazın Benzersiz Cihaz tanımlayıcısı.|Windows, iOS|
|Intune Cihaz Kimliği|Cihazı benzersiz şekilde tanımlayan GUID.|Windows, iOS|
|Seri numarası|Üreticisinden cihazın seri numarası.|Windows, iOS|
|Paylaşılan cihaz|**Evet** ise cihaz birden fazla kullanıcı tarafından paylaşılır.|Windows, iOS|
|Kullanıcı onaylı kayıt|Yanıt **Evet**ise, cihazın cihazdaki belirli güvenlik ayarlarını yönetmesine olanak tanıyan Kullanıcı onaylı kaydı vardır.|Windows, iOS|
|İşletim sistemi|Cihazda kullanılan işletim sistemi.|Windows, iOS|
|İşletim sistemi sürümü|Cihazdaki işletim sisteminin sürümü.|Windows, iOS|
|İşletim sistemi dili|Cihazdaki işletim sisteminin dil kümesi.|Windows, iOS|
|Yapı numarası|İşletim sisteminin yapı numarası.|Android|
|Güvenlik Düzeltme eki düzeyi|Cihaz için güvenlik düzeltme eki düzeyi.|Android|
|Toplam depolama alanı|Cihazdaki toplam depolama alanı (gigabayt olarak).|Windows, iOS|
|Boş depolama alanı|Cihazdaki kullanılmayan depolama alanı (gigabayt olarak).|Windows, iOS|
|IMEI|Cihazın Uluslararası Mobil Ekipman Tanımlayıcısı.|Windows, iOS/ıpados, Android|
|MEID|Cihazın mobil ekipman tanımlayıcısı.|Windows, iOS/ıpados, Android|
|Üretici|Cihazın üreticisi.|Windows, iOS/ıpados, Android|
|Model|Cihazın modeli.|Windows, iOS/ıpados, Android|
|Telefon numarası|Cihaza atanan telefon numarası.|Windows, iOS/ıpados, Android *|
|Abone operatör|Cihazın kablosuz operatörü.|Windows, iOS/ıpados, Android|
|Hücresel teknoloji|Cihaz tarafından kullanılan radyo sistemi.|Windows, iOS/ıpados, Android|
|Wi-Fi MAC|Cihazın Ortam Erişim Denetimi adresi.|Windows, iOS/ıpados, Android|
|ICCID|Entegre Devre Kart Tanımlayıcısı, yani bir SIM kartın benzersiz kimlik numarası.|Windows, iOS/ıpados, Android|
|Kaydolma tarihi|Cihazın Intune’a kaydedildiği tarih ve saat.|Windows, iOS/ıpados, Android|
|Son iletişim|Cihazın Intune’a son bağlandığı tarih ve saat.|Windows, iOS/ıpados, Android|
|Etkinleştirme kilidi atlama kodu|Etkinleştirme kilidini devre dışı bırakmak için kullanılan kod.|iOS|
|Azure AD kayıtlı|**Evet** ise cihaz Azure Directory’ye kayıtlıdır.|Windows, iOS/ıpados, Android|
|Intune kayıtlı|Yanıt **Evet**ise, cihaz Intune 'a kaydedilir|Windows, iOS/ıpados, Android|
|Uyumluluk|Cihazın uyumluluk durumu.|Windows, iOS/ıpados, Android|
|EAS etkin|**Evet** ise cihaz Exchange posta kutusu ile eşitlenir.|Windows, iOS/ıpados, Android|
|EAS etkinleştirme kimliği|Cihazın Exchange ActiveSync tanımlayıcısı.|Windows, iOS/ıpados, Android|
|Denetimli|**Evet** ise yöneticiler cihaz üzerinde gelişmiş denetime sahiptir.|Windows, iOS/ıpados, Android|
|Şifreli|**Evet** ise cihazda depolanan veriler şifrelenir.|Windows, iOS/ıpados, Android|

> [!Note]  
> Telefon numarası, Android kurumsal adanmış veya tam olarak yönetilen cihazlarda envantere kaydedilmiş değildir.

## <a name="next-steps"></a>Sonraki adımlar
Intune ile [cihazlarınızı yönetmek](device-management.md) için başka neler yapabileceğinizi görün.
