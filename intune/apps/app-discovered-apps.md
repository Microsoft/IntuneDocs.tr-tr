---
title: Bulunan uygulamalar
titleSuffix: Microsoft Intune
description: Intune 'un cihazda bulduğu algılanan uygulamalarla ilgili ayrıntıları anlayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/28/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07dd262f-13e7-4cb2-9cc2-b755d1c276cf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: a9adacbc0946c45db75c2d1d91c0954e323b7d33
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181934"
---
# <a name="intune-discovered-apps"></a>Intune bulunan uygulamalar

Intune **bulunan uygulamalar** , Kiracınızdaki Intune 'a kayıtlı cihazlarda algılanan uygulamaların bir listesidir. Kiracınız için bir yazılım envanteri görevi görür. **Bulunan uygulamalar** , [uygulama yükleme](apps-monitor.md) raporlarından ayrı bir rapordur. Kişisel cihazlarda, Intune yönetilmeyen uygulamalarla ilgili bilgileri hiçbir şekilde toplamayacaktır. Kurumsal cihazlarda, yönetilen bir uygulama olup olmadığı veya bu rapor için toplanmadığı tüm uygulamalar. Beklenen davranışın eşlenme tablosu aşağıda verilmiştir. Rapor, genel olarak kayıt zamanından her 7 günde bir yenilenir (kiracı için haftalık yenileme değil). Bu yenileme döneminin tek istisnası, her 24 saatte bir toplanan Win32 uygulamaları için Intune yönetim uzantısı aracılığıyla toplanan uygulama bilgileri olur.

## <a name="monitor-discovered-apps-with-intune"></a>Bulunan uygulamaları Intune ile izleme

Intune, kiracınızdaki Intune 'A kayıtlı cihazlarda algılanan uygulamaların toplanmış bir listesini sağlar.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Uygulamalar** > **bulunan uygulamalar** > **izleme** ' yi seçin.

>[!NOTE]
>**Bulunan uygulamalar bölmesinden** **dışarı aktar** ' i seçerek bulunan uygulamalar listesini bir. csv dosyasına dışarı aktarabilirsiniz.
>
>Bulunan Win32 uygulamaları için şu anda toplam sayım yok. Bu tür veriler yalnızca cihaz başına temelinde görüntülenebilir.

Intune, kiracınızdaki ayrı bir cihaz için bulunan uygulamaların listesini de sağlar.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm cihazlar** > **cihazları** seçin.
3. Cihaz seçin.
4. Bu cihaza yönelik algılanan uygulamaları görüntülemek için **izleyici** bölümünde **bulunan uygulamalar** ' ı seçin.

## <a name="details-of-discovered-apps"></a>Bulunan uygulamaların ayrıntıları

Aşağıdaki liste, uygulama platformu türünü, kişisel cihazlar için izlenen uygulamaları, şirkete ait cihazlar için izlenen uygulamaları ve yenileme döngüsünü sağlar. Intune tarafından desteklenen uygulama türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune Içindeki uygulama türleri](apps-add.md#app-types-in-microsoft-intune).

| Platfveyam | Kişiye ait cihazlar için | Şirkete ait cihazlar için | Döngü süresi |
|------------------------------------------------------------------------|----------------------------------|--------------------------------------------------|---------------------------------------|
| Windows 10 (Win32 uygulamaları) NOTE: cihazda [Intune yönetim uzantısı gerekir](intune-management-extension.md) | Uygulanamaz | Yalnızca yönetilen uygulamalar | Cihaz kaydından her 24 saatte bir |
| Windows 10 (modern uygulamalar) | Yalnızca yönetilen modern uygulamalar | Cihazda yüklü tüm modern uygulamalar | Her 7 günde bir cihaz kaydı |
| Windows 8.1 | Yalnızca yönetilen uygulamalar | Yalnızca yönetilen uygulamalar | Her 7 günde bir cihaz kaydı |
| Windows Phone 8 | Yalnızca yönetilen uygulamalar | Yalnızca yönetilen uygulamalar | Her 7 günde bir cihaz kaydı |
| Windows RT | Yalnızca yönetilen uygulamalar | Yalnızca yönetilen uygulamalar | Her 7 günde bir cihaz kaydı |
| iOS/iPadOS | Yalnızca yönetilen uygulamalar | Cihazda yüklü tüm uygulamalar | Her 7 günde bir cihaz kaydı |
| Mac OS | Yalnızca yönetilen uygulamalar | Cihazda yüklü tüm uygulamalar | Her 7 günde bir cihaz kaydı |
| Android | Yalnızca yönetilen uygulamalar | Cihazda yüklü tüm uygulamalar | Her 7 günde bir cihaz kaydı |
| Android Kurumsal | Yalnızca yönetilen uygulamalar | Yalnızca Iş profilinde yüklü olan uygulamalar | Her 7 günde bir cihaz kaydı |

> [!NOTE]
> - Windows 10 karma Azure AD 'ye katılmış cihazlar Configuration Manager içindeki uygulama yönetimi iş yükünde gösterildiği gibi, şu anda uygulama envanterini yukarıdaki zamanlamaya göre Intune yönetim uzantısı (IME) aracılığıyla toplamamaktadır. Bu sorunu azaltmak için, IME 'nin cihaza yüklenebilmesi için Configuration Manager içindeki uygulama yönetimi iş yükünün Intune 'a geçiş yapması gerekir (Win32 envanter ve PowerShell dağıtımı için IME gereklidir). Bu davranıştaki tüm değişikliklerin veya güncelleştirmelerin [geliştirme](../fundamentals/in-development.md) ve [/veya yenilikler](../fundamentals/whats-new.md)' de duyurulduğunu unutmayın.
> - , Kasım 2019 ' den önce kaydedilen kişiye ait macOS cihazları, cihazlar yeniden kaydedilinceye kadar cihazda yüklü olan tüm uygulamaları göstermeye devam edebilir.
> - Android kurumsal tam olarak yönetilen ve adanmış, bulunan uygulamaları görüntülemez.

Bulunan uygulamaların sayısı uygulama yükleme durumu sayısıyla eşleşmeyebilir. Tutarsızlıkların olası nedenleri:

- Yüklü yönetilen bir uygulamanın hedefleme değişikliği, durum bölmesindeki yükleme sayısının azaltılmasına neden olabilir, ancak algılanan uygulamalarda bildirilen olarak kalır.
- Kiracıda aynı uygulamanın birden çok örneğinin hedeflenmesi, kullanıcı veya cihazların olası örtüşmesi nedeniyle farklı sayım sonuçları verebilir. Uygulamanın her bir örneği örtüşen kullanıcıları sayar ancak bulunan uygulamalarda yinelenen sayımlar olur.
- Bulunan uygulamalarla uygulama durumu farklı zaman çerçevelerinde toplanır ve bu da uygulama sayılarında tutarsızlığa neden olabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune içindeki uygulama türleri](apps-add.md#app-types-in-microsoft-intune)
- [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md)
