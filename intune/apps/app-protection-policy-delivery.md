---
title: Uygulama koruma ilkesi teslimini ve zamanlamasını anlama
titleSuffix: Microsoft Intune
description: Son Kullanıcı cihazlarınızda değişikliklerin ne zaman görünmeli olduğunu anlamak için, uygulama koruma ilkelerinin farklı dağıtım pencerelerini öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ec111319-7e02-434f-946b-88647726bf1a
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7460d5ccf046b25510d798c3a7ed4aa9ecd87a8a
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72499170"
---
# <a name="understand-app-protection-policy-delivery-timing"></a>Uygulama koruma Ilkesi teslim zamanlamasını anlama

Son Kullanıcı cihazlarınızda değişikliklerin ne zaman görünmeli olduğunu anlamak için, uygulama koruma ilkelerinin farklı dağıtım pencerelerini öğrenin.

## <a name="delivery-timing-summary"></a>Teslim zamanlaması Özeti

Uygulama koruma ilkesi teslimi, kullanıcılarınız için lisans durumuna ve Intune hizmeti kaydına bağlıdır.  

|    Kullanıcı durumu    |    Uygulama koruma davranışı     |    Yeniden deneme aralığı (bkz. nota bakın)    |    Bunun nedeni nedir?    |
|-----------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|    Kiracı eklendi değil    |    Sonraki yeniden deneme aralığı için bekleyin.  Uygulama koruması Kullanıcı için etkin değil.    |    24 saat    |    Intune için kiracınızı kurmayan bir durum oluşur.    |
|    Kullanıcı lisanslı değil     |    Sonraki yeniden deneme aralığı için bekleyin.  Uygulama koruması Kullanıcı için etkin değil.     |    12 saat, ancak Android cihazlarda bu Aralık, Intune uygulama SDK 'Sı sürüm 5.6.0 veya üstünü gerektirir. Aksi takdirde, Androd cihazları için Aralık 24 saattir.   |    Kullanıcı Intune için lisanslanmadığı zaman gerçekleşir.    |
|    Kullanıcı, uygulama koruma Ilkeleri atamadı    |    Sonraki yeniden deneme aralığı için bekleyin.  Uygulama koruması Kullanıcı için etkin değil.    |    12 saat        |    Kullanıcıya uygulama ayarları atamadığınızda gerçekleşir.    |
|    Kullanıcı Intune MAM için başarıyla kaydedildi    |    Uygulama koruması her ilke ayarı için uygulanır.    Güncelleştirmeler, yeniden deneme aralığına göre yapılır    |    Intune hizmeti, Kullanıcı yüküne göre tanımlanır.    Genellikle 30 dakika.     |    Kullanıcı MAM yapılandırması için Intune hizmetine başarıyla kaydolursa oluşur.    |

> [!NOTE]
> Yeniden deneme aralıkları etkin uygulama kullanımını gerektirebilir, bu da uygulamanın başlatıldığı ve kullanımda olması anlamına gelir.  Yeniden deneme aralığı 24 saattir ve Kullanıcı uygulamayı başlatmak için 48 saat bekliyorsa, uygulama koruma istemcisi 48 saat sonra yeniden dener.

## <a name="handling-network-connectivity-issues"></a>Ağ bağlantısı sorunlarını işleme

Ağ bağlantısı sorunları nedeniyle Kullanıcı kaydı başarısız olduğunda, hızlandırılmış bir yeniden deneme aralığı kullanılır.  Zaman aralığı 60 dakikaya ulaşana veya başarılı bir bağlantı yapılıncaya kadar, uygulama koruma istemcisi giderek daha uzun aralıklarla yeniden dener.  İstemci daha sonra başarılı bir bağlantı yapılıncaya kadar 60 dakikalık aralıklarla yeniden denemeye devam eder. Ardından, istemci, Kullanıcı durumuna göre standart yeniden deneme aralığına geri döner.

## <a name="next-steps"></a>Sonraki adımlar

[Cihazlarını Intune’a kaydedebilmeleri için kullanıcılara lisans atama](../fundamentals/licenses-assign.md)

