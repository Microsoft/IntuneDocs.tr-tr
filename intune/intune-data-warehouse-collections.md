---
title: Intune Veri Ambarı Koleksiyonları
titlesuffix: Microsoft Intune
description: Intune Veri Ambarı koleksiyonları, Veri Ambarı API’siyle ilgili ayrıntılar sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/11/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 29f09230-dc56-43db-b599-d961967bda49
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: a2a832e773a1a2fb413bfbc761d93988f2230ec7
ms.sourcegitcommit: 01d6832978cb7ca23049000950696b300a87abd4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55761084"
---
#  <a name="intune-data-warehouse-collections"></a>Intune Veri Ambarı Koleksiyonları

Aşağıdaki Intune Veri Ambarı koleksiyonları, Veri Ambarı API’si varlıklarının v1.0 koleksiyonlarının özellikleri, açıklamaları ve örneklerini sağlar. 

## <a name="apprevisions"></a>appRevisions
**appRevision** varlığı, uygulamaların tüm sürümlerini listeler.

|          Özellik          |                                      Açıklama                                      |                Örnek               |
|:--------------------------:|:-------------------------------------------------------------------------------------:|:------------------------------------:|
| AppKey                     | Uygulamanın benzersiz tanımlayıcısı.                                                         | 123                                  |
| ApplicationId              | Uygulamanın benzersiz tanımlayıcısı - AppKey’e benzerdir ancak doğal bir anahtardır.        | b66bc706-ffff-7437-0340-032819502773 |
| Gözden geçirme                   | İkili dosya karşıya yüklenirken yönetici tarafından bahsedilen sürüm.                   | 2                                    |
| Başlık                      | Uygulama başlığı.                                                                     | Excel                                |
| Yayımcı                  | Uygulama yayımcısı.                                                                 | Microsoft                            |
| UploadState                | Uygulamanın karşıya yüklenme durumu.                                                              | 1.                                    |
| AppTypeKey                 | Aşağıdaki bölümde açıklanan AppType özelliğine başvuru.                            | 1.                                    |
| VppProgramTypeKey          | Aşağıda açıklanan VppProgramType özelliğine başvuru.                                        | 30876                                |
| CreationTime               | Düzeltmenin oluşturulduğu saat.                                            | 23.11.2016 0:00                      |
| ModifiedTime               | Bu düzeltmeyle ilgili herhangi bir şeyin en son değiştirildiği an.                            | 23.11.2016 0:00                      |
| Boyut                       | İkili dosyanın bayt cinsinden boyutu.                                                          | 120.392.000                          |
| StartDateInclusiveUTC      | Bu uygulama düzeltmesinin veri ambarında oluşturulma tarihi ve saati (UTC).      | 23.11.2016 0:00                      |
| EndDateExclusiveUTC        | Bu uygulama düzeltmesinin kullanımdan kalkma tarihi ve saati (UTC).                        | 23.11.2016 0:00                      |
| IsCurrent                  | Uygulama sürümünün veri ambarında mevcut olup olmadığını gösterir.         | True/False                           |
| RowLastModifiedDateTimeUTC | Bu uygulama sürümünün veri ambarında son değiştirilme tarihi ve saati (UTC). | 23.11.2016 0:00                      |

## <a name="apptypes"></a>appTypes
**appTypes** varlığı, bir uygulamanın yükleme kaynağını listeler.

|   Özellik  |        Açıklama        |
|:-----------:|:-------------------------:|
| AppTypeID   | Tür kimliği           |
| AppTypeKey  | Anahtar için yedek anahtar |
| AppTypeName | Uygulama türü                  |

### <a name="example"></a>Örnek

| AppTypeID |                Ad               |                     Açıklama                     |
|:---------:|:---------------------------------:|:---------------------------------------------------:|
| 0         | Android mağazası uygulaması               | Bir Android mağazası uygulaması.                             |
| 1.         | Android LOB uygulaması                 | Bir Android iş kolu uygulaması.                  |
| 2         | Yönetilen Android mağazası uygulaması (MAM) | Yönetimi etkin bir Android mağazası uygulaması. |
| 3         | iOS mağazası uygulaması                   | Bir iOS mağazası uygulaması.                                 |
| 4         | iOS LOB uygulaması                     | Bir iOS iş kolu uygulaması.                      |
| 5         | Yönetilen iOS mağazası uygulaması (MAM)     | Yönetimi etkin bir iOS mağazası uygulaması.       |
| 6         | O365 Pro Plus Suite             | Windows 10 için Office 365 Pro Plus Suite.     |
| 7         | Web uygulaması                         | Bir web uygulaması.                                        |
| 8         | Windows Phone 8.1 mağazası uygulaması     | Bir Windows Phone 8.1 mağazası uygulaması.                    |
| 9         | Windows mağazası uygulaması               | Bir Windows mağazası uygulaması.                              |
| 10        | Windows LOB uygulaması                | Bir Windows AppX iş kolu uygulaması.              |
| 11        | Windows Mobile MSI              | Bir MSI iş kolu uygulaması.                      |
| 12        | Windows Phone LOB uygulaması           | Bir Windows Phone iş kolu uygulaması.             |

## <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities
Aşağıdaki tablo, uyumluluk ilkelerinin cihazlara atanma durumunu özetler. Ve her bir uyumluluk durumunda bulunan cihaz sayısını listeler.

|    Özellik   |                                                                                      Açıklama                                                                                     |  Örnek |
|:-------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey       | Uyumluluk ilkesi için özet oluşturulduğu ana ait tarih anahtarı.                                                                                                                   | 20161204 |
| Bilinmiyor       | Çevrimdışı olan veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramayan cihaz sayısı.                                                                           | 5        |
| NotApplicable | Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin uygulanabilir olmadığı cihaz sayısı.                                                                                     | 201      |
| Uyumlu     | Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesini başarıyla uygulayan cihaz sayısı.                                                                        | 4083     |
| YetkisizKullanımSüresinde | Uyumlu olmayan ancak yönetici tarafından belirlenen yetkisiz kullanım süresinde olan cihaz sayısı.                                                                                  | 57       |
| Uyumsuz  | Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamayan veya kullanıcısı yönetici tarafından hedeflenen ilkeler ile uyum sağlayamayan cihaz sayısı. | 43       |
|    Hata      |    Intune veya Azure AD ile iletişim kuramayan ve hata iletisi döndüren cihaz sayısı.                                                                          |    3     |

## <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities
Aşağıdaki tablo, uyumluluk ilkelerinin cihazlara atanma durumunu ilke başına ve ilke türü başına olacak şekilde özetler. Ve her atanmış uyumluluk ilkesi için her bir uyumluluk durumunda bulunan cihaz sayısını listeler.

|      Özellik     |                                                                                      Açıklama                                                                                     |  Örnek |
|:-----------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey           | Uyumluluk ilkesi için özet oluşturulduğu ana ait tarih anahtarı.                                                                                                                   | 20161219 |
| PolicyKey         | Özetin oluşturulduğu uyumluluk ilkesi için anahtar.                                                                                                                   | 10178    |
| PolicyPlatformKey | Özetin oluşturulduğu uyumluluk ilkesinin platform türü için anahtar.                                                                                            | 5        |
| Bilinmiyor           | Çevrimdışı olan veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramayan cihaz sayısı.                                                                           | 13       |
| NotApplicable     | Yönetici tarafından hedeflenen cihaz uyumluluk ilkelerinin uygulanabilir olmadığı cihaz sayısı.                                                                                     | 3        |
| Uyumlu         | Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesini başarıyla uygulayan cihaz sayısı.                                                                        | 45       |
| YetkisizKullanımSüresinde     | Uyumlu olmayan ancak yönetici tarafından belirlenen yetkisiz kullanım süresinde olan cihaz sayısı.                                                                                  | 3        |
| Uyumsuz      | Yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamayan veya kullanıcısı yönetici tarafından hedeflenen ilkeler ile uyum sağlayamayan cihaz sayısı. | 7        |
| Hata             | Intune veya Azure AD ile iletişim kuramayan ve hata iletisi döndüren cihaz sayısı.                                                                             | 3        |
## <a name="compliancestates"></a>complianceStates

|      Özellik      |                       Açıklama                      |
|:------------------:|:------------------------------------------------------:|
| complianceStatus   | mdmStatusKey sahibi cihazların uyumluluk durumu       |
| complianceStateKey | Cihaz ve uyumluluk durumuyla eşleşen uyumluluk anahtarı |
| complianceStateID  | Bu uyumluluk durumuyla eşleşen kimlik                |

### <a name="example"></a>Örnek

|  complianceStatus  |                       Açıklama                      |
|:------------------:|:------------------------------------------------------:|
|    Bilinmiyor         |    Bilinmiyor.                                                                        |
|    Uyumlu       |    Uyumlu.                                                                      |
|    Uyumsuz    |       Cihazın durumu uyumsuz ve şirket kaynaklarına erişimi engelli.             |
|    Çakışma        |    Diğer kurallarla çakışıyor.                                                      |
|    Hata           |       Hata.                                                                       |
|    ConfigManager   |    Yapılandırma Yöneticisi tarafından yönetiliyor.                                                      |
|    YetkisizKullanımSüresinde   |       Cihazın durumu uyumsuz ancak yine de şirket kaynaklarına erişimi var          |

## <a name="dates"></a>tarihler
**Date** varlığı, birden çok veri ambarı varlığında başvurulan tarihleri temsil eder.

|     Özellik    |                       Açıklama                      |    Örnek    |
|:---------------:|:------------------------------------------------------:|:-------------:|
| DateKey         | Veri ambarında bu tarihin benzersiz tanımlayıcısı. | 20160703      |
| FullDate        | Bu tarihin tam Tarih/Saat biçiminde temsili.        | 3.7.2016 0:00 |
| DayOfWeek       | Haftanın kaçıncı günü olduğu                                            | 1.             |
| DayOfMonth      | Ayın kaçıncı günü olduğu                                           | 3             |
| DayOfYear       | Yılın kaçıncı günü olduğu                                            | 185           |
| WeekOfYear      | Yılın kaçıncı haftası olduğu                                           | 28            |
| MonthOfYear     | Yılın kaçıncı ayı olduğu                                      | 7             |
| CalendarQuarter | Takvim çeyreği                                       | 3             |
| CalendarYear    | Takvim yılı                                          | 2016          |
| DateKey         | Veri ambarında bu tarihin benzersiz tanımlayıcısı. | 20160703      |
| FullDate        | Bu tarihin tam Tarih/Saat biçiminde temsili.        | 3.7.2016 0:00 |
| DayOfWeek       | Haftanın kaçıncı günü olduğu                                            | 1.             |
| DayOfMonth      | Ayın kaçıncı günü olduğu                                           | 3             |
| DayOfYear       | Yılın kaçıncı günü olduğu                                            | 185           |
| WeekOfYear      | Yılın kaçıncı haftası olduğu                                           | 28            |
| MonthOfYear     | Yılın kaçıncı ayı olduğu                                      | 7             |
| CalendarQuarter | Takvim çeyreği                                       | 3             |
| CalendarYear    | Takvim yılı                                          | 2016          |

## <a name="devicecategories"></a>deviceCategories

|      Özellik      |                                    Açıklama                                   |                Örnek               |
|:------------------:|:--------------------------------------------------------------------------------:|:------------------------------------:|
| deviceCategoryID   | Cihaz kategorisi için benzersiz tanımlayıcı.                                       | fb415ba2-7c08-41f6-a5e5-685b50da2c4c |
| deviceCategoryKey  | Veri ambarındaki cihaz kategorisinin benzersiz tanımlayıcısı - vekil anahtar | 1.                                    |
| deviceCategoryName | Cihaz kategorisi için görünen ad.                                            | Smartphones                          |

## <a name="deviceconfigurationprofiledeviceactivities"></a>deviceConfigurationProfileDeviceActivities
**DeviceConfigurationProfileDeviceActivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir cihaz kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Cihaza biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa varlık, başarılı sayacını artırır ve cihazı hata durumuna geçirir. Varlık, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

|  Özellik |                                          Açıklama                                          |  Örnek |
|:---------:|:---------------------------------------------------------------------------------------------:|:--------:|
| DateKey   | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. | 20160703 |
| Bekleniyor   | Bekleme durumundaki benzersiz cihazların sayısı.                                                    | 123      |
| Başarılı | Başarı durumundaki benzersiz cihazların sayısı.                                                    | 12       |
| Hata     | Hata durumundaki benzersiz cihazların sayısı.                                                      | 10       |
| Başarısız    | Başarısız durumundaki benzersiz cihazların sayısı.                                                     | 2        |

## <a name="deviceconfigurationprofileuseractivities"></a>deviceConfigurationProfileUserActivities 
**DeviceConfigurationProfileUserActivity** varlığı; başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısını listeler. Bu sayı, varlığa atanmış Cihaz Yapılandırma Profillerini gösterir. Örneğin, bir kullanıcı kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcı hata durumunda olarak değerlendirilir. **DeviceConfigurationProfileUserActivity** varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler. 

| Özellik  | Açıklama  | Örnek  |
|------------|----------------------------------------------------------------------------------------------|-----------|
| DateKey  | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı.  | 20160703  |
| Bekleniyor  | Bekleme durumundaki benzersiz kullanıcıların sayısı.  | 123  |
| Başarılı  | Başarı durumundaki benzersiz kullanıcıların sayısı.  | 12  |
| Hata  | Hata durumundaki benzersiz kullanıcıların sayısı.  | 10  |
| Başarısız  | Başarısız durumundaki benzersiz kullanıcıların sayısı.  | 2  |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

|          Özellik          |                                                                                      Açıklama                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | Günü gösteren tarih tablosuna başvuru.                                                                                                                                          |
| DeviceKey                  | Veri ambarındaki cihazın benzersiz tanımlayıcısı - vekil anahtar. Bu, Intune cihaz kimliğini barındıran Cihaz tablosuna bir başvurudur.                               |
| DeviceName                 | Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılamaz. |
| DeviceRegistrationStateKey | Bu cihazın cihaz kayıt durumu özniteliğinin anahtarı.                                                                                                                    |
| OwnerTypeKey               | Cihazın sahip türü özniteliğinin anahtarı: şirket, kişisel veya bilinmeyen.                                                                                                  |
| ManagementStateKey         | Cihazla ilişkili yönetim durumunun anahtarı, bir uzak eylemin en son durumunu veya cihazda jailbreak yapılıp yapılmamış ya da kök erişim izni verilip verilmemiş olduğunu gösterir.                                                |
| AzureADRegistered          | Bu cihazın Azure Active Directory’ye kayıtlı olup olmadığını gösterir.                                                                                                                             |
| ComplianceStateKey         | Bir ComplianceState anahtarı.                                                                                                                                                            |
| OSVersion                  | İşletim sistemi sürümü.                                                                                                                                                                          |
| JailBroken                 | Cihazda jailbreak yapılıp yapılmadığı veya kök erişim izni verilip verilmediğini gösterir.                                                                                                                                         |
| DeviceCategoryKey          | Bu cihaz için cihaz kategorisi özniteliğinin anahtarı.                                                                                                                                    |
## <a name="deviceregistrationstates"></a>deviceRegistrationStates
**DeviceRegistrationState** varlığı, diğer veri ambarı koleksiyonları tarafından başvurulan kayıt türünü temsil eder. 

|           Özellik          |                                     Açıklama                                     |
|:---------------------------:|:-----------------------------------------------------------------------------------:|
| deviceRegistrationStateID   | Kayıt durumu için benzersiz tanımlayıcı                                            |
| deviceRegistrationStateKey  | Veri ambarındaki kayıt durumunun benzersiz tanımlayıcısı - vekil anahtar |
| deviceRegistrationStateName | Kayıt durumu                                                                  |
|    NotRegistered                     |    NotRegistered                                                                                                                                                                  |
|    Kaydedildi                        |       Kaydedildi                                                                                                                                                                   |
|    İptal Edildi                           |       Durum, BT yöneticisinin istemciyi engellediği anlamına gelir ve istemcinin engeli kaldırılabilir. Bir cihaz ayrıca, silindikten veya devre dışı bırakıldıktan sonra İptal Edildi durumunda olabilir.        |
|    KeyConflict                       |    Anahtar Çakışması                                                                                                                                                                    |
|    ApprovalPending                   |    Onay Bekleniyor                                                                                                                                                                |
|    CertificateReset                  |    Sertifikayı sıfırla                                                                                                                                                               |
|    NotRegisteredPendingEnrollment    |    Kaydedilmedi kayıt bekleniyor                                                                                                                                               |
|    Bilinmiyor                           |    Bilinmeyen durum                                                                                                                                                                   |

## <a name="devices"></a>devices
**Device** varlığı, yönetime kaydedilen tüm cihazları ve bunlara karşılık gelen özellikleri listeler.

|          Özellik          |                                                                                       Açıklama                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | Veri ambarındaki cihazın benzersiz tanımlayıcısı - vekil anahtar.                                                                                                               |
| DeviceId                   | Cihazın benzersiz tanımlayıcısı.                                                                                                                                                     |
| DeviceName                 | Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Diğer platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılamaz. |
| DeviceTypeKey              | Bu cihazın cihaz türü özniteliğinin anahtarı.                                                                                                                                    |
| DeviceRegistrationState    | Bu cihazın istemci kayıt durumu özniteliğinin anahtarı.                                                                                                                      |
| OwnerTypeKey               | Cihaz için sahip türü özniteliğinin anahtarı: şirket, kişisel veya bilinmeyen.                                                                                                    |
| EnrolledDateTime           | Bu cihazın kaydedildiği tarih ve saat.                                                                                                                                         |
| LastSyncDateTime           | Cihazın bilinen son Intune iadesi.                                                                                                                                              |
| ManagementAgentKey         | Bu cihazla ilişkili yönetim aracısının anahtarı.                                                                                                                             |
| ManagementStateKey         | Cihazla ilişkili yönetim durumunun anahtarı, bir uzak eylemin en son durumunu veya cihazda jailbreak yapılıp yapılmamış ya da kök erişim izni verilip verilmemiş olduğunu gösterir.                                                |
| AzureADDeviceId            | Bu cihazın Azure cihaz kimliği.                                                                                                                                                  |
| AzureADRegistered          | Bu cihazın Azure Active Directory’ye kayıtlı olup olmadığını gösterir.                                                                                                                             |
| DeviceCategoryKey          | Cihazla ilişkili kategorinin anahtarı.                                                                                                                                     |
| DeviceEnrollmentType       | Bu cihazla ilişkili kayıt türünün anahtarı, kayıt yöntemini gösterir.                                                                                             |
| ComplianceStateKey         | Cihazla ilişkili Uyumluluk durumu anahtarı.                                                                                                                             |
| OSVersion                  | Cihazın işletim sistemi sürümü.                                                                                                                                                |
| EasDeviceId                | Cihazın Exchange ActiveSync kimliği.                                                                                                                                                  |
| seri numarası               | seri numarası                                                                                                                                                                           |
| UserId                     | Cihazla ilişkili kullanıcının Benzersiz Tanımlayıcısı.                                                                                                                           |
| RowLastModifiedDateTimeUTC | Bu cihazın veri ambarında son değiştirilme tarihi ve saati (UTC).                                                                                                       |
| Üretici               | Cihazın üreticisi                                                                                                                                                             |
| Model                      | Cihazın modeli                                                                                                                                                                    |
| OperatingSystem            | Cihazın işletim sistemi. Windows, iOS vb.                                                                                                                                   |
| IsDeleted                  | Bu cihazın silinip silinmediğini gösteren ikili dosya.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Android güvenlik düzeltme eki düzeyi                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Cihaz denetimli durumu                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Bayt Cinsinden Boş Depolama Alanı.                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Bayt Cinsinden Toplam Depolama Alanı.                                                                                                                                                                |
| EncryptionState            | Cihazdaki şifreleme durumu.                                                                                                                                                      |
| SubscriberCarrier          | Cihazın abone taşıyıcısı                                                                                                                                                       |
| PhoneNumber                | Cihazın telefon numarası                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| CellularTechnology         | Cihazın hücresel teknolojisi                                                                                                                                                    |
| WiFiMacAddress             | Wi-Fi MAC                                                                                                                                                                              |


## <a name="devicetypes"></a>deviceTypes
**deviceType** varlığı, diğer veri ambarı varlıkları tarafından başvurulan cihaz türünü temsil eder. Cihaz türü genellikle cihaz modelini, üreticisini veya her ikisini de belirtir.

|    Özellik    |                                  Açıklama                                 |
|:--------------:|:----------------------------------------------------------------------------:|
| DeviceTypeID   | Cihaz türünün benzersiz tanımlayıcısı                                       |
| DeviceTypeKey  | Veri ambarındaki cihaz türünün benzersiz tanımlayıcısı - vekil anahtar |
| DeviceTypeName | Cihaz türü                                                                |

### <a name="example"></a>Örnek

| deviceTypeID |        Name       |                      Açıklama                      |
|:------------:|:-----------------:|:-----------------------------------------------------:|
| -1           | Kullanılamıyor   | Cihaz türü kullanılamıyor.                     |
| 0            | Masaüstü           | Windows Masaüstü cihaz                              |
| 1.            | Windows           | Windows cihaz                                      |
| 2            | WinMO6            | Windows Mobile 6.0 cihaz                           |
| 3            | Nokia             | Nokia cihaz                                        |
| 4            | WindowsPhone      | Windows Phone cihaz                                |
| 5            | Mac               | Mac cihaz                                          |
| 6            | WinCE             | Windows CE cihaz                                   |
| 7            | WinEmbedded       | Windows Embedded cihaz                             |
| 8            | IPhone            | iPhone cihaz                                       |
| 9            | IPad              | iPad cihaz                                         |
| 10           | IPod              | iPod cihaz                                         |
| 11           | Android           | Cihaz Yöneticisi ile yönetilen Android cihaz   |
| 12           | ISocConsumer      | iSoc Consumer cihaz                                |
| 13           | Unix              | Unix cihaz                                         |
| 14           | MacMDM            | Yerleşik MDM aracısıyla yönetilen Mac OS X cihaz |
| 15           | HoloLens          | Holo Lens cihaz                                    |
| 16           | SurfaceHub        | Surface Hub cihaz                                  |
| 17           | AndroidForWork    | Android cihaz - Android Profil Sahibi kullanılarak yönetiliyor  |
| 18           | AndroidEnterprise | Android kurumsal cihaz.                          |
| 100          | Blackberry        | Blackberry Cihaz                                   |
| 101          | Palm              | Palm cihaz                                         |
| 255          | Bilinmiyor           | Bilinmeyen cihaz türü                                 |

## <a name="deviceenrollmenttypes"></a>deviceEnrollmentTypes
**deviceEnrollmentType** varlığı, bir cihazın nasıl kaydedildiğini gösterir. Kayıt türü, kayıt yöntemini yakalar. Örnekler, farklı kayıt türlerini ve bunların ne anlama geldiğini listeler.

|         Özellik         |                                    Açıklama                                    |
|:------------------------:|:---------------------------------------------------------------------------------:|
| deviceEnrollmentTypeID   | Kayıt türünün benzersiz tanımlayıcısı.                                       |
| deviceEnrollmentTypeKey  | Veri ambarındaki kayıt türünün benzersiz tanımlayıcısı - vekil anahtar. |
| deviceEnrollmentTypeName | Kayıt türü adı.                                                           |

### <a name="example"></a>Örnek

| enrollmentTypeID |                Name                |                                        Açıklama                                       |
|:----------------:|:----------------------------------:|:----------------------------------------------------------------------------------------:|
| 0                | Bilinmiyor                            | Kayıt türü toplanmadı                                                      |
| 1.                | UserEnrollment                     | KCG kanalı üzerinden kullanıcı yoluyla kayıt.                                           |
| 2                | DeviceEnrollmentManager            | Cihaz kayıt yöneticisi hesabıyla kullanıcı kaydı.                              |
| 3                | AppleBulkWithUser                  | Kullanıcı sınaması ile Apple toplu kaydı. (DEP, Apple Configurator)                   |
| 4                | AppleBulkWithoutUser               | Kullanıcı sınaması olmadan Apple toplu kaydı.   (DEP, Apple Configurator, Mobil Yapılandırma) |
| 5                | WindowsAzureADJoin                 | Windows 10 Azure AD Katılımı.                                                                |
| 6                | WindowsBulkUserless                | Sertifika ile ICD yoluyla Windows 10 Toplu kaydı.                               |
| 7                | WindowsAutoEnrollment              | Windows 10 otomatik kayıt.   (İş hesabı ekleyin)                                    |
| 8                | WindowsBulkAzureDomainJoin         | Windows 10 toplu Azure AD Katılımı.                                                           |
| 9                | WindowsCoManagement                | AutoPilot veya Grup İlkesi tarafından tetiklenen Windows 10 Ortak Yönetimi.                       |
| 10               | WindowsAzureADJoinsUsingDeviceAuth | Cihaz Kimlik Doğrulaması yoluyla Windows 10 Azure AD Katılımı.                                            |

## <a name="enrollmentactivities"></a>enrollmentActivities 
**EnrollmentActivity** varlığı, cihaz kaydı etkinliğini gösterir.

| Özellik                      | Açıklama                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Bu kayıt etkinlik zaman kaydedildiği tarihin anahtarı.               |
| deviceEnrollmentTypeKey       | Kayıt türünün anahtarı.                                        |
| DeviceTypeKey                 | Cihaz türünün anahtarı.                                                |
| enrollmentEventStatusKey      | Başarı veya başarısızlık kayıt gösteren durum anahtarı.    |
| enrollmentFailureCategoryKey  | Anahtar (kayıt başarısız olursa) kayıt hata kategorisi.        |
| enrollmentFailureReasonKey    | (Kayıt başarısız olursa) kayıt hatanın nedenini anahtarı.          |
| osVersion                     | Cihazın işletim sistemi sürümü.                               |
| count                         | Kayıt etkinliklerini yukarıdaki sınıflandırmaları eşleşen toplam sayısı.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
**EnrollmentEventStatus** varlığı, cihaz kaydı sonucunu gösterir.

| Özellik                   | Açıklama                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| enrollmentEventStatusKey   | (Yedek anahtar) veri ambarındaki kayıt durumunun benzersiz tanımlayıcısı  |
| enrollmentEventStatusName  | Kayıt durumu adı. Aşağıdaki örneklere bakın.                            |

### <a name="example"></a>Örnek

| enrollmentEventStatusName  | Açıklama                            |
|----------------------------|----------------------------------------|
| Başarılı                    | Başarılı cihaz kaydı         |
| Başarısız                     | Başarısız cihaz kaydı             |
| Kullanılamıyor              | Kayıt durumu kullanılamıyor.  |

## <a name="enrollmentfailurecategories"></a>enrollmentFailureCategories 
**EnrollmentFailureCategory** varlığı gösteren neden bir cihaz kaydı başarısız oldu. 

| Özellik                       | Açıklama                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| enrollmentFailureCategoryKey   | Kayıt hatası kategorisi (yedek anahtar) veri ambarındaki benzersiz tanımlayıcısı  |
| enrollmentFailureCategoryName  | Kayıt hatası kategori adı. Aşağıdaki örneklere bakın.                            |

### <a name="example"></a>Örnek

| enrollmentFailureCategoryName   | Açıklama                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Uygulanamaz                  | Kayıt hatası kategorisi geçerli değil.                                                            |
| Kullanılamıyor                   | Kayıt hatası kategori kullanılamıyor.                                                             |
| Bilinmiyor                         | Bilinmeyen hata.                                                                                                |
| Authentication                  | Kimlik doğrulaması başarısız oldu.                                                                                        |
| Yetkilendirme                   | Çağrı kimliği doğrulanmış ancak kaydetmek için yetkili değil.                                                         |
| AccountValidation               | Kayıt hesabı doğrulanamadı. (Hesabı engellenen kayıt etkin değil)                      |
| UserValidation                  | Kullanıcı doğrulanamadı. (Kullanıcı yok, lisans eksik)                                           |
| DeviceNotSupported              | Cihaz mobil cihaz yönetimi için desteklenmiyor.                                                         |
| InMaintenance                   | Hesap bakımda.                                                                                    |
| BadRequest                      | İstemci, hizmeti tarafından anlaşılan/desteklenen değil bir istek gönderdi.                                        |
| FeatureNotSupported             | Bu kayıt tarafından kullanılan özellikleri, bu hesap için desteklenmez.                                        |
| EnrollmentRestrictionsEnforced  | Yönetici tarafından yapılandırılan kayıt kısıtlamaları, bu kayıt engellendi.                                          |
| ClientDisconnected              | İstemci zaman aşımına uğradı veya kayıt son kullanıcı tarafından iptal edildi.                                                        |
| UserAbandonment                 | Kayıt, son kullanıcı tarafından bırakıldı. (Son kullanıcı ekleme başlatıldı ancak iadelerinin zamanında tamamlanmasına başarısız oldu)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
**EnrollmentFailureReason** varlığı, bir cihaz kayıt hatası verilen hata kategorisi için ayrıntılı bir neden gösterir.  

| Özellik                     | Açıklama                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| enrollmentFailureReasonKey   | Kayıt hatanın nedenini (yedek anahtar) veri ambarındaki benzersiz tanıtıcısı  |
| enrollmentFailureReasonName  | Kayıt hatanın nedenini adı. Aşağıdaki örneklere bakın.                            |

### <a name="example"></a>Örnek

| enrollmentFailureReasonName      | Açıklama                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Uygulanamaz                   | Kayıt hatanın nedenini geçerli değildir.                                                                                                                                                       |
| Kullanılamıyor                    | Kayıt hatanın nedenini kullanılamıyor.                                                                                                                                                        |
| Bilinmiyor                          | Bilinmeyen hata.                                                                                                                                                                                         |
| UserNotLicensed                  | Kullanıcı, Intune'da bulunamadı veya geçerli bir lisansa sahip değil.                                                                                                                                     |
| UserUnknown                      | Kullanıcı Intune için bilinmiyor.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Yalnızca bir kullanıcı bir cihaz kaydedebilir. Bu cihaz, daha önce başka bir kullanıcı tarafından kaydedildi.                                                                                                                |
| EnrollmentOnboardingIssue        | Intune mobil cihaz Yönetimi (MDM) yetkilisi henüz yapılandırılmadı.                                                                                                                                 |
| AppleChallengeIssue              | İOS yönetim profili yüklemesi geciktirildi veya başarısız oldu.                                                                                                                                         |
| AppleOnboardingIssue             | Intune'a kaydetmek için Apple MDM anında iletme sertifikası gereklidir.                                                                                                                                       |
| DeviceCap                        | İzin verilen en yüksek sayıdan daha fazla cihaz kaydetmeye çalıştı. kullanıcı.                                                                                                                                        |
| AuthenticationRequirementNotMet  | Intune kayıt hizmeti, bu isteği yetkilendirmek başarısız oldu.                                                                                                                                            |
| UnsupportedDeviceType            | Bu cihaz, Intune kaydı için en düşük gereksinimleri karşılamıyor.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Bu cihaz, bir kayıt kısıtlama kuralı nedeniyle kaydedilemedi.                                                                                                                          |
| BulkDeviceNotPreregistered       | Bu cihazın uluslararası mobil ekipman tanımlayıcısı (IMEI) veya seri numarası bulunamadı.  Bu tanımlayıcı olmadan, cihazlar, şu anda engelleniyor kişiye ait cihazlar kabul edilir.  |
| FeatureNotSupported              | Kullanıcı, tüm müşteriler için henüz yayımlanmayan veya Intune yapılandırmanız ile uyumlu olmayan bir özelliğe erişmeye çalışıyordu.                                                            |
| UserAbandonment                  | Kayıt, son kullanıcı tarafından bırakıldı. (Son kullanıcı ekleme başlatıldı ancak iadelerinin zamanında tamamlanmasına başarısız oldu)                                                                                           |
| APNSCertificateExpired           | Apple cihazlar süresi dolmuş bir Apple MDM anında iletme sertifikasıyla yönetilemez.                                                                                                                            |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions
**intuneManagementExtension**, günlük olarak her bir Windows 10 cihazın **intuneManagementExtension** durumunu listeler. Son 60 günün verileri alınır.

|       Özellik      |                          Açıklama                          | Örnek |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| DateKey             | Tarihin benzersiz tanımlayıcısı.                                | 123     |
| TenantKey           | Kiracının benzersiz tanımlayıcısı.                              | 456     |
| DeviceKey           | Cihazın benzersiz tanımlayıcısı.                              | 789     |
| ExtensionVersionKey | IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1.       |
| ExtensionStateKey   | Sistem durumunun benzersiz tanımlayıcısı.                            | 2       |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates
**IntuneManagementExtensionHealthState**, **IntuneManagementExtension** varlığının olası tüm durumlarını listeler.

|      Özellik     |                   Açıklama                  | Örnek |
|:-----------------:|:----------------------------------------------:|:-------:|
| ExtensionStateKey | Sistem durumunun benzersiz tanımlayıcısı.           | 2       |
| ExtensionState    | Bir IntuneManagementExtension uzantısının durumu. | Sorunsuz |

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions
**IntuneManagementExtensionVersion** varlığı, **IntuneManagementExtension** tarafından kullanılan tüm sürümleri listeler.

|       Özellik      |                          Açıklama                          | Örnek |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| ExtensionVersionKey | IntuneManagementExtension sürümünün benzersiz tanımlayıcısı. | 1.       |
| ExtensionVersion    | 4 basamaklı sürüm numarası.                                   | 1.0.2.0 |

## <a name="managementagenttypes"></a>managementAgentTypes
**managementAgentType** varlığı, bir cihazı yönetmek için kullanılan aracıları temsil eder.

|         Özellik        |                                       Açıklama                                       |
|:-----------------------:|:---------------------------------------------------------------------------------------:|
| ManagementAgentTypeID   | Yönetim aracısı türünün benzersiz tanımlayıcısı.                                         |
| ManagementAgentTypeKey  | Veri ambarındaki yönetim aracısı türünün benzersiz tanımlayıcısı - vekil anahtar. |
| ManagementAgentTypeName | Cihazı yönetmek için ne tür bir aracı kullanıldığını gösterir.                              |

### <a name="example"></a>Örnek

| ManagementAgentTypeID |                Name               |                                  Açıklama                                 |
|:---------------------:|:---------------------------------:|:----------------------------------------------------------------------------:|
| 1.                     | EAS                               | Cihaz, Exchange Active Sync yoluyla yönetiliyor                         |
| 2                     | MDM                               | Cihaz, bir MDM aracısı kullanılarak yönetiliyor                                   |
| 3                     | EasMdm                            | Cihaz, Exchange Active Sync ve bir MDM aracısıyla yönetiliyor        |
| 4                     | IntuneClient                      | Cihaz, Intune bilgisayar aracısı tarafından yönetiliyor                               |
| 5                     | EasIntuneClient                   | Cihaz, Exchange Active Sync ve Intune bilgisayar aracısıyla yönetiliyor |
| 8                     | ConfigManagerClient               | Cihaz, System Center Configuration Manager aracısı tarafından yönetiliyor     |
| 10                    | ConfigurationManagerClientMdm     | Cihaz, Configuration Manager ve MDM tarafından yönetiliyor.                    |
| 11                    | ConfigurationManagerCLientMdmEas  | Cihaz; Configuration Manager, MDM ve EAS tarafından yönetiliyor.               |
| 16                    | Bilinmiyor                           | Bilinmeyen yönetim aracısı türü                                              |
| 32                    | Jamf                              | Cihaz öznitelikleri Jamf’den getirilir.                               |
| 64                    | GoogleCloudDevicePolicyController |  Cihaz, Google’ın CloudDPC hizmeti tarafından yönetiliyor.                                 |

## <a name="managementstates"></a>managementStates
**ManagementState** varlığı, cihazın durumu hakkında ayrıntılar sağlar. Ayrıntılar; uzak eylemlerin uygulandığı, cihaza jailbreak uygulandığı veya cihazın kökünün belirtildiği durumlarda faydalı olabilir.

|       Özellik      |                                     Açıklama                                    |
|:-------------------:|:----------------------------------------------------------------------------------:|
| managementStateID   | Yönetim durumunun benzersiz tanımlayıcısı.                                       |
| managementStateKey  | Veri ambarındaki yönetim durumunun benzersiz tanımlayıcısı - vekil anahtar. |
| managementStateName | Cihaza uygulanan uzak eylemin durumunu gösterir.                 |

### <a name="example"></a>Örnek

| managementStateID |      Name      |                                                   Açıklama                                                   |
|:-----------------:|:--------------:|:---------------------------------------------------------------------------------------------------------------:|
| 0                 | Yönetilen        | Hiçbir bekleyen uzak eylem olmadan yönetilir.                                                                       |
| 1.                 | RetirePending  | Cihaz için bekleyen bir devre dışı bırakma komutu var.                                                             |
| 2                 | RetireFailed   | Devre dışı bırakma komutu cihazda başarısız oldu.                                                                      |
| 3                 | WipePending    | Cihaz için bekleyen bir silme komutu var.                                                               |
| 4                 | WipeFailed     | Silme komutu cihazda başarısız oldu.                                                                        |
| 5                 | İyi durumda değil      | Kötü durumda.                                                                                              |
| 6                 | DeletePending  | Cihaz için bekleyen bir silme komutu var.                                                             |
| 7                 | RetireIssued   | Cihaza bir devre dışı bırakma komutu verildi.                                                               |
| 8                 | WipeIssued     | Bir silme komutu verildi.                                                                               |
| 9                 | WipeCanceled   | Silme komutu iptal edildi.                                                                               |
| 10                | RetireCanceled | Devre dışı bırakma komutu iptal edildi.                                                                             |
| 11                | Bulundu     | Cihaz, Intune tarafından yeni keşfedildi. İlk defa iade edildikten sonra -Yönetiliyor- durumuna geçer. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates
MobileAppInstallState varlığı, bir mobil uygulama cihaz, kullanıcı veya her ikisini de içeren bir gruba atandıktan sonra uygulamanın yükleme durumunu temsil eder.

|       Özellik      |                        Açıklama                       |
|:-------------------:|:--------------------------------------------------------:|
| AppInstallStateKey  | Hesabınız için uygulama yükleme durumunun benzersiz kimliği. |
| AppInstallState     | Uygulama yükleme durumunun Enum değeri.                     |
| AppInstallStateName | Uygulama yükleme durumunun adı.                           |

## <a name="mobileappinstallstatuscounts"></a>mobileAppInstallStatusCounts
Microsoft Intune yoluyla Mobil Uygulama Yönetimini kullanarak bir hedef cihaz türü için mobil uygulama yükleme durumunu temsil eder.

|      Özellik      |                                                          Açıklama                                                          |
|:------------------:|:-----------------------------------------------------------------------------------------------------------------------------:|
| DateKey            | Uygulama yükleme durumunun kaydedildiği tarihin anahtarı.                                                                     |
| AppKey             | AppRevision örneğini tanımlamak için kullanılan mobil uygulamanın anahtarı.                                                          |
| DeviceTypeKey      | Mobil Uygulama ile ilişkili Cihaz Türü anahtarı.                                                              |
| AppInstallStateKey | MobileAppInstallState örneğini tanımlamak için kullanılan uygulama yükleme durumunun anahtarı.                                         |
| hata kodu          | Uygulama yükleyicisi, mobil platform veya uygulamanın yüklemesiyle ilgili hizmet tarafından döndürülen hata kodu. |
| Sayı              | Toplam miktar.                                                                                                                  |

## <a name="ownertypes"></a>ownerTypes
**ownerType** varlığı; bir cihazın sahipliğinin şirket, kişisel veya bilinmeyen olduğunu gösterir.

|    Özellik   |                                                                                     Açıklama                                                                                    |           Örnek          |
|:-------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------:|
| ownerTypeID   | Sahip türünün benzersiz tanımlayıcısı.                                                                                                                                               |                            |
| ownerTypeKey  | Veri ambarındaki sahip türünün benzersiz tanımlayıcısı - vekil anahtar.                                                                                                       |                            |
| ownerTypeName | Cihazların sahip türünü temsil eder:  Şirket - cihaz kuruluşa aittir.  Kişisel - Cihaz kişiye aittir (KCG).   Bilinmiyor - Bu cihazda bilgi yok. | Kurumsal kişisel bilinmiyor |

> [!Note]  
> İçin `ownerTypeName` filtre değeri ayarlamak gereken cihazlar için dinamik grupları oluştururken AzureAD `deviceOwnership` olarak `Company`. Daha fazla bilgi için [cihazlar için kuralları](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="policies"></a>ilkeler
**İlke** varlığı, cihaz yapılandırma profillerini, uygulama yapılandırma profillerini ve uyumluluk ilkelerini listeler. Kuruluşunuzda bir gruba Mobil Cihaz Yönetimi (MDM) ilkeleri atayabilirsiniz.

|          Özellik          |                                                                       Açıklama                                                                      |                Örnek               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| PolicyKey                  | Veri ambarında ilkeyi temsil eden Benzersiz Anahtar.                                                                                              | 123                                  |
| PolicyId                   | İlkenin veri ambarındaki benzersiz tanımlayıcısı.                                                                                                 | b66bc706-ffff-7437-0340-032819502773 |
| PolicyName                 | İlkenin Adı.                                                                                                                                    | "Windows 10 Temel"                |
| PolicyVersion              | Yapılandırmanın Sürümü. İlke düzenlendiğinde veya değiştirildiğinde, daha yeni bir sürüm oluşturulur.                                                             | 1, 2, 3                              |
| IsDeleted                  | Bu İlke kaydının güncelleştirilip güncelleştirilmediğini gösterir.  True - İlkenin güncelleştirilmiş alanları içeren yeni bir kaydı var.  False - İlke için en son kayıt. | True/False                           |
| StartDateInclusiveUTC      | Bu ilkenin veri ambarında oluşturulma tarihi ve saati (UTC).                                                                              | 23.11.2016 0:00                      |
| DeletedDateUTC             | IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat.                                                                                                   | 23.11.2016 0:00                      |
| RowLastModifiedDateTimeUTC | Bu ilkenin veri ambarında son değiştirilme tarihi ve saati (UTC).                                                                        | 23.11.2016 0:00                      |

## <a name="policydeviceactivities"></a>policyDeviceActivities
Aşağıdaki tablo; başarılı, beklemede, başarısız veya hata durumundaki cihazların günlük sayısını listeler. Bu sayı, İlke Türü profillerindeki verileri yansıtır. Örneğin, bir cihaz kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Cihaza biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa varlık, başarılı sayacını artırır ve cihazı hata durumuna geçirir. **policyDeviceActivity** varlığı, son 30 gün içindeki belirli bir gün için kaç cihazın hangi durumda olduğunu listeler.

|  Özellik |                                           Açıklama                                           |        Örnek        |
|:---------:|:-----------------------------------------------------------------------------------------------:|:---------------------:|
| DateKey   | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. | 20160703              |
| Bekleniyor   | Bekleme durumundaki benzersiz cihazların sayısı.                                                    | 123                   |
| Başarılı oldu | Başarı durumundaki benzersiz cihazların sayısı.                                                    | 12                    |
| PolicyKey | İlke Anahtarı, İlke ile birleştirilerek policyName elde edilebilir.                                  | Windows 10 temel |
| Hata     | Hata durumundaki benzersiz Cihazların sayısı.                                                      | 10                    |
| Başarısız    | Başarısız durumundaki benzersiz Cihazların sayısı.                                                     | 2                     |

## <a name="policyplatformtypes"></a>policyPlatformTypes

|        Özellik        |                      Açıklama                      |     Örnek    |
|:----------------------:|:-----------------------------------------------------:|:--------------:|
| PolicyPlatformTypeKey  | İlke platform türü için benzersiz anahtar.        | 20170519       |
| PolicyPlatformTypeId   | İlke platform türü için benzersiz tanımlayıcı. | 1.              |
| PolicyPlatformTypeName | İlke platform türünün adı.              | AndroidForWork |

## <a name="policytypeactivities"></a>policyTypeActivities
**PolicyTypeActivity** varlığı, başarılı, beklemede, başarısız veya hata durumundaki cihazların toplam sayısını listeler. Bu durumları cihazın yapılandırma profiline, uygulama yapılandırma profiline veya uyumluluk ilkesine göre günlük olarak listeler.

|    Özellik   |                                          Açıklama                                          |           Örnek           |
|:-------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| DateKey       | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. | 20160703                    |
| PolicyKey     | İlke Anahtarı, İlke ile birleştirilerek policyName elde edilebilir.                                | Windows 10 temel         |
| PolicyTypeKey | İlke Anahtarı türü, İlke Türü ile birleştirilerek ilke türü adı elde edilebilir.             | Windows 10 Uyumluluk İlkesi |
| Bekleniyor       | Bekleme durumundaki benzersiz cihazların sayısı.                                                    | 123                         |
| Başarılı     | Başarı durumundaki benzersiz cihazların sayısı.                                                    | 12                          |
| Hata         | Hata durumundaki benzersiz cihazların sayısı.                                                      | 10                          |
| Başarısız        | Başarısız durumundaki benzersiz cihazların sayısı.                                                     | 2                           |

## <a name="policytypes"></a>policyTypes
**PolicyType** varlığı, cihaz yapılandırma profillerini, uygulama yapılandırma profillerini ve Uyumluluk ilkeleri türlerini listeler. Kuruluşunuzda bir gruba Mobil Cihaz Yönetimi (MDM) ilkeleri atayabilirsiniz.

|    Özellik    |                       Açıklama                      |            Örnek            |
|:--------------:|:------------------------------------------------------:|:-----------------------------:|
| PolicyTypeId   | İlkenin kaynak sistemindeki benzersiz tanımlayıcısı.  | 123                           |
| PolicyTypeKey  | İlkenin veri ambarındaki benzersiz tanımlayıcısı. | 1.                             |
| PolicyTypeName | İlke türünün adı.                               | Windows 10 Uyumluluk ilkesi. |

## <a name="policyuseractivities"></a>policyUserActivities
Aşağıdaki tablo; başarılı, beklemede, başarısız veya hata durumundaki kullanıcıların günlük sayısını listeler. Bu sayı, İlke Türü profillerindeki verileri yansıtır. Örneğin, bir kullanıcı kendisine atanan tüm ilkeler için başarılı durumunda ise ilgili gün için başarılı sayacı bir artar. Bir kullanıcıya biri başarılı diğeri hata durumunda olmak üzere iki profil atanmışsa, kullanıcı hata durumunda olarak değerlendirilir. **PolicyUserActivity** varlığı, son 30 gün içindeki belirli bir gün için kaç kullanıcının hangi durumda olduğunu listeler.

|  Özellik |                                          Açıklama                                          |       Örnek       |
|:---------:|:---------------------------------------------------------------------------------------------:|:-------------------:|
| DateKey   | Cihaz Yapılandırma Profilinin iade işleminin, veri ambarına kaydedildiği zamanı belirten Tarih Anahtarı. | 20160703            |
| Bekleniyor   | Bekleme durumundaki benzersiz cihazların sayısı.                                                    | 123                 |
| Başarılı | Başarı durumundaki benzersiz cihazların sayısı.                                                    | 12                  |
| PolicyKey | İlke Anahtarı, İlke ile birleştirilerek policyName elde edilebilir.                                | Windows 10 temel |
| Hata     | Hata durumundaki benzersiz cihazların sayısı.                                                      | 10                  |

## <a name="termsandconditions"></a>termsAndConditions
**termsAndConditions** varlığı, bir Hüküm ve Koşullar (T-C) ilkesinin meta verilerini ve içeriğini temsil eder. T-C ilkelerinin içeriği, kullanıcılara Intune’a ilk kaydolmaya çalıştıklarında ve bir yönetici yeniden kabul gerektirdiğinde içerikte yapılan düzenlemelerden sonra sunulur. Bu ilkeler, yöneticilerin bir kullanıcının Intune’a cihaz kaydetmesi için onaylaması gereken sağlamaları sunmasını sağlar.

|    Özellik        |    Açıklama    |    Örnek        |
|----------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------|
|    termsAndConditionsKey    |    “userTermsAndConditionsAcceptances” koleksiyonundaki bir girişe karşılık gelen anahtar    |    123    |
|    termsAndCondidionsId    |    Bu termsAndConditions girişinin kimliği    |    276edcb7-7440-4339-b6c5-8b6fc556fee6    |
|    termsAndConditionsVersion    |    Bu hüküm ve koşullar girişinin sürümü    |    1.    |
|    ad    |    Bu termsAndConditions girişinin adı.        |    Intune kullanım koşulları     |
|    açıklama    |    Bu hüküm ve koşulların açıklaması.     |         |
|    title    |    Bu hüküm ve koşulların başlığı.     |    Cihaz yönetimi şirket ilkesi        |
|    summaryOfTerms    |    Kullanıcıya verilen koşulların özeti.     |    Hüküm ve koşulları kabul ediyorum.    |
|    termsAndConditionsBodyText    |    Bu hüküm ve koşulların metin gövdesi.       |    *Cihaz şifreleme* 6 basamaklı PIN zorlama    |
|    IsDeleted    |    Bu değerin silinip silinmediğine ilişkin True veya False değerleri.     |    False    |
|    startDateInclusiveUTC    |    Bu hüküm ve koşulların başlama tarihi.     |    23.8.2018 4:01:34 ÖÖ    |
|    endDateEclusiveUTC    |    Bu hüküm ve koşulların bitiş tarihi.     |    31.12.9999 12.00.00 ÖÖ    |

## <a name="userdeviceassociations"></a>userDeviceAssociations
**UserDeviceAssociation** varlığı kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir.

|        Ad        |                                             Açıklama                                            |     Örnek     |
|:------------------:|:--------------------------------------------------------------------------------------------------:|:---------------:|
| UserKey            | Kullanıcının veri ambarındaki benzersiz tanımlayıcısı.   (Yedek anahtar).                            | 123             |
| DeviceKey          | Cihazın veri ambarındaki benzersiz tanımlayıcısı.                                             | 123             |
| CreatedDateTimeUTC | Kullanıcı cihaz ilişkisinin oluşturulduğu tarih ve saat. UTC biçimini kullanır.                     | 23.11.2016 0:00 |
| IsDeleted          | Kullanıcının cihaz kaydını kaldırdığını ve ilişkinin artık geçerli olmadığını gösterir. | True/False      |
| EndedDateTimeUTC   | IsDeleted değerinin True olarak değiştirildiği tarih ve UTC diliminde saat.                                               | 23.6.2017 0:00  |

## <a name="users"></a>kullanıcılar
**user** varlığı, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını listeler.

**Kullanıcı** varlık koleksiyonu, kullanıcı verilerini içerir. Bu kayıtlar, kullanıcı kaldırıldıysa dahi, veri toplama döneminde kullanıcı durumlarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı, raporun olduğu saatte bulunmasa da kullanıcı ve durum, önceki ayın verilerinde bulunuyor. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

|          Özellik          |                                                                                                           Açıklama                                                                                                          |                Örnek               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | Veri ambarındaki kullanıcının benzersiz tanımlayıcısı - vekil anahtar.                                                                                                                                                         | 123                                  |
| UserId                     | Kullanıcının benzersiz tanımlayıcısı - UserKey’e benzerdir ancak doğal bir anahtardır.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | Kullanıcının e-posta adresi.                                                                                                                                                                                                     | John@constoso.com                    |
| UPN                        | Kullanıcının kullanıcı asıl adı.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Kullanıcının görünen adı.                                                                                                                                                                                                      | John                                 |
| IntuneLicensed             | Kullanıcının Intune lisansı olup olmadığını belirtir.                                                                                                                                                                              | Doğru/Yanlış                           |
| IsDeleted                  | Kullanıcının tüm lisanslarının geçerliliğini yitirip yitirmediğini ve kullanıcının buna bağlı olarak Intune’dan kaldırılıp kaldırılmadığını belirtir. Tek bir kayıt için bu bayrak değişmez. Bunun yerine, yeni bir kullanıcı durumu için yeni bir kayıt oluşturulur. | True/False                           |
| RowLastModifiedDateTimeUTC | Kaydın veri ambarında son değiştirilme tarihi ve saati (UTC)                                                                                                                                                 | 23.11.2016 0:00                      |

## <a name="usertermsandconditionsacceptances"></a>userTermsAndConditionsAcceptances
**userTermsAndConditionsAcceptance** varlığı, bir Hüküm ve Koşullar (T-C) ilkesinin bir kullanıcı tarafından kabul durumunu temsil eder. Kullanıcılar, Şirket Portalı’na erişimlerini koruyabilmek için bu koşulların en güncel sürümünü kabul etmelidir.

|    Özellik    |    Açıklama    |    Örnek    |
|-------------------------------|--------------------------------------------------------------------------------|----------------------------|
|    dateKey    |    “dates” koleksiyonundaki tarih değerlerine karşılık gelen anahtar.     |    20180823    |
|    userKey    |    “Kullanıcılar” koleksiyonunda bir kullanıcıyla eşleşen kullanıcı anahtarı.     |    20000    |
|    termsAndConditionsKey    |    “termsAndConditions” koleksiyonundaki bir girişe karşılık gelen anahtar    |    1.    |
|    acceptedDateTimeUTC    |    Kullanıcının bu hüküm ve koşulları kabul ettiği saat    |    23.8.2018 4:01:34 ÖÖ    |
|    lastModifiedDateTimeUTC    |    Bu girişin son değiştirildiği zaman.     |    23.8.2018 4:01:34 ÖÖ    |

## <a name="vppprogramtypes"></a>vppProgramTypes 
**vppProgramType** varlığı, bir uygulama için olası VPP program türlerini listeler.

|      Özellik      |          Açıklama         |
|:------------------:|:----------------------------:|
| VppProgramTypeID   | Tür kimliği.           |
| VppProgramTypeKey  | Anahtar için vekil anahtar. |
| VppProgramTypeName | VPP Program türü.          |

### <a name="example"></a>Örnek

|             VppProgramID             |         Ad        | Açıklama                |
|:------------------------------------:|:-------------------:|----------------------------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft           | Microsoft’un VPP programı. |
| 00000000-0000-0000-0000-000000000000 | Henüz Kullanılamıyor | Varsayılan değer, VPP Yok.   |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple               | Apple’ın VPP programı.     |

## <a name="next-steps"></a>Sonraki adımlar

Intune Veri Ambarı hakkında daha fazla bilgi için bkz. [Veri Ambarı veri modeli](https://docs.microsoft.com/intune/reports-ref-data-model).

