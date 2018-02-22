---
title: "Cihazlar - Intune Veri Ambarı | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki varlık koleksiyonlarının Cihazlar kategorisi için başvuru konusu."
keywords: "Intune Veri Ambarı"
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f304e07de7ceefb09152aeb30d113c378e716d38
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
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

| Özellik  | Description |
|---------|------------|
| DeviceTypeID |Cihaz türünün benzersiz tanımlayıcısı |
| DeviceTypeKey |Veri ambarındaki cihaz türünün benzersiz tanımlayıcısı - vekil anahtar |
| DeviceTypeName |Cihaz türü |

## <a name="example"></a>Örnek

| deviceTypeID  | Ad | Description |
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
| 15 |HoloLens |Holo Lens cihaz |
| 16 |SurfaceHub |Surface Hub cihaz |
| 17 |AndroidForWork |Android cihaz-Android for Work Profil Sahibi ile yönetilen |
| 100 |Blackberry |Blackberry Cihaz |
| 101 |Palm |Palm cihaz |
| 255 |Bilinmiyor |Bilinmeyen cihaz türü |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

**ClientRegistrationStateTypes** varlığı, diğer veri ambarı tabloları tarafından başvurulan kayıt türünü temsil eder.

| Özellik  | Description |
|---------|------------|
| clientRegisterationStateID |Kayıt durumu için benzersiz tanımlayıcı |
| clientRegisterationStateKey |Veri ambarındaki kayıt durumunun benzersiz tanımlayıcısı - vekil anahtar |
| clientRegisterationStateName |Kayıt durumu |

## <a name="example"></a>Örnek

| ClientRegisterationStateID  | Ad | Description |
|---------|------------|--------|
| 0 |NotRegistered |NotRegistered |
| 1 |SMSIDConflict |SMS ID çakışması |
| 2 |Kaydedildi |Kaydedildi |
| 3 |İptal Edildi |Durum, BT yöneticisinin istemciyi engellediği anlamına gelir ve istemcinin engeli kaldırılabilir. Bir cihaz ayrıca, silindikten veya devre dışı bırakıldıktan sonra İptal Edildi durumunda olabilir. |
| 4 |KeyConflict |Anahtar Çakışması |
| 5 |ApprovalPending |Onay Bekleniyor |
| 6 |ResetCert |Sertifikayı sıfırla |
| 7 |NotRegisteredPendingEnrollment |Kaydedilmedi kayıt bekleniyor |
| 8 |Bilinmiyor |Bilinmeyen durum |

## <a name="enrollmenttypes"></a>EnrollmentTypes

**EnrollmentTypes** varlığı, bir cihazın nasıl kaydedildiğini gösterir. Kayıt türü, kayıt yöntemini yakalar. Örnekler, farklı kayıt türlerini ve bunların ne anlama geldiğini listeler.

| Özellik  | Description |
|---------|------------|
| managementStateID |Yönetim durumunun benzersiz tanımlayıcısı. |
| managementStateKey |Veri ambarındaki yönetim durumunun benzersiz tanımlayıcısı - vekil anahtar. |
| managementStateName |Cihaza uygulanan uzak eylemin durumunu gösterir. |

## <a name="example"></a>Örnek

| enrollmentTypeID  | Ad | Description |
|---------|------------|--------|
| 0 |Bilinmiyor |Kayıt türü toplanmadı |
| 1 |UserEnrollment |Kullanıcı tarafından başlatılan kayıt |
| 2 |DeviceEnrollment |Kullanıcısız profille DEP Cihaz kaydı |
| 3 |DeviceEnrollmentWithUDA |UDA profiliyle cihaz kaydı. |
| 4 |AzureDomainJoined |Azure Active Directory yoluyla kullanıcı tarafından başlatılan cihaz kaydı |
| 5 |UserEnrollmentWithServiceAccount |Hizmet hesabı yoluyla kullanıcı tarafından başlatılan kayıt |
| 6 |DepDeviceEnrollment |Kullanıcısız profil ile DEP Cihaz kaydı |
| 7 |DepDeviceEnrollmentWithUDA |UDA profiliyle DEP Cihaz kaydı |
| 8 |AutoEnrollment |KCG senaryosu için DRS ve MDM Kaydı birleşimi |

## <a name="ownertypes"></a>OwnerTypes

**EnrollmentTypes** varlığı; bir cihazın sahipliğinin şirket, kişisel veya bilinmeyen olduğunu gösterir.

| Özellik  | Description | Örnek |
|---------|------------|--------|
| ownerTypeID |Sahip türünün benzersiz tanımlayıcısı. | |
| ownerTypeKey |Veri ambarındaki sahip türünün benzersiz tanımlayıcısı - vekil anahtar. | |
| ownerTypeName |Cihazların sahip türünü temsil eder:  <br>Şirket - cihaz kuruluşa aittir. <br>Kişisel - cihaz kişiye aittir (KCG).  <br>Bilinmiyor - bu cihazda bilgi yok. |Şirket/Kişisel Bilinmiyor |

## <a name="mdmstatuses"></a>MdmStatuses

**MdmStatuses** varlığı, cihazın uyumluluk durumunu gösterir.

| Özellik  | Description |
|---------|------------|
| MdmStatusID |Uyumluluk durumu için benzersiz tanımlayıcı |
| MdmStatusKey |Veri ambarındaki uyumluluk durumunun benzersiz tanımlayıcısı - vekil anahtar | 
| ComplianceStatus |Cihaz uyumluluk durumu aşağıdaki tablodaki değerlerden birine sahip olmalıdır | 


## <a name="example"></a>Örnek

| MdmStatusID  | ComplianceStatus | Description |
|---------|------------|--------|
| 0 |Bilinmiyor |Cihaz uyumluluk durumu bilinmiyor. |
| 1 |Uyumlu |Cihaz uyumlu. |
| 2 |Uyumsuz |Cihaz uyumsuz. |
| 3 |Çakışma |Cihazın uyumluluğu çakışma ile sonuçlandı. |
| 4 |Hata |Cihazın uyumluluk durumunda bir okuma hatası vardı. |


## <a name="managementstates"></a>ManagementStates

**ManagementStates** varlığı, cihazın durumu hakkında ayrıntılar sağlar. Ayrıntılar; uzak eylemlerin uygulandığı, cihaza jailbreak uygulandığı veya cihazın kökünün belirtildiği durumlarda faydalı olabilir.

| Özellik  | Description |
|---------|------------|
| managementStateID | Yönetim durumunun benzersiz tanımlayıcısı. |
| managementStateKey | Veri ambarındaki yönetim durumunun benzersiz tanımlayıcısı - vekil anahtar. |
| managementStateName | Cihaza uygulanan uzak eylemin durumunu gösterir. |

## <a name="example"></a>Örnek

| managementStateID  | Ad | Description |
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

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

**WorkPlaceJoinStateTypes** varlığı, cihazın Azure Active Directory Workplace Join durumunu temsil eder.  Kayıt iş akışı, doğrulama yapmak veya kimlik doğrulamak için bir ya da daha fazla sertifika kullanabilir. Bir cihaz WorkPlace’i kaydedildiğinde, cihazı ve kullanıcıyı doğrulamak için bu sertifikalar kullanılır. Sertifikaların verilmesi, SCEP (Basit Sertifika Kayıt Noktası) sunucusu yoluyla olur. Varlıktaki değerler, cihazın bu işlem sırasında geçebileceği çeşitli durumları gösterir. Bu durumlardan bazıları, gerekli bir sertifikanın verilmesinin (SCEP sunucusundan) başarısız olması sebebiyle WorkPlace katılımının başarısız olduğuna işaret eder. Cihaz bu iş akışından hiç geçmediyse, bu değer Bilinmeyen olarak gösterilir.

| Özellik  | Description |
|---------|------------|
| WorkPlaceJoinStateID | İş yeri katılım durumunun benzersiz tanımlayıcısı |
| WorkPlaceJoinStateKey | Veri ambarındaki iş yeri katılım durumunun benzersiz tanımlayıcısı - vekil anahtar |
| WorkPlaceJoinStateName | İş yeri katılım durumu |

## <a name="example"></a>Örnek

| workPlaceJoinStateID  | Ad | Description |
|---------|------------|--------|
| 0 |Bilinmiyor |Bir cihaz iş yerine katılmamışsa, Bilinmeyen durumundadır |
| 1 |Başarılı |İş yerine katılma başarılı |
| 2 |FailureToGetScepMetadata |SCEP meta verileri alma başarısız |
| 3 |FailureToGetScepChallenge |SCEP sınama alma başarısız |
| 4 |DeviceFailureToInstallScepCommand |Cihazda SCEP komutu yükleme başarısız |
| 5 |DeviceFailureToGetCertificate |Cihaz SCEP sunucusundan sertifika alamadı |
| 6 |DeviceScepPending |Bekleme durumunda; cihaz hala SCEP yapıyor |
| 7 |DeviceScepFailed |Cihaz SCEP sunucusundan sertifika yükleyemedi |
| 8 |AADValidationFailed |Cihazın AAD’de mevcut olduğunu doğrulama başarısız |

## <a name="managementagenttypes"></a>ManagementAgentTypes

**ManagementAgentTypes** varlığı, bir cihazı yönetmek için kullanılan aracıları temsil eder.

| Özellik  | Description |
|---------|------------|
| ManagementAgentTypeID | Yönetim aracısı türünün benzersiz tanımlayıcısı. |
| ManagementAgentTypeKey | Veri ambarındaki yönetim aracısı türünün benzersiz tanımlayıcısı - vekil anahtar. |
| ManagementAgentTypeName |Cihazı yönetmek için ne tür bir aracı kullanıldığını gösterir. |

## <a name="example"></a>Örnek

| ManagementAgentTypeID  | Ad | Description |
|---------|------------|--------|
| 1 |EAS | Cihaz, Exchange Active Sync yoluyla yönetiliyor |
| 2 |MDM | Cihaz bir MDM aracısı kullanılarak yönetiliyor |
| 3 |EasMdm | Cihaz, Exchange Active Sync ve bir MDM aracısıyla yönetiliyor |
| 4 |IntuneClient | Cihaz, Intune bilgisayar aracısı tarafından yönetilir |
| 5 |EasIntuneClient | Cihaz, Exchange Active Sync ve Intune bilgisayar aracısıyla yönetiliyor |
| 8 |ConfigManagerClient | Cihaz, System Center Configuration Manager aracısıyla yönetiliyor |
| 16 |Bilinmiyor | Bilinmeyen yönetim aracısı türü |

## <a name="devices"></a>Cihazlar

**Cihazlar** varlığı, yönetime kaydedilen tüm cihazları ve bunlara karşılık gelen özellikleri listeler.

| Özellik  | Description |
|---------|------------|
| DeviceKey | Veri ambarındaki cihazın benzersiz tanımlayıcısı - vekil anahtar. |
| DeviceId | Cihazın benzersiz tanımlayıcısı. |
| DeviceName | Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılabilir olamaz. |
| DeviceTypeKey | Bu cihaz için cihaz türü özniteliğinin anahtarı. |
| ClientRegisterationStateKey | Bu cihaz için istemci kayıt durumu özniteliğinin anahtarı. |
| OwnerTypeKey | Cihaz için sahip türü özniteliğinin anahtarı: şirket, kişisel veya bilinmeyen. |
| objectSourceKey | Bu sütunu yoksayın. |
| CreatedDate | Cihazın kaydedildiği tarih. |
| LastContact | Cihazın bilinen son Intune iadesi. |
| LastContactNotification | Intune’un cihazı Intune ile iade etmesi için uyardığı son an. |
| LastContactWorkplaceJoin | Cihaz için bilinen son Workplace Join durumunu gösteren zaman damgası. |
| ManagementAgentKey | Cihazla ilişkili yönetim aracısının anahtarı. |
| ManagementStateKey | Cihazla ilişkili yönetim durumunun anahtarı, bir uzak eylemin en son durumunu veya cihazda jailbreak/kök belirtme yapılıp yapılmadığını gösterir. |
| ReferenceId | Cihazın Azure Active Directory’deki kimliği. |
| WorkPlaceJoinStateKey | Cihazla ilişkili iş yeri katılım durumunun anahtarı. |
| CategoryId | Bu sütunu yoksayın. |
| EnrollmentTypeKey | Cihazla ilişkili kayıt türünün anahtarı, kayıt yöntemini gösterir. |
| CertExpirationDate | MDM yönetim sertifikasının sona erme tarihi. |
| MdmStatusKey | MdmStatus anahtarı. |
| OSFamily | İşletim Sistemi Ailesi (Windows, iOS, Android vb.) |
| OSVersion | İşletim sistemi sürümü |
| OSMajorVersion | İşletim sistemi sürümünün ana sürüm bileşeni (major.minor.build.revision). |
| OSMinorVersion | İşletim sistemi sürümünün alt sürüm bileşeni (major.minor.build.revision). |
| OSBuildNumber | İşletim sistemi sürümünün derleme sürümü bileşeni (major.minor.build.revision). |
| OSRevisionNumber | İşletim sistemi sürümünün düzeltme sürümü bileşeni (major.minor.build.revision). |
| EasID | Cihaz Exchange Active Sync ile yönetiliyorsa cihazın EAS kimliği. |
| GraphDeviceIsManaged | Intune’un Azure AD’de ayarladığı son yönetim durumu. |
| GraphDeviceIsCompliant | Intune’un Azure AD’de ayarladığı son uyumluluk durumu. |
| SerialNumber | Mevcutsa cihazın seri numarası. |
| EnrolledByUser | Kullanıcı tablosundaki userId sütununa başvuran ve cihazı kaydeden kullanıcının kimliği. |
| RowLastModifiedDateTimeUTC | Bu kaydın son değiştirildiği tarih. |
| ProcessorArchitecture | İşlemci mimarisi. |
| DeviceAction | Yapılan son cihaz eylemi, Şimdilik yoksayın. |
| Üretici | Cihazın üreticisi. |
| Model | Cihazın modeli. |
| LastPolicyUpdateUtc | Cihazda ilkenin güncelleştirildiği son an. |
| LastExchangeStatusUtc | Cihazın Exchange ile son eşitlendiği an. |
| IsDeleted | Cihaz artık Intune ile yönetilmiyorsa, True olarak ayarlayın. Bilinen son durumu korur. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

**DevicePropertyHistory** varlığı, cihazlar tablosuyla aynı özelliklere sahiptir ve her cihaz kaydının son 90 gün boyunca günlük olarak anlık görüntüsünü alır. DateKey sütunu, her satır için günü gösterir.

| Özellik  | Description |
|---------|------------|
| DateKey |Günü gösteren tarih tablosuna başvuru. |
| DeviceKey |Veri ambarındaki cihazın benzersiz tanımlayıcısı - vekil anahtar. Bu, Intune cihaz kimliğini barındıran Cihaz tablosuna bir başvurudur. |
| DeviceName |Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılabilir olamaz. |
| DeviceTypeKey |Bu cihaz için cihaz türü özniteliğinin anahtarı. |
| ClientRegisterationStateKey |Bu cihaz için istemci kayıt durumu özniteliğinin anahtarı. |
| OwnerTypeKey |Cihaz için sahip türü özniteliğinin anahtarı: şirket, kişisel veya bilinmeyen. |
| objectSourceKey |Bu sütunu yoksayın. |
| CreatedDate |Cihazın kaydedildiği tarih. |
| LastContact |Cihazın bilinen son Intune iadesi. |
| LastContactNotification |Intune’un cihazı Intune ile iade etmesi için uyardığı son an. |
| LastContactWorkplaceJoin |Cihaz için bilinen son Workplace Join durumunu gösteren zaman damgası. |
| ManagementAgentKey |Cihazla ilişkili yönetim aracısının anahtarı. |
| ManagementStateKey |Cihazla ilişkili yönetim durumunun anahtarı, bir uzak eylemin en son durumunu veya cihazda jailbreak/kök belirtme yapılıp yapılmadığını gösterir. |
| ReferenceId |Cihazın Azure Active Directory’deki kimliği. |
| WorkPlaceJoinStateKey |Cihazla ilişkili iş yeri katılım durumunun anahtarı. |
| CategoryId |Bu sütunu yoksayın. |
| EnrollmentTypeKey |Cihazla ilişkili kayıt türünün anahtarı, kayıt yöntemini gösterir. |
| CertExpirationDate |MDM yönetim sertifikasının sona erme tarihi. |
| MdmStatusKey |MdmStatus anahtarı. |
| OSFamily |İşletim Sistemi Ailesi (Windows, iOS, Android vb.) |
| OSVersion |İşletim sistemi sürümü. |
| OSMajorVersion |İşletim sistemi sürümünün ana sürüm bileşeni (major.minor.build.revision). |
| OSMinorVersion |İşletim sistemi sürümünün alt sürüm bileşeni (major.minor.build.revision). |
| OSBuildNumber |İşletim sistemi sürümünün derleme sürümü bileşeni (major.minor.build.revision). |
| OSRevisionNumber |İşletim sistemi sürümünün düzeltme sürümü bileşeni (major.minor.build.revision). |
| EasID |Cihaz Exchange Active Sync ile yönetiliyorsa cihazın EAS kimliği. |
| GraphDeviceIsManaged |Intune’un Azure AD’de ayarladığı son yönetim durumu. |
| GraphDeviceIsCompliant |Intune’un Azure AD’de ayarladığı son uyumluluk durumu. |
| SerialNumber |Mevcutsa cihazın seri numarası. |
| EnrolledByUser |Kullanıcı tablosundaki userId sütununa başvuran ve cihazı kaydeden kullanıcının kimliği. |
| RowLastModifiedDateTimeUTC |Bu kaydın son değiştirildiği tarih. |
| ProcessorArchitecture |İşlemci mimarisi. |
| DeviceAction |Yapılan son cihaz eylemi, Şimdilik yoksayın. |
| Üretici |Cihazın üreticisi. |
| Model |Cihazın modeli. |
| LastPolicyUpdateUtc |Cihazda ilkenin güncelleştirildiği son an. |
| LastExchangeStatusUtc |Cihazın Exchange ile son eşitlendiği an. |

## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

**MdmDeviceInventoryHistories** varlığı, MDM ile yönetilen cihazların envanter verileri için son 90 günlük anlık görüntülerini barındırır. DateKey sütunu, satır için günü gösterir. Bazı özellikler tüm cihazlarda uygulanamayabilir veya doldurulamayabilir, o nedenle daha fazla ayrıntı için bu sayfadan yardım alın. Daha fazla bilgi için bkz. [Microsoft Intune’da envanterli cihazlarınızı anlama](https://docs.microsoft.com/Intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-Intune).

| Özellik  | Description |
|---------|------------|
| DateKey | Günü gösteren tarih tablosuna başvuru. |
| DeviceKey |Veri ambarındaki cihazın benzersiz tanımlayıcısı - vekil anahtar. Bu, Intune cihaz kimliğini barındıran Cihaz tablosuna bir başvurudur. |
| DeviceModel |Cihazın modeli. |
| İşletim sistemi |Cihazın işletim sistemi. |
| DeviceName |Cihaz adlandırmaya izin veren platformlardaki cihaz adı. Buna izin vermeyen platformlarda ise Intune, diğer özelliklerden bir ad oluşturur. Bu öznitelik tüm cihazlarda kullanılabilir olamaz. |
| SoftwareVersion |Bu, çoğu zaman işletim sistemi sürümüdür ancak Apple platformlarında işletim sistemi sürümünden farklıdır. |
| Imei |IMEI numarası |
| HardwareInventoryTimeUtc |Cihaz için envanterin ilk raporlandığı an. |
| InventoryModifiedTimeUtc |Bu anlık görüntü alındığında envanterin depolandığı son an. |
| InventoryReportingTimeUtc |Cihaz için envanterin ilk toplandığı an. |
| ExchangeActiveSyncId |Exchange ActiveSync Cihaz Kimliği. |
| ComputerSystemDescription |Sistem açıklaması. |
| ComputerSystemName |Sistem Adı. |
| ComputerSystemManufacturer |Sistem Üreticisi. |
| ComputerSystemModel |Sistem Modeli. |
| UserName |Kullanıcı adı. |
| OSType |İşletim Sistemi Türü. |
| OSCaption |İşletim Sistemi Açıklamalı Alt Yazısı. |
| OSName |İşletim Sistemi Adı. |
| OSManufacturer |İşletim Sistemi Üreticisi. |
| OSProductSuite |İşletim Sistemi Ürün Paketi. |
| OSProductType |İşletim Sistemi Ürün Türü. |
| Yerel Ayar |İşletim Sistemi Yerel Ayarı. |
| PhysicalMemoryCapacity |Fiziksel Bellek Kapasitesi (bayt cinsinden). |
| PhysicalMemoryRemovable |Çıkarılabilir Fiziksel Bellek (bayt cinsinden). |
| SystemEnclosureChassisTypesInnerText |Cihaz için sistem gövdesi türünü tanımlar. Sayılar aşağıdaki değerleri gösterir:  <br>0 veya Boş = Bilinmiyor   <br>1 = Masaüstüdür   <br>2 = Dizüstüdür  <br>3 = İş İstasyonudur  <br>4 = Kuruluş Sunucusudur  <br>100 = Telefondur  <br>101 = Tablettir  <br>102/103 = Başka bir bilinmeyen Mobil cihaz türü |
| SystemEnclosureModel |Sistem Kutusu modeli. |
| SystemEnclosureSerialNumber |Sistem Kutusu Seri numarası. |
| NetworkAdapterConfigurationText |Ağ bağdaştırıcısından yapılandırma metni. |
| MacAddress |MAC adresi. |
| SmsID |Intune cihaz kimliği. |
| CertExpiry |MDM yönetim sertifikasının sona erme tarihi. |
| DeviceClientAgentVersion |İstemci Aracısı Sürümü. |
| DeviceClientID |Cihaz İstemci Kimliği. |
| SerialNumber |Seri Numarası. |
| DeviceManufacturer |Cihaz Üreticisi. |
| DMVersion |DM sürümü. |
| FirmwareVersion |Üretici Yazılımı Sürümü. |
| HardwareVersion |Donanım Sürümü. |
| PlatformType |Platform Türü. |
| ProcessorLevel |İşlemci düzeyi. |
| ProcessorRevision |İşlemci Düzeltmesi. |
| Ürün |Ürün. |
| ProductVersion |Ürün sürümü. |
| OEM |Özgün Ekipman üreticisi. |
| DeviceBuildVersion |Cihaz Derleme sürümü. |
| Meid |Mobil ekipman tanımlayıcısı. |
| PhoneNumber |Telefon numarası. |
| SubscriberCarrierNetwork |Operatör Ağ Adı. |
| CellularTechnology |Operatör Ağ Türü (CDMA/GSM). |
| Imsi |IMSI numarası. |
| JailBroken |Cihazda Jailbreak veya Kök belirtme uygulandıysa True şeklindedir. |
| IsActivationLockEnabled |Etkinleştirme Kilidi etkinse True şeklindedir |
| DeviceType |Cihaz Türü |
| IsSupervised |Denetimli |
| DeviceDisplayNumberOfColors |Cihaz ekranı Renk Sayısı |
| HorizontalResolution |Cihaz yatay ekran çözünürlüğü |
| VerticalResolution |Cihazın dikey ekran çözünürlüğü |
| StorageFree |Boş depolama alanı (bayt cinsinden) |
| StorageTotal |Toplam depolama alanı (bayt cinsinden) |
| ProgramFree |Boş Program belleği (bayt cinsinden) |
| ProgramTotal |Toplam Program belleği (bayt cinsinden) |
| RemovableStorageFree |Boş çıkarılabilir depolama alanı (bayt cinsinden) |
| RemovableStorageTotal |Toplam çıkarılabilir depolama alanı (bayt cinsinden) |
| DeviceMemoryDeviceCapacity |Cihaz bellek kapasitesi |
| DeviceMemoryAvailableDeviceCapacity |Cihaz belleğinin kullanılabilir kapasitesi |
| DeviceOSVersion |İşletim Sistemi Sürümü |
| DeviceOSPlatform |İşletim Sistemi platformu |
| DeviceOSLanguage |İşletim Sistemi Dili |
| PasswordMaxAttemptsBeforeWipe |Cihaz silinmeden önce izin verilen parola denemesi üst sınırı |
| PasswordMinComplexChars |Parolada olması gereken karmaşık karakter sayısı alt sınırı |
| PasswordMinLength |Gereken en düşük parola uzunluğu |
| PasswordHistory |Parola - Kabul edilmeyen eski şifre alt sınırı |
| PasswordEnabled |Parola - Etkin? |
| PasswordExpiration |Parola - Sona erme tarihi. |
| AllowRecoveryPassword |Parola kurtarmaya izin verin. |
| PasswordAutoLockTimeout |Parola - Otomatik kilit zaman aşımı. |
| PasswordType |Parola Türü. |
| BacklightACTimeout |Bir güç kaynağına bağlıyken arka ışık zaman aşımı. |
| BacklightBatTimeout |Pilde arka ışık zaman aşımı. |
| PowerBackupPercent |Güç yedekleme yüzdesi. |
| BatteryPercent |Kalan pil yüzdesi. |
| PlatformID |Platform kimliği. |
| ExchangeDeviceID |Exchange Cihaz Kimliği. |
| SmsProcessorDescription |İşlemci açıklaması. |
| OwnerEmailAddress |Sahibin e-posta adresi. |
| DeviceOSName |İşletim Sistemi Adı. |
| WifiMac |WIFI Mac adresi. |
| EthernetMac |Ethernet MAC adresi. |
| RequireEncryption |Cihazın şifreli olup olmadığını gösterir. |
| ActivationLockBypassCode |Etkinleştirme kilidi Atlama kodu. |

## <a name="applicationinventory"></a>ApplicationInventory

**ApplicationInventory** varlığı, envanter toplandığı anda cihazda bulunan uygulamaları listeler.

| Özellik  | Description |
|---------|------------|
| DeviceKey |Cihazlar tablosuna başvuru. |
| ApplicationKey |? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
| ApplicationName |? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
| ApplicationVersion |? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
| BundleSize |? (ExchangeDeviceService\DeviceApplication konumundan kopyalandı). |
