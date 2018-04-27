---
title: Microsoft Intune - Azure’da Endpoint Protection ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da bir macOS veya Windows 10 cihaz profili oluşturduğunuzda Endpoint Protection ayarları oluşturun.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b960b837cef5941fac829eeb878eb520b0274fba
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Intune’da Endpoint Protection ayarları ekleme

Endpoint Protection; cihazlarınızda güvenlik duvarı, bitlocker, uygulamaya izin verme ve uygulama engelleme, Windows Defender ve şifreleme gibi pek çok farklı güvenlik özelliğini kontrol etmenize olanak verir. Microsoft Intune’da bu ayarları, cihaz profillerini kullanarak yapılandırabilirsiniz.

Örneğin yalnızca macOS kullanıcılarının Mac App Store’dan uygulama indirmesine izin veren bir Endpoint Protection profili oluşturabilirsiniz. Veya Windows 10 cihazlarda uygulama çalıştırırken Windows SmartScreen’i etkinleştirebilirsiniz.

Bu makalede, bir profilin nasıl oluşturulacağı gösterilir. Daha sonra kullanılabilir ayarlar hakkında daha fazla ayrıntı için cihaz platformunuzu seçin.

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Endpoint Protection ayarlarını içeren bir cihaz profili oluşturma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Endpoint Protection profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
   - **macOS**
   - **Windows 10 ve üzeri**
6. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin. 
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)
8. Bitirdiğinizde **Profil oluştur** sayfasına dönün ve **Oluştur**'a tıklayın.

Profil oluşturulur ve profil listesi sayfasında görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).

## <a name="next-steps"></a>Sonraki adımlar
Bir profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).
