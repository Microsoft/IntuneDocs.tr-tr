---
title: Bulunan uygulamalar
titleSuffix: Microsoft Intune
description: Intune 'un cihazda bulduğu algılanan uygulamalarla ilgili ayrıntıları anlayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07dd262f-13e7-4cb2-9cc2-b755d1c276cf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b8fcf211c19146ae632a40aad032266d498c183
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731449"
---
# <a name="intune-discovered-apps"></a>Intune bulunan uygulamalar

Intune **bulunan uygulamalar** , Kiracınızdaki Intune 'a kayıtlı cihazlarda algılanan uygulamaların bir listesidir. Kiracınız için bir yazılım envanteri görevi görür. **Bulunan uygulamalar** , [uygulama yükleme](apps-monitor.md) raporlarından ayrı bir rapordur. Kişisel cihazlarda, Intune yönetilmeyen uygulamalarla ilgili bilgileri hiçbir şekilde toplamayacaktır. Kurumsal cihazlarda, yönetilen bir uygulama olup olmadığı veya bu rapor için toplanmadığı tüm uygulamalar. Beklenen davranışın eşlenme tablosu aşağıda verilmiştir. Rapor, genel olarak kayıt zamanından her 7 günde bir yenilenir (kiracı için haftalık yenileme değil). Bu yenileme döneminin tek istisnası, her 24 saatte bir toplanan Win32 uygulamaları için Intune yönetim uzantısı aracılığıyla toplanan uygulama bilgileri olur.

## <a name="monitor-discovered-apps-with-intune"></a>Bulunan uygulamaları Intune ile izleme

Intune, kiracınızdaki Intune 'A kayıtlı cihazlarda algılanan uygulamaların toplanmış bir listesini sağlar.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde, **istemci uygulamaları** > **bulunan uygulamalar**' ı seçin.

>[!NOTE]
>**Bulunan uygulamalar dikey penceresinden** **dışarı aktar** ' i seçerek bulunan uygulamalar listesini bir. csv dosyasına dışarı aktarabilirsiniz.
>
>Bulunan Win32 uygulamaları için şu anda toplam sayım yok. Bu tür veriler yalnızca cihaz başına temelinde görüntülenebilir.

Intune, kiracınızdaki ayrı bir cihaz için bulunan uygulamaların listesini de sağlar.

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. Intune bölmesinde, **cihazlar** > **tüm cihazlar**' ı seçin.
3. Cihaz seçin.
4. Bu cihaza yönelik algılanan uygulamaları görüntülemek için **izleyici** bölümünde **bulunan uygulamalar** ' ı seçin.

## <a name="details-of-discovered-apps"></a>Bulunan uygulamaların ayrıntıları

Aşağıdaki liste, uygulama platformu türünü, kişisel cihazlar için izlenen uygulamaları, şirkete ait cihazlar için izlenen uygulamaları ve yenileme döngüsünü sağlar. Intune tarafından desteklenen uygulama türleri hakkında daha fazla bilgi için bkz. [Microsoft Intune Içindeki uygulama türleri](apps-add.md#app-types-in-microsoft-intune).

| Platfveyam | Kişiye ait cihazlar için | Şirkete ait cihazlar için | Döngü süresi |
|------------------------------------------------------------------------|----------------------------------|--------------------------------------------------|---------------------------------------|
| Windows 10 (Win32 uygulamaları) NOTE: cihazda [Intune yönetim uzantısı gerekir](intune-management-extension.md) | Uygulanamaz | Program Ekle Kaldır listesinde bulunan tüm Win32 uygulamaları | Cihaz kaydından her 24 saatte bir |
| Windows 10 (modern uygulamalar) | Yalnızca yönetilen modern uygulamalar | Cihazda yüklü tüm modern uygulamalar | Her 7 günde bir cihaz kaydı |
| Windows 8.1 | Yalnızca yönetilen uygulamalar | Yalnızca yönetilen uygulamalar | Her 7 günde bir cihaz kaydı |
| Windows Phone 8 | Yalnızca yönetilen uygulamalar | Yalnızca yönetilen uygulamalar | Her 7 günde bir cihaz kaydı |
| Windows RT | Yalnızca yönetilen uygulamalar | Yalnızca yönetilen uygulamalar | Her 7 günde bir cihaz kaydı |
| iOS | Yalnızca yönetilen uygulamalar | Cihazda yüklü tüm uygulamalar | Her 7 günde bir cihaz kaydı |
| Mac OS | Cihazda yüklü tüm uygulamalar | Cihazda yüklü tüm uygulamalar | Her 7 günde bir cihaz kaydı |
| Android | Yalnızca yönetilen uygulamalar | Cihazda yüklü tüm uygulamalar | Her 7 günde bir cihaz kaydı |
| Android Kurumsal | Yalnızca yönetilen uygulamalar | Yalnızca Iş profilinde yüklü olan uygulamalar | Her 7 günde bir cihaz kaydı |

> [!NOTE]
> Windows 10 karma Azure AD 'ye katılmış cihazlar Configuration Manager içindeki uygulama yönetimi iş yükünde gösterildiği gibi, şu anda uygulama envanterini yukarıdaki zamanlamaya göre Intune yönetim uzantısı (IME) aracılığıyla toplamamaktadır. Bu sorunu azaltmak için, IME 'nin cihaza yüklenebilmesi için Configuration Manager içindeki uygulama yönetimi iş yükünün Intune 'a geçiş yapması gerekir (Win32 envanter ve PowerShell dağıtımı için IME gereklidir). Bu davranıştaki tüm değişikliklerin veya güncelleştirmelerin [geliştirme](../fundamentals/in-development.md) ve [/veya yenilikler](../fundamentals/whats-new.md)' de duyurulduğunu unutmayın.

Bulunan uygulamaların sayısı uygulama yükleme durumu sayısıyla eşleşmeyebilir. Tutarsızlıkların olası nedenleri:

- Yüklü yönetilen uygulamada bir hedefleme değişikliği, durum dikey penceresindeki yükleme sayısının azalmasına neden olabilir ama algılanan uygulamalarda bildirilmeye devam eder.
- Kiracıda aynı uygulamanın birden çok örneğinin hedeflenmesi, kullanıcı veya cihazların olası örtüşmesi nedeniyle farklı sayım sonuçları verebilir. Uygulamanın her örneği örtüşen kullanıcıları sayar ama bulunan uygulamaların yinelenen sayımları ortaya çıkar.
- Bulunan uygulamalarla uygulama durumu farklı zaman çerçevelerinde toplanır ve bu da uygulama sayılarında tutarsızlığa neden olabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune içindeki uygulama türleri](apps-add.md#app-types-in-microsoft-intune)
- [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md)
