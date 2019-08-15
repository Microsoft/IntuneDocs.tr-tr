---
title: Android cihazınız şifrelenmiş görünüyor | Microsoft Docs
description: Şirket Portalı ve Microsoft Intune uygulamasındaki şifreleme durumunu çözümleyin
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/14/2019
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
ms.openlocfilehash: d63ecdb23b107d844c37d7a805247092116618e1
ms.sourcegitcommit: b30a2ba2b67aa2fc3421f0b2f6c5f361a0de612a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2019
ms.locfileid: "69022746"
---
# <a name="device-encrypted-but-apps-say-otherwise"></a>Cihaz şifrelendi, ancak uygulamalar bu şekilde söyleniyor

Şirket Portalı veya Microsoft Intune uygulama, cihazınızın şifrelenmediğini, ancak bunun olduğundan emin olduğunuzu düşünüyorsanız, bu makaledeki adımları deneyin.  

## <a name="add-a-startup-pin"></a>Başlangıç PIN’i ekleme

Belirli Android cihazları, cihazınızın güvenli olduğundan emin olmak için bir başlangıç PIN’i oluşturmayı gerektirir. Bu ayarın konumu cihazınızın **Ayarlar** uygulamasında olacaktır. Ayarın adı ve konumu değişebilir. Örneğin, Samsung Galaxy S7, ayar **güvenli başlangıç**olarak adlandırılır. Etkinleştirmek ve geçiş kodu oluşturmak için **Ayarlar** > **kilit ekranı ve güvenlik** > **güvenli başlangıç**' a gidin.  

## <a name="encrypt-the-entire-device"></a>Tüm cihazı şifreleyin

Bu bölüm yalnızca Şirket Portalı uygulaması için geçerlidir. Bazı cihazlar size, tüm cihazı veya yalnızca kullanılan alanı şifreleme seçeneği sunar. Tüm cihazı şifreleme seçeneğini belirleyin. Yalnızca kullanılan alanı şifrelemeyi seçtiyseniz:

1. [Bu cihazı Şirket portalı kaldırın](unenroll-your-device-from-intune-android.md).
2. Kullanılan alanın şifresini çözün.  
3. Tüm cihazı şifreleyin.  
4. Cihazı yeniden kaydedin.  

## <a name="downgrade-your-version-of-android"></a>Android sürümünüzü düşürme

Bu bölüm yalnızca Şirket Portalı uygulaması için geçerlidir. Cihazınız, Android 6,0 ve üzeri sürümlere düşürme seçeneği sunuyorsa, bunu yapın. Cihazınızı indirgemenize çalışırsanız veri kaybı riski vardır. Aksi takdirde, bu sorunu çözmek için şirketinizin destek birimine başvurmanızı öneririz. [Şirket portalı Web sitesinde](https://go.microsoft.com/fwlink/?linkid=2010980)şirketinizin destek birimine yönelik iletişim bilgilerini alın.  

## <a name="specific-manufacturer-issues"></a>Belirli üretici sorunları

Sürüm 7,0 ve üzeri sürümlerde bazı Android cihazlar, belirli Android Platform standartları ile tutarsız yollarla verileri şifreler. Bu şifreleme yöntemleri cihaz bilgilerini riske koyar. Sonuç olarak, bu cihazlar desteklenmez. 

Desteklenen Android cihazlarının ayrıntılı olmayan bir listesi için bkz. [Intune 'Da desteklenen işletim sistemleri ve tarayıcılar](https://docs.microsoft.com/intune/supported-devices-browsers#supported-samsung-knox-standard-devices)makalesi. Cihazınız listede yoksa, cihaz üreticisine başvurun veya destek sorumlunuza başvurun. 

> [!Note]
> Microsoft, test ederken veya kullanıcıların bize rapor verdiği sorunları ele almak için üreticilerle birlikte çalışmaktadır. Yeni bilgiler mevcut oldukça bu makaleyi güncelleştireceğiz. 

## <a name="update-devices"></a>Cihazları güncelleştirme   

Cihazınızı en son Android sürümüne güncelleştirmediyseniz, cihazınızın **Ayarlar** uygulamasına gidin ve **Güncelleştir**' i seçin.  

## <a name="next-steps"></a>Sonraki adımlar   
Bu bilgiler yardımcı olmadı mı? Şirketinizin destek birimine başvurun (iletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın) veya <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android ekibine</a> yazın.  
