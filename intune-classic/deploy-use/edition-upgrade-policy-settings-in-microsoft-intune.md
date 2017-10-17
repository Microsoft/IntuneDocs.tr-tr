---
title: "Windows sürümü yükseltme ilkesi ayarları"
description: "Windows 10 cihazlarını otomatik olarak Intune’un farklı bir sürümüne yükseltmeyi öğrenin."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 690fe1f1b2555996b2ef124cde6e3fba53e82ec7
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows sürümünü yükseltme ilkesi ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune **Sürüm Yükseltme İlkesi**, aşağıdaki Windows 10 sürümlerinden birini çalıştıran cihazları farklı bir sürüme otomatik olarak yükseltmenizi sağlar:
* Windows 10 Masaüstü
* Windows 10 Holographic
* Windows 10 Mobile

Aşağıdaki yükseltme yolları desteklenmektedir:
- Windows 10 Pro'dan Windows 10 Enterprise'a
- Windows 10 Home'dan Windows 10 Education'a
- Windows 10 Mobile'dan Windows 10 Mobile Enterprise'a
- Windows 10 Holographic Pro'dan Windows 10 Holographic Enterprise'a

## <a name="before-you-start"></a>Başlamadan önce
Cihazları en son sürüme yükseltmeye başlamadan önce aşağıdakilerden birine sahip olmanız gerekir:
* İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için). Çoklu Etkinleştirme Anahtarları (MAK) veya Anahtar Yönetimi Sunucusu (KMS) anahtarlarından herhangi birini kullanabilirsiniz.
**veya** İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için gerekli lisans bilgilerini içeren bir Microsoft lisans dosyası (Windows 10 Mobile ve Windows 10 Holographic sürümleri için).
* Hedeflediğiniz Windows 10 cihazları Microsoft Intune’a kayıtlı olmalıdır. Intune bilgisayar istemcisi yazılımını çalıştıran bilgisayarlar ile sürüm yükseltme ilkesini kullanamazsınız.

## <a name="edition-upgrade-policy-settings"></a>Sürüm yükseltme ilkesi ayarları

|Ayar adı|Ayrıntılar|
|-|-|
|**Ad**|Sürüm yükseltme ilkesi için bir ad girin.|
|**Açıklama**|İsteğe bağlı olarak, Intune konsolunda ilkeyi tanımanıza yardımcı olacak bir açıklama girin.
|**Yükseltilecek sürüm**|Açılan listede, hedef cihazları yükseltmek istediğiniz Windows 10 Masaüstü, Windows 10 Holographic veya Windows 10 Mobile sürümünü seçin.
|**Ürün Anahtarı**|Microsoft’tan aldığınız ve tüm hedeflenen Windows 10 Masaüstü cihazlarını yükseltmek için kullanılabilen ürün anahtarını belirtin.<br>Ürün anahtarı içeren bir ilke oluşturduğunuzda, ürün anahtarını daha sonra düzenleyemezsiniz. Bunun nedeni, anahtarın güvenlik nedeniyle engellenmesidir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girmeniz gerekir.
|**Lisans Dosyası**|Microsoft’tan aldığınız ve hedeflenen cihazları yükseltmek istediğiniz Windows Holographic veya Windows 10 Mobile sürümünün lisans bilgilerini içeren lisans dosyasını seçmek için **Gözat**’ı seçin.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
