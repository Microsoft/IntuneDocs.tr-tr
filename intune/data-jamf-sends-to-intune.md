---
title: JAMF Pro veri gönderen için Intune | Microsoft Intune
description: Jamf Pro Microsoft Intune gönderdiği verilerin listesi
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5b58a92ed59d4485f06370672d8c335ff2fffcc7
ms.sourcegitcommit: 7c41f42d6e398ed46aa602ec8aaa4f39aaf92772
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54325065"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Veri Jamf Pro'nın Intune'a gönderdiği

Kullanırken [Jamf Pro](https://www.jamf.com) , son kullanıcılar Mac bilgisayarları Intune ile yönetmek için Jamf Pro, yönetilen macOS cihazları hakkında Envanter bilgileri yakalar. Jamf Pro, Intune'a aşağıdaki bilgileri bildirir:

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
* Etki alanına katılma
* Jamf kimliği
* MAC adresi
* Yapın
* Model
* Model Tanımlayıcısı
* NIC Hızı
* Çekirdek Sayısı
* İşlemci Sayısı
* İşletim Sistemi
* Platform
* İşlemci Hızı
* İşlemci türü
* İkincil MAC Adresi
* Seri Numarası
* SMS Sürümü
* Toplam RAM
* UDID
* Kullanıcı E-postası


**Tüm cihazlar** görünümünde **Sil**’i seçerek Jamf tarafından yönetilen bir cihazı Intune konsolundan kaldırabilirsiniz. Toplu cihaz silme işlemi birden çok cihaz seçip **Sil**’e tıklayarak etkinleştirilebilir.

[Jamf ile yönetilen bir cihazı nasıl kaldıracağınız hakkında, Jamf Pro belgelerinden](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information) bilgi edinebilirsiniz. Daha fazla yardım için [Jamf destek](https://www.jamf.com/support/) ekibine bir destek bileti de gönderebilirsiniz. 

