---
title: "Intune yönetilen iOS cihazları yedekten geri yükleme"
description: "Son kullanıcılara, cihazlarını yedekten geri yükledikten sonra yeniden kaydetme yönergeleri sağlar."
keywords: "geri yükleme, yönetilen, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7fc99a944000a8d5ecfc09ebc2e956e7c0f201c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="restore-intune-managed-ios-devices-from-backup"></a>Intune yönetilen iOS cihazları yedekten geri yükleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bir kullanıcının yeni bir cihaz alması gibi, siz veya kullanıcılarınızın bir iOS cihazı yedekten geri yüklemesini gerektirecek durumlar olacaktır. Bu konu, cihaz geri yüklendikten sonra Intune yönetimini ayarlamak için atmanız gereken ek adımları açıklar.

## <a name="restoring-backups-onto-the-same-device"></a>Yedekleri aynı cihaza geri yükleme

Yedek, aynı cihaza geri yükleniyorsa, cihazdaki kayıt durumu da geri yüklenir. Başka bir işlem yapmaya gerek yoktur.

## <a name="restoring-backups-onto-different-devices"></a>Yedekleri farklı cihazlara geri yükleme

Yedek, farklı bir cihaza geri yükleniyorsa, kayıt durumu yeni cihazda otomatik olarak geri yüklenmez. Kullanıcıların [iOS cihazlarını Intune’a kaydetmek](/intune-user-help/enroll-your-device-in-intune-ios) için Şirket Portalı uygulamasının uygulama sürümü 2.1.22 veya üzeri sürümlerdeki standart kayıt adımlarını izlemesi gerekir.

> [!NOTE]
> Koşullu erişim ilkeleriyle son kullanıcılarınızı hedefliyorsanız, yeniden kaydolduklarında şirket e-postasına erişemezler.

> [!TIP]
> Kullanıcılarınız için örnek bir iletişim aşağıdaki gibi olabilir: Yeni cihazınızı kaydetmek için Şirket Portalı uygulamasının 2.1.22 veya üzeri bir sürümde olduğundan emin olun. Sürümü denetlemek için Şirket Portalı uygulamasını açın, sağ üstteki Menü düğmesine dokunun ve ardından Hakkında’ya dokunun. Önceki bir sürüm kullanıyorsanız, Şirket Portalı uygulamasından çıkın ve App Store’u açın. Sağ alt köşedeki Güncelleştirmeler düğmesine dokunun ve ardından listedeki Şirket Portalı öğesinin yanındaki Güncelleştir düğmesine dokunun. Güncelleştirme tamamlandıktan sonra, Şirket Portalı uygulamasını başlatın ve [iOS cihazınızı Intune'a kaydedin](/intune-user-help/enroll-your-device-in-intune-ios).

## <a name="resolving-known-issues-with-restores"></a>Geri yükleme işlemleriyle ilgili bilinen sorunları çözme

Kullanıcılar hala Şirket Portalı 2.1.21 veya önceki bir sürüme sahipken cihazlarını geri yükleyip Şirket Portalı uygulamasını başlattıklarında bazı zorluklar yaşayabilir. Bu sorunlar, kullanıcının durumuna uygun adımlar uygulanarak çözülebilir.

### <a name="for-users-who-will-only-use-their-new-device"></a>Yalnızca yeni cihazlarını kullanacak kullanıcılar
Şirket Portalı uygulamasını başlatın ve geçerli cihaz kutucuğunu seçip __Kaldır__ düğmesine dokunarak kaydı silin. Kaldırdıktan sonra, [Intune'a bir iOS cihazı kaydetmek](/intune-user-help/enroll-your-device-in-intune-ios) için standart kayıt adımlarını uygulayın.

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a>Hem eski hem de yeni cihazlarını kullanacak kullanıcılar
Safari’de __Ayarlar__ > __Safari__ > __Tarihçeyi ve Web Sitesi Verilerini Sil__’e dokunarak tanımlama bilgilerini temizleyin. Temizleme sonrası, Şirket Portalı uygulamasını kaldırıp yeniden yükleyin ve ardından [Intune'a bir iOS cihazı kaydetmek](/intune-user-help/enroll-your-device-in-intune-ios) için standart kayıt adımlarını uygulayın.
