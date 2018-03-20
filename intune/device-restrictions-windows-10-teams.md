---
title: "Windows 10 Team için Windows Intune cihaz kısıtlamaları"
titlesuffix: 
description: "Windows 10 Team çalıştıran cihazlar için sağlanan cihaz kısıtlamaları hakkında bilgi edinin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 69cceda6857412f7e9a50c58d075caeee4ea9c20
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-windows-10-team-device-restriction-settings"></a>Microsoft Intune Windows 10 Team cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu makalede, Windows 10 Team çalıştıran cihazlar için yapılandırabileceğiniz Microsoft Intune cihaz kısıtlama ayarları gösterilir.


## <a name="apps-and-experience"></a>Uygulamalar ve deneyim

- **Birisi odadayken uyku modundan çıkar** - Algılayıcı, odada birisini algıladığında cihazın otomatik olarak uyanmasına izin verir.
- **Hoş Geldiniz ekranında gösterilen toplantı bilgileri** - Hoş Geldiniz ekranının Toplantılar kutucuğunda gösterilecek bilgileri seçmek için bu seçeneği etkinleştirin. Şunları yapabilirsiniz:
    - **Yalnızca düzenleyeni ve saati göster**
    - **Düzenleyeni, saati ve konuyu göster (özel toplantılar için konu gizlidir)**
- **Hoş Geldiniz ekranı arka plan görüntüsü URL’si** - Windows 10 Team cihazlarının **Hoş Geldiniz** ekranında, belirttiğiniz URL’den özel bir arka plan görüntülemek için bu ayarı etkinleştirin.<br>Görüntü PNG biçiminde olmalıdır ve URL **https://** ile başlamalıdır.

## <a name="azure-operational-insights"></a>Azure operasyonel öngörüler

- **Azure Operasyonel Öngörüler** - Microsoft Operations Manager’ın bir parçası olan Azure Operasyonel Öngörüler, Windows 10 Team cihazlarından günlük dosyası verilerini toplar, depolar ve analiz eder.
Azure Operasyonel Öngörüler'e bağlanmak için bir **Çalışma Alanı Kimliği** ve bir **Çalışma Alanı Anahtarı** belirtmeniz gerekir.

## <a name="maintenance"></a>Bakım

- **Güncelleştirmeler için bakım penceresi** - Cihazda güncelleştirme gerçekleştirilebildiği zaman pencereyi yapılandırır. Pencerenin **Başlangıç saati** ve **Saat cinsinden süresi**’ni (1-5 saat) yapılandırabilirsiniz.

## <a name="wireless-projection"></a>Kablosuz yansıtma

- **Kablosuz projeksiyon için PIN** - Cihazın kablosuz projeksiyon özelliklerini kullanabilmek için PIN girmenin gerekli olup olmadığını belirtir.
- **Miracast kablosuz projeksiyon** - Windows 10 Team cihazlarının projeksiyon için Miracast özellikli cihazları kullanmasına izin vermek istiyorsanız bu seçeneği etkinleştirin.
- **Miracast kablosuz yansıtma kanalı** - Bağlantı kurmak için kullanılan Miracast kanalını seçin.


## <a name="next-steps"></a>Sonraki adımlar

[Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md) makalesindeki bilgileri kullanarak profili kaydedin ve kullanıcı ve cihazlara atayın.
