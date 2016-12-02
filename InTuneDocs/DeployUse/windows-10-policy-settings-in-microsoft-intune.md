---
title: "Windows 10 ilke ayarları | Microsoft Intune"
description: "Kayıtlı Windows 10 masaüstü bilgisayarları ve Windows 10 mobil cihazlarında yerleşik ve özel ayarları yapılandırmanıza yardımcı olması için, bu konu başlığı altında listelenen ilke ayarlarını kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
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
ms.sourcegitcommit: ad36bfd7b4f60626181ecaf27c51a9b108005979
ms.openlocfilehash: 8c970a4d1362def67e17da656b5e12e5bab2667b


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları

Bu konu, Windows 10 cihazlarını yönetmek için kullanabileceğiniz Intune ilke ayarlarını anlamanıza yardımcı olacak bilgiler içermektedir. Kaydedilmiş Windows 10 Desktop ve Windows 10 Mobile cihazlarının yerleşik ve özel ayarlarını yapılandırmak için bu konuyu [Cihazlarınızdaki ayarları ve özellikleri Microsoft Intune ilkeleriyle yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) bölümündeki yordamlarla birlikte okuyun. Bu ilkeleri [Intune bilgisayarı istemci yazılımı](/intune/get-started/windows-pc-management-capabilities-in-microsoft-intune) çalıştıran bilgisayarlarla kullanamazsınız.

İki ilke türünden birini seçebilirsiniz:

- **Özel ilke**: Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel ilkesini** kullanın. Windows 10, [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok ayarı kullanıma sunar.
- **Genel yapılandırma ilkesi**: Microsoft Intune ile sağlanan yerleşik listeden ayar seçmek istediğinizde bu ilke türünü kullanın.

## <a name="custom-policy-settings"></a>Özel ilke ayarları

Özel bir ilkede aşağıdaki ayarları sağlayın.

### <a name="general"></a>Genel

Intune konsolunda tanımanıza yardımcı olması için bu ilke için bir ad ve isterseniz bir açıklama girin.

### <a name="oma-uri-settings"></a>OMA-URI ayarları

Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu konuda bulunan [Windows 10 URI ayarları başvurusunu](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) kullanın:

- **Ayar adı**: Ayar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.
- **Ayar açıklaması**: İsterseniz ayar için bir açıklama girin.
- **Veri türü**: Aşağıdaki veri türleri arasından seçim yapın:
    - **Dize**
    - **Dize (XML)**
    - **Tarih ve saat**
    - **Tamsayı**
    - **Kayan nokta**
    - **Boole değeri**
- **OMA-URI (büyük/küçük harfe duyarlı)**: Bir ayarını girmek istediğiniz OMA-URI’yi belirtin.
- **Değer**: Girdiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.

### <a name="example"></a>Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilke örneği](./media/custom-policy-example.png)

## <a name="windows-10-uri-settings"></a>Windows 10 URI ayarları
Bir **Windows 10 Özel İlkesi** ile yapılandırabileceğiniz OMA-URI ayarları hakkında bilgi edinmek için bu bölümü kullanın.

### <a name="policy"></a>İlke

|İlke adı ve URI|Ayrıntılar|
|---------------|------------|-----------|
|**Otomatik Güncelleştirmeye İzin Ver**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Yalnızca masaüstü<br>**Veri türü:** Tamsayı<br />**Değerler:** **0** - **5** (varsayılan: **1**)|
|**Yükleme Gününü Planla**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Yalnızca mobil<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazar<br>**2** - Pazartesi<br>**3** - Salı<br>**4** - Çarşamba<br>**5** - Perşembe<br>**6** - Cuma<br>**7** - Cumartesi|
|**Yükleme Zamanını Planla**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** – **23** saat (**0**, gece yarısıdır) (varsayılan: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Kullanıcı parola yetkisiz kullanım süresi zamanlayıcısını ayarlayamaz; değer "her defasında" olarak ayarlanır<br>**1** - Kullanıcı, parola yetkisiz kullanım süresi zamanlayıcısını ayarlayabilir (varsayılan)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – **Wi-Fi bağlantısı kullanılmasına** izin verme<br>**1** –**Wi-Fi bağlantısı kullanılmasına izin ver** (varsayılan)|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Masaüstü ve mobil<br>**Veri türü:** Tamsayı<br />**Değerler<br>** **0** – İnternet paylaşımına izin verme <br> **1** – İnternet paylaşımına izin ver (varsayılan)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Yalnızca MDM ile yapılandırdığınız Wi-Fi bağlantılarına izin ver.<br>**1** – Önceden MDM tarafından oluşturulmuş SSID’lerin yanı sıra yeni ağ SSID’leri eklemeye izin verilir (varsayılan)|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Masaüstü ve mobil<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – İzin verilmez (yalnızca Kurumsal)<br>**1** – Sınırlı<br>**2** – Tam (varsayılan)<br>**3** - Tam ve tanılama bilgileri|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – İzin verilmiyor<br>**1**- Yalnızca ayarlar (varsayılan)<br>**2**- Ayarlar ve deneme|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hırsızlık Önleme moduna izin verme<br>**1** - Kullanıcı tercihi (varsayılan)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br>**1** – İzin veriliyor (varsayılan)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hücresel şebeke üzerinden VPN’ye izin verilmez<br>**1** – VPN, hücresel şebeke de dahil tüm bağlantıları kullanır (varsayılan)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Kullanıcının Bluetooth’u açmasına izin verilmez.<br>**1** – Ayrılmış. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (MDM için Windows Phone 8.1, EAS, Windows 10 masaüstü veya Windows 10 Mobile’da desteklenmez).<br>**2** - İzin verilir. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (varsayılan).|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – Dolaşıma izin verme<br> **1** – Dolaşıma izin ver (varsayılan)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** (varsayılan)<br> **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0**<br> **1** (varsayılan)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** (varsayılan)<br> **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** (varsayılan)<br> **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** (varsayılan)<br> **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0**<br> **1** (varsayılan)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** (varsayılan)<br> **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** (varsayılan)<br> **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – İzin verme.<br>Açık Genişletilmiş Sözlük kapalıdır.<br>Kullanıcı şunları yapamaz:<br>-Yeni bir Açık Genişletilmiş Sözlük ekleme.<br />-Yeni bir arama tümleştirme yapılandırma dosyası ekleme.<br>-Bulut aday özelliğini kullanma.<br>-Kullanıcı tarafından kaydedilen sözcüğü gönderme.<br>**1** - İzin ver<br>Açık Genişletilmiş Sözlük eklenebilir ve varsayılan olarak kullanılabilir. Ayrıca, arama tümleştirme işlevi varsayılan olarak kullanılabilir.<br>Kullanıcı şunları yapabilir:<br>-Bulut aday özelliğini kullanma.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hatalı dönüştürme günlüğü kapalı<br>**1** - Hatalı dönüştürme günlüğü açık (varsayılan)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor <br>**1** – İzin veriliyor (varsayılan)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - Shift JIS karakterleri dışında tümü filtrelenir|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br />**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - JIS0208 karakterleri dışında tümü filtrelenir|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - JIS0208 karakterleri veya EUDC karakterleri dışında tümü filtrelenir|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Katı, yetişkinlere yönelik içeriğe karşı en yüksek filtreleme<br>**1** – Orta, yetişkinlere yönelik içeriğe karşı orta düzeyli filtreleme (geçerli arama sonuçları filtrelenmez) (varsayılan)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**Başlatmaya Zorlama Boyutu**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Kullanıcı boyut değişikliğine izin ver (varsayılan)<br>**1** - Tam olmayan ekranı zorla<br>**2** - Tam ekranı zorla|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Yükseltmeyi erteleme (geçerli dal olan CB’de kal) (varsayılan)<br>**1** - Güncelleştirme ve yükseltmelerin ertelenmesini etkinleştir (cihaz, geçerli iş dalı olan CBB’nin kurallarına uyar)<br />Ayrıntılar için bkz.<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Masaüstü ve mobil<br>**Açıklama**: Yazılım güncelleştirmelerini dört haftaya kadar erteleme ilkesi<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** - Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**-**4** - Yazılım güncelleştirmelerinin erteleneceği hafta sayısı<br />Ayrıntılar için bkz.<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Masaüstü ve mobil<br>**Açıklama**: Özellik yükseltmelerini sekiz aya kadar erteleme ilkesi<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**-**8** - Özellik yükseltmelerinin erteleneceği ay sayısı<br />Ayrıntılar için bkz.<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Masaüstü ve mobil<br>**Açıklama:** Bir cihazın beş hafta boyunca güncelleştirme ve yükseltme almayı durdurmasını sağlar.<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Güncelleştirmeleri hemen uygula (varsayılan)<br>**1** - Güncelleştirmeleri ve yükseltmeleri duraklat (beş hafta sonra süresi dolar)|

### <a name="windows-defender"></a>Windows Defender

|İlke adı ve URI|Ayrıntılar|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br> **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Tüm dosyaları izle (varsayılan)<br>**1** – Gelen dosyaları izle<br>**2** – Giden dosyaları izle|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - **90** – Kötü amaçlı yazılımın ne kadar süre tutulacağını belirtir<br>**0** – Kötü amaçlı yazılımları sonsuza kadar karantina klasöründe tutar ve otomatik olarak kaldırmaz (varsayılan)|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**1** – Hızlı tarama (varsayılan)<br>**2** - Tam tarama|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazartesi<br>**2** - Salı<br>**3** - Çarşamba<br>**4** - Perşembe<br>**5** - Cuma<br>**6** - Cumartesi<br>**7** - Pazar<br>**8** – Zamanlanmış tarama yok|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - 00:00<br>**60** – 1:00<br>**120** – 2:00 (varsayılan)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Bakım penceresi|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Yalnızca masaüstü<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - 00:00<br>**60** – 1:00<br>**120** – 2:00 (varsayılan)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** - **100** (varsayılan: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br>**Değerler:<br>** **0** – İzin verilmiyor (varsayılan)<br> **1** – İzin veriliyor|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor (varsayılan)<br> **1** – İzin veriliyor|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan) - İzin veriliyor olarak ayarlandıysa RTP açık olduğunda da çalıştırılır|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Bir aralıkta imza denetleme<br>**1** - Saatte bir imzaları denetle<br>**2** – İki saatte bir denetle <br>**24** - Her gün denetle<br>**8** – Sekiz saatte bir denetle (varsayılan)|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verilmiyor<br> **1** – İzin veriliyor (varsayılan)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Her zaman sor (varsayılan)<br>**1** – Güvenli örnekleri otomatik olarak gönder<br>**2** – Hiçbir zaman gönderme<br>**3** – Tüm örnekleri otomatik olarak gönder|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br>*&lt;Noktalı virgülle ayrılmış uzantı listesi&gt;* Örnek: **obj;lib**<br>**Varsayılan -** Hiçbir uzantı dışlanmaz|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br />*&lt;Noktalı virgülle ayrılmış yol listesi&gt;*<br />Örnek: **c:\test;c:\test1.exe**<br />**Varsayılan -** Hiçbir yol dışlanmaz|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br>*&lt;Noktalı virgülle ayrılmış yol listesi&gt;*<br>Örnek: **c:\test.exe;c:\test1.exe**<br>**Varsayılan -** Hiçbir işlem dışlanmaz|

### <a name="edge-browser"></a>Edge tarayıcısı

|İlke adı ve URI|Ayrıntılar|
|---------------|------------|-----------|
|**Tarayıcıya İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** - Gözatma kapalı <br>**1** - Gözatma açık (varsayılan)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler<br>** **0** - Önerileri gösterme<br> **1** - Önerileri göster (varsayılan)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Devre dışı (intranet sitelerini Microsoft Edge tarayıcısında aç - varsayılan)<br>**1**: Etkin (intranet sitelerini Internet Explorer'da aç)|
|**Do Not Track Özelliğine İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – Devre dışı (DNT gönderilmez - varsayılan)<br> **1** – Etkin (DNT gönder)|
|**SmartScreen’i Yapılandır**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – İzin verme<br> **1** – İzin ver (varsayılan)|
|**Açılır Pencerelere İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:<br>** **0** – Açılır pencereleri engelle (varsayılan)<br> **1** – Açılır pencerelere izin ver|
|**Tanımlama Bilgilerine İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Tüm web sitelerinin tanımlama bilgilerine izin ver (varsayılan)<br>**1** – Yalnızca üçüncü taraf tanımlama bilgilerini engelle<br>**2** – Tüm tanımlama bilgilerini engelle|
|**Parola Kaydetmeye İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Parola Yöneticisi devre dışı <br>**1** – Parola Yöneticisi etkin (varsayılan)|
|**Otomatik Doldurmaya İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler**:<br> **0** – Devre dışı (varsayılan)<br> **1** – Etkin|
|**Enterprise Site Listesini Yapılandır**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:**<br>**0** – Yapılandırılmamış<br>**1** – Yapılandırılmışsa IE'nin kuruluş modu site listesini kullan (varsayılan)<br>**2** – Kuruluş site listesi için konum belirt|

## <a name="general-configuration-policy-settings"></a>Genel yapılandırma ilkesi ayarları

Kaydedilmiş Windows 10 masaüstü ve Windows 10 Mobile cihazlarının yerleşik ayarlarını yapılandırmak için Microsoft Intune Windows 10 için **genel yapılandırma ilkesini** kullanın.

### <a name="password"></a>Parola

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Cihazların kilidini açmak için parola gerektir**|-|
|**Gerekli parola türü**|Parolanın alfasayısal mı yoksa sayısal mı olacağını belirtir|
|**Gerekli parola türü** - **Minimum karakter kümesi sayısı**| Parolanın karakter kümelerinden (küçük harfler, büyük harfler, sayılar ve semboller) kaçını içereceğini belirtir|
|**En düşük parola uzunluğu**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**.|Windows 10 çalıştıran cihazlar için: Cihazda BitLocker etkinse, belirttiğiniz başarısız oturum açma sayısından sonra cihaz BitLocker kurtarma moduna alınır. Cihazda BitLocker etkin değilse, bu ayar uygulanmaz.<br>Windows 10 Mobile çalıştıran cihazlar için: Belirttiğiniz başarısız oturum açma sayısından sonra cihaz silinir.|
|**Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir|
|**Parola kullanım süresi (gün)**|Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir|
|**Parola geçmişini anımsa**|Son kullanıcının daha önce kullanılmış parolalar oluşturmasının kısıtlanıp kısıtlanmayacağını belirtir|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir|
|**Cihaz boş bir durumdan döndürüldüğünde parola iste**|Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir (yalnızca Windows 10 Mobile)|

### <a name="encryption"></a>Şifreleme

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Cihazda şifrelemeyi gerektir**|Hedeflenen cihazlarda şifrelemeyi etkinleştirir<br>(Yalnızca Windows 10 Mobile)|

### <a name="system"></a>Sistem

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Ekran yakalamaya izin ver**|Kullanıcının cihaz ekranını bir resim olarak yakalamasına olanak sağlar (yalnızca Windows 10 Mobile)|
|**Elle kayıt kaldırmaya izin ver**|Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar|
|**Elle kök sertifikası yüklemeye izin ver**|Windows 10 Mobile için geçerlidir|
|**Microsoft'a tanılama ve kullanım verilerinin gönderilmesine izin ver**|Olası değerler şunlardır:<br><br>**Hayır** - Microsoft’a hiç veri gönderilmez<br>**Temel** - Microsoft’a sınırlı bilgi gönderilir<br>**Gelişmiş** - Microsoft’a gelişmiş tanılama bilgileri gönderilir<br>**Tam (önerilen)** - **Gelişmiş** ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir|


### <a name="account-and-synchronization"></a>Hesap ve eşitleme

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Microsoft hesabına izin ver**|Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar|
|**Microsoft olmayan hesapların elle eklenmesine izin ver**|Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar|
|**Microsoft hesapları için ayarları eşitlemeye izin ver**|Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin|

### <a name="microsoft-edge"></a>Microsoft Edge

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Web tarayıcısına izin ver**|Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verir<br>(Yalnızca Windows 10 Mobile)|
|**Adres çubuğunda arama önerilerine izin ver**|Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar|
|**Internet Explorer'a intranet trafiği göndermeye izin ver**|Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar<br>(Yalnızca Windows 10 masaüstü)|
|**Do Not Track özelliğine izin ver**|Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine İzleme (DNT) üst bilgileri gönderecek şekilde yapılandırır|
|**SmartScreen’i etkinleştir**||
|**Etkin betik yazmaya izin ver**|Edge tarayıcısında JavaScript gibi betiklerin çalıştırılmasına izin verir|
|**Açılır pencerelere izin ver**|Yalnızca Windows 10 Desktop için geçerlidir|
|**Tanımlama bilgilerine izin ver**||
|**Otomatik Doldurmaya İzin Ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır<br>(Yalnızca Windows 10 masaüstü)|
|**Parola Yöneticisi’ne izin ver**|Microsoft Edge Parola Yöneticisi özelliğini etkinleştirir veya devre dışı bırakır|
|**Kurumsal Mod site listesi konumu**|Kurumsal modda açılan web siteleri listesinin nerede olduğunu belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü)|

### <a name="apps"></a>Uygulamalar

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Uygulama depolamaya izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|



### <a name="cellular"></a>Hücresel

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Veri dolaşımına izin ver**|Verilere erişirken ağlar arasında dolaşıma izin verin|
|**Hücresel veri üzerinden VPN'ye izin ver**|Cihazın cep telefonu şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler|
|**Hücresel veri üzerinden VPN dolaşımına izin ver**|Cihazın cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler|

### <a name="hardware"></a>Donanım

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Kameraya izin ver**|-|
|**Çıkarılabilir depolamaya izin ver**|Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir|
|**Wi-Fi bağlantısına izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**İnternet paylaşımına izin ver**|Cihazda İnternet bağlantısı paylaşımının kullanımına izin verir|
|**Elle Wi-Fi yapılandırmasına izin ver**|Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin<br>(Yalnızca Windows 10 Mobile)|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar|
|**Coğrafi konuma izin ver**|Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir|
|**NFC'ye izin ver**|Cihazın Yakın Alan İletişimi özelliklerini kullanmasına izin verir|
|**Bluetooth'a izin ver**|-|
|**Bluetooth bulunabilirlik moduna izin ver**|Bu cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar|
|**Bluetooth reklamlarına izin ver**|Cihazların Bluetooth üzerinden reklam almasına izin verir|
|**Telefon sıfırlamaya izin ver**|Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler|
|**USB bağlantısına izin ver**|Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler|
|**AntiTheft modunu etkinleştir**|Windows AntiTheft modunun etkin olup olmadığını yapılandırın|

### <a name="features"></a>Özellikler

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Ses kaydetmeye izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Cortana’ya izin ver**|Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın|
|**İşlem merkezi bildirimlerine izin ver**|Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın<br>(Yalnızca Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Tüm ayarlar yalnızca Windows 10 masaüstüne yöneliktir.

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Gerçek zamanlı izlemeye izin ver**|Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir|
|**Davranış izlemeye izin ver**|Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar|
|**Ağ İnceleme Sistemi'ni Etkinleştir**|Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur|
|**Tüm indirmeleri tara**|Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler|
|**Betik taramaya izin ver**|Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar|
|**Dosya ve program etkinliğini izle**|Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir|
|**Çözümlenen kötü amaçlı yazılımın izleneceği gün sayısı**|Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. |
|**İstemci UI erişimine izin ver**|Windows Defender kullanıcı arabiriminin kullanıcılardan gizlenip gizlenmediğini denetler.<br>Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.|
|**Günlük hızlı tarama zamanla**|Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar|
|**Sistem taraması zamanla**|Seçtiğiniz gün ve saatte düzenli olarak gerçekleştirilecek tam veya hızlı bir sistem taraması zamanlamanıza olanak sağlar|
|**Tarama sırasında CPU kullanımını sınırla**|Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar|
|**Arşiv dosyalarını tara**|Defender’ın .zip veya .cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.|
|**E-posta iletilerini tara**|Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir|
|**Çıkarılabilir sürücüleri tara**|Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar|
|**Eşlenen ağ sürücülerini tara**|Defender’ın eşlenen ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**Paylaşılan ağ klasörlerinden açılan dosyaları tara**|Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**İmza güncelleştirme aralığı**|Defender’ın yeni imza dosyalarını denetleme aralığını belirtir.|
|**Bulut korumasına izin ver**|Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir veya bunu engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.|
|**Kullanıcılardan örnek göndermelerini iste**|Kötü amaçlı olup olmadıklarını belirlemek için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler|
|**Olası İstenmeyen Uygulama Algılama**|Kayıtlı Windows masaüstü cihazlarını, Windows Defender tarafından olası istenmeyen yazılım şeklinde sınıflandırılan yazılımları çalıştırmaya karşı korur. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya ve klasörler**|Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya uzantıları**|Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak işlemler**|Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekler. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|


### <a name="updates"></a>Updates

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|---------------|
|**Otomatik güncelleştirmelere izin ver**|Otomatik güncelleştirmelere izin verir. Güncelleştirme davranışını denetlemek için aşağıdaki ayarlardan birini yapılandırın:<br />**İndirmeyi bildir**<br />**Bakım sırasında otomatik olarak yükle**<br />**Bakım sırasında otomatik olarak yükle ve yeniden başlat**<br />**Zamanlanan tarihte otomatik yükle ve yeniden başlat** Not: Bu seçenek belirtildiğinde şu ayarları yapılandırabilirsiniz: **Son kullanıcıya bildirimi önle** ve **Zamanlanmış güncelleştirmeler için yükleme gününü tanımla**.<br>(Yalnızca Windows 10 masaüstü)|
|**Yayın öncesi özelliklere izin ver**|Microsoft’un Windows 10 cihazlara sürüm öncesi ayarlar ve özellikler dağıtmasına imkan tanır. Yalnızca ayarlara izin vermeyi tercih edebilirsiniz; aksi takdirde tüm sürüm öncesi ayarlar ve özellikler yüklenir.|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Nov16_HO4-->


