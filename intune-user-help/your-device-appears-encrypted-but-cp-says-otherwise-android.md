---
title: Android cihazınız şifrelenmiş görünüyor | Microsoft Docs
description: Uygulamasında, Şirket portalı ve Microsoft Intune şifreleme durumu çözümleyin
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8c35400f37ab4ddee275cf23f7a50f280322e3b
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61501587"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Aksi takdirde cihaz şifrelenir, ancak uygulamalar söyleyin

Şirket portalı veya Microsoft Intune uygulama Cihazınızı şifreli değildir, ancak, bu makaledeki adımları deneyin olup olmadığını derseniz.  

## <a name="add-a-startup-pin"></a>Başlangıç PIN’i ekleme

Belirli Android cihazları, cihazınızın güvenli olduğundan emin olmak için bir başlangıç PIN’i oluşturmayı gerektirir. Bu ayarın konum, cihazınızın içinde olacaktır **ayarları** uygulama. Ayar konumunu ve adını gösterebilir. Örneğin, Samsung Galaxy S7'de, ayar olarak adlandırılır **güvenli başlatma**. Etkinleştirmediğiniz ve geçiş kodu oluşturmak için Git **ayarları** > **kilit ekranı ve güvenlik** > **güvenli başlatma**.  

## <a name="encrypt-the-entire-device"></a>Tüm cihazı şifreleyin

Bu bölüm, yalnızca Şirket portalı uygulaması için geçerlidir. Bazı cihazlar size, tüm cihazı veya yalnızca kullanılan alanı şifreleme seçeneği sunar. Tüm cihazı şifreleme seçeneğini seçin. Yalnızca kullanılan alanı şifreleyin seçtiyseniz:

1. [Bu cihazı şirket Portalı'ndan kaldırdığınızda](unenroll-your-device-from-intune-android.md).
2. Kullanılan alanın şifresini çözün.  
3. Cihazın tamamını şifreleyin.  
4. Cihazı yeniden kaydedin.  

## <a name="downgrade-your-version-of-android"></a>Android sürümünüzü düşürme

Bu bölüm, yalnızca Şirket portalı uygulaması için geçerlidir. Cihazınız Android 6.0 ve üzeri düşürme seçeneği sunuyorsa, bunu yapın. Cihazınızın sürümünü düşürmeyi denediğinizde, veri kaybı riski yoktur. Aksi takdirde, bu sorunu çözmek için şirketinizin destek birimine başvurmanızı öneririz. Şirketinizin destek biriminin iletişim bilgilerini edinin [Şirket portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980).  

## <a name="specific-manufacturer-issues"></a>Belirli üretici sorunları

Bazı sürüm 7.0 ve üzeri Android cihazlar, belirli Android platformu standartlarına uymayan yollarla veri şifreler. Bu cihazlar, yeni olsalar dahi şifreli görünebilir. Intune, bu cihazların şifreleme yönteminin cihaz bilgilerini riske attığını algılar. Bu risk temel olarak cihaza fiziksel erişimi olan kötü amaçlı kullanıcılardan kaynaklanır.

> [!Note]
> Microsoft, sınama aşamasında ya da kullanıcıların bize bildirdiği tüm sorunları ele almak için üreticiler ile birlikte çalışır. Yeni bilgiler mevcut oldukça bu makaleyi güncelleştireceğiz. 

## <a name="update-known-devices"></a>Bilinen cihazlar güncelleştir   

Cihazınızı en son Android sürümüne güncelleştirmediyseniz, cihazınızın Git **ayarları** seçin **güncelleştirme**. Bunları güncelleştirilene kadar bu cihazların uyumlu görünmeyebilir.  

- Huawei Honor 8
- Huawei P9

## <a name="known-devices-that-always-appear-encrypted"></a>Her zaman şifreli görünür bilinen cihazlar  
Aşağıdaki cihazlar, her zaman şifreli görünür ve şirket kaynaklarına erişmek için kullanılamaz. Şirket kaynaklarına erişmek için farklı bir cihaz kullanmanız gerekir.  

- Huawei Mate 8
- OPPO cihazları
- Vivo cihazları
- Xiaomi Mi smartphones  

## <a name="next-steps"></a>Sonraki adımlar   
Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.  