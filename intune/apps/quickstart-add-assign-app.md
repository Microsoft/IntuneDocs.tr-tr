---
title: Hızlı Başlangıç - İstemci uygulaması ekleme ve atama
titleSuffix: Microsoft Intune
description: Bu hızlı başlangıçta bir istemci uygulaması eklemek ve atamak için Microsoft Intune’u kullanacaksınız.
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
ms.assetid: dab6f5c8-1ebb-42c4-a7a7-7af001f94e15
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40337b3c45885dacf486173814044a27b7f3f6cc
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755077"
---
# <a name="quickstart-add-and-assign-a-client-app"></a>Hızlı Başlangıç: İstemci uygulaması ekleme ve atama

Bu hızlı başlangıçta şirketinizin iş gücüne bir istemci uygulaması eklemek ve bunu atamak için Intune’u kullanacaksınız. Yöneticinin önceliklerinden biri, son kullanıcıların işlerini yapabilmeleri için gereken uygulamalara erişimleri olduğundan emin olmaktır. 

Bir Intune aboneliğiniz yoksa [ücretsiz bir deneme hesabı için kaydolun](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Prerequisites

- Bu hızlı başlangıcı tamamlamak için [bir kullanıcı oluşturmanız](../fundamentals/quickstart-create-user.md), [bir grup oluşturmanız](../fundamentals/quickstart-create-group.md) ve [bir cihaz kaydetmeniz](../quickstart-setup-auto-enrollment.md) gerekir.

## <a name="sign-in-to-intune"></a>Intune'da oturum açma

[Intune](https://aka.ms/intuneportal) 'da [genel yönetici veya Intune Hizmet Yöneticisi](../fundamentals/users-add.md#types-of-administrators)olarak oturum açın. Intune Deneme aboneliği oluşturduysanız aboneliği oluşturduğunuz hesap Genel yönetici rolüne sahip olur.

## <a name="add-the-client-app-to-intune"></a>İstemci uygulamasını Intune’a ekleme

Intune’un uygulama görünüşünü yönetebilmesi amacıyla herhangi bir uygulama Intune’a dahil edilebilir. 

Intune’a bir uygulama eklemek için aşağıdaki adımları kullanın:
1. [Intune](https://aka.ms/intuneportal)'Da, **uygulamalar** > **tüm uygulamalar** > **Ekle**' yi seçin. 
2. **Uygulama türü seç** bölmesinin **Office 365 Suite** bölümünde **Windows 10** ' u seçin.
3. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.
4. **Uygulama paketi bilgileri** sayfasında varsayılan ayrıntıları onaylayın.
5. **İleri** ' ye tıklayarak **uygulama paketini Yapılandır** sayfasını görüntüleyin.
6. **Güncelleştirme kanalı** ' nın yanındaki açılan kutudan **aylık** ' i seçin.
7. ***Uygulama paketi yapılandırma** sayfasında kalan varsayılan ayrıntıları onaylayın.
8. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.
9. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. Daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](~/fundamentals/scope-tags.md).
10. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.
11. Uygulama için Grup atamalarını seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md). 
12. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
13. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

## <a name="assign-the-app-to-a-group"></a>Uygulamayı bir gruba atama

Microsoft Intune’a bir uygulama ekledikten sonra uygulamayı kullanıcı veya cihaz gruplarına atayabilirsiniz.

> [!NOTE]
> Bu hızlı başlangıç, bu serideki önceki hızlı başlangıçlarda oluşturulur. Ayrıntılar için lütfen bu hızlı başlangıçtaki [önkoşullar](quickstart-add-assign-app.md#prerequisites) kısmına bakın.

Uygulamaları gruplara eklemek için aşağıdaki adımları kullanın:
1. [Intune](https://aka.ms/intuneportal)'da **tüm uygulamalar** > **uygulamalar** ' ı seçin. 
2. Bir gruba atamak istediğiniz uygulamayı seçin.
3. **Grup Ekle bölmesini göstermek** için **atamalar** > **Grup Ekle** ' ye tıklayın.
4. Açılan **Atama türü** kutusunda **Kayıtlı cihazlar için kullanılabilir**’i seçin. 
5. **Dahil Edilen Gruplar** > **Dahil edilecek grupları seçin** > **Contoso Sınama Aracı**’nı seçin.
6. Grubu atamak için **Seçin** > **Tamam** > **Tamam** > **Kaydet**’e tıklayın.

Böylece uygulamayı **Contoso Sınama Aracı**’na atadınız.

## <a name="install-the-app-on-the-enrolled-device"></a>Kayıtlı cihazda uygulamayı yükleme

Intune yoluyla kullanılabilir olan **Contoso’nun To-Do** uygulamasını yüklemek için Şirket Portalı uygulamasını yükleyip kullanmanız gerekir. Uygulamanın kayıtlı cihazdaki kullanıcı için kullanılabilir olduğunu doğrulamak amacıyla aşağıdaki adımları kullanın.

1. Kayıtlı Windows 10 Masaüstü cihazınızda oturum açın.

    > [!IMPORTANT]
    > Cihazın [Intune’a kayıtlı](../quickstart-enroll-windows-device.md) olması gerekir. Ayrıca uygulamaya atadığınız gruba dahil olan bir hesapla cihazda oturum açmanız gerekir.

2. **Başlat** menüsünden **Microsoft Store**’u açın. Daha sonra **Şirket Portalı** uygulamasını bulun ve yükleyin.
3. **Şirket Portalı** uygulamasını başlatın.
4. Intune’u kullanarak eklediğiniz uygulamaya tıklayın. Bu hızlı başlangıçta **Microsoft Office 365 uygulama paketi** uygulamasını eklediniz.

    > [!NOTE]
    > Intune kullanıcısına hiçbir uygulama atayamadıysanız şu iletiyi görürsünüz: *BT yöneticiniz hiçbir uygulamayı sizin kullanımınıza sunmadı.*

5. **Yükle**’ye tıklayın.

İş gereksinimleriniz Şirket Portalı uygulamasını iş gücünüze atamanızı gerektiriyorsa Windows 10 Şirket Portalı uygulamasını doğrudan Intune’dan el ile atayabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](../company-portal-app.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıçta Intune’a bazı uygulamalar eklediniz, daha sonra bu uygulamaları bir gruba atadınız ve kayıtlı Windows 10 Masaüstü cihazına yüklediniz. Intune’da uygulamaları yönetme hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama yönetimi nedir?](app-management.md)

Bu Intune hızlı başlangıç serisini takip etmek için bir sonraki hızlı başlangıca ilerleyin.

> [!div class="nextstepaction"]
> [Hızlı Başlangıç: Uygulama koruma ilkesi oluşturma ve atama](quickstart-create-assign-app-policy.md)
