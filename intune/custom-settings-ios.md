---
title: Microsoft Intune - Azure’da iOS cihazlara özel ayarlar ekleme | Microsoft Docs
titleSuffix: ''
description: Apple Configurator veya Apple Profile Manager araçlarından iOS ayarlarını dışarı aktarın ve daha sonra bu ayarları Microsoft Intune’a aktarın. Bu ayarlar iOS cihazlarda özel ayar ve özellikler oluşturabilir, kullanabilir ve denetleyebilir. Daha sonra bu özel profil, bir ana hat veya standart oluşturmak için kuruluşunuzdaki iOS cihazlara atanabilir veya dağıtılabilir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae0ca22134e3a43cc2dfae85433a04ba8b654377
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57393526"
---
# <a name="use-custom-settings-for-ios-devices-in-microsoft-intune"></a>Microsoft Intune’da iOS cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, “özel profiller” kullanan iOS cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

iOS cihazlarda Intune’a özel ayarlar eklemenin iki yolu vardır:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

Bir yapılandırma profiline ayar aktarmak için bu araçları kullanabilirsiniz. Intune’da bu dosyayı içeri aktarır ve sonra profili, iOS kullanıcılarınıza ve cihazlarınıza atarsınız. Profil atandıktan sonra ayarlar dağıtılır ve kuruluşunuzda iOS için bir ana hat veya standart oluşturulur.

Bu makale, iOS cihazlar için özel profil oluşturma işlemini gösterir. Ayrıca Apple Configurator ve Apple Profile Manager’ı nasıl kullanacağınız konusunda rehberlik sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

- Yapılandırma profilini oluşturmak için **Apple Configurator** kullanırken dışarı aktardığınız ayarların kullandığınız cihazın iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların çözümlenmesi hakkında bilgi için [Apple Developer](https://developer.apple.com/) web sitesinde **Configuration Profile Reference** ve **Mobile Device Management Protocol Reference** başlıklarını arayın.

- **Apple Profile Manager**’ı kullanırken şunları yapmayı unutmayın:

  - Profile Manager’da [mobil cihaz yönetimini](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) etkinleştirin.
  - Profile Manager’a [iOS cihazlar](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) ekleyin.
  - Profile Manager’a cihaz ekledikten sonra **Under the Library (Kitaplık Altında)** > **Devices** (Cihazlar) seçeneğine gidip cihazınızı seçin ve **Settings** (Ayarlar) seçeneğine gidin. Cihazın genel ayarlarını girin.

    Bu dosyayı indirin ve kaydedin. Intune profilinde bu dosyayı girmeniz istenir.

  - Apple Profile Manager’dan dışarı aktardığınız ayarların kullandığınız cihazların iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların çözümlenmesi hakkında bilgi için [Apple Developer](https://developer.apple.com/) web sitesinde **Configuration Profile Reference** ve **Mobile Device Management Protocol Reference** başlıklarını arayın.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için bir ad girmeniz `ios custom profile`.
    - **Açıklama**: Profil için bir açıklama girin.
    - **Platform**: Seçin **iOS**.
    - **Profil türü**: Seçin **özel**.

4. **Özel yapılandırma**’da şu ayarları girin:

    - **Özel yapılandırma profili adı**: İlke için bir ad girin. Bu ad, cihazda ve Intune durumunda gösterilir.
    - **Yapılandırma profili dosyası**: Apple Configurator veya Apple profili Manager'ı kullanarak oluşturduğunuz yapılandırma profiline göz atın. İçeri aktardığınız dosya, **Dosya içeriği** alanında görüntülenir.

5. **Tamam** > **Oluştur**’a tıklayarak Intune profilini oluşturun. Profiliniz oluşturulduğunda **Cihaz yapılandırması - Profiller** listesinde görünür.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

Bkz. [macOS cihazlarda profil oluşturma](custom-settings-macos.md). 
