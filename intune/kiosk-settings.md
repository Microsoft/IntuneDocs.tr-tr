---
title: Windows ve Microsoft Intune - Azure Holographic cihazları için bilgi noktası ayarları | Microsoft Docs
description: Windows 10 (ve üzeri) ve Windows Holographic for Business cihazlar tek uygulama ve çoklu uygulama bilgi noktaları olarak yapılandırmak, Başlat menüsünü özelleştirmek, uygulama ekleme, görev çubuğunu göster ve bir web tarayıcısı Intune yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c777beb294482a179d4b99fc71db031367698d0d
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835801"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Windows 10 ve Windows Holographic for Business cihaz ayarları Intune kullanarak atanmış bilgi noktası çalıştırmak

Windows 10 cihazlarda, bazen bir adanmış cihaz olarak bilinen bir bilgi noktası olarak çalıştıran cihazlar için Intune kullanın. Bir cihaz bilgi noktası modunda, bir uygulama çalıştırmasına veya birçok uygulaması çalıştırın. Göster ve Başlat menüsü özelleştirme, Win32 uygulamaları dahil olmak üzere farklı uygulama, ekleme, bir web tarayıcısı ve daha fazla bilgi için belirli bir giriş sayfası ekleyin. 

Bu özellik çalıştıran cihazlar için geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business

Intune, cihaz başına bir bilgi noktası profili destekler. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir [Özel OMA-URI](custom-settings-windows-10.md) kullanabilirsiniz.

Intune kullanır "yapılandırma profillerini" oluşturabilir ve kuruluşunuzun ihtiyaçları için bu ayarları özelleştirebilirsiniz. Bu özellikler bir profilde ekledikten sonra anında iletme veya kuruluşunuzdaki gruplara bu ayarları dağıtın.

Bu makalede bir cihaz yapılandırma profilinin nasıl oluşturulacağını gösterir. Tüm ayarların bir listesi ve ne yaptıkları için bkz. [Windows 10 bilgi noktası ayarları](kiosk-settings-windows.md) ve [Windows Holographic for Business bilgi noktası ayarları](kiosk-settings-holographic.md).

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Seçin **Windows 10 ve üzeri**
   - **Profil türü**: Seçin **bilgi noktası**

4. İçinde **ayarları**seçin bir **bilgi noktası modu**. **Bilgi noktası modu**, ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

    - **Yapılandırılmamış** (varsayılan): Bilgi noktası modu ilke sağlamaz.
    - **Tek bir uygulama, tam ekran bilgi noktası**: Cihaz, tek bir kullanıcı hesabı çalışır ve tek bir Store uygulaması için kilitler. Dolayısıyla kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
    - **Çoklu uygulama bilgi noktası**: Cihaz, uygulama kullanıcı modeli kimliği (AUMID'yi) kullanarak, birden çok Store uygulamaları Win32 uygulamaları veya gelen Windows uygulamaları çalıştırır. Cihazda yalnızca eklediğiniz uygulamalar kullanılabilir.

        Çok uygulamalı bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak kullanıcılara anlaşılması kolay bir deneyim sunmasıdır. Bir de ihtiyaçları olmayan uygulamaları görünümden kaldırmasıdır.

    Tüm ayarların bir listesi ve ne yaptıkları için bkz:
      - [Windows 10 bilgi noktası ayarları](kiosk-settings-windows.md)
      - [Windows Holographic for Business bilgi noktası ayarları](kiosk-settings-holographic.md)

5. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin. 

Profil oluşturulur ve Profiller listesinde gösterilen. Ardından, [atama](device-profile-assign.md) profili.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Aşağıdaki platformları çalıştıran cihazlar için bilgi noktası profillerini oluşturabilirsiniz:
- [Android](device-restrictions-android.md#kiosk)
- [Android Kurumsal](device-restrictions-android-for-work.md#kiosk-settings)
- [Windows 10 ve üzeri](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)
