---
# required metadata

title: Microsoft Intune’da Windows sürümünü yükseltme ilkesi ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Windows sürümünü yükseltme ilkesi ayarları
Microsoft Intune **Sürüm Yükseltme İlkesi**, aşağıdaki Windows 10 sürümlerinden birini çalıştıran cihazları daha yeni bir sürüme otomatik olarak yükseltmenizi sağlar:
* Windows 10 Masaüstü
* Windows 10 Holographic

## Başlamadan önce
Cihazları en son sürüme yükseltmeye başlamadan önce aşağıdakilerden birine sahip olmanız gerekir:
* İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için geçerli olan bir ürün anahtarı (Windows 10 Masaüstü sürümleri için)
* İlkeyle hedeflediğiniz tüm cihazlara Windows’un yeni sürümünü yüklemek için gerekli lisans bilgilerini içeren bir Microsoft lisans dosyası (Windows 10 Mobile ve Windows 10 Holographic sürümleri için).
* Hedeflediğiniz Windows 10 cihazlarının Microsoft Intune’a kayıtlı olması gerekir.

## Sürüm yükseltme ilkesi ayarları

|Ayar adı|Ayrıntılar|
|-|-|
|**Ad**|Sürüm yükseltme ilkesi için bir ad girin.|
|**Açıklama**|İsteğe bağlı olarak, Intune konsolunda ilkeyi tanımanıza yardımcı olacak bir açıklama girin.
|**Yükseltilecek sürüm**|Açılan listede, hedef cihazları yükseltmek istediğiniz Windows 10 Masaüstü, Windows 10 Holographic veya Windows 10 Mobile sürümünü seçin.
|**Ürün Anahtarı**|Microsoft’tan aldığınız ve tüm hedeflenen Windows 10 Masaüstü cihazlarını yükseltmek için kullanılabilen ürün anahtarını belirtin.<br>Ürün anahtarı içeren bir ilke oluşturduğunuzda, ürün anahtarını daha sonra düzenleyemezsiniz. Bunun nedeni, anahtarın güvenlik nedeniyle engellenmesidir. Ürün anahtarını değiştirmek için tüm anahtarı yeniden girmeniz gerekir.
|**Lisans Dosyası**|Microsoft’tan aldığınız ve hedeflenen cihazları yükseltmek istediğiniz Windows Holographic sürümünün lisans bilgilerini içeren lisans dosyasını seçmek için **Gözat**’a tıklayın.

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

<!--HONumber=May16_HO1-->

