---
title: Cihazlar - Intune Veri Ambarı
titleSuffix: Microsoft Intune
description: Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Cihazlar kategorisi için başvuru konusu.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19ecbc632b924dda297b3692cabf5345b4724b30
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/25/2020
ms.locfileid: "77575778"
---
# <a name="reference-for-devices-entities"></a>Cihaz varlıkları için başvuru

**Cihazlar** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- Cihaz türü
- Cihaz kaydı ve kayıt durumu
- Cihaz sahipliği
- Cihaz yönetim durumu
- Cihazın Azure AD üyelik durumu
- Kayıt durumu
- Cihazın geçmiş bilgisi
- Cihazdaki uygulamaların envanteri

## <a name="devicetypes"></a>deviceTypes

**DeviceType** varlığı, diğer veri ambarı varlıkları tarafından başvurulan cihaz türünü temsil eder. Cihaz türü genellikle cihaz modelini, üreticisini veya her ikisini de belirtir.

| Özellik  | Açıklama |
|---------|------------|
| deviceTypeID |Cihaz türünün benzersiz tanımlayıcısı |
| deviceTypeKey |Veri ambarındaki cihaz türünün benzersiz tanımlayıcısı - vekil anahtar |
| deviceTypeName |Cihaz türü |

### <a name="example"></a>Örnek

| deviceTypeID  | Ad | Açıklama |
|---------|------------|--------|
| 0 |Masaüstü |Windows Masaüstü cihaz |
| 1 |WindowsRT |WindowsRT cihaz |
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
| 15 |HoloLens |HoloLens cihazı |
| 16 |SurfaceHub |Surface Hub cihaz |
| 17 |AndroidForWork |Android Profil Sahibi kullanılarak yönetilen Android cihaz |
| 100 |Blackberry |Blackberry Cihaz |
| 101 |Palm |Palm cihaz |
| 255 |Bilinmiyor |Bilinmeyen cihaz türü |

## <a name="enrollmentactivities"></a>Kayıt \ tüm 
KayıtSayısı **varlığı,** bir cihaz kaydının etkinliğini gösterir.

| Özellik                      | Açıklama                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Bu kayıt etkinliğinin kaydedildiği tarih anahtarı.               |
| deviceEnrollmentTypeKey       | Kayıt türünün anahtarı.                                        |
| deviceTypeKey                 | Cihaz türünün anahtarı.                                                |
| Kayıtanahtarı      | Kaydın başarı veya başarısızlık durumunu gösteren anahtar.    |
| Kayıt%0 kategori anahtarı  | Kayıt hatası kategorisinin anahtarı (kayıt başarısız olduysa).        |
| Kayıtefailurereasonkey    | Kayıt hatası nedeninin anahtarı (kayıt başarısız olursa).          |
| osVersion                     | Cihazın işletim sistemi sürümü.                               |
| {1&gt;count&lt;1}                         | Yukarıdaki sınıflandırmalarla eşleşen kayıt etkinliklerinin toplam sayısı.  |

## <a name="enrollmenteventstatuses"></a>kayıt \ Menteventdurumlar 
KayıtSayısı **varlığı,** bir cihaz kaydının sonucunu gösterir.

| Özellik                   | Açıklama                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| Kayıtanahtarı   | Veri ambarındaki (vekil anahtar) kayıt durumunun benzersiz tanımlayıcısı  |
| KayıtAdı Menteventstatusname  | Kayıt durumunun adı. Aşağıdaki örneklere bakın.                            |

### <a name="example"></a>Örnek

| KayıtAdı Menteventstatusname  | Açıklama                            |
|----------------------------|----------------------------------------|
| Başarılı                    | Başarılı bir cihaz kaydı         |
| Başarısız                     | Hatalı bir cihaz kaydı             |
| Kullanılamıyor              | Kayıt durumu kullanılamıyor.  |

## <a name="enrollmentfailurecategories"></a>kayıtkonumunda Mentfailurecategories 
**Kayıt%0 kategori** varlığı, cihaz kaydının neden başarısız olduğunu gösterir. 

| Özellik                       | Açıklama                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| Kayıt%0 kategori anahtarı   | Veri ambarındaki (vekil anahtar) kayıt hatası kategorisinin benzersiz tanıtıcısı  |
| kayıtkonumunda Mentfailurecategoryname  | Kayıt hatası kategorisinin adı. Aşağıdaki örneklere bakın.                            |

### <a name="example"></a>Örnek

| kayıtkonumunda Mentfailurecategoryname   | Açıklama                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Uygulanamaz                  | Kayıt hatası kategorisi geçerli değil.                                                            |
| Kullanılamıyor                   | Kayıt hatası kategorisi kullanılamıyor.                                                             |
| Bilinmiyor                         | Bilinmeyen hata.                                                                                                |
| Kimlik Doğrulama                  | Kimlik doğrulama başarısız oldu.                                                                                        |
| Yetkilendirme                   | Çağrının kimliği doğrulandı, ancak kaydolma yetkisi yok.                                                         |
| AccountValidation               | Kayıt için Hesap doğrulanamadı. (Hesap engellendi, kayıt etkin değil)                      |
| Kullanıcı doğrulaması                  | Kullanıcı doğrulanamadı. (Kullanıcı yok, Lisans eksik)                                           |
| DeviceNotSupported              | Cihaz mobil cihaz yönetimi için desteklenmiyor.                                                         |
| Inmaintenance                   | Hesap bakımda.                                                                                    |
| Işlemindeki hatalı istek                      | İstemci, hizmet tarafından anlaşılmayan/desteklenmeyen bir istek gönderdi.                                        |
| FeatureNotSupported             | Bu kayıt tarafından kullanılan Özellik (ler) Bu hesap için desteklenmiyor.                                        |
| EnrollmentRestrictionsEnforced  | Yönetici tarafından yapılandırılan kayıt kısıtlamaları bu kaydı engelledi.                                          |
| Clientconnected              | İstemci zaman aşımına uğradı veya kayıt Son Kullanıcı tarafından iptal edildi.                                                        |
| Kullanıcı bırakma                 | Kayıt Son Kullanıcı tarafından bırakıldı. (Son Kullanıcı ekleme başlattı ancak zamanında tamamlanamadı)  |

## <a name="enrollmentfailurereasons"></a>kayıtkullanım Failurereadönemleri  
**Kayıtlımafailurereason** varlığı, belirli bir hata kategorisindeki cihaz kaydı hatasının daha ayrıntılı bir nedenini gösterir.  

| Özellik                     | Açıklama                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| Kayıtefailurereasonkey   | Veri ambarındaki (vekil anahtar) kayıt hatası nedeninin benzersiz tanıtıcısı  |
| Kayıtefailurereasonname  | Kayıt hatası nedeninin adı. Aşağıdaki örneklere bakın.                            |

### <a name="example"></a>Örnek

| Kayıtefailurereasonname      | Açıklama                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Uygulanamaz                   | Kayıt hatası nedeni geçerli değil.                                                                                                                                                       |
| Kullanılamıyor                    | Kayıt hatası nedeni kullanılamıyor.                                                                                                                                                        |
| Bilinmiyor                          | Bilinmeyen hata.                                                                                                                                                                                         |
| Usernotlisanslanmış                  | Kullanıcı Intune 'da bulunamadı veya geçerli bir lisansı yok.                                                                                                                                     |
| Kullanıcı bilinmiyor                      | Kullanıcı Intune tarafından tanınmıyor.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Bir cihazı yalnızca tek bir Kullanıcı kaydedebilir. Bu cihaz daha önce başka bir kullanıcı tarafından kaydedilmiş.                                                                                                                |
| EnrollmentOnboardingIssue        | Intune mobil cihaz yönetimi (MDM) yetkilisi henüz yapılandırılmadı.                                                                                                                                 |
| AppleChallengeIssue              | İOS Yönetim profili yüklemesi gecikti veya başarısız oldu.                                                                                                                                         |
| AppleOnboardingIssue             | Intune 'a kaydolmak için bir Apple MDM anında iletme sertifikası gerekir.                                                                                                                                       |
| DeviceCap                        | Kullanıcı izin verilen üst sınıra göre daha fazla cihaz kaydetmeyi denedi.                                                                                                                                        |
| Authenticationgereksinimnotmet  | Intune kayıt hizmeti bu isteği yetkilendiremedi.                                                                                                                                            |
| UnsupportedDeviceType            | Bu cihaz, Intune kaydı için en düşük gereksinimleri karşılamıyor.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Bu cihaz, yapılandırılmış bir kayıt kısıtlama kuralı nedeniyle kayıt yapamadı.                                                                                                                          |
| Bulkdevicenotpreryumura       | Bu cihazın uluslararası mobil ekipman tanımlayıcısı (ıMEı) veya seri numarası bulunamadı.  Bu tanımlayıcı olmadan, cihazlar, şu anda engellenen kişiye ait cihazlar olarak tanınır.  |
| FeatureNotSupported              | Kullanıcı, tüm müşteriler için henüz yayınlanmamış olan veya Intune yapılandırmanızla uyumlu olmayan bir özelliğe erişmeye çalışıyor.                                                            |
| Kullanıcı bırakma                  | Kayıt Son Kullanıcı tarafından bırakıldı. (Son Kullanıcı ekleme başlattı ancak zamanında tamamlanamadı)                                                                                           |
| Apnscercertificate kullanım dışı           | Apple cihazları, zaman aşımına uğradı bir Apple MDM anında iletme sertifikasıyla yönetilemez.                                                                                                                            |
## <a name="ownertypes"></a>ownerTypes

Kayıtsahibi **türü** varlığı, bir cihazın kurumsal, kişisel veya bilinmeyen olduğunu gösterir.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| ownerTypeID |Sahip türünün benzersiz tanımlayıcısı. | |
| ownerTypeKey |Veri ambarındaki sahip türünün benzersiz tanımlayıcısı - vekil anahtar. | |
| ownerTypeName |Cihazların sahip türünü temsil eder:  <br>Şirket-cihaz, kuruluşa aittir. <br>Kişisel - cihaz kişiye aittir (KCG).  <br>Bilinmiyor - bu cihazda bilgi yok. |Şirket kişisel bilinmiyor |

> [!Note]  
> Cihazlar için dinamik gruplar oluştururken AzureAD içindeki `ownerTypeName` için, `deviceOwnership` filtre değerini `Company`olarak ayarlamanız gerekir. Daha fazla bilgi için bkz. [Cihazlar Için kurallar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>managementStates

**Managementstates** varlığı, cihazın durumu hakkında ayrıntılar sağlar. Ayrıntılar; uzak eylemlerin uygulandığı, cihaza jailbreak uygulandığı veya cihazın kökünün belirtildiği durumlarda faydalı olabilir.

| Özellik  | Açıklama |
|---------|------------|
| managementStateID | Yönetim durumunun benzersiz tanımlayıcısı. |
| managementStateKey | Veri ambarındaki yönetim durumunun benzersiz tanımlayıcısı - vekil anahtar. |
| managementStateName | Cihaza uygulanan uzak eylemin durumunu gösterir. |

### <a name="example"></a>Örnek

| managementStateID  | Ad | Açıklama |
|---------|------------|--------|
| 0 |Yönetilen | Hiçbir bekleyen uzak eylem olmadan yönetilir. |
| 1 |RetirePending | Cihaz için bekleyen bir devre dışı bırakma komutu vardır. |
| 2 |RetireFailed | Devre dışı bırakma komutu cihazda başarısız oldu. |
| 3 |WipePending | Cihaz için bekleyen bir silme komutu vardır. |
| 4 |WipeFailed | Silme komutu cihazda başarısız oldu. |
| 5 |Sağlıksız | Kötü durumda. |
| 6 |DeletePending | Cihaz için bekleyen bir silme komutu vardır. |
| 7 |RetireIssued | Cihaz için bir devre dışı bırakma komutu verildi. |
| 8 |WipeIssued | Bir silme komutu verildi. |
| 9 |WipeCanceled | Silme komutu iptal edildi. |
| 10 |RetireCanceled | Devre dışı bırakma komutu iptal edildi. |
| 11 |Bulundu | Cihaz, Intune tarafından yeni keşfedildi, ilk defa iade edildikten sonra -Yönetiliyor- durumuna geçer. |

## <a name="managementagenttypes"></a>managementAgentTypes

**Managementagenttype** varlığı, bir cihazı yönetmek için kullanılan aracıları temsil eder.

| Özellik  | Açıklama |
|---------|------------|
| Managementagenttypeıd | Yönetim aracısı türünün benzersiz tanımlayıcısı. |
| managementAgentTypeKey | Veri ambarındaki yönetim aracısı türünün benzersiz tanımlayıcısı - vekil anahtar. |
| managementAgentTypeName |Cihazı yönetmek için ne tür bir aracı kullanıldığını gösterir. |

### <a name="example"></a>Örnek

| ManagementAgentTypeID  | Ad | Açıklama |
|---------|------------|--------|
| 1 |EAS | Cihaz, Exchange Active Sync yoluyla yönetiliyor |
| 2 |MDM | Cihaz bir MDM aracısı kullanılarak yönetiliyor |
| 3 |EasMdm | Cihaz, Exchange Active Sync ve bir MDM aracısıyla yönetiliyor |
| 4 |IntuneClient | Cihaz, Intune bilgisayar aracısı tarafından yönetilir |
| 5 |EasIntuneClient | Cihaz, Exchange Active Sync ve Intune bilgisayar aracısıyla yönetiliyor |
| 8 |ConfigManagerClient | Cihaz, Configuration Manager Aracısı tarafından yönetiliyor |
| 16 |Bilinmiyor | Bilinmeyen yönetim aracısı türü |

## <a name="devices"></a>devices

**Cihazlar** varlığı, yönetim altındaki tüm kayıtlı cihazları ve bunlara karşılık gelen özellikleri listeler.

|          Özellik          |                                                                                       Açıklama                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| deviceKey                  | Veri ambarındaki cihazın benzersiz tanımlayıcısı - vekil anahtar.                                                                                                               |
| deviceId                   | Cihazın benzersiz tanımlayıcısı.                                                                                                                                                     |
| deviceName                 | Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Diğer platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılamaz. |
| deviceTypeKey              | Bu cihazın cihaz türü özniteliğinin anahtarı.                                                                                                                                    |
| deviceRegistrationState    | Bu cihazın istemci kayıt durumu özniteliğinin anahtarı.                                                                                                                      |
| ownerTypeKey               | Cihaz için sahip türü özniteliğinin anahtarı: şirket, kişisel veya bilinmeyen.                                                                                                    |
| Kaydoleddatetime           | Bu cihazın kaydedildiği tarih ve saat.                                                                                                                                         |
| lastSyncDateTime           | Cihazın bilinen son Intune iadesi.                                                                                                                                              |
| managementAgentKey         | Bu cihazla ilişkili yönetim aracısının anahtarı.                                                                                                                             |
| managementStateKey         | Cihazla ilişkili yönetim durumunun anahtarı, bir uzak eylemin en son durumunu veya cihazda jailbreak yapılıp yapılmamış ya da kök erişim izni verilip verilmemiş olduğunu gösterir.                                                |
| Azureaddeviceıd            | Bu cihazın Azure cihaz kimliği.                                                                                                                                                  |
| azureADRegistered          | Bu cihazın Azure Active Directory’ye kayıtlı olup olmadığını gösterir.                                                                                                                             |
| deviceCategoryKey          | Cihazla ilişkili kategorinin anahtarı.                                                                                                                                     |
| Devicekayıtlarını Menttype       | Bu cihazla ilişkili kayıt türünün anahtarı, kayıt yöntemini gösterir.                                                                                             |
| complianceStateKey         | Cihazla ilişkili Uyumluluk durumu anahtarı.                                                                                                                             |
| osVersion                  | Cihazın işletim sistemi sürümü.                                                                                                                                                |
| Easdeviceıd                | Cihazın Exchange ActiveSync KIMLIĞI.                                                                                                                                                  |
| serialNumber               | SerialNumber                                                                                                                                                                           |
| UserID                     | Cihazla ilişkili kullanıcının Benzersiz Tanımlayıcısı.                                                                                                                           |
| rowLastModifiedDateTimeUTC | Bu cihazın veri ambarında son değiştirilme tarihi ve saati (UTC).                                                                                                       |
| üretici               | Cihazın üreticisi                                                                                                                                                             |
| {1&gt;model&lt;1}                      | Cihazın modeli                                                                                                                                                                    |
| operatingSystem            | Cihazın işletim sistemi. Windows, iOS/ıpados, vb.                                                                                                                                   |
| isDeleted                  | Bu cihazın silinip silinmediğini gösteren ikili dosya.                                                                                                                                 |
| androidSecurityPatchLevel  | Android güvenlik düzeltme eki düzeyi                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Cihaz denetimli durumu                                                                                                                                                               |
| freeStorageSpaceInBytes    | Bayt Cinsinden Boş Depolama Alanı.                                                                                                                                                                 |
| totalStorageSpaceInBytes   | Bayt Cinsinden Toplam Depolama Alanı.                                                                                                                                                                |
| encryptionState            | Cihazdaki şifreleme durumu.                                                                                                                                                      |
| subscriberCarrier          | Cihazın abone taşıyıcısı                                                                                                                                                       |
| phoneNumber                | Cihazın telefon numarası                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| cellularTechnology         | Cihazın hücresel teknolojisi                                                                                                                                                    |
| WiFiMacAddress             | Wi-Fi MAC                                                                                                                                                                              |
| ICD                       | Tümleşik devre kartı tanımlayıcısı                                                                                                                                                     |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

**Devicepropertyhistory** varlığı, cihazlar tablosuyla aynı özelliklere ve son 90 gün boyunca her bir cihaz kaydının günlük anlık görüntülerine sahiptir. DateKey sütunu, her satır için günü gösterir.

|          Özellik          |                                                                                      Açıklama                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| dateKey                    | Günü gösteren tarih tablosuna başvuru.                                                                                                                                          |
| deviceKey                  | Veri ambarındaki cihazın benzersiz tanımlayıcısı-vekil anahtar. Bu, Intune cihaz kimliğini barındıran Cihaz tablosuna bir başvurudur.                               |
| deviceName                 | Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılamaz. |
| deviceRegistrationStateKey | Bu cihazın cihaz kayıt durumu özniteliğinin anahtarı.                                                                                                                    |
| ownerTypeKey               | Cihazın sahip türü özniteliğinin anahtarı: şirket, kişisel veya bilinmeyen.                                                                                                  |
| managementStateKey         | Cihazla ilişkili yönetim durumunun anahtarı, bir uzak eylemin en son durumunu veya cihazda jailbreak yapılıp yapılmamış ya da kök erişim izni verilip verilmemiş olduğunu gösterir.                                                |
| azureADRegistered          | Bu cihazın Azure Active Directory’ye kayıtlı olup olmadığını gösterir.                                                                                                                             |
| complianceStateKey         | Bir ComplianceState anahtarı.                                                                                                                                                            |
| OSVersion                  | İşletim sistemi sürümü.                                                                                                                                                                          |
| Jailbreak uygulanmış                 | Cihazda jailbreak yapılıp yapılmadığı veya kök erişim izni verilip verilmediğini gösterir.                                                                                                                                         |
| deviceCategoryKey          | Bu cihaz için cihaz kategorisi özniteliğinin anahtarı. 

