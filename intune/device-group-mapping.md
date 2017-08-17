---
title: Intune'da cihaz kategorilerini kullanma
titleSuffix: Intune on Azure
description: "Kullanıcıların cihazlarını Intune'a kaydederken seçebilecekleri cihaz kategorilerini kullanmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c5d97499545d0ad3899f28ed4e88eb4dc1fe734
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2017
---
# <a name="map-device-groups"></a>Cihaz gruplarını eşleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cihazların yönetimini kolaylaştırmak için cihazları kendi tanımladığınız kategorilere göre otomatik olarak gruplara eklemek için Microsoft Intune cihaz kategorilerini kullanın.

Cihaz kategorileri aşağıdaki iş akışını kullanır:
1. Kullanıcıların cihazlarını kaydederken arasından seçim yapacağı kategoriler oluşturma
3. iOS ve Android cihazlarının son kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Bir Windows cihazına bir kategori atamak için, son kullanıcıların Şirket Portalı web sitesini kullanmaları gerekir (ayrıntılar için bu konu başlığındaki **Cihaz gruplarını yapılandırdıktan sonra** bölümüne bakın).
4. Ardından bu gruplara ilkeler ve uygulamalar dağıtabilirsiniz.

İstediğiniz herhangi bir cihaz kategori oluşturabilirsiniz, örneğin:
- Satış noktası cihazı
- Tanıtım cihazı
- Satış
- Muhasebe
- Manager

## <a name="how-to-configure-device-categories"></a>Cihaz kategorilerini yapılandırma

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1. Adım - Azure Portal’ın Intune dikey penceresinde cihaz kategorileri oluşturma
1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz Kaydı**'nı seçin.
3. **Cihaz Kaydı** dikey penceresinde **Cihaz Kategorileri**’ni seçin.
4. **Cihaz Kategorileri** sayfasında, yeni kategori eklemek için **Oluştur**’u seçin.
5. Sonraki dikey pencerede, yeni kategori için bir **Ad** ve isteğe bağlı **Açıklama** girin.
6. İşiniz bittiğinde **Oluştur**’a tıklayın. Yeni oluşturduğunuz kategoriyi kategoriler listesinde görürsünüz.

2. adımda Azure Active Directory güvenlik grupları oluştururken cihaz kategorisi adını kullanacaksınız.

### <a name="step-2---create-azure-active-directory-security-groups"></a>2. Adım - Active Directory güvenlik grupları oluşturma
Bu adımda, Azure portalında cihaz kategorisi ve cihaz kategorisi adına dayalı dinamik gruplar oluşturacaksınız.

Devam etmek için Azure Active Directory belgelerindeki [Gelişmiş kurallar oluşturmak için öznitelikleri kullanma](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) konusuna bakın. 

**deviceCategory** özniteliğini kullanarak gelişmiş bir kural ile bir cihaz grubu oluşturmak için bu bölümdeki bilgilerden yararlanın. Örneğin, (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Siz cihaz gruplarını yapılandırdıktan ve kullanıcılar cihazlarını kaydettikten sonra, onlara sizin yapılandırdığınız kategori listesi gösterilir. Kullanıcılar kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen Active Directory güvenlik grubuna eklenir.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Yönettiğiniz cihazların kategorilerini görüntüleme

1.  Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Azure Portal’ın Intune dikey penceresinde **Cihazlar ve Gruplar**’ı seçin.

3.  **Yönet**’in altında **Tüm cihazlar**’a tıklayın.

4.  Cihaz listesinde **Kategori** sütununu inceleyin.

**Kategori** sütunu görüntülenmiyorsa **Sütunlar**’a tıklayın, listeden **Kategori**’yi seçin ve **Uygula**’ya tıklayın.

### <a name="to-change-the-category-of-a-device"></a>Cihazın kategorisini değiştirmek için

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar ve Gruplar**’ı seçin.
4. **Cihazlar ve Gruplar** dikey penceresinde **Yönet** > **Tüm cihazlar**’ı seçin.
5. Cihaz listesinde istediğiniz cihazı seçin ve ardından cihaz özellikleri dikey penceresinde **Yönet** > **Özellikler**’i seçin.
6. Sonraki dikey pencerede, seçili cihazın **Cihaz kategorisi**’ni daha önce yapılandırmış olduğunuz herhangi bir kategori adıyla değiştirebilirsiniz.

## <a name="after-you-configure-device-groups"></a>Cihaz gruplarını yapılandırdıktan sonra

iOS ve Android cihazlarının son kullanıcıları cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Kategoriyi seçip kaydı tamamladıktan sonra, cihazları seçtikleri kategoriye karşılık gelen Intune cihaz grubuna veya Active Directory güvenlik grubuna eklenir.

Bir Windows cihazına bir kategori atamak için, cihazı kaydettikten sonra son kullanıcıların Şirket Portalı web sitesini (portal.manage.microsoft.com) kullanmaları gerekir. Bir Windows cihazında, web sitesine erişin ve **Menü** > **Cihazlarım**'a gidin. Sayfada listelenen kayıtlı bir cihazı seçin, sonra bir kategori seçin. 

Bir kategori seçtikten sonra cihaz, oluşturduğunuz karşılık gelen gruba otomatik olarak eklenir. Cihaz siz kategorileri yapılandırmadan önce kaydedildiyse, son kullanıcı Şirket Portalı web sitesinde cihaz hakkında bir bildirim görür ve Şirket Portalı uygulamasına iOS veya Android üzerinde bir daha eriştiğinde kendisinden bir kategori seçmesi istenir.

## <a name="further-information"></a>Daha fazla bilgi
- Azure Portal’da cihaz kategorisini düzenleyebilirsiniz; ama bunu yaparsanız, bu kategoriye başvuran tüm Azure Active Directory Güvenlik gruplarını el ile güncelleştirmeniz gerekir.

- Bir kategoriyi silerseniz, bu kategoriye atanmış olan tüm cihazlar sonunda **Atanmamış** kategori adını görüntüler.


