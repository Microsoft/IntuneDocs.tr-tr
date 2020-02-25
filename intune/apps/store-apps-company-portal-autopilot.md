---
title: Autopilot tarafından sağlanan cihazlar için Windows 10 Şirket Portalı uygulaması ekleme ve atama
titleSuffix: Microsoft Intune
description: Autopilot tarafından sağlanan cihazlar için Windows 10 Şirket Portalı uygulamasını ekleyin ve Intune 'a atayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c13d8d774037f0d2db5832af7f39c864330fef30
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77579770"
---
# <a name="add-and-assign-the-windows-10-company-portal-app-for-autopilot-provisioned-devices"></a>Autopilot tarafından sağlanan cihazlar için Windows 10 Şirket Portalı uygulaması ekleme ve atama

Cihazları yönetmek ve uygulamaları yüklemek için kullanıcılarınız Şirket Portalı uygulamasını kullanabilir. Windows 10 Şirket Portalı uygulamasını doğrudan Intune 'dan atayabilirsiniz. 

## <a name="prerequisites"></a>Önkoşullar

Windows 10 Autopilot tarafından sağlanan cihazlarda, Microsoft Store for Business hesabınızı Intune ile ilişkilendirmeniz önerilir. Daha fazla bilgi için bkz. [Microsoft Intune Ile iş için Microsoft Store toplu satın alınan uygulamaları yönetme](~/apps/windows-store-for-business.md).

Şirket Portalı (çevrimdışı) aşağıdaki adımları kullanarak yüklenmek üzere seçilmiştir. Şirket Portalı uygulaması, Autopilot grubuna atandığında ve Kullanıcı oturum açmadan önce cihaza yüklendiğinde cihaz bağlamına yüklenir. 

## <a name="configure-settings-to-show-offline-apps"></a>Çevrimdışı uygulamaları göstermek için ayarları yapılandırma
1. [İş için Microsoft Store](https://www.microsoft.com/business-store)’da yönetici hesabınızla oturum açın.
2. Pencerenin üst kısmında **Yönet** sekmesini seçin.
3. Sol bölmede **Ayarlar**’ı seçin.
4. **Alışveriş deneyimi** altında **Çevrimdışı uygulamaları göster** seçeneğini **Açık** olarak ayarlayın.  
    Çevrimdışı lisanslı uygulamalar görüntülenir.

## <a name="get-the-offline-company-portal-app"></a>Çevrimdışı Şirket Portalı uygulamasını al
1. **Şirket Portalı** uygulamasını arayın ve seçin.
2. **Lisans türü** olarak **Çevrimdışı** ayarlayın.
3. Çevrimdışı Şirket Portalı uygulamasını almak ve envanterinize eklemek için **Uygulamayı al**’ı seçin.

## <a name="assign-the-company-portal-app"></a>Şirket Portalı uygulamasını atama
1.  [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) 'nde Yönetici hesabınızla oturum açın. 
2. Sağ bölmedeki **uygulamalar** sekmesini seçin. 
3.  **Platform tarafından**altında **Windows**' u seçin. 
4.  **Şirket portalı (çevrimdışı)** seçeneğini belirleyin.   
5. Eşitleme zamanlamasının tamamlanmasını beklemeniz ya da Microsoft Endpoint Manager yönetim merkezinden el ile eşitleme yapmanız gerekir.
6. Şirket Portalı uygulamasını seçtiğiniz Autopilot cihaz gruplarına gerekli bir uygulama olarak atayın.

## <a name="next-steps"></a>Sonraki adımlar

- Uygulama atama hakkında daha fazla bilgi için bkz. [uygulamaları gruplara atama](apps-deploy.md).

