---
title: Microsoft Intune - Azure’da Endpoint Protection ayarlarını yapılandırma | Microsoft Docs
description: Microsoft Intune’da bir macOS veya Windows 10 cihaz profili oluşturduğunuzda Endpoint Protection ayarları oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: 1a5cd898545bae51395352d5cf1e7b1ee9bd22dd
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883242"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Intune’da Endpoint Protection ayarları ekleme

Intune ile, cihazlarda aşağıdakiler de dahil olmak üzere ortak uç nokta koruma güvenlik özelliklerini yönetmek için cihaz yapılandırma profillerini kullanabilirsiniz:
- Güvenlik Duvarı 
- BitLocker
- Uygulamalara izin verme ve bunları engelleme  
- Windows Defender ve şifreleme

Örneğin yalnızca macOS kullanıcılarının Mac App Store’dan uygulama indirmesine izin veren bir Endpoint Protection profili oluşturabilirsiniz. Veya Windows 10 cihazlarda uygulama çalıştırırken Windows SmartScreen’i etkinleştirebilirsiniz.

Bir profil oluşturmadan önce, Intune 'un desteklenen her platform için yöneteceği Endpoint Protection ayarlarını ayrıntılandırın aşağıdaki makalelerini gözden geçirin: 
- [macOS ayarları](endpoint-protection-macos.md)
- [Windows 10 ayarları](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Endpoint Protection ayarlarını içeren bir cihaz profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Endpoint Protection profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
   - **macOS**
   - **Windows 10 ve üzeri**
6. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin. 
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Bkz.
   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)  

8. Geçerli ayarları yapılandırdıktan sonra **Profil oluştur** sayfasında **Oluştur** ' u seçin.

   Profil oluşturulur ve profil listesi sayfasında görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).


## <a name="next-steps"></a>Sonraki adımlar  

Bir profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).
