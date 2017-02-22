---
title: "Intune’da cihaz kategorilerini kullanma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Kullanıcıların cihazlarını Intune’a kaydederken seçebilecekleri cihaz kategorilerini kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1609ed2f127fe9d7d1f1c3b3e923bd12f1088200
ms.openlocfilehash: 41b3cfb8006a7390094d01b4f0fdc38417e858be


---

# <a name="map-device-groups"></a>Cihaz gruplarını eşleme


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Cihazların yönetimini kolaylaştırmak için cihazları kendi tanımladığınız kategorilere göre otomatik olarak gruplara eklemek için Microsoft Intune cihaz kategorilerini kullanın.

Cihaz kategorileri aşağıdaki iş akışını kullanır:
1.    Kullanıcıların cihazlarını kaydederken arasından seçim yapacağı kategoriler oluşturma
4.    Son kullanıcılar cihazlarını kaydettiklerinde, yapılandırdığınız kategori listesinden bir kategori seçmeleri gerekir. Bir cihaz zaten kaydedilmişse, Şirket Portalı uygulamasına bir sonraki erişiminde son kullanıcıdan bir kategori seçmesi istenir.


İstediğiniz herhangi bir cihaz kategori oluşturabilirsiniz, örneğin:
- Satış noktası cihazı
- Tanıtım cihazı
- Satış
- Muhasebe
- Manager

## <a name="how-to-configure-device-categories"></a>Cihaz kategorilerini yapılandırma

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>1. Adım - Azure Portal’ın Intune dikey penceresinde cihaz kategorileri oluşturma
1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları kaydet**’i seçin.
3. **Kayıt** dikey penceresinde **Cihaz Kategorileri**’ni seçin.
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
1.    Azure Portal’ın Intune dikey penceresinde **Cihazlar ve Gruplar**’ı seçin.

2.    **Yönet**’in altında **Tüm cihazlar**’a tıklayın.

3.    Cihaz listesinde **Kategori** sütununu inceleyin.

**Kategori** sütunu görüntülenmiyorsa **Sütunlar**’a tıklayın, listeden **Kategori**’yi seçin ve **Uygula**’ya tıklayın.

### <a name="to-change-the-category-of-a-device"></a>Cihazın kategorisini değiştirmek için

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar ve Gruplar**’ı seçin.
4. **Cihazlar ve Gruplar** dikey penceresinde **Yönet** > **Tüm cihazlar**’ı seçin.
5. Cihaz listesinde istediğiniz cihazı seçin ve ardından cihaz özellikleri dikey penceresinde **Yönet** > **Özellikler**’i seçin.
6. Sonraki dikey pencerede, seçili cihazın **Cihaz kategorisi**’ni daha önce yapılandırmış olduğunuz herhangi bir kategori adıyla değiştirebilirsiniz.



## <a name="further-information"></a>Daha fazla bilgi
- Azure Portal’da cihaz kategorisini düzenleyebilirsiniz; ama bunu yaparsanız, bu kategoriye başvuran tüm Azure Active Directory Güvenlik gruplarını el ile güncelleştirmeniz gerekir.

- Bir kategoriyi silerseniz, bu kategoriye atanmış olan tüm cihazlar sonunda **Atanmamış** kategori adını görüntüler.





<!--HONumber=Feb17_HO2-->


