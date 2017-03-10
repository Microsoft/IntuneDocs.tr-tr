---
title: "Windows 10 Team için Intune cihaz kısıtlamaları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows 10 Team cihazları için sağlanan cihaz kısıtlamalarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 4df8afe50912912e42e03b6b9bc1c397fff2d6db
ms.lasthandoff: 02/18/2017


---

# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 Team cihaz kısıtlama ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

- **Birisi odadayken uyku modundan çıkar** - Algılayıcı, odada birisini algıladığında cihazın otomatik olarak uyanmasına izin verir.
- **Kablosuz projeksiyon için PIN** - Cihazın kablosuz projeksiyon özelliklerini kullanabilmek için PIN girmenin gerekli olup olmadığını belirtir.
- **Miracast kablosuz projeksiyon** - Windows 10 Team cihazlarının projeksiyon için Miracast özellikli cihazları kullanmasına izin vermek istiyorsanız bu seçeneği etkinleştirin.
- **Hoş geldiniz ekranında gösterilen toplantı bilgileri** - Hoş Geldiniz ekranının Toplantılar kutucuğunda gösterilecek bilgileri seçmek için bu seçeneği etkinleştirin. Şunları yapabilirsiniz:
    - **Yalnızca düzenleyeni ve saati göster**
    - **Düzenleyeni, saati ve konuyu göster (özel toplantılar için konu gizlidir)**
- **Hoş Geldiniz ekranı arka plan görüntüsü URL’si** - Windows 10 Team cihazlarının **Hoş Geldiniz** ekranında, belirttiğiniz URL’den özel bir arka plan görüntülemek için bu ayarı etkinleştirin.<br>Görüntü PNG biçiminde olmalıdır ve URL **https://** ile başlamalıdır.
- **Güncelleştirmeler için bakım penceresi** - Cihazda güncelleştirme gerçekleştirilebildiği zaman pencereyi yapılandırır. Pencerenin başlangıç saatini ve süresini (1-5 saat) yapılandırabilirsiniz.
- **Azure Operasyonel Öngörüler** - Microsoft Operations Manager’ın bir parçası olan Azure Operasyonel Öngörüler, Windows 10 Team cihazlarından günlük dosyası verilerini toplar, depolar ve analiz eder.<br>Azure Operasyonel Öngörüler'e bağlanmak için bir **Çalışma Alanı Kimliği** ve bir **Çalışma Alanı Anahtarı** belirtmeniz gerekir.

