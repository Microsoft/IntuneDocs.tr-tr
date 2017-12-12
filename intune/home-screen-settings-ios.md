---
title: "iOS cihazları için Intune Giriş ekranı düzen ayarları"
titlesuffix: Azure portal
description: "iOS cihazlarındaki giriş sayfasını ve dock’ı özelleştirmek için kullanabileceğiniz ayarları öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0dcc8f5509afa5308f8ae91a3d60ee081d5daa0b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>iOS cihazları için Intune Giriş ekranı düzen ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu ayarları, iOS'un dock ve Giriş ekranında uygulamaların ve klasörlerin yerleşimini yapılandırmak için kullanın.

Profili atadığınız iOS cihazlarının denetimli modda olması ve iOS 9.3 veya üzeri çalıştırması gerekir.

1. **Cihaz özellikleri** dikey penceresinde **Giriş Ekranı Düzeni (yalnızca denetimli)** seçeneğini belirtin.
2. **Giriş Ekranı Düzeni (yalnızca denetimli)** dikey penceresinde, **Dock** veya **Sayfalar** düzenlerini yapılandırmak isteyip istemediğinizi seçin.

## <a name="add-items-to-the-dock"></a>Dock’a öğe ekleme

**Dock** dikey penceresinde, iOS ekranındaki dock kısmına en fazla altı öğe veya klasör ekleyebilirsiniz. Ancak birçok cihaz bundan daha az öğeyi destekler, örneğin iPhone cihazlar en fazla dört öğeyi destekler. Bu durumda, cihazda yalnızca yapılandırdığınız ilk dört öğe görüntülenecektir.

1. Dock’a öğe eklemek için **Ekle**’yi seçin.
2. **Satır Ekle** dikey penceresinde, **Uygulama** veya **Klasör** seçiminizi belirtin.
3. Bu konudaki bilgileri kullanarak dock kısmında görüntülenmesini istediğiniz uygulama ve klasörleri yapılandırın.
4. Öğeleri eklemeye devam edin. İşiniz bittiğinde **Profil Oluştur** dikey penceresine geri dönene kadar her dikey pencerede **Tamam**’a tıklayın. **Oluştur**’u seçin.

>[!TIP]
> Öğeleri yeniden düzenlemek için herhangi bir Giriş ekranı ve sayfalar listesine sürükleyip bırakabilirsiniz. 

### <a name="example"></a>Örnek

Bu örnekte, dock ekranını yalnızca Safari, Mail ve Borsa uygulamalarını göstermek üzere yapılandırdınız. Aşağıdaki resimde, Mail uygulaması özelliklerini göstermek için seçilmiştir:

![Örnek iOS dock ayarları](http://i.imgur.com/FfFiUcP.png)

İlkeyi bir iPhone’a atadığınızda, sonuç şu ekran görüntüsündekine benzer bir dock olacaktır:

![iPhone’da örnek iOS dock düzeni](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Giriş ekranı sayfaları ekleme

Giriş ekranında görünmesini istediğiniz sayfaları ve her sayfada görünecek uygulamaları ekleyin. Bir sayfaya ekleyeceğiniz uygulamalar, listede belirtildikleri sırada, soldan sağa düzenlenmiştir. Bir sayfaya alabileceğinden fazla uygulama eklerseniz fazla olanlar bir sonraki sayfaya taşınır.


1. **Sayfalar** dikey penceresinde **Ekle**’yi seçin.
2. **Satır Ekle** dikey penceresinde, bir **Sayfa adı** girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
3. **Ekle**’yi seçin ve ardından **Uygulama** veya **Klasör** seçiminizi belirtin.
4. Bu konudaki bilgileri kullanarak sayfada görüntülenmesini istediğiniz uygulama ve klasörleri yapılandırın.

### <a name="example"></a>Örnek

Bu örnekte **Contoso** adlı yeni bir sayfa yapılandırdınız. Sayfa yalnızca Arkadaşları Bul ve Ayarlar uygulamalarını gösterir. Aşağıdaki resimde, Ayarlar uygulaması özelliklerini göstermek için seçilmiştir:

![iOS Giriş ekranı ayarları örneği](http://i.imgur.com/Jc2OxyX.png)

İlkeyi bir iPhone cihaza atadığınızda, sonuç şu ekran görüntüsündekine benzer bir sayfa olacaktır:

![Değiştirilmiş giriş ekranı ile iOS cihazı](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Listeye uygulama ekleme

1. **Uygulama Adı** girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
2. Görüntülemek istediğiniz uygulamanın **Uygulama Paket Kimliği**’ni girin. Yardım için bu konu başlığının ileri bölümlerindeki **Yerleşik iOS uygulamaları için Paket Kimliği başvurusu** konusuna bakın.
3. **Tamam**’a tıklayın ve cihaz dock’ı için en fazla **6**, cihaz sayfası içinse en fazla **60** olacak şekilde öğe eklemeye devam edin.
4. İşiniz bittiğinde **Tamam**'a tıklayın.

## <a name="how-to-add-a-folder-to-the-list"></a>Listeye klasör ekleme

Bir klasördeki sayfaya ekleyeceğiniz uygulamalar, listede belirtildikleri sırada, soldan sağa düzenlenmiştir. Bir sayfaya alabileceğinden fazla uygulama eklerseniz fazla olanlar bir sonraki sayfaya taşınır.

1. **Klasör adı** girin. Bu ad, kullanıcıların cihazlarında görüntülenir.
2. Klasörde bir sayfa oluşturmak için **Ekle**’yi seçin. En fazla 20 sayfa ekleyebilirsiniz.
3. **Satır Ekle** dikey penceresinde, bir sayfa adı girin. Bu ad, Azure portalında başvuru amacıyla kullanılır ve iOS cihazda *görüntülenmez*.
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
