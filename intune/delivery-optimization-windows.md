---
title: Microsoft Intune - Azure'da Windows 10 için dağıtım iyileştirme ayarlarını | Microsoft Docs
description: Yazılım güncelleştirmeleri için Windows 10 ve üzeri cihazlar ile kullanılabilir teslimat iyileştirme bulut hizmetlerini kullanarak cihazlarınızı nasıl teslim edildiğini yapılandırın. Intune, internet'ten güncelleştirmeleri yüklemek için bir cihaz yapılandırma profili oluşturma. Ayrıca var olan güncelleştirme halkaları teslim iyileştirme profiliyle nasıl değiştirileceğini bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36cfb5ac05b2d69b5c7349f4ebc6054848a08fc8
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52730111"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Windows 10 (ve üzeri) delivery optimization ayarları Microsoft Intune

Bu makale, listeler ve Windows 10 cihazlar için yapılandırabileceğiniz tüm delivery optimization ayarları açıklar. Bu ayarları bir cihaz yapılandırma profili eklendiğinde ve sonra atanan veya Microsoft Intune kullanarak cihazlarınızı dağıtılmış.

## <a name="settings"></a>Ayarlar

**Teslim iyileştirme indirme modu**: güncelleştirmeleri, cihazlara nasıl teslim edildiğini seçin. Seçenekleriniz şunlardır:

- **Yapılandırılmamış**: son kullanıcıların cihazlarını kullanmak için kendi yöntemlerini kullanarak güncelleştirme **Windows güncelleştirmeleri** veya **teslim iyileştirme** ayarları OS ile kullanılabilir.
- **Yalnızca HTTP, eşleme yok**: yalnızca internet'ten güncelleştirmeleri alın. Güncelleştirmeler (eşleme veya eşler arası olarak adlandırılır), ağınızdaki diğer bilgisayarlardan elde etmezsiniz.
- **Özel bir grup üzerinde eşleme ile karışık NAT HTTP aynı eşleme ile karışık HTTP**: internet'ten ve ağınızdaki diğer bilgisayarlardan güncelleştirmeleri alın. Eşleme, aynı Active Directory (varsa) sitesi veya aynı etki alanında cihazlarda gerçekleşir. Bu seçenek belirlendiğinde, eşleme ağ adresi çevirisi (NAT) IP adreslerinizi çizer.
- **Internet eşlemesi ile karışık HTTP**: internet'ten ve ağınızdaki diğer bilgisayarlardan güncelleştirmeleri alın.
- **Eşlemesiz basit indirme modu**: Microsoft gibi güncelleştirme sahibinden doğrudan internet'ten güncelleştirmeleri alır. Bu teslim iyileştirme bulut Hizmetleri iletişim kurmaz.
- **Atlama modu**: kullanım arka plan Akıllı Aktarım Hizmeti (güncelleştirmeleri almak için BITS). Teslim iyileştirme kullanmayın.

## <a name="move-from-existing-update-rings-to-delivery-optimization"></a>Var olan güncelleştirme kademeleri için teslim iyileştirme Taşı

**Yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları** değiştirilir **teslim iyileştirme** ayarları. Mevcut uygulamanızı güncelleştirme halkaları kullanmak için kolayca değiştirilebilir **teslim iyileştirme** ayarları. Adımlar:

1. Teslim iyileştirme yapılandırma profili oluşturun:

    1. Intune'da seçin **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**.
    2. Profil için bir **Ad** ve bir **Açıklama** girin.
    3. İçin **Platform**, seçin **Windows 10 ve üzeri**. İçin **profil türü**, seçin **teslim iyileştirme**.
    4. **Ayarlar**’ı seçin. İçin **teslim iyileştirme indirme modu**, mevcut yazılım güncelleştirme kademesi tarafından kullanılan aynı modunu seçin. Seçenekleriniz şunlardır:
        - **Yapılandırılmadı**
        - **Yalnızca HTTP, eşleme yok**
        - **Aynı NAT özel bir grup üzerinde eşleme ile karışık HTTP arkasında eşleme ile karışık HTTP**
        - **Internet eşlemesi ile karışık HTTP**
        - **Eşlemesiz basit indirme modu**
        - **Atlama modu**

2. Bu yeni profili aynı cihazları ve kullanıcıları, mevcut yazılım güncelleştirme kademesi atayın. [Profil atama](device-profile-assign.md) adımları listelenir.

3. Mevcut yazılım halka yapılandırmasını Kaldır:
    1. Intune'da Git **yazılım güncelleştirmelerini** > Windows 10 güncelleştirme halkaları.
    2. Listede, güncelleştirme kademesi seçin.
    3. Ayarları'nda **teslim iyileştirme indirme modu** için **yapılandırılmadı**.
    4. **Tamam** > **Kaydet** yaptığınız değişiklikleri.

## <a name="next-steps"></a>Sonraki adımlar

[Profil atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md) durumu.