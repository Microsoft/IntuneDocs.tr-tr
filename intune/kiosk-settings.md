---
title: Microsoft Intune'da Windows 10 için bilgi noktası ayarları - Azure | Microsoft Docs
description: Windows 10 (ve sonrası) cihazlarınızı başlat menüsü özelleştirme, uygulama ekleme, görev çubuğu ve bir web tarayıcısı yapılandırma da dahil olmak üzere tekli uygulama veya çoklu uygulama bilgi noktaları olarak yapılandırın. Ayrıca, Microsoft Intune’da Windows Holographic for Business cihazlarını çoklu uygulama bilgi noktası olarak yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7552c9c1fa8e94560505a8971143886160cff6ce
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185969"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Intune’da Windows 10 (ve sonrası) için bilgi noktası ayarları

Windows 10 cihazlarda Intune kullanarak cihazları bilgi noktası olarak çalıştırabilirsiniz. Bilgi noktası, tek bir uygulama veya birkaç uygulama çalıştırabilir. Ayrıca bir başlat menüsü gösterme ve özelleştirme, Win32 uygulamaları dahil farklı uygulamalar ekleme, bir Web tarayıcısına belirli bir giriş sayfası ekleme gibi pek çok şey yapabilirsiniz. 

Bu makaledeki adımları kullanarak Intune’da tekli uygulama bilgi noktası veya çoklu uygulama bilgi noktası oluşturabilirsiniz.

Intune, cihaz başına bir bilgi noktası profili destekler. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir [Özel OMA-URI](custom-settings-windows-10.md) kullanabilirsiniz.

## <a name="kiosk-settings"></a>Bilgi noktası ayarları

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: **Windows 10 ve üzeri**’ni seçin
   - **Profil türü**: **Bilgi Noktası (Önizleme)** seçin

4. Bir **bilgi noktası modu** seçin. **Bilgi noktası modu**, ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

    - **Yapılandırılmamış** (varsayılan): İlke, bilgi noktası modunu etkinleştirmez.
    - **Tekli uygulama, tam ekran bilgi noktası**: Cihaz tek kullanıcı hesabı olarak çalışır ve tek bir Mağaza uygulamasına kilitlenir. Dolayısıyla kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
    - **Çoklu uygulama bilgi noktası**: Cihaz, Uygulama Kullanıcı Modeli Kimliği (AUMID) kullanarak birden fazla Store, Win32 veya Windows uygulaması çalıştırır. Cihazda yalnızca eklediğiniz uygulamalar kullanılabilir.

        Çok uygulamalı bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak kullanıcılara anlaşılması kolay bir deneyim sunmasıdır. Bir de ihtiyaçları olmayan uygulamaları görünümden kaldırmasıdır.

## <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları
Tekli uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamalar, girdiğiniz kullanıcı hesabı olarak çalışır. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10 sürüm 1803 ve sonrası)**: Kullanıcının oturum açmasını gerektirmeyen, genel kullanıma açık ortamlardaki bilgi noktaları içindir, konuk hesabına benzerdir. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: Cihaz için yerel kullanıcı hesabını girin. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.

- **Uygulama türü**: **Mağaza uygulaması**’nı seçin.

- **Bilgi noktası modunda çalışacak uygulama**: **Bir mağaza uygulaması ekle**’yi seçin ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

- **Bilgi noktası tarayıcı ayarları**: Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Store’dan [Bilgi noktası tarayıcı uygulamasını](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) edindiğinize, Intune’a [İstemci Uygulaması](apps-add.md) olarak eklediğinize ve uygulamayı bilgi noktası cihazlarına atadığınıza emin olun.

  Aşağıdaki ayarları girin:

  - **Varsayılan giriş sayfası URL’si**: Bilgi noktası tarayıcısı açıldığında veya yeniden başlatıldığında gösterilen varsayılan URL’yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

  - **Giriş düğmesi**: Bilgi noktası tarayıcısının giriş düğmesini **gösterin** veya **gizleyin**. Varsayılan olarak düğme gösterilmez.

  - **Gezinti düğmeleri**: İleri ve geri düğmelerini **gösterin** veya **gizleyin**. Varsayılan olarak gezinti düğmeleri gösterilmez.

  - **Oturumu sonlandır düğmesi**: Oturumu sonlandır düğmesini **gösterin** veya **gizleyin**. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

  - **Boşta kalma süresi geçince tarayıcıyı yenile**: Bilgi noktası tarayıcısı temiz bir durumda yeniden başlatılana kadar geçecek oturum başka kalma süresini (1-1440 dakika) girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

  - **İzin verilen web siteleri**: Belirli Web sitelerinin açılmasına izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `http://contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.
 
      Belirli web sitelerine izin vermek için izin verilecek web sitelerini ayrı satırlarda listeleyen bir dosyayı karşıya yükleyin. Bir dosya eklemezseniz tüm web sitelerine izin verilir. Intune, joker karakter olarak * (yıldız işareti) destekler.

      Örnek dosyanız, aşağıdaki listeye benzer görünmelidir:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır.

Çoklu uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **S modu cihazlarında Windows 10 hedefle**: Bilgi noktası profilinde mağaza uygulamaları ve AUMID uygulamalarına (Win32 uygulamaları harici) izin vermek için **Evet**’i seçin. Bilgi noktası profilinde mağaza uygulamaları, Win32 uygulamaları ve AUMID uygulamalarına izin vermek için **Hayır**’ı seçin. **Hayır**’ı seçtiğinizde bilgi noktası profili S modu cihazlarına dağıtılmaz.

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamalar, girdiğiniz kullanıcı hesabı olarak çalışır. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10 sürüm 1803 ve sonrası)**: Kullanıcının oturum açmasını gerektirmeyen, genel kullanıma açık ortamlardaki bilgi noktaları içindir, konuk hesabına benzerdir. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: Cihaz için yerel kullanıcı hesabını **ekleyin**. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.
  - **Azure Active Directory kullanıcı veya grubu (Windows 10 sürüm 1803 ve sonrası)**: **Ekle**’ye tıklayarak listeden Azure Active Directory kullanıcıları veya grupları seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçisi**: Ziyaretçi hesabı, [paylaşılan PC modu kavramlarında](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) anlatıldığı gibi, kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir konuk hesabıdır.

- **Uygulamalar**: Bilgi noktası cihazında çalışacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Mağaza uygulaması ekle**: İş İçin Microsoft Store’dan bir uygulama ekleyin. Listede hiç uygulama yoksa uygulama edilebilir ve [bunları Intune’a ekleyebilirsiniz](store-apps-windows.md). Örneğin Bilgi Noktası Tarayıcısı, Excel, OneNote gibi pek çok uygulama ekleyebilirsiniz.

  - **Win32 uygulaması ekle**: Win32 uygulamaları, Visual Studio Code veya Google Chrome gibi geleneksel masaüstü uygulamalarıdır. Aşağıdaki özellikleri girin:

    - **Uygulama adı**: Gereklidir. Uygulama için bir ad girin.
    - **Yerel yol**: Gereklidir. Yürütülebilir dosyanın yolunu girin, örneğin `C:\Program Files (x86)\Microsoft VS Code\Code.exe` veya `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Uygulama kullanıcı modeli kimliği (AUMID)**: Win32 uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu ayar, masaüstündeki kutucuk başlangıç düzenini belirler. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Kutucuk boyutu**: Gereklidir. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.
  
  - **AUMID’e göre ekle**: Notepad veya Hesap Makinesi gibi gelen kutusu Windows uygulamalarını eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin: 

    - **Uygulama adı**: Gereklidir. Uygulama için bir ad girin.
    - **Uygulama kullanıcı modeli kimliği (AUMID)**: Gereklidir. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Kutucuk boyutu**: Gereklidir. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

  > [!TIP]
  > Tüm uygulamaları ekledikten sonra tıklayıp sürükleme yoluyla listedeki uygulamaların görüntülenme sırasını değiştirebilirsiniz.  

  Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

- **Bilgi noktası tarayıcı ayarları**: Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Bilgi noktasına web tarayıcısı uygulamasını [İstemci Uygulamaları](apps-add.md)’nı kullanarak dağıttığınıza emin olun.

  Aşağıdaki ayarları girin:

  - **Varsayılan giriş sayfası URL’si**: Bilgi noktası tarayıcısı açıldığında veya yeniden başlatıldığında gösterilen varsayılan URL’yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

  - **Giriş düğmesi**: Bilgi noktası tarayıcısının giriş düğmesini **gösterin** veya **gizleyin**. Varsayılan olarak düğme gösterilmez.

  - **Gezinti düğmeleri**: İleri ve geri düğmelerini **gösterin** veya **gizleyin**. Varsayılan olarak gezinti düğmeleri gösterilmez.

  - **Oturumu sonlandır düğmesi**: Oturumu sonlandır düğmesini **gösterin** veya **gizleyin**. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

  - **Boşta kalma süresi geçince tarayıcıyı yenile**: Bilgi noktası tarayıcısı temiz bir durumda yeniden başlatılana kadar geçecek oturum başka kalma süresini (1-1440 dakika) girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

  - **İzin verilen web siteleri**: Belirli Web sitelerinin açılmasına izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.

    Belirli Web sitelerine izin vermek için izin verilen Web siteleri listesini içeren bir .csv dosyasını karşıya yükleyin. Bir .csv dosyası eklemezseniz tüm Web sitelerine izin verilir.

  Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

- **Alternatif Başlangıç menüsü düzeni kullan**: Uygulamaların sırası da dahil olmak üzere Başlat menüsünde nasıl göründüğünü açıklayan bir XML dosyası girmek için **Evet**’i seçin. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

- **Windows Görev Çubuğu**: Görev çubuğunu **Göstermeyi** veya **Gizlemeyi** seçin. Varsayılan olarak görev çubuğu gösterilmez.

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business cihazlarında, bu cihazları tekli uygulama bilgi noktası modunda veya çoklu uygulama bilgi noktası modunda çalıştırılacak şekilde yapılandırabilirsiniz. Bazı özellikler, Windows Holographic for Business’ta desteklenmez.

#### <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları
Tekli uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Kullanıcı oturum açma türü**: Cihaz için yerel kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili Microsoft Hesabı’nı (MSA) girmek için **Yerel kullanıcı hesabı**’nı seçin. **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.

- **Uygulama türü**: **Mağaza uygulaması**’nı seçin.

- **Bilgi noktası modunda çalışacak uygulama**: **Bir mağaza uygulaması ekle**’yi seçin ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

#### <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları
Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır. Çoklu uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **S modu cihazlarında Windows 10’u hedefle**: **Hayır**’ı seçin. S modu, Windows Holographic for Business’ta desteklenmez.

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamaları kullanabilecek bir veya birden çok kullanıcı hesabı belirtin. Seçenekleriniz şunlardır: 

  - **Otomatik oturum açma**: Windows Holographic for Business’ta desteklenmez.
  - **Yerel kullanıcı hesapları**: Cihaz için yerel kullanıcı hesabını **ekleyin**. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.
  - **Azure Active Directory kullanıcı veya grubu (Windows 10, sürüm 1803 ve sonrası)**: Cihazda oturum açmak için kullanıcı kimlik bilgilerini gerektirir. Listeden Azure Active Directory kullanıcılarını veya gruplarını seçmek için **Ekle**’yi seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçisi**: Ziyaretçi hesabı, [paylaşılan PC modu kavramlarında](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) anlatıldığı gibi, kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir konuk hesabıdır.

- **Uygulamalar**: Bilgi noktası cihazında çalışacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Store uygulamaları ekle**: [İstemci Uygulamaları](apps-add.md)’nı kullanarak eklediğiniz mevcut uygulamalardan birini seçin. Listede hiç uygulama yoksa uygulama edilebilir ve [bunları Intune’a ekleyebilirsiniz](store-apps-windows.md).
  - **Win32 uygulaması ekle**: Windows Holographic for Business’ta desteklenmez.
  - **AUMID’e göre ekle**: Gelen kutusu Windows uygulamalarını eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin: 

    - **Uygulama adı**: Gereklidir. Uygulama için bir ad girin.
    - **Uygulama kullanıcı modeli kimliği (AUMID)**: Gereklidir. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Kutucuk boyutu**: Gereklidir. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

- **Bilgi noktası tarayıcı ayarları**: Windows Holographic for Business’ta desteklenmez.

- **Alternatif Başlangıç menüsü düzeni kullan**: Uygulamaların sırası da dahil olmak üzere Başlat menüsünde nasıl göründüğünü açıklayan bir XML dosyası girmek için **Evet**’i seçin. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens), Windows Holographic for Business cihazları için rehberlik sağlar ve belirli bir XML dosyası içerir.

- **Windows Görev Çubuğu**: Windows Holographic for Business’ta desteklenmez.



## <a name="next-steps"></a>Sonraki adımlar
[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
