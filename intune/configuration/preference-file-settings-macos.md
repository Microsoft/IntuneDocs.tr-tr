---
title: Microsoft Intune-Azure 'da macOS cihazlarına tercih dosyası ayarları ekleme | Microsoft Docs
titleSuffix: ''
description: Uygulamanız hakkında önemli bilgileri içeren bir XML veya plist dosyası ekleyin. Özellik Listesi dosyasındaki anahtar bilgilerini değiştirmek ve macOS cihazlarınıza atamak için bir tercih dosyası cihaz yapılandırma profili kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ed04c1bf135793da9cece9debc2c7cdd481601a
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74691684"
---
# <a name="add-a-property-list-file-to-macos-devices-using-microsoft-intune"></a>Microsoft Intune kullanarak macOS cihazlarına bir özellik listesi dosyası ekleyin

Microsoft Intune kullanarak, macOS cihazları için bir özellik listesi dosyası (. plist) veya macOS cihazlarındaki uygulamalar ekleyebilirsiniz.

Bu özellik şu platformlarda geçerlidir:

- 10,7 ve daha yeni çalıştıran macOS cihazları

Özellik listesi dosyaları genellikle macOS uygulamalarıyla ilgili bilgileri içerir. Daha fazla bilgi için bkz. [bilgi özellik listesi dosyaları](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple 'ın Web sitesi) ve [özel yük ayarları](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)hakkında.

Bu makalede, macOS cihazlarına ekleyebileceğiniz farklı özellik listesi dosyası ayarları listelenir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, uygulama paketi KIMLIĞINI (`com.company.application`) eklemek ve. plist dosyasını eklemek için bu ayarları kullanın.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra macOS cihazlarınıza atanır veya dağıtılır.

## <a name="before-you-begin"></a>Başlamadan önce

[Profili oluşturun](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- Bu ayarlar doğrulanmaz. Profili cihazlarınıza atamadan önce değişikliklerinizi test ettiğinizden emin olun.
- Uygulama anahtarı girme konusunda emin değilseniz, uygulama içindeki ayarı değiştirin. Ardından, ayarın nasıl yapılandırıldığını görmek için [Xcode](https://developer.apple.com/xcode/) kullanarak uygulamanın tercih dosyasını gözden geçirin. Apple, dosyayı içeri aktarmadan önce Xcode kullanılarak yönetilebilir olmayan ayarların kaldırılmasını önerir.
- Yalnızca bazı uygulamalar yönetilen tercihlerle çalışır ve tüm ayarları yönetmenize izin verebilir.
- Kullanıcı kanalı ayarlarını değil cihaz kanalı ayarlarını hedef alan özellik listesi dosyalarını karşıya yüklediğinizden emin olun. Özellik listesi dosyaları tüm cihazı hedefleyin.

## <a name="preference-file"></a>Tercih dosyası

- **Tercih etki alanı adı**: özellik listesi dosyaları genellikle Web tarayıcıları (Microsoft Edge), [Microsoft Defender Gelişmiş tehdit koruması](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac)ve özel uygulamalar için kullanılır. Bir tercih etki alanı oluşturduğunuzda, bir paket KIMLIĞI de oluşturulur. `com.company.application`gibi paket KIMLIĞINI girin. Örneğin `com.Contoso.applicationName`, `com.Microsoft.Edge` veya `com.microsoft.wdav`girin.
- **Özellik listesi dosyası**: uygulamanızla ilişkili özellik listesi dosyasını seçin. Bir `.plist` veya `.xml` dosyası olduğundan emin olun. Örneğin, bir `YourApp-Manifest.plist` veya `YourApp-Manifest.xml` dosyası yükleyin.
- **Dosya içeriği**: Özellik Listesi dosyasındaki önemli bilgiler gösterilir. Anahtar bilgilerini değiştirmeniz gerekiyorsa, liste dosyasını başka bir düzenleyicide açın ve ardından dosyayı Intune 'A yeniden yükleyin.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturulur ve profiller listesinde gösterilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

Microsoft Edge için tercih dosyaları hakkında daha fazla bilgi için bkz. [macOS 'Ta Microsoft Edge ilke ayarlarını yapılandırma](https://docs.microsoft.com/deployedge/configure-microsoft-edge-on-mac).
