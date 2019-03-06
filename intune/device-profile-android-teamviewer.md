---
title: Microsoft Intune - Azure’da cihazları uzaktan yönetme | Microsoft Docs
description: TeamViewer'ı kullanmak için gerekli rolleri görüntüleyin, TeamViewer bağlayıcısını nasıl yükleyeceğinizi öğrenin ve Azure portalında Microsoft Intune'u kullanarak cihazları uzaktan yönetmek için adım adım yönergelere göz atın
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/05/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 968bbb345522257329cfbfe1e99289aae64269b5
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57399438"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Intune cihazlarını uzaktan yönetmek için TeamViewer kullanma

Intune tarafından yönetilen cihazlar [TeamViewer](https://www.teamviewer.com) kullanarak uzaktan yönetilebilir. TeamViewer ayrı olarak satın aldığınız üçüncü taraf bir programdır. Bu konu başlığında, TeamViewer'ı Intune’da nasıl yapılandıracağınız ve bir cihazı uzaktan nasıl yöneteceğiniz gösterilir. 

## <a name="prerequisites"></a>Önkoşullar

- Desteklenen bir cihaz kullanın. Intune ile yönetilen Android, Windows, iOS ve macOS cihazlar, uzaktan yönetimi destekler. TeamViewer Windows Holographic (HoloLens), Windows Team (Surface Hub) veya Windows 10 S. desteklemeyebilir. Desteklenebilirlik için bkz. tüm güncelleştirmeler için [TeamViewer](https://www.teamviewer.com).

- Azure portalındaki Intune yöneticisi, aşağıdaki [Intune rollerine](role-based-access-control.md) sahip olmalıdır:  

    - **Uzaktan Yardımı güncelleştirme**: Yöneticilerin TeamViewer Bağlayıcısı ayarlarını değiştirmesine izin verir
    - **Uzaktan Yardım isteği**: Herhangi bir kullanıcı için yeni bir Uzaktan Yardım oturumu başlatmak yöneticilerin sağlar. Bu role sahip kullanıcılar, bir kapsam dahilindeki herhangi bir Intune rolüyle kısıtlanmaz. Ayrıca, bir kapsam dahilinde bir Intune rolü atanmış olan kullanıcı veya cihaz grupları da uzaktan yardım isteyebilir. 

- A [TeamViewer](https://www.teamviewer.com) hesabı ile oturum açma kimlik bilgileri. TeamViewer lisansı yalnızca bazı Intune ile tümleştirmesini desteklemiyor olabilir. Belirli TeamViewer gereksinimleri için bkz. [TeamViewer tümleştirmesi iş ortağı: Microsoft Intune](https://www.teamviewer.com/integrations/microsoft-intune/).

TeamViewer'ı kullanarak TeamViewer for Intune Connector'ın TeamViewer oturumları oluşturmasına, Active Directory verilerini okumasına ve TeamViewer hesap erişim belirtecini kaydetmesine izin vermiş olursunuz.

## <a name="configure-the-teamviewer-connector"></a>TeamViewer Bağlayıcısı'nı yapılandırma

Cihazlara uzaktan yardım sağlamak için, Intune TeamViewer bağlayıcısını aşağıdaki adımları kullanarak yapılandırın:

1. [Azure portalında](https://portal.azure.com), **Tüm Hizmetler**’i seçin ve **Microsoft Intune** araması yapın.
2. **Microsoft Intune**’da **Cihazlar**’ı ve ardından **TeamViewer Bağlayıcısı**’nı seçin.
3. **Bağlan**’ı seçin ve lisans sözleşmesini kabul edin.
4. **Yetkilendirmek için TeamViewer'da Oturum Aç**'ı seçin.
5. TeamViewer sitesine bir web sayfası açılır. TeamViewer lisansı kimlik bilgilerinizi girin ve ardından **Oturum Açın**.

## <a name="remotely-administer-a-device"></a>Bir cihazı uzaktan yönetme

Bağlayıcı yapılandırıldıktan sonra bir cihazı uzaktan yönetebilirsiniz. Aşağıdaki adımları kullanın: 

1. [Azure portalında](https://portal.azure.com), **Tüm Hizmetler**’i seçin ve **Microsoft Intune** araması yapın.
2. **Microsoft Intune**’da **Cihazlar**’ı ve ardından **Tüm Cihazlar**’ı seçin.
3. Listeden uzaktan yönetmek istediğiniz cihazı seçin. Cihaz özelliklerinde **Yeni Uzaktan Yardım Oturumu**’nu seçin.
4. Intune TeamViewer hizmetine bağlandıktan sonra cihaz hakkında bazı bilgiler göreceksiniz. Uzak oturumu başlatmak için **Bağlanın**.

![TeamViewer kullanarak Android cihazı uzaktan yönetme - örnek](./media/android-teamviewer.png)

Uzak oturumu başlattığınızda, kullanıcılar kendi cihazında Şirket portalı uygulaması simgesinde bir bildirim bayrağı görür. Bir bildirim, uygulama açıldığında da görünür. Kullanıcılar, sonra Uzaktan Yardım isteğini kabul edebilir.

> [!NOTE]
> DEM ve WCD, gibi "Kullanıcısız" yöntemler kullanılarak kaydedilen Windows cihazlar, Şirket portalı uygulamasında TeamViewer bildirim gösterme. Bu senaryolarda, TeamViewer portalı oturum oluşturmak için kullanılması önerilir.

TeamViewer'da, cihazın kontrolünü ele almak da dahil olmak üzere, cihazda bir dizi işlem gerçekleştirebilirsiniz. Neler yapabileceğinizin tam ayrıntıları için bkz. [TeamViewer rehberi](https://www.teamviewer.com/support/documents/).

İşiniz bittiğinde TeamViewer penceresini kapatın.
