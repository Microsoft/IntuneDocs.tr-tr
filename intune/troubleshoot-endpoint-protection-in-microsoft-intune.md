---
title: Microsoft Intune’da uç nokta koruması sorunlarını giderme | Microsoft Docs
description: Microsoft Intune Endpoint Protection’ı kullanarak sorunları çözün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
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
ms.openlocfilehash: ec655a53018c2e45d1cb771c1ce9c0aad376b2b1
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040162"
---
# <a name="troubleshoot-endpoint-protection-in-intune"></a>Intune’da Endpoint Protection sorunlarını giderme

Uç nokta koruması kullanırken karşılaşabileceğiniz sorunları çözmek için bu bilgileri kullanın. Ayrıca [Windows Defender AV ile sorun gidermek için olay günlüklerini ve hata kodlarını gözden geçirebilirsiniz](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](get-support.md).

### <a name="error-messages"></a>Hata iletileri
Bu bölüm, aşağıdaki hata ve uyarılarla ilgili olası nedenler ve çözümleri açıklamaktadır.

|Durum öğesi|Olası nedenler|Olası çözümler|
|---------------|--------------------|-----------------------|
|**Endpoint Protection altyapısı kullanılamıyor**|Intune Endpoint Protection altyapısı bozuk veya silinmiş.|Intune Endpoint Protection altyapısı bozuksa, yazılımı güncelleştirmeyi veya yeniden yüklemeyi deneyebilirsiniz.<br /><br />Bir güncelleştirmeyi hemen uygulamak için, Endpoint Protection istemci yazılımında **Güncelleştir**'i seçin (yönetilen bilgisayarlarda görev çubuğunda bulunur).<br /><br />Altyapı güncelleştirilemiyorsa, Endpoint Protection altyapısını yeniden yüklemeniz gerekir.<br /><br />Yönetilen bilgisayarda Denetim Masası'nda yüklü programlar listesinde, **Microsoft Intune Endpoint Protection Aracısı**'nı bulun ve uygulamayı kaldırın.<br /><br />Sonraki güncelleştirme eşitlemesinde, Microsoft Online Management Güncelleştirme Yöneticisi eksik programı algılar ve zamanlanan yükleme sırasında yeniden yükler.|
|**Endpoint Protection devre dışı**|Intune uç nokta koruması, bir yönetici tarafından yapılandırma profili kullanılarak veya yönetilen bilgisayardaki bir kullanıcı tarafından devre dışı bırakılmış.|Uç nokta korumasını etkinleştirin. Intune’da [uç nokta koruması ayarları ekleme](endpoint-protection-configure.md)’ye veya [şirket kaynaklarına erişmek için Windows Defender’ı açma](/intune-user-help/turn-on-defender-windows)’ya bakın.|
|**Gerçek zamanlı koruma devre dışı**|Gerçek zamanlı koruma, bir yönetici tarafından profil kullanılarak veya yönetilen bilgisayardaki bir kullanıcı tarafından devre dışı bırakılmış.|Uç nokta korumasını etkinleştirin. Intune’da [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus)’ya veya [şirket kaynaklarına erişmek için gerçek zamanlı korumayı açma](/intune-user-help/turn-on-defender-windows)’ya bakın. |
|**İndirme taraması devre dışı**|İndirme taraması, bir yönetici tarafından profil kullanılarak veya yönetilen bilgisayardaki bir kullanıcı tarafından devre dışı bırakılmış.|Taramayı etkinleştirin. Intune’da [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus)’ya veya [şirket kaynaklarına erişmek için gerçek zamanlı korumayı açma](/intune-user-help/turn-on-defender-windows)’ya bakın. |
|**Dosya ve program etkinliği izleme devre dışı**|Dosya ve program etkinliği izleme, bir yönetici tarafından profil kullanılarak veya yönetilen bir bilgisayardaki bir kullanıcı tarafından devre dışı bırakılmış.|Dosya ve program etkinliğini etkinleştirin. Intune’da [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus)’ya veya [şirket kaynaklarına erişmek için gerçek zamanlı korumayı açma](/intune-user-help/turn-on-defender-windows)’ya bakın. |
|**Davranış izleme devre dışı**|Davranış izleme, yönetici tarafından profil kullanılarak veya yönetilen bilgisayardaki bir kullanıcı tarafından devre dışı bırakılmış.|Davranış izlemeyi etkinleştirin. Intune’da [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus)’ya veya [şirket kaynaklarına erişmek için gerçek zamanlı korumayı açma](/intune-user-help/turn-on-defender-windows)’ya bakın. |
|**Betik taraması devre dışı**|Betik taraması, yönetici tarafından profil kullanılarak veya yönetilen bilgisayardaki bir kullanıcı tarafından devre dışı bırakıldı.|Betik taramasını etkinleştirin. Intune’da [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus)’ya veya [şirket kaynaklarına erişmek için gerçek zamanlı korumayı açma](/intune-user-help/turn-on-defender-windows)’ya bakın. |
|**Ağ Denetleme Sistemi devre dışı**|community edition community edition Ağ İnceleme Sistemi, bir yönetici tarafından profil kullanılarak veya yönetilen bir bilgisayardaki bir kullanıcı tarafından devre dışı bırakıldı.|Ağ İnceleme Sistemi’ni (NIS) etkinleştirin. Intune’da [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus)’ya veya [şirket kaynaklarına erişmek için gerçek zamanlı korumayı açma](/intune-user-help/turn-on-defender-windows)’ya bakın. |
|**Kötü amaçlı yazılım tanımları güncel değil**|Bilgisayarın İnternet bağlantısı uzun bir süre boyunca kesilmiş ve kötü amaçlı yazılım tanımları henüz güncelleştirilmemiş olabilir. Bu durum, bilgisayardaki kötü amaçlı yazılım tanımları 14 gün veya daha uzun süre güncel olmadığında görüntülenir.|Kötü amaçlı yazılım tanımları güncel değilse, tanımları [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus) kullanarak güncelleştirebilirsiniz.|
|**Tam tarama süresi doldu**|14 gün boyunca bir tam tarama yapılmadı. Bu durum bir tam tarama sırasında bilgisayarın yeniden başlatılmasıyla oluşabilir.|Bir tam tarama geciktiyse, tek seferlik bir tam tarama çalıştırabilir veya yinelenen tam taramalar zamanlayabilirsiniz. Bkz. [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Hızlı taramanın süresi doldu**|14 gün boyunca bir hızlı tarama yapılmadı. Bu durum bir hızlı tarama sırasında bilgisayarın yeniden başlatılmasıyla oluşabilir.|Bir hızlı tarama geciktiyse, tek seferlik bir hızlı tarama çalıştırabilir veya yinelenen hızlı taramalar zamanlayabilirsiniz. Bkz. [Windows Defender Virüsten Koruma](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Başka bir uç nokta koruma uygulaması çalışıyor**|Başka bir uç nokta koruma uygulaması çalışıyor ve bilgisayarın sistem durumu iyi.|Varsayılan olarak, başka bir uç nokta koruma uygulaması yüklüyse ve Intune bu uygulamayı algılarsa cihaz kararsız duruma gelebilir.|

### <a name="next-steps"></a>Sonraki adımlar
Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](get-support.md).
