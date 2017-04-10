---
title: "Intune eğitim ayarlarını yapılandırma"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Yönettiğiniz cihazlarda eğitim ayarlarını yapılandırmak için Intune’u kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 5c73719c4fd2805f91c6af3ba48c39f5d798aaeb
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-education-settings-in-microsoft-intune"></a>Microsoft Intune’da eğitim ayarlarını yapılandırma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Eğitim profilleri Windows Sınav Zamanı uygulamasının yapılandırıldığı hesap ayrıntıları ve sınav URL’si gibi ayrıntıları belirtmenize olanak tanır. Bunu yapılandırdığınızda, Sınav Zamanı uygulaması sizin belirttiğiniz sınavla başlar ve sınav tamamlanana kadar cihazda başka hiçbir uygulama çalıştırılamaz.

Bu konu başlığı altında verilen bilgileri kullanarak cihaz kısıtlama profillerini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Eğitim profili ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, cihaz kısıtlama profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinde **Eğitim profili**’ni seçin. 
7. Ayarlar > Yapılandır’ı seçin, ardından **Sınav Zamanı** dikey penceresinde aşağıdakileri yapılandırın:
    - **Hesap kullanıcı adı** - Sınav Zamanı uygulamasıyla kullanılan hesabın kullanıcı adını girin. Bu bir etki alanı hesabı, Azure Active Directory (AAD) hesabı veya yerel bilgisayar hesabı olabilir.
    - **Değerlendirme URL’si** - Kullanıcılarınızın katılmasını istediğiniz sınavın URL’sini sağlayın. Daha fazla bilgi için Sınav Zamanı belgelerine bakın.
    - **Ekran yakalama** - Kullanıcılar sınavı yaparken ekran etkinliğini izlemek isteyip istemediğinizi belirtin.
    - **Metin önerisi** - Kullanıcılar sınavı yaparken metin önerilerine izin verin veya bunları engelleyin.
8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine gidin ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).




