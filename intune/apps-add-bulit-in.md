---
title: "Intune kullanarak mobil cihazlara yerleşik uygulamalar yükleme"
titlesuffix: Azure portal
description: "Mobil cihazlarda yerleşik uygulamaları yüklemeyi kolaylaştırmak için Intune’u nasıl kullanabileceğinizi öğrenin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90bec6442084e46f499c57cf128e6ef57fe1ce9c
ms.sourcegitcommit: 0a5f424a8f683daa919b13b5c363173040d561c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Microsoft Intune’a yerleşik uygulama ekleme

**Yerleşik** uygulama türü, iOS ve Android cihazlara Office 365 uygulamaları gibi seçkin yönetilen uygulamaları atamanızı kolaylaştırır. Bu uygulama türüne belirli uygulamaları atayabilirsiniz; örneğin Excel, Power BI, SharePoint, Teams, OneDrive, Outlook, Skype ve diğerleri. Bir uygulamayı ekledikten sonra uygulama türünü **Yerleşik iOS uygulaması** veya **Yerleşik Android uygulaması** olarak görürsünüz. Yerleşik uygulama türünü kullanarak bu belirli uygulamalardan hangilerini cihaz kullanıcılarına yayımlayacağınızı seçebilirsiniz.

 Intune konsolunun önceki sürümlerinde Intune, Outlook ve OneDrive gibi varsayılan olarak yönetilen birkaç Office 365 uygulaması sağlar. Bu yönetilen uygulamalar için uygulama türü “Yönetilen iOS Mağaza Uygulaması” veya “Yönetilen Android Uygulaması” olarak etiketlenmiştir. “Yönetilen iOS Mağaza Uygulaması” veya “Yönetilen Android Uygulaması” yerine yerleşik uygulama türünü kullanmanızı öneririz çünkü yerleşik uygulama türü Office 365 uygulamalarını düzenleme ve silme konusunda daha fazla esneklik sağlar.

>[!NOTE]
>“Yönetilen iOS Mağaza Uygulaması” veya “Yönetilen Android Uygulaması” olarak etiketli varsayılan Office 365 uygulamaları, bu uygulamalar için tüm atamalar silindiğinde uygulama listesinden kaldırılacaktır.

## <a name="add-built-in-app"></a>Yerleşik Uygulama Ekleme

Aşağıdaki adımlar, Microsoft Intune’da mümkün olan uygulamalara yerleşik uygulama eklemenizi sağlar.
1.  Azure Portal’da oturum açın.
2.  **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçerek Microsoft Intune dikey penceresini görüntüleyin.
3.  **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4.  **Mobil uygulamalar** dikey penceresindeki **Yönet** grubundan **Uygulamalar**’ı seçin.
5.  **Ekle**’yi seçerek yeni bir uygulama ekleyin.
6.  **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinden **Yerleşik uygulama**’yı seçin.
7.  Dahil edeceğiniz yerleşik uygulamaları seçmek için **Uygulama seç**’e tıklayın.
8.  Yerleşik uygulama dikey penceresinden dahil etmek istediğiniz uygulamaları seçin.
9.  **Uygulama ekle** dikey penceresinde **Ekle**’ye tıklayarak uygulamaları dahil edin.


## <a name="configure-app-information"></a>Uygulama bilgilerini yapılandırma

Yerleşik uygulama hakkındaki bilgileri değiştirebilirsiniz. Bu bilgiler, uygulamayı Intune’da bulmanıza yardımcı olur ve kullanıcıların da uygulamayı Şirket Portalı’nda bulması kolaylaşır.
1.  **Mobil uygulamalar - Uygulamalar** dikey penceresinde değiştirmek istediğiniz yerleşik uygulamayı seçin. Yerleşik uygulamaya ait bir dikey pencere görüntülenecektir.
2.  **Yönet** grubundan **Özellikler** seçeneğine tıklayın.
3.  Yerleşik uygulama bilgilerini değiştirmek için **Yapılandır** seçeneğine tıklayın.
4.  **Uygulama bilgileri** dikey penceresinde aşağıdaki bilgileri değiştirebilirsiniz:
    -   **Ad** - Yerleşik uygulamanın Şirket Portalı’nda görüntülenen adını girin. Kullandığınız tüm adların benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    -   **Açıklama** - Uygulama için bir açıklama girin. 
    -   **Yayımcı** - Uygulamanın yayımcısının adını girin.
    -   **Kategori** - İsteğe bağlı olarak, yerleşik uygulama kategorilerinden birini seçin. Bu seçeneği ayarladığınızda, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    -   **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    -   **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    -   **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    -   **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    -   **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak İK departmanı gibi bir ad girin.
    -   **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    -   **Simge Yükle** - Kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenecek bir simge yükleyin.
3.  İşiniz bittiğinde **Uygulama bilgileri** dikey penceresinde **Tamam**’a tıklayın.
4.  **Özellikler** dikey penceresinde **Kaydet**’e tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara uygulamaları atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).
