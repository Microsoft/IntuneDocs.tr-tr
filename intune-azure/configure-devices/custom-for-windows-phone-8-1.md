---
title: "Windows Phone 8.1 cihazları için Intune özel ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows Phone 8.1 özel profilinde kullanabileceğiniz ayarları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 652eca69f3e53365b75fd8590fce299209e2a12f
ms.lasthandoff: 02/18/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows Phone 8.1 cihazları için özel ayarlar

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Windows Phone 8.1 cihazlardaki özellikleri denetlemek amacıyla kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune Windows Phone 8.1 **Özel** profilini kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, diğer Intune ilkeleriyle ile yapılandırılamayan ayarları dağıtmanıza olanak sağlamak için tasarlanmıştır.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Windows Phone 8.1 cihazları için özel ilke ayarları

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](how-to-configure-custom-settings.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** dikey penceresinde **Ayarlar**’ı seçin.
3. **Satır Ekle** dikey penceresinde, her ayar için aşağıdaki değerleri yapılandırın:
    - **Ad** - Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama** - Ayara genel bir bakış sağlayan ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama belirtin.
    - **OMA-URI** - Ayar sağlamak istediğiniz OMA-URI’yi belirtin.
    - **Veri türü** - Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize**, **Tarih ve saat**, **Tamsayı**, **Kayan nokta** ve **Boole değeri** seçeneklerinden birini belirtin.
    - **Değer** - Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz değeri girin.

4. Bitirdiğinizde **Tamam**’a tıklayın, ardından gereken diğer ayarları eklemeye devam edin.

