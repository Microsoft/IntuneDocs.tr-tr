---
title: Windows 10 Şirket Portalı uygulamasını el ile ekleme
titleSuffix: Microsoft Intune
description: Windows 10 Şirket Portalı uygulamasını el ile eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a696dfa29504bda67c82ea8d792e01105ae71fe
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
6. Dosyayı yerel makinenize kaydetmek için **İndir**’i seçin.

    ![İndirme işlemi için seçili “Windows 10 tüm cihazlar” ve Mimari X86 paketi ayrıntıları](./media/Win10CP-all-devices.png)

7. **İndir**’i seçerek “Gerekli Çerçeveler” başlığı altındaki tüm paketleri indirin.  
    Bu eylem x86, x64 ve ARM mimarileri için gerçekleştirilmelidir. Yani toplam 12 paket gerekir.
8. Şirket Portalı uygulamasını Intune’a yüklemeden önce, paketlerin aşağıdaki şekilde yapılandırıldığı bir klasör (ör: C:\Şirket Portalı) oluşturun:
   - Şirket Portalı paketini C:\Company Portal adresine koyun. Bu konumda bir *Bağımlılıklar* alt klasörü oluşturun.  

     ![APPXBUN dosyasıyla kaydedilen Bağımlılıklar klasörünün görüntüsü](./media/Win10CP-Dependencies-save.png)

   - Bağımlılık paketlerini *Dependencies* klasörüne yerleştirin. 

     > [!NOTE]
     > Bağımlılıklar doğru biçimde yerleştirilmezse, Intune dosyaları tanıyamaz ve paket karşıya yükleme işlemi sırasında bunları karşıya yükleyemez. Bu durumda, karşıya yükleme başarısız olur ve bir hata görüntülenir.

9. Azure portalında Microsoft Intune’da Şirket Portalı uygulamasını yeni bir uygulama olarak karşıya yükleyin. 
10. Şirket Portalı uygulamasını, seçili hedef kullanıcılar kümenize gerekli uygulama olarak atayın.  

Intune’un Evrensel uygulamaların bağımlılıklarını nasıl işlediği hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune MDM aracılığıyla bağımlılıkları olan bir appxbundle dağıtma](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

## <a name="frequently-asked-questions"></a>Sık sorulan sorular 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Kullanıcılarım eski uygulamaları mağazadan zaten yüklemişlerse cihazlarında Şirket Portalı uygulamasını nasıl güncelleştirebilirim?
Kullanıcılarınız, Windows 8.1 veya Windows Phone 8.1 Şirket Portalı uygulamalarını Microsoft Store’dan zaten yüklemişlerse sizin ya da kullanıcınızın herhangi bir işlemde bulunmasına gerek kalmadan bu uygulamalar otomatik olarak en son sürüme güncelleştirilecektir. Bu güncelleştirme gerçekleşmezse, kullanıcılarınızdan cihazlarında Store uygulamaları için otomatik güncelleştirmeleri etkinleştirdiklerini doğrulamalarını isteyin.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenen Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows 8.1 Şirket Portalı uygulaması için atama eylemini **Kaldır** olarak ayarlayıp atamayı silmektir. Bu ayarı seçtikten sonra, yukarıda açıklanan seçeneklerden herhangi birini kullanarak Windows 10 Şirket Portalı uygulamasını atayabilirsiniz.  

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec Sertifikasıyla imzalamadan atadıysanız, yükseltmeyi tamamlamak için bu makalenin önceki bölümlerinde yer alan adımları tamamlayın.

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec kod imzalama sertifikası ile imzalayıp atadıysanız, sıradaki bölümde sunulan adımları izleyin.  

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

