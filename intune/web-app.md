---
title: Microsoft Intune’a web uygulamaları ekleme
titleSuffix: ''
description: Microsoft Intune'a web uygulamaları ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d62341e35bf851bb429b15a582183bec62a9d4a
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="add-web-apps-to-microsoft-intune"></a>Microsoft Intune’a web uygulamaları ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, web uygulamaları da dahil olmak üzere çeşitli uygulama türlerini destekler. Web uygulaması, bir istemci-sunucu uygulamasıdır. Sunucu; kullanıcı arabirimi, içerik ve işlevleri içeren web uygulamasını sağlar. Ayrıca modern web barındırma platformları çoğu zaman güvenlik, yük dengeleme ve diğer yararlar da sunar. Web uygulaması web’de ayrı olarak korunur. Bu uygulama türüne işaret etmek için Microsoft Intune kullanırsınız. Bu uygulamaya erişebilecek kullanıcı gruplarını da atarsınız. 

Kullanıcılarınız için uygulamaları yönetebilmek ve atayabilmek için önce uygulamayı Intune’a ekleyin. Intune, kullanıcının cihazındaki giriş ekranında web uygulaması için bir kısayol oluşturur.

> [!Note]
> Android for Work ve macOS cihazlarında web uygulamaları desteklenmez.

## <a name="add-a-web-app-to-intune"></a>Intune’a bir web uygulaması ekleme
Bir uygulamayı web’de uygulamanın kısayolu olarak Intune’a eklemek için:

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin.  
    Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükü bölmesindeki **Yönet**'in altında **Uygulamalar**’ı seçin.
5. **Uygulamalar** bölmesinde **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** açılan listesinden **Web bağlantısı** türünü seçin.
7. **Yapılandır**’ı seçin.
8. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri ekleyin:
    - **Ad**: Şirket Portalı’nda görüntülendiği şekliyle uygulamanın adını girin.
    - **Açıklama**: Uygulama için bir açıklama girin. Bu açıklama Şirket Portalı’nda kullanıcılara görüntülenir.Açıklama şirket portalında kullanıcılara görüntülenir.
    - **Yayımcı**: Bu uygulamanın yayımcısının adını girin.
    - **Uygulama URL’si**: Atamak istediğiniz uygulamayı barındıran web sitesinin URL’sini girin.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden veya kendi oluşturduğunuz kategorilerden birini ya da birkaçını seçin. Böylelikle, Şirket Portalı’na göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Bu seçenek uygulama paketini, kullanıcılar uygulamalara göz atarken Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüler.
    - **Bu bağlantının açılabilmesi için bir yönetilen tarayıcı gerektir**: Kullanıcılara, Intune ile yönetilen tarayıcıda açabilecekleri bir web sitesi veya web uygulaması bağlantısı atayın. Bu tarayıcı cihazlarında yüklü olmalıdır.
    - **Logo**: Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
9. **Tamam**’ı seçin.
10. **Uygulama ekle** bölmesinde **Ekle**’yi seçin.

> [!Note]
> Android cihazlarına atanmış web uygulamalarını görüntüleyebilmek için kullanıcıların giriş ekranlarına Intune pencere öğesini eklemeleri gerekir.

## <a name="next-steps"></a>Sonraki adımlar

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md). 
