---
title: Intune’daki cihazları gruplar halinde kategorilere ayırma
titleSuffix: Microsoft Intune
description: Daha kolay yönetim için cihazları gruplar halinde kategorilere ayırmayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 159079686507815ad4cf1738ca4157467352f681
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189529"
---
# <a name="categorize-devices-into-groups-for-easier-management"></a>Daha kolay yönetim için cihazları gruplar halinde kategorilere ayırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tanımladığınız cihaz kategorilerine dayanarak cihazları gruplara otomatik olarak eklemek için Microsoft Intune cihaz gruplarını kullanın. Böylece bu cihazları yönetmeniz kolaylaşır.

Cihaz kategorileri aşağıdaki iş akışını kullanır:
1. Kullanıcıların cihazlarını kaydederken arasından seçim yapabileceği kategoriler oluşturun.
2. iOS ve Android cihazlarının kullanıcıları bir cihaz kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Bir Windows cihaza kategori atamak için kullanıcıların Şirket Portalı web sitesini kullanmaları gerekir.
3. Ardından bu gruplara ilkeler ve uygulamalar dağıtabilirsiniz.

İstediğiniz herhangi bir cihaz kategorisini oluşturabilirsiniz. Örneğin:
- Satış noktası cihazı
- Tanıtım cihazı
- Satış
- Muhasebe
- Manager

## <a name="how-to-configure-device-categories"></a>Cihaz kategorilerini yapılandırma

### <a name="step-1-create-device-categories-on-the-intune-blade-of-the-azure-portal"></a>1. Adım: Azure portalının Intune dikey penceresinde cihaz kategorileri oluşturma
1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı**’nı seçin.
2. **Cihaz kaydı** dikey penceresinde **Cihaz kategorileri**’ni seçin.
3. **Cihaz kategorileri** sayfasında, yeni kategori eklemek için **Oluştur**’u seçin.
4. **Cihaz kategorisi oluştur** dikey penceresinde, yeni kategori için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.
5. İşiniz bittiğinde **Oluştur**’u seçin. Kategori listesinde yeni kategoriyi görebilirsiniz.

2. adımda Azure Active Directory (Azure AD) güvenlik grupları oluştururken cihaz kategorisi adını kullanacaksınız.

### <a name="step-2-create-azure-active-directory-security-groups"></a>2. Adım: Active Directory güvenlik grupları oluşturma
Bu adımda, Azure portalında cihaz kategorisi ve cihaz kategorisi adına dayalı dinamik gruplar oluşturacaksınız.

Devam etmek için Azure AD belgelerindeki [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) konusuna bakın.

**deviceCategory** özniteliğini kullanarak gelişmiş bir kural ile bir cihaz grubu oluşturmak için bu bölümdeki bilgilerden yararlanın. Örneğin (**device.deviceCategory -eq** “*Azure portalından aldığınız cihaz kategorisi adı*”.

Siz cihaz gruplarını yapılandırdıktan ve kullanıcılar cihazlarını kaydettikten sonra, onlara sizin yapılandırdığınız kategori listesi gösterilir. Kullanıcılar kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen Active Directory güvenlik grubuna eklenir.

### <a name="view-the-categories-of-devices-that-you-manage"></a>Yönettiğiniz cihazların kategorilerini görüntüleme

1.  [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar**’ı seçin.

2.  **Yönet** altında **Tüm cihazlar**’ı seçin.

3.  Cihaz listesinde **Cihaz kategorisi** sütununu inceleyin.

**Cihaz kategorisi** sütununu göremiyorsanız **Sütunlar**’ı seçin. Listeden **Cihaz kategorisi**’ni seçin ve daha sonra **Uygula**’ya tıklayın.

### <a name="change-the-category-of-a-device"></a>Bir cihazın kategorisini değiştirme

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar**’ı seçin.
2. **Yönet** kısmındaki **Cihazlar** dikey penceresinde **Tüm cihazlar**’ı seçin.
3. Cihazlar listesinde istediğiniz cihazı seçin. Daha sonra **Yönet** bölümü altındaki cihaz özellikleri dikey penceresinde **Özellikler**’i seçin.
4. Sonraki dikey pencerede, seçili cihazın **Cihaz kategorisi**’ni daha önce yapılandırmış olduğunuz herhangi bir kategori adıyla değiştirebilirsiniz.

## <a name="after-you-configure-device-groups"></a>Cihaz gruplarını yapılandırdıktan sonra

iOS ve Android cihazlarının kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Kategoriyi seçip kaydı tamamladıktan sonra cihazlar, seçtikleri kategoriye karşılık gelen Intune cihaz grubuna veya Active Directory güvenlik grubuna eklenir.

Windows kullanıcıları bir kategori seçmek için Şirket Portalı web sitesini kullanmalıdır.

Platformları ne olursa olsun kullanıcılarınız cihazlarını kaydettikten sonra istedikleri zaman portal.manage.microsoft.com adresine gidebilir. Kullanıcının Şirket Portalı web sitesine erişmesini ve **Cihazlarım**’a gitmesini sağlayın. Kullanıcı, sayfada listelenen kayıtlı bir cihazı ve sonra da kategoriyi seçebilir.

Bir kategori seçtikten sonra cihaz, oluşturduğunuz karşılık gelen gruba otomatik olarak eklenir. Kategorileri yapılandırmadan önce kaydedilmiş bir cihaz varsa kullanıcı, Şirket Portalı web sitesinde bu cihaz hakkında bildirim alır. Bu bildirim, kullanıcıya iOS veya Android’de Şirket Portalı’na eriştiğinde kategori seçmesi gerektiğini belirtir.

## <a name="further-information"></a>Daha fazla bilgi
- Azure Portalı’nda cihaz kategorisini düzenleyebilirsiniz ama bu kategoriye başvuran tüm Azure AD güvenlik gruplarını kendiniz güncelleştirmeniz gerekir.

- Bir kategoriyi silerseniz, bu kategoriye atanmış olan tüm cihazlar **Atanmamış** kategori adını görüntüler.
