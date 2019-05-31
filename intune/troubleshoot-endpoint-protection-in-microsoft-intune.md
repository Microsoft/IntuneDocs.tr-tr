---
title: Genel endpoint protection iletileri Microsoft Intune - Azure | Microsoft Docs
description: "Bkz: Genel iletileri ve kullanarak ve endpoint protection ve Windows Defender'ın Microsoft Intune sorun giderme olası çözüm."
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4f749ab85d283ed9743d227476f8229dc1cf7c3
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402640"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Uç nokta koruma sorunları ve olası çözümlerini Microsoft Intune

Bu makale, listeler ve olası nedenler ve çözümler bazı hatalar ve Uyarılar için açıklar. Endpoint protection'ı kullanırken, sorunların çözümüne yardımcı olmak için bilgileri kullanın.

## <a name="windows-defender-error-codes"></a>Windows Defender hata kodları

Olay Günlükleri ve hata kodları inceleyin [Windows Defender AV ile ilgili sorunları giderme](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Genel Intune hataları ve olası çözümleri

#### <a name="endpoint-protection-engine-unavailable"></a>Endpoint Protection altyapısı kullanılamıyor

**Olası neden**: Intune Endpoint Protection altyapısı bozuk veya silinmiş.

**Olası çözümler**:

- Endpoint protection bozuk veya güncelleştirme kalmaz, ardından güncelleştirin veya program yeniden yükleyin.
- Bir güncelleştirmeyi hemen uygulamak. (Büyük olasılıkla çubuğunda) uç nokta koruma istemci programında seçin **güncelleştirme**.
- Denetim Masası'ndaki > Programlar, **Microsoft Intune Endpoint Protection Aracısı**. Uygulamayı kaldırın.
- Sonraki güncelleştirme eşitlemesinde, Microsoft Online Management Güncelleştirme Yöneticisi eksik programı algılar ve zamanlanan yükleme sırasında yeniden yükler.

#### <a name="features-are-disabled"></a>Özellikleri devre dışı bırakılır

Bazı özellikler devre dışı belirten bir ileti alabilirsiniz. Intune endpoint protection veya Windows Defender yapılandırma profili kullanarak bir yönetici tarafından devre dışı bırakılırsa, bu iletileri gerçekleşebilir. Veya cihazdaki bir son kullanıcı tarafından devre dışı. Olası iletileri:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Olası çözümler**: Bu özellikleri sağlar. Yönergeler için bkz:

- [Endpoint protection ayarları ekleme](endpoint-protection-configure.md)
- [Windows Defender virüsten koruma](device-restrictions-windows-10.md#windows-defender-antivirus)
- [Son kullanıcılar: Gerçek zamanlı korumayı şirket kaynaklarına erişim](/intune-user-help/turn-on-defender-windows)

#### <a name="malware-definitions-out-of-date"></a>Kötü amaçlı yazılım tanımları güncel değil

Bu durum, cihazdaki kötü amaçlı yazılım tanımları 14 gün veya daha eski olduğunda gösterir. Örneğin, cihazın Internet bağlantısı kesildiğinde veya kötü amaçlı yazılım tanımlarını güncel ileti görüntülenebilir.

**Olası çözümler**: Kötü amaçlı yazılım tanımları güncel değilse kullanarak tanımları güncelleştirme [Windows Defender virüsten koruma](device-restrictions-windows-10.md#windows-defender-antivirus).

#### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Tam tarama süresi doldu veya hızlı tarama süresi doldu

14 gün boyunca bir tam tarama veya hızlı tarama tamamlandı edilmemiş. Tam tarama sırasında cihaz yeniden başlatılırsa bu senaryo gerçekleşebilir.

**Olası çözümler**: Bir taramanın süresi dolduysa, tek seferlik bir tarama çalıştırabilir veya yinelenen taramalar zamanlayabilirsiniz. Bkz. [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus).

#### <a name="another-endpoint-protection-application-running"></a>Başka bir uç nokta koruma uygulaması çalışıyor

Başka bir uç nokta koruma uygulaması çalışıyor ve aygıt iyi durumda.

**Olası çözümler**: Başka bir uç nokta koruma uygulaması yüklüyse ve Intune bu uygulamayı algılarsa, cihaz kararsız hale gelebilir.

## <a name="next-steps"></a>Sonraki adımlar

Alma [destekleyen Microsoft gelen Yardım](get-support.md), veya [topluluk forumları](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
