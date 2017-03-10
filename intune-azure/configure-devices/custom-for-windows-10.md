---
title: "Windows 10 cihazlar için Intune özel ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows 10 özel profilinde kullanabileceğiniz ayarları öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 647415914fb0f44807eff7baf7a56ea3a382f027
ms.lasthandoff: 02/18/2017


---

# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 cihazları için özel cihaz ayarları

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel** profilini kullanın. Windows 10, [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok ayarı kullanıma sunar.

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](how-to-configure-custom-settings.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** dikey penceresinde **Ayarlar**’ı seçin.
3. **Özel OMA-URI Ayarları** dikey penceresinde, yeni değer eklemek için **Ekle**’ye tıklayın. Ayrıca, virgülle ayrılmış değerler (.csv) dosyasında yapılandırdığınız tüm değerlerin listesini oluşturmak için **Dışarı Aktar**’a da tıklayabilirsiniz.
4. Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu konu başlığı altındaki listeyi kullanın:
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
5. Bitirdiğinizde, **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.
Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="example"></a>Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilkeye örnek](./media/custom-policy-example.png)


## <a name="policy-settings"></a>İlke ayarları

|İlke adı ve URI|Ayrıntılar|
|---------------|------------|-----------|
|**Otomatik Güncelleştirmeye İzin Ver**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Yalnızca masaüstü<br>**Veri türü:** Tamsayı<br />**Değerler:** **0** - **5** (varsayılan: **1**)|
|**Yükleme Gününü Planla**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Yalnızca mobil<br>**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazar<br>**2** - Pazartesi<br>**3** - Salı<br>**4** - Çarşamba<br>**5** - Perşembe<br>**6** - Cuma<br>**7** - Cumartesi|
|**Yükleme Zamanını Planla**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – **23** saat (**0** gece yarısıdır) (varsayılan: **3**)|
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

## <a name="windows-defender-settings"></a>Windows Defender ayarları

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

## <a name="edge-browser-settings"></a>Edge tarayıcı ayarları

|İlke adı ve URI|Ayrıntılar|
|---------------|------------|-----------|
|**Tarayıcıya İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Yalnızca mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0**: tarama kapalı, **1**: tarama açık (varsayılan)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0**: Önerileri gösterme, **1**: Önerileri göster (varsayılan)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0**: Devre dışı (intranet sitelerini Microsoft Edge tarayıcısında aç - varsayılan)<br>**1**: Etkin (intranet sitelerini Internet Explorer'da aç).|
|**Do Not Track Özelliğine İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Devre Dışı (DNT gönderilmez - varsayılan), **1** – Etkin (DNT gönder)|
|**SmartScreen’i Yapılandır**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – İzin verme, **1** – İzin ver (varsayılan)|
|**Açılır Pencerelere İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Açılır pencereleri engelle (varsayılan), **1** – Açılır pencerelere izin ver|
|**Tanımlama Bilgilerine İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Tüm web sitelerinin tanımlama bilgilerine izin ver (varsayılan)<br>**1** – Yalnızca üçüncü taraf tanımlama bilgilerini engelle<br>**2** – Tüm tanımlama bilgilerini engelle|
|**Parola Kaydetmeye İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Masaüstü ve mobil<br />**Veri türü:** Tamsayı<br />**Değerler:**<br>**0** – Parola yöneticisi devre dışı; <br>**1** – Parola yöneticisi etkin (varsayılan)|
|**Otomatik Doldurmaya İzin Ver**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Yalnızca masaüstü<br />**Veri türü:** Tamsayı<br />**Değerler:** **0** – Devre dışı (varsayılan), **1** – Etkin|
|**Enterprise Site Listesini Yapılandır**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Yalnızca masaüstü<br />**Veri türü:** Dize<br />**Değerler:<br>**0** – Yapılandırılmadı<br>**1** – Yapılandırıldıysa, IE’nin kurumsal mod site listesini kullan (varsayılan)<br>**2** – Kurumsal site listesinin konumunu belirt|

