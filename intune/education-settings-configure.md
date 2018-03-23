---
title: Windows 10 için Intune eğitim ayarlarını yapılandırma
titleSuffix: Microsoft Intune
description: Yönettiğiniz cihazlarda Windows 10 Education ayarlarını yapılandırmak için Intune’u kullanmayı öğrenin.
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6fa631cfb799fe02aee935f524a4012f381973d8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 Education ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Eğitim profilleri Windows Sınav Zamanı uygulamasının yapılandırıldığı hesap ayrıntıları ve sınav URL’si gibi ayrıntıları belirtmenize olanak tanır. Bunu yapılandırdığınızda, Sınav Zamanı uygulaması sizin belirttiğiniz sınavla başlar ve sınav tamamlanana kadar cihazda başka hiçbir uygulama çalıştırılamaz.

Sınav Zamanı uygulaması hakkında ayrıntılar için bkz. [Windows 10’da sınava girme](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Eğitim profili ayarlarını içeren bir cihaz profili oluşturma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
3. Profiller bölmesinde **Profil oluştur**’u seçin.
4. **Profil Oluştur** bölmesinde, cihaz kısıtlama profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinde **Eğitim profili**’ni seçin. 
7. **Ayarlar > Yapılandır**’ı seçin, ardından **Sınav Zamanı** bölmesinde aşağıdakileri yapılandırın:
    - **Hesap türü** - Açılan alandan hesap türünü seçin.
    - **Hesap kullanıcı adı** - Sınav Zamanı uygulamasıyla kullanılan hesabın kullanıcı adını girin. Bu bir etki alanı hesabı, Azure Active Directory (AAD) hesabı veya yerel bilgisayar hesabı olabilir.
    - **Değerlendirme URL’si** - Kullanıcılarınızın katılmasını istediğiniz sınavın URL’sini sağlayın. Daha fazla bilgi için Sınav Zamanı belgelerine bakın.
    - **Ekran yakalama** - Kullanıcılar sınavı yaparken ekran etkinliğini izlemek isteyip istemediğinizi belirtin.
    - **Metin önerisi** - Kullanıcılar sınavı yaparken metin önerilerine izin verin veya bunları engelleyin.
8. Bitirdiğinizde **Profil oluştur** bölmesine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).



