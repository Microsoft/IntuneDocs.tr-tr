---
title: "Android cihazları için Intune özel ayarları"
titleSuffix: Azure portal
description: "Bir Android özel profilinde kullanabileceğiniz ayarları öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 92014eb9fd5564c0527b8cbf68732a51cf83bc96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazları için özel ayarlar

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android cihazlarındaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını atamak için Microsoft Intune Android **Özel** profilini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılamayan Android ayarlarını atamanıza olanak sağlamak için tasarlanmıştır.

## <a name="custom-profile-settings-for-android-devices"></a>Android cihazları için özel profil ayarları

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** dikey penceresinde **Ayarlar**’ı seçin.
3. **Satırı Düzenle** dikey penceresinde, her ayar için aşağıdaki değerleri yapılandırın:
    - **Ad** - Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama** - Ayara genel bir bakış sağlayan ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama belirtin.
    - **Veri türü** - Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize**, **Dize (XML)**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta** ve **Boole değeri** seçeneklerinden birini belirtin.
    - **OMA-URI** - Ayar sağlamak istediğiniz OMA-URI’yi belirtin.
    - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz değeri girin.
4. Bitirdiğinizde **Tamam**’a tıklayın, ardından gereken diğer ayarları eklemeye devam edin.

## <a name="next-steps"></a>Sonraki adımlar

Ayarları tamamladığınızda profil oluşturulur ve profil listesi dikey penceresinde görüntülenir. Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).

Kullanabileceğiniz özel ayarlara bazı örnekler için bkz.

- [Microsoft Intune özel cihaz profili kullanarak önceden paylaşılan anahtara sahip Wi-Fi profili oluşturma](/intune/wi-fi-profile-shared-key)
- [Microsoft Intune özel profili kullanarak Android cihazları için uygulama başına VPN profili oluşturma](/intune/android-pulse-secure-per-app-vpn)
- [Microsoft Intune’da özel ilkeler kullanarak Samsung KNOX Standart cihazları için uygulamalara izin verme veya bunları engelleme](/intune/samsung-knox-apps-allow-block)
