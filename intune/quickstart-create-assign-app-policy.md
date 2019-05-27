---
title: Hızlı Başlangıç - Uygulama koruma ilkesi oluşturma ve atama
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta bir uygulama koruma ilkesi oluşturmak ve atamak için Microsoft Intune’u kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bad416e738f1a0481c67480d9a83157a4781c71b
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050330"
---
# <a name="quickstart-create-and-assign-an-app-protection-policy"></a>Hızlı Başlangıç: Uygulama koruma ilkesini oluşturma ve atama

Bu hızlı başlangıçta son kullanıcı cihazı üzerinde bir uygulama koruma ilkesi oluşturmak ve bunu bir istemci uygulamasına atamak için Intune’u kullanacaksınız. Intune, uygulamalarınızın kuruluşunuzdaki veri koruma gereksinimlerini karşıladığını onaylamak için uygulama koruma ilkeleri kullanır.

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](quickstart-create-user.md), [bir grup oluşturmanız](quickstart-create-group.md), [bir cihaz kaydetmeniz](quickstart-setup-auto-enrollment.md) ve [bir uygulama ekleyip atamanız](quickstart-add-assign-app.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal)’da [Genel Yönetici veya Intune Hizmet yöneticisi](users-add.md#types-of-administrators) olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="create-an-app-protection-policy"></a>Uygulama koruma ilkesi oluşturma

Bir uygulama koruma ilkesi oluşturmak için aşağıdaki adımları kullanın:

1. [Intune](https://aka.ms/intuneportal)’da **İstemci uygulamaları** > **Uygulama koruma ilkeleri** > **İlke Oluştur**’u seçin. 
2. Aşağıdaki ayrıntıları girin: 

    - **Ad**: *Windows 10 içerik koruma*
    - **Açıklama**: *Bu ilkeyle ilişkilendirilen kullanıcıların kesme, kopyalama veya cihaza atanan uygulama ve diğer yönetilmeyen uygulamalar arasında herhangi bir içeriği yapıştırın mümkün olmayacaktır.*
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

1.  [Intune](https://aka.ms/intuneportal)’da **Intune** > **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. 
2.  Daha önce oluşturduğunuz uygulama koruma ilkesini seçin. Bu hızlı başlangıçta ilke, **Windows 10 içerik koruma** ilkesidir.
3.  **Atamalar**’ı seçin.
4.  **Ekle** sekmesinde **Dahil edilecek gruplar**’ı seçin.
5.  Eklenecek grup olarak **Contoso Sınama Aracı**’nı seçin.
6.  Tıklayın **seçin** > **Kaydet**. 

Uygulama koruma ilkesini şimdi atadınız.

> [!NOTE]
> Uygulama koruma ilkeleri cihaz içeren gruplara değil, yalnızca kullanıcı içeren gruplara uygulanabilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta bir uygulama koruma ilkesi oluşturdunuz ve atadınız. Bu ilkenin atandığı kullanıcılar, atanan uygulama ve cihazdaki diğer yönetilmeyen uygulamalar arasında kesme, kopyalama ve yapıştırma eylemleri gerçekleştiremez. Bu tür bir koruma, kuruluşunuzun verilerini korumaya yardımcı olur. Intune’da uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Oluşturun ve özel bir rol atayın](quickstart-create-custom-role.md)
