---
title: iOS cihazları için Intune AirPlay ayarları
titlesuffix: Microsoft Intune
description: iOS cihazları AirPlay uyumlu cihazlara otomatik olarak bağlamaya yardımcı olması için Microsoft Intune’u nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 06d1fbc5a27e0e5187c6419b45f4a0380b895d6b
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="intune-airplay-settings-for-ios-devices"></a>iOS cihazları için Intune AirPlay ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Yönettiğiniz iOS cihazlarını ağınızdaki AirPlay uyumlu cihazlara (Apple TV gibi) bağlamaya yardımcı olması için bu ayarları kullanın.
Bu özellik ile şunları yapabilirsiniz:

- **Bir cihaz ve parola listesi yapılandırma** - Kullanıcıların menzildeki AirPlay cihazlarına otomatik olarak bağlanmasına olanak tanıyın. Onlara AirPlay cihazlarının adını ve parolasını sağlayın; böylece bağlandıklarında bu bilgileri girmeleri gerekmesin.
- **İzin verilen hedefleri yapılandırma** - AirPlay cihazlarının listesini yapılandırın (cihaz kimliğine göre). Son kullanıcılar yalnızca listelediğiniz cihazları görebilir ve bunlara bağlanabilir (yalnızca denetimli cihazlar için).

## <a name="get-started"></a>Başlarken

1. [Azure Portalı’nda Intune](https://portal.azure.com)’dan, cihaz yapılandırma alanındaki [**Cihaz özellikleri**’ne gidin](device-features-configure.md). 
1. **Cihaz özellikleri** bölmesinde **AirPlay**’i seçin.
2. **AirPlay** bölmesinde, aşağıdaki eylemlerden birini veya ikisini birden seçin:

## <a name="configure-a-device-and-password-list"></a>Cihaz ve parola listesi yapılandırma

1. **Parolalar** bölmesinde, bir AirPlay cihazının **Cihaz Adını** ve **Parolasını** girin, örneğin **Contoso Apple TV**.
2. Cihaz ayrıntılarını girdikten sonra **Ekle**’ye tıklayın. Cihaz, **Cihaz Adı** listesinde görünür.
3. Cihaz eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.


## <a name="configure-allowed-destinations"></a>İzin verilen hedefleri yapılandırma

1. **İzin verilen hedefler (yalnızca denetimli)** bölmesinde bir AirPlay cihazının **Cihaz Kimliğini** girin, örneğin 52:46:CD:51:83:4C.
2. Cihaz kimliğini girdikten sonra **Ekle**’ye tıklayın. Kimlik, **Cihaz Kimliği** listesinde görünür.
3. Cihaz eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.

Ayrıca cihaz ve parolaları ve izin verilen hedefleri virgülle ayrılmış değerler (csv) dosyasından içeri aktarabilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).

