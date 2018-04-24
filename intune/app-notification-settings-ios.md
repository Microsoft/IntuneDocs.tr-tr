---
title: Microsoft Intune - Azure'da iOS cihazları için uygulama bildirimleri oluşturma | Microsoft Docs
description: Microsoft Intune'da iOS cihazları için uygulama bildirimleri ekleyin veya oluşturun. Hangi uygulamaların bildirim göndereceğini seçin, kilit ekranındaki bildirim ayarlarını yapılandırın, sesi etkinleştirin, uyarı türünü seçin ve gösterge ekleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 43068163c15c0588a8a6ef745d5b191f4547a94d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>Intune'da iOS cihazlarındaki uygulama bildirimi ayarlarını yapılandırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

iOS cihazında yüklü olan uygulamaların nasıl bildirim göndereceğini yapılandırın. Bu ayarlar, iOS 9.3 ve üzerini çalıştıran denetimli cihazları destekler.

## <a name="add-the-app-notification"></a>Uygulama bildirimi ekleme

1. [Azure Portal](https://portal.azure.com)’da oturum açın.
2. iOS veya macOS profilinde **Cihaz özellikleri**'ni seçin. [iOS veya macOS cihaz özellikleri](device-features-configure.md) altında profil oluşturma adımları listelenir.
3. **Uygulama Bildirimleri (yanızca denetimli)** öğesini ve ardından **Ekle**'yi seçin: ![Intune'da iOS veya macOS profiline uygulama bildirimi ekleme](./media/ios-macos-app-notifications.png)
4. Aşağıdaki özellikleri girin:

   - **Uygulama paket kimliği**: Yapılandırmak istediğiniz uygulamanın **Uygulama Paket Kimliği**’ni girin. **Yerleşik iOS uygulamaları için Paket Kimliği başvurusu**  (bu makalede) biraz yardım sağlar.
   - **Uygulama adı**: Yapılandırmak istediğiniz uygulamanın adını girin. Bu ad cihazda görüntülenmez ve listedeki uygulamayı belirlemenize yardımcı olmak için kullanılır.
   - **Yayımcı**: Yapılandırmak istediğiniz uygulama yayımcısının adını girin. Bu yayımcı adı cihazda görüntülenmez ve yalnızca listedeki uygulamayı belirlemenize yardımcı olmak için kullanılır.
   - **Bildirimler**: Uygulamanın cihaza bildirim göndermesini etkinleştirin veya devre dışı bırakın. Bu ayarı devre dışı bırakırsanız, aşağıdaki ayarlar da devre dışı bırakılır.
     - **Bildirim Merkezi’nde Göster** - Bu ayarı uygulamanın cihaz Bildirim Merkezi’nde bildirim göstermesine izin vermek için etkinleştirin.
     - **Kilit Ekranında Göster** - Bu ayarı cihaz kilitleme ekranında uygulama bildirimlerini görmek için etkinleştirin.
     - **Uyarı türü** - Cihaz kilidi aşağıdakilerden açıldığında istediğiniz bildirim türlerini seçin:
       - **Hiçbiri** - Bildirim görüntülenmez.
       - **Başlık** - Bildirimi gösteren başlık kısaca görüntülenir.
       - **Kalıcı** - Bildirim görüntülenir ve kullanıcının cihazı kullanmaya devam etmesi için bunu el ile kapatması gerekir.
     - **Uygulama simgesi üzerindeki rozet** - Bu ayarı uygulamanın bildirim gönderdiğini belirtmek üzere uygulama simgesine rozet eklemek için etkinleştirin.
     - **Sesler** - Bu ayarı bir bildirim iletildiğinde ses çalınması için etkinleştirin.

5. Gerektiği kadar uygulama eklemeye devam edin. Uygulamaları eklemeyi bitirdiğinizde **Tamam**'ı seçin.
6. Profilinizi kaydetmek için **Oluştur**’u seçin.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için Paket Kimliği başvurusu

Aşağıdaki liste, bazı yaygın yerleşik iOS uygulamalarının paket kimliğini gösterir. Diğer uygulamaların paket kimliğini bulmak için en iyi yöntem yazılım satıcınıza başvurmaktır.

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

## <a name="next-steps"></a>Sonraki adımlar

Seçtiğiniz gruplara cihaz profilini atayın. Adımlar, [Cihaz profilleri atama](device-profile-assign.md) altında listelenir.