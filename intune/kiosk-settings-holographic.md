---
title: Microsoft Intune - Azure'da Windows Holographic for Business için bilgi noktası ayarları | Microsoft Docs
description: Tek uygulama ve çoklu uygulama bilgi noktaları, Windows Holographic for Business cihazları yapılandırmak, Başlat menüsünü özelleştirmek, uygulama ekleme, görev çubuğunu göster ve bir web tarayıcısı Intune yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 38bc5ed233bf3368ae9b0ce21b8688966a1ffdef
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57232362"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Windows Holographic for Business cihaz ayarlarını ıntune'da bilgi noktası olarak çalıştırmak

Windows Holographic for Business cihazlarında, bu cihazları tekli uygulama bilgi noktası modunda veya çoklu uygulama bilgi noktası modunda çalıştırılacak şekilde yapılandırabilirsiniz. Bazı özellikler, Windows Holographic for Business’ta desteklenmez.

Bu makalede, listeler ve cihazları Windows Holographic for Business denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, Windows Holographic for Business cihazları bilgi noktası modunda çalışacak şekilde yapılandırmak için bu ayarları kullanın.

Bir Intune Yöneticisi olarak oluşturun ve bu ayarlar, cihazlara atayın.

Intune'da Windows bilgi noktası özelliği hakkında daha fazla bilgi için bkz. [bilgi noktası ayarları yapılandırma](kiosk-settings.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Profil oluşturma](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Tekli tam ekran uygulama bilgi noktaları

Tekli uygulama bilgi noktası modunu seçtiğinizde aşağıdaki ayarları girin:

- **Kullanıcı oturum açma türü**: Seçin **yerel kullanıcı hesabı** yerel (cihaz) kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili bir Microsoft hesabı (MSA) hesabı girmek için. **Otomatik oturum açma** kullanıcı hesabı türleri Windows Holographic for Business’da desteklenmez.

- **Uygulama türü**: Seçin **app Store**.

- **Bilgi noktası modunda çalıştırmak için uygulama**: Seçin **bir mağaza uygulaması ekleme**ve listeden bir uygulama seçin.

    Listede hiç uygulama yok mu? [İstemci Uygulamaları](apps-add.md)’ndaki adımları kullanarak birkaç uygulama ekleyin.

    Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

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

Bilgi noktası profilleri de oluşturabilirsiniz [Android](device-restrictions-android.md#kiosk), [Android Kurumsal](device-restrictions-android-for-work.md#dedicated-device-settings), ve [Windows 10 ve üzeri](kiosk-settings-windows.md) cihazlar.
