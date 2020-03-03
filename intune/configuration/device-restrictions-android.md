---
title: Microsoft Intune'da Android için cihaz kısıtlama ayarları - Azure | Microsoft Docs
description: Microsoft Intune'da denetleyebileceğiniz ve kısıtlayabileceğiniz tüm Android cihaz ayarlarının listesine bakın. Parolayı denetlemek, Google Play'e erişmek, uygulamalara izin vermek veya bunları yasaklamak, tarayıcı ayarlarını denetlemek, uygulamaları engellemek, Google bulutuna yedekleme yapmak ve mesaj, ses, veri dolaşımı, Wi-Fi ve Bluetooth bağlantı seçeneklerini denetlemek için bu ayarları kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd05547d4699888f5fade58fb5a50557604d81ea
ms.sourcegitcommit: fab685b22a010fe231b27a0c5eda34a6f22f4c8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78216050"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-lists-in-intune"></a>Intune 'da Android ve Samsung KNOX Standard cihaz kısıtlama ayarları listeleri

Bu makalede, Android çalıştıran cihazlar için yapılandırabileceğiniz tüm Microsoft Intune cihaz kısıtlama ayarları gösterilir.

>[!TIP]
>İstediğiniz ayarlar mevcut değilse cihazlarınızı bir [özel profil](../custom-settings-android.md) kullanarak yapılandırabilirsiniz.

## <a name="general"></a>Genel

- **Kamera**: kameraya erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** ayarı cihazın kamerasına erişim sağlar.
- **Kopyala ve Yapıştır (yalnızca Samsung KNOX)**: kopyalamayı ve yapıştırmayı engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazdaki kopyalama ve yapıştırma işlevlerine izin verir.
- **Uygulamalar arasında Pano paylaşımı (yalnızca Samsung KNOX)**: uygulamalar arasında kopyalama ve yapıştırma için panonun kullanılmasını engellemek üzere **blok** ' ı seçin. **Yapılandırılmamış** uygulamalar arasında kopyalama ve yapıştırma için panonun kullanılmasına izin verir.
- **Tanılama verileri gönderme (yalnızca Samsung KNOX)**: kullanıcının cihazdan hata raporları göndermesini durdurmak için **Engelle** ' yi seçin. **Yapılandırılmadı** , kullanıcının verileri göndermesine izin verir.
- **Temizleme (yalnızca Samsung KNOX)**: kullanıcının cihazda [silme](../remote-actions/devices-wipe.md) eylemi çalıştırmasına izin verir.
- **Coğrafi konum (yalnızca Samsung KNOX)**: Cihazın konum bilgilerini kullanmasını devre dışı bırakmak için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazın konum bilgilerini kullanmasına izin verir.
- **Kapatma (yalnızca Samsung KNOX)**: kullanıcının cihazı kapatmasına engel olmak için **Engelle** ' yi seçin. Bu ayar devre dışı bırakılırsa, **cihaz ayarı silinmeden önce oturum açma hatalarının sayısı** ayarlanamaz ve çalışmaz. **Yapılandırılmadı** , kullanıcının cihazı kapatmasına izin verir.
- **Ekran yakalama (yalnızca Samsung KNOX)**: ekran görüntülerini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , kullanıcının ekran içeriğini bir resim olarak yakalamasına olanak sağlar.
- **Sesli yardımcı (yalnızca Samsung KNOX)**: S Ses hizmetini devre dışı bırakmak için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda S ses hizmeti ve uygulamasının kullanılmasına izin verir. Bu ayar, Bıxby için veya ekran içeriğini yüksek sesle okuyan erişilebilirlik için ses Yardımcısı 'na uygulanmaz.
- **YouTube (yalnızca Samsung KNOX)**: kullanıcıların YouTube uygulamasını kullanmalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda YouTube uygulamasının kullanılmasına izin verir.
- **Paylaşılan cihazlar (yalnızca Samsung KNOX)**: yönetilen bir Samsung KNOX Standard cihazını paylaşılan olarak yapılandırın. **Izin ver**olarak ayarlandığında, son kullanıcılar, Azure AD kimlik bilgileriyle cihazda oturum açabilir ve bu cihazları alabilir. Cihaz, kullanımda olup olmadığı için yönetilmeye devam eder.</br>Bir SCEP sertifika profili ile birlikte kullanıldığında, bu özellik son kullanıcıların tüm kullanıcılar için aynı uygulamalarla bir cihaz paylaşmasına izin verir. Ancak, her kullanıcının kendi SCEP Kullanıcı sertifikası vardır. Kullanıcılar oturumu kapattığında tüm veriler silinir. Bu özellik yalnızca LOB uygulamalarıyla sınırlıdır. </br>**Yapılandırılmadı** , birden fazla son kullanıcının Azure AD kimlik bilgilerini kullanarak cihazdaki Şirket portalı uygulamasında oturum açmasını engeller.
- **Tarih ve saat değişikliklerini engelle (Samsung KNOX)**: kullanıcının cihazdaki tarih ve saat ayarlarını değiştirmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , kullanıcıların tarih ve saat ayarlarını değiştirmesine izin verir.

## <a name="password"></a>Parola

- **Parola**: son kullanıcının cihaza erişmek için bir parola girmesini **gerektir** . **Yapılandırılmadı** ayarı kullanıcıların parola girmeden cihaza erişmelerine izin verir.

    > [!NOTE]
    > Samsung Knox cihazlar, MDM kaydı sırasında otomatik olarak 4 basamaklı bir PIN gerektirir. Yerel Android cihazlar, koşullu erişimle uyumlu hale gelmesi için otomatik olarak bir PIN gerektirebilir.

- **Minimum parola uzunluğu**: bir kullanıcının girmesi gereken parola uzunluğu alt sınırını girin (4 ile 16 karakter arasında).
- **Ekran kilitlenmeden önce geçmesi gereken işlem yapılmayan dakika**sayısı: ekran kilitlenmeden önce cihazda izin verilen en fazla dakika sayısını girin. Bir cihazda, son kullanıcı profilde yapılandırılmış olan süreden daha büyük bir değer ayarlayamaz. Son kullanıcı daha düşük bir süre değeri ayarlayabilir. Örneğin, profilde 15 dakika ayarlandıysa, son kullanıcı değer olarak 5 dakika ayarlayabilir. Son kullanıcı değer olarak 30 dakika ayarlayamaz. 
- **Cihaz silinmeden önceki oturum açma hatalarının sayısı**: cihaz temizlenmeden önce izin verilecek oturum açma hatalarının sayısını girin.
- **Parola kullanım süresi (gün)**: cihaz parolasının değiştirilmesi gereken gün sayısını girin.
- **Gerekli parola türü**: gerekli parola karmaşıklığı düzeyini ve biyometrik cihazların kullanılıp kullanılamayacağını girin. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **En az sayısal**
  - **Sayısal karmaşık**: "1111" veya "1234" gibi yinelenen veya ardışık numaralara izin verilmez. <sup>1</sup>
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle**: son kullanıcının daha önce kullanmış olduğu bir parolayı oluşturmasını engeller.
- **Parmak iziyle kilit açma (yalnızca Samsung KNOX)**: cihazın kilidini açmak için parmak izi kullanımını engellemek için **bloğu** seçin. **Yapılandırılmadı** ayarı, kullanıcının cihaz kilidini parmak izi kullanarak açmasını sağlar.
- **Akıllı kilit ve diğer güven aracıları**: akıllı kilit veya diğer güven aracılarının kilit ekranı ayarlarını (Samsung KNOX Standard 5.0 +) değiştirmesini engellemek için **Engelle** ' yi seçin. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken cihaz kilidi ekran parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin, bu özellik, cihaz belirli bir Bluetooth cihazına bağlandığında veya bir NFC etiketine yakın olduğunda kullanılabilir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.
- **Şifreleme**: cihazdaki dosyaların şifrelenmesi için **gerektir** ' i seçin. Tüm cihazlar şifrelemeyi desteklemez. Bu özelliği kullanmak için ayrıca: 
  1. **Parolayı** **gerekli**olarak ayarlayın.
  2. **Gerekli parola türünü** **en az sayısal**olarak ayarlayın.
  3. Bu ayar için uyumluluğu doğru şekilde raporlamak için **en az parola uzunluğu** ' nu en az 4 olarak ayarlayın.

  > [!NOTE]
  > Bir şifreleme ilkesi uygulanırsa Samsung Knox cihazlar, kullanıcıların cihaz parolası olarak 6 karakterli karmaşık bir parola ayarlamasını gerektirir.

<sup>1</sup> bu ayarı cihazlara atamadan önce, Şirket Portalı uygulamasını bu cihazlarda en son sürüme güncelleştirdiğinizden emin olun.

**Gerekli parola türünü** **sayısal**olarak belirleyip 5,0 'den önceki bir Android sürümünü çalıştıran bir cihaza atarsanız, aşağıdaki davranış geçerlidir:

- Şirket Portalı uygulaması 1704 sürümünden önceki bir sürümü çalıştırıyorsa, cihaza bir PIN ilkesi uygulanmaz ve Microsoft Endpoint Manager Yönetim merkezinde bir hata gösterilir.
- Şirket Portalı uygulaması 1704 veya üzeri bir sürüm çalıştırıyorsa yalnızca basit bir PIN uygulanabilir. 5,0 'den önceki Android sürümleri bu ayarı desteklemez. Microsoft Endpoint Manager Yönetim merkezinde herhangi bir hata gösterilmez.

## <a name="google-play-store"></a>Google Play Store

- **Google Play deposu (yalnızca Samsung KNOX)**: kullanıcıların Google Play deposunu kullanmalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , kullanıcının cihazdaki Google Play deposuna erişmesine izin verir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Cihazdaki belirli uygulamalara izin vermek veya bunları engellemek için bu ayarları kullanın. Bu özellik Android ve Samsung KNOX Standard cihazlarında desteklenir:

- **Yasaklanmış uygulamalar**: Intune tarafından yönetilmeyen ve cihaza yüklenmesini istemediğiniz uygulamaların listesi. Kullanıcı bu listedeki bir uygulamayı yüklerse, Intune bunu size bildirir.
- **Onaylanan uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamaların bir listesi. Uyumluluğun korunması için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- İstediğiniz uygulamanın Google Play Store URL 'sini **ekleyin** . Örneğin, Android için Microsoft Uzak Masaüstü uygulamasını eklemek için `https://play.google.com/store/apps/details?id=com.microsoft.rdc.android`girin. Bir uygulamanın URL 'sini bulmak için [Google Play Store](https://play.google.com/store/apps)' u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop Play Store` veya `Microsoft Planner` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.
- URL'si de dahil olmak üzere uygulamayla ilgili ayrıntıların bulunduğu bir CSV dosyasını içeri aktarın. < App*url*> <*uygulama adı*>, <*uygulama yayımcısı*> biçimini kullanın. Veya, kısıtlanmış uygulamalar listesini içeren mevcut bir listeyi aynı biçimde **dışarı aktarın** .

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="browser"></a>Tarayıcı

- **Web tarayıcısı (yalnızca Samsung KNOX)**: varsayılan Web tarayıcısının cihazda kullanılmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazın varsayılan Web tarayıcısının kullanılmasına izin verir.
- **Otomatik doldurma (yalnızca Samsung KNOX)**: tarayıcıdaki metnin otomatik olarak otomatik olarak değiştirilmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , Web tarayıcısının otomatik doldurma işlevinin kullanılmasına izin verir.
- **Tanımlama bilgileri (yalnızca Samsung KNOX)**: cihazdaki Web sitelerinden tanımlama bilgilerini nasıl işlemek istediğinizi seçin. Seçenekleriniz şunlardır:
  - İzin ver
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinin tanımlama bilgilerine izin ver
- **JavaScript (yalnızca Samsung KNOX)**: Web tarayıcısının Java betikleri çalıştırmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihaz Web tarayıcısının Java betiklerini çalıştırmasına izin verir.
- **Açılır pencereler (yalnızca Samsung KNOX)**: Web tarayıcısında açılır pencereleri engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , Web tarayıcısında açılır pencerelere izin verir.

## <a name="allow-or-block-apps"></a>Uygulamalara izin verme veya uygulamaları engelleme

Samsung KNOX Standard cihazlarında belirli uygulamalara izin vermek, bunları engellemek veya gizlemek için bu ayarları kullanın. Gizli olan uygulamalar, Kullanıcı tarafından açılamaz veya çalıştırılmamalıdır.

Seçenekleriniz şunlardır:

- **Yüklenmesine izin verilen uygulamalar (yalnızca Samsung Knox Standard)**
- **Başlatılması engellenen uygulamalar (yalnızca Samsung Knox Standard)**
- **Kullanıcıdan gizlenen uygulamalar (yalnızca Samsung Knox Standard)**

Her ayar için, uygulamaların bir listesini ekleyin. Seçenekleriniz şunlardır:

- **Paket adına göre uygulama ekleme**: öncelikle iş kolu uygulamaları için kullanılır. Uygulamanın ve uygulama paketinin adını girin.
- **URL 'ye göre uygulama ekleme**: uygulama adını ve Google Play deposuna URL 'sini girin.
- **Mağaza uygulaması ekleme**: Intune 'da yönettiğiniz mevcut uygulamalar listesinden bir uygulama seçin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Google yedekleme (yalnızca Samsung KNOX)**: cihazın Google yedekleme 'ye eşitlenmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , Google yedekleme 'nin kullanılmasına izin verir.
- **Google hesabı otomatik eşitlemesi (yalnızca Samsung KNOX)**: cihazda Google hesabı otomatik eşitleme özelliğinin oluşmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.
- **Çıkarılabilir depolama birimi (yalnızca Samsung KNOX)**: cihazın çıkarılabilir depolama alanını kullanmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazın SD kart gibi çıkarılabilir depolama birimi kullanmasına izin verir.
- **Depolama kartlarında şifreleme (yalnızca Samsung KNOX)**: **gerektir** , depolama kartlarının şifrelenmesini zorunlu tutar. **Yapılandırılmadı** , şifrelenmemiş depolama kartlarının kullanılmasına izin verir. Tüm cihazlar depolama kartı şifrelemesini desteklemez. Doğrulamak için cihaz üreticisine danışın.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Veri dolaşımı (yalnızca Samsung KNOX)**: hücresel ağ üzerinde veri dolaşımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihaz hücresel ağ üzerindeyken veri dolaşımına izin verir.
- **SMS/MMS Mesajlaşma (yalnızca Samsung KNOX)**: cihazda metin iletilerini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda SMS ve MMS Mesajlaşma kullanımına izin verir.
- **Sesli arama (yalnızca Samsung KNOX)**: kullanıcıların cihazda sesli arama özelliğini kullanmalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda sesli aramaya izin verir.
- **Ses dolaşımı (yalnızca Samsung KNOX)**: hücresel ağ üzerinde ses dolaşımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihaz hücresel ağ üzerindeyken ses dolaşımına izin verir.
- **Bluetooth (yalnızca Samsung KNOX)**: cihazda Bluetooth 'un kullanılmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda Bluetooth kullanımına izin verir.
- **NFC (yalnızca Samsung KNOX)**: yakın alan ILETIŞIMI (NFC) teknolojisini durdurmak için **Engelle** ' yi seçin. **Yapılandırılmadı** , desteklenen cihazlarda yakın alan iletişimi kullanan işlemlere izin verir.
- **Wi-Fi (yalnızca Samsung KNOX)**: cihazda Wi-Fi kullanımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazın Wi-Fi özelliklerinin kullanılmasına izin verir.
- **Wi-Fi internet paylaşımı (yalnızca Samsung KNOX)**: cihazda Wi-Fi internet paylaşımını kullanmayı engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda Wi-Fi internet paylaşımı kullanımına izin verir.

## <a name="kiosk"></a>Bilgi noktası

Bilgi noktası ayarları yalnızca Samsung Knox Standard cihazlarda ve Intune ile yönettiğiniz uygulamalarda geçerlidir.

- Cihaz bilgi noktası modundayken çalıştırmak istediğiniz uygulamaları ekleyin. Bilgi noktası modunda, yalnızca eklediğiniz uygulamalar çalışır; eklenmemiş uygulamalar çalışmaz. Cihaz bilgi noktası modunda olduğunda, önceden yüklenmiş tarayıcılar uygulama olarak çalışmaz. Bir tarayıcı gerekliyse [Managed Browser](../apps/app-configuration-managed-browser.md) kullanabilirsiniz.

  Uygulama seçenekleriniz:

  - **Paket adına göre uygulama ekleme**: öncelikle iş kolu uygulamaları için kullanılır. Uygulamanın ve uygulama paketinin adını girin.
  - **URL 'ye göre uygulama ekleme**: uygulama adını ve Google Play deposuna URL 'sini girin.
  - **Mağaza uygulaması ekleme**: Intune 'da yönettiğiniz mevcut uygulamalar listesinden bir uygulama seçin.

- **Ekran uyku düğmesi**: ekran uyku düğmesini engellemek veya gizlemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazda ekran uyku modundan çıkarma düğmesine izin verir.
- **Ses düğmeleri**: ses düğmelerini devre dışı bırakarak kullanıcının birimi değiştirmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , cihazdaki ses düğmelerinin kullanılmasına izin verir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](../device-profile-assign.md) ve [durumunu izleme](../device-profile-monitor.md).

Ayrıca, [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) ve [Windows 10](kiosk-settings.md) cihazları için bilgi noktası profilleri oluşturabilirsiniz.
