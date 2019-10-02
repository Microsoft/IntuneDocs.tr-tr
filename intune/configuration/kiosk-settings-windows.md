---
title: Microsoft Intune'da Windows 10 için bilgi noktası ayarları - Azure | Microsoft Docs
description: Windows 10 (ve sonraki) cihazlarınızı tek uygulama ve çoklu uygulama kiisleri olarak yapılandırın, Başlat menüsünü özelleştirin, uygulamalar ekleyin, görev çubuğunu görüntüleyin ve Microsoft Intune bir Web tarayıcısını yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c2a94253934454bc9e176db8de0eec2454ddfee0
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730581"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Intune 'da bilgi noktası olarak çalıştırılacak Windows 10 ve üzeri cihaz ayarları

Windows 10 ve üzeri cihazlarda, bu cihazları tek uygulama bilgi noktası modunda veya çok uygulama bilgi noktası modunda çalışacak şekilde yapılandırabilirsiniz.

Bu makalede, Windows 10 ve üzeri cihazlarda denetleyebilmeniz için farklı ayarlar listelenmektedir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, Windows 10 ve üzeri cihazlarınızı bilgi noktası modunda çalışacak şekilde yapılandırmak için bu ayarları kullanın.

Bir Intune Yöneticisi olarak bu ayarları oluşturabilir ve cihazlarınıza atayabilirsiniz.

Intune 'da Windows bilgi noktası özelliği hakkında daha fazla bilgi edinmek için bkz. [bilgi noktası ayarlarını yapılandırma](../kiosk-settings.md).

## <a name="before-you-begin"></a>Başlamadan önce

- [Profili oluşturun](kiosk-settings.md#create-the-profile).

- Bu bilgi noktası profili, [Microsoft Edge bilgi noktası ayarları](device-restrictions-windows-10.md#microsoft-edge-browser)kullanılarak oluşturduğunuz cihaz kısıtlamaları profiliyle doğrudan ilgilidir. Özetlemek için:

  1. Bu bilgi noktası profilini, cihazı bilgi noktası modunda çalıştırmak için oluşturun.
  2. [Cihaz kısıtlamaları profilini](device-restrictions-windows-10.md#microsoft-edge-browser)oluşturun ve Microsoft Edge 'de izin verilen belirli özellikleri ve ayarları yapılandırın.

> [!IMPORTANT]
> Bu bilgi noktası profilini [Microsoft Edge profilinizle](device-restrictions-windows-10.md#microsoft-edge-browser)aynı cihazlara atadığınızdan emin olun.

## <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları

Cihazda yalnızca bir uygulama çalıştırır.

- **Bilgi noktası modu seçin**: **tek uygulama, tam ekran bilgi noktası**seçin.

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamalar, girdiğiniz kullanıcı hesabı olarak çalışır. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10 sürüm 1803 ve üzeri)** : bir Konuk hesabına benzer şekilde, kullanıcının oturum açmasını gerektirmeyen, genel kullanıma yönelik ortamlarda bilgi noktaları üzerinde kullanın. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: Cihaz için yerel kullanıcı hesabını girin. Girdiğiniz hesap, bilgi noktasında oturum açar.

- **Uygulama türü**: uygulama türünü seçin. Seçenekleriniz şunlardır:

  - **Microsoft Edge tarayıcısı Ekle**: **Microsoft Edge tarayıcısı**' nı seçin ve **uç bilgi noktası modu türünü**seçin:

    - **Dijital/Etkileşimli imza**: bir URL tam ekran açar ve yalnızca o Web sitesindeki içeriği gösterir. [Dijital Işaretleri ayarla](https://docs.microsoft.com/windows/configuration/setup-digital-signage) özelliği, bu özellik hakkında daha fazla bilgi sağlar.
    - **Genel göz atma (InPrivate)** : Microsoft Edge 'in sınırlı bir çok sekmeli sürümünü çalıştırır. Kullanıcılar herkese açık bir şekilde göz atabilir veya gözatma oturumlarını sonlandırabilir.

    Bu seçenekler hakkında daha fazla bilgi için bkz. [Microsoft Edge bilgi noktası modunu dağıtma](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Bu ayar cihazda Microsoft Edge tarayıcısını sunar. Microsoft Edge 'e özgü ayarları yapılandırmak için bir cihaz yapılandırma**profili oluşturun (** **cihaz yapılandırma** > **profiller** >  > platform Için  > **Windows 10** **cihaz kısıtlamaları**  >  **Microsoft Edge tarayıcısı**). [Microsoft Edge tarayıcısı](device-restrictions-windows-10.md#microsoft-edge-browser) , kullanılabilir ayarları listeler ve açıklar.

  - **Bilgi noktası tarayıcısı Ekle**: **bilgi noktası tarayıcı ayarları**' nı seçin. Bu ayarlar bilgi noktasındaki web tarayıcısı uygulamasını denetler. [Bilgi noktası tarayıcı uygulamasını](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) mağazadan aldığınızdan emin olun, bunu bir [Istemci uygulaması](../apps/apps-add.md)olarak Intune 'a ekleyin. Ardından, uygulamayı bilgi noktası cihazlarına atayın.

    Aşağıdaki ayarları girin:

    - **Varsayılan giriş sayfası URL’si**: Bilgi noktası tarayıcısı açıldığında veya yeniden başlatıldığında gösterilen varsayılan URL’yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

    - **Giriş düğmesi**: Bilgi noktası tarayıcısının giriş düğmesini **gösterin** veya **gizleyin**. Varsayılan olarak düğme gösterilmez.

    - **Gezinti düğmeleri**: İleri ve geri düğmelerini **gösterin** veya **gizleyin**. Varsayılan olarak gezinti düğmeleri gösterilmez.

    - **Oturumu sonlandır düğmesi**: Oturumu sonlandır düğmesini **gösterin** veya **gizleyin**. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

    - **Boşta kalma süresi geçince tarayıcıyı yenile**: Bilgi noktası tarayıcısı temiz bir durumda yeniden başlatılana kadar geçecek oturum başka kalma süresini (1-1440 dakika) girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

    - **İzin verilen web siteleri**: Belirli Web sitelerinin açılmasına izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `http://contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.

      Belirli web sitelerine izin vermek için izin verilecek web sitelerini ayrı satırlarda listeleyen bir dosyayı karşıya yükleyin. Bir dosya eklemezseniz tüm web sitelerine izin verilir. Intune, joker karakter olarak `*` (yıldız işareti) destekler.

      Örnek dosyanız, aşağıdaki listeye benzer görünmelidir:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`

    > [!NOTE]
    > Microsoft bilgi noktası tarayıcısı kullanılarak otomatik oturum açma özelliği etkinleştirilmiş Windows 10 kiosks, Microsoft Store Iş için çevrimdışı bir lisans kullanmalıdır. Bu gereksinim, otomatik oturum açma 'nın Azure Active Directory (AD) kimlik bilgileri olmayan bir yerel kullanıcı hesabı kullanması nedeniyle oluşur. Bu nedenle, çevrimiçi lisanslar değerlendirilemiyor. Daha fazla bilgi için bkz. [çevrimdışı uygulamaları dağıtma](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Mağaza uygulaması ekleme**: **Mağaza uygulaması Ekle**' yi seçin ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](../apps/apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.
    
 - **Uygulama yeniden başlatmaları Için bakım penceresini belirtin**: varsayılan "Yapılandırılmadı", yüklemenin tamamlanabilmesi için yeniden başlatma gerektiren uygulamaları denetlemek Için "gerektir" seçeneğini belirleyin.
 
     Bilgi noktası tarayıcısı veya iş için diğer Microsoft Store kullanıyorsanız, uygulama yüklemeyi tamamlaması için yeniden başlatma gerektiren uygulama güncelleştirmelerini ne sıklıkta deneteceğinize karar verin. Yapılandırılmamışsa, Iş uygulamaları için Microsoft Store, bir uygulama güncelleştirmesi yüklendikten sonra zamanlanmamış bir süre 3 gün sonra yeniden başlatılır.
     
     - **Bakım penceresi başlangıç zamanı**: yeniden başlatma gerektiren tüm uygulama güncelleştirmeleri için istemcileri denetlemeye başlamak üzere günün tarihini ve saatini seçin. Varsayılan başlangıç saati gece yarısı veya sıfır dakikadır.
     
     - **Bakım penceresi yinelemesi**: varsayılan olarak günlük.
         Uygulama güncelleştirmelerinin bakım pencerelerinin ne sıklıkla olacağını ayarlayın. Zamanlanmamış uygulama yeniden başlatmalarının önüne geçmek için öneri günlük bir uygulamadır.

  [ApplicationManagement/Scheduleforcerestartforupdatearızaları CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

## <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır. Bir uygulamanın başka bir uygulamaya bağımlılığı varsa, her ikisi de izin verilen uygulamalar listesine eklenmelidir. Örneğin, Internet Explorer 64 bit Internet Explorer 32 bit 'e bağımlıdır, bu nedenle hem "C:\Program Files\explorer\iexplore.exe" hem de "C:\Program Files (x86) \Internet Explorer\iexplore.exe" için izin vermelisiniz. 

- **Bilgi noktası modu seçin**: **birden çok uygulama bilgi noktası**seçin.

- **Windows 10 ' un modundaki cihazları hedefleyin**:
  - **Evet**: bilgi noktası profilinde mağaza uygulamalarına ve aumıd uygulamalarına (Win32 uygulamalarını hariç tutar) izin verir.
  - **Hayır**: bilgi noktası profilinde mağaza uygulamalarına, Win32 uygulamalarına ve aumıd uygulamalarına izin verir. Bu bilgi noktası profili S modundaki cihazlara dağıtılmadı.

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamalar, girdiğiniz kullanıcı hesabı olarak çalışır. Seçenekleriniz şunlardır:

  - **Otomatik oturum açma (Windows 10 sürüm 1803 ve üzeri)** : bir Konuk hesabına benzer şekilde, kullanıcının oturum açmasını gerektirmeyen, genel kullanıma yönelik ortamlarda bilgi noktaları üzerinde kullanın. Bu ayar, [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) kullanır.
  - **Yerel kullanıcı hesabı**: Cihaz için yerel kullanıcı hesabını **ekleyin**. Girdiğiniz hesap, bilgi noktasında oturum açar.
  - **Azure AD kullanıcısı veya grubu (Windows 10 sürüm 1803 ve üzeri)** : **Ekle**' yi SEÇIN ve listeden Azure AD kullanıcıları veya grupları ' nı seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçisi**: Ziyaretçi hesabı, [paylaşılan PC modu kavramlarında](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) anlatıldığı gibi, kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir konuk hesabıdır.

- **Tarayıcı ve uygulamalar**: bilgi noktası cihazında çalıştırılacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Tarayıcısında**

    - **Microsoft Edge Ekle**: Microsoft Edge uygulama kılavuzuna eklenir ve tüm uygulamalar bu bilgi noktasında çalıştırılabilir. **Microsoft Edge bilgi noktası modu türünü**seçin:

      - **Normal mod (Microsoft Edge 'in tam sürümü)** : tüm göz atma özellikleriyle Microsoft Edge 'in tam bir sürümünü çalıştırır. Kullanıcı verileri ve durumu oturumlar arasında kaydedilir.
      - **Genel göz atma (InPrivate)** : tam ekran modunda çalışan bilgi noktaları için özel bir deneyim ile Microsoft Edge InPrivate 'ın çok bölgeli bir sürümünü çalıştırır.

      Bu seçenekler hakkında daha fazla bilgi için bkz. [Microsoft Edge bilgi noktası modunu dağıtma](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Bu ayar cihazda Microsoft Edge tarayıcısını sunar. Microsoft Edge 'e özgü ayarları yapılandırmak için bir cihaz yapılandırma**profili oluşturun (** **cihaz yapılandırma** > **profiller** >  > platform Için  > **Windows 10** **cihaz kısıtlamaları**  >  **Microsoft Edge tarayıcısı**). [Microsoft Edge tarayıcısı](device-restrictions-windows-10.md#microsoft-edge-browser) , kullanılabilir ayarları listeler ve açıklar.

    - **Bilgi noktası tarayıcısı Ekle**: Bu ayarlar, bilgi noktasında bir Web tarayıcısı uygulamasını denetler. Bilgi noktasına web tarayıcısı uygulamasını [İstemci Uygulamaları](../apps/apps-add.md)’nı kullanarak dağıttığınıza emin olun.

      Aşağıdaki ayarları girin:

      - **Varsayılan giriş sayfası URL’si**: Bilgi noktası tarayıcısı açıldığında veya yeniden başlatıldığında gösterilen varsayılan URL’yi girin. Örneğin `http://bing.com` veya `http://www.contoso.com` girin.

      - **Giriş düğmesi**: Bilgi noktası tarayıcısının giriş düğmesini **gösterin** veya **gizleyin**. Varsayılan olarak düğme gösterilmez.

      - **Gezinti düğmeleri**: İleri ve geri düğmelerini **gösterin** veya **gizleyin**. Varsayılan olarak gezinti düğmeleri gösterilmez.

      - **Oturumu sonlandır düğmesi**: Oturumu sonlandır düğmesini **gösterin** veya **gizleyin**. Gösterildiğinde, kullanıcı düğmeyi seçer ve uygulama oturumun sonlandırılmasını ister. Onaylandığında tarayıcı, tüm göz atma verilerini (çerezler, önbellek vb.) temizler ve daha sonra varsayılan URL’yi açar. Varsayılan olarak düğme gösterilmez.

      - **Boşta kalma süresi geçince tarayıcıyı yenile**: Bilgi noktası tarayıcısı temiz bir durumda yeniden başlatılana kadar geçecek oturum başka kalma süresini (1-1440 dakika) girin. Boşta kalma süresi, kullanıcının son etkileşiminden sonra geçen dakika sayısıdır. Varsayılan olarak değer boştur veya boşluktur ve bu, boşta kalma süresinin olmadığı anlamına gelir.

      - **İzin verilen web siteleri**: Belirli Web sitelerinin açılmasına izin vermek için bu ayarı kullanın. Diğer bir deyişle, cihazda web sitelerine erişimi kısıtlamak veya tamamen önlemek için bu özelliği kullanın. Örneğin `contoso.com*` adresindeki tüm Web sitelerinin açılmasına izin verebilirsiniz. Varsayılan olarak tüm Web sitelerine izin verilir.

        Belirli Web sitelerine izin vermek için izin verilen Web siteleri listesini içeren bir .csv dosyasını karşıya yükleyin. Bir .csv dosyası eklemezseniz tüm Web sitelerine izin verilir.

      > [!NOTE]
      > Microsoft bilgi noktası tarayıcısı kullanılarak otomatik oturum açma özelliği etkinleştirilmiş Windows 10 kiosks, Microsoft Store Iş için çevrimdışı bir lisans kullanmalıdır. Bu gereksinim, otomatik oturum açma 'nın Azure Active Directory (AD) kimlik bilgileri olmayan bir yerel kullanıcı hesabı kullanması nedeniyle oluşur. Bu nedenle, çevrimiçi lisanslar değerlendirilemiyor. Daha fazla bilgi için bkz. [çevrimdışı uygulamaları dağıtma](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Uygulamaları**

    - **Mağaza uygulaması ekle**: İş İçin Microsoft Store’dan bir uygulama ekleyin. Listede hiç uygulama yoksa uygulama edilebilir ve [bunları Intune’a ekleyebilirsiniz](../apps/store-apps-windows.md). Örneğin Bilgi Noktası Tarayıcısı, Excel, OneNote gibi pek çok uygulama ekleyebilirsiniz.

    - **Win32 uygulaması ekle**: Win32 uygulamaları, Visual Studio Code veya Google Chrome gibi geleneksel masaüstü uygulamalarıdır. Aşağıdaki özellikleri girin:

      - **Uygulama adı**: Gereklidir. Uygulama için bir ad girin.
      - **Yerel yol**: Gereklidir. Yürütülebilir dosyanın yolunu girin, örneğin `C:\Program Files (x86)\Microsoft VS Code\Code.exe` veya `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Uygulama kullanıcı modeli kimliği (AUMID)** : Win32 uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu ayar, masaüstündeki kutucuk başlangıç düzenini belirler. Bu KIMLIĞI almak için bkz. [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps).

    - **AUMID’e göre ekle**: Notepad veya Hesap Makinesi gibi gelen kutusu Windows uygulamalarını eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin:

      - **Uygulama adı**: Gereklidir. Uygulama için bir ad girin.
      - **Uygulama kullanıcı modeli kimliği (AUMID)** : Gereklidir. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

    - **Oto başlatması**: isteğe bağlı. Kullanıcı oturum açtığında, yeniden başlatılacak bir uygulama seçin. Yalnızca tek bir uygulama, oto başlatılabilir.
    - **Kutucuk boyutu**: Gereklidir. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

  > [!TIP]
  > Tüm uygulamaları ekledikten sonra tıklayıp sürükleme yoluyla listedeki uygulamaların görüntülenme sırasını değiştirebilirsiniz.  

- **Alternatif Başlangıç menüsü düzeni kullan**: Uygulamaların sırası da dahil olmak üzere Başlat menüsünde nasıl göründüğünü açıklayan bir XML dosyası girmek için **Evet**’i seçin. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

- **Windows Görev Çubuğu**: Görev çubuğunu **Göstermeyi** veya **Gizlemeyi** seçin. Varsayılan olarak görev çubuğu gösterilmez. Wi-Fi simgesi gibi simgeler gösterilir, ancak ayarlar son kullanıcılar tarafından değiştirilemez.

- **Indirmeler klasörüne erişime Izin ver**: kullanıcıların Windows Gezgini 'nde indirmeler klasörüne erişmesine izin vermek için **Evet** ' i seçin. Varsayılan olarak, Indirmeler klasörüne erişim devre dışıdır. Bu özellik genellikle son kullanıcıların bir tarayıcıdan indirilen öğelere erişmesi için kullanılır.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)ve [Windows holographic for Business](kiosk-settings-holographic.md) cihazları için bilgi noktası profilleri de oluşturabilirsiniz.
