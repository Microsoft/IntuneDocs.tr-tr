---
title: "Intune’daki cihazları gruplar halinde kategorilere ayırma"
titleSuffix: Microsoft Intune
description: "Daha kolay yönetim için cihazları gruplar halinde kategorilere ayırmayı öğrenin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d07b025881ea78299d617205ce5ba39bb92a1231
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="categorize-devices-into-groups-for-easier-management"></a>Daha kolay yönetim için cihazları gruplar halinde kategorilere ayırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihazların yönetimini kolaylaştırmak için cihazları kendi tanımladığınız kategorilere göre otomatik olarak gruplara eklemek için Microsoft Intune cihaz kategorilerini kullanın.

Cihaz kategorileri aşağıdaki iş akışını kullanır:
1. Kullanıcıların cihazlarını kaydederken arasından seçim yapabileceği kategoriler oluşturma
2. iOS ve Android cihazlarının son kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Bir Windows cihazına bir kategori atamak için, son kullanıcıların Şirket Portalı web sitesini kullanmaları gerekir (diğer ayrıntılar için bu makaledeki **Cihaz gruplarını yapılandırdıktan sonra** bölümüne bakın).
3. Ardından bu gruplara ilkeler ve uygulamalar dağıtabilirsiniz.

İstediğiniz herhangi bir cihaz kategori oluşturabilirsiniz, örneğin:
- Satış noktası cihazı
- Tanıtım cihazı
- Satış
- Muhasebe
- Manager

## <a name="how-to-configure-device-categories"></a>Cihaz kategorilerini yapılandırma

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1. Adım - Azure Portal’ın Intune dikey penceresinde cihaz kategorileri oluşturma
1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihaz kaydı**’nı seçin.
2. **Cihaz kaydı** dikey penceresinde **Cihaz kategorileri**’ni seçin.
3. **Cihaz kategorileri** sayfasında, yeni kategori eklemek için **Oluştur**’u seçin.
4. **Cihaz kategorisi oluştur** dikey penceresinde, yeni kategori için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.
5. İşiniz bittiğinde **Oluştur**’a tıklayın. Kategori listesinde yeni kategoriyi görebilirsiniz.

2. adımda Azure Active Directory güvenlik grupları oluştururken cihaz kategorisi adını kullanacaksınız.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. Adım - Active Directory güvenlik grupları oluşturma
Bu adımda, Azure portalında cihaz kategorisi ve cihaz kategorisi adına dayalı dinamik gruplar oluşturacaksınız.

Devam etmek için Azure Active Directory belgelerindeki [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) makalesine bakın.

**deviceCategory** özniteliğini kullanarak gelişmiş bir kural ile bir cihaz grubu oluşturmak için bu bölümdeki bilgilerden yararlanın. Örneğin, (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Siz cihaz gruplarını yapılandırdıktan ve kullanıcılar cihazlarını kaydettikten sonra, onlara sizin yapılandırdığınız kategori listesi gösterilir. Kullanıcılar kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen Active Directory güvenlik grubuna eklenir.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Yönettiğiniz cihazların kategorilerini görüntüleme

1.  [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar**’ı seçin.

2.  **Yönet**’in altında **Tüm cihazlar**’a tıklayın.

3.  Cihaz listesinde **Cihaz kategorisi** sütununu inceleyin.

**Cihaz kategorisi** sütunu görüntülenmiyorsa **Sütunlar**’a tıklayın, listeden **Cihaz kategorisi**’ni seçin ve **Uygula**’ya tıklayın.

### <a name="to-change-the-category-of-a-device"></a>Cihazın kategorisini değiştirmek için

1. [Azure portalında Intune](https://aka.ms/intuneportal)’da, **Cihazlar**’ı seçin.
2. **Yönet** kısmındaki **Cihazlar** dikey penceresinde **Tüm cihazlar**’ı seçin.
3. Cihaz listesinde istediğiniz cihazı seçin ve ardından **Yönet** kısmındaki cihaz özellikleri dikey penceresinde **Özellikler**’i seçin.
4. Sonraki dikey pencerede, seçili cihazın **Cihaz kategorisi**’ni daha önce yapılandırmış olduğunuz herhangi bir kategori adıyla değiştirebilirsiniz.

## <a name="after-you-configure-device-groups"></a>Cihaz gruplarını yapılandırdıktan sonra

iOS ve Android cihazlarının son kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen Intune cihaz grubuna veya Active Directory güvenlik grubuna eklenir.

Windows'daki son kullanıcılar bir kategori seçmek için Şirket Portalı web sitesini kullanmalıdır.

Platformları ne olursa olsun, son kullanıcılarınız cihazlarını kaydettikten sonra istedikleri zaman portal.manage.microsoft.com adresine gidebilir. Kullanıcının Şirket Portalı web sitesine erişmesini ve **Cihazlarım**'a gitmesini sağlayın. Sayfada listelenen kayıtlı bir cihazı ve sonra da kategoriyi seçebilir.

Bir kategori seçtikten sonra cihaz, oluşturduğunuz karşılık gelen gruba otomatik olarak eklenir. Cihaz siz kategorileri yapılandırmadan önce kaydedildiyse, son kullanıcı Şirket Portalı web sitesinde cihaz hakkında bir bildirim görür ve Şirket Portalı uygulamasına iOS veya Android üzerinde bir daha eriştiğinde kendisinden bir kategori seçmesi istenir.

## <a name="further-information"></a>Daha fazla bilgi
- Azure Portal’da cihaz kategorisini düzenleyebilirsiniz; ama bu kategoriye başvuran tüm Azure Active Directory Güvenlik gruplarını el ile güncelleştirmeniz gerekir.

- Bir kategoriyi silerseniz, bu kategoriye atanmış olan tüm cihazlar **Atanmamış** kategori adını görüntüler.
