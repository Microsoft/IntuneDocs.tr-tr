---
title: "Microsoft Intune - Azure’da iOS veya macOS cihaz profili oluşturma | Microsoft Docs"
description: "Bir iOS veya macOS cihaz profili ekleyin veya oluşturun ve sonra Microsoft Intune'da AirPrint, AirPlay, giriş ekranı düzeni, uygulama bildirimleri, paylaşılan cihaz, çoklu oturum açma ve web içerik filtresi ayarlarını yapılandırın"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3de7d1bccd57da1290987a714416373cbdd2b0d
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Intune’da iOS veya macOS cihaz özelliği ayarları ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihaz özellikleri, iOS ve macOS cihazlarındaki aşağıdaki gibi çeşitli ayarları ve özellikleri denetlemenizi sağlar:

- AirPrint ve AirPlay ayarları
- Giriş ekranı düzeni
- Uygulamalardan bildirimler
- Paylaşılan cihaz yapılandırması
- Çoklu oturum açmayı yapılandırın
- Web içeriğini filtreleme

Bu makalede, iOS cihaz özelliği profillerini yapılandırmayla ilgili temel bilgiler verilir. Ardından, cihazlarınız için platforma özgü ayarları yapılandırmak üzere ek makalelere göz atabilirsiniz.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması**’nı, **Profiller**’i seçin ve ardından **Profil Oluştur**’u seçin.
4. Aşağıdaki özellikleri girin:

  - **Ad**: Yeni profil için açıklayıcı bir ad girin
  - **Açıklama**: (İsteğe bağlı ancak önerilir) Profil için bir açıklama girin
  - **Platform**: Platform türünüzü seçin:
    - **iOS**
    - **macOS**
  - **Profil türü**: **Cihaz özellikleri**'ni seçin
  - **Ayarlar**: Ayarlar seçtiğiniz platforma bağlıdır. Aşağıdaki makaleler her profil türü için ayarları açıklar:

    - [iOS ve MacOS cihazları için AirPrint ayarları](air-print-settings-ios-macos.md)
    - [iOS için AirPlay ayarları](airplay-settings-ios.md)
    - [iOS için Giriş ekranı düzen ayarları](home-screen-settings-ios.md)
    - [iOS için uygulama bildirimi ayarları](app-notification-settings-ios.md)
    - [iOS için paylaşılan cihaz yapılandırma ayarları](shared-device-settings-ios.md)
    - [Intune'u iOS cihazında Çoklu Oturum Açma için](sso-ios.md) yapılandırma
    - [iOS için web içerik filtresi ayarları](web-content-filter-settings-ios.md)

5. İşiniz bittiğinde **Tamam**’ı ve değişikliklerinizi kaydetmek için **Oluştur**’u seçin.

Profil oluşturulur ve listede görüntülenir.

## <a name="next-step"></a>Sonraki adım

Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).