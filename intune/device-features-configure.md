---
title: Microsoft Intune - Azure’da iOS veya macOS cihaz profili oluşturma | Microsoft Docs
description: Ekleme veya bir iOS veya macOS cihaz profili oluşturma ve ardından Intune AirPrint, giriş ekranı, uygulama bildirimleri, paylaşılan cihaz, çoklu oturum açma ve web içeriği filtresi ayarları düzeni için ayarları yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a5c85c936e49c277b54b542f372f97b247d6a37
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373815"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Intune’da iOS veya macOS cihaz özelliği ayarları ekleme

Intune birçok özellik içerir ve yardımcı Yöneticiler ayarları iOS ve macOS cihazlarını denetleyebilirsiniz. Örneğin, yöneticiler şunları yapabilir:

- Kullanıcılar, ağınızdaki AirPrint yazıcıları erişmesine
- Uygulama ve klasörleri yeni sayfalar ekleme dahil olmak üzere ana ekrana Ekle
- Varsa ve uygulama içi bildirimler gösterilen nasıl seçin
- Kilit ekranında bir ileti veya varlık etiketi, paylaşılan cihazlar için özellikle göstermek için yapılandırma
- Kullanıcıların kimlik bilgilerini uygulamalar arasında paylaşmak için güvenli çoklu oturum açma deneyimini sağlamak.
- Yetişkin dili kullanın ve izin veren veya özel web sitelerini engelleme Filtresi web siteleri

Bu özellikler, Intune'da bulunan ve yönetici tarafından yapılandırılabilir. Intune kullanır "yapılandırma profillerini" oluşturabilir ve kuruluşunuzun ihtiyaçları için bu ayarları özelleştirebilirsiniz. Bu özellikler bir profilde ekledikten sonra daha sonra anında iletme veya kuruluşunuzda iOS ve macOS cihazlarına profil dağıtmak.

Bu makalede bir cihaz yapılandırma profilinin nasıl oluşturulacağını gösterir. İçin tüm kullanılabilir ayarlar da görebilirsiniz [iOS](ios-device-features-settings.md) ve [macOS](macos-device-features-settings.md) cihazlar.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Platformunuzu seçin:
        - **iOS**
        - **macOS**
    - **Profil türü**: Seçin **cihaz özellikleri**.
    - **Ayarları**: Yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yaptıkları için bkz:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. İşiniz bittiğinde **Tamam**’ı ve değişikliklerinizi kaydetmek için **Oluştur**’u seçin.

Profil oluşturulur ve listede gösterilen. Mutlaka [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak üzere hazırdır. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

İçin tüm cihaz özelliği ayarlarını görüntüleme [iOS](ios-device-features-settings.md) ve [macOS](macos-device-features-settings.md) cihazlar.
