---
title: Microsoft Intune-Azure 'da Windows ve holographic cihazları için bilgi noktası ayarları | Microsoft Docs
description: Windows 10 (ve üzeri) ve Windows holographic for Business cihazlarınızı tek uygulamayla ve çok kullanıcılı bilgi olarak yapılandırın, Başlat menüsünü özelleştirin, uygulamalar ekleyin, görev çubuğunu görüntüleyin ve Microsoft Intune bir Web tarayıcısı yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 271b49a4c927bccb5cd967ea99b0d7bd5c2bd515
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492363"
---
# <a name="windows-10-and-windows-holographic-for-business-device-settings-to-run-as-a-dedicated-kiosk-using-intune"></a>Intune kullanarak adanmış bir bilgi noktası olarak çalışacak Windows 10 ve Windows holographic for Business cihaz ayarları

Windows 10 cihazlarında, cihazları bir bilgi noktası olarak çalıştırmak için Intune 'u kullanın, bazen adanmış bir cihaz olarak bilinir. Bilgi noktası modundaki bir cihaz bir uygulama çalıştırabilir veya birçok uygulama çalıştırabilir. Bir başlangıç menüsünü gösterebilir ve özelleştirebilir, Win32 uygulamaları dahil farklı uygulamalar ekleyebilir, bir Web tarayıcısına belirli bir giriş sayfası ekleyebilir ve daha fazlasını yapabilirsiniz. 

Bu özellik çalıştıran cihazlar için geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business

Intune, cihaz başına bir bilgi noktası profili destekler. Tek bir cihazda birden fazla bilgi noktası profiline ihtiyacınız varsa bir [Özel OMA-URI](custom-settings-windows-10.md) kullanabilirsiniz.

Intune, kuruluşunuzun ihtiyaçlarına göre bu ayarları oluşturmak ve özelleştirmek için "yapılandırma profillerini" kullanır. Bu özellikleri bir profilde ekledikten sonra bu ayarları kuruluşunuzdaki gruplara gönderin veya dağıtın.

Bu makalede bir cihaz yapılandırma profili oluşturma konusu gösterilmektedir. Tüm ayarların bir listesi ve ne yapacaklarınız için bkz. [Windows 10 bilgi noktası ayarları](kiosk-settings-windows.md) ve [Windows holographic for Business bilgi noktası ayarları](kiosk-settings-holographic.md).

## <a name="create-the-profile"></a>Profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihaz yapılandırması** > **Profiller** > **Profil Oluştur**’u seçin.
3. Aşağıdaki özellikleri girin:

   - **Ad**: Yeni profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: **Windows 10 ve üzeri**’ni seçin
   - **Profil türü**: **bilgi noktası** seçin

4. **Ayarlar**' da bir **bilgi noktası modu**seçin. **Bilgi noktası modu**, ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

    - **Yapılandırılmamış** (varsayılan): İlke, bilgi noktası modunu etkinleştirmez.
    - **Tekli uygulama, tam ekran bilgi noktası**: Cihaz tek kullanıcı hesabı olarak çalışır ve tek bir Mağaza uygulamasına kilitlenir. Dolayısıyla kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
    - **Çoklu uygulama bilgi noktası**: Cihaz, Uygulama Kullanıcı Modeli Kimliği (AUMID) kullanarak birden fazla Store, Win32 veya Windows uygulaması çalıştırır. Cihazda yalnızca eklediğiniz uygulamalar kullanılabilir.

        Çok uygulamalı bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak kullanıcılara anlaşılması kolay bir deneyim sunmasıdır. Bir de ihtiyaçları olmayan uygulamaları görünümden kaldırmasıdır.

    Tüm ayarların bir listesi ve ne yapacaklarınız için, bkz.:
      - [Windows 10 bilgi noktası ayarları](kiosk-settings-windows.md)
      - [Windows holographic for Business bilgi noktası ayarları](kiosk-settings-holographic.md)

5. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin. 

Profil oluşturulur ve profiller listesinde gösterilir. Sonra, profili [atayın](device-profile-assign.md) .

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Aşağıdaki platformları çalıştıran cihazlar için bilgi noktası profilleri oluşturabilirsiniz:
- [Outlook Web Access (OWA)](device-restrictions-android.md#kiosk)
- [Android Kurumsal](device-restrictions-android-for-work.md#dedicated-device-settings)
- [Windows 10 ve üzeri](kiosk-settings-windows.md)
- [Windows Holographic for Business](kiosk-settings-holographic.md)
