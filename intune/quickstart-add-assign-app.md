---
title: Hızlı Başlangıç - İstemci uygulaması ekleme ve atama
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta bir istemci uygulaması eklemek ve atamak için Microsoft Intune’u kullanacaksınız.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/25/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dab6f5c8-1ebb-42c4-a7a7-7af001f94e15
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 024c4eb37d1b9991db6d1ca0b5c528e9dd333422
ms.sourcegitcommit: b0cf661145ccc6e3518db620af199786a623a0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64764798"
---
# <a name="quickstart-add-and-assign-a-client-app"></a>Hızlı Başlangıç: Ekleme ve bir istemci uygulama atama

Bu hızlı başlangıçta şirketinizin iş gücüne bir istemci uygulaması eklemek ve bunu atamak için Intune’u kullanacaksınız. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. 

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](free-trial-sign-up.md).

## <a name="prerequisites"></a>Önkoşullar

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](quickstart-create-user.md), [bir grup oluşturmanız](quickstart-create-group.md) ve [bir cihaz kaydetmeniz](quickstart-setup-auto-enrollment.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

Oturum [Intune](https://aka.ms/intuneportal) olarak bir [genel yönetici veya Intune Hizmet Yöneticisi](users-add.md#types-of-administrators). Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="add-the-client-app-to-intune"></a>İstemci uygulamasını Intune’a ekleme

Intune’un uygulama görünüşünü yönetebilmesi amacıyla herhangi bir uygulama Intune’a dahil edilebilir. 

Intune’a bir uygulama eklemek için aşağıdaki adımları kullanın:

1. [Intune](https://aka.ms/intuneportal)’da **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçin. 
2. Açılan **Uygulama türü** kutusundaki **Office 365 Paketi** bölümünde **Windows 10**’u seçin.
3. Office uygulamalarının Intune kullanıcısına atanması için **Uygulama Paketini yapılandır**’ı seçin.
4. Varsayılan olarak seçili uygulamaları kabul etmek için **Tamam**’a tıklayın.
5. **Uygulama Paketi bilgileri**’ni seçin.
6. **Paket Adı** olarak **Microsoft Office 365 uygulama paketi** yazın.
7. Girin **Microsoft Office 365 uygulama paketini** olarak **Paket açıklaması**.
8. **Şirket Portalı’nda bu uygulamayı öne çıkan uygulama olarak görüntüle** ayarını **Evet** olarak belirleyin.
9. **Tamam**'ı tıklatın.

    ![Uygulama bilgileri ekleme ekran görüntüsü](media/quickstart-add-assign-app/quickstart-add-assign-app-01.png)

8. **Uygulama Paketi Ayarları**’nı seçin.
9. Açılan **Güncelleştirme Kanalı** kutusunda **Aylık** seçeneğini belirleyin.
10. **Tamam** > **Ekle**’ye tıklayın.

## <a name="assign-the-app-to-a-group"></a>Uygulamayı bir gruba atama

Microsoft Intune’a bir uygulama ekledikten sonra uygulamayı kullanıcı veya cihaz gruplarına atayabilirsiniz.

> [!NOTE]
> Bu hızlı başlangıçta, önceki hızlı başlangıçlar, bu serinin üzerine inşa edilmiştir. Ayrıntılar için lütfen bu hızlı başlangıçtaki [önkoşullar](quickstart-add-assign-app.md#prerequisites) kısmına bakın.

Uygulamaları gruplara eklemek için aşağıdaki adımları kullanın:
1. [Intune](https://aka.ms/intuneportal)’da **İstemci uygulamaları** > **Uygulamalar**’ı seçin. 
2. Bir gruba atamak istediğiniz uygulamayı seçin.   
3. **Atamalar** > **Grup ekle**’yi seçerek **Grup ekle** dikey penceresini görüntüleyin.
4. Açılan **Atama türü** kutusunda **Kayıtlı cihazlar için kullanılabilir**’i seçin. 
5. **Dahil Edilen Gruplar** > **Dahil edilecek grupları seçin** > **Contoso Sınama Aracı**’nı seçin.
6. Grubu atamak için **Seçin** > **Tamam** > **Tamam** > **Kaydet**’e tıklayın.

Böylece uygulamayı **Contoso Sınama Aracı**’na atadınız.

## <a name="install-the-app-on-the-enrolled-device"></a>Kayıtlı cihazda uygulamayı yükleme

Intune yoluyla kullanılabilir olan **Contoso’nun To-Do** uygulamasını yüklemek için Şirket Portalı uygulamasını yükleyip kullanmanız gerekir. Uygulamanın kayıtlı cihazdaki kullanıcı için kullanılabilir olduğunu doğrulamak amacıyla aşağıdaki adımları kullanın.

1. Kayıtlı Windows 10 Masaüstü cihazınızda oturum açın.

    > [!IMPORTANT]
    > Cihazın [Intune’a kayıtlı](quickstart-enroll-windows-device.md) olması gerekir. Ayrıca uygulamaya atadığınız gruba dahil olan bir hesapla cihazda oturum açmanız gerekir.

2. **Başlat** menüsünden **Microsoft Store**’u açın. Daha sonra **Şirket Portalı** uygulamasını bulun ve yükleyin.
3. **Şirket Portalı** uygulamasını başlatın.
4. Intune’u kullanarak eklediğiniz uygulamaya tıklayın. Bu hızlı başlangıçta **Microsoft Office 365 uygulama paketi** uygulamasını eklediniz.

    > [!NOTE]
    > Başarılı bir şekilde herhangi bir uygulama için Intune kullanıcı atamadığınız, şu iletiyi görürsünüz: *BT yöneticiniz tüm uygulamaları kullanılabilir hale değil.*

5. **Yükle**'ye tıklatın.

İş gereksinimleriniz Şirket Portalı uygulamasını iş gücünüze atamanızı gerektiriyorsa Windows 10 Şirket Portalı uygulamasını doğrudan Intune’dan el ile atayabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](store-apps-company-portal-app.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta Intune’a bazı uygulamalar eklediniz, daha sonra bu uygulamaları bir gruba atadınız ve kayıtlı Windows 10 Masaüstü cihazına yüklediniz. Intune’da uygulamaları yönetme hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama yönetimi nedir?](app-management.md)

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Bir uygulama koruma ilkesi oluşturma ve atama](quickstart-create-assign-app-policy.md)
