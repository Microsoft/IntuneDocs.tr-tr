---
title: Microsoft Intune'da Windows 10 için bilgi noktası ayarları - Azure | Microsoft Docs
description: Tek uygulama ve çoklu uygulama bilgi noktaları Windows 10 (ve üzeri) cihazlarınızı yapılandırmak, Başlat menüsünü özelleştirmek, uygulama ekleme, görev çubuğunu göster ve bir web tarayıcısı Intune yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/11/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0e83e371f5c3d1690cc50c6b250db8a2c3251b48
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394963"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows 10 ve üzeri cihaz ayarları ıntune'da bilgi noktası olarak çalıştırmak için

Windows 10 ve üzeri cihazlarda, bu cihazların tek uygulama bilgi noktası modu veya çoklu uygulama bilgi noktası modunda çalıştırmak için yapılandırabilirsiniz.

Bu makalede, listeler ve Windows 10 ve üzeri cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, Windows 10 ve üzeri cihazları bilgi noktası modunda çalışacak şekilde yapılandırmak için bu ayarları kullanın.

Bir Intune Yöneticisi olarak oluşturun ve bu ayarlar, cihazlara atayın.

Intune'da Windows bilgi noktası özelliği hakkında daha fazla bilgi için bkz. [bilgi noktası ayarları yapılandırma](kiosk-settings.md).

## <a name="before-you-begin"></a>Başlamadan önce

- [Profil oluşturma](kiosk-settings.md#create-the-profile).

- Bu bilgi noktası profil oluşturma kullanarak cihaz kısıtlama profiline doğrudan ilgili [Microsoft Edge bilgi noktası ayarları](device-restrictions-windows-10.md#microsoft-edge-browser). Özetlersek:

  1. Cihaz bilgi noktası modunda çalıştırmak için bu bilgi noktası profili oluşturun.
  2. Oluşturma [cihaz kısıtlama profilindeki](device-restrictions-windows-10.md#microsoft-edge-browser)ve belirli özellikler ve Microsoft Edge'de izin ayarlarını yapılandırın.

> [!IMPORTANT] 
> Bu kiosk profili aynı cihaz olarak atadığınızdan emin olun, [Microsoft Edge profili](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları

Yalnızca bir uygulama cihazda çalışır.

- **Bilgi noktası modu**: Seçin **tek bir uygulama, tam ekran bilgi noktası**.

- **Kullanıcı oturum açma türü**: Girdiğiniz kullanıcı hesabı eklediğiniz uygulamalar çalıştırın. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10, 1803 ve sonraki sürümleri)**: Benzer bir Konuk hesabı ile oturum açmasını gerektirmeyen ortak ortamlardaki bilgi noktaları için kullanabilirsiniz. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: Yerel (cihaz) kullanıcı hesabını girin. Hesap oturum açtığında için bilgi girin.

- **Uygulama türü**: Uygulama türünü seçin. Seçenekleriniz şunlardır:

  - **Microsoft Edge tarayıcısı ekleme**: Seçin **Microsoft Edge tarayıcısı**ve **kenar bilgi noktası modu türünü**:

    - **Sayısal/etkileşimli Tabela**: URL tam ekranı açılır ve yalnızca bu Web sitesinde içerik gösterir. [Dijital ayarlanan](https://docs.microsoft.com/windows/configuration/setup-digital-signage) bu özellik hakkında daha fazla bilgi sağlar.
    - **Genel (InPrivate) gözatma**: Microsoft Edge sınırlı bir çoklu sekme sürümünü çalıştırır. Kullanıcılar genel göz atın veya kendi tarayıcı oturumunu sona erdirme.

    Bu seçenekler hakkında daha fazla bilgi için bkz. [Microsoft Edge dağıtma bilgi noktası modu](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Bu ayar, cihazda Microsoft Edge tarayıcısı sağlar. Microsoft Edge özgü ayarları yapılandırmak için bir cihaz yapılandırma profili oluşturma (**cihaz Yapılandırması** > **profilleri** > **profilioluşturma**  >  **Windows 10** Platform > **cihaz kısıtlamaları** >  **Microsoft Edge tarayıcı**). [Microsoft Edge tarayıcısı](device-restrictions-windows-10.md#microsoft-edge-browser) listelenir ve kullanılabilir ayarlar açıklanır.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **Bilgi noktası tarayıcı ekleme**: Seçin **bilgi noktası tarayıcı ayarlarını**. Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Size unutmayın [bilgi noktası tarayıcı uygulamasını](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) ıntune'a eklemek Store bir [istemci uygulaması](apps-add.md)ve ardından uygulama bilgi noktası cihazlarına atayabilirsiniz.

    Aşağıdaki ayarları girin:

    - **Varsayılan giriş sayfası URL'si**: Bilgi noktası tarayıcı açıldığında veya tarayıcı yeniden başlatıldığında gösterilen varsayılan URL'yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

    - **Giriş düğmesi**: **Göster** veya **Gizle** bilgi noktası tarayıcı giriş düğmesi. Varsayılan olarak düğme gösterilmez.

    - **Gezinti düğmelerini**: **Göster** veya **Gizle** İleri ve geri düğmeleri. Varsayılan olarak gezinti düğmeleri gösterilmez.

    - **Son oturum düğmesi**: **Göster** veya **Gizle** sonu oturumu düğmesi. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

    - **Boşta kalma süresinden sonra tarayıcıyı yenileyin**: Bilgi noktası tarayıcı içinde yeni bir duruma yeniden başlatılana kadar (1-1440 dakika) boşta geçen süreyi girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

    - **Web siteleri izin**: Açmak belirli Web sitelerine izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `http://contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.

      Belirli web sitelerine izin vermek için izin verilecek web sitelerini ayrı satırlarda listeleyen bir dosyayı karşıya yükleyin. Bir dosya eklemezseniz tüm web sitelerine izin verilir. Intune destekler `*` (yıldız işareti) bir joker.

      Örnek dosyanız, aşağıdaki listeye benzer görünmelidir:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **App Store ekleme**: Seçin **bir mağaza uygulaması ekleme**ve bir uygulamayı listeden seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

  Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır. Bir uygulamanın başka bir uygulama üzerinde bir bağımlılık varsa, izin verilen uygulamalar listesinde eklenmelidir. Örneğin, hem "C:\Program Files\internet explorer\iexplore.exe" ve "C:\Program Files (x86) \Internet" izin için Internet Explorer 64-bit Internet Explorer 32-bit üzerinde bağımlılığı vardır. 

- **Bilgi noktası modu**: Seçin **çoklu uygulama bilgi noktası**.

- **Windows 10 S modu cihazları hedefleyen**:
  - **Evet**: Mağaza uygulamaları ve AUMID'sini uygulamalar (Win32 uygulamaları hariç) bilgi noktası profilinde izin verir.
  - **Hayır**: Mağaza uygulamaları ve Win32 uygulamaları AUMID'sini uygulamaları bilgi noktası profilinde sağlar. Bu bilgi noktası profilini S modu cihazlara dağıttığınız değil.

- **Kullanıcı oturum açma türü**: Girdiğiniz kullanıcı hesabı eklediğiniz uygulamalar çalıştırın. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10, 1803 ve sonraki sürümleri)**: Benzer bir Konuk hesabı ile oturum açmasını gerektirmeyen ortak ortamlardaki bilgi noktaları için kullanabilirsiniz. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: **Ekleme** yerel (cihaz) kullanıcı hesabı. Hesap oturum açtığında için bilgi girin.
  - **Azure AD kullanıcısı veya grubu (Windows 10, 1803 ve sonraki sürümleri)**: Seçin **Ekle**, Azure AD kullanıcı veya Grup listesinden seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçi**: Ziyaretçi herhangi bir kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir Konuk hesabı bölümünde anlatıldığı gibi hesaptır [PC modu kavramları paylaşılan](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Tarayıcı ve uygulamaları**: Bilgi noktası cihazda çalıştırılacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Tarayıcılar**

    - **Microsoft Edge ekleme**: Microsoft Edge uygulama kılavuza eklenir ve tüm uygulamalar, bu bilgi noktası üzerinde çalıştırabilirsiniz. Seçin **Microsoft Edge bilgi noktası modu türünü**:

      - **Normal moda (tam sürümünü Microsoft Edge)**: Microsoft Edge sürümü tam tarama tüm özellikleriyle çalışır. Kullanıcı verileri ve durum oturumları arasında kaydedilir.
      - **Genel (InPrivate) gözatma**: Tam ekran modunda çalışan bilgi noktaları için özel olarak uyarlanmış bir deneyim ile çoklu sekme sürümünü Microsoft Edge InPrivate çalıştırır.

      Bu seçenekler hakkında daha fazla bilgi için bkz. [Microsoft Edge dağıtma bilgi noktası modu](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Bu ayar, cihazda Microsoft Edge tarayıcısı sağlar. Microsoft Edge özgü ayarları yapılandırmak için bir cihaz yapılandırma profili oluşturma (**cihaz Yapılandırması** > **profilleri** > **profilioluşturma**  >  **Windows 10** Platform > **cihaz kısıtlamaları** >  **Microsoft Edge tarayıcı**). [Microsoft Edge tarayıcısı](device-restrictions-windows-10.md#microsoft-edge-browser) listelenir ve kullanılabilir ayarlar açıklanır.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Bilgi noktası tarayıcı ekleme**: Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. Bilgi noktasına web tarayıcısı uygulamasını [İstemci Uygulamaları](apps-add.md)’nı kullanarak dağıttığınıza emin olun.

      Aşağıdaki ayarları girin:

      - **Varsayılan giriş sayfası URL'si**: Bilgi noktası tarayıcı açıldığında veya tarayıcı yeniden başlatıldığında gösterilen varsayılan URL'yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

      - **Giriş düğmesi**: **Göster** veya **Gizle** bilgi noktası tarayıcı giriş düğmesi. Varsayılan olarak düğme gösterilmez.

      - **Gezinti düğmelerini**: **Göster** veya **Gizle** İleri ve geri düğmeleri. Varsayılan olarak gezinti düğmeleri gösterilmez.

      - **Son oturum düğmesi**: **Göster** veya **Gizle** sonu oturumu düğmesi. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

      - **Boşta kalma süresinden sonra tarayıcıyı yenileyin**: Bilgi noktası tarayıcı içinde yeni bir duruma yeniden başlatılana kadar (1-1440 dakika) boşta geçen süreyi girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

      - **Web siteleri izin**: Açmak belirli Web sitelerine izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.

        Belirli Web sitelerine izin vermek için izin verilen Web siteleri listesini içeren bir .csv dosyasını karşıya yükleyin. Bir .csv dosyası eklemezseniz tüm Web sitelerine izin verilir.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

  - **Uygulamaları**

    - **Mağaza uygulaması ekleme**: Uygulama, iş için Microsoft Store ' ekleyin. Listede hiç uygulama yoksa uygulama edilebilir ve [bunları Intune’a ekleyebilirsiniz](store-apps-windows.md). Örneğin Bilgi Noktası Tarayıcısı, Excel, OneNote gibi pek çok uygulama ekleyebilirsiniz.

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Win32 uygulaması Ekle**: Visual Studio Code veya Google Chrome gibi geleneksel bir masaüstü uygulaması bir Win32 uygulamasıdır. Aşağıdaki özellikleri girin:

      - **Uygulama adı**: Gerekli. Uygulama için bir ad girin.
      - **Yerel yol**: Gerekli. Yürütülebilir dosyanın yolunu girin, örneğin `C:\Program Files (x86)\Microsoft VS Code\Code.exe` veya `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Uygulama kullanıcı modeli kimliği (AUMID'sini)**: Win32 uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu ayar, masaüstündeki kutucuk başlangıç düzenini belirler. Bu kimliği almak için bkz: [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Tarafından AUMID'sini ekleme**: Not Defteri veya hesap makinesi gibi gelen Windows uygulama eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin:

      - **Uygulama adı**: Gerekli. Uygulama için bir ad girin.
      - **Uygulama kullanıcı modeli kimliği (AUMID'sini)**: Gerekli. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

      Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

    - **Döşeme boyutu**: Gerekli. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

  > [!TIP]
  > Tüm uygulamaları ekledikten sonra tıklayıp sürükleme yoluyla listedeki uygulamaların görüntülenme sırasını değiştirebilirsiniz.  

- **Kullanım alternatif başlangıç düzeni**: Seçin **Evet** sırasını uygulamaları dahil olmak üzere, Başlat menüsünde uygulamaları nasıl göründüğünü açıklayan bir XML dosyası girmek için. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

- **Windows görev çubuğunda**: Tercih **Göster** veya **Gizle** görev. Varsayılan olarak görev çubuğu gösterilmez. Wi-Fi simgesi gibi simgeler gösterilir, ancak ayarlar son kullanıcılar tarafından değiştirilemez.

- **İndirilenler klasöründen erişmesine izin vermek**: Seçin **Evet** kullanıcıların indirmeler klasörü Windows Gezgini'nde erişmesine izin vermek için. Varsayılan olarak, indirmeler klasörüne erişimi devre dışıdır. Bu özellik, son kullanıcılar için bir tarayıcıdan indirilen öğelere erişmek için yaygın olarak kullanılır.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Bilgi noktası profilleri de oluşturabilirsiniz [Android](device-restrictions-android.md#kiosk), [Android Kurumsal](device-restrictions-android-for-work.md#dedicated-device-settings), ve [Windows Holographic for Business](kiosk-settings-holographic.md) cihazlar.
