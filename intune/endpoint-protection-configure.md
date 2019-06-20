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
ms.openlocfilehash: 2bebdf712ccf325c6742e6bb326a8fb2768023b7
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251179"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Intune’da Endpoint Protection ayarları ekleme

Intune ile cihaz yapılandırma profilleri cihazlarda da dahil olmak üzere ortak uç nokta koruma güvenlik özelliklerini yönetmek için kullanabilirsiniz:
- Güvenlik Duvarı 
- BitLocker
- İzin verme ve uygulamaları engelleme  
- Windows Defender ve şifreleme

Örneğin yalnızca macOS kullanıcılarının Mac App Store’dan uygulama indirmesine izin veren bir Endpoint Protection profili oluşturabilirsiniz. Veya Windows 10 cihazlarda uygulama çalıştırırken Windows SmartScreen’i etkinleştirebilirsiniz.

Bir profili oluşturmadan önce desteklenen her platform için Intune endpoint protection ayarları yönetebilir, ayrıntı aşağıdaki makaleleri inceleyin: 
   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Endpoint Protection ayarlarını içeren bir cihaz profili oluşturma

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Endpoint Protection profili için bir **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, özel ayarları uygulamak istediğiniz cihaz platformunu seçin. Şu anda, cihaz kısıtlama ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
   - **macOS**
   - **Windows 10 ve üzeri**
6. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin. 
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Bkz.
   - [macOS ayarları](endpoint-protection-macos.md)
   - [Windows 10 ayarları](endpoint-protection-windows-10.md)  

8. Uygun ayarları yapılandırdıktan sonra seçin **Oluştur** üzerinde **profili oluşturma** sayfası.

   Profil oluşturulur ve profil listesi sayfasında görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).


## <a name="next-steps"></a>Sonraki adımlar  

Bir profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).
