---
title: Microsoft Intune'da Windows 10 için bilgi noktası ayarları - Azure | Microsoft Docs
description: Tek uygulama ve çoklu uygulama bilgi noktaları Windows 10 (ve üzeri) cihazlarınızı yapılandırmak, Başlat menüsünü özelleştirmek, uygulama ekleme, görev çubuğunu göster ve bir web tarayıcısı yapılandırın. Ayrıca, Microsoft Intune’da Windows Holographic for Business cihazlarını çoklu uygulama bilgi noktası olarak yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: 353c18affa41e56501a76bf695f95cbe95796e99
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203476"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Intune kullanarak atanmış bilgi noktası çalıştırmak için Windows 10 (ve üzeri) cihaz ayarları

Windows 10 cihazlarda, bazen bir adanmış cihaz olarak bilinen bir bilgi noktası olarak çalıştıran cihazlar için Intune kullanın. Bir cihaz bilgi noktası modunda, bir uygulama çalıştırmasına veya birçok uygulaması çalıştırın. Göster ve Başlat menüsü özelleştirme, Win32 uygulamaları dahil olmak üzere farklı uygulama, ekleme, bir web tarayıcısı ve daha fazla bilgi için belirli bir giriş sayfası ekleyin. 

Bu makalede, listeler ve Windows 10 ve üzeri cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bilgi noktası modunda çalıştırmak için Windows 10 cihazlarınızı yapılandırmak için bu ayarları kullanın.

Intune, cihaz başına bir bilgi noktası profili destekler. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir [Özel OMA-URI](custom-settings-windows-10.md) kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-profile-create.md).

## <a name="kiosk-settings"></a>Bilgi noktası ayarları

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Seçin **Windows 10 ve üzeri**
   - **Profil türü**: Seçin **bilgi noktası**

4. Bir **bilgi noktası modu** seçin. **Bilgi noktası modu**, ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

    - **Yapılandırılmamış** (varsayılan): Bilgi noktası modu ilke sağlamaz.
    - **Tek bir uygulama, tam ekran bilgi noktası**: Cihaz, tek bir kullanıcı hesabı çalışır ve tek bir Store uygulaması için kilitler. Dolayısıyla kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
    - **Çoklu uygulama bilgi noktası**: Cihaz, uygulama kullanıcı modeli kimliği (AUMID'yi) kullanarak, birden çok Store uygulamaları Win32 uygulamaları veya gelen Windows uygulamaları çalıştırır. Cihazda yalnızca eklediğiniz uygulamalar kullanılabilir.

        Çok uygulamalı bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak kullanıcılara anlaşılması kolay bir deneyim sunmasıdır. Bir de ihtiyaçları olmayan uygulamaları görünümden kaldırmasıdır.

## <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları
Tekli uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Kullanıcı oturum açma türü**: Girdiğiniz kullanıcı hesabı eklediğiniz uygulamalar çalıştırın. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10, 1803 ve sonraki sürümleri)**: Ortak ortamlardaki bilgi noktaları için, benzer bir Konuk hesabı ile oturum açmasını gerektirmez. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: Yerel (cihaz) kullanıcı hesabını girin. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.

- **Uygulama türü**: Seçin **app Store**.

- **Bilgi noktası modunda çalıştırmak için uygulama**: Seçin **bir mağaza uygulaması ekleme**ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

- **Bilgi noktası tarayıcı ayarlarını**: Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Size unutmayın [bilgi noktası tarayıcı uygulamasını](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) ıntune'a eklemek Store bir [istemci uygulaması](apps-add.md)ve ardından uygulama bilgi noktası cihazlarına atayabilirsiniz.

  Aşağıdaki ayarları girin:

  - **Varsayılan giriş sayfası URL'si**: Bilgi noktası tarayıcı açıldığında veya tarayıcı yeniden başlatıldığında gösterilen varsayılan URL'yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

  - **Giriş düğmesi**: **Göster** veya **Gizle** bilgi noktası tarayıcı giriş düğmesi. Varsayılan olarak düğme gösterilmez.

  - **Gezinti düğmelerini**: **Göster** veya **Gizle** İleri ve geri düğmeleri. Varsayılan olarak gezinti düğmeleri gösterilmez.

  - **Son oturum düğmesi**: **Göster** veya **Gizle** sonu oturumu düğmesi. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

  - **Boşta kalma süresinden sonra tarayıcıyı yenileyin**: Bilgi noktası tarayıcı içinde yeni bir duruma yeniden başlatılana kadar (1-1440 dakika) boşta geçen süreyi girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

  - **Web siteleri izin**: Açmak belirli Web sitelerine izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `http://contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.
 
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

- **Windows 10 S modu cihazları hedefleyen**: Seçin **Evet** mağazası uygulamaları ve AUMID'sini uygulamaları (Win32 uygulamaları hariç) bilgi noktası profilinde izin vermek için. Bilgi noktası profilinde mağaza uygulamaları, Win32 uygulamaları ve AUMID uygulamalarına izin vermek için **Hayır**’ı seçin. **Hayır**’ı seçtiğinizde bilgi noktası profili S modu cihazlarına dağıtılmaz.

- **Kullanıcı oturum açma türü**: Girdiğiniz kullanıcı hesabı eklediğiniz uygulamalar çalıştırın. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10, 1803 ve sonraki sürümleri)**: Ortak ortamlardaki bilgi noktaları için, benzer bir Konuk hesabı ile oturum açmasını gerektirmez. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: **Ekleme** yerel (cihaz) kullanıcı hesabı. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.
  - **Azure AD kullanıcısı veya grubu (Windows 10, 1803 ve sonraki sürümleri)**: Listeden Azure Active Directory kullanıcılarını veya gruplarını seçmek için **Ekle**’yi seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçi**: Ziyaretçi herhangi bir kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir Konuk hesabı bölümünde anlatıldığı gibi hesaptır [PC modu kavramları paylaşılan](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Uygulamaları**: Bilgi noktası cihazda çalıştırılacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Mağaza uygulaması ekleme**: Uygulama, iş için Microsoft Store ' ekleyin. Listede hiç uygulama yoksa uygulama edilebilir ve [bunları Intune’a ekleyebilirsiniz](store-apps-windows.md). Örneğin Bilgi Noktası Tarayıcısı, Excel, OneNote gibi pek çok uygulama ekleyebilirsiniz.

  - **Win32 uygulaması Ekle**: Visual Studio Code veya Google Chrome gibi geleneksel bir masaüstü uygulaması bir Win32 uygulamasıdır. Aşağıdaki özellikleri girin:

    - **Uygulama adı**: Gerekli. Uygulama için bir ad girin.
    - **Yerel yol**: Gerekli. Yürütülebilir dosyanın yolunu girin, örneğin `C:\Program Files (x86)\Microsoft VS Code\Code.exe` veya `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Uygulama kullanıcı modeli kimliği (AUMID'sini)**: Win32 uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu ayar, masaüstündeki kutucuk başlangıç düzenini belirler. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).
    - **Döşeme boyutu**: Gerekli. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.
  
  - **Tarafından AUMID'sini ekleme**: Not Defteri veya hesap makinesi gibi gelen Windows uygulama eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin: 

    - **Uygulama adı**: Gerekli. Uygulama için bir ad girin.
    - **Uygulama kullanıcı modeli kimliği (AUMID'sini)**: Gerekli. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Döşeme boyutu**: Gerekli. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

  > [!TIP]
  > Tüm uygulamaları ekledikten sonra tıklayıp sürükleme yoluyla listedeki uygulamaların görüntülenme sırasını değiştirebilirsiniz.  

  Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

- **Bilgi noktası tarayıcı ayarlarını**: Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Bilgi noktasına web tarayıcısı uygulamasını [İstemci Uygulamaları](apps-add.md)’nı kullanarak dağıttığınıza emin olun.

  Aşağıdaki ayarları girin:

  - **Varsayılan giriş sayfası URL'si**: Bilgi noktası tarayıcı açıldığında veya tarayıcı yeniden başlatıldığında gösterilen varsayılan URL'yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

  - **Giriş düğmesi**: **Göster** veya **Gizle** bilgi noktası tarayıcı giriş düğmesi. Varsayılan olarak düğme gösterilmez.

  - **Gezinti düğmelerini**: **Göster** veya **Gizle** İleri ve geri düğmeleri. Varsayılan olarak gezinti düğmeleri gösterilmez.

  - **Son oturum düğmesi**: **Göster** veya **Gizle** sonu oturumu düğmesi. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

  - **Boşta kalma süresinden sonra tarayıcıyı yenileyin**: Bilgi noktası tarayıcı içinde yeni bir duruma yeniden başlatılana kadar (1-1440 dakika) boşta geçen süreyi girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

  - **Web siteleri izin**: Açmak belirli Web sitelerine izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.

    Belirli Web sitelerine izin vermek için izin verilen Web siteleri listesini içeren bir .csv dosyasını karşıya yükleyin. Bir .csv dosyası eklemezseniz tüm Web sitelerine izin verilir.

  Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

- **Kullanım alternatif başlangıç düzeni**: Seçin **Evet** sırasını uygulamaları dahil olmak üzere, Başlat menüsünde uygulamaları nasıl göründüğünü açıklayan bir XML dosyası girmek için. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

- **Windows görev çubuğunda**: Tercih **Göster** veya **Gizle** görev. Varsayılan olarak görev çubuğu gösterilmez.

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business cihazlarında, bu cihazları tekli uygulama bilgi noktası modunda veya çoklu uygulama bilgi noktası modunda çalıştırılacak şekilde yapılandırabilirsiniz. Bazı özellikler, Windows Holographic for Business’ta desteklenmez.

#### <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları
Tekli uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Kullanıcı oturum açma türü**: Seçin **yerel kullanıcı hesabı** yerel (cihaz) kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili bir Microsoft hesabı (MSA) hesabı girmek için. **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.

- **Uygulama türü**: Seçin **app Store**.

- **Bilgi noktası modunda çalıştırmak için uygulama**: Seçin **bir mağaza uygulaması ekleme**ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

#### <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları
Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır. Çoklu uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Windows 10 S modu cihazları hedefleyen**: Seçin **Hayır**. S modu, Windows Holographic for Business üzerinde desteklenmiyor.

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamaları kullanabilecek bir veya daha fazla kullanıcı hesaplarını ekleyin. Seçenekleriniz şunlardır: 

  - **Otomatik oturum açma**: Windows Holographic for Business üzerinde desteklenmiyor.
  - **Yerel kullanıcı hesapları**: **Ekleme** yerel (cihaz) kullanıcı hesabı. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.
  - **Azure AD kullanıcısı veya grubu (Windows 10, 1803 ve sonraki sürümleri)**: Cihaza oturum açmak için kullanıcı kimlik bilgilerini gerektirir. Listeden Azure Active Directory kullanıcılarını veya gruplarını seçmek için **Ekle**’yi seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçi**: Ziyaretçi herhangi bir kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir Konuk hesabı bölümünde anlatıldığı gibi hesaptır [PC modu kavramları paylaşılan](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Uygulamaları**: Bilgi noktası cihazda çalıştırılacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Store uygulamaları ekleme**: Eklenen kullanarak mevcut bir uygulamayı seçtiğinizden [istemci uygulamaları](apps-add.md). Listede hiç uygulama yoksa uygulama edilebilir ve [bunları Intune’a ekleyebilirsiniz](store-apps-windows.md).
  - **Win32 uygulaması Ekle**: Windows Holographic for Business üzerinde desteklenmiyor.
  - **Tarafından AUMID'sini ekleme**: Gelen kutusu Windows uygulama eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin: 

    - **Uygulama adı**: Gerekli. Uygulama için bir ad girin.
    - **Uygulama kullanıcı modeli kimliği (AUMID'sini)**: Gerekli. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Döşeme boyutu**: Gerekli. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

- **Bilgi noktası tarayıcı ayarlarını**: Windows Holographic for Business üzerinde desteklenmiyor.

- **Kullanım alternatif başlangıç düzeni**: Seçin **Evet** sırasını uygulamaları dahil olmak üzere, Başlat menüsünde uygulamaları nasıl göründüğünü açıklayan bir XML dosyası girmek için. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens), Windows Holographic for Business cihazları için rehberlik sağlar ve belirli bir XML dosyası içerir.

- **Windows görev çubuğunda**: Windows Holographic for Business üzerinde desteklenmiyor.

## <a name="next-steps"></a>Sonraki adımlar
[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Bilgi noktası profilleri de oluşturabilirsiniz [Android](device-restrictions-android.md#kiosk) ve [Android Kurumsal](device-restrictions-android-for-work.md#kiosk-settings) cihazlar.
