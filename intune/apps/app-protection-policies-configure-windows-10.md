---
title: Windows 10 için uygulama koruma ilkelerini yapılandırma
titleSuffix: Microsoft Intune
description: Bu konu başlığında Windows 10 cihazlar için uygulama koruma ilkelerini (APP) yapılandırma adımları anlatılmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0e1ff8fd39d301bd685e9806c319f49e9189d7f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507408"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Windows 10 için uygulama koruma ilkeleri yapılandırmaya hazırlanma 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Azure AD’de MAM sağlayıcısını ayarlayarak Windows 10 için mobil uygulama yönetimini (MAM) etkinleştirin. Azure AD’de bir MAM sağlayıcısı ayarlamak, Intune ile yeni bir Windows Bilgi Koruması (WIP) ilkesi oluştururken kayıt durumunu belirtmenizi sağlar. Kayıt durumu MAM ya da mobil cihaz yönetimi (MDM) olabilir.

## <a name="to-configure-the-mam-provider"></a>MAM sağlayıcısını yapılandırmak için

1. Azure portalında oturum açın ve **Azure Active Directory** seçeneğini belirleyin.

2. **Yönet** grubunda **Mobilite (MDM ve MAM)** öğesini seçin.

3. **Microsoft Intune**’a tıklayın.

4. **Yapılandır** dikey penceresinde **Varsayılan MAM URL’lerini geri yükle** grubundaki ayarları yapılandırın.

   **MAM kullanıcı kapsamı**  
   Çalışanlarınızın Windows cihazlarındaki kurumsal verileri yönetmek için MAM otomatik kaydı kullanın. MAM otomatik kayıt, kendi cihazını getir senaryoları için yapılandırılacaktır.<ul><li>**Yok.**<br>MAM’a kaydedilecek kullanıcı yoksa bunu seçin.</li><li>**Bazı**<br>MAM’a kayıt olacak kullanıcıları içeren Azure AD gruplarını seçin.</li><li>**Tümü**<br>Tüm kullanıcıların MAM’a kayıt olup olamayacağını seçin.</li></ul>

   **MDM kullanım koşulları URL’si**  
   MAM kullanım koşulları URL’si Microsoft Intune’da desteklenmez. Koruma ilkelerinin uygulanması için bu giriş kutusu boş bırakılmalıdır.

   **MDM bulma URL’si**  
   MAM hizmeti kayıt uç noktası URL'si. Kayıt uç noktası, cihazları MAM hizmetine yönetim için kaydetmek üzere kullanılır.

   **MAM uyumluluğu URL’si**  
   MAM uyumluluk URL’si Microsoft Intune’da desteklenmez. Koruma ilkelerinin uygulanması için bu giriş kutusu boş bırakılmalıdır. 

5. **Kaydet**'e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

[WIP uygulama koruma ilkesi oluşturma](windows-information-protection-policy-create.md)