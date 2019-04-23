---
title: Cihazlar - Intune Veri Ambarı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Cihazlar kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: c361c6054cf52c802155587084eaea76e024f78c
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511226"
---
# <a name="reference-for-devices-entities"></a>Cihaz varlıkları için başvuru

**Cihazlar** kategorisi, mobil cihazlar için aşağıdaki gibi bilgileri izleyen varlıklar içerir:

  -  Cihaz türü
  -  Cihaz kaydı ve kayıt durumu
  -  Cihaz sahipliği
  -  Cihaz yönetim durumu
  -  Cihazın Azure AD üyelik durumu
  -  Kayıt durumu
  -  Cihazın geçmiş bilgisi
  -  Cihazdaki uygulamaların envanteri

## <a name="devicetypes"></a>DeviceTypes

**DeviceTypes** varlığı, diğer veri ambarı varlıkları tarafından başvurulan cihaz türünü temsil eder. Cihaz türü genellikle cihaz modelini, üreticisini veya her ikisini de belirtir.

| Özellik  | Açıklama |
|---------|------------|
| DeviceTypeID |Cihaz türünün benzersiz tanımlayıcısı |
| DeviceTypeKey |Veri ambarındaki cihaz türünün benzersiz tanımlayıcısı - vekil anahtar |
| DeviceTypeName |Cihaz türü |

### <a name="example"></a>Örnek

| deviceTypeID  | Name | Açıklama |
|---------|------------|--------|
| 0 |Masaüstü |Windows Masaüstü cihaz |
| 1. |WindowsRT |WindowsRT cihaz |
| 2 |WinMO6 |Windows Mobile 6.0 cihaz |
| 3 |Nokia |Nokia cihaz |
| 4 |WindowsPhone |Windows Phone cihaz |
| 5 |Mac |Mac cihaz |
| 6 |WinCE |Windows CE cihaz |
| 7 |WinEmbedded |Windows Embedded cihaz |
| 8 |IPhone |iPhone cihaz |
| 9 |IPad |iPad cihaz |
| 10 |IPod |iPod cihaz |
| 11 |Android |Android cihaz-Cihaz Yöneticisi ile yönetilen |
| 12 |ISocConsumer |iSoc Consumer cihaz |
| 14 |MacMDM |Yerleşik MDM aracısıyla yönetilen Mac OS X cihaz |
| 15 |HoloLens |HoloLens cihaz |
| 16 |SurfaceHub |Surface Hub cihaz |
| 17 |AndroidForWork |Android Profil Sahibi kullanılarak yönetilen Android cihaz |
| 100 |Blackberry |Blackberry Cihaz |
| 101 |Palm |Palm cihaz |
| 255 |Bilinmiyor |Bilinmeyen cihaz türü |

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
| Authentication                  | Kimlik doğrulaması gerçekleştirilemedi.                                                                                        |
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
## <a name="ownertypes"></a>OwnerTypes

**EnrollmentTypes** varlığı; bir cihazın sahipliğinin şirket, kişisel veya bilinmeyen olduğunu gösterir.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ownerTypeID |Sahip türünün benzersiz tanımlayıcısı. | |
| ownerTypeKey |Veri ambarındaki sahip türünün benzersiz tanımlayıcısı - vekil anahtar. | |
| ownerTypeName |Cihazların sahip türünü temsil eder:  <br>Şirket - cihaz şirkete aittir olup. <br>Kişisel - cihaz kişiye aittir (KCG).  <br>Bilinmiyor - bu cihazda bilgi yok. |Kurumsal kişisel bilinmiyor |

> [!Note]  
> İçin `ownerTypeName` cihazlar için dinamik grupları oluştururken AzureAD filtre değeri ayarlamanız gerekir. `deviceOwnership` olarak `Company`. Daha fazla bilgi için [cihazlar için kuralları](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>ManagementStates

**ManagementStates** varlığı, cihazın durumu hakkında ayrıntılar sağlar. Ayrıntılar; uzak eylemlerin uygulandığı, cihaza jailbreak uygulandığı veya cihazın kökünün belirtildiği durumlarda faydalı olabilir.

| Özellik  | Açıklama |
|---------|------------|
| managementStateID | Yönetim durumunun benzersiz tanımlayıcısı. |
| managementStateKey | Veri ambarındaki yönetim durumunun benzersiz tanımlayıcısı - vekil anahtar. |
| managementStateName | Cihaza uygulanan uzak eylemin durumunu gösterir. |

### <a name="example"></a>Örnek

| managementStateID  | Name | Açıklama |
|---------|------------|--------|
| 0 |Yönetilen | Hiçbir bekleyen uzak eylem olmadan yönetilir. |
| 1 |RetirePending | Cihaz için bekleyen bir devre dışı bırakma komutu vardır. |
| 2 |RetireFailed | Devre dışı bırakma komutu cihazda başarısız oldu. |
| 3 |WipePending | Cihaz için bekleyen bir silme komutu vardır. |
| 4 |WipeFailed | Silme komutu cihazda başarısız oldu. |
| 5 |İyi durumda değil | Kötü durumda. |
| 6 |DeletePending | Cihaz için bekleyen bir silme komutu vardır. |
| 7 |RetireIssued | Cihaz için bir devre dışı bırakma komutu verildi. |
| 8 |WipeIssued | Bir silme komutu verildi. |
| 9 |WipeCanceled | Silme komutu iptal edildi. |
| 10 |RetireCanceled | Devre dışı bırakma komutu iptal edildi. |
| 11 |Bulundu | Cihaz, Intune tarafından yeni keşfedildi, ilk defa iade edildikten sonra -Yönetiliyor- durumuna geçer. |

## <a name="managementagenttypes"></a>ManagementAgentTypes

**ManagementAgentTypes** varlığı, bir cihazı yönetmek için kullanılan aracıları temsil eder.

| Özellik  | Açıklama |
|---------|------------|
| ManagementAgentTypeID | Yönetim aracısı türünün benzersiz tanımlayıcısı. |
| ManagementAgentTypeKey | Veri ambarındaki yönetim aracısı türünün benzersiz tanımlayıcısı - vekil anahtar. |
| ManagementAgentTypeName |Cihazı yönetmek için ne tür bir aracı kullanıldığını gösterir. |

### <a name="example"></a>Örnek

| ManagementAgentTypeID  | Name | Açıklama |
|---------|------------|--------|
| 1. |EAS | Cihaz, Exchange Active Sync yoluyla yönetiliyor |
| 2 |MDM | Cihaz bir MDM aracısı kullanılarak yönetiliyor |
| 3 |EasMdm | Cihaz, Exchange Active Sync ve bir MDM aracısıyla yönetiliyor |
| 4 |IntuneClient | Cihaz, Intune bilgisayar aracısı tarafından yönetilir |
| 5 |EasIntuneClient | Cihaz, Exchange Active Sync ve Intune bilgisayar aracısıyla yönetiliyor |
| 8 |ConfigManagerClient | Cihaz, System Center Configuration Manager aracısıyla yönetiliyor |
| 16 |Bilinmiyor | Bilinmeyen yönetim aracısı türü |

## <a name="devices"></a>Cihazlar

**Cihazlar** varlığı, yönetime kaydedilen tüm cihazları ve bunlara karşılık gelen özellikleri listeler.

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

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

**DevicePropertyHistory** varlığı, cihazlar tablosuyla aynı özelliklere sahiptir ve her cihaz kaydının son 90 gün boyunca günlük olarak anlık görüntüsünü alır. DateKey sütunu, her satır için günü gösterir.

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
| DeviceCategoryKey          | Bu cihaz için cihaz kategorisi özniteliğinin anahtarı. 

## <a name="applicationinventory"></a>ApplicationInventory

**ApplicationInventory** varlığı, envanter toplandığı anda cihazda bulunan uygulamaları listeler.


|      Özellik      |                       Açıklama                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Cihazlar tablosuna başvuru.               |
|   ApplicationKey   | ? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
|  ApplicationName   | ? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
| ApplicationVersion | ? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
|     BundleSize     | ? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |

