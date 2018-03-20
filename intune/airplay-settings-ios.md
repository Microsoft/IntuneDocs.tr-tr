---
title: "iOS cihazları için Intune AirPlay ayarları"
titlesuffix: Azure portal
description: "iOS cihazları AirPlay uyumlu cihazlara otomatik olarak bağlamaya yardımcı olması için Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9de6f0e2f7c74e7aec45c27f0fa20189b26c5e22
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="intune-airplay-settings-for-ios-devices"></a>iOS cihazları için Intune AirPlay ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Yönettiğiniz iOS cihazlarını ağınızdaki AirPlay uyumlu cihazlara (Apple TV gibi) bağlamaya yardımcı olması için bu ayarları kullanın.
Bu özellik ile şunları yapabilirsiniz:

- **Bir cihaz ve parola listesi yapılandırma** - Kullanıcıların menzildeki AirPlay cihazlarına otomatik olarak bağlanmasına olanak tanıyın. Onlara AirPlay cihazlarının adını ve parolasını sağlayın; böylece bağlandıklarında bu bilgileri girmeleri gerekmesin.
- **İzin verilen hedefleri yapılandırma** - AirPlay cihazlarının listesini yapılandırın (cihaz kimliğine göre). Son kullanıcılar yalnızca listelediğiniz cihazları görebilir ve bunlara bağlanabilir (yalnızca denetimli cihazlar için).

## <a name="get-started"></a>Başlarken

1. [Azure Portalı’nda Intune](https://portal.azure.com)’dan, cihaz yapılandırma alanındaki [**Cihaz özellikleri**’ni seçin](device-features-configure.md). 
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

