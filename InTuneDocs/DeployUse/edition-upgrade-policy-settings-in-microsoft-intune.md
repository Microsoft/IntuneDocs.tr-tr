---
title: "Windows sürümünü yükseltme ilkesi ayarları | Microsoft Intune"
description: "Windows 10 cihazlarını otomatik olarak Intune’un en son sürümüne yükseltmeyi öğrenin."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a08ace43fb61f57a9d29b119c59698bc50e7af8
ms.openlocfilehash: 49bc54f36b281d85c9667c51fb6ddbe0d454b4d1


---

# Microsoft Intune’da Windows sürümünü yükseltme ilkesi ayarları
Microsoft Intune **Sürüm Yükseltme İlkesi**, aşağıdaki Windows 10 sürümlerinden birini çalıştıran cihazları daha yeni bir sürüme otomatik olarak yükseltmenizi sağlar:
* Windows 10 Masaüstü
* Windows 10 Holographic

## Başlamadan önce
Cihazları en son sürüme yükseltmeye başlamadan önce aşağıdakilerden birine sahip olmanız gerekir:
* İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için geçerli bir ürün anahtarı (Windows 10 Masaüstü sürümleri için).
* İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için gerekli lisans bilgilerini içeren bir Microsoft lisans dosyası (Windows 10 Mobile ve Windows 10 Holographic sürümleri için).
* Hedeflediğiniz Windows 10 cihazları Microsoft Intune’a kayıtlı olmalıdır.

## Sürüm yükseltme ilkesi ayarları

|Ayar adı|Ayrıntılar|
|-|-|
|**Ad**|Sürüm yükseltme ilkesi için bir ad girin.|
|**Açıklama**|İsteğe bağlı olarak, Intune konsolunda ilkeyi tanımanıza yardımcı olacak bir açıklama girin.
|**Yükseltilecek sürüm**|Açılan listede, hedef cihazları yükseltmek istediğiniz Windows 10 Masaüstü, Windows 10 Holographic veya Windows 10 Mobile sürümünü seçin.
|**Ürün Anahtarı**|Microsoft’tan aldığınız ve tüm hedeflenen Windows 10 Masaüstü cihazlarını yükseltmek için kullanılabilen ürün anahtarını belirtin.<br>Ürün anahtarı içeren bir ilke oluşturduğunuzda, ürün anahtarını daha sonra düzenleyemezsiniz. Bunun nedeni, anahtarın güvenlik nedeniyle engellenmesidir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girmeniz gerekir.
|**Lisans Dosyası**|Microsoft’tan aldığınız ve hedeflenen cihazları yükseltmek istediğiniz Windows Holographic veya Windows 10 Mobile sürümünün lisans bilgilerini içeren lisans dosyasını seçmek için **Gözat**’ı seçin.

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO4-->


