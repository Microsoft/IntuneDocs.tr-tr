---
title: "Windows 10 ilke ayarları | Microsoft Intune"
description: "Kayıtlı Windows 10 masaüstü bilgisayarları ve Windows 10 mobil cihazlarında yerleşik ve özel ayarları yapılandırmanıza yardımcı olması için, bu konu başlığı altında listelenen ilke ayarlarını kullanın."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b8522406a3c73746b09616c3ec917464cf751312
ms.openlocfilehash: 6e482beb5e2edce648ecb6f1821baa6214fa0f2f


---

# Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları

Bu konu, Windows 10 cihazlarını yönetmek için kullanabileceğiniz Intune ilke ayarlarını anlamanıza yardımcı olacak bilgiler içermektedir. Kaydedilmiş Windows 10 Desktop ve Windows 10 Mobile cihazlarının yerleşik ve özel ayarlarını yapılandırmak için bu konuyu [Cihazlarınızdaki ayarları ve özellikleri Microsoft Intune ilkeleriyle yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) bölümündeki yordamlarla birlikte okuyun. Bu ilkeleri [Intune bilgisayarı istemci yazılımı](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune) çalıştıran bilgisayarlarla kullanamazsınız.

İki ilke türünden birini seçebilirsiniz:

- **Özel ilke** - Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel ilkesini** kullanın. Windows 10, [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok ayarı kullanıma sunar.
- **Genel yapılandırma ilkesi** - Microsoft Intune ile sağlanan yerleşik listeden ayar seçmek istediğinizde bu ilke türünü kullanın.

## Özel ilke ayarları

Özel bir ilkede aşağıdaki ayarları sağlayın:

## &nbsp;&nbsp;&nbsp;Genel

Intune konsolunda tanımanıza yardımcı olması için bu ilke için bir ad ve isterseniz bir açıklama girin.

## &nbsp;&nbsp;&nbsp;OMA-URI ayarları

Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu konuda bulunan [Windows 10 URI ayarları başvurusunu](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) kullanın: 

- **Ayar adı** - Ayar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.
- **Ayar açıklaması** - İsterseniz ayar için bir açıklama girin.
- **Veri türü** - Aşağıdakilerden birini seçin:
    - **Dize**
    - **Dize (XML)**
    - **Tarih ve saat**
    - **Tamsayı**
    - **Kayan nokta**
    - **Boole değeri**
- **OMA-URI (büyük/küçük harfe duyarlı)** - Bir ayarını girmek istediğiniz OMA-URI’yi belirtin.
- **Değer** - Girdiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.

### Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)

## Windows 10 URI ayarları
Bir **Windows 10 Özel İlkesi** ile yapılandırabileceğiniz OMA-URI ayarları hakkında bilgi edinmek için bu bölümü kullanın.

## &nbsp;&nbsp;&nbsp;İlke

|İlke adı ve URI|Ayrıntılar|
|---------------|------------|-----------|
|**Otomatik Güncelleştirmeye İzin Ver**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Yalnızca masaüstü<br>**Veri türü:** Tamsayı<br />**Değerler:** **0** - **5** (varsayılan: **1**)|
|**Yükleme Gününü Zamanlama**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Yalnızca mobil<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazar<br>**2** - Pazartesi<br>**3** - Salı<br>**4** - Çarşamba<br>**5** - Perşembe<br>**6** - Cuma<br>**7** - Cumartesi|
|**Yükleme Saatini Zamanlama**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – **23** saat (**0** gece yarısıdır) (varsayılan: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - kullanıcı parola yetkisiz kullanım süresi zamanlayıcısını ayarlayamaz; değer “her defasında” olarak ayarlanır<br>**1** - kullanıcı, parola yetkisiz kullanım süresi zamanlayıcısını ayarlayabilir (varsayılan)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – **Wi-Fi bağlantısı kullanılmasına** izin verme.<br>**1** –**Wi-Fi bağlantısı kullanılmasına izin ver** (varsayılan)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Masaüstü ve mobil<br>**Veri türü:** Tamsayı<br />**Değerler:** **0** – İnternet Paylaşımına izin verme, **1** – İnternet Paylaşımına izin ver (varsayılan)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – MDM tarafından sağlanan dışında bir Wi-Fi bağlantısına izin verilmez.<br>**1** – Önceden MDM tarafından sağlananlar dışında yeni ağ SSID’leri eklenmesine izin verilir (varsayılan)|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Masaüstü ve mobil<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – İzin verilmiyor (yalnızca Kurumsal)<br>**1** – Sınırlı<br>**2** – Tam (varsayılan)<br>**3** - Tam ve tanılama bilgileri|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – İzin verilmiyor<br>**1**- Yalnızca ayarlar (varsayılan)<br>**2**- Ayarlar ve deneme|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hırsızlık Önleme moduna izin verme<br>**1** Kullanıcı tercihi (varsayılan)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hücresel şebeke üzerinden VPN’ye izin verilmez<br>**1** – VPN, hücresel şebeke de dahil tüm bağlantıları kullanır (varsayılan)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Kullanıcının Bluetooth’u açmasına izin verilmez.<br>**1** – Ayrılmış. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (MDM için Windows Phone 8.1, EAS, Windows 10 masaüstü veya Windows 10 Mobile’da desteklenmez)<br>**2** - İzin verilir. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (varsayılan)|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Dolaşıma izin verme **1** – Dolaşıma izin ver (varsayılan)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** (varsayılan), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0**, **1** (varsayılan)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** (varsayılan), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** (varsayılan), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** (varsayılan), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0**, **1** (varsayılan)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** (varsayılan), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** (varsayılan), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – İzin verme<br>Açık Genişletilmiş Sözlük kapalıdır.<br>Kullanıcı şunları yapamaz:<br>-Yeni bir Açık Genişletilmiş Sözlük ekleme<br />-Yeni bir arama tümleştirme yapılandırma dosyası ekleme<br>-Bulut aday özelliğini kullanma<br>-Kullanıcı tarafından kaydedilen sözcüğü gönderme.<br>**1** - İzin ver<br>Açık Genişletilmiş Sözlük eklenebilir ve varsayılan olarak kullanılabilir. Ayrıca, arama tümleştirme işlevi varsayılan olarak kullanılabilir.<br>Kullanıcı şunları yapabilir:<br>Bulut aday özelliğini kullanma.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hatalı dönüştürme günlüğü kapalıdır.<br>**1** - Hatalı dönüştürme günlüğü açık (varsayılan)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez **1** – izin verilir (varsayılan)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - Shift JIS karakterleri dışında tümü filtrelenir|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br />**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - JIS0208 karakterleri dışında tümü filtrelenir|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - JIS0208 karakterleri veya EUDC karakterleri dışında tümü filtrelenir|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Katı, yetişkinlere yönelik içeriğe karşı en yüksek filtreleme<br>**1** – Orta, yetişkinlere yönelik içeriğe karşı orta düzeyli filtreleme (geçerli arama sonuçları filtrelenmez - varsayılan)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**Başlatmaya Zorlama Boyutu**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - kullanıcı boyut değişikliğine izin ver (varsayılan)<br>**1** - tam olmayan ekranı zorla<br>**2** - tam ekranı zorla|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0**: Yükseltmeyi erteleme (geçerli dal olan CB’de kal - varsayılan)<br>**1**: Güncelleştirme ve yükseltmelerin ertelenmesini etkinleştir (Cihaz, geçerli iş dalı olan CBB’nin kurallarına uyar)<br />Ayrıntılar için bkz.<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Masaüstü ve mobil<br>**Açıklama**: Yazılım güncelleştirmelerini 4 haftaya kadar erteleme ilkesi<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0**: Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**-**4**: Yazılım güncelleştirmelerinin erteleneceği hafta sayısı.<br />Ayrıntılar için bkz.<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Masaüstü ve mobil<br>**Açıklama**: Özellik yükseltmelerini 8 aya kadar erteleme ilkesi<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0**: Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**-**8**: Özellik yükseltmelerinin erteleneceği ay sayısı.<br />Ayrıntılar için bkz.<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Masaüstü ve mobil<br>**Açıklama:** Bir cihazın 5 hafta boyunca güncelleştirme ve yükseltme almayı durdurmasını sağlar.<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0**: Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**: Güncelleştirmeleri ve yükseltmeleri duraklat (5 hafta sonra süresi dolar)|

## &nbsp;&nbsp;&nbsp;Windows Defender

|İlke adı ve URI|Ayrıntılar|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Tüm dosyaları izle (varsayılan)<br>**1** – Gelen dosyaları izle<br>**2** – Giden dosyaları izle|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - **90** – Kötü amaçlı yazılımın ne kadar süre tutulacağını belirtir<br>**Varsayılan:** **0** – sonsuza kadar karantina klasöründe tutar ve otomatik olarak kaldırmaz|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**1** – Hızlı tarama (varsayılan)<br>**2** - Tam tarama|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazartesi<br>**2** - Salı<br>**3** - Çarşamba<br>**4** - Perşembe<br>**5** - Cuma<br>**6** - Cumartesi<br>**7** - Pazar<br>**8** – Zamanlanmış tarama yok|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - 00:00<br>**60** – 1:00<br>**120** – 2:00 (varsayılan)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Bakım penceresi|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Yalnızca masaüstü<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - 00:00<br>**60** – 1:00<br>**120** – 2:00 (varsayılan)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** - **100** (varsayılan: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br>**Değerler:** **0** – izin verilmez (varsayılan), **1** – izin verilir|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez (varsayılan), **1** – izin verilir|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan) – İzin verilir olarak ayarlanırsa, RTP açık olduğunda da çalışır|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Bir aralıkta imza denetleme<br>**1** - Saatte bir imzaları denetle<br>**2** – Her 2 vb. saatte bir denetle<br>**24** - Her gün denetle<br>**Varsayılan değer:** 8 – Her 8 saatte bir denetle|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – izin verilmez, **1** – izin verilir (varsayılan)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Her zaman sor (varsayılan)<br>**1** – Güvenli örnekleri otomatik olarak gönder<br>**2** – Hiçbir zaman gönderme<br>**3** – Tüm örnekleri otomatik olarak gönder|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br>*&lt;noktalı virgülle ayrılmış uzantılar listesi&gt;* Örn. **obj;lib**<br>**Varsayılan:** Hiçbir uzantı dışlanmaz|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br />*&lt;noktalı virgülle ayrılmış yollar listesi&gt;*<br />Örnek: **c:\test;c:\test1.exe**<br />**Varsayılan değer:** Hiçbir yol dışlanmaz|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br>*&lt;noktalı virgülle ayrılmış yollar listesi&gt;*<br>Örnek: **c:\test.exe;c:\test1.exe**<br>**Varsayılan değer:** Hiçbir işlem dışlanmaz|

## &nbsp;&nbsp;&nbsp;Edge tarayıcısı

|İlke adı ve URI|Ayrıntılar|
|---------------|------------|-----------|
|**Tarayıcıya İzin Verme**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0**: tarama kapalı, **1**: tarama açık (varsayılan)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0**: Önerileri gösterme, **1**: Önerileri göster (varsayılan)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0**: Devre dışı (intranet sitelerini Microsoft Edge tarayıcısında aç - varsayılan)<br>**1**: Etkin (intranet sitelerini Internet Explorer'da aç).|
|**Do Not Track’e İzin Verme**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Devre Dışı (DNT gönderilmez - varsayılan), **1** – Etkin (DNT gönder)|
|**SmartScreen’i Yapılandırma**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – İzin verme, **1** – İzin ver (varsayılan)|
|**Açılır Pencerelere İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Açılır pencereleri engelle (varsayılan), **1** – Açılır pencerelere izin ver|
|**Tanımlama Bilgilerine İzin Verme**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Tüm web sitelerinin tanımlama bilgilerine izin ver (varsayılan)<br>**1** – Yalnızca üçüncü taraf tanımlama bilgilerini engelle<br>**2** – Tüm tanımlama bilgilerini engelle|
|**Parola Kaydetmeye İzin Verme**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Parola yöneticisi devre dışı; <br>**1** – Parola yöneticisi etkin (varsayılan)|
|**Otomatik Doldurma’ya izin ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Devre dışı (varsayılan), **1** – Etkin|
|**Enterprise Site Listesi Yapılandırma**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:<br>**0** – Yapılandırılmadı<br>**1** – Yapılandırıldıysa, IE’nin kurumsal mod site listesini kullan (varsayılan)<br>**2** – Kurumsal site listesinin konumunu belirt|

## Genel yapılandırma ilkesi ayarları

Kaydedilmiş Windows 10 Desktop ve Windows 10 Mobile cihazlarının yerleşik ayarlarını yapılandırmak için Microsoft Intune Windows 10 için **genel yapılandırma ilkesini** kullanın. 

## &nbsp;&nbsp;&nbsp;Parola

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Cihazların kilidini açmak için parola gerektir**|-|
|**Gerekli parola türü**|Parolanın yalnızca sayısal mı, yoksa alfasayısal mı olacağını belirtir|
|**Gerekli parola türü** - **Minimum karakter kümesi sayısı**|Küçük harfler, büyük harfler, rakamlar ve semboller şeklinde dört karakter kümesi vardır. Bu ayar, parolanın bu kümelerden kaçını içermesi gerektiğini belirtir.|
|**Minimum parola uzunluğu**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Windows 10 çalıştıran cihazlar için: Cihazda BitLocker etkinse, belirttiğiniz oturum açma sayısından sonra cihaz BitLocker kurtarma moduna alınır. Cihazda BitLocker etkin değilse, bu ayar uygulanmaz.<br>Windows 10 Mobile çalıştıran cihazlar için: Belirttiğiniz oturum açma sayısından sonra cihaz silinir.|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.|
|**Parola geçmişini anımsa**|Son kullanıcının daha önce kullanılmış parolalar oluşturmasını kısıtlamak isteyip istemediğinizi belirtir.|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Cihazın hatırladığı önceden kullanılmış parola sayısını belirtir.|
|**Cihaz boş bir durumdan döndürüldüğünde parola iste**|Etkinleştirilirse, cihazın kilidini açmak için kullanıcının bir parola girmesi gerekir. (Yalnızca Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Şifreleme

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Cihazda şifrelemeyi gerektir**|Hedeflenen cihazlarda şifrelemeyi etkinleştirin.<br>(Yalnızca Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Sistem

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Ekran yakalamaya izin ver**|Kullanıcının cihaz ekranını bir resim olarak yakalamasına olanak sağlar. (Yalnızca Windows 10 Mobile)|
|**Elle kayıt kaldırmaya izin ver**|Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.|
|**Elle kök sertifikası yüklemeye izin ver**|Windows 10 Mobile için geçerlidir|
|**Microsoft'a tanılama ve kullanım verilerinin gönderilmesine izin ver**|Olası değerler şunlardır:<br><br>**Hayır** - Microsoft’a hiç veri gönderilmez<br>**Temel** - Microsoft’a sınırlı bilgi gönderilir<br>**Gelişmiş** - Microsoft’a gelişmiş tanılama bilgileri gönderilir<br>**Tam (önerilen)** - **Gelişmiş** ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir|


## &nbsp;&nbsp;&nbsp;Hesap ve eşitleme

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Microsoft Hesabına izin ver**|Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.|
|**Microsoft olmayan hesapların elle eklenmesine izin ver**|Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.|
|**Microsoft hesapları için ayarları eşitlemeye izin ver**|Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin.|

## &nbsp;&nbsp;&nbsp;Microsoft Edge

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Web tarayıcısına izin ver**|Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verin.<br>(Yalnızca Windows 10 Mobile)|
|**Adres çubuğunda arama önerilerine izin ver**|Siz arama tümcecikleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.|
|**Internet Explorer'a intranet trafiği göndermeye izin ver**|Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar.<br>(Yalnızca Windows 10 masaüstü)|
|**İzleme özelliğine izin ver**|Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine Do Not Track (İzleme) üst bilgileri gönderecek şekilde yapılandırır.|
|**SmartScreen’i etkinleştir**|-|
|**Etkin betik yazmaya izin ver**|Microsoft Edge tarayıcısında Javascript gibi betiklerin çalıştırılmasına izin verir.|
|**Açılır pencerelere izin ver**|Yalnızca Windows 10 Desktop için geçerlidir|
|**Tanımlama bilgilerine izin ver**|-|
|**Otomatik Doldurma’ya izin ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.<br>(Yalnızca Windows 10 masaüstü)|
|**Parola Yöneticisi’ne izin ver**|Microsoft Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.|
|**Kurumsal Mod site listesi konumu**|Kurumsal modda açılacak web siteleri listesinin nerede olduğunu belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü)|

## &nbsp;&nbsp;&nbsp;Uygulamalar

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Uygulama mağazasına izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|



## &nbsp;&nbsp;&nbsp;Hücresel

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Veri dolaşımına izin ver**|Verilere erişirken ağlar arasında dolaşıma izin verin.|
|**Hücresel veri üzerinden VPN'ye izin ver**|Cihazın cep telefonu şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.|
|**Hücresel veri üzerinden VPN dolaşımına izin ver**|Cihazın cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.|

## &nbsp;&nbsp;&nbsp;Donanım

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Kameraya izin ver**|-|
|**Çıkarılabilir depolama birimine izin ver**|Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir.|
|**Wi-Fi'a izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**İnternet paylaşımına izin ver**|Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.|
|**Elle Wi-Fi yapılandırmasına izin ver**|Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin.<br>(Yalnızca Windows 10 Mobile)|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.|
|**Coğrafi konuma izin ver**|Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.|
|**NFC'ye izin ver**|Cihazın Yakın Alan İletişimi özelliklerini kullanmasına izin verir.|
|**Bluetooth'a izin ver**|-|
|**Bluetooth bulunabilirlik moduna izin ver**|Bu cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.|
|**Bluetooth reklamlarına izin ver**|Cihazların Bluetooth üzerinden reklam almasına izin verir.|
|**Telefon sıfırlamaya izin ver**|Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler.|
|**USB bağlantısına izin ver**|Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler.|
|**AntiTheft modunu etkinleştir**|Windows AntiTheft modunun etkin olup olmadığını yapılandırın.|

## &nbsp;&nbsp;&nbsp;Özellikler

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Ses kaydetmeye izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Cortana’ya izin ver**|Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.|
|**İşlem merkezi bildirimlerine izin ver**|Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın.<br>(Yalnızca Windows 10 Mobile)|

## &nbsp;&nbsp;&nbsp;Windows Defender

Tüm ayarlar yalnızca Windows 10 masaüstüne yöneliktir.

|Ayar adı|Ek bilgiler (gerekliyse)|
|-|-|
|**Gerçek zamanlı izlemeye izin ver**|Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir.|
|**Davranış izlemeye izin ver**|Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar.|
|**Ağ Denetleme Sistemi'ni Etkinleştir**|Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur.|
|**Tüm indirmeleri tara**|Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.|
|**Betik taramaya izin ver**|Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.|
|**Dosya ve program etkinliğini izle**|Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin vermek için bu ayarı etkinleştirin.|
|**Çözümlenen kötü amaçlı yazılımın izleneceği gün sayısı**|Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. |
|**İstemci UI erişimine izin ver**|Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler.<br>Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.|
|**Günlük hızlı tarama zamanla**|Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.|
|**Sistem taraması zamanla**|Seçtiğiniz gün ve saatte düzenli olarak gerçekleştirilecek tam veya hızlı bir sistem taraması zamanlamanıza olanak sağlar.|
|**Tarama sırasında CPU kullanımını sınırla**|Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar|
|**Arşiv dosyalarını tara**|Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.|
|**E-posta iletilerini tara**|Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.|
|**Çıkarılabilir sürücüleri tara**|Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.|
|**Eşlenen ağ sürücülerini tara**|Defender’ın eşlenen ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**Paylaşılan ağ klasörlerinden açılan dosyaları tara**|Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**İmza güncelleştirme aralığı**|Defender’ın yeni imza dosyalarını denetleme aralığını belirtin.|
|**Bulut korumasına izin ver**|Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verin veya bunu engelleyin. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.|
|**Kullanıcılardan örnek göndermelerini iste**|Kötü amaçlı olup olmadıklarını saptamak için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler.|
|**Olası İstenmeyen Uygulama Algılama**|Bu ayar, kayıtlı Windows masaüstü cihazlarını, Windows Defender tarafından olası istenmeyen yazılım şeklinde sınıflandırılan yazılımları çalıştırmaya karşı korumak üzere kullanılabilir. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya ve klasörler**|Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekleyin. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya uzantıları**|Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak işlemler**|Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.| 


## &nbsp;&nbsp;&nbsp;Updates

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|---------------|
|**Otomatik güncelleştirmelere izin ver**|Otomatik güncelleştirmelere izin vermek bu ayarı etkinleştirin. Ardından, güncelleştirme davranışını denetlemek için aşağıdaki ayarlardan birini yapılandırın:<br />**İndirmeyi bildir**<br />**Bakım sırasında otomatik olarak yükle**<br />**Bakım sırasında otomatik olarak yükle ve yeniden başlat**<br />**Zamanlanan tarihte otomatik yükle ve yeniden başlat** **Not:** Bu seçenek belirtildiğinde şu ayarları yapılandırabilirsiniz: **Son kullanıcıya bildirimi önle** ve **Zamanlanmış güncelleştirmeler için yükleme gününü tanımla**.<br>(Yalnızca Windows 10 masaüstü)|
|**Yayın öncesi özelliklere izin ver**|Microsoft’un Windows 10 cihazlara sürüm öncesi ayarlar ve özellikler dağıtmasına imkan tanır. Yalnızca ayarlara izin vermeyi tercih edebilirsiniz; aksi takdirde tüm sürüm öncesi ayarlar ve özellikler yüklenir.|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)





<!--HONumber=Oct16_HO1-->


