---
title: Ekleme veya Microsoft Intune - Azure eğitim ayarlarını yapılandırma | Microsoft Docs
description: Sınav zamanı uygulamasının Windows 10 ve üzeri cihazlar Intune cihaz yapılandırma profili kullanın. Eğitim settiings kullanarak bir yapılandırma profili oluşturma ve test uygulama URL'sini girin, sonra da nasıl kullanıcı oturum açma, test sırasında ekran izleme ve izin ver veya test sırasında metin önerilerine önlemek seçin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 27f573ca028c64a5aae64bc6feef707d42ad7f06
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841615"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>Windows 10 cihazlarda Microsoft Intune sınav zamanı uygulamasının kullanın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune'da eğitim profilleri, bir test veya sınavı cihazlarda gerçekleştirilecek Öğrenciler için tasarlanmıştır. Bu özellik şunları içerir **sınav** uygulama ve bir test URL'si eklemek için ayarları seçin nasıl son kullanıcılar test ve daha fazlası için oturum açın. Bu özellik, platformu destekler:

- Windows 10 ve üzeri

Kullanıcı oturum açtığında sınav zamanı uygulaması otomatik olarak girdiğiniz test ile açılır. Test sürerken cihaz üzerinde başka hiçbir uygulama çalıştırabilirsiniz. [Windows 10'da testleri ele](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) uygulamasının sınav zamanı hakkında daha fazla ayrıntı sağlar.

Bu makalede, Microsoft Intune cihaz yapılandırma profili oluşturma adımları listelenir. Ayrıca, okuma ve Windows 10 cihazlarınız için kullanılabilir eğitim ayarları hakkında bilgi edinmek için bilgi içerir.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki özellikleri girin:

    - **Ad**: Yeni profil için açıklayıcı bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Seçin **Windows 10 ve üzeri**.
    - **Profili**: Seçin **eğitim profili**.

4. Yapılandırmak istediğiniz ayarları girin:

    - [Windows 10 ve üzeri](education-settings-windows.md)

5. Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

Ayarlarınızı girdikten ve profili oluşturduktan sonra profiliniz profil listesinde gösterilir. Daha sonra [bu profili bazı gruplara atayın](device-profile-assign.md).

## <a name="next-steps"></a>Sonraki adımlar

Listesini [Windows 10 education ayarlarını](education-settings-windows.md) ve açıklamalarının.

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
