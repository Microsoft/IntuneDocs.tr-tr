---
title: iOS çalıştıran cihazlar için Microsoft Intune giriş ekranı düzeni ayarları
titleSuffix: ''
description: iOS çalıştıran cihazlardaki giriş ekranını ve dock’u özelleştirmek için kullanabileceğiniz Microsoft Intune ayarları hakkında bilgi edinin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3361ce41dfa95de0cb1a7a3bdbdbd74e7d6d5edf
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-home-screen-layout-settings-for-devices-running-ios"></a>iOS çalıştıran cihazlar için Microsoft Intune giriş ekranı düzeni ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

iOS çalıştıran cihazların dock ve giriş ekranındaki uygulama düzenini ve klasörlerini yapılandırmak için bu ayarları kullanın.

Atanmış bir profile sahip iOS çalıştıran cihazlar denetimli modda olmalı ve iOS 9.3 veya daha yeni bir sürüm çalıştırmalıdır.

1. [Azure Portalı’nda Intune](https://portal.azure.com)’dan, cihaz yapılandırma alanındaki [**Cihaz özellikleri**’ne gidin](device-features-configure.md).
2. **Cihaz özellikleri** bölmesinde **Giriş Ekranı Düzeni (yalnızca denetimli)** seçeneğini belirleyin.
3. **Giriş Ekranı Düzeni (yalnızca denetimli)** bölmesinde, **Dock** veya **Sayfalar** düzenlerini yapılandırmak isteyip istemediğinizi seçin.

## <a name="add-items-to-the-dock"></a>Dock’a öğe ekleme

**Dock** bölmesinde, iOS ekranındaki dock kısmına en fazla altı öğe veya klasör ekleyebilirsiniz. Ancak birçok cihaz bundan daha az öğeyi destekler, örneğin iPhone cihazlar en fazla dört öğeyi destekler. Bu durumda, cihazda yalnızca yapılandırdığınız ilk dört öğe görüntülenecektir.

1. Dock’a öğe eklemek için **Ekle**’yi seçin.
2. **Satır Ekle** bölmesinde, **Uygulama** mı yoksa **Klasör** mü eklemek istediğinizi belirtin.
3. Bu konudaki bilgileri kullanarak dock kısmında görüntülenmesini istediğiniz uygulama ve klasörleri yapılandırın.
4. Öğeleri eklemeye devam edin. İşiniz bittiğinde **Profil Oluştur** bölmesine geri dönene kadar her bölmede **Tamam**’a tıklayın. **Oluştur**’u seçin.

>[!TIP]
> Öğeleri yeniden düzenlemek için herhangi bir Giriş ekranı ve sayfalar listesine sürükleyip bırakabilirsiniz.

### <a name="example"></a>Örnek

Bu örnekte, dock ekranını yalnızca Safari, Mail ve Borsa uygulamalarını göstermek üzere yapılandırdınız. Aşağıdaki resimde, Mail uygulaması özelliklerini göstermek için seçilmiştir:

![Örnek iOS dock ayarları](./media/FfFiUcP.png)

İlkeyi bir iPhone’a atadığınızda, sonuç şu ekran görüntüsündekine benzer bir dock olacaktır:

![iPhone’da örnek iOS dock düzeni](./media/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Giriş ekranı sayfaları ekleme

Giriş ekranında görünmesini istediğiniz sayfaları ve her sayfada görünecek uygulamaları ekleyin. Bir sayfaya ekleyeceğiniz uygulamalar, listede belirtildikleri sırada, soldan sağa düzenlenmiştir. Bir sayfaya alabileceğinden fazla uygulama eklerseniz fazla olanlar bir sonraki sayfaya taşınır.

1. **Sayfalar** bölmesinde **Ekle**’yi seçin.
2. **Satır Ekle** bölmesinde, bir **Sayfa adı** girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
3. **Ekle**’yi seçin ve ardından **Uygulama** veya **Klasör** seçiminizi belirtin.
4. Bu konudaki bilgileri kullanarak sayfada görüntülenmesini istediğiniz uygulama ve klasörleri yapılandırın.

### <a name="example"></a>Örnek

Bu örnekte **Contoso** adlı yeni bir sayfa yapılandırdınız. Sayfa yalnızca Arkadaşları Bul ve Ayarlar uygulamalarını gösterir. Aşağıdaki resimde, Ayarlar uygulaması özelliklerini göstermek için seçilmiştir:

![iOS Giriş ekranı ayarları örneği](./media/Jc2OxyX.png)

İlkeyi bir iPhone cihaza atadığınızda, sonuç şu ekran görüntüsündekine benzer bir sayfa olacaktır:

![Değiştirilmiş giriş ekranı ile iOS cihazı](./media/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Listeye uygulama ekleme

1. **Uygulama Adı** girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
2. Görüntülemek istediğiniz uygulamanın **Uygulama Paket Kimliği**’ni girin. Yardım için bu konu başlığının ileri bölümlerindeki **Yerleşik iOS uygulamaları için Paket Kimliği başvurusu** konusuna bakın.
3. **Tamam**’a tıklayın ve cihaz dock’ı için en fazla **6**, cihaz sayfası içinse en fazla **60** olacak şekilde öğe eklemeye devam edin.
4. İşiniz bittiğinde **Tamam**'a tıklayın.

## <a name="how-to-add-a-folder-to-the-list"></a>Listeye klasör ekleme

Bir klasördeki sayfaya ekleyeceğiniz uygulamalar, listede belirtildikleri sırada, soldan sağa düzenlenmiştir. Bir sayfaya alabileceğinden fazla uygulama eklerseniz fazla olanlar bir sonraki sayfaya taşınır.

1. **Klasör adı** girin. Bu ad, kullanıcıların cihazlarında görüntülenir.
2. Klasörde bir sayfa oluşturmak için **Ekle**’yi seçin. En fazla 20 sayfa ekleyebilirsiniz.
3. **Satır Ekle** bölmesinde, sayfa için bir ad girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
3. **Uygulama Adı** girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
2. Görüntülemek istediğiniz uygulamanın **Uygulama Paket Kimliği**’ni girin. Yardım için bkz. **Listeye uygulama ekleme**.
3. **Ekle**’yi seçin. En fazla 60 öğe ekleyebilirsiniz.
4. İşiniz bittiğinde **Tamam**'a tıklayın.


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


## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).
