---
title: "iOS cihazları için Intune web içeriği filtresi ayarları"
titlesuffix: Azure portal
description: "iOS cihazlarından web sitelerine erişim izni vermek veya bunu engellemek için kullanabileceğiniz ayarları öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89641cee439d7da9f73d56c2ab3d6d8299164700
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="web-content-filter-settings-for-ios-devices"></a>iOS cihazları için web içeriği filtresi ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Web tarayıcısı son kullanıcılarının iOS cihazlarda ziyaret edebileceği veya edemeyeceği URL’leri yapılandırmak için bu ayarları kullanın. URL'leri yapılandırmak için kullanabileceğiniz iki yöntem vardır:

- **URL'leri yapılandırma** - Apple'ın küfür veya cinsel içerikli terimleri arayan yerleşik web filtresini kullanın. Bu işlev, yüklenirken her web sayfasını değerlendirir ve uygunsuz içeriği belirlemeyi ve engellemeyi dener. Ayrıca, filtre tarafından denetlenmeyen URL'ler veya filtre ayarlarından bağımsız olarak engellenen URL'ler de yapılandırabilirsiniz.

- **Yalnızca belirli web siteleri** (Yalnızca Safari web tarayıcısı için) - Bu URL'ler Safari tarayıcısının yer işaretlerine eklenir. Kullanıcının **yalnızca** bu siteleri ziyaret etmesine izin verilir; başka sitelere erişilemez. Bu seçeneği yalnızca kullanıcıların erişebileceği URL'lerin tam listesini biliyorsanız kullanın.
Herhangi bir URL belirtmezseniz son kullanıcılar microsoft.com, microsoft.net ve apple.com dışında hiçbir web sitesine erişemez.



## <a name="get-started"></a>Başlarken

1. Cihaz özellikleri dikey penceresinde **Web İçerik Filtresi (yalnızca denetimli)** seçeneğini belirleyin.
2. **Web İçerik Filtresi** dikey penceresinde, yapılandırmak istediğiniz **Filtre türünü** seçin:
    - **Yapılandırılmamış** - Filtre uygulanmaz.
    - **URL’leri Yapılandır**
    - **Yalnızca belirli web siteleri**
3. Ardından, kullanmakta olduğunuz filtre türüne bağlı olarak aşağıdaki yordamlardan birini kullanın:


## <a name="configure-urls"></a>URL’leri Yapılandırma

1. **Web İçerik Filtresi** dikey penceresinde, gerekirse aşağıdaki ayarlardan birini seçin:
    - **İzin verilen URL'ler** - **İzin verilen URL’ler** dikey penceresinde, izin vermek istediğiniz URL’leri girin (Apple web filtresini atlayarak) ve her birinden sonra giriş seçeneğini belirleyin.
    - **Engellenen URL'ler** - **Engellenen URL’ler** dikey penceresinde, engellemek istediğiniz URL’leri girin (Apple web filtresi ayarlarına bakılmaksızın) ve her birinden sonra giriş seçeneğini belirleyin.
2. İşiniz bittiğinde **Tamam**'a tıklayın.


## <a name="specific-websites-only"></a>Yalnızca belirli web siteleri

1. **Web İçerik Filtresi** dikey penceresinde, izin vermek istediğiniz her web sitesi için aşağıdaki ayarları yapılandırın:
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

**Profil Oluştur** dikey penceresine dönmek için **Tamam**’ı ve ardından **Oluştur**’u seçin.

## <a name="next-steps"></a>Sonraki adımlar

Artık seçtiğiniz gruplara cihaz profilini atayabilirsiniz. Ayrıntılar için bkz. [Cihaz profilleri atama](device-profile-assign.md).
