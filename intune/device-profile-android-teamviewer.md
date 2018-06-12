---
title: Microsoft Intune - Azure’da cihazları uzaktan yönetme | Microsoft Docs
description: TeamViewer'ı kullanmak için gerekli rolleri görüntüleyin, TeamViewer bağlayıcısını nasıl yükleyeceğinizi öğrenin ve Azure portalında Microsoft Intune'u kullanarak cihazları uzaktan yönetmek için adım adım yönergelere göz atın
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 60d9398b80a30adee194470ac4e5c6c1efc0bd4c
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744644"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Intune cihazlarını uzaktan yönetmek için TeamViewer kullanma

Intune tarafından yönetilen cihazlar [TeamViewer](https://www.teamviewer.com) kullanarak uzaktan yönetilebilir. TeamViewer ayrı olarak satın aldığınız üçüncü taraf bir programdır. Bu konu başlığında, TeamViewer'ı Intune’da nasıl yapılandıracağınız ve bir cihazı uzaktan nasıl yöneteceğiniz gösterilir. 

## <a name="prerequisites"></a>Önkoşullar

- Desteklenen bir cihaz kullanın. Intune ile yönetilen Android, Windows, iOS ve macOS cihazlar, uzaktan yönetimi destekler. TeamViewer Windows Holographic (HoloLens), Windows Team (Surface Hub) veya Windows 10 S. desteklemeyebilir. Desteklenebilirlik için bkz. tüm güncelleştirmeler için [TeamViewer](https://www.teamviewer.com).

- Azure portalındaki Intune yöneticisi, aşağıdaki [Intune rollerine](role-based-access-control.md) sahip olmalıdır:  

    - **Uzaktan Yardımı Güncelleştirme**: Yöneticilerin TeamViewer bağlayıcısı ayarlarını değiştirmesine olanak tanır
    - **Uzaktan Yardım İsteği**: Yöneticilerin herhangi bir kullanıcı için yeni bir Uzaktan Yardım oturumu başlatmasına olanak tanır. Bu role sahip kullanıcılar, bir kapsam dahilindeki herhangi bir Intune rolüyle kısıtlanmaz. Ayrıca, bir kapsam dahilinde bir Intune rolü atanmış olan kullanıcı veya cihaz grupları da uzaktan yardım isteyebilir. 

- Oturum açma kimlik bilgileri ile bir [TeamViewer](https://www.teamviewer.com) hesabı

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

Bir uzak oturumu başlattığınızda, bir son kullanıcı kendi cihazında Şirket Portalı uygulaması simgesinde bir bildirim bayrağı görür. Uygulama açıldığında da bir bildirim görüntülenir. Daha sonra kullanıcı uzaktan yardım isteğini kabul edebilir.

TeamViewer'da, cihazın kontrolünü ele almak da dahil olmak üzere, cihazda bir dizi işlem gerçekleştirebilirsiniz. Neler yapabileceğinizin tam ayrıntıları için bkz. [TeamViewer rehberi](https://www.teamviewer.com/support/documents/).

İşiniz bittiğinde TeamViewer penceresini kapatın.