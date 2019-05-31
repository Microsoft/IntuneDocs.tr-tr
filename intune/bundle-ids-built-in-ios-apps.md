---
title: iOS için Microsoft Intune - Azure'da yerleşik uygulama kimlikleri paket | Microsoft Docs
titleSuffix: ''
description: Yerleşik iOS uygulamaları için paket kimliklerinin bir listesini görürsünüz. Bu paket kimliklerini açıkça uygulamalarında cihaz yapılandırma profilleri ve ilkeleri Microsoft Intune izin vermek için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/30/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ff5b411f14fef4ad294b0dd8b265680fd67df08
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402758"
---
# <a name="bundle-ids-for-built-in-ios-apps-you-can-use-in-intune"></a>Intune'da kullanabileceğiniz yerleşik iOS uygulamaları için paket kimlikleri

İOS cihazlarda özellik yapılandırmak, iOS cihazlarda yerleşik uygulamaları da ekleyebilirsiniz. Bu makalede, paket kimlikleri bazı yaygın yerleşik iOS uygulamalarının listelenmektedir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun. Apple'nın listesini [iOS paket kimlikleri](https://support.apple.com/guide/mdm/ios-bundle-ids-mdm90f60c1ce/web) (Apple web sitesini açar).

## <a name="bundle-ids"></a>Paket kimlikleri

| Paket Kimliği                   | Uygulama Adı     | Yayımcı |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Uygulama Mağazası    | Apple     |
| com.apple.calculator        | Hesap Makinesi   | Apple     |
| com.apple.mobilecal         | Takvim     | Apple     |
| com.apple.camera            | Kamera       | Apple     |
| com.apple.mobiletimer       | Saat        | Apple     |
| com.apple.compass           | Pusula      | Apple     |
| com.apple.MobileAddressBook | Kişiler     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | Dosyalar        | Apple     |
| com.apple.mobileme.fmf1     | Arkadaşları Bul | Apple     |
| com.apple.mobileme.fmip1    | iPhone’u Bul  | Apple     |
| com.apple.gamecenter        | Oyun Merkezi  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Durum       | Apple     |
| com.apple.Home              | Ana Sayfası         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Haritalar         | Apple     |
| com.apple.MobileSMS         | İletiler     | Apple     |
| com.apple.Music             | Müzik        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Notlar        | Apple     |
| com.apple.Numbers           | Sayılar      | Apple     |
| com.apple.Pages             | Sayfaları        | Apple     |
| com.apple.mobilephone       | Phone        | Apple     |
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
| com.apple.Bridge            | İzleme        | Apple     |
| com.apple.weather           | Hava durumu      | Apple     |

## <a name="next-steps"></a>Sonraki adımlar

Bu paket kimliklerini yapılandırmak için kullanmayı [cihaz özellikleri](ios-device-features-settings.md) ve [izin vermek veya bazı ayarları kısıtlamak](device-restrictions-ios.md) iOS cihazlarda.
