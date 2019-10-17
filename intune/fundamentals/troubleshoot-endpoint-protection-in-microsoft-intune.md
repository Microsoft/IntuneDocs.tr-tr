---
title: Microsoft Intune-Azure 'da ortak uç nokta koruma iletileri | Microsoft Docs
description: Microsoft Intune 'da Endpoint Protection ve Windows Defender kullanırken ve sorunlarını giderirken ortak iletilere ve olası çözüme bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/26/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e34e1cb30469593c8ec9e756659ad03589ae38bc
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509784"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Microsoft Intune uç nokta koruma sorunları ve olası çözümleri

Bu makalede, bazı hatalar ve uyarılar için olası nedenler ve çözümler listelenmektedir ve açıklanmaktadır. Endpoint Protection kullanırken sorunları çözmeye yardımcı olması için bu bilgileri kullanın.

## <a name="windows-defender-error-codes"></a>Windows Defender hata kodları

[Windows Defender av ile ilgili sorunları gidermek](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)için olay günlüklerini ve hata kodlarını gözden geçirin.

## <a name="common-intune-errors-and-possible-resolutions"></a>Yaygın Intune hataları ve olası çözümleri

### <a name="endpoint-protection-engine-unavailable"></a>Endpoint Protection altyapısı kullanılamıyor

**Olası neden**: Intune Endpoint Protection altyapısı bozuk veya silinmiş.

**Olası çözümler**:

- Endpoint Protection bozuksa veya güncelleştirmez, sonra programı güncelleştirin veya yeniden yükleyin.
- Anında güncelleştirmeye zorla. Endpoint Protection istemci programında (muhtemelen görev çubuğunda) **Güncelleştir**' i seçin.
- Denetim Masası > Programlar ' da **Microsoft Intune Endpoint Protection Aracısı**' nı seçin. Uygulamayı kaldırın.
- Sonraki güncelleştirme eşitlemesinde, Microsoft Online Management Güncelleştirme Yöneticisi eksik programı algılar ve zamanlanan yükleme sırasında yeniden yükler.

### <a name="features-are-disabled"></a>Özellikler devre dışı

Bazı özelliklerin devre dışı bırakıldığını belirten bir ileti alabilirsiniz. Intune Endpoint Protection veya Windows Defender bir yapılandırma profili kullanan bir yönetici tarafından devre dışı bırakılmışsa bu iletiler gerçekleşebilir. Veya, cihazdaki bir son kullanıcı tarafından devre dışı bırakıldı. Olası iletiler:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Olası çözümler**: Bu özellikleri etkinleştirin. Rehberlik için bkz.:

- [Endpoint Protection ayarları ekle](../protect/endpoint-protection-configure.md)
- [Windows Defender virüsten koruma](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)
- [Son kullanıcılar: şirket kaynaklarına erişmek için gerçek zamanlı korumayı etkinleştirin](/intune-user-help/turn-on-defender-windows)

### <a name="malware-definitions-out-of-date"></a>Kötü amaçlı yazılım tanımları güncel değil

Bu durum, cihazdaki kötü amaçlı yazılım tanımlarının 14 gün veya daha fazla zaman aşımına uğrar olduğunu gösterir. Örneğin ileti, cihazın Internet bağlantısı kesildiğinde veya kötü amaçlı yazılım tanımlarının güncel olup olmadığını gösterebilir.

**Olası çözümler**: kötü amaçlı yazılım tanımları güncel değilse, tanımları [Windows Defender virüsten koruma](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)kullanarak güncelleştirin.

### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Tam Tarama süresi doldu veya hızlı tarama süresi doldu

14 gün boyunca tam tarama veya hızlı tarama tamamlanmadı. Bu senaryo, tam tarama sırasında cihaz yeniden başlatılırsa meydana gelebilir.

**Olası çözümler**: Taramanın süresi dolduysa, bir kerelik tarama çalıştırabilir veya yinelenen taramalar zamanlayabilirsiniz. Bkz. [Windows Defender Virüsten Koruma](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="another-endpoint-protection-application-running"></a>Başka bir uç nokta koruma uygulaması çalışıyor

Başka bir uç nokta koruma uygulaması çalışıyor ve cihaz sağlıklı.

**Olası çözümler**: başka bir uç nokta koruma uygulaması yüklüyse ve Intune bu uygulamayı algılarsa, cihaz kararsız hale gelebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Microsoft 'un destek yardımına](get-support.md)ulaşın veya [topluluk forumlarını](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune)kullanın.
