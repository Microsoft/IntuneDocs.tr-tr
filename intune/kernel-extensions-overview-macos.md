---
title: MacOS Microsoft Intune - Azure çekirdek uzantıları cihaz profili oluşturma | Microsoft Docs
titleSuffix: ''
description: Ekleme veya macOS cihaz profili oluşturma ve ardından kullanıcı geçersiz kılmaya izin ver, takım tanımlayıcısı ve bir paket ve takım kimliği Intune eklemek için çekirdek uzantılarını yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd2e03c09cb2bed49ee7607283bf63e2c3ae67da
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67404015"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Intune'da macOS çekirdek uzantıları ekleme

MacOS cihazlarında çekirdek düzeyinde özellikler ekleyebilirsiniz. Bu özellikler normal programlar erişemiyor işletim sistemi bölümlerini erişin. Kuruluşunuzun belirli gereksinimlerine veya bir uygulama, bir cihaz özelliği ve benzeri kullanılamayan gereksinimleri olabilir. 

Her zaman cihazlarınıza yüklemek için izin verilen çekirdek uzantıları eklemek için "çekirdek uzantıları" ekleyin (KEXT) Intune ve ardından bu uzantıları cihazlarınıza dağıtın.

Örneğin, Cihazınızı kötü amaçlı içerik tarar virüs tarama programı var. İzin verilen çekirdek uzantı Intune olarak programın çekirdek uzantısı bu virüs ekleyebilirsiniz. Ardından, "uzantı macOS cihazlarınızda atayın".

Bu özellik ile Yöneticiler, kullanıcıların geçersiz kılma çekirdek uzantıları, takım tanımlayıcılar ekleme ve Intune'a belirli çekirdek uzantıları ekleme izin verebilir.

Bu özellik şu platformlarda geçerlidir:

- macOS 10.13.2 ve üzeri

Bu özelliği kullanmak için cihazlar olmalıdır:

- Apple cihaz kayıt programı (DEP) kullanarak Intune'a kayıtlı. [Otomatik olarak macOS cihazlarını kaydetme](device-enrollment-program-enroll-macos.md) daha fazla bilgi bulunur.

  OR

- "Kullanıcı onaylı kaydıyla" Intune'a kayıtlı (Apple'nın terimi). [MacOS High Sierra uzantıları çekirdek değişiklikleri hazırlama](https://support.apple.com/en-us/HT208019) (Apple web sitesini açar) daha fazla bilgi bulunur.

Intune kullanır "yapılandırma profillerini" oluşturabilir ve kuruluşunuzun ihtiyaçları için bu ayarları özelleştirebilirsiniz. Bu özellikler bir profilde ekledikten sonra daha sonra anında iletme veya kuruluşunuzda macOS cihazlarına profil dağıtmak.

Bu makalede çekirdek uzantılarıyla Intune'da cihaz yapılandırma profili oluşturma işlemini gösterir.

> [!TIP]
> Çekirdek uzantıları hakkında daha fazla bilgi için bkz. [çekirdek uzantısına genel bakış](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (Apple web sitesini açar).

## <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- İmzasız eski çekirdek uzantıları eklenebilir.
- Doğru takım tanımlayıcısı girin ve paket Kimliğini çekirdek uzantının emin olun. Intune, girdiğiniz değerler doğrulamaz. Yanlış bilgi girerseniz, uzantı cihazda çalışmaz.

> [!NOTE]
> Apple imzalama ve tüm yazılımlar için notarization bilgi yayımladı. Macos'ta 10.14.5 ve daha yeni sürümü, çekirdek uzantıları Intune aracılığıyla dağıtılan Apple'nın notarization ilkeyi karşılamak zorunda değilsiniz.
>
> Bu notarization ilke ve herhangi bir güncelleştirme veya değişiklik hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:
>
>  - [Uygulamanızın dağıtım önce notarizing](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (Apple web sitesi açılır) 
>  - [MacOS High Sierra uzantıları çekirdek değişiklikleri hazırlama](https://support.apple.com/en-us/HT208019) (Apple web sitesi açılır)

## <a name="create-the-profile"></a>Profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Seçin **macOS**
    - **Profil türü**: Seçin **uzantıları**.
    - **Ayarları**: Yapılandırmak istediğiniz ayarları girin. Tüm ayarların bir listesi ve ne yaptıkları için bkz:

        - [macOS](kernel-extensions-settings-macos.md)

4. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin.

Profil oluşturulur ve listede gösterilen. Mutlaka [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduktan sonra atanmak üzere hazırdır. Ardından [profili atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).
