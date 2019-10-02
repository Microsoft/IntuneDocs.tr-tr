---
title: Veri JAMF Pro, Intune 'a gönderir
titleSuffix: Microsoft Intune
description: JAMF Pro 'Yu Intune ile Mac yönetmek üzere tümleştirdiğinizde Microsoft Intune, JAMF Pro tarafından gönderilen veri listesini gözden geçirin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ce9a92a9fffad13c6723504735b1b1cb9442f61f
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729317"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Jamf Pro’nun Intune’a gönderdiği veriler

Intune ile son kullanıcılarınızın Mac 'nizi yönetmek için [JAMF Pro](https://www.jamf.com) kullandığınızda, JAMF Pro yönetilen MacOS cihazlarıyla ilgili envanter bilgilerini yakalar. 

## <a name="data"></a>Veri  
Jamf Pro, Intune'a aşağıdaki bilgileri bildirir:  

* Azure AD cihaz kimliği
* JAMF Envanter Durumu (son 24 saat içinde Jamf Pro ile kontrol edilen bir bilgisayar stok durumu)
* İşletim Sistemi Sürümü
* Azure AD cihaz kimliği
* Şifreli (FileVault 2)
* Ağ Geçidi Durumu
* Parola: minimum sayıda karakter kümesi
* Parola zaman aşımı (gün sayısı)
* Parola türü - basit, alfasayısal veya bilinmeyen
* Otomatik oturum açma engelleme
* Gerekli parola uzunluğu
* Parola: önceki parolaların yeniden kullanılmasını önlemek için önceki parola sayısı
* Sistem Bütünlüğü Koruması
* Son İade Zamanı
* Mimari Türü
* Kullanılabilir RAM Yuvaları
* Pil kapasitesi
* Önyükleme ROM'u
* Veri Yolu Hızı
* Önbellek Boyutu
* Cihaz adı
* Etki alanına ekleme
* Jamf kimliği
* MAC adresi
* Yapabilir
* Model
* Model Tanımlayıcısı
* NIC Hızı
* Çekirdek Sayısı
* İşlemci Sayısı
* İşletim sistemi
* Platfveyam
* İşlemci Hızı
* İşlemci türü
* İkincil MAC Adresi
* Seri Numarası
* SMS Sürümü
* Toplam RAM
* UDID
* Kullanıcı E-postası

**Tüm cihazlar** görünümünde **Sil**’i seçerek Jamf tarafından yönetilen bir cihazı Intune konsolundan kaldırabilirsiniz. Toplu cihaz silme işlemi birden çok cihaz seçip **Sil**’e tıklayarak etkinleştirilebilir.

## <a name="next-steps"></a>Sonraki adımlar
JAMF [Pro belgelerinden JAMF ile yönetilen bir cihazı kaldırma](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information)hakkında bilgi alın. Ek Yardım için [JAMF desteğiyle](https://www.jamf.com/support/) bir destek bileti de oluşturabilirsiniz. 

