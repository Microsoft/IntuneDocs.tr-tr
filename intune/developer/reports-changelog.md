---
title: Intune Veri Ambarı Değişiklik günlüğü
titleSuffix: Microsoft Intune
description: Bu konu, Microsoft Intune veri ambarı API 'SI için değişikliklerin bir listesini sağlar.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9740eed3ab727d76a9af4e46642d8279b310fd9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490530"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Intune Veri Ambarı API’si için değişiklik günlüğü

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune Veri Ambarı hakkında güncel bilgiler edinin.

## <a name="1903-part-2"></a>1903 (Bölüm 2)
_Yayımlanma tarihi 2019_

### <a name="beta-changes"></a>Beta değişiklikleri

Aşağıdaki tabloda, Intune veri ambarındaki son kaldırılan koleksiyonlar ve değişiklik koleksiyonları listelenmiştir.

|    Koleksiyon                          |    Değişebilir     |    Ek bilgiler                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Mobileappdeviceuserınstallstatus    |    Kaldırılır    |    Bunun yerine [Mobileappınstallstatuscounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts) kullanın.                                                                                                                                                                                                                                                                     |
|    enrollmentTypes                     |    Kaldırılır    |    Bunun yerine [Devicekayıtlarını Menttypes](intune-data-warehouse-collections.md#deviceenrollmenttypes) kullanın.                                                                                                                                                                                                                                                                                      |
|    Mdmdurumlar                         |    Kaldırılır    |    Bunun yerine [Karmaşıkstes](intune-data-warehouse-collections.md#compliancestates) kullanın.                                                                                                                                                                                                                                                                                               |
|    workPlaceJoinStateTypes             |    Kaldırılır    |    Bunun yerine [Devices](intune-data-warehouse-collections.md#devices) ve [devicepropertygeçmişteki](intune-data-warehouse-collections.md#devicepropertyhistories) `azureAdRegistered` özelliğini kullanın.                                                                                                                                                                                                             |
|    clientRegistrationStateTypes        |    Kaldırılır    |    Bunun yerine [Deviceregistrationstates](intune-data-warehouse-collections.md#deviceregistrationstates) kullanın.                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Kaldırılır    |    Bunun yerine [Kullanıcılar](intune-data-warehouse-collections.md#users) koleksiyonunu kullanın.                                                                                                                                                                                                                                                                                                      |
|    Mdmdeviceınventoryhistories         |    Kaldırılır    |    Özelliklerin birçoğu gereksizdir veya artık [Devicepropertygeçmişleri](intune-data-warehouse-collections.md#devicepropertyhistories) veya [cihazlar](intune-data-warehouse-collections.md#devices) koleksiyonlarında bulunabilir. Bu iki koleksiyon ile önceden listelenmeyen tüm **Mdmdeviceınventorygeçmişözellikleri** artık kullanılamaz. Aşağıdaki ayrıntılara bakın.    |

Aşağıdaki tabloda, daha önce **Mdmdeviceınventorygeçmişin** koleksiyonunda bulunan eski Özellikler ve değişiklik/değiştirme listelenmiştir. **Mdmdeviceınventorygeçmişde** bulunan ancak aşağıda listelenmeyen tüm özellikler kaldırılmıştır.

|    Eski Özellik                |    Değiştirme/değiştirme                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    cellularTechnology          |    cihazlar koleksiyonunda cellularTechnology                                     |
|    DeviceClientID              |    cihazlar koleksiyonundaki DeviceID                                               |
|    deviceManufacturer          |    cihazlar için üretici koleksiyonu                                           |
|    deviceModel                 |    cihazlar koleksiyonundaki model                                                  |
|    deviceName                  |    cihazlar koleksiyonundaki aygıtadı                                             |
|    deviceOsPlatform            |    cihazlar koleksiyonunda deviceTypeKey                                          |
|    deviceOsVersion             |    Devicepropertygeçmişde koleksiyonda osVersion                              |
|    deviceType                  |    cihazlar koleksiyonunda deviceTypeKey, DeviceType koleksiyonuna başvuruyor    |
|    encryptionState             |    cihazlar koleksiyonundaki encryptionState özelliği                           |
|    exchangeActiveSyncId        |    Devices koleksiyonundaki Easdeviceıd özelliği                               |
|    Exchangedeviceıd            |    cihazlar koleksiyonundaki Easdeviceıd                                            |
|    imei                        |    cihazlar için IMEI koleksiyonu                                                   |
|    isSupervised                |    cihazlar koleksiyonundaki ıssuperdenetimli özelliği                              |
|    Jailbreak uygulanmış                  |    Jailbreak uygulanmış Devicepropertygeçmişcollection                             |
|    meid                        |    cihazlar koleksiyonundaki MEID özelliği                                      |
|    $                         |    cihazlar için üretici koleksiyonu                                           |
|    osName                      |    cihazlar koleksiyonunda deviceTypeKey, DeviceType koleksiyonuna başvuruyor    |
|    phoneNumber                 |    cihazlar koleksiyonundaki phoneNumber                                            |
|    platformType                |    cihazlar koleksiyonundaki model                                                  |
|    ürün                     |    cihazlar koleksiyonunda deviceTypeKey                                          |
|    productVersion              |    Devicepropertygeçmişde koleksiyonda osVersion                              |
|    serialNumber                |    cihazlar koleksiyonunda serialNumber                                           |
|    storageFree                 |    cihazlar koleksiyonundaki freeStorageSpaceInBytes özelliği                   |
|    storageTotal                |    cihazlar koleksiyonundaki totalStorageSpaceInBytes özelliği                |
|    subscriberCarrierNetwork    |    cihazlar koleksiyonundaki subscriberCarrier özelliği                         |
|    wifimac                     |    cihazlar koleksiyonunda wiFiMacAddress                                         |

Aşağıdaki tabloda [Devicepropertygeçmişleri](intune-data-warehouse-collections.md#devicepropertyhistories) koleksiyonunda bulunan özelliklere yapılan değişiklikler listelenmiştir: 

|    Eski Özellik                  |    Değiştirme/değiştirme                                               |
|----------------------------------|---------------------------------------------------------------------|
|    CategoryID                    |    deviceCategoryKey, deviceCategories koleksiyonuna başvuruyor       |
|    certExpirationDate            |    Kaldırılır                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    cihazlar koleksiyonunda Kaydoleddatetime                           |
|    deviceTypeKey                 |    cihazlar koleksiyonunda deviceTypeKey                              |
|    Easıd                         |    cihazlar koleksiyonundaki Easdeviceıd                                |
|    Kaydolma kullanıcısı                |    cihazlar koleksiyonundaki Kullanıcı kimliği                                     |
|    kayıtkonumunda Menttypekey             |    cihazlar koleksiyonunda Devicekayıtmenttypekey                    |
|    Graphdeviceısuyumlu        |    Kaldırılır                                                          |
|    Graphdeviceısmanaged          |    Kaldırılır                                                          |
|    lastContact                   |    cihazlar koleksiyonunda lastSyncDateTime                           |
|    lastContactNotification       |    Kaldırılır                                                          |
|    Lastcontactworkplacejoın      |    Kaldırılır                                                          |
|    lastExchangeStatusUtc         |    Kaldırılır                                                          |
|    lastModifiedDateTimeUTC       |    Kaldırılır                                                          |
|    lastPolicyUpdateUtc           |    Kaldırılır                                                          |
|    managementAgentKey            |    managementStateKey                                               |
|    üretici                  |    cihazlar için üretici koleksiyonu                               |
|    mdmStatusKey                  |    Karmaşıkstes koleksiyonuna başvuruda bulunan Karmaşıkstatekey    |
|    model                         |    cihazlar koleksiyonundaki model                                      |
|    osFamily                      |    cihazlar koleksiyonunda operatingSystem                            |
|    osRevisionNumber              |    cihazlar koleksiyonundaki osVersion                                  |
|    ProcessorArchitecture         |    Kaldırılır                                                          |
|    Referenceıd                   |    cihazlar koleksiyonundaki Azureaddeviceıd                            |
|    serialNumber                  |    cihazlar koleksiyonunda serialNumber                               |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

Aşağıdaki tabloda, [cihazlar](intune-data-warehouse-collections.md#devices) koleksiyonunda bulunan özelliklerde yapılan değişiklikler listelenmiştir: 

|    Eski Özellik                  |    Değiştirme/değiştirme                                               |
|----------------------------------|---------------------------------------------------------------------|
|    CategoryID                    |    deviceCategoryKey, deviceCategories koleksiyonuna başvuruyor       |
|    certExpirationDate            |    Kaldırılır                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    Kaydoleddatetime                                                 |
|    Easıd                         |    Easdeviceıd                                                      |
|    Kaydolma kullanıcısı                |    UserID                                                           |
|    kayıtkonumunda Menttypekey             |    deviceEnrollmentTypeKey                                          |
|    Graphdeviceısuyumlu        |    Kaldırılır                                                          |
|    Graphdeviceısmanaged          |    Kaldırılır                                                          |
|    lastContact                   |    lastSyncDateTime                                                 |
|    lastContactNotification       |    Kaldırılır                                                          |
|    Lastcontactworkplacejoın      |    Kaldırılır                                                          |
|    lastExchangeStatusUtc         |    Kaldırılır                                                          |
|    lastPolicyUpdateUtc           |    Kaldırılır                                                          |
|    mdmStatusKey                  |    Karmaşıkstes koleksiyonuna başvuruda bulunan Karmaşıkstatekey    |
|    osFamily                      |    operatingSystem                                                  |
|    ProcessorArchitecture         |    Kaldırılır                                                          |
|    Referenceıd                   |    Azureaddeviceıd                                                  |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

Aşağıdaki tabloda, kayıtlistesi/ [kayıtlar koleksiyonunda bulunan](intune-data-warehouse-collections.md#enrollmentactivities) özelliklerde yapılan değişiklikler listelenmiştir: 

|    Eski Özellik         |    Değiştirme/değiştirme         |
|-------------------------|-------------------------------|
|    kayıtkonumunda Menttypekey    |    deviceEnrollmentTypeKey    |

Aşağıdaki tabloda, [Mamapplications](intune-data-warehouse-collections.md#mamapplications) koleksiyonunda bulunan özelliklerde yapılan değişiklikler listelenmiştir: 

|    Eski Özellik       |    Değiştirme/değiştirme    |
|-----------------------|--------------------------|
|    applicationKey     |    mamApplicationKey     |
|    ApplicationName    |    mamApplicationName    |
|    Uygulama      |    mamApplicationId      |

Aşağıdaki tabloda, [mamApplicationInstances](intune-data-warehouse-collections.md#mamapplicationinstances) koleksiyonunda bulunan özelliklerde yapılan değişiklikler listelenmiştir: 

|    Eski Özellik     |    Değiştirme/değiştirme    |
|---------------------|--------------------------|
|    Uygulama    |    mamApplicationId      |
|    DeviceID         |    Mamdeviceıd           |
|    deviceType       |    mamDeviceType         |
|    deviceName       |    Mamaygıtadı         |

Aşağıdaki tabloda, [Mamcheckins](intune-data-warehouse-collections.md#mamcheckins) koleksiyonunda bulunan özelliklerde yapılan değişiklikler listelenmiştir: 

|    Eski Özellik      |    Değiştirme/değiştirme    |
|----------------------|--------------------------|
|    applicationKey    |    mamApplicationKey     |

Aşağıdaki tabloda, [Kullanıcılar](intune-data-warehouse-collections.md#users) koleksiyonunda bulunan özelliklerde yapılan değişiklikler listelenmiştir: 

|    Eski Özellik             |    Değiştirme/değiştirme    |
|-----------------------------|--------------------------|
|    StartDate, Iveutc    |    Kaldırılır               |
|    EndDate, Iveutc      |    Kaldırılır               |
|    IsCurrent                |    Kaldırılır               |

## <a name="1903"></a>1903
_Yayımlanma tarihi 2019_

### <a name="v10-changes-reflecting-back-to-beta"></a>V 1.0 değişiklikleri Beta 'ya geri yansıtır
V 1.0 ilk olarak 1808 sürümünde sunulunca Beta API 'sinden bazı önemli yollarla farklıydı. 1903 ' de, bu değişiklikler Beta API sürümüne geri yansıtılır. Beta API sürümünü kullanan önemli raporlarınız varsa, değişikliklerden kaçınmak için bu raporların V 1.0 'a geçişini kesinlikle öneririz. Veri ambarı API 'SI sürümleri ve geriye dönük uyumluluk hakkında daha fazla bilgi için lütfen [API sürüm bilgilerine](../reports-api-url.md) bakın. 

## <a name="1902"></a>1902 
_Yayımlanma tarihi 2019_

### <a name="power-bi-compliance-app"></a>Uyumluluk uygulaması Power BI 

Intune [Uyumluluk (veri ambarı)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) uygulamasını kullanarak Power BI çevrimiçi ortamda Intune veri ambarınıza erişin. Bu Power BI uygulamayla, artık önceden oluşturulmuş raporlara herhangi bir kurulum olmadan ve Web tarayıcınızdan çıkmadan erişebilir ve bunları paylaşabilirsiniz. 

> [!NOTE]
> Intune uyumluluk uygulamasına uygulayabileceğiniz iki ek filtre vardır.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Intune uyumluluk uygulamasına ek filtreler ekleme
1. Web tarayıcılarınızın [Intune uyumluluk (veri ambarı)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) uygulamasını açın.
2. **Uyumlu olmayan cihazlar** ' a tıklayın ve **karmaşıstatus** filtresinde **uyumlu değil** ' i seçin. 
3. **Bilinmeyen cihazlar** ' a tıklayın ve daha önce **karmaşıstatus** filtresinde **yok** ' u seçin. 

## <a name="1812"></a>1812 
_Serbest bırakıldı Aralık 2018_

### <a name="enrollment-activities-collection-released-to-v10"></a>V 1.0 'da yayınlanan kayıt etkinlikleri koleksiyonu 

Kayıt etkinlikleri koleksiyonu artık v 1.0 sürümünde kullanılabilir. Bu koleksiyonu, ortamınızdaki kayıt hatası hacmini ve eğilimlerini anlamak için kullanabilirsiniz. Daha fazla bilgi için [bkz.](intune-data-warehouse-collections.md#enrollmentfailurereasons) [Kayıtetacmize](intune-data-warehouse-collections.md#enrollmentactivities), [kayıteteventdurumlar](intune-data-warehouse-collections.md#enrollmenteventstatuses), [kayıtefailurecategories](intune-data-warehouse-collections.md#enrollmentfailurecategories)ve kayıtlar.

## <a name="1808"></a>1808
_Yayınlanma tarihi: Ağustos 2018_

### <a name="v10-collections"></a>v1.0 Koleksiyonlar  

Artık `api-version=v1.0` sorgu parametresini ayarlayarak Intune Veri Ambarı’nın v1.0 sürümünü kullanabilirsiniz. Veri Ambarı’ndaki koleksiyonlara yapılan güncelleştirmeler ek olarak yapılır, yani mevcut senaryoları bozmaz.

### <a name="enrollment-activities-collection-released-to-beta"></a>Beta 'da yayınlanan kayıt etkinlikleri koleksiyonu

Yeni `Enrollment Activities` koleksiyonu, beta sürümünde yayımlandı. Bu koleksiyonu kullanarak en yaygın hataları görüntüleyebilir ve ortamınızın ne durumda olduğunu anlayabilirsiniz. 


## <a name="1805"></a>1805
_Yayımlanma Tarihi Mayıs 2018_

### <a name="correction-to-device-count-in-devices-collection"></a>**Cihazlar** koleksiyonundaki cihaz sayısında düzeltme 

**Cihazlar** koleksiyonunda, `isDeleted` özniteliğine göre filtreleme yapan cihazların toplam sayısını azaltma ihtimali olan bir düzeltme yapıldı. Bu azalma, düzeltmenin sonucu olarak ortaya çıkar ve bir hata değildir. **Cihazlar** koleksiyonu hakkında daha fazla bilgi için bkz. [Cihaz varlıkları için başvuru](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Ocak 2018’de yayımlandı_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Intune Veri Ambarı uygulaması - yalnızca kimlik doğrulama <!-- 1867540 -->

Azure Active Directory (Azure AD) kullanarak bir uygulamayı ayarlayabilir ve Intune Veri Ambarı’nda kimlik doğrulayabilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı uygulaması - yalnızca kimlik doğrulama](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri <!-- 2077525 -->

- Intune Veri Ambarı’na (API dahil) erişirken, bir Intune lisansının kullanıcıya atanması artık gerekli değildir.
- Intune rol adı, **Raporlar** yerine **Intune veri ambarı** olarak değiştirildi. 

    Daha fazla bilgi için bkz. [Azure AD ve Intune kimlik bilgisi gereksinimleri](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>OData sorgu seçenekleri <!-- 2077711 -->

<code>$select</code> öğesini OData sorgu parametresi olarak kullanabilirsiniz. Mevcut sürüm, aşağıdaki OData sorgu parametrelerini destekler: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> ve <code>$top</code>. Daha fazla bilgi için bkz. [OData sorgu seçenekleri](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Veri ambarı veri modelinde yeni varlıklar <!-- 2077804 -->

- [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md) varlığı eklendi. **MobileAppDeviceUserInstallStatus** belirli bir cihaz ve kullanıcı için mobil uygulama yükleme durumunu gösterir.
- [**Mobileappınstallstates**](reports-ref-application.md#mobileappinstallstates)varlığı eklendi. **MobileAppInstallState** varlığı, bir mobil uygulamanın cihazlar, kullanıcılar veya her ikisini de içeren bir gruba atandıktan sonra yükleme durumunu gösterir. 

## <a name="1710"></a>1710
_Yayımlanma tarihi: Kasım 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Geçerli Kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin olan kullanıcı verisi ile sınırlıdır <!-- 1544273 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, verilerde kullanıcı ve durumu bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmamış olan kullanıcıları içerir. **Geçerli kullanıcı** varlık koleksiyonu yalnızca etkin kullanıcıları içerir. **Geçerli Kullanıcı** öğesi hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](../reports-ref-current-user.md).

## <a name="1709"></a>1709
_Yayınlanma tarihi: Ekim 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune veri ambarı veri modeline eklenen Kullanıcı cihaz ilişkilendirmesi varlık koleksiyonu <!-- 1187917 -->

Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz. OData uç noktası veya özel bir istemci geliştirme yoluyla Veri Ambarı Intune sayfasından alınan Power BI dosyasından (PBIX) veri modeline erişebilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı Cihaz İlişkisi](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Veri ambarı veri modelinde yeni varlıklar <!-- 1479526 --><!-- -->

- [**UserDeviceAssociation**](reports-ref-user-device.md) varlığı eklendi. **UserDeviceAssociation**, kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir. Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz.  
- [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) varlığı eklendi. **IntuneManagementExtension**, mobil cihazlar için sürüm veya yükleme durumu gibi bilgileri izleyen varlıklar barındırır.

## <a name="next-steps"></a>Sonraki adımlar
- [Intune’daki haftalık yenilikleri](../fundamentals/whats-new.md) öğrenin. Yaklaşan değişiklikler, hizmet hakkında önemli bildirimler ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.
- [Microsoft Intune Blogu](https://go.microsoft.com/fwlink/?LinkID=273882)’nu okuyun.
