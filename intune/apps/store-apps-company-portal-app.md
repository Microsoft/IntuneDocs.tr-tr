---
title: Windows 10 Şirket Portalı uygulamasını el ile ekleme
titleSuffix: Microsoft Intune
description: İş gücünüzün Windows 10 Şirket Portalı uygulamasını Microsoft Store BILGISAYARA nasıl el ile ekleyebileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32411e513cec9683faf598c8d73d6d803bcddb3d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507116"
---
# <a name="manually-add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Kullanıcılarınız, cihaz yönetmek ve uygulama yüklemek için Intune Şirket Portalı uygulamasını Microsoft Mağazası’ndan kendileri yükleyebilirler. Şirketiniz, Şirket Portalı uygulamasını kullanıcılara sizin atamanızı gerektiriyorsa Windows 10 Şirket Portalı uygulamasını doğrudan Intune’dan el ile atayabilirsiniz. Intune ile İş İçin Microsoft Store’u tümleştirmediyseniz bile bunu yapabilirsiniz.

 > [!NOTE]
 > Bu makalede açıklanan seçenek, bir uygulama güncelleştirmesi yayımlandığında bunları her seferinde el ile atamanızı gerektirir.

## <a name="configure-settings-to-show-offline-apps"></a>Çevrimdışı uygulamaları göstermek için ayarları yapılandırma
1. [İş için Microsoft Store](https://www.microsoft.com/business-store)’da yönetici hesabınızla oturum açın.
2. Pencerenin üst kısmında **Yönet** sekmesini seçin.
3. Sol bölmede **Ayarlar**’ı seçin.
4. **Alışveriş deneyimi** altında **Çevrimdışı uygulamaları göster** seçeneğini **Açık** olarak ayarlayın.  
    Çevrimdışı lisanslı uygulamalar görüntülenir.

## <a name="download-the-offline-company-portal-app"></a>Çevrimdışı Şirket Portalı uygulamasını indirme
1. **Şirket Portalı** uygulamasını arayın ve seçin.
2. **Lisans türü** olarak **Çevrimdışı** ayarlayın.
3. Çevrimdışı Şirket Portalı uygulamasını almak ve envanterinize eklemek için **Uygulamayı al**’ı seçin.
4. **Şirket Portalı** uygulama sayfasında **Yönet**’i seçin.
5. **Platform** olarak **Windows 10 tüm cihazlar**’ı seçin ve ardından uygun **En düşük sürüm**, **Mimari** ve **Uygulama indirme meta verileri** değerlerini seçin. 
6. Dosyayı yerel makinenize kaydetmek için **paket ayrıntıları** altında **İndir** ' i seçin.

    ![Mimari x86 'ya eşit olan Windows 10 cihazları seçilidir](./media/app-sideload-windows/Win10CP-all-devices.png)

7. **İndir**’i seçerek “Gerekli Çerçeveler” başlığı altındaki tüm paketleri indirin.  

    Bu eylemin x86, x64 ve ARM mimarileri için tamamlanması gerekir:<br> 
    *En düşük işletim sistemi sürümü olarak 1507 ' i seçerken, 1511 ' i seçerken 12 paket ve 1607 seçilirken 15 paket olan 9 gerekli çerçeve paketi vardır.*

8. Azure portalında Microsoft Intune’da Şirket Portalı uygulamasını yeni bir uygulama olarak karşıya yükleyin. Uygulama **Ekle** bölmesinde Uygulama **türü** olarak iş kolu uygulaması ' nı seçerek uygulamayı eklersiniz. Ardından uygulama paketi dosyasını (uzantısı) seçersiniz. Appxdemeti).

9. **Bağımlılık uygulama dosyalarını Seç** ' in altında, adım 7 ' de indirdiğiniz tüm bağımlılıkları Shift tuşuna basarak seçin ve **eklenen** sütunun, ihtiyacınız olan mimarilere göre **Evet** görüntülendiğini doğrulayın.

     > [!NOTE]
     > Bağımlılıklar eklenmemişse, uygulama belirtilen cihaz türlerine yüklenemeyebilir.

10. **Tamam**' a tıklayın, Istenen **uygulama bilgilerini**girin ve **Ekle**' ye tıklayın.

11. Şirket Portalı uygulamasını seçtiğiniz kullanıcı veya cihaz grupları kümesine gerekli bir uygulama olarak atayın.  

Intune’un Evrensel uygulamaların bağımlılıklarını nasıl işlediği hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune MDM aracılığıyla bağımlılıkları olan bir appxbundle dağıtma](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

## <a name="frequently-asked-questions"></a>Sık sorulan sorular 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Kullanıcılarım eski uygulamaları mağazadan zaten yüklemişlerse cihazlarında Şirket Portalı uygulamasını nasıl güncelleştirebilirim?
Kullanıcılarınız, Windows 8.1 veya Windows Phone 8.1 Şirket Portalı uygulamalarını Microsoft Store’dan zaten yüklemişlerse sizin ya da kullanıcınızın herhangi bir işlemde bulunmasına gerek kalmadan bu uygulamalar otomatik olarak en son sürüme güncelleştirilecektir. Bu güncelleştirme gerçekleşmezse, kullanıcılarınızdan cihazlarında Store uygulamaları için otomatik güncelleştirmeleri etkinleştirdiklerini doğrulamalarını isteyin.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenen Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows 8.1 Şirket Portalı uygulaması için atama eylemini **Kaldır** olarak ayarlayıp atamayı silmektir. Bu ayarı seçtikten sonra, yukarıda açıklanan seçeneklerden herhangi birini kullanarak Windows 10 Şirket Portalı uygulamasını atayabilirsiniz.  

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec Sertifikasıyla imzalamadan atadıysanız, yükseltmeyi tamamlamak için bu makalenin önceki bölümlerinde yer alan adımları tamamlayın.

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı uygulamasını Symantec kod imzalama sertifikası ile imzalayıp atadıysanız, sıradaki bölümde sunulan adımları izleyin.

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenmiş ve imzalı Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulaması için atama eylemini **Kaldır** şeklinde ayarlayarak mevcut atamayı silmektir. Bu ayarı seçtikten sonra Windows 10 Şirket Portalı uygulamasını normal şekilde atayabilirsiniz.  

Aksi takdirde, yükseltme yoluna uyulduğundan emin olmak için Windows 10 Şirket Portalı uygulamasının uygun şekilde güncelleştirilmesi ve imzalanması gerekir.  

Windows 10 Şirket Portalı uygulamasını bu şekilde imzalar ve atarsanız, mağazada kullanıma sunulan her yeni uygulama güncelleştirmesi için bu işlemi tekrarlamanız gerekecektir. Mağaza güncelleştirildiğinde uygulama otomatik olarak güncelleştirilmez.  

Uygulamanın bu şekilde nasıl imzalanıp atanacağı aşağıda açıklanmaktadır:

1. [Microsoft Intune Windows 10 Şirket Portalı Uygulaması İmzalama Betiği](https://aka.ms/win10cpscript)’ni indirin.  
    Bu betik, Windows 10 için Windows SDK’nın ana bilgisayara yüklenmiş olmasını gerektirir. [Windows 10 için Windows SDK’sını indirin](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Windows 10 Şirket Portalı uygulamasını yukarıda açıklandığı biçimde İş İçin Microsoft Store’dan indirin.  
3. Windows 10 Şirket Portalı uygulamasını imzalamak için aşağıda gösterildiği şekilde betik üst bilgisinde açıklanan giriş parametrelerini kullanıp betiği çalıştırın.  
    Bağımlılıkların betiğe geçirilmesi gerekmez. Bunlar, yalnızca uygulama Intune Yönetici Konsolu’na yüklenirken gereklidir.

| Parametre |  Description  |
|---|---|
| InputWin10AppxBundle  |  Kaynak appxbundle dosyasının yolu. |
| OutputWin10AppxBundle | İmzalı appxbundle dosyası için çıkış yolu. 
| Win81Appx  | Windows 8.1 veya Windows Phone 8.1 Şirket Portalı (.APPX) dosyasının yolu. |
| PfxFilePath  |  Symantec Enterprise Mobil Kod İmza Sertifikası (.PFX) dosyasının yolu.  |
| PfxPassword  | Symantec Enterprise Mobil Kod İmza Sertifikası’nın parolası. |
| PublisherId | Kuruluşun Yayımcı Kimliği. Bu yoksa, Symantec Kurumsal Mobil Kod İmzalama Sertifikası’nın Konu alanı kullanılır. |
| SdkPath | Windows 10 için Windows SDK’sı kök klasörünün yolu. Bu bağımsız değişken isteğe bağlıdır ve varsayılan olarak ${env:ProgramFiles(x86)}\Windows Kits\10 şeklindedir.  |

Betik, çalışması tamamlandığında Windows 10 Şirket Portalı uygulamasının imzalı sürümünü çıktı olarak sunar. Ardından Intune aracılığıyla uygulamanın imzalı sürümünü bir iş kolu (LOB) uygulaması olarak atayabilirsiniz. Böylece atanmış durumdaki sürümler, bu yeni uygulamaya yükseltilir.  

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
