---
title: Microsoft Intune-Azure 'da yerleşik uygulamalar için iOS paket kimlikleri | Microsoft Docs
titleSuffix: ''
description: Yerleşik iOS uygulamaları için paket kimliklerinin listesini görüntüleyin. Microsoft Intune ' deki cihaz yapılandırma profilleri ve ilkelerindeki uygulamalara açıkça izin vermek için bu paket kimliklerini kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/30/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1eda7fef3ee9c2ca4e4a13d9b6effba2ed121b0e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506964"
---
# <a name="bundle-ids-for-built-in-ios-apps-you-can-use-in-intune"></a>Intune 'da kullanabileceğiniz yerleşik iOS uygulamaları için paket kimlikleri

İOS cihazlarında özellikleri yapılandırdığınızda, iOS cihazlarına yerleşik uygulamaları da ekleyebilirsiniz. Bu makalede, bazı yaygın yerleşik iOS uygulamalarının paket kimlikleri listelenir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun. Apple 'ın [iOS paket kimlikleri](https://support.apple.com/guide/mdm/ios-bundle-ids-mdm90f60c1ce/web) listesine bakın (Apple 'ın Web sitesini açar).

## <a name="bundle-ids"></a>Paket kimlikleri

| Paket Kimliği                   | Uygulama Adı     | Publisher |
|-----------------------------|--------------|-----------|
| com. Apple. Store             | Uygulama Mağazası    | Apple     |
| com.apple.calculator        | Hesap Makinesi   | Apple     |
| com.apple.mobilecal         | Takvim     | Apple     |
| com.apple.camera            | Kamera       | Apple     |
| com.apple.mobiletimer       | Saat        | Apple     |
| com. Apple. Clip             | İniz        | Apple     |
| com.apple.compass           | Pusula      | Apple     |
| com.apple.MobileAddressBook | Kişiler     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | dosyalarý        | Apple     |
| com.apple.mobileme.fmf1     | Arkadaşları Bul | Apple     |
| com.apple.mobileme.fmip1    | iPhone’u Bul  | Apple     |
| com.apple.gamecenter        | Oyun Merkezi  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Sistem Durumu       | Apple     |
| com.apple.Home              | Giriş         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Harita         | Apple     |
| com.apple.MobileSMS         | İletiler     | Apple     |
| com.apple.Music             | Müzik        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Notlar        | Apple     |
| com.apple.Numbers           | Sayılar      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com. Apple. mobilephone       | Numarası        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotoğraflar       | Apple     |
| com.apple.podcasts          | Podcast’ler     | Apple     |
| com.apple.reminders         | Anımsatıcılar    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Ayarlar     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Borsa       | Apple     |
| com.apple.tips              | İpuçları         | Apple     |
| com.apple.tv                | TV           | Apple     |
| com.apple.videos            | Videolar       | Apple     |
| com.apple.VoiceMemos        | Sesli Notlar   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | Hava Durumu      | Apple     |      

## <a name="next-steps"></a>Sonraki adımlar

Bu paket kimliklerini, [cihaz özelliklerini](ios-device-features-settings.md) yapılandırmak ve iOS cihazlarında [bazı ayarlara izin vermek veya kısıtlamak](device-restrictions-ios.md) için kullanın.
