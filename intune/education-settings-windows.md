---
title: Windows 10 education ayarlarını Microsoft Intune - Azure | Microsoft Docs
description: Windows 10 cihazlar için tüm eğitim ayarlarını bir listesini görürsünüz. Bu cihaz yapılandırma profili ayarlarında bir Test uygulaması sınav zamanı uygulamasıyla kullanın, İzleyicisi'nde, test sırasında ekran ve diğer Intune kullanıcıları veya Öğrenciler nasıl oturum seçin.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 206bc3276f3c175fe61852f235c722b835ad60b4
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57564865"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Intune kullanarak Windows 10 cihazlarda sınav zamanı uygulaması yapılandırma

Bu makalede, tüm Windows 10 ve üstünü çalıştıran cihazlarda yapılandırabileceğiniz ayarların Intune eğitim alın uygulaması gösterilmektedir. Bu uygulamayı kullanarak Öğrenciler bir cihazda oturum açın ve sınav.

Bu ayarları bir cihaz yapılandırma profili eklendiğinde ve sonra atanan veya Microsoft Intune kullanarak cihazlarınızı dağıtılmış.

[Intune'da bir Test uygulaması ele](education-settings-configure.md) bu özellik hakkında daha fazla bilgi sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Sınav ayarları

- **Hesap türü**: Kullanıcılar teste nasıl oturum seçin. Seçenekleriniz şunlardır:
  - Azure AD hesabı
  - Etki alanı hesabı
  - Yerel hesap
- **Hesap kullanıcı adı**: Kullanıcı hesabının adını, bir Test uygulaması sınav zamanı uygulamasıyla kullanılan. Hesapları şu biçimde girebilirsiniz:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Değerlendirme URL'si**: Kullanıcılarınızın istediğiniz test URL'sini girin. URL alma hakkında daha fazla bilgi için bkz. [testi dokümantasyonu almak](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).
- **Ekran izleme**: Seçin **izin** kullanıcılar sınavı yaparken ekran etkinliğini izlemek için. **Yapılandırılmamış** test sırasında ekran izleme işleminden engeller.
- **Metin önerisi**: Seçin **izin** test girenlerin metin önerilerine görebilirsiniz. **Yapılandırılmamış** kullanıcılar bir sınavı yaparken metin önerilerine engeller.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur, ancak, hiçbir şey henüz yapmadan. Mutlaka [profili atama](device-profile-assign.md), ve [atamanın durumunu izlemenize](device-profile-monitor.md).
