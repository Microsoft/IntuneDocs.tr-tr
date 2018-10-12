---
title: Hızlı Başlangıç - Intune'da otomatik kayıt ayarlama
description: Hızlı Başlangıç - Intune'da Windows 10 cihazları için otomatik kayıt ayarlayın.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 3b713f090fb6ada884a269e286f55f6e1b1087c4
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581776"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Hızlı Başlangıç: Windows 10 cihazları için otomatik kayıt ayarlama

Bu hızlı başlangıçta Microsoft Intune'u, belirli kullanıcılar Windows 10 cihazlarında oturum açtığında bu cihazları otomatik kaydetmeye ayarlayacaksınız.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için önce [bir kullanıcı oluşturun](quickstart-create-user.md) ve [bir grup oluşturun](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)'da Genel Yönetici veya Intune Hizmet Yöneticisi olarak oturum açın.

## <a name="set-up-windows-10-automatic-enrollment"></a>Windows 10 otomatik kaydını ayarlama

Bu örnekte gerek kurumsal gerekse "kendininkini getir" cihazlarının otomatik kaydolabilmesi için MDM kaydını kullanacaksınız.

1. Azure'da **Azure Active Directory** > **Mobilite (MDM ve MAM)** > **Microsoft Intune** > **Bazı**'yı seçin.
![Tarayıcı](media/quickstart-setup-auto-enrollment/setup-automatic-enrollment-win10.png)
2. **Grupları seç** > **Contoso Testers** > **Seç**'i işaretleyin.
3. Aşağıdaki URL'ler için varsayılan değerleri kullanın:
    - MDM kullanım koşulları URL'si
    - MDM bulma URL'si
    - MDM uyumluluğu URL'si
4. **Kaydet**’i seçin.
5. Bir Windows 10 cihazında grupta bir kullanıcı olarak oturum açın ve yönergeleri izleyin.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Intune otomatik kaydını yeniden yapılandırmak için [Windows cihazları için kayıt ayarlama](windows-enroll.md)'ya bakın.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta Windows 10 cihazları için otomatik kaydı ayarlamayı öğrendiniz. Tüm platformlar genelinde cihaz kaydetmenin başka yolları hakkında bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Cihaz kaydı nedir? makalesi](device-enrollment.md)