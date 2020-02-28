---
title: Microsoft Intune - Azure’da cihazları uzaktan yönetme | Microsoft Docs
description: TeamViewer'ı kullanmak için gerekli rolleri görüntüleyin, TeamViewer bağlayıcısını nasıl yükleyeceğinizi öğrenin ve Azure portalında Microsoft Intune'u kullanarak cihazları uzaktan yönetmek için adım adım yönergelere göz atın
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fede9e67e77804ca293bbe9889d5a6623e4ea90c
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781130"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Intune cihazlarını uzaktan yönetmek için TeamViewer kullanma

Intune tarafından yönetilen cihazlar [TeamViewer](https://www.teamviewer.com) kullanarak uzaktan yönetilebilir. TeamViewer ayrı olarak satın aldığınız üçüncü taraf bir programdır. Bu konu başlığında, TeamViewer'ı Intune’da nasıl yapılandıracağınız ve bir cihazı uzaktan nasıl yöneteceğiniz gösterilir. 

## <a name="prerequisites"></a>Önkoşullar

- Desteklenen bir cihaz kullanın. Intune ile yönetilen Android Cihaz Yöneticisi, Android Iş profili, Windows, iOS/ıpados ve macOS cihazları uzaktan yönetimi destekler. TeamViewer Windows Holographic (HoloLens), Windows Team (Surface Hub) veya Windows 10 S. desteklemeyebilir. Desteklenebilirlik için bkz. tüm güncelleştirmeler için [TeamViewer](https://www.teamviewer.com).

> [!NOTE]
> Android adanmış ve tam olarak yönetilen desteklenmez.

- Azure portalındaki Intune yöneticisi, aşağıdaki [Intune rollerine](../fundamentals/role-based-access-control.md) sahip olmalıdır:  

  - **Uzaktan Yardımı Güncelleştirme**: Yöneticilerin TeamViewer bağlayıcısı ayarlarını değiştirmesine olanak tanır
  - **Uzaktan Yardım İsteği**: Yöneticilerin herhangi bir kullanıcı için yeni bir Uzaktan Yardım oturumu başlatmasına olanak tanır. Bu role sahip kullanıcılar, bir kapsam dahilindeki herhangi bir Intune rolüyle kısıtlanmaz. Ayrıca, bir kapsam dahilinde bir Intune rolü atanmış olan kullanıcı veya cihaz grupları da uzaktan yardım isteyebilir. 

- Oturum açma kimlik bilgilerine sahip bir [TeamViewer](https://www.teamviewer.com) hesabı. Yalnızca bazı TeamViewer lisansları, Intune ile tümleştirmeyi destekleyebilir. Belirli TeamViewer ihtiyaçları için bkz. [TeamViewer Integration partner: Microsoft Intune](https://www.teamviewer.com/integrations/microsoft-intune/).

TeamViewer'ı kullanarak TeamViewer for Intune Connector'ın TeamViewer oturumları oluşturmasına, Active Directory verilerini okumasına ve TeamViewer hesap erişim belirtecini kaydetmesine izin vermiş olursunuz.

## <a name="configure-the-teamviewer-connector"></a>TeamViewer Bağlayıcısı'nı yapılandırma

Cihazlara uzaktan yardım sağlamak için, Intune TeamViewer bağlayıcısını aşağıdaki adımları kullanarak yapılandırın:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2.  >  **bağlayıcıları ve belirteçleri** > **TeamViewer Bağlayıcısı**' nı seçin.
3. **Bağlan**’ı seçin ve lisans sözleşmesini kabul edin.
4. **Yetkilendirmek için TeamViewer'da Oturum Aç**'ı seçin.
5. TeamViewer sitesine bir web sayfası açılır. TeamViewer lisansı kimlik bilgilerinizi girin ve ardından **Oturum Açın**.

## <a name="remotely-administer-a-device"></a>Bir cihazı uzaktan yönetme

Bağlayıcı yapılandırıldıktan sonra bir cihazı uzaktan yönetebilirsiniz. Aşağıdaki adımları kullanın: 

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431).
2. **Cihazlar**’ı ve ardından **Tüm cihazlar**’ı seçin.
3. Listeden uzaktan yönetmek istediğiniz cihazı seçin > **...** **Yeni uzaktan yardım oturumu** > .
4. Intune TeamViewer hizmetine bağlandıktan sonra cihaz hakkında bazı bilgiler göreceksiniz. Uzak oturumu başlatmak için **Bağlanın**.

![TeamViewer kullanarak Android cihazı uzaktan yönetme - örnek](./media/teamviewer-support/android-teamviewer.png)

Bir uzak oturum başlattığınızda, kullanıcılar cihazındaki Şirket Portalı uygulama simgesinde bir bildirim bayrağı görür. Uygulama açıldığında bir bildirim de görüntülenir. Kullanıcılar daha sonra uzaktan yardım isteğini kabul edebilir.

> [!NOTE]
> DEM ve WCD gibi "kullanıcısız" yöntemler kullanılarak kaydedilen Windows cihazları, Şirket Portalı uygulamasında TeamViewer bildirimini göstermez. Bu senaryolarda, oturumu oluşturmak için TeamViewer portalını kullanmanız önerilir.

TeamViewer'da, cihazın kontrolünü ele almak da dahil olmak üzere, cihazda bir dizi işlem gerçekleştirebilirsiniz. Neler yapabileceğinizin tam ayrıntıları için bkz. [TeamViewer rehberi](https://www.teamviewer.com/support/documents/).

İşiniz bittiğinde TeamViewer penceresini kapatın.
