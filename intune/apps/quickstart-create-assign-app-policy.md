---
title: Hızlı Başlangıç - Uygulama koruma ilkesi oluşturma ve atama
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta bir uygulama koruma ilkesi oluşturmak ve atamak için Microsoft Intune’u kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1800fa91ed5650fd57a31d24fdb3767a60dc5816
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563788"
---
# <a name="quickstart-create-and-assign-an-app-protection-policy"></a>Hızlı Başlangıç: Uygulama koruma ilkesi oluşturma ve atama

Bu hızlı başlangıçta son kullanıcı cihazı üzerinde bir uygulama koruma ilkesi oluşturmak ve bunu bir istemci uygulamasına atamak için Intune’u kullanacaksınız. Intune, uygulamalarınızın kuruluşunuzdaki veri koruma gereksinimlerini karşıladığını onaylamak için uygulama koruma ilkeleri kullanır.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](../fundamentals/quickstart-create-user.md), [bir grup oluşturmanız](../fundamentals/quickstart-create-group.md), [bir cihaz kaydetmeniz](../quickstart-setup-auto-enrollment.md) ve [bir uygulama ekleyip atamanız](../quickstart-add-assign-app.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)’da [Genel Yönetici veya Intune Hizmet yöneticisi](../fundamentals/users-add.md#types-of-administrators) olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma

Uygulama koruma ilkesi oluşturmak için aşağıdaki adımları kullanın:

1. [Intune](https://aka.ms/intuneportal)'Da, **Ilke oluştur** > **Uygulama koruma ilkeleri** > **uygulamalar** ' ı seçin. 
2. Aşağıdaki ayrıntıları girin: 

    - **Ad**: *Windows 10 içerik koruma*
    - **Açıklama**: *Bu ilkeyle ilişkilendirilen kullanıcılar, atanan uygulama ve cihazdaki diğer yönetilmeyen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemleri gerçekleştiremez.*
    - **Platform**: *Windows 10*
    - **Kayıt durumu**: *Kayıt ile*

3. Bu ilkeye uyması gereken uygulamaları seçmek için **Korunan uygulamalar**’ı seçin.
4. **Uygulama ekle**’ye tıklayın.
5. **Önerilen uygulamalar** altında **Word Mobile**’ı seçin.
5. **Tamam** > **Tamam**’a tıklayın. 
6. Uygulamayı yapılandırmak için **Gerekli ayarlar**’ı seçin.
7. Windows Bilgi Koruması modunu ayarlamak için **Geçersiz Kılmalara İzin Ver**’e tıklayın. Bu seçeneğin belirtilmesi, kurumsal verilerin korunan uygulamadan dışarı çıkmasını engeller.
8. **Tamam** > **Oluştur**’a tıklayın.

Artık uygulama koruma ilkesini Intune’a görebilirsiniz.

### <a name="assign-the-app-protection-policy"></a>Uygulama koruma ilkesini atama

Intune’a bir uygulama koruma ilkesi oluşturduktan sonra bunu gruplara atayabilirsiniz. 

Uygulama koruma ilkesini atamak için aşağıdaki adımları izleyin:

1. [Intune](https://aka.ms/intuneportal)'Da, **uygulama koruma ilkeleri** > **Intune** > **uygulamalar** ' ı seçin. 
2. Daha önce oluşturduğunuz uygulama koruma ilkesini seçin. Bu hızlı başlangıçta ilke, **Windows 10 içerik koruma** ilkesidir.
3. **Atamalar**’ı seçin.
4. **Ekle** sekmesinde **Dahil edilecek gruplar**’ı seçin.
5. Eklenecek grup olarak **Contoso Sınama Aracı**’nı seçin.
6. **Kaydet** > **Seç** ' e tıklayın. 

Uygulama koruma ilkesini şimdi atadınız.

> [!NOTE]
> Uygulama koruma ilkeleri cihaz içeren gruplara değil, yalnızca kullanıcı içeren gruplara uygulanabilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir uygulama koruma ilkesi oluşturdunuz ve atadınız. Bu ilkenin atandığı kullanıcılar, atanan uygulama ve cihazdaki diğer yönetilmeyen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemleri gerçekleştiremez. Bu tür bir koruma, kuruluşunuzun verilerini korumaya yardımcı olur. Intune’da uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Özel rol oluşturma ve atama](../fundamentals/create-custom-role.md)
