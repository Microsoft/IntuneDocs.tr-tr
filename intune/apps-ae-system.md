---
title: Android kurumsal sistem uygulamalarını Microsoft Intune ekleyin
titleSuffix: ''
description: Microsoft Intune 'ye kurumsal sistem uygulamaları eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6cf1694c22e748fd10bb016607b7ff38963e80b5
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71304163"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Android kurumsal sistem uygulamalarını Microsoft Intune ekleyin

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihaza veya kullanıcı grubuna uygulama atamadan önce uygulamayı ilk olarak Microsoft Intune’a eklemeniz gerekir. Sistem uygulamaları, Android kurumsal cihazlarda desteklenir. [Android kurumsal adanmış cihazlar](android-kiosk-enroll.md) veya [tam olarak yönetilen cihazlar](android-fully-managed-enroll.md)için bir sistem uygulamasını etkinleştirebilirsiniz. 

## <a name="add-the-app"></a>Uygulama ekleme

Aşağıdakileri yaparak Azure portal Intune 'a bir Android kurumsal sistem uygulaması ekleyebilirsiniz:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde **İstemci uygulamaları** > **Uygulamalar** > **Ekle**'yi seçin.
3. **Uygulama Ekle** bölmesinde, kullanılabilir **diğer** türler altında **Android kurumsal sistem uygulaması**' nı seçin.
4. Uygulama bilgilerini yapılandırmak için **Yapılandır**' ı seçin ve ardından aşağıdaki bilgileri sağlayın:
    - **Uygulama adı**: Uygulamanın adını girin.
    - **Yayımcı**: Uygulama yayımcısının adını girin.  
    - **Paket adı**: Bir paket adı girin. Intune, paket adının geçerli olduğunu doğrular.
5. **Tamam**’ı seçin.
6. **Add (Ekle)** seçeneğini belirleyin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

Android kurumsal sistem uygulamaları, zaten platformun parçası olan uygulamaları etkinleştirir veya devre dışı bırakır. Bir uygulamayı etkinleştirmek için, sistem uygulamasını **gerektiği**şekilde atayın. Bir uygulamayı devre dışı bırakmak için, sistem uygulamasını **kaldırma**olarak atayın. Sistem uygulamaları, bir kullanıcı için kullanılabilir olarak atanamaz.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md)
