---
title: "Windows 10 Team için Intune cihaz kısıtlamaları"
titlesuffix: Azure portal
description: "Windows 10 Team cihazları için sağlanan cihaz kısıtlamalarını öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3648f8b273f666d1898226f3da8580e55a6bc6f8
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 Team cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


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
- **Miracast kablosuz yansıtma kanalı** - Bağlantı kurmak için kullanılacak Miracast kanalını seçin.


## <a name="next-steps"></a>Sonraki adımlar

[Cihaz kısıtlama ayarlarını yapılandırma](device-restrictions-configure.md) makalesindeki bilgileri kullanarak profili kaydedin ve kullanıcı ve cihazlara atayın.
