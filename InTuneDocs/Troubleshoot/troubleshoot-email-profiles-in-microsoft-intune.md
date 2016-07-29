---
title: "E-posta profilleriyle ilgili sorunları giderme | Microsoft Intune"
description: "E-posta profili sorunları, bu sorunları giderme ve çözme."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: 9b699229489be2f09ea4c7a80e1e80f6ec7b106e


---

# Microsoft Intune’da e-posta profilleriyle ilgili sorunları giderme
Burada bazı e-posta profili sorunları listelenir, bunların nasıl giderileceği ve çözüleceği açıklanır.

Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).


## E-posta hesabından resim gönderilemedi
Otomatik olarak yapılandırılan e-posta hesaplarına sahip kullanıcılar, cihazlarından resim veya görüntü gönderemiyor.
**Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver** seçeneği etkinleştirilmediğinde bu durum ortaya çıkar.

### Intune çözümü

1.  Microsoft Intune Yönetim Konsolu’nu açın, **İlke** iş yükü &gt; **Yapılandırma İlkesi**’ni seçin.

2.  E-posta profilini seçin ve **Düzenle**’yi seçin.

3.  **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

### Intune ile tümleştirilmiş Configuration Manager çözümü

1.  Configuration Manager konsolu &gt; **Varlıklar ve Uyum**'u açın.

2.  **Genel Bakış** -&gt;**Uyumluluk Ayarları** -&gt; **Şirket Kaynağına Erişim**’i genişletin ve **E-posta Profilleri**’ni seçin.

3.  E-posta profiline sağ tıklayın ve **Özellikler**’i açın.

4.  **Eşitleme Ayarları** sekmesinde **Üçüncü taraf uygulamalardan e-posta gönderilmesine izin ver**’i seçin.

## Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Jul16_HO4-->


