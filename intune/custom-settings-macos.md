---
title: Microsoft Intune - Azure’da macOS cihazlara özel ayarlar ekleme | Microsoft Docs
titleSuffix: ''
description: Apple Configurator veya Apple Profile Manager araçlarından macOS ayarlarını dışarı aktarın ve daha sonra bu ayarları Microsoft Intune’a aktarın. Bu ayarlar macOS cihazlarda özel ayar ve özellikler oluşturabilir, kullanabilir ve denetleyebilir. Daha sonra bu özel profil, bir ana hat veya standart oluşturmak için kuruluşunuzdaki macOS cihazlara atanabilir veya dağıtılabilir.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3136088f307d8e2e83faaccafbda4ad2664c6f62
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183222"
---
# <a name="use-custom-settings-for-macos-devices-in-microsoft-intune"></a>Microsoft Intune’da macOS cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, bir “özel profil” kullanan macOS cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

macOS cihazlarda Intune’a özel ayarlar eklemenin iki yolu vardır:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

Bir yapılandırma profiline ayar aktarmak için bu araçları kullanabilirsiniz. Intune’da bu dosyayı içeri aktarır ve sonra profili, macOS kullanıcılarınıza ve cihazlarınıza atarsınız. Profil atandıktan sonra ayarlar dağıtılır ve kuruluşunuzda macOS için bir ana hat veya standart oluşturulur.

Bu makale, macOS cihazlar için özel profil oluşturma işlemini gösterir. Ayrıca Apple Configurator ve Apple Profile Manager’ı nasıl kullanacağınız konusunda rehberlik sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

- Yapılandırma profilini oluşturmak için **Apple Configurator** kullanırken dışarı aktardığınız ayarların kullandığınız cihazın macOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların çözümlenmesi hakkında bilgi için [Apple Developer](https://developer.apple.com/) web sitesinde **Configuration Profile Reference** ve **Mobile Device Management Protocol Reference** başlıklarını arayın.

- **Apple Profile Manager**’ı kullanırken şunları yapmayı unutmayın:

  - Profile Manager’da [mobil cihaz yönetimini](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) etkinleştirin.
  - Profile Manager’a [macOS cihazlar](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) ekleyin.
  - Profile Manager’a cihaz ekledikten sonra **Under the Library (Kitaplık Altında)** > **Devices** (Cihazlar) seçeneğine gidip cihazınızı seçin ve **Settings** (Ayarlar) seçeneğine gidin. Cihaz için genel ayarlar ile güvenlik, gizlilik, dizin ve sertifika ayarlarını girin.

    Bu dosyayı indirin ve kaydedin. Intune profilinde bu dosyayı girmeniz istenir. 

  - Apple Profile Manager’dan dışarı aktardığınız ayarların kullandığınız cihazların macOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların çözümlenmesi hakkında bilgi için [Apple Developer](https://developer.apple.com/) web sitesinde **Configuration Profile Reference** ve **Mobile Device Management Protocol Reference** başlıklarını arayın.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Profil için `macos custom profile` gibi bir ad girin.
    - **Açıklama**: Profil için bir açıklama girin.
    - **Platform**: **macOS**’u seçin.
    - **Profil türü**: **Özel**’i seçin.

4. **Özel yapılandırma**’da şu ayarları girin:

    - **Özel yapılandırma profili adı**: İlke için bir ad girin. Bu ad, cihazda ve Intune durumunda gösterilir.
    - **Yapılandırma profili dosyası**: Apple Configurator veya Apple Profile Manager’ı kullanarak oluşturduğunuz yapılandırma profiline gidin. İçeri aktardığınız dosya, **Dosya içeriği** alanında görüntülenir.

5. **Tamam** > **Oluştur**’a tıklayarak Intune profilini oluşturun. Profiliniz oluşturulduğunda **Cihaz yapılandırması - Profiller** listesinde görünür.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Daha sonra, [profili atayın](device-profile-assign.md).

Bkz. [iOS cihazlarda profil oluşturma](custom-settings-ios.md).