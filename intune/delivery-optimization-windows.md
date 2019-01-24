---
title: Microsoft Intune - Azure'da Windows 10 için dağıtım iyileştirme ayarlarını | Microsoft Docs
description: Yazılım güncelleştirmeleri için Windows 10 ve üzeri cihazlar ile kullanılabilir teslimat iyileştirme bulut hizmetlerini kullanarak cihazlarınızı nasıl teslim edildiğini yapılandırın. Intune, internet'ten güncelleştirmeleri yüklemek için bir cihaz yapılandırma profili oluşturma. Ayrıca var olan güncelleştirme halkaları teslim iyileştirme profiliyle nasıl değiştirileceğini bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a59cab5f709897e064b315193b292cb46dc2f2e
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831556"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Windows 10 (ve üzeri) delivery optimization ayarları Microsoft Intune

> [!NOTE]
> **Yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları** değiştirilir **teslim iyileştirme** ayarları. Kullanmak için var olan güncelleştirme halkaları değiştirilebilir **teslim iyileştirme** ayarları. [Var olan güncelleştirme halkaları için teslim iyileştirme taşıma](#move-existing-update-rings-to-delivery-optimization) (Bu makalede) adımları listelenir. 


Bu özellik aşağıdaki platformlar için geçerlidir:

- Windows 10 ve üzeri

Bu makale, listeler ve Windows 10 cihazlar için yapılandırabileceğiniz tüm delivery optimization ayarları açıklar. Bu ayarları bir cihaz yapılandırma profili eklendiğinde ve sonra atanan veya Microsoft Intune kullanarak cihazlarınızı dağıtılmış.

[Teslim iyileştirme güncelleştirmeleri](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) Windows 10 teslim iyileştirme hakkında daha fazla bilgi edinmek için harika bir kaynaktır.

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.

2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.

3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Platformu seçin:  

        - **Windows 10 ve üzeri**

    - **Profil türü**: Seçin **teslim iyileştirme**.
    - **Ayarları**: Yüklenen güncelleştirmeleri nasıl istediğinizi seçin. Seçenekleriniz şunlardır: 

        - **Yapılandırılmamış**: Son kullanıcılar cihazlarını kullanmak için kendi yöntemlerini kullanarak güncelleştirme **Windows güncelleştirmeleri** veya **teslim iyileştirme** ayarları OS ile kullanılabilir.
        - **Yalnızca HTTP, eşleme yok**: Güncelleştirmeleri yalnızca internet'ten alın. Güncelleştirmeler (eşleme veya eşler arası olarak adlandırılır), ağınızdaki diğer bilgisayarlardan elde etmezsiniz.
        - **Aynı NAT arkasında eşleme ile karışık HTTP**: Güncelleştirmeleri internet'ten ve ağınızdaki diğer bilgisayarlar alın. 
        - **Özel bir grup üzerinde eşleme ile karışık HTTP**: Eşleme, aynı Active Directory (varsa) sitesi veya aynı etki alanında cihazlarda gerçekleşir. Bu seçenek belirlendiğinde, eşleme ağ adresi çevirisi (NAT) IP adreslerinizi çizer.
        - **Internet eşlemesi ile karışık HTTP**: Güncelleştirmeleri internet'ten ve ağınızdaki diğer bilgisayarlar alın.
        - **Eşlemesiz basit indirme modu**: Güncelleştirmeleri Microsoft update sahibinden doğrudan internet'ten alır. Bu teslim iyileştirme bulut Hizmetleri iletişim kurmaz.
        - **Atlama modu**: Güncelleştirmeleri almak için arka plan Akıllı Aktarım Hizmeti (BITS) kullanın. Teslim iyileştirme kullanmayın.

4. İşiniz bittiğinde seçin **Tamam** > **Oluştur** yaptığınız değişiklikleri kaydedin.

Profil oluşturulur ve listede görüntülenir. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Var olan güncelleştirme halkaları için teslim iyileştirme Taşı

**Yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları** değiştirilir **teslim iyileştirme** ayarları. Mevcut uygulamanızı güncelleştirme halkaları kullanmak için kolayca değiştirilebilir **teslim iyileştirme** ayarları. Adımlar:

1. Teslim iyileştirme yapılandırma profili oluşturun:

    1. Intune'da seçin **cihaz Yapılandırması** > **profilleri** > **profili oluşturma**.
    2. Aşağıdaki özellikleri girin:

        - **Ad**: Yeni profil için açıklayıcı bir ad girin.
        - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
        - **Platform**: Seçin **Windows 10 ve üzeri**.
        - **Profil türü**: Seçin **teslim iyileştirme**.
        - **Ayarları**: İçin **teslim iyileştirme indirme modu**, mevcut yazılım güncelleştirme kademesi tarafından kullanılan aynı modunu seçin. Seçenekleriniz şunlardır:
            - **Yapılandırılmadı**
            - **Yalnızca HTTP, eşleme yok**
            - **Aynı NAT arkasında eşleme ile karışık HTTP**
            - **Özel bir grup üzerinde eşleme ile karışık HTTP**
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
