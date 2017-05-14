---
title: "Android cihazları için Intune özel ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Android özel profilinde kullanabileceğiniz ayarları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 0ac1a6eeca125261f44607bbbb76b04253d5270e
ms.contentlocale: tr-tr
ms.lasthandoff: 05/05/2017


---

# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazları için özel ayarlar

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Android cihazlarındaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını atamak için Microsoft Intune Android **Özel** profilini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılamayan Android ayarlarını atamanıza olanak sağlamak için tasarlanmıştır.

## <a name="custom-profile-settings-for-android-devices"></a>Android cihazları için özel profil ayarları

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](how-to-configure-custom-settings.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** dikey penceresinde **Ayarlar**’ı seçin.
3. **Satırı Düzenle** dikey penceresinde, her ayar için aşağıdaki değerleri yapılandırın:
    - **Ad** - Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama** - Ayara genel bir bakış sağlayan ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama belirtin.
    - **Veri türü** - Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize**, **Dize (XML)**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta** ve **Boole değeri** seçeneklerinden birini belirtin.
    - **OMA-URI** - Ayar sağlamak istediğiniz OMA-URI’yi belirtin.
    - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz değeri girin.
4. Bitirdiğinizde **Tamam**’a tıklayın, ardından gereken diğer ayarları eklemeye devam edin.

