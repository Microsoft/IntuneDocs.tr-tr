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
ms.openlocfilehash: c07ce82bbc056e1d76abeb5d31bf57e0973fad6e
ms.sourcegitcommit: bdf948be824cf5390d5166a277f389f3785c81f9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71960890"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Android kurumsal sistem uygulamalarını Microsoft Intune ekleyin

Bir cihaza veya bir kullanıcı grubuna uygulama atamadan önce, önce uygulamayı Microsoft Intune eklemeniz gerekir. Sistem uygulamaları, Android kurumsal cihazlarda desteklenir. [Android kurumsal adanmış cihazlar](../enrollment/android-kiosk-enroll.md) veya [tam olarak yönetilen cihazlar](../enrollment/android-fully-managed-enroll.md)için bir sistem uygulamasını etkinleştirebilirsiniz.

## <a name="add-the-app"></a>Uygulamayı ekleyin

Aşağıdakileri yaparak Azure portal Intune 'a bir Android kurumsal sistem uygulaması ekleyebilirsiniz:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Intune** bölmesinde, **istemci uygulamaları** > **uygulama** > **Ekle**' yi seçin.
3. **Uygulama Ekle** bölmesinde, kullanılabilir **diğer** türler altında **Android kurumsal sistem uygulaması**' nı seçin.
4. Uygulama bilgilerini yapılandırmak için **Yapılandır**' ı seçin ve ardından aşağıdaki bilgileri sağlayın:
    - **Uygulama adı**: uygulamanın adını girin.
    - **Yayımcı**: uygulamanın yayımcısının adını girin.  
    - **Paket adı**: bir paket adı girin. Intune, paket adının geçerli olduğunu doğrular.
5. **Tamam**’ı seçin.
6. **Add (Ekle)** seçeneğini belirleyin.

> [!NOTE]
> Etkinleştirmek/devre dışı bırakmak istediğiniz uygulamanın paket adını bulmak için cihazınızın OEM ile çalışmanız gerekir.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada seçtiğiniz gruplara atayabilirsiniz. 

Android kurumsal sistem uygulamaları, zaten platformun parçası olan uygulamaları etkinleştirir veya devre dışı bırakır. Bir uygulamayı etkinleştirmek için, sistem uygulamasını **gerektiği**şekilde atayın. Bir uygulamayı devre dışı bırakmak için, sistem uygulamasını **kaldırma**olarak atayın. Sistem uygulamaları, bir kullanıcı için kullanılabilir olarak atanamaz.


## <a name="next-steps"></a>Sonraki adımlar

- [Uygulamaları gruplara atama](apps-deploy.md)
