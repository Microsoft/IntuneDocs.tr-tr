---
title: Microsoft Intune-Azure 'da macOS çekirdek uzantısı ayarları | Microsoft Docs
titleSuffix: ''
description: Çekirdek uzantıları kullanmak için macOS cihazlarındaki ayarları ekleyin, yapılandırın veya oluşturun. Ayrıca, kullanıcıların onaylanan uzantıları geçersiz kılmasına, bir takım tanımlayıcısından tüm uzantılara izin vermelerine veya Microsoft Intune içindeki belirli uzantılara veya uygulamalara izin erişmesine izin verin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1306bfea1880061980413d283943e6521c1ac213
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730605"
---
# <a name="macos-device-settings-to-configure-and-use-kernel-extensions-in-intune"></a>Intune 'da çekirdek uzantılarını yapılandırmak ve kullanmak için macOS cihaz ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede, macOS cihazlarında denetleyebilmeniz için farklı çekirdek uzantısı ayarları listelenir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, cihazlarınıza çekirdek uzantıları eklemek ve bunları yönetmek için bu ayarları kullanın.

Intune 'da çekirdek uzantıları ve Önkoşullar hakkında daha fazla bilgi edinmek için bkz. [macOS çekirdek uzantıları ekleme](../kernel-extensions-overview-macos.md).

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra macOS cihazlarınıza atanır veya dağıtılır.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz çekirdeği Uzantıları yapılandırma profili oluşturun](../kernel-extensions-overview-macos.md).

> [!NOTE]
> Bu ayarlar farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](../macos-enroll.md).

## <a name="kernel-extensions"></a>Çekirdek uzantıları

### <a name="settings-apply-to-user-approved-automated-device-enrollment"></a>Ayarlar için geçerlidir: Kullanıcı onaylı, otomatik cihaz kaydı

- **Kullanıcı geçersiz kılmasına Izin ver**: **izin ver** , yapılandırma profilinde bulunmayan kullanıcıların çekirdek uzantılarını onaylamasını sağlar. **Yapılandırılmadı** (varsayılan), kullanıcıların yapılandırma profilinde bulunmayan uzantılara izin vermesini engeller. Anlamı olarak yalnızca yapılandırma profiline eklenen uzantılara izin verilir.

  Bu özellik hakkında daha fazla bilgi için bkz. [Kullanıcı onaylı çekirdek uzantısı yükleme](https://developer.apple.com/library/archive/technotes/tn2459/_index.html) (Apple 'ın Web sitesini açar).

- **Izin verilen takım tanımlayıcıları**: bir veya daha fazla takım kimliğine izin vermek için bu ayarı kullanın. Girdiğiniz ekip kimlikleriyle imzalanan tüm çekirdek uzantılarına izin verilir ve bunlar güvenilir. Diğer bir deyişle, belirli bir geliştirici veya iş ortağı olabilecek aynı takım KIMLIĞI içindeki tüm çekirdek uzantılarına izin vermek için bu seçeneği kullanın.

  Yüklemek istediğiniz geçerli ve imzalı çekirdek uzantılarının ekip tanımlayıcısını **ekleyin** . Birden çok takım tanımlayıcısı ekleyebilirsiniz. Takım tanımlayıcısının alfasayısal (harfler ve rakamlar) olması ve 10 karaktere sahip olması gerekir. Örneğin, şunu girin: `ABCDE12345`.

  Ekip tanımlayıcı ekledikten sonra da silinebilir.

  [Takım kimliğinizi bulun](https://help.apple.com/developer-account/#/dev55c3c710c) (Apple 'ın Web sitesini açar) daha fazla bilgi içerir.

- **Izin verilen çekirdek uzantıları**: belirli çekirdek uzantılarına izin vermek için bu ayarı kullanın. Yalnızca girdiğiniz çekirdek uzantılarına izin verilir veya güvenilir. 

  Yüklemek istediğiniz bir çekirdek uzantısının paket tanımlayıcısını ve takım tanımlayıcısını **ekleyin** . İmzasız eski çekirdek uzantıları için boş bir takım tanımlayıcısı kullanın. Birden çok çekirdek uzantısı ekleyebilirsiniz. Takım tanımlayıcısının alfasayısal (harfler ve rakamlar) olması ve 10 karaktere sahip olması gerekir. Örneğin, **paket kimliği**için `com.contoso.appname.macos` ve **takım tanımlayıcısı**için `ABCDE12345` girin.

  > [!TIP]
  > Bir macOS cihazında çekirdek uzantısının paket KIMLIĞINI (KEXT) almak için şunları yapabilirsiniz:
  >
  > 1. Terminalde `kextstat | grep -v com.apple` ' ı çalıştırın ve çıktıyı aklınızda edin. İstediğiniz yazılımı veya KEXT 'yi yükler. @No__t-0 ' ı yeniden çalıştırın ve değişiklikler olup olmadığına bakın.
  >
  >    Terminalde `kextstat`, işletim sistemindeki tüm çekirdek uzantılarını listeler. 
  >
  > 2. Cihazda, bir KEXT için bilgi özelliği liste dosyasını (Info. plist) açın. Paket KIMLIĞI gösterilir. Her bir KEXT içinde depolanan Info. plist dosyasına sahiptir. 

> [!NOTE]
> Takım tanımlayıcıları ve çekirdek uzantıları eklemeniz gerekmez. Bir veya diğerini yapılandırabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](../device-profile-assign.md) ve [durumunu izleme](../device-profile-monitor.md).
