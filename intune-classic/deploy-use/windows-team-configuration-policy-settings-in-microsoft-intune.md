---
title: Windows Team yapılandırma ilkesi ayarları
description: Microsoft Surface Hub gibi kayıtlı Windows 10 Team cihazlarının ayarlarını yapılandırmak için Microsoft Intune **Windows 10 Team genel yapılandırma ilkesini** kullanın.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows Team yapılandırma ilkesi ayarları

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Surface Hub gibi kayıtlı Windows 10 Team cihazlarının ayarlarını yapılandırmak için Microsoft Intune **Windows 10 Team genel yapılandırma ilkesini** kullanın.


|                                  Ayar adı                                   |                                                                                                                                                                Ayrıntılar                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Odada birisi olduğunda ekranın otomatik olarak uyanmasına izin ver</strong>   |                                                                                                                         Algılayıcı, odada birisini algıladığında cihazın otomatik olarak uyanmasına izin verir.                                                                                                                          |
|              <strong>Kablosuz projeksiyon için PIN iste</strong>               |                                                                                                             Cihazın kablosuz projeksiyon özelliklerini kullanabilmek için PIN girmenin gerekli olup olmadığını belirtir.                                                                                                             |
|          <strong>Cihaz güncelleştirmeleri için bir bakım penceresi ayarla</strong>           |                                                                                          Cihazda güncelleştirme gerçekleştirilebildiği zaman pencereyi yapılandırır. Pencerenin başlangıç saatini ve süresini (1-5 saat) yapılandırabilirsiniz.                                                                                           |
|               
  <strong>Azure Operasyonel İçgörüler'i etkinleştir</strong>                |                  Microsoft Operations Manager’ın bir parçası olan Azure Operasyonel İçgörüler, Windows 10 Team cihazlarından günlük dosyası verilerini toplar, depolar ve analiz eder.<br /><br />Azure Operasyonel İçgörüler'e bağlanmak için bir <strong>Çalışma Alanı Kimliği</strong> ve bir <strong>Çalışma Alanı Anahtarı</strong> belirtmeniz gerekir.                   |
|              <strong>Miracast kablosuz projektörü etkinleştir</strong>               |                                          Windows 10 Team cihazlarının yansıtmak için Miracast özellikli cihazları kullanmasına izin vermek istiyorsanız bu seçeneği etkinleştirin.<br /><br />Bu seçeneği etkinleştirirseniz <strong>Miracast kanalı seçin</strong> menüsünden içeriği yansıtmak için kullanılan Miracast kanalını seçin.                                           |
| <strong>Karşılama ekranında görüntülenen toplantı bilgilerini seçin</strong> | Bu seçeneği etkinleştirirseniz, <strong>Hoş Geldiniz</strong> ekranının <strong>Toplantılar</strong> kutucuğunda gösterilecek bilgileri seçebilirsiniz. Şunları yapabilirsiniz:<br /><br />-   <strong>Yalnızca düzenleyeni ve saati göster</strong><br />-   <strong>Düzenleyeni, saati ve konuyu göster (özel toplantılar için konu gizlidir)</strong> |
|                <strong>Kilit ekranı arka plan görüntüsü URL'si</strong>                 |                                           Windows 10 Team cihazlarının <strong>Hoş Geldiniz</strong> ekranında belirttiğiniz URL’den özel bir arka plan görüntülemek için bu ayarı etkinleştirin.<br /><br />Görüntü PNG biçiminde olmalıdır ve URL <strong>https://</strong> ile başlamalıdır.                                            |

### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

