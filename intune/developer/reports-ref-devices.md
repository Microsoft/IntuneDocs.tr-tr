---
title: Cihazlar-Intune veri ambarı
titleSuffix: Microsoft Intune
description: Intune veri ambarı API 'sindeki varlık koleksiyonlarının cihazlar kategorisi için başvuru konusu.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 032b0f8dcc9d4535838b28c8b24247ff6f4a72f1
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940002"
---
# <a name="reference-for-devices-entities"></a>Cihaz varlıkları için başvuru

**Cihazlar** kategorisi, mobil cihazlar için şu gibi bilgileri izleyen varlıklar içerir:

- Cihaz türü
- Cihaz kaydı ve kayıt durumu
- Cihaz sahipliği
- Cihaz yönetimi durumu
- Azure AD durumuna cihaz üyeliği
- Kayıt durumu
- Cihazla ilgili geçmişteki bilgiler
- Cihazdaki uygulamaların envanteri

## <a name="devicetypes"></a>DeviceType

**DeviceType** varlığı, diğer veri ambarı varlıkları tarafından başvurulan cihaz türünü temsil eder. Cihaz türü genellikle cihaz modelini, üreticiyi veya her ikisinin birleşimini açıklar.

| Özellik  | Açıklama |
|---------|------------|
| DeviceTypeID |Cihaz türünün benzersiz tanımlayıcısı |
| deviceTypeKey |Veri ambarındaki cihaz türünün benzersiz tanımlayıcısı-vekil anahtar |
| DeviceTypeName |Cihaz türü |

### <a name="example"></a>Örnek

| DeviceTypeID  | Name | Açıklama |
|---------|------------|--------|
| 0 |Masaüstü |Windows Masaüstü cihazı |
| 1\. |WindowsRT |WindowsRT cihazı |
| 2 |WinMO6 |Windows Mobile 6,0 cihazı |
| 3 |Nokia |Nokia cihazı |
| 4 |WindowsPhone |Windows Phone cihaz |
| 5 |Mac |Mac cihazı |
| 6 |WinCE |Windows CE cihaz |
| 7 |Wınembedded |Windows Embedded cihazı |
| 8 |IPhone |iPhone cihazı |
| 9 |'De |iPad cihazı |
| 10 |IPod |iPod cihazı |
| 11 |Android |Android cihaz-Cihaz Yöneticisi kullanılarak yönetiliyor |
| 12 |Isocconsumer |Isoc tüketici cihazı |
| 14 |Macmdd |Yerleşik MDM aracısıyla yönetilen Mac OS X cihaz |
| 15 |HoloLens |HoloLens cihazı |
| 16 |Surçok yönlü hub |Surface Hub cihaz |
| 17 |AndroidForWork |Android cihaz-Android profil sahibi kullanılarak yönetiliyor |
| 100 |RT |BlackBerry cihazı |
| 101 |Palm |Palm cihazı |
| 255 |Bilinmiyor |Bilinmeyen cihaz türü |

## <a name="enrollmentactivities"></a>Kayıt \ tüm 
KayıtSayısı **varlığı,** bir cihaz kaydının etkinliğini gösterir.

| Özellik                      | Açıklama                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| DateKey                       | Bu kayıt etkinliğinin kaydedildiği tarih anahtarı.               |
| Devicekayıtlarını Menttypekey       | Kayıt türünün anahtarı.                                        |
| deviceTypeKey                 | Cihaz türünün anahtarı.                                                |
| Kayıtanahtarı      | Kaydın başarı veya başarısızlık durumunu gösteren anahtar.    |
| Kayıt%0 kategori anahtarı  | Kayıt hatası kategorisinin anahtarı (kayıt başarısız olduysa).        |
| Kayıtefailurereasonkey    | Kayıt hatası nedeninin anahtarı (kayıt başarısız olursa).          |
| osVersion                     | Cihazın işletim sistemi sürümü.                               |
| count                         | Yukarıdaki sınıflandırmalarla eşleşen kayıt etkinliklerinin toplam sayısı.  |

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
| Kimlik doğrulaması                  | Kimlik doğrulama başarısız oldu.                                                                                        |
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
## <a name="ownertypes"></a>OwnerTypes

Kayıtsahibi **türü** varlığı, bir cihazın kurumsal, kişisel veya bilinmeyen olduğunu gösterir.

| Özellik  | Açıklama | Örnek |
|---------|------------|--------|
| Ownertypeıd |Sahip türünün benzersiz tanımlayıcısı. | |
| ownerTypeKey |Veri ambarındaki sahip türünün benzersiz tanımlayıcısı-vekil anahtar. | |
| ownerTypeName |Cihazların sahip türünü temsil eder:  <br>Şirket-cihaz, kuruluşa aittir. <br>Kişisel-cihaz kişiye aittir (BYOD).  <br>Bilinmiyor-bu cihaz hakkında bilgi yok. |Şirket kişisel bilinmiyor |

> [!Note]  
> Cihazlar için dinamik gruplar oluştururken AzureAD içindeki `ownerTypeName` için, `deviceOwnership` filtre değerini `Company` olarak ayarlamanız gerekir. Daha fazla bilgi için bkz. [Cihazlar Için kurallar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>Yönetim durumları

**Managementstates** varlığı, cihazın durumu hakkında ayrıntılar sağlar. Ayrıntı, uzak eylemlerin uygulandığı, cihazın jailbreak uygulanmış veya kök olduğu durumlarda yararlı olabilir.

| Özellik  | Açıklama |
|---------|------------|
| Managementstateıd | Yönetim durumunun benzersiz tanımlayıcısı. |
| managementStateKey | Veri ambarındaki yönetim durumunun benzersiz tanımlayıcısı-vekil anahtar. |
| managementStateName | Bu cihaza uygulanan uzak eylemin durumunu gösterir. |

### <a name="example"></a>Örnek

| Managementstateıd  | Name | Açıklama |
|---------|------------|--------|
| 0 |Lebilmesi | Bekleyen uzak eylemler olmadan yönetilir. |
| 1\. |Retırepbitiriliyor | Cihaz için bekleyen bir devre dışı bırakma komutu var. |
| 2 |RetireFailed | Devre dışı bırakma komutu cihazda başarısız oldu. |
| 3 |WipePending | Cihaz için bekleyen bir silme komutu var. |
| 4 |WipeFailed | Silme komutu cihazda başarısız oldu. |
| 5 |Sağlıksız | Sağlıksız durum. |
| 6 |DeletePending | Cihaz için bekleyen bir silme komutu var. |
| 7 |RetireIssued | Cihaza devre dışı bırakma komutu verildi. |
| 8 |Wipeyayınlandı | Silme komutu verildi. |
| 9 |Wonu Anceled | Silme komutu iptal edildi. |
| 10 |Retirecli | Devre dışı bırakma komutu iptal edildi. |
| 11 |Tespit | Cihaz, Intune tarafından yeni keşfedildiğinde, ilk kez yönetilen durumu iade eder. |

## <a name="managementagenttypes"></a>ManagementAgentTypes

**Managementagenttype** varlığı, bir cihazı yönetmek için kullanılan aracıları temsil eder.

| Özellik  | Açıklama |
|---------|------------|
| Managementagenttypeıd | Yönetim Aracısı türünün benzersiz tanımlayıcısı. |
| ManagementAgentTypeKey | Veri ambarındaki Yönetim Aracısı türünün benzersiz tanımlayıcısı-vekil anahtar. |
| ManagementAgentTypeName |Cihazı yönetmek için ne tür bir aracı kullanıldığını belirtir. |

### <a name="example"></a>Örnek

| Managementagenttypeıd  | Name | Açıklama |
|---------|------------|--------|
| 1\. |OLDUĞUNDAN | Cihaz, Exchange Active Sync ile yönetilir |
| 2 |MDM | Cihaz bir MDM Aracısı kullanılarak yönetiliyor |
| 3 |EasMdm | Cihaz hem Exchange Active Sync hem de bir MDM Aracısı tarafından yönetilir |
| 4 |Intuneclient | Cihaz, Intune bılgısayar Aracısı tarafından yönetiliyor |
| 5 |EasIntuneClient | Cihaz hem Exchange Active Sync hem de Intune bılgısayar Aracısı tarafından yönetilir |
| 8 |ConfigManagerClient | Cihaz, System Center Configuration Manager Aracısı tarafından yönetiliyor |
| 16 |Bilinmiyor | Bilinmeyen Yönetim Aracısı türü |

## <a name="devices"></a>Cihazlarınız

**Cihazlar** varlığı, yönetim altındaki tüm kayıtlı cihazları ve bunlara karşılık gelen özellikleri listeler.

|          Özellik          |                                                                                       Açıklama                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | Veri ambarındaki cihazın benzersiz tanımlayıcısı-vekil anahtar.                                                                                                               |
| DeviceID                   | Cihazın benzersiz tanımlayıcısı.                                                                                                                                                     |
| DeviceName                 | Cihaz adlandırmasına izin veren platformlardaki cihaz adı. Diğer platformlarda Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlar için kullanılamaz. |
| deviceTypeKey              | Bu cihaz için cihaz türü özniteliğinin anahtarı.                                                                                                                                    |
| DeviceRegistrationState    | Bu cihaz için istemci kayıt durumu özniteliğinin anahtarı.                                                                                                                      |
| ownerTypeKey               | Bu cihaz için sahip türü özniteliğinin anahtarı: Kurumsal, kişisel veya bilinmeyen.                                                                                                    |
| Kaydoleddatetime           | Bu cihazın kaydedildiği tarih ve saat.                                                                                                                                         |
| LastSyncDateTime           | Intune ile bilinen son cihaz denetimi.                                                                                                                                              |
| ManagementAgentKey         | Bu cihazla ilişkili yönetim aracısının anahtarı.                                                                                                                             |
| managementStateKey         | Bu cihazla ilişkili yönetim durumunun anahtarı, uzak bir eylemin en son durumunu veya jailbreak uygulanmış/kök dizini olduğunu gösterir.                                                |
| Azureaddeviceıd            | Bu cihaz için Azure DeviceID.                                                                                                                                                  |
| AzureADRegistered          | Cihazın Azure Active Directory kayıtlı olup olmadığı.                                                                                                                             |
| DeviceCategoryKey          | Bu cihazla ilişkili kategorinin anahtarı.                                                                                                                                     |
| Devicekayıtlarını Menttype       | Kayıt yöntemini belirten bu cihazla ilişkili kayıt türünün anahtarı.                                                                                             |
| Karmaşıstatekey         | Bu cihazla ilişkili uyumluluk durumunun anahtarı.                                                                                                                             |
| osVersion                  | Cihazın işletim sistemi sürümü.                                                                                                                                                |
| Easdeviceıd                | Cihazın Exchange ActiveSync KIMLIĞI.                                                                                                                                                  |
| Number               | Number                                                                                                                                                                           |
| UserID                     | Cihazla ilişkili kullanıcı için benzersiz tanımlayıcı.                                                                                                                           |
| RowLastModifiedDateTimeUTC | Bu cihazın veri ambarında en son değiştirildiği tarih ve saat (UTC).                                                                                                       |
| Üreticisini               | Cihazın üreticisi                                                                                                                                                             |
| model                      | Cihazın modeli                                                                                                                                                                    |
| OperatingSystem            | Cihazın işletim sistemi. Windows, iOS, vb.                                                                                                                                   |
| IsDeleted                  | Cihazın silinip silinmediğini gösteren ikili.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Android güvenlik düzeltme eki düzeyi                                                                                                                                                           |
| MEıD                       | MEıD                                                                                                                                                                                   |
| ıssuperdenetimli               | Cihaz denetimli durumu                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Bayt cinsinden boş depolama alanı.                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Bayt cinsinden toplam depolama alanı.                                                                                                                                                                |
| EncryptionState            | Cihazdaki şifreleme durumu.                                                                                                                                                      |
| SubscriberCarrier          | Cihazın abone taşıyıcısı                                                                                                                                                       |
| PhoneNumber                | Cihazın telefon numarası                                                                                                                                                             |
| IMEı                       | IMEı                                                                                                                                                                                   |
| CellularTechnology         | Cihazın hücresel teknolojisi                                                                                                                                                    |
| WiFiMacAddress             | Wi-Fi MAC                                                                                                                                                                              |
| ICD                       | Tümleşik devre kartı tanımlayıcısı                                                                                                                                                     |

## <a name="devicepropertyhistories"></a>Devicepropertygeçmişleri

**Devicepropertyhistory** varlığı, cihazlar tablosuyla aynı özelliklere ve son 90 gün boyunca her bir cihaz kaydının günlük anlık görüntülerine sahiptir. DateKey sütunu her satır için günü gösterir.

|          Özellik          |                                                                                      Açıklama                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | Günü gösteren tarih tablosuna başvuru.                                                                                                                                          |
| DeviceKey                  | Veri ambarındaki cihazın benzersiz tanımlayıcısı-vekil anahtar. Bu, Intune cihaz KIMLIĞINI içeren cihaz tablosuna bir başvurudur.                               |
| DeviceName                 | Cihaz adlandırmasına izin veren platformlardaki cihaz adı. Diğer platformlarda Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlar için kullanılamaz. |
| DeviceRegistrationStateKey | Bu cihaz için cihaz kayıt durumu özniteliğinin anahtarı.                                                                                                                    |
| ownerTypeKey               | Bu cihaz için sahip türü özniteliğinin anahtarı: Kurumsal, kişisel veya bilinmeyen.                                                                                                  |
| managementStateKey         | Bu cihazla ilişkili yönetim durumunun anahtarı, uzak bir eylemin en son durumunu veya jailbreak uygulanmış/kök dizini olduğunu gösterir.                                                |
| AzureADRegistered          | Cihazın Azure Active Directory kayıtlı olup olmadığı.                                                                                                                             |
| Karmaşıstatekey         | Karmaşıkstate 'e yönelik bir anahtar.                                                                                                                                                            |
| OSVersion                  | İşletim sistemi sürümü.                                                                                                                                                                          |
| Jailbreak uygulanmış                 | Cihazın kopuk veya kökü belirtilmiş olup olmadığı.                                                                                                                                         |
| DeviceCategoryKey          | Bu cihaz için cihaz kategorisi özniteliğinin anahtarı. 

