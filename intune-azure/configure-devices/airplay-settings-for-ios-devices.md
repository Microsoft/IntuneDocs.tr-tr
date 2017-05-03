---
title: "iOS cihazları için Intune AirPlay ayarları"
titleSuffix: Intune Azure preview
description: "iOS cihazları AirPlay uyumlu cihazlara otomatik olarak bağlamaya yardımcı olması için Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: f1f7aa6a0b441b51f20d104c4353a1542a9e01ad
ms.lasthandoff: 04/19/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>iOS cihazları için Intune AirPlay ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Yönettiğiniz iOS cihazlarını ağınızdaki AirPlay uyumlu cihazlara (Apple TV gibi) bağlamaya yardımcı olması için bu ayarları kullanın.
Bu özellik ile şunları yapabilirsiniz:

- **Cihaz ve parola listesi yapılandırma** - Aralık içinde olduğunda otomatik olarak bağlanmaları için cihazlara AirPlay cihazlarının adını ve parolasını sağlayın. Bir parola sağlarsanız, son kullanıcıların bağlandıklarında parola sağlaması gerekmez.
- **İzin verilen hedefleri yapılandırma** - AirPlay cihazlarının listesini yapılandırın (cihaz kimliğine göre). Son kullanıcılar yalnızca listelediğiniz cihazları görebilir ve bunlara bağlanabilir (yalnızca denetimli cihazlar için).

## <a name="get-started"></a>Başlarken

1. **Cihaz özellikleri** dikey penceresinde **AirPlay**’i seçin.
2. **AirPlay** dikey penceresinde, aşağıdaki eylemlerden birini veya ikisini birden seçin:

## <a name="configure-a-device-and-password-list"></a>Cihaz ve parola listesi yapılandırma

1. **Parolalar** dikey penceresinde, bir AirPlay cihazının **Cihaz Adını** ve **Parolasını** girin, örneğin **Contoso Apple TV**.
2. Cihaz ayrıntılarını girdikten sonra **Ekle**’ye tıklayın. Cihaz, **Cihaz Adı** listesinde görünür.
3. Cihaz eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.


## <a name="configure-allowed-destinations"></a>İzin verilen hedefleri yapılandırma

1. **İzin verilen hedefler (yalnızca denetimli)* dikey penceresinde bir AirPlay cihazının **Cihaz Kimliğini** girin, örneğin 52:46:CD:51:83:4C.
2. Cihaz kimliğini girdikten sonra **Ekle**’ye tıklayın. Kimlik, **Cihaz Kimliği** listesinde görünür.
3. Cihaz eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.

Ayrıca cihaz ve parolaları ve izin verilen hedefleri virgülle ayrılmış değerler (csv) dosyasından içeri aktarabilirsiniz.



