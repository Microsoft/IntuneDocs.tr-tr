---
title: "Intune ile cihazları yönetme"
titleSuffix: Intune on Azure
description: "Intune ile yönettiğiniz cihazları görmeyi ve bu cihazlar üzerinde çeşitli işlemler yapmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Microsoft Intune cihaz yönetimi nedir?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazlar** iş yükü, yönettiğiniz cihazlarla ilgili bilgi sahibi olmanızı sağlar ve bu cihazlar üzerinde uzak görevler gerçekleştirmenize olanak tanır. İş yüküne erişmek için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.

Artık aşağıdaki işlemleri yapabilirsiniz:

- [Cihaz envanterini görüntüleme](device-inventory.md)
- Uzak cihaz eylemleri gerçekleştirme:
    - [Şirket verilerini kaldır](device-company-data-remove.md) 
    - [Fabrika sıfırlaması](device-factory-reset.md)
    - [Uzaktan kilitleme](device-remote-lock.md)
    - [Geçiş Kodunu Sıfırla](device-passcode-reset.md)
    - [Etkinleştirme Kilidini Atla](device-activation-lock-bypass.md)
    - [Fresh Start](device-fresh-start.md)
    - [Kayıp modu](device-lost-mode.md)
    - [Cihazı bul](device-locate.md)
    - [Yeniden başlat](device-restart.md)
    - [Windows 10 PIN sıfırlama](device-windows-pin-reset.md)
    - [Android için uzaktan denetim](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>Her cihaz eylemi için destek

Her bir eylem tarafından desteklenen cihaz platformlarını anlamak için aşağıdaki tabloyu kullanın.

|||||||
|-|-|-|-|-|-|
|Cihaz eylemi|Windows|Windows Phone|iOS|Mac OS|Android|
|**Şirket verilerini kaldır**|Evet|Evet|Evet|Evet|Evet|
|**Fabrika sıfırlaması**|Windows 8.1 ve üzeri (EAS ile yönetilen cihazlar değil)|Evet|Evet|Hayır|Android for Work desteklenmiyor|
|**Sil**|Evet|Evet|Evet|Evet|Evet|
|**Uzaktan kilitleme**|Hayır|Windows Phone 8.1 ve üzeri|Evet|Hayır|Evet|
|**Geçiş Kodunu Sıfırla**|Hayır|Windows Phone 8.1’den Windows 10 Creators güncelleştirmesi Azure AD’ye katılmadı, Windows 10 Creators Update ve üzeri - hepsi|Evet|Hayır|Android 7 öncesi için Android for Work desteklenmiyor|
|**Yeni geçiş kodu** (Windows 10 cihazlar için)|Hayır|Windows 10 Creators Update ve üzeri (Azure AD’ye katılmış)|Hayır|Hayır|Android for Work desteklenmiyor|
|**Etkinleştirme Kilidini Atla**|Hayır|Hayır|Yalnızca şirkete ait cihazlar|Hayır|Hayır|
|**Kayıp modu**|Hayır|Hayır|iOS 9.3 ve üzeri, denetimli ve şirkete ait|Hayır|Hayır|
|**Cihazı bul**|Hayır|Hayır|Kayıp modu iOS 9.3 ve üzeri, denetimli ve şirkete ait|Hayır|Hayır|
|**Geçerli kullanıcının oturumunu kapatma**|Hayır|Hayır|iOS 9.3 ve üzeri (yalnızca paylaşılan iPad cihazlar)|Hayır|Hayır|
|**Yeniden başlat**|Windows 8.1 ve üzeri|Windows Phone 8.1 ve üzeri|Hayır|Hayır|Hayır|
|**Fresh Start**|Windows 10 Creators güncelleştirmesi ve üzeri|Hayır|Hayır|Hayır|Hayır|
|**Yeni Uzaktan Yardım oturumu**|Hayır|Hayır|Hayır|Hayır|Evet|
|**Kullanıcı kaldırma**|Hayır|Hayır|iOS 9.3 ve üzeri (yalnızca paylaşılan iPad cihazlar)|Hayır|Hayır|

## <a name="next-steps"></a>Sonraki adımlar

- Yönettiğiniz cihazlarda gerçekleştirilen eylemlerin durumunu görmek için **Cihaz Eylemleri**’ni seçin. 
![Cihaz eylemlerini izleme](./media/monitor-device-actions.png)