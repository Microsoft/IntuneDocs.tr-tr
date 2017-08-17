---
title: "Intune ile Windows cihazlarda geçiş kodunu sıfırlama"
titleSuffix: Intune on Azure
description: "Microsoft PIN Sıfırlama Hizmeti ile tümleştirilmiş Windows cihazlarda Intune’u kullanarak geçiş kodunu nasıl sıfırlayacağınızı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9cf2549852c5949ff1c95af12b40f59136d56e34
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Microsoft PIN Sıfırlama Hizmeti ile tümleştirilmiş Windows cihazlarda Intune’u kullanarak geçiş kodunu sıfırlama

Windows cihazlar için geçiş kodu sıfırlama yeteneği, Microsoft PIN Sıfırlama Hizmeti ile tümleşik çalışarak Windows 10 Mobile çalıştıran cihazlarda yeni bir geçiş kodu oluşturmanıza olanak verir. Cihazların Windows 10 Creators Update veya üzerini çalıştırıyor olması gerekir.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Windows 10 Creators Update ve üzerinde desteklenir (Azure AD’ye katılmış)
- Windows Phone - Desteklenmiyor
- iOS - Desteklenmiyor
- macOS - Desteklenmiyor
- Android - Desteklenmiyor


## <a name="before-you-start"></a>Başlamadan önce

Yönettiğiniz Windows cihazlarda geçiş kodunu uzaktan sıfırlayabilmeniz için önce PIN sıfırlama hizmetinizi Intune kiracınıza eklemeli ve yönettiğiniz cihazları yapılandırmalısınız. Bunu ayarlamak için aşağıdaki yönergeleri izleyin:

### <a name="connect-intune-with-the-pin-reset-service"></a>Intune ile PIN sıfırlama hizmetini bağlama

1. [Microsoft PIN Sıfırlama Hizmeti Tümleştirmesi web sitesini](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) ziyaret edin ve Intune kiracınızı yönetmek için kullandığınız kiracı yönetici hesabınızla oturum açın.
2. Oturum açtıktan sonra **Kabul Et**’e tıklayarak PIN sıfırlama hizmetinin hesabınıza erişmesine izin verin.<br>
![PIN sıfırlama hizmeti izinleri sayfası](./media/pin-reset-service-application.png)
3. Aşağıdaki ekran görüntüsünde gösterilen Azure portalı Kurumsal uygulamalar - Tüm uygulamalar dikey penceresinden Intune ve PIN sıfırlama hizmetinin tümleşik olduğunu doğrulayabilirsiniz:<br>
![Azure’da PIN sıfırlama hizmeti uygulaması](./media/pin-reset-service-home-screen.png)
4. Kiracı yönetici kimlik bilgilerinizi kullanarak [bu web sitesinde](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) oturum açın ve tekrar **Kabul Et**’e tıklayarak hizmetin hesabınıza erişmesine izin verin.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Windows cihazları, PIN sıfırlama kullanmak üzere yapılandırma

Yönettiğiniz Windows cihazlarda PIN sıfırlamayı yapılandırmak için bir [Intune Windows 10 özel cihaz ilkesi](custom-settings-windows-10.md) kullanarak bu özelliği etkinleştirin. İlkeyi, aşağıdaki Windows ilke yapılandırma hizmet sağlayıcısını (CSP) kullanarak yapılandırın:


- **Cihazlar için** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**

*Kiracı kimliği* Azure Active Directory’nin **Özellikler** sayfasından elde edebileceğiniz Azure Active Directory, Dizin Kimliği’ne başvurur.

Bu CSP için değeri **True** olarak ayarlayın.

## <a name="steps-to-reset-the-passcode"></a>Geçiş kodunu sıfırlama adımları

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinde **Yönet** > **Tüm cihazlar**'ı seçin.
5. Geçiş kodunu sıfırlamak istediğiniz cihazı seçin ve daha sonra cihaz özellikleri dikey penceresinde **Yeni geçiş kodu**’nu seçin.
6. Görüntülenen onay ekranında **Evet**’i seçin. Böylece geçiş kodu oluşturulur ve gelecek yedi gün boyunca portalda görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

Geçiş kodu sıfırlama başarısız olursa daha fazla bilgi almanız için portalda size bir link verilir.


