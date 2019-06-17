---
title: Microsoft Intune'da Android için cihaz kısıtlama ayarları - Azure | Microsoft Docs
description: Microsoft Intune'da denetleyebileceğiniz ve kısıtlayabileceğiniz tüm Android cihaz ayarlarının listesine bakın. Parolayı denetlemek, Google Play'e erişmek, uygulamalara izin vermek veya bunları yasaklamak, tarayıcı ayarlarını denetlemek, uygulamaları engellemek, Google bulutuna yedekleme yapmak ve mesaj, ses, veri dolaşımı, Wi-Fi ve Bluetooth bağlantı seçeneklerini denetlemek için bu ayarları kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f13b78e05b9f0b94d98677004c7059f1acaa80f9
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045713"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-lists-in-intune"></a>Android ve Samsung Knox Standard cihaz kısıtlama ayarları listelerinde Intune

Bu makalede, Android çalıştıran cihazlar için yapılandırabileceğiniz tüm Microsoft Intune cihaz kısıtlama ayarları gösterilir.

>[!TIP]
>İstediğiniz ayarlar mevcut değilse cihazlarınızı bir [özel profil](custom-settings-android.md) kullanarak yapılandırabilirsiniz.

## <a name="general"></a>Genel

- **Kamera**: Seçin **blok** kameraya erişimi engellemek için. **Yapılandırılmadı** ayarı cihazın kamerasına erişim sağlar.
- **Kopyalama ve yapıştırma (yalnızca Samsung Knox)**: Seçin **blok** Kopyala ve Yapıştır önlemek için. **Yapılandırılmamış** cihazda kopyalama ve yapıştırma işlevlerine izin verir.
- **(Yalnızca Samsung Knox) uygulamalar arasında pano paylaşımı**: Seçin **blok** Kopyala ve Yapıştır uygulamalar arasında Pano kullanılmasını önlemek için. **Yapılandırılmamış** uygulamalar arasında kopyalama ve yapıştırma için panonun kullanımına izin verir.
- **Tanılama verisi gönderme (yalnızca Samsung Knox)**: Seçin **blok** kullanıcının CİHAZDAN Tanılama verileri göndermesini durdurmak için. **Yapılandırılmamış** verileri göndermesine imkan tanır.
- **(Yalnızca Samsung Knox) temizleme**: Çalıştırmak kullanıcının bir [silme](devices-wipe.md) cihazda eylem.
- **Coğrafi konum (yalnızca Samsung Knox)**: Seçin **blok** konumu bilgilerini kullanarak cihazın devre dışı bırakmak için. **Yapılandırılmamış** cihazın konum bilgilerini kullanmasına izin verir.
- **Kapatma (yalnızca Samsung Knox)**: Seçin **blok** kullanıcının cihazı kapatıp destekleyen gelen önlemek için. Bu ayarı devre dışıysa, **cihaz silinmeden önceki oturum açma hatası sayısı** ayarı nelze nastavit ve çalışmaz. **Yapılandırılmamış** kullanıcının cihazı kapatmasına izin verir.
- **Ekran Yakalama (yalnızca Samsung Knox)**: Seçin **blok** ekran görüntüleri önlemek için. **Yapılandırılmamış** kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Sesli yardımcı (yalnızca Samsung Knox)**: Seçin **blok** S ses hizmeti devre dışı bırakın. **Yapılandırılmamış** S ses hizmet ve uygulama kullanımını cihazda izin verir. Bu ayar, Bixby veya sesli Yardım sayfası içeriğini sesli olarak okuyan erişilebilirlik için geçerli değildir.
- **YouTube (yalnızca Samsung Knox)**: Seçin **blok** kullanıcılar YouTube uygulamasının kullanmasını önlemek için. **Yapılandırılmamış** cihazda YouTube uygulamasının kullanımına izin verir.
- **Paylaşılan cihazlar (yalnızca Samsung Knox)**: Yönetilen bir Samsung Knox Standard cihazını paylaşılan olarak yapılandırın. Ayarlandığında **izin**, son kullanıcılar ve kendi Azure AD kimlik bilgileriyle cihazda oturum açabilir. Kullanımda olup olmadığına bakılmaksızın cihaz yönetilen kalır.</br>Bir SCEP sertifika profili ile kullanıldığında, bu özellik, son kullanıcılar, aynı uygulamalara tüm kullanıcılar için bir cihaz paylaşmasına izin verir. Ancak, her kullanıcının kendi SCEP kullanıcı sertifikası vardır. Kullanıcılar oturumu kapattığında tüm veriler silinir. Bu özellik yalnızca LOB uygulamalarıyla sınırlıdır. </br>**Yapılandırılmamış** birden çok son kullanıcılar için Şirket portalı uygulaması, Azure AD kimlik bilgilerini kullanarak cihazda oturum açarken engeller.
- **Engelleyin (Samsung Knox) tarih ve saat değişikliklerini**: Seçin **blok** saat ayarları cihazın ve kullanıcının tarihi değiştirmesini önlemek için. **Yapılandırılmamış** kullanıcıların değiştirme tarih ve saat ayarlarını olanak tanır.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: **Gerekli** ayarı son kullanıcının cihaza erişmek için parola girmesini zorunlu tutar. **Yapılandırılmadı** ayarı kullanıcıların parola girmeden cihaza erişmelerine izin verir.

    > [!NOTE]
    > Samsung Knox cihazlar, MDM kaydı sırasında otomatik olarak 4 basamaklı bir PIN gerektirir. Yerel Android cihazlar otomatik olarak koşullu erişim ile uyumlu olması bir PIN gerektirebilir.

- **Minimum parola uzunluğu**: (4 ile 16 karakter arasında) bir kullanıcının girmesi parola alt sınırını girin.
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Ekran otomatik olarak kilitlenmeden önce izin verilecek işlem yapılmayan en fazla dakika sayısını girin. Bir cihazda, son kullanıcı profilde yapılandırılmış olan süreden daha büyük bir değer ayarlayamaz. Son kullanıcı daha düşük bir süre değeri ayarlayabilir. Örneğin, profilde 15 dakika ayarlandıysa, son kullanıcı değer olarak 5 dakika ayarlayabilir. Son kullanıcı değer olarak 30 dakika ayarlayamaz. 
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihaz temizlenmeden önce izin vermek için oturum açma hatalarının sayısı girin.
- **Parola zaman aşımı (gün sayısı)**: Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin.
- **Gerekli parola türü**: Girmeniz gereken parola karmaşıklık düzeyini ve biyometrik cihaz kullanılıp kullanılamayacağı. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal**
  - **Sayısal karmaşıklık**: Yinelenen veya "1111" veya "1234" gibi ardışık sayılar izin verilmez. <sup>1</sup>
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelleme**: Son kullanıcının önceden kullanmış bir parolayı oluşturmasını durdurur.
- **Parmak iziyle kilit açma (yalnızca Samsung Knox)**: Cihaz kilidinin parmak izi kullanılarak açılmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmamış** parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.
- **Akıllı kilit ve diğer güven aracıları**: Seçin **blok** akıllı kilit veya diğer güven aracılarının kilit ekranı ayarları (Samsung KNOX Standard 5.0 +) ayarlamasını engellemek için. Bazı durumlarda bir güven aracısı olarak da bilinen bu telefon özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin, bu özellik, cihaz belirli bir Bluetooth cihazına bağlı olduğunda ya da bir NFC etiketinin yakınında olduğunda kullanılabilir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.
- **Şifreleme**: Seçin **gerektiren** böylece cihazdaki dosyaların şifrelenir. Tüm cihazlar şifrelemeyi destekler. Ayrıca bu özelliği kullanmak için: 
  1. Ayarlama **parola** için **gerektiren**.
  2. Ayarlama **gerekli parola türü** için **en az sayısal**.
  3. Ayarlama **Minimum parola uzunluğu** uyumluluğu doğru olarak raporlamak için bu ayar için en az 4.

  > [!NOTE]
  > Bir şifreleme ilkesi uygulanırsa Samsung Knox cihazlar, kullanıcıların cihaz parolası olarak 6 karakterli karmaşık bir parola ayarlamasını gerektirir.

<sup>1</sup> bu ayarı cihazlara atamadan önce Şirket portalı uygulamasının bu cihazlarda en son sürümüne güncelleştirdiğinizden emin olun.

Ayarlarsanız **gerekli parola türü** için **sayısal karmaşık**, aşağıdaki davranış geçerlidir sonra Android 5.0 öncesi bir sürümü çalıştıran bir cihaza atayın:

- Şirket portalı uygulaması 1704 öncesi bir sürümü çalıştıran cihaza PIN ilkesi uygulanır ve Azure portalında bir hata gösterilir.
- Şirket Portalı uygulaması 1704 veya üzeri bir sürüm çalıştırıyorsa yalnızca basit bir PIN uygulanabilir. Android'ın önceki sürümlerinde bu ayar 5.0 desteklemez. Azure portalında herhangi bir hata gösterilir.

## <a name="google-play-store"></a>Google Play Store

- **Google Play store (yalnızca Samsung Knox)**: Seçin **blok** kullanıcıların Google Play Store'da kullanmasını önlemek için. **Yapılandırılmamış** kullanıcının cihazda Google Play Store'a erişmesine izin verir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

İzin vermek veya cihazın belirli uygulamaları engellemek için bu ayarları kullanın. Bu özellik, Android ve Samsung Knox Standard cihazlarda desteklenir:

- **Yasak uygulamalar**: Intune tarafından yönetilmeyen ve cihazda bulunmasını istemediğiniz uygulamaların listesi. Kullanıcı bu listedeki bir uygulamayı yüklerse, Intune bunu size bildirir.
- **Onaylı uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamaların listesi. Uyumluluğun korunması için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.

Bu listeler için uygulama eklemek için şunları yapabilirsiniz:

- **Ekleme** istediğiniz uygulamanın Google Play Store URL'sini. Örneğin, Android için Microsoft Uzak Masaüstü uygulamasını eklemek için girin `https://play.google.com/store/apps/details?id=com.microsoft.rdc.android`. Bir uygulamanın URL'sini bulmak için açın [Google Play Store'da](https://play.google.com/store/apps)ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop Play Store` veya `Microsoft Planner` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.
- URL'si de dahil olmak üzere uygulamayla ilgili ayrıntıların bulunduğu bir CSV dosyasını içeri aktarın. Kullanım <*uygulama URL'si*>, <*uygulama adı*>, <*Uygulama Yayımcısı*> biçimi. Veya, **dışarı** aynı biçimdeki kısıtlı uygulama listesi içeren mevcut bir listesi.

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="browser"></a>Tarayıcı

- **Web tarayıcısı (yalnızca Samsung Knox)**: Seçin **blok** aygıtta kullanılan varsayılan web tarayıcısı önlemek için. **Yapılandırılmamış** cihazın varsayılan web tarayıcısının kullanılması izin verir.
- **Otomatik doldurma (yalnızca Samsung Knox)**: Seçin **blok** metin tarayıcıda otomatik doldurmaya önlemek için. **Yapılandırılmamış** kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.
- **Tanımlama bilgileri (yalnızca Samsung Knox)**: Cihazda Web sitelerinden tanımlama bilgilerini işlemek nasıl istediğinizi seçin. Seçenekleriniz şunlardır:
  - İzin Ver
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinin tanımlama bilgilerine izin ver
- **JavaScript (yalnızca Samsung Knox)**: Seçin **blok** web tarayıcısının Java betiklerini çalışmasını engelleyin. **Yapılandırılmamış** cihazın web tarayıcısının Java betiklerini çalıştırmasına izin verir.
- **Açılır pencereler (yalnızca Samsung Knox)**: Seçin **blok** web tarayıcısında açılır pencereleri önlemek için. **Yapılandırılmamış** web tarayıcısında açılır pencerelere izin verir.

## <a name="allow-or-block-apps"></a>Uygulamalara izin verme veya uygulamaları engelleme

İzin, engelleme ya da belirli uygulamaları Samsung Knox Standard cihazlarda gizlemek için bu ayarları kullanın. Gizli uygulamalar açılamaz veya kullanıcı tarafından çalıştırıldı.

Seçenekleriniz şunlardır:

- **Yüklenmesine izin verilen uygulamalar (yalnızca Samsung Knox Standard)**
- **Başlatılması engellenen uygulamalar (yalnızca Samsung Knox Standard)**
- **Kullanıcıdan gizlenen uygulamalar (yalnızca Samsung Knox Standard)**

Her ayar için uygulamaların bir listesini ekleyin. Seçenekleriniz şunlardır:

- **Paket adına göre uygulama ekleme**: Satır iş kolu uygulamaları için kullanılır. Uygulamanın ve uygulama paketinin adını girin.
- **URL'ye göre uygulama ekleme**: Google Play Mağazası'nda, uygulama adını ve URL'sini girin.
- **Mağaza uygulaması ekleme**: Mevcut Intune yönettiğiniz uygulamalar listesinden bir uygulama seçin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Google yedekleme (yalnızca Samsung Knox)**: Seçin **blok** cihaz Google yedekleme eşitlenmesini önlemek için. **Yapılandırılmamış** Google yedeklemesinin kullanımına izin verir.
- **Google hesabı otomatik eşitlemesi (yalnızca Samsung Knox)**: Seçin **blok** cihazda Google hesabı otomatik eşitleme özelliğini önlemek için. **Yapılandırılmamış** Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.
- **Çıkarılabilir Depolama Birimi (yalnızca Samsung Knox)**: Seçin **blok** aygıtın çıkarılabilir depolama birimi kullanmasını önlemek için. **Yapılandırılmamış** cihazın SD kartı gibi çıkarılabilir depolama birimi kullanmasına izin verir.
- **(Yalnızca Samsung Knox) depolama kartlarında şifreleme**: **Gerekli** depolama kartları şifrelenmelidir zorlar. **Yapılandırılmamış** kullanılacak şifrelenmemiş bir depolama kartları sağlar. Tüm cihazları depolama kartı şifrelemesini destekler. Onaylamak için cihazınızın üreticisine denetleyin.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Veri dolaşımı (yalnızca Samsung Knox)**: Cep telefonu şebekesi üzerinden veri dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmamış** cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **SMS/MMS mesajları (yalnızca Samsung Knox)**: Seçin **blok** cihaza Mesajlaşma metin önlemek için. **Yapılandırılmamış** SMS ve MMS mesajlaşması cihazda kullanımına izin verir.
- **Sesli arama (yalnızca Samsung Knox)**: Kullanıcıların cihazda sesli arama özelliğini kullanmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmamış** cihazda sesle sağlar.
- **Ses dolaşımı (yalnızca Samsung Knox)**: Cep telefonu şebekesi üzerinden ses dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmamış** ses cihaz hücresel ağ kullanırken dolaşımına izin verir.
- **Bluetooth (yalnızca Samsung Knox)**: Seçin **blok** cihazda Bluetooth kullanarak önlemek için. **Yapılandırılmamış** cihazda Bluetooth'un kullanımına izin verir.
- **NFC (yalnızca Samsung Knox)**: Seçin **blok** yakın alan iletişimi (NFC) teknolojisini durdurmak için. **Yapılandırılmamış** yakın desteklenen cihazlarda alan iletişimi kullanan işlemlere izin verir.
- **Wi-Fi (yalnızca Samsung Knox)**: Seçin **blok** cihazda Wi-Fi kullanılmasını önlemek için. **Yapılandırılmamış** cihazın Wi-Fi özelliklerinin kullanımına izin verir.
- **Wi-Fi Paylaşımı (yalnızca Samsung Knox)**: Seçin **blok** cihazda Wi-Fi paylaşımının kullanımını engellemek için. **Yapılandırılmamış** cihazda Wi-Fi paylaşımının kullanılmasına izin verir.

## <a name="kiosk"></a>Bilgi noktası

Bilgi noktası ayarları yalnızca Samsung Knox Standard cihazlarda ve Intune ile yönettiğiniz uygulamalarda geçerlidir.

- Cihaz bilgi noktası modunda olduğunda çalıştırmak istediğiniz uygulamaları ekleyin. Bilgi noktası modunda yalnızca eklediğiniz uygulamalar çalıştırın eklenen uygulamalar çalışmaz. Önceden yüklenen tarayıcılar, cihaz bilgi noktası modunda olduğunda bir uygulama olarak çalıştırmayın. Bir tarayıcı gerekliyse [Managed Browser](app-configuration-managed-browser.md) kullanabilirsiniz.

  Uygulama Seçenekleri:

  - **Paket adına göre uygulama ekleme**: Satır iş kolu uygulamaları için kullanılır. Uygulamanın ve uygulama paketinin adını girin.
  - **URL'ye göre uygulama ekleme**: Google Play Mağazası'nda, uygulama adını ve URL'sini girin.
  - **Mağaza uygulaması ekleme**: Mevcut Intune yönettiğiniz uygulamalar listesinden bir uygulama seçin.

- **Ekran uyku düğmesi**: Seçin **blok** ekran Uyku düğmesi Gizle veya önlemek için. **Yapılandırılmamış** cihazda ekran uykuya geçme Uyandırma düğmesine izin verir.
- **Ses düğmeleri**: Seçin **blok** kullanıcının ses düğmelerini devre dışı bırakarak birim ayarlama önlemek için. **Yapılandırılmamış** cihazdaki ses düğmelerini kullanarak sağlar.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Bilgi noktası profilleri de oluşturabilirsiniz [Android Kurumsal](device-restrictions-android-for-work.md#dedicated-device-settings) ve [Windows 10](kiosk-settings.md) cihazlar.
