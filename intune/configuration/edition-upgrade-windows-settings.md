---
title: Microsoft Intune-Azure 'da Windows 10 yükseltme ve S modu ayarları | Microsoft Docs
description: Tüm ayarların bir listesini ve bir cihazda Windows 10 sürümünü yükseltirken ne yaptığını ve Microsoft Intune bir cihaz yapılandırma profili kullanan bir cihazda S modunu etkinleştir ' i inceleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 75878e2110e9d855c2a0f78c0e7a1112f883872e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72489666"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>Windows 10 (ve daha yeni) cihazları yükseltmek veya Intune 'da S modunu etkinleştirmek için cihaz ayarları

Microsoft Intune cihazlarınızı yönetmenize ve korumanıza yardımcı olacak birçok ayar içerir. Bu makalede, Windows 10 cihazlarında sürümlerini yükseltmek veya S modunu etkinleştirmek için ayarların listesi ve açıklanmaktadır. Bu ayarlar, Intune 'da gönderilen veya cihazlara dağıtılan bir yükseltme yapılandırma profilinde oluşturulur.

Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları, Windows 10 cihazlarınızın sürümü ve S mod seçeneklerini denetlemek için kullanın.

Bu özellik hakkında daha fazla bilgi için bkz. [Windows 10 sürümlerini yükseltme veya S modunu etkinleştirme](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Profili oluşturun](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Sürüm yükseltme

- **Yükseltilecek sürüm**: Yükseltme yaptığınız Windows 10 sürümünü seçin. Bu ilke tarafından hedeflenen cihazlar seçtiğiniz sürüme yükseltilir.
- **Ürün Anahtarı**: Microsoft'tan aldığınız ürün anahtarını girin. Ürün anahtarıyla bir ilke oluşturulduktan sonra anahtar güncelleştirilemez ve güvenlik nedeniyle gizlenir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girin.
- **Lisans Dosyası**: **İş için Windows 10 Holographic** veya **Windows 10 Mobile sürümü**'nde, seçmek üzere **Gözat** ile Microsoft'tan aldığınız dosyaya gidin. Bu lisans dosyası, cihazları yükselttiğiniz sürümlerin lisans bilgilerini içerir.

## <a name="mode-switch"></a>Mod anahtarı

- **Yapılandırma yok**: s modu bir cihaz, s modunda kalır. Son kullanıcı cihazı S modundan çıkarabilir.
- **S modunda tut**: Son kullanıcının cihazı S modundan çıkarmasını devre dışı bırakır.
- **Çıkış**: Cihazı S modundan çıkarır.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu, ancak henüz bir şey yapmamış olabilir. [Profili atadığınızdan](device-profile-assign.md)emin olun ve [durumunu izleyin](device-profile-monitor.md).

Ayrıca, [Windows holographic for Business](holographic-upgrade.md) cihazları için sürüm yükseltme profilleri oluşturabilirsiniz.
