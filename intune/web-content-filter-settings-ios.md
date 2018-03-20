---
title: "iOS cihazları için Microsoft Intune web içeriği filtresi ayarları"
titlesuffix: 
description: "iOS çalıştıran cihazlarından web sitelerine erişim izni vermek veya erişimi engellemek için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a401a3a04d10587606b8ec4862a62e551e7aadf0
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="web-content-filter-settings-for-ios-devices"></a>iOS cihazları için web içeriği filtresi ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu makalede, iOS çalıştıran cihazlardan tarayıcı URL erişimini denetlemek için kullanabileceğiniz Microsoft Intune ayarları gösterilir.

URL'leri yapılandırmak için kullanabileceğiniz iki yöntem vardır:

- **URL'leri yapılandırma** - Apple'ın küfür veya cinsel içerikli terimleri arayan yerleşik web filtresini kullanın. Bu işlev, yüklenirken her web sayfasını değerlendirir ve uygunsuz içeriği belirlemeyi ve engellemeyi dener. Ayrıca, filtre tarafından denetlenmeyen URL'ler veya filtre ayarlarından bağımsız olarak engellenen URL'ler de yapılandırabilirsiniz.

- **Yalnızca belirli web siteleri** (Yalnızca Safari web tarayıcısı için) - Bu URL'ler Safari tarayıcısının yer işaretlerine eklenir. Kullanıcının **yalnızca** bu siteleri ziyaret etmesine izin verilir; başka sitelere erişilemez. Bu seçeneği yalnızca kullanıcıların erişebileceği URL'lerin tam listesini biliyorsanız kullanın.
Herhangi bir URL belirtmezseniz son kullanıcılar microsoft.com, microsoft.net ve apple.com dışında hiçbir web sitesine erişemez.

## <a name="get-started"></a>Başlarken

1. Cihaz özellikleri bölmesinde **Web İçerik Filtresi (yalnızca denetimli)** seçeneğini belirleyin.
2. **Web İçerik Filtresi** sayfasında, yapılandırmak istediğiniz **Filtre türünü** seçin:
    - **Yapılandırılmamış** - Filtre uygulanmaz.
    - **URL’leri Yapılandır**
    - **Yalnızca belirli web siteleri**
3. Ardından, kullanmakta olduğunuz filtre türüne bağlı olarak aşağıdaki yordamlardan birini kullanın:


## <a name="configure-urls"></a>URL’leri Yapılandırma

1. **Web İçerik Filtresi** sayfasında, gerekirse aşağıdaki ayarlardan birini seçin:
   - **İzin verilen URL'ler** - **İzin verilen URL’ler** sayfasında, izin vermek istediğiniz URL’leri girin (Apple web filtresini atlayarak) ve her birinden sonra giriş seçeneğini belirleyin.
     > [!NOTE]
     > Burada belirttiğiniz URL’ler, Apple web filtresi uygulamak istemediğiniz uygulamalardır. Bu URL’ler izin verilen sitelerin bir listesini temsil etmez. İstediğiniz buysa, **Yalnızca belirli web siteler**’i kullanın.

   - **Engellenen URL'ler** - **Engellenen URL’ler** sayfasında, engellemek istediğiniz URL’leri girin (Apple web filtresi ayarlarına bakılmaksızın) ve her birinden sonra giriş seçeneğini belirleyin.
2. İşiniz bittiğinde **Tamam**'a tıklayın.


## <a name="specific-websites-only"></a>Yalnızca belirli web siteleri

1. **Web İçerik Filtresi** bölmesinde, izin vermek istediğiniz her web sitesi için aşağıdaki ayarları yapılandırın:
    - **URL** - İzin vermek istediğiniz web sitesinin URL'sini girin; ör. **http://www.contoso.com**.
    - **Yer İşareti Yolu** - Yer işaretini kaydetmek istediğiniz yolu girin; ör. **/Contoso/İş Uygulamaları**. Bir yol eklemezseniz yer işareti cihazdaki varsayılan yer işareti klasörüne eklenir.
    - **Başlık** - Yer işareti için açıklayıcı bir başlık girin.
2. Her web sitesinin bilgilerini girdikten sonra **Ekle**’ye tıklayın.
3. İşiniz bittiğinde **Tamam**'a tıklayın.

>[!IMPORTANT]
> Aşağıdaki URL’lere Intune tarafından otomatik olarak izin verilir.
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## <a name="finish-up"></a>Bitirme

**Profil Oluştur** bölmesine dönmek için **Tamam**’ı ve ardından **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).
