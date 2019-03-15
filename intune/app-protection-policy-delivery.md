---
title: Undertastand uygulama koruma İlkesi teslim ve zamanlama
titleSuffix: Microsoft Intune
description: Değişiklikleri son kullanıcı cihazlarınızda görüntülendiğinde anlamak uygulama koruma ilkeleri için farklı dağıtım windows öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ec111319-7e02-434f-946b-88647726bf1a
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 879ccc890a727ddbd911a2b42266d205a1a293c5
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57389021"
---
# <a name="understand-app-protection-policy-delivery-timing"></a>Uygulama koruma İlkesi teslim zamanlamasını anlama

Değişiklikleri son kullanıcı cihazlarınızda görüntülendiğinde anlamak uygulama koruma ilkeleri için farklı dağıtım windows öğrenin.

## <a name="delivery-timing-summary"></a>Teslim zamanlamasını özeti

Uygulama koruma İlkesi teslim lisans durumu ve kullanıcılarınızın Intune hizmeti kaydını bağlıdır.  

|    Kullanıcı durumu    |    Uygulama koruma davranışı     |    Yeniden deneme aralığı (bkz. Not)    |    Bu neden gerçekleşir?    |
|-----------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|    Kiracı eklenmedi    |    Sonraki yeniden deneme zaman aralığını bekler.  Uygulama koruma kullanıcı için etkin değil.    |    24 saat    |    Kiracınız için Intune kurulmadı olduğunda gerçekleşir.    |
|    Kullanıcı lisanslı değil     |    Sonraki yeniden deneme zaman aralığını bekler.  Uygulama koruma kullanıcı için etkin değil.     |    12 saat - Android cihazlarda ancak, Intune uygulama SDK'sı sürüm 5.6.0 bu aralığı gerektirir veya üzeri. Aksi takdirde Andriod cihazlar için aralığı 24 saattir.   |    Kullanıcının Intune lisansı değil oluşur.    |
|    Kullanıcı tarafından atanan uygulama koruma ilkeleri yok    |    Sonraki yeniden deneme zaman aralığını bekler.  Uygulama koruma kullanıcı için etkin değil.    |    12 saat        |    Uygulama ayarları kullanıcıya atadığınız değil oluşur.    |
|    Kullanıcı için Intune MAM başarıyla kaydedildi    |    Uygulama koruma İlkesi ayarları uygulanır.    Güncelleştirmeler yeniden deneme aralığına göre yapılır    |    Intune hizmet, kullanıcı yükü göre tanımlanır.    Genellikle 30 dakika.     |    Kullanıcı MAM yapılandırması için Intune hizmetine başarıyla kaydettiği zaman oluşur.    |

> [!NOTE]
> Yeniden deneme aralıkları uygulaması başlatılır yani gerçekleşmesi için etkin uygulaması kullanımı gerektirir ve kullanımda olabilir.  Yeniden deneme aralığı 24 saattir ve kullanıcı uygulamayı başlatmak için 48 saat bekler, uygulama koruma istemci 48 saat yeniden deneyecek.

## <a name="handling-network-connectivity-issues"></a>İşleme ağ bağlantısı sorunları

Kullanıcı kaydı ağ bağlantısı sorunları nedeniyle başarısız olduğunda bir hızlandırılmış yeniden deneme aralığı kullanılır.  Uygulama koruması istemci başarılı bir bağlantı yapılır ya da aralığı 60 dakika ulaşana kadar gittikçe daha uzun aralıklarla yeniden deneyecek.  İstemci 60 dakikalık aralıklarla başarılı bir bağlantı kurulana kadar yeniden denemeye devam eder. Ardından, istemci kullanıcı durumuna göre standart yeniden deneme aralığını döndürür.

## <a name="next-steps"></a>Sonraki adımlar

[Kullanıcılar cihazlarını Intune'a kaydedebilmesi için kullanıcılara lisans atama](licenses-assign.md)

