---
title: Android kurumsal sistem uygulamalarını Microsoft Intune ekleyin
titleSuffix: ''
description: Microsoft Intune 'ye kurumsal sistem uygulamaları eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 613369070d847265f371a7b228a2b6d81bf813fe
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755264"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Android kurumsal sistem uygulamalarını Microsoft Intune ekleyin

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. Sistem uygulamaları, Android kurumsal cihazlarda desteklenir. [Android kurumsal adanmış cihazlar](../enrollment/android-kiosk-enroll.md) veya [tam olarak yönetilen cihazlar](../enrollment/android-fully-managed-enroll.md)için bir sistem uygulamasını etkinleştirebilirsiniz.

## <a name="add-the-app"></a>Uygulama ekleme

Aşağıdakileri yaparak Azure portal Intune 'a bir Android kurumsal sistem uygulaması ekleyebilirsiniz:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, kullanılabilir **diğer** türler altında **Android kurumsal sistem uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.
**Uygulama bilgileri** sayfasında, uygulama ayrıntılarını ekleyin:
    - **Uygulama adı**: uygulamanın adını girin.
    - **Yayımcı**: Uygulama yayımcısının adını girin.  
    - **Paket adı**: bir paket adı girin. Intune, paket adının geçerli olduğunu doğrular.
5. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.
8. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. Daha fazla bilgi için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma](~/fundamentals/scope-tags.md).
9. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.
10. Uygulama için Grup atamalarını seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md). 
11. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
12. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

Oluşturduğunuz uygulamanın **genel bakış** dikey penceresi görüntülenir.

> [!NOTE]
> Etkinleştirmek/devre dışı bırakmak istediğiniz uygulamanın paket adını bulmak için cihazınızın OEM ile çalışmanız gerekir.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

Android kurumsal sistem uygulamaları, zaten platformun parçası olan uygulamaları etkinleştirir veya devre dışı bırakır. Bir uygulamayı etkinleştirmek için, sistem uygulamasını **gerektiği**şekilde atayın. Bir uygulamayı devre dışı bırakmak için, sistem uygulamasını **kaldırma**olarak atayın. Sistem uygulamaları, bir kullanıcı için kullanılabilir olarak atanamaz.


## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
