---
title: Microsoft Intune - Azure ile Windows 10 cihazlarında geçiş kodunu sıfırlama | Microsoft Docs
description: Windows cihazlarında geçiş kodunu sıfırlamak için, Microsoft Pin Sıfırlama Hizmeti ve Microsoft Pin Sıfırlama İstemcisi'ni yükleyin, Azure Active Directory Dizin Kimliğinizi kullanarak bir cihaz ilkesi oluşturun ve ardından Azure portalında Microsoft Intune'u kullanarak geçiş kodunu sıfırlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b2390462376c88129435de30eb98020563f3878
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713094"
---
# <a name="reset-the-passcode-on-windows-devices-using-intune"></a>Intune kullanarak Windows cihazlarında geçiş kodunu sıfırlama

Windows cihazlarında geçiş kodunu sıfırlayabilirsiniz. Geçiş kodunu sıfırlama özelliği, Microsoft Pin Sıfırlama Hizmeti'ni kullanarak Windows 10 Mobile çalıştıran cihazlarda yeni bir geçiş kodu oluşturur. 

## <a name="supported-platforms"></a>Desteklenen platformlar

- Creators Update ve üzerini çalıştıran Windows 10 Mobile (Azure AD’ye katılmış).

Şu platformlar **desteklenmez**:
- Windows
- iOS
- Mac OS
- Android

## <a name="authorize-the-pin-reset-services"></a>PIN sıfırlama hizmetlerini yetkilendirme

Windows cihazlarında geçiş kodunu sıfırlamak için, PIN sıfırlama hizmetini Intune kiracınıza ekleyin.

1. [Microsoft PIN Sıfırlama Hizmeti üretimine](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) gidin ve kiracı yönetici hesabını kullanarak oturum açın.
2. PIN sıfırlama hizmetinin hesabınıza erişimini onaylamayı **kabul edin**: ![PIN Sıfırlama Sunucusu izin isteğini kabul edin](./media/device-windows-pin-reset/pin-reset-service-home-screen.png)
3. [Microsoft PIN Sıfırlama İstemcisi üretimine](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) gidin ve kiracı yönetici hesabını kullanarak oturum açın. PIN sıfırlama istemcisinin hesabınıza erişimini onaylamayı **kabul edin**.
4. [Azure portalında](https://portal.azure.com), PIN sıfırlama hizmetlerinin Kurumsal uygulamalar (Tüm uygulamalar) içinde listelendiğini onaylayın: ![PIN sıfırlama hizmeti izinler sayfası](./media/device-windows-pin-reset/pin-reset-service-application.png)

> [!NOTE]
> PIN sıfırlama isteklerini kabul ettikten sonra, `Page not found` iletisini alabilirsiniz veya hiçbir şey olmuyor gibi görünebilir. Bu, normal bir davranıştır. İki PIN Sıfırlama uygulamasının kiracınızda listelendiğini onaylamayı unutmayın.

## <a name="configure-windows-devices-to-use-pin-reset"></a>Windows cihazları, PIN sıfırlama kullanmak üzere yapılandırma

Yönettiğiniz Windows cihazlarında PIN sıfırlamayı yapılandırmak için bir [Intune Windows 10 özel cihaz ilkesi](../configuration/custom-settings-windows-10.md) kullanın. İlkeyi, aşağıdaki Windows ilke yapılandırma hizmet sağlayıcısını (CSP) kullanarak yapılandırın:

**Cihaz ilkesi kullanma** - `./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery`

*Kiracı kimliğini*, [Azure portalında](https://portal.azure.com) Azure Active Directory'nin **Özellikler**'i arasında listelenen Azure AD Dizin Kimliğinizle değiştirin.

Bu CSP için değeri **True** olarak ayarlayın.

> [!TIP]
> İlkeyi oluşturduktan sonra, bunu bir gruba atarsınız (veya dağıtırsınız). İlke, kullanıcı gruplarına veya cihaz gruplarına atanabilir. Kullanıcı grubuna atarsanız, grup iOS gibi başka cihazları olan kullanıcıları içerebilir. Teknik olarak, ilke uygulanmaz ama bu cihazlar yine de durum ayrıntılarına eklenir.

## <a name="reset-the-passcode"></a>Geçiş kodunu sıfırlama

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın. 
2. **Cihazlar**’ı ve ardından **Tüm Cihazlar**’ı seçin.
3. Geçiş kodunu sıfırlamak istediğiniz cihazı seçin. Cihaz özelliklerinde **Yeni geçiş kodu**'nu seçin.
4. Onaylamak için **Evet** ' i seçin. Böylece geçiş kodu oluşturulur ve gelecek yedi gün boyunca portalda görüntülenir.

## <a name="next-step"></a>Sonraki adım

Geçiş kodu sıfırlama başarısız olursa, portalda diğer ayrıntılara ulaşabilmeniz için bir bağlantı sağlanır.
