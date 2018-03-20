---
title: "Windows mağazası uygulamalarını Microsoft Intune’a ekleme"
titleSuffix: 
description: "Microsoft Intune'a Windows mağazası uygulamaları ekleme hakkında bilgi edinin."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e2280ad72bbd353d80af316cde436e8ffc79d1f
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Windows mağazası uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. Aşağıdaki adımlar Microsoft Intune'a bir Windows mağaza uygulaması eklemenizi sağlar.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama ekle** bölmesinde, **Uygulama türü** olarak **Windows**’u ve **Uygulama bilgileri**’ni seçin.
7. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri yapılandırın. Bitirdiğinizde, **Tamam**’a tıklayın. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad** - Uygulamanın şirket portalında görüntülenecek olan adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama** - Şirket portalında kullanıcılara görüntülenmek üzere bir uygulama açıklaması girin.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Uygulama mağazası URL’si** - Oluşturmak istediğiniz uygulamanın uygulama mağazası URL’sini girin.
    - **Kategori (isteğe bağlı)** - Yerleşik uygulama kategorilerinden birini veya daha fazlasını ya da oluşturduğunuz bir kategoriyi seçin; bu, şirket portalına göz atan kullanıcıların uygulamayı bulmasını kolaylaştırır.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Logo** -- Uygulamayla ilişkilendirilecek bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülenir.
8. İşiniz bittiğinde, **Uygulama ekle** bölmesinde **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulamaları gruplara ekleme](apps-deploy.md)