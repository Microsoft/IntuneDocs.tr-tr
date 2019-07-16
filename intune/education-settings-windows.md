---
title: Microsoft Intune-Azure 'da Windows 10 eğitim ayarları | Microsoft Docs
description: Windows 10 cihazları için tüm eğitim ayarlarının listesini görüntüleyin. Bu ayarları, test alma uygulaması ile bir cihaz yapılandırma profilinde kullanın, kullanıcıların veya öğrencilerin oturum açmasını, test sırasında ekranı nasıl izleyeceğinizi ve Intune 'da daha fazlasını yapın.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d5c78f72e7ffc580cce6cfec7237a3efe3ceb3e5
ms.sourcegitcommit: fd2499df5123758ecb093b4cdd486e35f713b040
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68230092"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>Intune kullanarak Windows 10 cihazlarda bir test alma uygulaması yapılandırma

Bu makalede, Windows 10 ve üzeri sürümlerini çalıştıran cihazlarda yapılandırabileceğiniz bir test uygulama ayarlarını tüm Microsoft Intune eğitimde bulabilirsiniz. Bu uygulamayı kullanarak, öğrenciler bir cihazda oturum açabilir ve bir test alabilir.

Bu ayarlar bir cihaz yapılandırma profiline eklenir ve Microsoft Intune kullanarak cihazlarınıza atanır veya dağıtılır.

[Intune 'da bir test uygulaması alma](education-settings-configure.md) bu özellik hakkında daha fazla bilgi sağlar.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Test ayarları yapın  

- **Hesap türü**: Kullanıcıların testte oturum açmasını seçin. Seçenekleriniz şunlardır:
  - Azure AD hesabı
  - Etki alanı hesabı
  - Yerel hesap
- **Hesap Kullanıcı adı**: Test alma uygulaması ile kullanılan hesabın kullanıcı adını girin. Hesapları aşağıdaki biçimde girebilirsiniz:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Değerlendirme URL 'si**: Kullanıcıların geçirmesine istediğiniz testin URL 'sini girin. URL 'YI alma hakkında daha fazla bilgi için [test alma belgelerine](https://docs.microsoft.com/education/windows/take-tests-in-windows-10)bakın.
- **Ekran izleme**: Kullanıcılar bir test yaparken ekran etkinliğini izlemeye **Izin ver** ' i seçin. **Yapılandırılmadı** , sınama sırasında ekranı izlemekten engel olur.
- **Metin önerisi**: **Izin ver** ' i seçerek test takicileri metin önerilerini görebilir. **Yapılandırılmadı** , kullanıcılar bir test sunarken metin önerilerini engeller.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu, ancak henüz bir şey yapmamış olabilir. [Profili atadığınızdan](device-profile-assign.md)emin olun ve [durumunu izleyin](device-profile-monitor.md).
