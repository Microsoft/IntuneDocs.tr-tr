---
title: "Android cihazlar için Intune özel ayarları | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Android özel profilinde kullanabileceğiniz ayarları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3a80a69a27b540b66fb96e098c0b0f66a0854297


---

# <a name="custom-settings-for-android-devices-in-intune-azure-preview"></a>Intune Azure önizlemesinde Android cihazları için özel ayarlar

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Android cihazlarındaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune Android **Özel** profilini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılabilir olmayan Android ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.

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



<!--HONumber=Feb17_HO1-->

