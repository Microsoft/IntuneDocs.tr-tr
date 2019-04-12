---
title: Intune Veri Ambarı Değişiklik günlüğü
titleSuffix: Microsoft Intune
description: Bu konu, Microsoft Intune veri ambarı API'si için değişikliklerin bir listesini sağlar.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/11/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b4765cf953c2cdc9e972224b4f04c54df7a32af
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/11/2019
ms.locfileid: "59509727"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Intune Veri Ambarı API’si için değişiklik günlüğü

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune Veri Ambarı hakkında güncel bilgiler edinin.

## <a name="1903-part-2"></a>1903 (Bölüm 2)
_Nisan 2019 yayımlanan_

### <a name="beta-changes"></a>Beta değişiklikleri

Aşağıdaki tabloda, son kaldırılan koleksiyonları ve Intune veri ambarı'nda değişiklik koleksiyonları listeler.

|    Koleksiyon                          |    Değiştir     |    Ek bilgiler                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    mobileAppDeviceUserInstallStatus    |    Kaldırılır    |    Kullanım [mobileAppInstallStatusCounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts) yerine.                                                                                                                                                                                                                                                                     |
|    EnrollmentTypes                     |    Kaldırılır    |    Kullanım [deviceEnrollmentTypes](intune-data-warehouse-collections.md#deviceenrollmenttypes) yerine.                                                                                                                                                                                                                                                                                      |
|    MdmStatuses                         |    Kaldırılır    |    Kullanım [complianceStates](intune-data-warehouse-collections.md#compliancestates) yerine.                                                                                                                                                                                                                                                                                               |
|    WorkPlaceJoinStateTypes             |    Kaldırılır    |    Kullanım `azureAdRegistered` özelliğinde [cihazları](intune-data-warehouse-collections.md#devices) ve [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) koleksiyonlar yerine.                                                                                                                                                                                                             |
|    ClientRegistrationStateTypes        |    Kaldırılır    |    Kullanım [deviceRegistrationStates](intune-data-warehouse-collections.md#deviceregistrationstates) yerine.                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Kaldırılır    |    Kullanım [kullanıcılar](intune-data-warehouse-collections.md#users) koleksiyonu yerine.                                                                                                                                                                                                                                                                                                      |
|    Mdmdeviceınventoryhistories         |    Kaldırılır    |    Özelliklerin birçoğu yedekli veya bulunan artık olabilir [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) veya [cihazları](intune-data-warehouse-collections.md#devices) koleksiyonları. Tüm **Mdmdeviceınventoryhistories** henüz bu iki koleksiyonlarla listelenen özellikleri artık mevcut olmayan. Ayrıntılar için aşağıya bakın.    |

Aşağıdaki tabloda önceden bulunan eski özellik **Mdmdeviceınventoryhistories** toplama ve değişiklik/değiştirme:

|    Eski özelliği                |    Değişiklik/değiştirme                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    CellularTechnology          |    cihaz koleksiyonundaki cellularTechnology                                     |
|    Deviceclientıd              |    cihaz koleksiyonundaki cihaz kimliği                                               |
|    deviceManufacturer          |    cihaz koleksiyonundaki üreticisi                                           |
|    deviceModel                 |    cihaz koleksiyonuna modeli                                                  |
|    DeviceName                  |    cihaz koleksiyonundaki deviceName                                             |
|    deviceOsPlatform            |    cihaz koleksiyonundaki deviceTypeKey                                          |
|    deviceOsVersion             |    osVersion devicePropertyHistories koleksiyondaki                              |
|    deviceType                  |    cihaz koleksiyonundaki deviceTypes koleksiyona başvuran deviceTypeKey    |
|    EncryptionState             |    cihaz koleksiyonuna encryptionState özelliği                           |
|    ExchangeActiveSyncId        |    cihaz koleksiyonuna easDeviceId özelliği                               |
|    exchangeDeviceId            |    cihaz koleksiyonundaki easDeviceId                                            |
|    imei                        |    ımeı cihazları koleksiyondaki                                                   |
|    isSupervised                |    cihaz koleksiyonuna isSupervised özelliği                              |
|    jailBroken                  |    jailbreak uygulanmış devicePropertyHistories koleksiyondaki                             |
|    meid                        |    cihaz koleksiyonuna meıd özelliği                                      |
|    OEM                         |    cihaz koleksiyonundaki üreticisi                                           |
|    osName                      |    cihaz koleksiyonundaki deviceTypes koleksiyona başvuran deviceTypeKey    |
|    Telefon numarası                 |    koleksiyondaki cihazları telefon numarası                                            |
|    PlatformType                |    cihaz koleksiyonuna modeli                                                  |
|    Ürün                     |    cihaz koleksiyonundaki deviceTypeKey                                          |
|    ProductVersion              |    osVersion devicePropertyHistories koleksiyondaki                              |
|    serialNumber                |    koleksiyondaki cihazları seri numarası                                           |
|    StorageFree                 |    cihaz koleksiyonuna freeStorageSpaceInBytes özelliği                   |
|    StorageTotal                |    cihaz koleksiyonuna totalStorageSpaceInBytes özelliği                |
|    SubscriberCarrierNetwork    |    cihaz koleksiyonuna subscriberCarrier özelliği                         |
|    wifimac                     |    cihaz koleksiyonundaki wiFiMacAddress                                         |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) koleksiyonu: 

|    Eski özelliği                  |    Değişiklik/değiştirme                                               |
|----------------------------------|---------------------------------------------------------------------|
|    CategoryID                    |    deviceCategories koleksiyona başvuran deviceCategoryKey,       |
|    CertExpirationDate            |    Kaldırılır                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    CreatedDate                   |    cihaz koleksiyonundaki enrolledDateTime                           |
|    DeviceTypeKey                 |    cihaz koleksiyonundaki deviceTypeKey                              |
|    EasID                         |    cihaz koleksiyonundaki easDeviceId                                |
|    EnrolledByUser                |    cihaz koleksiyonundaki UserID                                     |
|    EnrollmentTypeKey             |    cihaz koleksiyonundaki deviceEnrollmentTypeKey                    |
|    GraphDeviceIsCompliant        |    Kaldırılır                                                          |
|    GraphDeviceIsManaged          |    Kaldırılır                                                          |
|    LastContact                   |    cihaz koleksiyonundaki lastSyncDateTime                           |
|    LastContactNotification       |    Kaldırılır                                                          |
|    lastContactWorkplaceJoin      |    Kaldırılır                                                          |
|    lastExchangeStatusUtc         |    Kaldırılır                                                          |
|    lastModifiedDateTimeUTC       |    Kaldırılır                                                          |
|    lastPolicyUpdateUtc           |    Kaldırılır                                                          |
|    ManagementAgentKey            |    managementStateKey                                               |
|    üretici                  |    cihaz koleksiyonundaki üreticisi                               |
|    MdmStatusKey                  |    complianceStates koleksiyona başvuran complianceStateKey,    |
|    model                         |    cihaz koleksiyonuna modeli                                      |
|    osFamily                      |    cihaz koleksiyonundaki operatingSystem                            |
|    osRevisionNumber              |    cihaz koleksiyonundaki osVersion                                  |
|    ProcessorArchitecture         |    Kaldırılır                                                          |
|    Başvuru Kimliği                   |    cihaz koleksiyonundaki azureAdDeviceId                            |
|    serialNumber                  |    koleksiyondaki cihazları seri numarası                               |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [cihazları](intune-data-warehouse-collections.md#devices) koleksiyonu: 

|    Eski özelliği                  |    Değişiklik/değiştirme                                               |
|----------------------------------|---------------------------------------------------------------------|
|    CategoryID                    |    deviceCategories koleksiyona başvuran deviceCategoryKey,       |
|    CertExpirationDate            |    Kaldırılır                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    CreatedDate                   |    EnrolledDateTime                                                 |
|    easId                         |    easDeviceId                                                      |
|    EnrolledByUser                |    userId                                                           |
|    EnrollmentTypeKey             |    deviceEnrollmentTypeKey                                          |
|    GraphDeviceIsCompliant        |    Kaldırılır                                                          |
|    GraphDeviceIsManaged          |    Kaldırılır                                                          |
|    LastContact                   |    lastSyncDateTime                                                 |
|    LastContactNotification       |    Kaldırılır                                                          |
|    lastContactWorkplaceJoin      |    Kaldırılır                                                          |
|    lastExchangeStatusUtc         |    Kaldırılır                                                          |
|    lastPolicyUpdateUtc           |    Kaldırılır                                                          |
|    MdmStatusKey                  |    complianceStates koleksiyona başvuran complianceStateKey,    |
|    osFamily                      |    operatingSystem                                                  |
|    ProcessorArchitecture         |    Kaldırılır                                                          |
|    Başvuru Kimliği                   |    azureAdDeviceId                                                  |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities) koleksiyonu: 

|    Eski özelliği         |    Değişiklik/değiştirme         |
|-------------------------|-------------------------------|
|    EnrollmentTypeKey    |    deviceEnrollmentTypeKey    |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [mamApplications](intune-data-warehouse-collections.md#mamapplications) koleksiyonu: 

|    Eski özelliği       |    Değişiklik/değiştirme    |
|-----------------------|--------------------------|
|    Tanıtıcı, ApplicationKey     |    mamApplicationKey     |
|    ApplicationName    |    mamApplicationName    |
|    ApplicationId      |    mamApplicationId      |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [mamApplicationInstances](intune-data-warehouse-collections.md#mamapplicationinstances) koleksiyonu: 

|    Eski özelliği     |    Değişiklik/değiştirme    |
|---------------------|--------------------------|
|    ApplicationId    |    mamApplicationId      |
|    deviceId         |    mamDeviceId           |
|    deviceType       |    mamDeviceType         |
|    DeviceName       |    mamDeviceName         |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [mamCheckins](intune-data-warehouse-collections.md#mamcheckins) koleksiyonu: 

|    Eski özelliği      |    Değişiklik/değiştirme    |
|----------------------|--------------------------|
|    Tanıtıcı, ApplicationKey    |    mamApplicationKey     |

Aşağıdaki tabloda bulunan özelliklerde yapılan değişiklikler [kullanıcılar](intune-data-warehouse-collections.md#users) koleksiyonu: 

|    Eski özelliği             |    Değişiklik/değiştirme    |
|-----------------------------|--------------------------|
|    StartDateInclusiveUtc    |    Kaldırılır               |
|    endDateInclusiveUtc      |    Kaldırılır               |
|    IsCurrent                |    Kaldırılır               |

## <a name="1903"></a>1903
_Mart 2019 yayımlanan_

### <a name="v10-changes-reflecting-back-to-beta"></a>Beta sürümünden yansıtan V1.0 değişiklikleri
V1.0, ilk olarak 1808 içinde sunulmuştur, önemli bazı açılardan'ı Beta'dan API farklıydı. 1903 bu değişiklikleri geri beta API sürümüne yansıtılır. Beta API sürümünü kullanan önemli raporlarınız varsa, bu raporları önemli değişiklikler önlemek için V1.0 geçiş kesinlikle öneririz. Lütfen [API sürüm bilgisi](reports-api-url.md) daha fazla bilgi veri ambarı API sürümleri ve geriye dönük uyumluluk. 

## <a name="1902"></a>1902 
_Şubat 2019 yayımlanan_

### <a name="power-bi-compliance-app"></a>Power BI uyumluluk uygulaması 

Power BI çevrimiçi kullanarak Intune veri ambarı'nızı erişim [Intune uyumluluk (veri ambarı)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) uygulama. Bu Power BI uygulaması ile artık erişmek ve herhangi bir kurulum yapmadan ve web tarayıcınızı çıkmadan önceden oluşturulmuş raporları paylaşabilirsiniz. 

> [!NOTE]
> Intune uyumluluk uygulamaya uygulayabilirsiniz iki ek filtreler vardır.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Intune uyumluluk uygulamaya ek filtreler ekleyin
1. Açık [Intune uyumluluk (veri ambarı)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) , web tarayıcıları uygulamasında.
2. Tıklayın **uyumlu olmayan cihazları** seçip **uyumlu** içinde **complianceStatus** filtre. 
3. Tıklayarak **bilinmeyen cihazlar** seçip **henüz** içinde **complianceStatus** filtre. 

## <a name="1812"></a>1812 
_Aralık 2018'de yayınlanan_

### <a name="enrollment-activities-collection-released-to-v10"></a>V1.0 için yayımlanan kayıt etkinlikler koleksiyonu 

Kayıt etkinliklerini koleksiyon v1.0 kullanıma sunulmuştur. Bu koleksiyon, ortamınızda kayıt hatası birim ve eğilimleri anlamak için kullanabilirsiniz. Daha fazla bilgi için [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories), ve [ enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons).

## <a name="1808"></a>1808
_Yayınlanma tarihi: Ağustos 2018_

### <a name="v10-collections"></a>v1.0 Koleksiyonlar  

Artık `api-version=v1.0` sorgu parametresini ayarlayarak Intune Veri Ambarı’nın v1.0 sürümünü kullanabilirsiniz. Veri Ambarı’ndaki koleksiyonlara yapılan güncelleştirmeler ek olarak yapılır, yani mevcut senaryoları bozmaz.

### <a name="enrollment-activities-collection-released-to-beta"></a>Beta için yayımlanan kayıt etkinlikler koleksiyonu

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

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>İçinde veri ambarı veri modelinde yeni varlıklar <!-- 2077804 -->

 - [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md) varlığı eklendi. **MobileAppDeviceUserInstallStatus** belirli bir cihaz ve kullanıcı için mobil uygulama yükleme durumunu gösterir.
 - [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate) varlığı eklendi. **MobileAppInstallState** varlığı, bir mobil uygulamanın cihazlar, kullanıcılar veya her ikisini de içeren bir gruba atandıktan sonra yükleme durumunu gösterir. 

## <a name="1710"></a>1710
_Yayımlanma tarihi: Kasım 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Geçerli kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin kullanıcı verisi ile sınırlıdır <!-- 1544273 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, verilerde kullanıcı ve durumu bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmamış olan kullanıcıları içerir. **Geçerli kullanıcı** varlık koleksiyonu yalnızca etkin kullanıcıları içerir. **Geçerli Kullanıcı** öğesi hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Yayınlanma tarihi: Ekim 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Eklenen Intune veri ambarı veri modeline kullanıcı cihaz ilişkisi varlık koleksiyonu <!-- 1187917 -->

Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz. OData uç noktası veya özel bir istemci geliştirme yoluyla Veri Ambarı Intune sayfasından alınan Power BI dosyasından (PBIX) veri modeline erişebilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı Cihaz İlişkisi](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>İçinde veri ambarı veri modelinde yeni varlıklar <!-- 1479526 --><!-- -->

 - [**UserDeviceAssociation**](reports-ref-user-device.md) varlığı eklendi. **UserDeviceAssociation**, kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir. Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz.  
 - [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) varlığı eklendi. **IntuneManagementExtension**, mobil cihazlar için sürüm veya yükleme durumu gibi bilgileri izleyen varlıklar barındırır.

## <a name="next-steps"></a>Sonraki adımlar
 - [Intune’daki haftalık yenilikleri](whats-new.md) öğrenin. Yaklaşan değişiklikler, hizmet hakkında önemli bildirimler ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.
 - [Microsoft Intune Blogu](https://go.microsoft.com/fwlink/?LinkID=273882)’nu okuyun.
