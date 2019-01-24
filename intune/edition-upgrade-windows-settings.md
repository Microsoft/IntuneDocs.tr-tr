---
title: Windows 10 yükseltme ve S modu ayarları Microsoft Intune - Azure | Microsoft Docs
description: Tüm ayarların bir listesi ve bir cihaz üzerinde bir Windows 10 sürüm yükseltme sırasında ne yaptıklarını görün veya Microsoft Intune cihaz yapılandırma profili kullanarak bir cihazdaki S modunu etkinleştirin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a2a7d7ab1603300119f28596e81ae49cbbcbf550
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831691"
---
# <a name="windows-10-and-newer-device-settings-to-upgrade-editions-or-enable-s-mode-in-intune"></a>Yükseltme sürümleri ya da Intune etkinleştirme S modunda Windows 10 (ve üzeri) cihaz ayarları

Microsoft Intune, cihazların yönetilmesine ve korunmasına yardımcı olmak üzere birçok ayarlarını içerir. Bu makalede, listeler ve sürümleri yükseltme veya Windows 10 cihazlarında S modunu etkinleştirmek için ayarları açıklar. Bu ayarlar, ıntune'a gönderilen veya cihazlara dağıttığınız yükseltme yapılandırma profilinde oluşturulur.

Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, sürüm ve Windows 10 cihazlarınızın S modu seçenekleri denetlemek için bu ayarları kullanın.

Bu özellik hakkında daha fazla bilgi için bkz. [etkinleştir S modu veya Windows 10 yükseltme sürümlerini](edition-upgrade-configure-windows-10.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Profil oluşturma](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Sürüm yükseltme

- **Yükseltilecek sürüm**: Yükseltme yapıyorsanız Windows 10 sürümünü seçin. Bu ilke tarafından hedeflenen cihazlar seçtiğiniz sürüme yükseltilir.
- **Ürün anahtarı**: Microsoft'tan aldığınız ürün anahtarını girin. Ürün anahtarıyla bir ilke oluşturulduktan sonra anahtar güncelleştirilemez ve güvenlik nedeniyle gizlenir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girin.
- **Lisans dosyası**: İçin **iş için Windows 10 Holographic** veya **Windows 10 Mobile sürümü**, seçin **Gözat** Microsoft'tan aldığınız lisans dosyasını seçmek için. Bu lisans dosyası cihazları yükselttiğiniz sürümleri için lisans bilgileri içerir.

## <a name="mode-switch"></a>Moduna geçme

- **Yapılandırma**: Bir S modu cihaz S modda kalır. Son kullanıcı cihazı S modundan çıkarabilir.
- **S modunda tutmak**: Geçiş aygıtını S modundan son kullanıcının devre dışı bırakır.
- **Anahtar**: Cihaz S modundan geçer.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur, ancak, hiçbir şey henüz yapmadan. Mutlaka [profili atama](device-profile-assign.md), ve [atamanın durumunu izlemenize](device-profile-monitor.md).

Sürüm yükseltme profillerini oluşturabilirsiniz [Windows Holographic for Business](holographic-upgrade.md) cihazlar.