---
title: "iOS cihazları için Intune uygulama bildirim ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS cihazlarındaki uygulamaların bildirimlerini denetlemek için kullanabileceğiniz ayarları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c64167275a2628c6a3a4e899e00c25df4c10b06b
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-app-notifications-settings-for-ios-devices"></a>iOS cihazları için Intune uygulama bildirim ayarları

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bir cihazda yüklü uygulamaların bildirimleri nasıl göndereceğini yapılandırmanıza olanak sağlar. Bu ayarlar, iOS 9.3 ve üzerini çalıştıran denetimli cihazları destekler.

## <a name="configure-settings"></a>Ayarları yapılandırma

1. **Cihaz özellikleri** dikey penceresinde **Uygulama Bildirimleri (yalnızca denetimli)** seçeneğini belirleyin.
2. **Uygulama Bildirimleri** dikey penceresinde, **Ekle**’yi seçin ve aşağıdaki değerleri yapılandırın:
    - **Uygulama paket kimliği** - Yapılandırmak istediğiniz uygulamanın **Uygulama Paket Kimliği**’ni girin. Yardım için bu konu başlığının ileri bölümlerindeki **Yerleşik iOS uygulamaları için Paket Kimliği başvurusu** konusuna bakın.
    - **Uygulama adı** - Yapılandırmak istediğiniz uygulamanın adını girin. Bu, cihazda görüntülenmez ve listedeki uygulamayı belirlemenize yardımcı olması için kullanılır.
    - **Yayımcı** - Yapılandırmak istediğiniz uygulama yayımcısının adını girin. Bu, cihazda görüntülenmez ve listedeki uygulamayı belirlemenize yardımcı olması için kullanılır.
    - **Bildirimler** - Uygulamanın cihaza bildirim göndermesini etkinleştirin veya devre dışı bırakın. Bu ayarı devre dışı bırakırsanız, aşağıdaki ayarlar da devre dışı bırakılır.
        - **Bildirim Merkezinde Göster** - Uygulamanın cihaz Bildirim Merkezinde bildirimler göstermesine izin vermek için etkinleştirin.
        - **Kilit Ekranında Göster** - Cihaz kilit ekranında uygulamanın bildirimlerini görmek için etkinleştirin.
        - **Uyarı türü** - Cihaz kilidi aşağıdakilerden açıldığında istediğiniz bildirim türlerini seçin:
            - **Hiçbiri** - Bildirim görüntülenmez.
            - **Başlık** - Bildirimi gösteren başlık kısaca görüntülenir.
            - **Kalıcı** - Bildirim görüntülenir ve kullanıcının cihazı kullanmaya devam etmesi için bunu el ile kapatması gerekir.
        - **Uygulama simgesi üzerinde rozet** - Uygulamanın bildirim gönderdiğini belirtmek üzere uygulama simgesine rozet eklemek için bunu etkinleştirin.
        - **Sesler** - Bir bildirim iletildiğinde ses çalınmasını etkinleştirin.
3. Gerektiği kadar uygulama eklemeye devam edin. İşiniz bittiğinde **Tamam**’ı seçin.
4. **Profil Oluştur** dikey penceresine dönene kadar **Tamam**’ı ve ardından **Oluştur**’u seçin. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için Paket Kimliği başvurusu

Bu liste, bazı yaygın yerleşik iOS uygulamalarının paket kimliğini gösterir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun. 

|||
|-|-|
|Uygulama adı|Paket Kimliği|
|Uygulama Mağazası|com.apple.AppStore|
|Hesap Makinesi|com.apple.calculator|
|Takvim|com.apple.mobilecal|
|Kamera|com.apple.camera|
|Saat|com.apple.mobiletimer|
|Pusula|com.apple.compass|
|Kişiler|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Arkadaşları Bul|com.apple.mobileme.fmf1|
|iPhone’u Bul|com.apple.mobileme.fmip1|
|Oyun Merkezi|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Sistem Durumu|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Harita|com.apple.Maps|
|İletiler|com.apple.MobileSMS|
|Müzik|com.apple.Music|
|News|com.apple.news|
|Notlar|com.apple.mobilenotes|
|Sayılar|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotoğraflar|com.apple.mobileslideshow|
|Podcast’ler|com.apple.podcasts|
|Anımsatıcılar|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Ayarlar|com.apple.Preferences|
|Borsa|com.apple.stocks|
|İpuçları|com.apple.tips|
|Videolar|com.apple.videos|
|Sesli Notlar|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Hava Durumu|com.apple.weather|
