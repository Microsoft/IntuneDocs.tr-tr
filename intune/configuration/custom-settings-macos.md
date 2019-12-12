---
title: Microsoft Intune - Azure’da macOS cihazlara özel ayarlar ekleme | Microsoft Docs
titleSuffix: ''
description: Apple Configurator veya Apple Profile Manager araçlarından macOS ayarlarını dışarı aktarın ve daha sonra bu ayarları Microsoft Intune’a aktarın. Bu ayarlar, macOS cihazlarında özel ayarları ve özellikleri oluşturabilir, kullanabilir ve denetleyebilir. Daha sonra bu özel profil, bir ana hat veya standart oluşturmak için kuruluşunuzdaki macOS cihazlara atanabilir veya dağıtılabilir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c24c120b033a4db0162e985ef185932dd931eda
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506929"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Microsoft Intune’da macOS cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, bir “özel profil” kullanan macOS cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

macOS cihazlarda Intune’a özel ayarlar eklemenin iki yolu vardır:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

Bir yapılandırma profiline ayar aktarmak için bu araçları kullanabilirsiniz. Intune’da bu dosyayı içeri aktarır ve sonra profili, macOS kullanıcılarınıza ve cihazlarınıza atarsınız. Atandıktan sonra ayarlar dağıtılır. Ayrıca, kuruluşunuzda macOS için bir taban çizgisi veya standart oluşturur.

Bu makalede, Apple Configurator ve Apple Profile Manager kullanımı hakkında bazı yönergeler sağlanır ve yapılandırabileceğiniz özellikler açıklanmaktadır.

## <a name="before-you-begin"></a>Başlamadan önce

[Profili oluşturun](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- Yapılandırma profilini oluşturmak için **Apple Configurator** kullanırken, dışarı aktarma yaptığınız ayarların cihazlardaki MacOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların çözümlenmesi hakkında bilgi için [Apple Developer](https://developer.apple.com/) web sitesinde **Configuration Profile Reference** ve **Mobile Device Management Protocol Reference** başlıklarını arayın.

- **Apple Profile Manager**’ı kullanırken şunları yapmayı unutmayın:

  - Profile Manager’da [mobil cihaz yönetimini](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) etkinleştirin.
  - Profile Manager’a [macOS cihazlar](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) ekleyin.
  - Profile Manager’a cihaz ekledikten sonra **Under the Library (Kitaplık Altında)**  > **Devices** (Cihazlar) seçeneğine gidip cihazınızı seçin ve **Settings** (Ayarlar) seçeneğine gidin. Cihaz için genel ayarlar ile güvenlik, gizlilik, dizin ve sertifika ayarlarını girin.

    Bu dosyayı indirin ve kaydedin. Intune profilinde bu dosyayı girmeniz istenir. 

  - Apple Profile Manager 'dan dışarı verdiğiniz ayarların cihazlardaki macOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların çözümlenmesi hakkında bilgi için [Apple Developer](https://developer.apple.com/) web sitesinde **Configuration Profile Reference** ve **Mobile Device Management Protocol Reference** başlıklarını arayın.

## <a name="custom-configuration-profile-settings"></a>Özel yapılandırma profili ayarları

- **Özel yapılandırma profili adı**: İlke için bir ad girin. Bu ad, cihazda ve Intune durumunda gösterilir.
- **Yapılandırma profili dosyası**: Apple Configurator veya Apple Profile Manager’ı kullanarak oluşturduğunuz yapılandırma profiline gidin. İçeri aktardığınız dosya, **Dosya içeriği** alanında görüntülenir.

  Ayrıca, `.mobileconfig` dosyalarınıza cihaz belirteçleri ekleyebilirsiniz. Cihaz belirteçleri cihaza özgü bilgileri eklemek için kullanılır. Örneğin, seri numarasını göstermek için `{{serialnumber}}`girin. Cihazda, metin her bir cihaz için benzersiz olan `123456789ABC`benzer şekilde görünür. Değişken girerken `{{ }}`kaşlı ayraç kullandığınızdan emin olun. [Uygulama yapılandırma belirteçleri](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) , kullanılabilecek değişkenlerin bir listesini içerir. `deviceid` veya başka bir cihaza özgü değeri de kullanabilirsiniz.

  > [!NOTE]
  > Değişkenler kullanıcı arabiriminde doğrulanmaz ve büyük/küçük harfe duyarlıdır. Sonuç olarak, yanlış girişle kaydedilmiş profiller görebilirsiniz. Örneğin, `{{deviceid}}`yerine `{{DeviceID}}` girerseniz, aygıtın benzersiz KIMLIĞI yerine değişmez dize gösterilir. Doğru bilgileri girdiğinizden emin olun.

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin. Profil oluşturulur ve profiller listesinde gösterilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

Bkz. [iOS cihazlarda profil oluşturma](../custom-settings-ios.md).
