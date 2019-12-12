---
title: Microsoft Intune-Azure 'da Windows holographic for Business için bilgi noktası ayarları | Microsoft Docs
description: Windows holographic for Business cihazlarınızı tek uygulama ve çok kullanıcılı kiler olarak yapılandırın, Başlat menüsünü özelleştirin, uygulamalar ekleyin, görev çubuğunu görüntüleyin ve Microsoft Intune bir Web tarayıcısı yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e555c62030cede57e98e34034367831c298c0ced
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72492406"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Intune 'da bilgi noktası olarak çalışacak Windows holographic for Business cihaz ayarları

Windows Holographic for Business cihazlarında, bu cihazları tekli uygulama bilgi noktası modunda veya çoklu uygulama bilgi noktası modunda çalıştırılacak şekilde yapılandırabilirsiniz. Bazı özellikler, Windows Holographic for Business’ta desteklenmez.

Bu makalede, Windows holographic for Business cihazlarında denetleyebilmeniz için farklı ayarlar listelenmektedir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, Windows holographic for Business cihazlarınızı bilgi noktası modunda çalışacak şekilde yapılandırmak için bu ayarları kullanın.

Bir Intune Yöneticisi olarak bu ayarları oluşturabilir ve cihazlarınıza atayabilirsiniz.

Intune 'da Windows bilgi noktası özelliği hakkında daha fazla bilgi edinmek için bkz. [bilgi noktası ayarlarını yapılandırma](kiosk-settings.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Profili oluşturun](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları

Tekli uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Kullanıcı oturum açma türü**: Cihaz için yerel kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili Microsoft Hesabı’nı (MSA) girmek için **Yerel kullanıcı hesabı**’nı seçin. **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.

- **Uygulama türü**: **Mağaza uygulaması**’nı seçin.

- **Bilgi noktası modunda çalışacak uygulama**: **Bir mağaza uygulaması ekle**’yi seçin ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](../apps/apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

Bu modda uygulamalar Başlat menüsünde sağlanır. Bu uygulamalar, yalnızca kullanıcıların açabildiği uygulamalardır. Çoklu uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **S modu cihazlarında Windows 10’u hedefle**: **Hayır**’ı seçin. S modu, Windows holographic for Business üzerinde desteklenmez.

- **Kullanıcı oturum açma türü**: Eklediğiniz uygulamaları kullanabilecek bir veya birden çok kullanıcı hesabı belirtin. Seçenekleriniz şunlardır: 

  - **Otomatik oturum açma**: Windows Holographic for Business’ta desteklenmez.
  - **Yerel kullanıcı hesapları**: Cihaz için yerel kullanıcı hesabını **ekleyin**. Girdiğiniz hesap, bilgi noktasında oturum açmak için kullanılır.
  - **Azure Active Directory kullanıcı veya grubu (Windows 10, sürüm 1803 ve sonrası)** : Cihazda oturum açmak için kullanıcı kimlik bilgilerini gerektirir. Listeden Azure Active Directory kullanıcılarını veya gruplarını seçmek için **Ekle**’yi seçin. Birden çok kullanıcı ve grup seçebilirsiniz. Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.
  - **HoloLens ziyaretçisi**: Ziyaretçi hesabı, [paylaşılan PC modu kavramlarında](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts) anlatıldığı gibi, kullanıcı kimlik bilgileri veya kimlik doğrulaması gerektirmeyen bir konuk hesabıdır.

- **Uygulamalar**: Bilgi noktası cihazında çalışacak uygulamaları ekleyin. Birden fazla uygulama ekleyebileceğinizi unutmayın.

  - **Mağaza uygulamaları ekleme**: LOB uygulamaları [dahil olmak üzere](../apps/apps-add.md)Intune 'a eklediğiniz veya Intune 'a dağıttığınız mevcut bir uygulamayı seçin. Listelenen uygulamalarınız yoksa Intune, [Intune 'a eklediğiniz](../apps/store-apps-windows.md)birçok [uygulama türünü](../apps/apps-add.md) destekler.
  - **Win32 uygulaması ekle**: Windows Holographic for Business’ta desteklenmez.
  - **AUMID’e göre ekle**: Gelen kutusu Windows uygulamalarını eklemek için bu seçeneği kullanın. Aşağıdaki özellikleri girin: 

    - **Uygulama adı**: Gereklidir. Uygulama için bir ad girin.
    - **Uygulama kullanıcı modeli kimliği (AUMID)** : Gereklidir. Windows uygulamasının uygulama kullanıcı modeli kimliğini (AUMID) girin. Bu kimliği almak için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Modeli Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).
    - **Kutucuk boyutu**: Gereklidir. Küçük, Orta, Geniş veya Büyük uygulama kutucuk boyutu seçin.

- **Bilgi noktası tarayıcı ayarları**: Windows Holographic for Business’ta desteklenmez.

- **Alternatif Başlangıç menüsü düzeni kullan**: Uygulamaların sırası da dahil olmak üzere Başlat menüsünde nasıl göründüğünü açıklayan bir XML dosyası girmek için **Evet**’i seçin. Başlangıç menünüzü daha fazla özelleştirmeniz gerekiyorsa bu seçeneği kullanın. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens), Windows Holographic for Business cihazları için rehberlik sağlar ve belirli bir XML dosyası içerir.

- **Windows Görev Çubuğu**: Windows Holographic for Business’ta desteklenmez.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings)ve [Windows 10 ve üzeri](kiosk-settings-windows.md) cihazlar için bilgi noktası profilleri de oluşturabilirsiniz.
