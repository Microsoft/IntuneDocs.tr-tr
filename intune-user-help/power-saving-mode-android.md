---
title: Güç iyileştirmenin e-posta erişimini engellemesi | Microsoft Docs
description: E-postalarınızı alacağınızdan emin olmak için Android’de güç iyileştirmeyi devre dışı bırakmayı öğrenin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/07/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 663da92e11befeae1f65467e887870a52640cbeb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020580"
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a>Android’de pil iyileştirme açık olduğunda Outlook yönetilen e-postaları eşitlemez

> [!IMPORTANT]
> Konuyla ilgili rapor gönderen müşteri sayısı gittikçe arttığı için bu soruna burada değiniyoruz. Bu adımları tamamladıktan sonra sorununuz hala devam ederse yardım için [şirketinizin destek birimine](https://portal.manage.microsoft.com#HelpDeskDialog) başvurun.

Cihazınızı Intune’a kaydetmek, şirket kaynaklarına erişmenizi sağlar. En yaygın kaynaklardan biri e-posta erişimidir. Outlook ile e-postaya erişim konusunda yaşanan sorunların, güç iyileştirme açıkken meydana geldiğini gördük. Pil iyileştirme, cihazınızın olabildiğince uzun süre çalışmasını sağlamak için otomatik olarak açılabilir. Pil iyileştirme, e-postaların otomatik indirilmesini durdurmaya çalışarak size kısmen yardımcı olur.

Microsoft Intune ekibi, bu soruna bir çözüm getirmek için hızla çalışmaktadır. Cihazınızın düşük güç moduna geçmesini önlemenin bir yolu, pilinizin %30’un altına düşmemesini sağlamaktır. Düşük güç moduna girdiğinizde bu sorunla karşılaşmamak için pil iyileştirme ve güç tasarrufu ayarlarınızdan etkilenen uygulamalar listesinden Şirket Portalı ve Outlook uygulamalarını çıkarmanız gerekir.

Pek çok üretici tarafından üretilen farklı Android cihazları olduğu için her cihazda yapmanız gerekenleri adım adım anlatmamız mümkün değil. Bu eylemi yalnızca sistem ayarlarınızda gerçekleştirmeniz yeterli olabileceği gibi, üreticiye göre değişen bazı ayarlar da söz konusu olabilir. Ancak yaygın olarak kullanılan Android cihazlarda bu sorunu çözebilmeniz için aşağıda bazı örnekler sağlanmıştır.

## <a name="unmodified-android-devices"></a>Değiştirilmemiş Android cihazlar

Birçok üretici, Android cihazlarında değişiklik yapar. Bu değişiklikler cihazla etkileşiminizi değiştiren türden olabilir, örneğin temalar ve bildirimler gibi. Google, telefonlarına genellikle bu tip değişiklikler yapmaz. Örneğin, Android 7.0 veya üstü çalıştıran bir Google Pixel cihazda bu uygulamaları pil iyileştirme listesinden kaldırmak için şu adımları izlemeniz gerekir:

1. **Ayarlar**’ı açın.
2. **Pil** > **Daha fazla** > **Pil iyileştirme**’ye dokunun.
3. Aşağı oka ve sonra **İyileştirilmeyen**’e dokunun.
4. Şirket Portalı ve Outlook uygulamalarını seçin ve pil iyileştirmeyi kapatın.

## <a name="samsung-devices"></a>Samsung cihazlar

Android 7.0 ve üstü çalıştıran diğer cihaz türlerinde (Samsung cihazlar gibi) ise Outlook ve Şirket Portalı uygulamalarını pil iyileştirmeden kaldırmak için farklı adımlar izlemeniz gerekir.

1. **Ayarlar**’ı açın.
2. **Menü (…)** > **Özel erişim** > **Pil kullanımını iyileştir**’e dokunun.
3. Açılan listede **Tüm uygulamalar**’ı seçin.
4. Şirket Portalı ve Outlook uygulamalarının yanındaki geçiş tuşunu **Kapalı** durumuna getirerek pil iyileştirmeyi kapatın.

Buna ek olarak, daha eski bir Android sürüm çalıştıran Samsung cihazınız varsa bu uygulamaları güç tasarrufu modundan kaldırmak için aşağıdaki adımları takip etmeniz gerekir.

1. **Ayarlar**’ı açın.
2. **Cihaz bakımı** > **Pil** > **İzlenmeyen uygulamalar**’a dokunun.
3. **Uygulama ekle**’ye dokunun.
4. Şirket Portalı ve Outlook uygulamalarını seçin ve **Bitti**’ye dokunun.

## <a name="oneplus-devices"></a>OnePlus cihazlar

Bu ayarları bulmanın bir diğer yolu da sistem ayarlarında arama yapmaktır. Örneğin, Android 7.1.1 çalıştıran bir OnePlus 3 cihazda şu adımları izlemeniz gerekir: 

1. **Sistem Ayarları**’nı açın. 
2. **Ara** düğmesine dokunun. Bu düğme, ekranın sağ üst köşesindeki büyüteç şeklindeki semboldür. 
3. Arama kısmına **pil iyileştirme** yazın, karşınıza çıkacak **Ayarlar** ekranında **Pil İyileştirme** seçeneğini seçin. 
4. **Pil** > **Pil iyileştirme**’ye dokunun.
5. Şirket Portalı ve Outlook uygulamalarını seçin ve **İyileştirme**’ye tıklayın. **Bitti**’ye dokunun.

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın.
