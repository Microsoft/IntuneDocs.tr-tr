---
title: Microsoft Intune-Azure 'da cihazları yapılandırmak için Graph API 'Leri | Microsoft Docs
titleSuffix: ''
description: Windows 10 cihazlarında eşleşen Windows CSP ve dengeleme URI 'sine sahip tüm Graph API varlıkların bir listesini ve Microsoft Intune cihazları yapılandırırken daha yeni kullanıldığını görün. Paylaşılan bilgisayarlar, uç nokta koruması, Microsoft Defender Gelişmiş tehdit koruması, kimlik koruması, Windows 10 takımları, bilgi noktası ve Iş Windows Update için eşleşen API ve CSP 'ye bakın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c99c166713b9e3d8614ebe8f2756a586356c5b3b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490726"
---
# <a name="graph-apis-and-matching-windows-10-csps-used-in-intune"></a>Intune’da kullanılan Graph API’leri ve eşleşen Windows 10 CSP’leri

Microsoft Intune, Windows 10 ve üstünü çalıştıran cihazları (**ıntune** > **cihaz yapılandırması**) yapılandırmak için [Graph API varlıklarını](https://docs.microsoft.com/graph/api/resources/intune-graph-overview) (başka bir docs sitesini açar) kullanır. Graph API, cihazlarda yapılandırma ayarlarını okumak, ayarlamak, değiştirmek ve/veya silmek için yapılandırma hizmeti sağlayıcılarını (CSP) kullanır.

Bu liste şu şekilde geçerlidir:

- Windows 10 ve üzeri

Bu makalede, grafik varlıkları ve bunların eşleşen Windows 10 CSP 'Leri ve eşleme URI 'Leri listelenmektedir.

Bu bilgiler çeşitli senaryolar için yararlıdır. Örneğin, bkz. Intune tarafından kullanılan özellikler, bkz. özel OMA-URI yapılandırmalarına eklenecek ayarlar ve benzeri. 

## <a name="windows-10-csps"></a>Windows 10 CSP 'Leri

Windows 10 yapılandırma hizmeti sağlayıcıları hakkında daha fazla bilgi için bkz. [yapılandırma hizmeti sağlayıcısı başvurusu](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (başka bir docs sitesi açar).

## <a name="graph-api-properties-to-csp-mapping"></a>CSP eşleme Graph API Özellikler

Aşağıdaki listede, Windows 10 cihaz yapılandırması için Microsoft Intune tarafından kullanılan Graph API varlıkların çoğunluğu gösterilmektedir. Ayrıca buna karşılık gelen Windows 10 CSP ve konum URI 'sini de gösterir.

Aşağıdaki API 'Lerin Windows 10 sürümlerini görmek için, Windows 10 [yapılandırma hizmeti sağlayıcı başvurusunu](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) kullanın (başka bir docs sitesini açar).

### <a name="editionupgradeconfigurationlicense"></a>Sürümupgradeconfiguration. Lisans 
**CSP**:./Device/Vendor/MSFT/windowslisanslama  
**Konum URI 'si**:/Upgradesürümwithlicense

### <a name="editionupgradeconfigurationlicensetype"></a>Sürümupgradeconfiguration. LicenseType 
**CSP**:./Device/Vendor/MSFT/windowslisanslama  
**Konum URI 'si**:/Licensekeytype

### <a name="editionupgradeconfigurationproductkey"></a>Sürümupgradeconfiguration. ProductKey 
**CSP**:./Device/Vendor/MSFT/windowslisanslama  
**Konum URI 'si**:/Upgradesürümwithproductkey

### <a name="editionupgradeconfigurationwindowssmode"></a>Sürümupgradeconfiguration. WindowsSMode 
**CSP**:./Device/Vendor/MSFT/windowslisanslama  
**Konum URI 'si**:/SMode/SwitchingPolicy

### <a name="sharedpcconfigurationaccountmanagerpolicy"></a>SharedPCConfiguration. AccountManagerPolicy 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Deletionpolicy,/DiskLevelCaching,/ınactivethreshold,/Disklevelsilinmeye

### <a name="sharedpcconfigurationaccountmanagerpolicy-windows-holographic-for-business-edition-targeted-devices"></a>SharedPCConfiguration. AccountManagerPolicy (Windows holographic for Business Edition hedeflenen cihazlar) 
**CSP**:./Vendor/MSFT/AccountManagement  
**Konum URI 'si**:/Deletionpolicy,/Storagecapacitystartsilinmeyi,/Storagecapacitystopsilinmeye,/Profileınactivitythreshold

### <a name="sharedpcconfigurationallowedaccounts"></a>SharedPCConfiguration. AllowedAccounts 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Accountmodel

### <a name="sharedpcconfigurationallowlocalstorage"></a>SharedPCConfiguration. AllowLocalStorage 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/RestrictLocalStorage

### <a name="sharedpcconfigurationdisableaccountmanager"></a>SharedPCConfiguration. DisableAccountManager 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Enableaccountmanager

### <a name="sharedpcconfigurationdisableedupolicies"></a>SharedPCConfiguration. Disableeğitipolicies Ilkeleri 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Setedupolicies

### <a name="sharedpcconfigurationdisablepowerpolicies"></a>SharedPCConfiguration. DisablePowerPolicies 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Setpowerpolicies

### <a name="sharedpcconfigurationdisablesigninonresume"></a>SharedPCConfiguration. Disablesignınonözgeçmişi 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Signınonözgeçmişi

### <a name="sharedpcconfigurationenabled"></a>SharedPCConfiguration. Enabled 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Enablesharedpcmode

### <a name="sharedpcconfigurationidletimebeforesleepinseconds"></a>SharedPCConfiguration. ıdleepınseconds 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/ınactivethreshold

### <a name="sharedpcconfigurationkioskappdisplayname"></a>SharedPCConfiguration. KioskAppDisplayName 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Kioskmodeusertilegörüntümetni

### <a name="sharedpcconfigurationkioskappusermodelid"></a>SharedPCConfiguration. KioskAppUserModelId 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Kioskmodeaumıd

### <a name="sharedpcconfigurationlocalstorage"></a>SharedPCConfiguration. LocalStorage 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/RestrictLocalStorage

### <a name="sharedpcconfigurationmaintenancestarttime"></a>SharedPCConfiguration. MaintenanceStartTime 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/MaintenanceStartTime

### <a name="sharedpcconfigurationsetaccountmanager"></a>SharedPCConfiguration. SetAccountManager
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Enableaccountmanager

### <a name="sharedpcconfigurationsetedupolicies"></a>SharedPCConfiguration. SetEduPolicies 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Setedupolicies

### <a name="sharedpcconfigurationsetpowerpolicies"></a>SharedPCConfiguration. SetPowerPolicies 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Setpowerpolicies

### <a name="sharedpcconfigurationsigninonresume"></a>SharedPCConfiguration. Signınonözgeçmişi 
**CSP**:./Vendor/MSFT/sharedpc  
**Konum URI 'si**:/Signınonözgeçmişi

### <a name="windows10endpointconfigurationsmartscreenblockoverrideforfiles"></a>Windows10endpointconfiguration.smartScreenBlockOverrideForFiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/SmartScreen/PreventOverrideForFilesInShell

### <a name="windows10endpointprotectionconfigurationapplicationguardallowfilesaveonhost"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardAllowFileSaveOnHost 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/savefilestohost

### <a name="windows10endpointprotectionconfigurationapplicationguardallowpersistence"></a>Windows10EndpointProtectionConfiguration. Applicationguardallowkalıcılığı 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/allowkalıcılığı

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttolocalprinters"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardAllowPrintToLocalPrinters 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Kaydırma URI 'si**:/Settings/printingsettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttonetworkprinters"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardAllowPrintToNetworkPrinters 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Kaydırma URI 'si**:/Settings/printingsettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttopdf"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardAllowPrintToPDF 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Kaydırma URI 'si**:/Settings/printingsettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowprinttoxps"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardAllowPrintToXPS 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Kaydırma URI 'si**:/Settings/printingsettings

### <a name="windows10endpointprotectionconfigurationapplicationguardallowvirtualgpu"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardAllowVirtualGPU 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/allowvirtualgpu

### <a name="windows10endpointprotectionconfigurationapplicationguardblockclipboardsharing"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardBlockClipboardSharing 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/clipboardsettings

### <a name="windows10endpointprotectionconfigurationapplicationguardblockfiletransfer"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardBlockFileTransfer 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/clipboardfiletype

### <a name="windows10endpointprotectionconfigurationapplicationguardblocknonenterprisecontent"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardBlockNonEnterpriseContent 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/blocknonenterprisecontent

### <a name="windows10endpointprotectionconfigurationapplicationguardenabled"></a>Windows10EndpointProtectionConfiguration.ApplicationGuardEnabled 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Settings/allowwindowssavunma derapplicationguard

### <a name="windows10endpointprotectionconfigurationapplicationguardforceauditing"></a>Windows10EndpointProtectionConfiguration. ApplicationGuardForceAuditing 
**CSP**:./Device/Vendor/MSFT/windowssavunma derapplicationguard  
**Konum URI 'si**:/Audit/auditapplicationguard

### <a name="windows10endpointprotectionconfigurationbitlockerallowstandarduserencryption"></a>Windows10EndpointProtectionConfiguration. BitLockerAllowStandardUserEncryption 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Allowstandarduserencryption

### <a name="windows10endpointprotectionconfigurationbitlockerdisablewarningforotherdiskencryption"></a>Windows10EndpointProtectionConfiguration. BitLockerDisableWarningForOtherDiskEncryption 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Allowwarningforotherdiskencryption

### <a name="windows10endpointprotectionconfigurationbitlockerenablestoragecardencryptiononmobile"></a>Windows10EndpointProtectionConfiguration. BitLockerEnableStorageCardEncryptionOnMobile 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Requirestokısallaştırılması

### <a name="windows10endpointprotectionconfigurationbitlockerencryptdevice"></a>Windows10EndpointProtectionConfiguration. BitLockerEncryptDevice 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Requiredeviceencryption

### <a name="windows10endpointprotectionconfigurationbitlockerfixeddrivepolicy"></a>Windows10EndpointProtectionConfiguration. Bitlockerfixeddriveilkesi 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Encryptionmethodbydrivetype,/FixedDrivesRequireEncryption,/FixedDrivesRecoveryOptions

### <a name="windows10endpointprotectionconfigurationbitlockerremovabledrivepolicy"></a>Windows10EndpointProtectionConfiguration. Bitlockerremovabledriveilkesi 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Encryptionmethodbydrivetype,/RemovableDrivesRequireEncryption

### <a name="windows10endpointprotectionconfigurationbitlockersystemdrivepolicy"></a>Windows10EndpointProtectionConfiguration. Bitlockersystemdriveilkesi 
**CSP**:./Device/Vendor/MSFT/BitLocker  
**Konum URI 'si**:/Encryptionmethodbydrivetype,/SystemDrivesRequireStartupAuthentication,/SystemDrivesMinimumPINLength,/SystemDrivesRecoveryMessage,/SystemDrivesRecoveryOptions

### <a name="windows10endpointprotectionconfigurationclientconnectionencryptionlevel"></a>windows10endpointprotectionconfiguration. clientConnectionEncryptionLevel 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteDesktopServices/clientconnectionencryptionlevel

### <a name="windows10endpointprotectionconfigurationconfiguresmbv1clientdriver"></a>windows10endpointprotectionconfiguration.configureSMBV1ClientDriver 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/mssecuritykılavuz/Configuresmbv1clientdriver

### <a name="windows10endpointprotectionconfigurationconnectivitydownloadingofprintdriversoverhttp"></a>Windows10EndpointProtectionConfiguration. ConnectivityDownloadingOfPrintDriversOverHttp 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/disabledownloadingofprintdriversoverhttp

### <a name="windows10endpointprotectionconfigurationconnectivityhardeneduncpaths"></a>Windows10EndpointProtectionConfiguration.ConnectivityHardenedUncPaths 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/HardenedUNCPaths

### <a name="windows10endpointprotectionconfigurationconnectivityinternetdownloadforwebpublishingandonlineorderingwizards"></a>Windows10EndpointProtectionConfiguration.ConnectivityInternetDownloadForWebPublishingAndOnlineOrderingWizards 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards

### <a name="windows10endpointprotectionconfigurationconnectivityprintingoverhttp"></a>Windows10EndpointProtectionConfiguration.ConnectivityPrintingOverHttp 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/diableprintingoverhttp

### <a name="windows10endpointprotectionconfigurationcredentialsuienumerateadministrators"></a>Windows10EndpointProtectionConfiguration.CredentialsUIEnumerateAdministrators 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/CredentialsUI/EnumerateAdministrators

### <a name="windows10endpointprotectionconfigurationdefenderadditionalguardedfolders"></a>Windows10EndpointProtectionConfiguration.DefenderAdditionalGuardedFolders 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/Defender/ControlledFolderAccessProtectedFolders

### <a name="windows10endpointprotectionconfigurationdefenderadvancedransomewareprotectiontype"></a>Windows10EndpointProtectionConfiguration. savunma Deradvancedransomewareprotectiontype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderattacksurfacereductionexcludedpaths"></a>Windows10EndpointProtectionConfiguration. savunma Dersaldırıda Ksurfacereductionexcludedpaths 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductiononlydışlamalar

### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecution"></a>Windows10EndpointProtectionConfiguration. savunma Deremailcontentexecution 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowemailscanning

### <a name="windows10endpointprotectionconfigurationdefenderemailcontentexecutiontype"></a>Windows10EndpointProtectionConfiguration. Savunderemailcontentexecutiontype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxml"></a>Windows10EndpointProtectionConfiguration. savunma Derpatıprotectionxml 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/patıguard/patıprotectionsettings

### <a name="windows10endpointprotectionconfigurationdefenderexploitprotectionxmlfilename"></a>Windows10EndpointProtectionConfiguration. savunma Derpatıprotectionxmlfilename 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/patıguard/patıprotectionsettings

### <a name="windows10endpointprotectionconfigurationdefenderguardedfoldersallowedapppaths"></a>Windows10EndpointProtectionConfiguration.DefenderGuardedFoldersAllowedAppPaths 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/Defender/ControlledFolderAccessAllowedApplications

### <a name="windows10endpointprotectionconfigurationdefenderguardmyfolderstype"></a>Windows10EndpointProtectionConfiguration. savunma Derguardmyfolderstype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/EnableControlledFolderAccess

### <a name="windows10endpointprotectionconfigurationdefendernetworkprotectiontype"></a>Windows10EndpointProtectionConfiguration. Savundernetworkprotectiontype 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/savunma der/enablenetworkprotection

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunch"></a>Windows10EndpointProtectionConfiguration. Savunderofficeappsexecutablecontentcreationorlaunch 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsexecutablecontentcreationorlaunchtype"></a>Windows10EndpointProtectionConfiguration. Savunderofficeappsexecutablecontentcreationorlaunchtype
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocess"></a>Windows10EndpointProtectionConfiguration. Savunderofficeappslaunchchildprocess 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderofficeappslaunchchildprocesstype"></a>Windows10EndpointProtectionConfiguration. Savunderofficeappslaunchchildprocesstype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjection"></a>Windows10EndpointProtectionConfiguration. Savunderofficeappsotherprocessınjection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderofficeappsotherprocessinjectiontype"></a>Windows10EndpointProtectionConfiguration. Savunderofficeappsotherprocessınjectiontype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype 

### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32imports"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32Imports 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderofficemacrocodeallowwin32importstype"></a>Windows10EndpointProtectionConfiguration.DefenderOfficeMacroCodeAllowWin32ImportsType 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefenderpreventcredentialstealingtype"></a>Windows10EndpointProtectionConfiguration. savunma Derpreventcredentialstealingtype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefenderprocesscreation"></a>Windows10EndpointProtectionConfiguration. savunma Derprocessoluşturma 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderprocesscreationtype"></a>Windows10EndpointProtectionConfiguration. Savunderprocesscreationtype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderprotectagainstpotentiallyunwantedapplications"></a>Windows10EndpointProtectionConfiguration.DefenderProtectAgainstPotentiallyUnwantedApplications 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/MSSecurityGuide/TurnOnWindowsDefenderProtectionAgainstPotentiallyUnwantedApplications

### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecution"></a>Windows10EndpointProtectionConfiguration. savunma Derscriptdownloadedpayloadexecution 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderscriptdownloadedpayloadexecutiontype"></a>Windows10EndpointProtectionConfiguration. Savunderscriptdownloadedpayloadexecutiontype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocode"></a>Windows10EndpointProtectionConfiguration. savunma Derscriptobfuscatedmacrocode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderscriptobfuscatedmacrocodetype"></a>Windows10EndpointProtectionConfiguration. savunma Derscriptobfuscatedmacrocodetype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterblockexploitprotectionoverride"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterblockpatıprotectionoverride 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/windowssavunma Dersecuritycenter/disallowpatıprotectionoverride

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableaccountui"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterdisableaccountuı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/disableaccountprotectionuı

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisableappbrowserui"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterdisableappbrowserui 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/disableappbrowseruı

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablefamilyui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableFamilyUI 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsDefenderSecurityCenter/DisableFamilyUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablehealthui"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterdisablehealthuı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/disablehealthuı

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablenetworkui"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterdisablenetworkuı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/disablenetworkuı

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablesecurebootui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableSecureBootUI 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/hidesecureboot

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisabletroubleshootingui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableTroubleshootingUI 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/hidetpmtroubleshooting

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterdisablevirusui"></a>Windows10EndpointProtectionConfiguration.DefenderSecurityCenterDisableVirusUI 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsDefenderSecurityCenter/DisableVirusUI

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpemail"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterhelpemail 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/email

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpphone"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterhelpphone 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/Phone

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterhelpurl"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterhelpurl 'Si 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/URL

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenteritcontactdisplay"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenteritcontactdisplay 
**CSP**:./Device/Vendor/MSFT/Policy  
**Uzaklığa göre URI**:/WindowsDefenderSecurityCenter/EnableCustomizedToasts,/Windowssavunma Dersecuritycenter/enableınappcustomization

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenternotificationsfromapp"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenternotificationsfromapp 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/hidewindowssecuritynotificationareacontrol

### <a name="windows10endpointprotectionconfigurationdefendersecuritycenterorganizationdisplayname"></a>Windows10EndpointProtectionConfiguration. Savundersecuritycenterorganizationdisplayname 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowssavunma Dersecuritycenter/CompanyName

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutable"></a>Windows10EndpointProtectionConfiguration. savunma Deruntrustedexecutable 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedexecutabletype"></a>Windows10EndpointProtectionConfiguration. savunma Deruntrustedexecutabletype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocess"></a>Windows10EndpointProtectionConfiguration. Savunderuntrustedusbprocess 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules

### <a name="windows10endpointprotectionconfigurationdefenderuntrustedusbprocesstype"></a>Windows10EndpointProtectionConfiguration. savunma Deruntrustedusbprocesstype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/saldırıda ksurfacereductionrules (CSP/yapılandırma grafik özellikleri gerektirir: Windows10endpointprotection/Configuration. savunma Derofficeappsotherprocessınjectiontype, windows10endpointprotection/ Configuration. Savunderofficeappsexecutablecontentcreationorlaunchtype, windows10endpointprotection/Configuration. savunma Derofficeappslaunchchildprocesstype, windows10endpointprotection/ Configuration. defenderOfficeMacroCodeAllowWin32ImportsType, windows10endpointprotection/Configuration. savunma Derscriptobfuscatedmacrocodetype, windows10endpointprotection/Configuration. savunma Derscriptdownloadedpayloadexecutiontype , windows10endpointprotection/Configuration. savunma Deremailcontentexecutiontype, windows10endpointprotection/Configuration. Savunderpreventcredentialstealingtype, windows10endpointprotection/ Configuration. savunma Deruntrustedusbprocesstype

### <a name="windows10endpointprotectionconfigurationdeviceguardenablesecurebootwithdma"></a>Windows10EndpointProtectionConfiguration.DeviceGuardEnableSecureBootWithDMA 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceguard/requireplatformsecurityfeatures

### <a name="windows10endpointprotectionconfigurationdeviceguardenablevirtualizationbasedsecurity"></a>Windows10EndpointProtectionConfiguration.DeviceGuardEnableVirtualizationBasedSecurity 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/deviceguard/enablevirtualizationbasedsecurity

### <a name="windows10endpointprotectionconfigurationdeviceguardlaunchsystemguard"></a>Windows10EndpointProtectionConfiguration. DeviceGuardLaunchSystemGuard 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceguard/configuressystemutility mguardlaunch

### <a name="windows10endpointprotectionconfigurationdeviceguardlocalsystemauthoritycredentialguardsettings"></a>Windows10EndpointProtectionConfiguration. DeviceGuardLocalSystemAuthorityCredentialGuardSettings 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceguard/lsacfgflags

### <a name="windows10endpointprotectionconfigurationdmaguarddeviceenumerationpolicy"></a>Windows10EndpointProtectionConfiguration. DmaGuardDeviceEnumerationPolicy 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/dmaguard/deviceenumerationpolicy

### <a name="windows10endpointprotectionconfigurationeventlogserviceapplicationlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration.EventLogServiceApplicationLogMaximumFileSizeInKb 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/eventlogservice/belirtilen ymaximumfilesizeapplicationlog

### <a name="windows10endpointprotectionconfigurationeventlogservicesecuritylogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration. Eventlogservicesecuritylogmaximumfilesizeınkb 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/eventlogservice/belirtilen ymaximumfilesizesecuritylog

### <a name="windows10endpointprotectionconfigurationeventlogservicesystemlogmaximumfilesizeinkb"></a>Windows10EndpointProtectionConfiguration. Eventlogservicessystemutility Mlogmaximumfilesizeınkb 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/eventlogservice/belirtimi ymaximumfilesizessystemutility

### <a name="windows10endpointprotectionconfigurationexplorerdataexecutionprevention"></a>Windows10EndpointProtectionConfiguration. Explorerdataexecutionönlemeye 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/FileExplorer/turnoffdataexecutionkoruyucu tionforexplorer

### <a name="windows10endpointprotectionconfigurationexplorerheapterminationoncorruption"></a>Windows10EndpointProtectionConfiguration. Explorerheapsonlandırmaonbozulmaları 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/FileExplorer/turnoffheapsonlandırationonbozulmaları

### <a name="windows10endpointprotectionconfigurationfirewallblockstatefulftp"></a>Windows10EndpointProtectionConfiguration. FirewallBlockStatefulFTP 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/disablestatefulftp

### <a name="windows10endpointprotectionconfigurationfirewallcertificaterevocationlistcheckmethod"></a>Windows10EndpointProtectionConfiguration.FirewallCertificateRevocationListCheckMethod 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/crlcheck

### <a name="windows10endpointprotectionconfigurationfirewallidletimeoutforsecurityassociationinseconds"></a>Windows10EndpointProtectionConfiguration. Firewaldletimeoutforsecurityassociationınseconds 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/saıdsaati

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowdhcp"></a>Windows10EndpointProtectionConfiguration. Firewalpsecmuaf Tionsallowdhcp 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/ıpsecmuaf

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowicmp"></a>Windows10EndpointProtectionConfiguration. Firewalpsecmuaf Tionsallowıcmp 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/ıpsecmuaf

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowneighbordiscovery"></a>Windows10EndpointProtectionConfiguration.FirewallIPSecExemptionsAllowNeighborDiscovery 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/ıpsecmuaf

### <a name="windows10endpointprotectionconfigurationfirewallipsecexemptionsallowrouterdiscovery"></a>Windows10EndpointProtectionConfiguration. Firewalpsecmuaf Tionsallowrouterdiscovery 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/ıpsecmuaf

### <a name="windows10endpointprotectionconfigurationfirewallmergekeyingmodulesettings"></a>Windows10EndpointProtectionConfiguration.FirewallMergeKeyingModuleSettings 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/MdmStore/Global/OpportunisticallyMatchAuthSetPerKM

### <a name="windows10endpointprotectionconfigurationfirewallpacketqueueingmethod"></a>Windows10EndpointProtectionConfiguration. FirewallPacketQueueingMethod 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/Global/enablepacketqueue

### <a name="windows10endpointprotectionconfigurationfirewallpresharedkeyencodingmethod"></a>Windows10EndpointProtectionConfiguration.FirewallPreSharedKeyEncodingMethod 
**CSP**:./Vendor/MSFT/Firewall  
**Konum URI 'si**:/MdmStore/Global/PresharedKeyEncoding

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomain"></a>Windows10EndpointProtectionConfiguration. FirewallProfileDomain 
**CSP**:./Vendor/MSFT/Firewall  
Sınır **URI 'si**:/EnableFirewall,/DisableStealthMode,/ekranlı,/DisableUnicastResponsesToMulticastBroadcast,/Disableınboundnotifications,/AuthAppsAllowUserPrefMerge,/GlobalPortsAllowUserPrefMerge,/AllowLocalPolicyMerge,/ Defaultoutboundavction,/Defaultinboundadction,/Disablestealthmodeıpsecsecuredpacketexemption,/Allowlocalıpsecpolicymerge

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. firewallProfileDomain. ınboundconnectionsengellendi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/DomainProfile/defaultinboundadction

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. firewallProfileDomain. ınboundnotificationsengellenme 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/DomainProfile/disableınboundnotifications

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomaininboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. firewallProfileDomain. ınboundnotificationsengellenme 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/DomainProfile/EnableFirewall

### <a name="windows10endpointprotectionconfigurationfirewallprofiledomainoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. firewallProfileDomain. Outboundconnectionsengellendi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/DomainProfile/defaultoutboundadction

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivate"></a>Windows10EndpointProtectionConfiguration. FirewallProfilePrivate 
**CSP**:./Vendor/MSFT/Firewall  
Sınır **URI 'si**:/EnableFirewall,/DisableStealthMode,/ekranlı,/DisableUnicastResponsesToMulticastBroadcast,/Disableınboundnotifications,/AuthAppsAllowUserPrefMerge,/GlobalPortsAllowUserPrefMerge,/AllowLocalPolicyMerge,/ Defaultoutboundavction,/Defaultinboundadction,/Disablestealthmodeıpsecsecuredpacketexemption,/Allowlocalıpsecpolicymerge

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivatefirewallenabled"></a>windows10endpointprotectionconfiguration. firewallProfilePrivate. firewallEnabled 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/privateprofile/EnableFirewall

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. firewallProfilePrivate. ınboundconnectionsengellendi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/privateprofile/defaultinboundadction

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. firewallProfilePrivate. ınboundnotificationsengellenme 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/privateprofile/disableınboundnotifications

### <a name="windows10endpointprotectionconfigurationfirewallprofileprivateoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. firewallProfilePrivate. Outboundconnectionsengellendi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/privateprofile/defaultoutboundadction

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublic"></a>Windows10EndpointProtectionConfiguration. FirewallProfilePublic 
**CSP**:./Vendor/MSFT/Firewall  
Sınır **URI 'si**:/EnableFirewall,/DisableStealthMode,/ekranlı,/DisableUnicastResponsesToMulticastBroadcast,/Disableınboundnotifications,/AuthAppsAllowUserPrefMerge,/GlobalPortsAllowUserPrefMerge,/AllowLocalPolicyMerge,/ Defaultoutboundavction,/Defaultinboundadction,/Disablestealthmodeıpsecsecuredpacketexemption,/Allowlocalıpsecpolicymerge

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicconnectionsecurityrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration. firewallProfilePublic. Connectionsecuritykurallarını Fromgrouppolicybirleştirildi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/PublicProfile/allowlocalıpsecpolicymerge

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicfirewallenabled"></a>windows10endpointprotectionconfiguration. firewallProfilePublic. firewallEnabled 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/PublicProfile/EnableFirewall

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. firewallProfilePublic. ınboundconnectionsengellendi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/PublicProfile/defaultinboundadction

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicinboundnotificationsblocked"></a>windows10endpointprotectionconfiguration. firewallProfilePublic. ınboundnotificationsengellenme 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/PublicProfile/disableınboundnotifications

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicoutboundconnectionsblocked"></a>windows10endpointprotectionconfiguration. firewallProfilePublic. Outboundconnectionsengellendi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/PublicProfile/defaultoutboundadction

### <a name="windows10endpointprotectionconfigurationfirewallprofilepublicpolicyrulesfromgrouppolicymerged"></a>windows10endpointprotectionconfiguration. firewallProfilePublic. Policykurallarını Fromgrouppolicybirleştirildi 
**CSP**:./Device/Vendor/MSFT/Firewall  
**Konum URI 'si**:/Mdmstore/PublicProfile/allowlocalpolicymerge

### <a name="windows10endpointprotectionconfigurationlanmanagerauthenticationlevel"></a>Windows10EndpointProtectionConfiguration. LanManagerAuthenticationLevel 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/networksecurity @ No__t-1LANManagerAuthenticationLevel

### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationdisableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration.LanManagerWorkstationDisableInsecureGuestLogons 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LanmanWorkstation/EnableInsecureGuestLogons

### <a name="windows10endpointprotectionconfigurationlanmanagerworkstationenableinsecureguestlogons"></a>Windows10EndpointProtectionConfiguration.LanManagerWorkstationEnableInsecureGuestLogons 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LanmanWorkstation/EnableInsecureGuestLogons

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratoraccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAdministratorAccountName 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1Renameyönetimtoraccount

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsadministratorelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsadministratoretavationpromptbehavior
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1BehaviorOfTheElevationPromptForAdministrators

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowanonymousenumerationofsamaccountsandshares"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowAnonymousEnumerationOfSAMAccountsAndShares 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/NetworkAccess @ No__t-1DoNotAllowAnonymousEnumerationOfSamAccountsAndShares

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowpku2uauthenticationrequests"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowPKU2UAuthenticationRequests 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/networksecurity @ No__t-1AllowPKU2UAuthenticationRequests

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanager"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsAllowRemoteCallsToSecurityAccountsManager 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/NetworkAccess @ No__t-1RestrictClientsAllowedToMakeRemoteCallsToSAM

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowremotecallstosecurityaccountsmanagerhelperbool"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsAllowRemoteCallsToSecurityAccountsManagerHelperBool 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/NetworkAccess @ No__t-1RestrictClientsAllowedToMakeRemoteCallsToSAM

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowsystemtobeshutdownwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowSystemToBeShutDownWithoutHavingToLogOn 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/kapatmadan @ No__t-1AllowSystemToBeShutDownWithoutHavingToLogOn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationelevation"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUIAccessApplicationElevation 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1AllowUIAccessApplicationsToPromptForElevation

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowuiaccessapplicationsforsecurelocations"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUIAccessApplicationsForSecureLocations 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsallowundockwithouthavingtologon"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsAllowUndockWithoutHavingToLogon 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/Devices @ No__t-1AllowUndockWithoutHavingToLogon

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockmicrosoftaccounts"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsBlockMicrosoftAccounts 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1BlockMicrosoftAccounts

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremotelogonwithblankpassword"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsBlockRemoteLogonWithBlankPassword 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockremoteopticaldriveaccess"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsBlockRemoteOpticalDriveAccess 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/Devices @ No__t-1Kısıttcdromaccesstolocallyloggedonuseronly

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsblockusersinstallingprinterdrivers"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsblockusersınstallingprinterdrivers 
**CSP**:./Vendor/MSFT/Policy  
**Kaydırma URI 'si**:/config/localpoliciessecurityoptions/Devices @ No__t-1Preventusersfromınstallingprinterdrivers Whenconnectingtosharedprinters

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclearvirtualmemorypagefile"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsClearVirtualMemoryPageFile 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/kapatmadan @ No__t-1ClearVirtualMemoryPageFile

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsclientdigıtallysigncommunicationsalyollar 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/microsoftnetworkclient @ No__t-1Digıtallysigncommunicationsalyollar

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsclientsendunencryptedpasswordtothirdpartysmbservers"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsclientsendunencryptedpasswordtoüçe Dpartysmbservers 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/microsoftnetworkclient @ No__t-1Sendunencryptedpasswordtoüçe Dpartysmbservers

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdetectapplicationinstallationsandpromptforelevation"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsdetectapplicationınstalsandpromptforelevation 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1Detectapplicationınstallationpromptforelevation

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableadministratoraccount"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsdisableyönetimtoraccount 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1Enableyönetimtoraccountstatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableclientdigitallysigncommunicationsifserveragrees"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsdisableclientdigitallysigncommunicationsıfserverkabul 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/microsoftnetworkclient @ No__t-1Digıtallysigncommunicationsıfserverkabul

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableguestaccount"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsDisableGuestAccount 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1EnableGuestAccountStatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsalways"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsdisableserverdigitallysigncommunicationsalyollar 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/microsoftnetworkserver @ No__t-1Digıtallysigncommunicationsalyollar

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdisableserverdigitallysigncommunicationsifclientagrees"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDisableServerDigitallySignCommunicationsIfClientAgrees 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/microsoftnetworkserver @ No__t-1DigitallySignCommunicationsIfClientAgrees

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotallowanonymousenumerationofsamaccounts"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsDoNotAllowAnonymousEnumerationOfSAMAccounts 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/NetworkAccess @ No__t-1DoNotAllowAnonymousEnumerationOfSAMAccounts

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotrequirectrlaltdel"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsDoNotRequireCtrlAltDel 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1DoNotRequireCTRLALTDEL

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsdonotstorelanmanagerhashvalueonnextpasswordchange"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsDoNotStoreLANManagerHashValueOnNextPasswordChange 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/networksecurity @ No__t-1DoNotStoreLANManagerHashValueOnNextPasswordChange

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableadministratoraccount"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsenableyönetimtoraccount 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1Enableyönetimtoraccountstatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsenableguestaccount"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsEnableGuestAccount 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1EnableGuestAccountStatus

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsformatandejectofremovablemediaalloweduser"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsFormatAndEjectOfRemovableMediaAllowedUser 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/Devices @ No__t-1AllowedToFormatAndEjectRemovableMedia

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsguestaccountname"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsGuestAccountName 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/accounts @ No__t-1RenameGuestAccount

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshidelastsignedinuser"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionshıdelastsignedınuser 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1Donotdisplaylastsignedın

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionshideusernameatsignin"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionshıdeusernameatsignın 
**CSP**:./Vendor/MSFT/Policy  
**Kayan URI**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1Donotdisplayusernameatsignın

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationdisplayedonlockscreen"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsInformationDisplayedOnLockScreen 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1Displayuserınformationwhenthesessioniskilitlendi

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsinformationshownonlockscreen"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsInformationShownOnLockScreen 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1Displayuserınformationwhenthesessioniskilitlendi

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetext"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsLogOnMessageText 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1MessageTextForUsersAttemptingToLogOn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionslogonmessagetitle"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsLogOnMessageTitle 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1MessageTitleForUsersAttemptingToLogOn

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimit"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsmachineınactivitylimit 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1Machineınactivitylimit

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsmachineinactivitylimitinminutes"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsmachineınactivitylimitınminutes 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1Machineınactivitylimit

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedclients"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedClients 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/networksecurity @ No__t-1MinimumSessionSecurityForNTLMSSPBasedClients

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsminimumsessionsecurityforntlmsspbasedservers"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsMinimumSessionSecurityForNtlmSspBasedServers 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/networksecurity @ No__t-1MinimumSessionSecurityForNTLMSSPBasedServers

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsonlyelevatesignedexecutables"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsonlyelivatesignedexecutables 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1Onlyelivateexecutablefilesthataresignedanddoğrulanan

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsrestrictanonymousaccesstonamedpipesandshares"></a>Windows10EndpointProtectionConfiguration.LocalSecurityOptionsRestrictAnonymousAccessToNamedPipesAndShares 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/NetworkAccess @ No__t-1RestrictAnonymousAccessToNamedPipesAndShares

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionssmartcardremovalbehavior"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsSmartCardRemovalBehavior 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/LocalPoliciesSecurityOptions/InteractiveLogon @ No__t-1SmartCardRemovalBehavior

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsstandarduserelevationpromptbehavior"></a>Windows10EndpointProtectionConfiguration. Localsecurityoptionsstandarduseryükseltir Tionpromptbehavior 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1BehaviorOfTheElevationPromptForStandardUsers

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsswitchtosecuredesktopwhenpromptingforelevation"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsSwitchToSecureDesktopWhenPromptingForElevation 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1SwitchToTheSecureDesktopWhenPromptingForElevation

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmode"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsUseAdminApprovalMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1UseAdminApprovalMode

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsuseadminapprovalmodeforadministrators"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsUseAdminApprovalModeForAdministrators 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1Runalladministratorsınadminapprovalmode

### <a name="windows10endpointprotectionconfigurationlocalsecurityoptionsvirtualizefileandregistrywritefailurestoperuserlocations"></a>Windows10EndpointProtectionConfiguration. LocalSecurityOptionsVirtualizeFileAndRegistryWriteFailuresToPerUserLocations 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/localpoliciessecurityoptions/UserAccountControl @ No__t-1VirtualizeFileAndRegistryWriteFailuresToPerUserLocations

### <a name="windows10endpointprotectionconfigurationnetworkicmpredirectsoverrideospfgeneratedroutes"></a>Windows10EndpointProtectionConfiguration.NetworkIcmpRedirectsOverrideOspfGeneratedRoutes 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/MSSLegacy/AllowICMPRedirectsToOverrideOSPFGeneratedRoutes

### <a name="windows10endpointprotectionconfigurationnetworkignorenetbiosnamereleaserequestsexceptfromwinsservers"></a>Windows10EndpointProtectionConfiguration.NetworkIgnoreNetBiosNameReleaseRequestsExceptFromWinsServers 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/MSSLegacy/AllowTheComputerToIgnoreNetBIOSNameReleaseRequestsExceptFromWINSServers

### <a name="windows10endpointprotectionconfigurationnetworkipsourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration. Networkıpsourceroutingprotectionlevel 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/msslegacy/ipsourceroutingprotectionlevel

### <a name="windows10endpointprotectionconfigurationnetworkipv6sourceroutingprotectionlevel"></a>Windows10EndpointProtectionConfiguration.NetworkIpV6SourceRoutingProtectionLevel 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/msslegacy/IPv4

### <a name="windows10endpointprotectionconfigurationpasswordpinlogon"></a>Windows10EndpointProtectionConfiguration. PasswordPinLogOn 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/credentialproviders/allowpinlogon

### <a name="windows10endpointprotectionconfigurationpowershellshellscriptblocklogging"></a>Windows10EndpointProtectionConfiguration. PowerShellShellScriptBlockLogging 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsPowerShell/turnonpowershellscriptblocklogging

### <a name="windows10endpointprotectionconfigurationremoteassistancesolicitedsetting"></a>Windows10EndpointProtectionConfiguration. Remoteyardım Tancesolicitedayarı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/HardenedUNCPaths

### <a name="windows10endpointprotectionconfigurationremotedesktopservicesclientconnectionencryptionlevel"></a>Windows10EndpointProtectionConfiguration. RemoteDesktopServicesClientConnectionEncryptionLevel 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteDesktopServices/clientconnectionencryptionlevel

### <a name="windows10endpointprotectionconfigurationremotedesktopservicesdriveredirection"></a>Windows10EndpointProtectionConfiguration. RemoteDesktopServicesDriveRedirection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteDesktopServices/donotallowdriveredirection

### <a name="windows10endpointprotectionconfigurationremotedesktopservicespasswordsaving"></a>Windows10EndpointProtectionConfiguration. Remotedesktopservicespasswordtasarrufu 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteDesktopServices/donotallowpasswordtasarrufu

### <a name="windows10endpointprotectionconfigurationremotedesktopservicespromptforpassworduponconnection"></a>Windows10EndpointProtectionConfiguration. RemoteDesktopServicesPromptForPasswordUponConnection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteDesktopServices/promptforpassworduponconnection

### <a name="windows10endpointprotectionconfigurationremotedesktopservicessecurerpccommunication"></a>Windows10EndpointProtectionConfiguration. RemoteDesktopServicesSecureRpcCommunication 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteDesktopServices/requiresecurerpccommunication

### <a name="windows10endpointprotectionconfigurationremotehostdelegationofnonexportablecredentials"></a>Windows10EndpointProtectionConfiguration. RemoteHostDelegationOfNonExportableCredentials 
**CSP**:./Device/Vendor/MSFT/Policy  
**Fark URI 'si**:/config/credentialsdelegation/remotehostallowsdelegationofnonexportablecredentials

### <a name="windows10endpointprotectionconfigurationremotemanagementclientbasicauthentication"></a>Windows10EndpointProtectionConfiguration. RemoteManagementClientBasicAuthentication 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteManagement/allowbasicauthentication @ No__t-1client

### <a name="windows10endpointprotectionconfigurationremotemanagementclientdigestauthentication"></a>Windows10EndpointProtectionConfiguration. RemoteManagementClientDigestAuthentication 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteManagement/disallowdigestauthentication

### <a name="windows10endpointprotectionconfigurationremotemanagementclientunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration. RemoteManagementClientUnencryptedTraffic 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteManagement/allowunencryptedtraffic @ No__t-1client

### <a name="windows10endpointprotectionconfigurationremotemanagementservicebasicauthentication"></a>Windows10EndpointProtectionConfiguration. RemoteManagementServiceBasicAuthentication 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteManagement/allowbasicauthentication @ No__t-1Service

### <a name="windows10endpointprotectionconfigurationremotemanagementservicestoringrunascredentials"></a>Windows10EndpointProtectionConfiguration.RemoteManagementServiceStoringRunAsCredentials 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteManagement/DisallowStoringOfRunAsCredentials

### <a name="windows10endpointprotectionconfigurationremotemanagementserviceunencryptedtraffic"></a>Windows10EndpointProtectionConfiguration. RemoteManagementServiceUnencryptedTraffic 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteManagement/allowunencryptedtraffic @ No__t-1Service

### <a name="windows10endpointprotectionconfigurationrpcunauthenticatedclientoptions"></a>Windows10EndpointProtectionConfiguration. Rpcundoğrulayıcısı Tedclientoptions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteProcedureCall/RestrictUnauthenticatedRPCClients

### <a name="windows10endpointprotectionconfigurationsecurityguideapplyuacrestrictionstolocalaccountsonnetworklogon"></a>Windows10EndpointProtectionConfiguration.SecurityGuideApplyUacRestrictionsToLocalAccountsOnNetworkLogon 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/MSSecurityGuide/ApplyUACRestrictionsToLocalAccountsOnNetworkLogon

### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1clientdriverstartconfiguration"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1ClientDriverStartConfiguration 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/mssecuritykılavuz/Configuresmbv1clientdriver

### <a name="windows10endpointprotectionconfigurationsecurityguidesmbv1server"></a>Windows10EndpointProtectionConfiguration.SecurityGuideSmbV1Server 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/mssecuritykılavuz/Configuresmbv1server

### <a name="windows10endpointprotectionconfigurationsecurityguidestructuredexceptionhandlingoverwriteprotection"></a>Windows10EndpointProtectionConfiguration. Securitykılavuz Structuredexceptionhandlingoverwriteprotection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/mssecuritykılavuz/Enablestructuredexceptionhandlingoverwriteprotection

### <a name="windows10endpointprotectionconfigurationsecurityguidewdigestauthentication"></a>Windows10EndpointProtectionConfiguration. Securitykılavuz Wdigestauthentication 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/mssecuritykılavuz/Wdigestauthentication

### <a name="windows10endpointprotectionconfigurationsmartscreenblockoverrideforfiles"></a>Windows10EndpointProtectionConfiguration.SmartScreenBlockOverrideForFiles 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/deviceguard/requireplatformsecurityfeatures

### <a name="windows10endpointprotectionconfigurationsmartscreenenableinshell"></a>Windows10EndpointProtectionConfiguration. Smartscreenenableınshell 
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI 'si**:/config/SmartScreen/enablesmartscreenınshell

### <a name="windows10endpointprotectionconfigurationsolicitedremoteassistance"></a>windows10endpointprotectionconfiguration. bağlantıları Itedremoteassistance 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/RemoteAssistance tance/confiitedremoteassistance

### <a name="windows10endpointprotectionconfigurationuserrightsaccesscredentialmanagerastrustedcaller"></a>Windows10EndpointProtectionConfiguration.UserRightsAccessCredentialManagerAsTrustedCaller 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/UserRights/AccessCredentialManagerAsTrustedCaller

### <a name="windows10endpointprotectionconfigurationuserrightsaccessfromnetwork"></a>windows10EndpointProtectionConfiguration. UserRightsAccessFromNetwork 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/accessfromnetwork

### <a name="windows10endpointprotectionconfigurationuserrightsactaspartoftheoperatingsystem"></a>Windows10EndpointProtectionConfiguration.userRightsActAsPartOfTheOperatingSystem 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/UserRights/ActAsPartOfTheOperatingSystem

### <a name="windows10endpointprotectionconfigurationuserrightsallowaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration. Usersağtsallowaccessfromnetwork 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/accessfromnetwork

### <a name="windows10endpointprotectionconfigurationuserrightsbackupdata"></a>Windows10EndpointProtectionConfiguration. Usersağtsbackupdata 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/backupfilesanddizinler

### <a name="windows10endpointprotectionconfigurationuserrightsblockaccessfromnetwork"></a>Windows10EndpointProtectionConfiguration. Usersağtsblockaccessfromnetwork 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/userlıts/denyaccessfromnetwork

### <a name="windows10endpointprotectionconfigurationuserrightschangesystemtime"></a>Windows10EndpointProtectionConfiguration. Usersağtschangessystemtime 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/changessystemtime

### <a name="windows10endpointprotectionconfigurationuserrightscreateglobalobjects"></a>Windows10EndpointProtectionConfiguration. Usersağtscreateglobalobjects 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/createglobalobjects

### <a name="windows10endpointprotectionconfigurationuserrightscreatepagefile"></a>Windows10EndpointProtectionConfiguration. Usersağtscreatepagefile 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/createpagefile

### <a name="windows10endpointprotectionconfigurationuserrightscreatepermanentsharedobjects"></a>Windows10EndpointProtectionConfiguration.UserRightsCreatePermanentSharedObjects 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/UserRights/CreatePermanentSharedObjects

### <a name="windows10endpointprotectionconfigurationuserrightscreatesymboliclinks"></a>Windows10EndpointProtectionConfiguration. Userlıtscreatesemboliclinks 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/createsemboliclinks

### <a name="windows10endpointprotectionconfigurationuserrightscreatetoken"></a>Windows10EndpointProtectionConfiguration. Usersağtscreatetoken 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/CreateToken

### <a name="windows10endpointprotectionconfigurationuserrightsdebugprograms"></a>Windows10EndpointProtectionConfiguration. Usersağtsdebugprograms 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/debugprograms

### <a name="windows10endpointprotectionconfigurationuserrightsdelegation"></a>Windows10EndpointProtectionConfiguration. Usersağtstemsilciyi 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/enabletemsili

### <a name="windows10endpointprotectionconfigurationuserrightsdenyaccessfromnetwork"></a>windows10EndpointProtectionConfiguration. Usersağtsdenyaccessfromnetwork 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/userlıts/denyaccessfromnetwork

### <a name="windows10endpointprotectionconfigurationuserrightsgeneratesecurityaudits"></a>Windows10EndpointProtectionConfiguration.UserRightsGenerateSecurityAudits 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/UserRights/GenerateSecurityAudits

### <a name="windows10endpointprotectionconfigurationuserrightsimpersonateclient"></a>Windows10EndpointProtectionConfiguration.UserRightsImpersonateClient 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/ImpersonateClient

### <a name="windows10endpointprotectionconfigurationuserrightsincreaseschedulingpriority"></a>Windows10EndpointProtectionConfiguration.UserRightsIncreaseSchedulingPriority 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/UserRights/IncreaseSchedulingPriority

### <a name="windows10endpointprotectionconfigurationuserrightsloadunloaddrivers"></a>Windows10EndpointProtectionConfiguration. Userrıtsloadunloaddrivers 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/loadunloaddevicedrivers

### <a name="windows10endpointprotectionconfigurationuserrightslocallogon"></a>Windows10EndpointProtectionConfiguration. Userletslocallogon 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/allowlocallogon

### <a name="windows10endpointprotectionconfigurationuserrightslockmemory"></a>Windows10EndpointProtectionConfiguration. Usersağtslockmemory 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/lockmemory

### <a name="windows10endpointprotectionconfigurationuserrightsmanageauditingandsecuritylogs"></a>Windows10EndpointProtectionConfiguration. Usersağtsmanageauditingandsecuritylogs 
**CSP**:./Device/Vendor/MSFT/Policy  
**Kaydırma URI 'si**:/config/usersağts/manageauditingandsecuritylog

### <a name="windows10endpointprotectionconfigurationuserrightsmanagevolumes"></a>Windows10EndpointProtectionConfiguration. Usersağtsmanagevolumes 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/managevolume

### <a name="windows10endpointprotectionconfigurationuserrightsmodifyfirmwareenvironment"></a>Windows10EndpointProtectionConfiguration. Usersağtsmodifyfirmwareenvironment 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/modifyfirmwareenvironment

### <a name="windows10endpointprotectionconfigurationuserrightsmodifyobjectlabels"></a>Windows10EndpointProtectionConfiguration.UserRightsModifyObjectLabels 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/UserRights/ModifyObjectLabel

### <a name="windows10endpointprotectionconfigurationuserrightsprofilesingleprocess"></a>Windows10EndpointProtectionConfiguration. Usersağtsprofilesingleprocess 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/profilesingleprocess

### <a name="windows10endpointprotectionconfigurationuserrightsregisterprocessasservice"></a>Windows10EndpointProtectionConfiguration. Usersağtsregisterprocessasservice 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/denylocallogon

### <a name="windows10endpointprotectionconfigurationuserrightsremotedesktopserviceslogon"></a>Windows10EndpointProtectionConfiguration. Userletsremotedesktopserviceslogon 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/denyremotedesktopserviceslogon

### <a name="windows10endpointprotectionconfigurationuserrightsremoteshutdown"></a>Windows10EndpointProtectionConfiguration. Usersağtsremotekapatması 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/remotekapatması

### <a name="windows10endpointprotectionconfigurationuserrightsrestoredata"></a>Windows10EndpointProtectionConfiguration. Usersağtsrestoredata 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/restorefilesanddizinler

### <a name="windows10endpointprotectionconfigurationuserrightstakeownership"></a>Windows10EndpointProtectionConfiguration.UserRightsTakeOwnership 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/usersağts/takesahiplik

### <a name="windows10endpointprotectionconfigurationwindowsconnectionmanagerconnectiontonondomainnetworks"></a>Windows10EndpointProtectionConfiguration. WindowsConnectionManagerConnectionToNonDomainNetworks 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowsconnectionmanager/prohitconnectiontonondomainnetworkswhenconnectedtodomaindoğrulayıcısı tednetwork

### <a name="windows10endpointprotectionconfigurationwindowslogonsigninlastinteractiveuseraftersysteminitiatedrestart"></a>Windows10EndpointProtectionConfiguration. Windowslogonsignınlastınteractiveuseraftersysteminibir yeniden başlatma 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsLogon/SignInLastInteractiveUserAutomaticallyAfterASystemInitiatedRestart

### <a name="windows10endpointprotectionconfigurationxboxservicesaccessorymanagementservicestartupmode"></a>Windows10EndpointProtectionConfiguration. Xboxservicesaccessoryımanagementservicestartupmode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/systemservices/configurexboxaccessorymanagementservicestartupmode

### <a name="windows10endpointprotectionconfigurationxboxservicesenablexboxgamesavetask"></a>Windows10EndpointProtectionConfiguration.XboxServicesEnableXboxGameSaveTask 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/TaskScheduler/EnableXboxGameSaveTask

### <a name="windows10endpointprotectionconfigurationxboxservicesliveauthmanagerservicestartupmode"></a>Windows10EndpointProtectionConfiguration. XboxServicesLiveAuthManagerServiceStartupMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/systemservices/configurexboxliveauthmanagerservicestartupmode

### <a name="windows10endpointprotectionconfigurationxboxserviceslivegamesaveservicestartupmode"></a>Windows10EndpointProtectionConfiguration.XboxServicesLiveGameSaveServiceStartupMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/SystemServices/XboxServicesLiveGameSaveServiceStartupMode

### <a name="windows10endpointprotectionconfigurationxboxserviceslivenetworkingservicestartupmode"></a>Windows10EndpointProtectionConfiguration. XboxServicesLiveNetworkingServiceStartupMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/systemservices/configurexboxlivenetworkingservicestartupmode

### <a name="windows10enterprisemodernappmanagementconfigurationuninstallbuiltinapps"></a>Windows10EnterpriseModernAppManagementConfiguration. UninstallBuiltInApps
**CSP**: n/a Graph API yalnızca bir arama **URI 'si**: n/a Graph API çağrı

### <a name="windows10generalconfigurationaccountsblockaddingnonmicrosoftaccountemail"></a>Windows10GeneralConfiguration. AccountsBlockAddingNonMicrosoftAccountEmail 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/accounts/allowaddingnonmicrosoftaccountsmanuel

### <a name="windows10generalconfigurationantitheftmodeblocked"></a>Windows10GeneralConfiguration. Antitheftmodeengelledi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Security/antitheftmode

### <a name="windows10generalconfigurationappmanagementmsiallowusercontroloverinstall"></a>Windows10GeneralConfiguration.AppManagementMSIAllowUserControlOverInstall 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/MSIAllowUserControlOverInstall

### <a name="windows10generalconfigurationappmanagementmsialwaysinstallwithelevatedprivileges"></a>Windows10GeneralConfiguration.AppManagementMSIAlwaysInstallWithElevatedPrivileges 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges

### <a name="windows10generalconfigurationappsallowtrustedappssideloading"></a>Windows10GeneralConfiguration. Appsallowtrustedappsdışarıdan yükleme 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/AllowAllTrustedApps

### <a name="windows10generalconfigurationappsblockwindowsstoreoriginatedapps"></a>Windows10GeneralConfiguration. AppsBlockWindowsStoreOriginatedApps 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/disablestoreoriginatedapps

### <a name="windows10generalconfigurationappsmicrosoftaccountsoptional"></a>Windows10GeneralConfiguration. AppsMicrosoftAccountsOptional 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/appruntime/allowmicrosoftaccountstobeoptional

### <a name="windows10generalconfigurationassignedaccessmultimodeprofiles"></a>Windows10GeneralConfiguration. Atandaccessmultimodeprofiles 
**CSP**:./Device/Vendor/MSFT/atana  
**Konum URI 'si**:/Configuration

### <a name="windows10generalconfigurationassignedaccesssinglemodeappusermodelid"></a>Windows10GeneralConfiguration. Atandaccesssinglimodeappusermodelıd 
**CSP**:./Device/Vendor/MSFT/atana  
**Konum URI 'si**:/Configuration

### <a name="windows10generalconfigurationassignedaccesssinglemodeusername"></a>Windows10GeneralConfiguration. Atandaccesssinglimodeusername 
**CSP**:./Device/Vendor/MSFT/atana  
**Konum URI 'si**:/Configuration

### <a name="windows10generalconfigurationauthenticationallowfidodevice"></a>Windows10GeneralConfiguration. AuthenticationAllowFIDODevice 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Authentication/allowfidodevicesignon

### <a name="windows10generalconfigurationauthenticationallowsecondarydevice"></a>Windows10GeneralConfiguration. AuthenticationAllowSecondaryDevice 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Authentication/AllowSecondaryAuthenticationDevice

### <a name="windows10generalconfigurationauthenticationpreferredazureadtenantdomainname"></a>Windows10GeneralConfiguration. AuthenticationPreferredAzureADTenantDomainName 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Authentication/preferredaadtenantdomainname

### <a name="windows10generalconfigurationauthenticationwebsignin"></a>Windows10GeneralConfiguration. Authenticationwebsignın 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Authentication/enablewebsignın

### <a name="windows10generalconfigurationautoplaydefaultautorunbehavior"></a>Windows10GeneralConfiguration.AutoPlayDefaultAutoRunBehavior 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AutoPlay/SetDefaultAutoRunBehavior

### <a name="windows10generalconfigurationautoplayfornonvolumedevices"></a>Windows10GeneralConfiguration.AutoPlayForNonVolumeDevices 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AutoPlay/DisallowAutoplayForNonVolumeDevices

### <a name="windows10generalconfigurationautoplaymode"></a>Windows10GeneralConfiguration.AutoPlayMode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AutoPlay/TurnOffAutoPlay

### <a name="windows10generalconfigurationbluetoothallowedservices"></a>Windows10GeneralConfiguration. Bluetootallowedservices 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Bluetoot/servicesallowedlist

### <a name="windows10generalconfigurationbluetoothblockadvertising"></a>Windows10GeneralConfiguration. Bluetootblockadvertising 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Bluetoot/allowadvertising

### <a name="windows10generalconfigurationbluetoothblockdiscoverablemode"></a>Windows10GeneralConfiguration. Bluetootblockdiscoverablemode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/bluetobir/Allowdiscoverablemode

### <a name="windows10generalconfigurationbluetoothblocked"></a>Windows10GeneralConfiguration. Bluetootbloke 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/allowbluetooth

### <a name="windows10generalconfigurationbluetoothblockprepairing"></a>Windows10GeneralConfiguration. Bluetootblockpreeşleştirmeye 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/bluetobir/Allowpreeşleştirmeye

### <a name="windows10generalconfigurationbluetoothblockpromptedproximalconnections"></a>Windows10GeneralConfiguration.BluetoothBlockPromptedProximalConnections 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Bluetooth/AllowPromptedProximalConnections

### <a name="windows10generalconfigurationbluetoothdevicename"></a>Windows10GeneralConfiguration. bluetootaygı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Bluetoot/localaygıtadı

### <a name="windows10generalconfigurationbootstartdriverinitialization"></a>windows10generalconfiguration. Bootstartdriverınitialization 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/bootstartdriverınitialization

### <a name="windows10generalconfigurationcamerablocked"></a>Windows10GeneralConfiguration.CameraBlocked 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Camera/AllowCamera

### <a name="windows10generalconfigurationcellularblockdatawhenroaming"></a>Windows10GeneralConfiguration. CellularBlockDataWhenRoaming 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/AllowCellularDataRoaming

### <a name="windows10generalconfigurationcellularblockvpn"></a>Windows10GeneralConfiguration. CellularBlockVpn 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/allowvpnoverhücresel

### <a name="windows10generalconfigurationcellularblockvpnwhenroaming"></a>Windows10GeneralConfiguration. CellularBlockVpnWhenRoaming 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/AllowVPNRoamingOverCellular

### <a name="windows10generalconfigurationcellulardata"></a>Windows10GeneralConfiguration. CellularData 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/allowcellulardata

### <a name="windows10generalconfigurationcertificatesblockmanualrootcertificateinstallation"></a>Windows10GeneralConfiguration. Certificatesblockmanualrootcertificateınstallation 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Security/allowmanualrootcertificateınstallation

### <a name="windows10generalconfigurationconnecteddevicesserviceblocked"></a>Windows10GeneralConfiguration. Connecteddevicesserviceengellendi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/allowconnecteddevices

### <a name="windows10generalconfigurationcopypasteblocked"></a>Windows10GeneralConfiguration.CopyPasteBlocked 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowCopyPaste

### <a name="windows10generalconfigurationcortanablocked"></a>Windows10GeneralConfiguration. Cortanabkilitlendi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AboveLock/AllowCortanaAboveLock

### <a name="windows10generalconfigurationcryptographyallowfipsalgorithmpolicy"></a>Windows10GeneralConfiguration. CryptographyAllowFipsAlgorithmPolicy 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Cryptography/allowfipsalgorithmpolicy

### <a name="windows10generalconfigurationdataprotectionblockdirectmemoryaccess"></a>Windows10GeneralConfiguration. DataProtectionBlockDirectMemoryAccess 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DataProtection/allowdirectmemoryaccess

### <a name="windows10generalconfigurationdefenderblockenduseraccess"></a>Windows10GeneralConfiguration. Savunderblockenduseraccess 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AllowUserUIAccess

### <a name="windows10generalconfigurationdefenderblockonaccessprotection"></a>Windows10GeneralConfiguration. Savunderblockonaccessprotection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowonaccessprotection

### <a name="windows10generalconfigurationdefendercloudblocklevel"></a>Windows10GeneralConfiguration. savunma Dercloudblocklevel 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/cloudblocklevel

### <a name="windows10generalconfigurationdefendercloudextendedtimeout"></a>Windows10GeneralConfiguration. savunma Dercloudextendedtimeout 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/cloudextendedtimeout

### <a name="windows10generalconfigurationdefendercloudextendedtimeoutinseconds"></a>Windows10GeneralConfiguration. savunma Dercloudextendedtimeoutınseconds 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/cloudextendedtimeout

### <a name="windows10generalconfigurationdefenderdaysbeforedeletingquarantinedmalware"></a>Windows10GeneralConfiguration. savunma Derdavysbeforedeletingquarantinedmalware 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/DaysToRetainCleanedMalware

### <a name="windows10generalconfigurationdefenderdetectedmalwareactions"></a>Windows10GeneralConfiguration. savunma Derdetectedmalwareactions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/threatseveritydefaultaction

### <a name="windows10generalconfigurationdefenderfileextensionstoexclude"></a>Windows10GeneralConfiguration. Savunderfileextensionstoexclude 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/ExcludedExtensions

### <a name="windows10generalconfigurationdefenderfilesandfolderstoexclude"></a>Windows10GeneralConfiguration. Savunderfilesandfolderstoexclude 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/excludedpaths

### <a name="windows10generalconfigurationdefendermonitorfileactivity"></a>Windows10GeneralConfiguration. Savundermonitorfileactivity 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AllowRealtimeMonitoring

### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappaction"></a>Windows10GeneralConfiguration.DefenderPotentiallyUnwantedAppAction 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/puaprotection

### <a name="windows10generalconfigurationdefenderpotentiallyunwantedappactionsetting"></a>Windows10GeneralConfiguration.DefenderPotentiallyUnwantedAppActionSetting 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/puaprotection

### <a name="windows10generalconfigurationdefenderprocessestoexclude"></a>Windows10GeneralConfiguration. Savunderprocessestoexclude 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/excludedprocesses

### <a name="windows10generalconfigurationdefenderpromptforsamplesubmission"></a>Windows10GeneralConfiguration. Savunderpromptforsamplegönderim 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/submitsamplesonayı

### <a name="windows10generalconfigurationdefenderrequirebehaviormonitoring"></a>Windows10GeneralConfiguration.DefenderRequireBehaviorMonitoring 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AllowBehaviorMonitoring

### <a name="windows10generalconfigurationdefenderrequirecloudprotection"></a>Windows10GeneralConfiguration. savunma Derrequirecses koruması 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowcloudprotection

### <a name="windows10generalconfigurationdefenderrequirenetworkinspectionsystem"></a>Windows10GeneralConfiguration. savunma Dertionırenetworkınspectionsystem 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowıntrusionkoruyucu sistem

### <a name="windows10generalconfigurationdefenderrequirerealtimemonitoring"></a>Windows10GeneralConfiguration. Savunmagereksinimleri ırerealtimemonitoring 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AllowRealtimeMonitoring

### <a name="windows10generalconfigurationdefenderscanarchivefiles"></a>Windows10GeneralConfiguration.DefenderScanArchiveFiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AllowArchiveScanning

### <a name="windows10generalconfigurationdefenderscandownloads"></a>Windows10GeneralConfiguration. savunma Derscandownloads 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowwioavprotection

### <a name="windows10generalconfigurationdefenderscanincomingmail"></a>Windows10GeneralConfiguration. savunma Derscanıncomingmail 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowscanningnetworkfiles

### <a name="windows10generalconfigurationdefenderscanmappednetworkdrivesduringfullscan"></a>Windows10GeneralConfiguration.DefenderScanMappedNetworkDrivesDuringFullScan 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowfullscanonmappednetworkdrives

### <a name="windows10generalconfigurationdefenderscanmaxcpu"></a>Windows10GeneralConfiguration. Savunderscanmaxcpu 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AvgCPULoadFactor

### <a name="windows10generalconfigurationdefenderscannetworkfiles"></a>Windows10GeneralConfiguration. Savunderscannetworkfiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowscanningnetworkfiles

### <a name="windows10generalconfigurationdefenderscanremovabledrivesduringfullscan"></a>Windows10GeneralConfiguration.DefenderScanRemovableDrivesDuringFullScan 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/AllowFullScanRemovableDriveScanning

### <a name="windows10generalconfigurationdefenderscanscriptsloadedininternetexplorer"></a>Windows10GeneralConfiguration. savunma Derscanscriptsloadedinınternetbu 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/allowscriptscanning

### <a name="windows10generalconfigurationdefenderscantype"></a>Windows10GeneralConfiguration. savunma Derscantype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Defender/ScanParameter

### <a name="windows10generalconfigurationdefenderscheduledquickscantime"></a>Windows10GeneralConfiguration. Savunderscheduledquickscantime 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/schedulequickscantime

### <a name="windows10generalconfigurationdefenderscheduledscantime"></a>Windows10GeneralConfiguration. savunma Derscheduledscantime 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/schedulescantime

### <a name="windows10generalconfigurationdefenderschedulescanday"></a>Windows10GeneralConfiguration. Savunderschedulescanday 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/schedulescanday

### <a name="windows10generalconfigurationdefendersignatureupdateintervalinhours"></a>Windows10GeneralConfiguration. savunma Dersignatureupdateıntervalınhours 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/signatureupdateınterval

### <a name="windows10generalconfigurationdefendersubmitsamplesconsenttype"></a>Windows10GeneralConfiguration. Savundersubmitsamplesconsenttype 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/submitsamplesonayı

### <a name="windows10generalconfigurationdefendersystemscanschedule"></a>Windows10GeneralConfiguration. Savundersystemscanschedule 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/savunma der/schedulescanday

### <a name="windows10generalconfigurationdeveloperunlocksetting"></a>Windows10GeneralConfiguration.DeveloperUnlockSetting 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/AllowDeveloperUnlock

### <a name="windows10generalconfigurationdevicemanagementblockfactoryresetonmobile"></a>Windows10GeneralConfiguration. DeviceManagementBlockFactoryResetOnMobile 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/allowusertoresetphone

### <a name="windows10generalconfigurationdevicemanagementblockmanualunenroll"></a>Windows10GeneralConfiguration. Devicemanagementblockmanualunkaydolma 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowManualMDMUnenrollment

### <a name="windows10generalconfigurationdiagnosticsdatasubmissionmode"></a>Windows10GeneralConfiguration. DiagnosticsDataSubmissionMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/allowtelemetrisi

### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedoff"></a>Windows10GeneralConfiguration. DisplayAppListWithGdiDPIScalingTurnedOff 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Display/TurnOffGdiDPIScalingForApps

### <a name="windows10generalconfigurationdisplayapplistwithgdidpiscalingturnedon"></a>Windows10GeneralConfiguration. DisplayAppListWithGdiDPIScalingTurnedOn 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Display/TurnOnGdiDPIScalingForApps

### <a name="windows10generalconfigurationedgeallowstartpagesmodification"></a>Windows10GeneralConfiguration. Edgeallowstartpagesdeiiklik 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/homepages

### <a name="windows10generalconfigurationedgeblockaccesstoaboutflags"></a>Windows10GeneralConfiguration. EdgeBlockAccessToAboutFlags 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/önleyici taccesstoaboutflagsinmicrosoftedge

### <a name="windows10generalconfigurationedgeblockaddressbardropdown"></a>Windows10GeneralConfiguration. Edgeblockaddressbardropaşağı 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowaddressbardropaşağı

### <a name="windows10generalconfigurationedgeblockautofill"></a>Windows10GeneralConfiguration. EdgeBlockAutofill 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowotomatik doldurma

### <a name="windows10generalconfigurationedgeblockcompatibilitylist"></a>Windows10GeneralConfiguration. EdgeBlockCompatibilityList 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowmicrosoftcompatibilitylist

### <a name="windows10generalconfigurationedgeblockdevelopertools"></a>Windows10GeneralConfiguration.EdgeBlockDeveloperTools 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/AllowDeveloperTools

### <a name="windows10generalconfigurationedgeblocked"></a>Windows10GeneralConfiguration. Edgeengellenme 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowbrowser

### <a name="windows10generalconfigurationedgeblockeditfavorites"></a>Windows10GeneralConfiguration. EdgeBlockEditFavorites 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/lockdownfavorites

### <a name="windows10generalconfigurationedgeblockextensions"></a>Windows10GeneralConfiguration. EdgeBlockExtensions 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/AllowExtensions

### <a name="windows10generalconfigurationedgeblockfullscreenmode"></a>Windows10GeneralConfiguration. EdgeBlockFullScreenMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowfullscreenmode

### <a name="windows10generalconfigurationedgeblockinprivatebrowsing"></a>Windows10GeneralConfiguration. Edgeblockinprivategözatılıyor 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowwinprivate

### <a name="windows10generalconfigurationedgeblocklivetiledatacollection"></a>Windows10GeneralConfiguration.EdgeBlockLiveTileDataCollection 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/preventlivetiledatacollection

### <a name="windows10generalconfigurationedgeblockpasswordmanager"></a>Windows10GeneralConfiguration. EdgeBlockPasswordManager 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowpasswordmanager

### <a name="windows10generalconfigurationedgeblockpopups"></a>Windows10GeneralConfiguration. Edgeblockpopup 'lar 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowpopup

### <a name="windows10generalconfigurationedgeblockprelaunch"></a>Windows10GeneralConfiguration. EdgeBlockPrelaunch 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowprelaunch

### <a name="windows10generalconfigurationedgeblockprinting"></a>Windows10GeneralConfiguration. EdgeBlockPrinting 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowprinting

### <a name="windows10generalconfigurationedgeblocksavinghistory"></a>Windows10GeneralConfiguration. EdgeBlockSavingHistory 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowsavinghistory

### <a name="windows10generalconfigurationedgeblocksearchsuggestions"></a>Windows10GeneralConfiguration. Edgeblocksearchönerilere 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowsearchmütionsinaddressbar

### <a name="windows10generalconfigurationedgeblocksendingdonottrackheader"></a>Windows10GeneralConfiguration. EdgeBlockSendingDoNotTrackHeader 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowdonottrack

### <a name="windows10generalconfigurationedgeblocksendingintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration.EdgeBlockSendingIntranetTrafficToInternetExplorer 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/SendIntranetTraffictoInternetExplorer

### <a name="windows10generalconfigurationedgeblocksideloadingextensions"></a>Windows10GeneralConfiguration. EdgeBlockSideloadingExtensions 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowsideloadingofextensions

### <a name="windows10generalconfigurationedgeblocktabpreloading"></a>Windows10GeneralConfiguration. Edgeblocktabönyüklemesi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowtabönyüklemesi

### <a name="windows10generalconfigurationedgeblockwebcontentonnewtabpage"></a>Windows10GeneralConfiguration.EdgeBlockWebContentOnNewTabPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/AllowWebContentOnNewTabPage

### <a name="windows10generalconfigurationedgeclearbrowsingdataonexit"></a>Windows10GeneralConfiguration. EdgeClearBrowsingDataOnExit 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/clearbrowsingdataonexit

### <a name="windows10generalconfigurationedgecookiepolicy"></a>Windows10GeneralConfiguration. Edgepişiriepolicy 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/AllowCookies

### <a name="windows10generalconfigurationedgedisablefirstrunpage"></a>Windows10GeneralConfiguration. EdgeDisableFirstRunPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/preventfirstrunpage

### <a name="windows10generalconfigurationedgeenterprisemodesitelistlocation"></a>Windows10GeneralConfiguration. EdgeEnterpriseModeSiteListLocation 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI**'si:/config/Browser/enterprisesitelistserviceurl

### <a name="windows10generalconfigurationedgefavoritesbarvisibility"></a>Windows10GeneralConfiguration. EdgeFavoritesBarVisibility 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/configurefavoritesbar

### <a name="windows10generalconfigurationedgefavoriteslistlocation"></a>Windows10GeneralConfiguration. EdgeFavoritesListLocation 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/provisionfavorites

### <a name="windows10generalconfigurationedgefirstrunurl"></a>Windows10GeneralConfiguration. EdgeFirstRunUrl 'Si 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/firstrunurl

### <a name="windows10generalconfigurationedgehomebuttonconfiguration"></a>Windows10GeneralConfiguration. EdgeHomeButtonConfiguration 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/sethomebuttonurl 'si

### <a name="windows10generalconfigurationedgehomebuttonconfigurationenabled"></a>Windows10GeneralConfiguration. EdgeHomeButtonConfigurationEnabled 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/configurehomebutton

### <a name="windows10generalconfigurationedgehomepageurls"></a>Windows10GeneralConfiguration. EdgeHomepageUrls 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/sethomebuttonurl 'si

### <a name="windows10generalconfigurationedgenewtabpageurl"></a>Windows10GeneralConfiguration. EdgeNewTabPageURL 'Si 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI**'si:/config/Browser/setnewtabpageurl

### <a name="windows10generalconfigurationedgeopenswith"></a>Windows10GeneralConfiguration. EdgeOpensWith 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/configureopenmicrosoftedgewith

### <a name="windows10generalconfigurationedgepreventcertificateerroroverride"></a>Windows10GeneralConfiguration. EdgePreventCertificateErrorOverride 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/preventcerterrorkılmalar

### <a name="windows10generalconfigurationedgerequiresmartscreen"></a>Windows10GeneralConfiguration. Edgerequiressmarttagscreen 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/allowsmartscreen

### <a name="windows10generalconfigurationedgesearchengine"></a>Windows10GeneralConfiguration. EdgeSearchEngine 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/setdefaultsearchengine

### <a name="windows10generalconfigurationedgesendintranettraffictointernetexplorer"></a>Windows10GeneralConfiguration.EdgeSendIntranetTrafficToInternetExplorer 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/SendIntranetTraffictoInternetExplorer

### <a name="windows10generalconfigurationedgeshowmessagewhenopeninginternetexplorersites"></a>Windows10GeneralConfiguration. Edgeshowmessagewhenopeningınternetexplorersites 
**CSP**:./Vendor/MSFT/Policy  
**Kaydırma URI 'si**:/config/Browser/showmessagewhenopeningsitesinınterne/2

### <a name="windows10generalconfigurationedgesyncfavoriteswithinternetexplorer"></a>Windows10GeneralConfiguration. Edgesyncfavoriteswithınternedynamicsnav 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/syncfavoritesbetweenıeandmicrosoftedge

### <a name="windows10generalconfigurationedgetelemetryformicrosoft365analytics"></a>Windows10GeneralConfiguration.EdgeTelemetryForMicrosoft365Analytics 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/ConfigureTelemetryForMicrosoft365Analytics

### <a name="windows10generalconfigurationenableautomaticredeployment"></a>Windows10GeneralConfiguration. Enableautomaticyeniden dağıtım 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/credentialproviders/disableautomaticredeploymentcredentials

### <a name="windows10generalconfigurationenterprisecloudprintdiscoveryendpoint"></a>Windows10GeneralConfiguration. EnterpriseCloudPrintDiscoveryEndPoint 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/enterprisecloudprint/cloudprinterdiscoveryendpoint

### <a name="windows10generalconfigurationenterprisecloudprintdiscoverymaxlimit"></a>Windows10GeneralConfiguration. EnterpriseCloudPrintDiscoveryMaxLimit 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/enterprisecloudprint/discoverymaxprinterlimit

### <a name="windows10generalconfigurationenterprisecloudprintmopriadiscoveryresourceidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintMopriaDiscoveryResourceIdentifier 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/EnterpriseCloudPrint/MopriaDiscoveryResourceId

### <a name="windows10generalconfigurationenterprisecloudprintoauthauthority"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintOAuthAuthority 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/EnterpriseCloudPrint/CloudPrintOAuthAuthority

### <a name="windows10generalconfigurationenterprisecloudprintoauthclientidentifier"></a>Windows10GeneralConfiguration.EnterpriseCloudPrintOAuthClientIdentifier 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/EnterpriseCloudPrint/CloudPrintOAuthAuthority

### <a name="windows10generalconfigurationenterprisecloudprintresourceidentifier"></a>Windows10GeneralConfiguration. Enterprisecloudprintresourceıdentifier 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/enterprisecloudprint/cloudprintresourceıd

### <a name="windows10generalconfigurationexperienceblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration.ExperienceBlockConsumerSpecificFeatures 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsConsumerFeatures

### <a name="windows10generalconfigurationexperienceblockdevicediscovery"></a>Windows10GeneralConfiguration.ExperienceBlockDeviceDiscovery 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowDeviceDiscovery

### <a name="windows10generalconfigurationexperienceblockerrordialogwhennosim"></a>Windows10GeneralConfiguration.ExperienceBlockErrorDialogWhenNoSIM 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowSIMErrorDialogPromptWhenNoSIM

### <a name="windows10generalconfigurationexperienceblocktaskswitcher"></a>Windows10GeneralConfiguration.ExperienceBlockTaskSwitcher 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowTaskSwitcher

### <a name="windows10generalconfigurationexperienceblockwindowsspotlight"></a>Windows10GeneralConfiguration.ExperienceBlockWindowsSpotlight 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsSpotlight

### <a name="windows10generalconfigurationexperiencedonotsyncbrowsersettings"></a>Windows10GeneralConfiguration.ExperienceDoNotSyncBrowserSettings 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/DoNotSyncBrowserSettings

### <a name="windows10generalconfigurationgamedvrblocked"></a>Windows10GeneralConfiguration. Gamedvrbloke 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/allowgamedvr

### <a name="windows10generalconfigurationhardwaredeviceinstallationbydeviceidentifiers"></a>Windows10GeneralConfiguration. Hardwaredeviceınstalledbydevicetanýmlayýcýlarý 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceınstald/preventınstalymatchingdevicıdds

### <a name="windows10generalconfigurationhardwaredeviceinstallationbysetupclasses"></a>Windows10GeneralConfiguration. Hardwaredeviceınstalledbysetupclasses 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceınstal/preventınstalofmatchingdevicesetupclasses

### <a name="windows10generalconfigurationinkworkspaceaccess"></a>Windows10GeneralConfiguration. ınkworkspace erişimi 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowsinkıworkspace/Allowwindowsinkworkspace

### <a name="windows10generalconfigurationinkworkspaceaccessstate"></a>Windows10GeneralConfiguration. ınkworkspace AccessState 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowsinkıworkspace/Allowwindowsinkworkspace

### <a name="windows10generalconfigurationinkworkspaceblocksuggestedapps"></a>Windows10GeneralConfiguration. ınkworkspace Blockmütedapps 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/windowsinkworkspace/Allowmütedappsinwindowsinkworkspace

### <a name="windows10generalconfigurationinternetexploreractivexcontrolsinprotectedmode"></a>Windows10GeneralConfiguration. ınternetexploreractivexcontrolsinprotectedmode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/donotallowactivexcontrolsinprotectedmode

### <a name="windows10generalconfigurationinternetexplorerautocomplete"></a>Windows10GeneralConfiguration. ınternetexplorerautocomplete 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/allowautocomplete

### <a name="windows10generalconfigurationinternetexplorerblockoutdatedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerBlockOutdatedActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/DoNotBlockOutdatedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarnings"></a>Windows10GeneralConfiguration. ınternetexplorerbypasssmartekran uyarıları 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/disablebypassofsmartekran uyarıları

### <a name="windows10generalconfigurationinternetexplorerbypasssmartscreenwarningsaboutuncommonfiles"></a>Windows10GeneralConfiguration. ınternetexplorerbypasssmartscreenwarningsai Uncommonfiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/disablebypassofsmartscreenwarningsai uncommonfiles

### <a name="windows10generalconfigurationinternetexplorercertificateaddressmismatchwarning"></a>Windows10GeneralConfiguration. ınternetexplorercertificateaddressmismatchwarning 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/allowcertificateaddressmismatchwarning

### <a name="windows10generalconfigurationinternetexplorercheckservercertificaterevocation"></a>Windows10GeneralConfiguration.InternetExplorerCheckServerCertificateRevocation 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/CheckServerCertificateRevocation

### <a name="windows10generalconfigurationinternetexplorerchecksignaturesondownloadedprograms"></a>Windows10GeneralConfiguration. ınternetexplorerchecktabeturesondownloadedprograms 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/CheckSignaturesOnDownloadedPrograms

### <a name="windows10generalconfigurationinternetexplorercrashdetection"></a>Windows10GeneralConfiguration. ınternetexplorercrashdetection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/disablecrashdetection

### <a name="windows10generalconfigurationinternetexplorerdisableprocessesinenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerDisableProcessesInEnhancedProtectedMode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/DisableProcessesInEnhancedProtectedMode

### <a name="windows10generalconfigurationinternetexplorerdownloadenclosures"></a>Windows10GeneralConfiguration. ınternetexplorerdownloadkasaları 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/DisableEnclosureDownloading

### <a name="windows10generalconfigurationinternetexplorerencryptionsupport"></a>Windows10GeneralConfiguration. ınternetexplorerencryptionsupport 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/disableencryptionsupport

### <a name="windows10generalconfigurationinternetexplorerenhancedprotectedmode"></a>Windows10GeneralConfiguration.InternetExplorerEnhancedProtectedMode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/AllowEnhancedProtectedMode

### <a name="windows10generalconfigurationinternetexplorerfallbacktossl3"></a>Windows10GeneralConfiguration.InternetExplorerFallbackToSsl3 
**CSP**:./Device/Vendor/MSFT/Policy  
**Kayma URI 'si**:/config/InternetExplorer/allowfallbacktossl3

### <a name="windows10generalconfigurationinternetexplorerignorecertificateerrors"></a>Windows10GeneralConfiguration.InternetExplorerIgnoreCertificateErrors 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/disableıgnoringcertificateerrors

### <a name="windows10generalconfigurationinternetexplorerincludeallnetworkpaths"></a>Windows10GeneralConfiguration. ınternetexplorerincludeallnetworkpaths 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ıncludeallnetworkpaths

### <a name="windows10generalconfigurationinternetexplorerinternetzoneaccesstodatasources"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneaccesstodatasources 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowaccesstodatasources

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneallowonlyapproıda Domainstouseactivexcontrols 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowonlyapproıdidomainstouseactivexcontrols

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

### <a name="windows10generalconfigurationinternetexplorerinternetzoneallowvbscripttorun"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneallowvbscripttorun 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowvbscripttoruninınterneıse

### <a name="windows10generalconfigurationinternetexplorerinternetzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneautomaticpromptforfiledownloads 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowautomaticpromptingforfiledownloads

### <a name="windows10generalconfigurationinternetexplorerinternetzonecopyandpasteviascript"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneCopyAndPasteViaScript 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneAllowCopyPasteViaScript

### <a name="windows10generalconfigurationinternetexplorerinternetzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneCrossSiteScriptingFilter 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneenablecrosssitescriptingfilter

### <a name="windows10generalconfigurationinternetexplorerinternetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDoNotRunAntimalwareAgainstActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonedotnetframeworkreliantcomponents 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallownetframeworkreliantcomponents

### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadSignedActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneDownloadSignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDownloadUnsignedActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneDownloadUnsignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneDragAndDropOrCopyAndPasteFiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneAllowDragAndDropCopyAndPasteFiles

### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonedragcontentfromfarklı Entdomainsacrosswindows 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

### <a name="windows10generalconfigurationinternetexplorerinternetzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonedragcontentfromfarklıentdomainswithınwindows 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

### <a name="windows10generalconfigurationinternetexplorerinternetzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneincludelocalpathwhenuploadingfilestoserver 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneincludelocalpathwhenuploadingfilestoserver

### <a name="windows10generalconfigurationinternetexplorerinternetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorerinternetzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzonejavapermissions


### <a name="windows10generalconfigurationinternetexplorerinternetzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonelaunchapplicationsandfilesinaniframe 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzonelaunchingapplicationsandfilesiniframe

### <a name="windows10generalconfigurationinternetexplorerinternetzonelessprivilegedsites"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonelessprivilegedsites 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowlessprivilegedsites

### <a name="windows10generalconfigurationinternetexplorerinternetzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneloadingofxamlfiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowloadingofxamlfiles

### <a name="windows10generalconfigurationinternetexplorerinternetzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneLogonOptions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneLogonOptions

### <a name="windows10generalconfigurationinternetexplorerinternetzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonenavigatewindowsandframesacrossfarklıentdomains 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzonenavigatewindowsandframes

### <a name="windows10generalconfigurationinternetexplorerinternetzonepopupblocker"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonepopupengelleyicisini 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneusepopupengelleyicisini

### <a name="windows10generalconfigurationinternetexplorerinternetzoneprotectedmode"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneprotectedmode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneenableprotectedmode

### <a name="windows10generalconfigurationinternetexplorerinternetzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonerundotnetframeworkreliantcomponentssignedwithauthenticode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzonerunnetframeworkreliantcomponentssignedwithauthenticode

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonescriptingofwebbrowsercontrols 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowscriptingofınternetexplorerwebbrowsercontrols

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonescriptınitite Windows 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowscriptınitilıve Windows

### <a name="windows10generalconfigurationinternetexplorerinternetzonescriptlets"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonescriptizin 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowscriptizin

### <a name="windows10generalconfigurationinternetexplorerinternetzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneSecurityWarningForPotentiallyUnsafeFiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneShowSecurityWarningForPotentiallyUnsafeFiles

### <a name="windows10generalconfigurationinternetexplorerinternetzonesmartscreen"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzonessmarttagscreen 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ınternetzoneallowsmartscreenie

### <a name="windows10generalconfigurationinternetexplorerinternetzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration.InternetExplorerInternetZoneUpdatesToStatusBarViaScript 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneAllowUpdatesToStatusBarViaScript

### <a name="windows10generalconfigurationinternetexplorerinternetzoneuserdatapersistence"></a>Windows10GeneralConfiguration. ınternetexplorerınternetzoneuserdatakalıcılığı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/InternetZoneAllowUserDataPersistence

### <a name="windows10generalconfigurationinternetexplorerintranetzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneDoNotRunAntimalwareAgainstActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/IntranetZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerintranetzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerIntranetZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/IntranetZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorerintranetzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexploreretzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ıntranzonejavapermissions

### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerLocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/LocalMachineZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerlocalmachinezonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/localmachinezonejavapermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddowninternetzonesmartscreen"></a>Windows10GeneralConfiguration. ınternetexplorerlockeddownınternetzonessmarttagscreen 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/lockeddownınternetzoneallowsmartscreenie

### <a name="windows10generalconfigurationinternetexplorerlockeddownintranetzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerlockeddownetzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/lockeddownıntranjavapermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddownlocalmachinezonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerlockeddownlocalmachinezonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/lockeddownlocalmachinezonejavapermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerlockeddownkısıtlayıcı Tedzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/lockeddownkısıttedsiteszonejavapermissions

### <a name="windows10generalconfigurationinternetexplorerlockeddownrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration. ınternetexplorerlockeddownkısıtlayıcı Tedzonessmarttagscreen 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/lockeddownkısıttedsiteszoneallowsmartscreenie

### <a name="windows10generalconfigurationinternetexplorerlockeddowntrustedzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerlockeddowntrustedzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/lockeddowntrustedsiteszonejavapermissions

### <a name="windows10generalconfigurationinternetexplorerpreventmanagingsmartscreenfilter"></a>Windows10GeneralConfiguration.InternetExplorerPreventManagingSmartScreenFilter 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/PreventManagingSmartScreenFilter

### <a name="windows10generalconfigurationinternetexplorerpreventperuserinstallationofactivexcontrols"></a>Windows10GeneralConfiguration. ınternetexplorerpreventperuserınstaldactivexcontrols 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/preventperuserınstaletactivexcontrols

### <a name="windows10generalconfigurationinternetexplorerprocessesconsistentmimehandling"></a>Windows10GeneralConfiguration. ınternetexplorerprocessespotentmimehandling 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/potentmimehandlingınternetexplorerprocesses

### <a name="windows10generalconfigurationinternetexplorerprocessesmimesniffingsafetyfeature"></a>Windows10GeneralConfiguration.InternetExplorerProcessesMimeSniffingSafetyFeature 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/MimeSniffingSafetyFeatureInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesmkprotocolsecurityrestriction"></a>Windows10GeneralConfiguration. ınternetexplorerprocessesmkprotocolsecurityrestriction 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/MKProtocolSecurityRestrictionInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesnotificationbar"></a>Windows10GeneralConfiguration. ınternetexplorerprocessesnotificationbar 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/notificationbarınternetexplorerprocesses

### <a name="windows10generalconfigurationinternetexplorerprocessesprotectionfromzoneelevation"></a>Windows10GeneralConfiguration. ınternetexplorerprocessesprotectionfromzoneyükselmesi 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/protectionfromzoneyükseltmeden tionınternetexplorerprocesses

### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictactivexinstall"></a>Windows10GeneralConfiguration.InternetExplorerProcessesRestrictActiveXInstall 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictActiveXInstallInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesrestrictfiledownload"></a>Windows10GeneralConfiguration.InternetExplorerProcessesRestrictFileDownload 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictFileDownloadInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerprocessesscriptedwindowsecurityrestrictions"></a>Windows10GeneralConfiguration. ınternetexplorerprocessesscriptedwindowsecurityrestrictions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/ScriptedWindowSecurityRestrictionsInternetExplorerProcesses

### <a name="windows10generalconfigurationinternetexplorerremoverunthistimebuttonforoutdatedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRemoveRunThisTimeButtonForOutdatedActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RemoveRunThisTimeButtonForOutdatedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneaccesstodatasources"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzoneaccesstodatasources 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowaccesstodatasources

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneactivescripting"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneActiveScripting 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowActiveScripting

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstouseactivexcontrols"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzoneallowonlyapproıda Domainstouseactivexcontrols 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowonlyapproıda domainstouseactivexcontrols

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowonlyapproveddomainstousetdcactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneAllowOnlyApprovedDomainsToUseTdcActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowOnlyApprovedDomainsToUseTDCActiveXControl

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneallowvbscripttorun"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzoneallowvbscripttorun 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowvbscripttoruninınterneıse

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneautomaticpromptforfiledownloads"></a>Windows10GeneralConfiguration. ınternetexplorerkısıttedzoneautomaticpromptforfiledownloads 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowautomaticpromptingforfiledownloads

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonebinaryandscriptbehaviors"></a>Windows10GeneralConfiguration. ınternetexplorerkısıttedzonebinaryandscriptdavranışlar 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowbinaryandscriptdavranışlar

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecopyandpasteviascript"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneCopyAndPasteViaScript 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowCopyPasteViaScript

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonecrosssitescriptingfilter"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneCrossSiteScriptingFilter 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneenablecrosssitescriptingfilter

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDoNotRunAntimalwareAgainstActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedotnetframeworkreliantcomponents"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonedotnetframeworkreliantcomponents 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallownetframeworkreliantcomponents

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadSignedActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneDownloadSignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedownloadunsignedactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDownloadUnsignedActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneDownloadUnsignedActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedraganddroporcopyandpastefiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneDragAndDropOrCopyAndPasteFiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowDragAndDropCopyAndPasteFiles

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainsacrosswindows"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonedragcontentfromfarklı Entdomainsacrosswindows 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsAcrossWindows

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonedragcontentfromdifferentdomainswithinwindows"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonedragcontentfromfarklıentdomainswithınwindows 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneEnableDraggingOfContentFromDifferentDomainsWithinWindows

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonefiledownloads"></a>Windows10GeneralConfiguration. ınternetexplorerkısıttedzonefiledownloads 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıttedsiteszoneallowfiledownloads

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneincludelocalpathwhenuploadingfilestoserver"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzoneincludelocalpathwhenuploadingfilestoserver 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneincludelocalpathwhenuploadingfilestoserver

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorerkısıttedzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszonejavapermissions

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelaunchapplicationsandfilesinaniframe"></a>Windows10GeneralConfiguration. ınternetexplorerkısıttedzonelaunchapplicationsandfilesinaniframe 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszonelaunchingapplicationsandfilesiniframe

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelessprivilegedsites"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonelessprivilegedsites 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowlessprivilegedsites

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneloadingofxamlfiles"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzoneloadingofxamlfiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowloadingofxamlfiles

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonelogonoptions"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneLogonOptions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneLogonOptions

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonemetarefresh"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneMetaRefresh 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowMETAREFRESH

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonenavigatewindowsandframesacrossdifferentdomains"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonenavigatewindowsandframesacrossfarklıentdomains 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszonenavigatewindowsandframes

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonepopupblocker"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonepopupengelleyicisini 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneusepopupengelleyicisini

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneprotectedmode"></a>Windows10GeneralConfiguration. ınternetexplorerkısıttedzoneprotectedmode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneturnonprotectedmode

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerunactivexcontrolsandplugins"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonerunactivexcontrolsandeklentiler 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszonerunactivexcontrolsandeklentileri

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonerundotnetframeworkreliantcomponentssignedwithauthenticode"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonerundotnetframeworkreliantcomponentssignedwithauthenticode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszonerunnetframeworkreliantcomponentssignedwithauthenticode

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptactivexcontrolsmarkedsafeforscripting"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneScriptActiveXControlsMarkedSafeForScripting 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneScriptActiveXControlsMarkedSafeForScripting

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofjavaapplets"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonescriptingofjavaapplet 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszonescriptingofjavaapplet

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptingofwebbrowsercontrols"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonescriptingofwebbrowsercontrols 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowscriptingofınternetexplorerwebbrowsercontrols

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptinitiatedwindows"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonescriptınititedwindows 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowscriptınititedwindows

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonescriptlets"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonescriptizin 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowscriptizin

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesecuritywarningforpotentiallyunsafefiles"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneSecurityWarningForPotentiallyUnsafeFiles 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneShowSecurityWarningForPotentiallyUnsafeFiles

### <a name="windows10generalconfigurationinternetexplorerrestrictedzonesmartscreen"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzonessmarttagscreen 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/kısıtlayıcı tedsiteszoneallowsmartscreenie

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneupdatestostatusbarviascript"></a>Windows10GeneralConfiguration.InternetExplorerRestrictedZoneUpdatesToStatusBarViaScript 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowUpdatesToStatusBarViaScript

### <a name="windows10generalconfigurationinternetexplorerrestrictedzoneuserdatapersistence"></a>Windows10GeneralConfiguration. ınternetexplorerkısıtlayıcı Tedzoneuserdatakalıcılığı 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/RestrictedSitesZoneAllowUserDataPersistence

### <a name="windows10generalconfigurationinternetexplorersecuritysettingscheck"></a>Windows10GeneralConfiguration. ınternetexplorersecuritysettingscheck 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/disablesecuritysettingscheck

### <a name="windows10generalconfigurationinternetexplorersecurityzonesuseonlymachinesettings"></a>Windows10GeneralConfiguration. ınternetexplorersecurityzonesuseonlymachinesettings 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/securityzonesuseonlymachinesettings

### <a name="windows10generalconfigurationinternetexplorersoftwarewhensignatureisinvalid"></a>Windows10GeneralConfiguration. ınternetexplorersoftwarewhensignatureısgeçersiz 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/allowsoftwarewhensignatureısgeçersiz

### <a name="windows10generalconfigurationinternetexplorertrustedzonedonotrunantimalwareagainstactivexcontrols"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneDoNotRunAntimalwareAgainstActiveXControls 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/TrustedSitesZoneDoNotRunAntimalwareAgainstActiveXControls

### <a name="windows10generalconfigurationinternetexplorertrustedzoneinitializeandscriptactivexcontrolsnotmarkedassafe"></a>Windows10GeneralConfiguration.InternetExplorerTrustedZoneInitializeAndScriptActiveXControlsNotMarkedAsSafe 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/TrustedSitesZoneInitializeAndScriptActiveXControls

### <a name="windows10generalconfigurationinternetexplorertrustedzonejavapermissions"></a>Windows10GeneralConfiguration. ınternetexplorertrustedzonejavapermissions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/trustedsiteszonejavapermissions

### <a name="windows10generalconfigurationinternetexploreruseactivexinstallerservice"></a>Windows10GeneralConfiguration. ınternetexploreruseactivexınstallerservice 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/belirtimi yuseofactivexınstallerservice

### <a name="windows10generalconfigurationinternetexplorerusersaddingsites"></a>Windows10GeneralConfiguration. ınternetexplorerusersaddingsites 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/DoNotAllowUsersToAddSites

### <a name="windows10generalconfigurationinternetexploreruserschangingpolicies"></a>Windows10GeneralConfiguration. ınternetexploreruserschangingpolicies 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/InternetExplorer/DoNotAllowUsersToChangePolicies

### <a name="windows10generalconfigurationinternetsharingblocked"></a>Windows10GeneralConfiguration. ınternetsharingengellenen 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WiFi/AllowInternetSharing

### <a name="windows10generalconfigurationlocationservicesblocked"></a>Windows10GeneralConfiguration. Locationservicesengellendi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/AllowLocation

### <a name="windows10generalconfigurationlockscreenallowtimeoutconfiguration"></a>Windows10GeneralConfiguration. LockScreenAllowTimeoutConfiguration 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/AllowScreenTimeoutWhileLockedUser/config

### <a name="windows10generalconfigurationlockscreenblockactioncenternotifications"></a>Windows10GeneralConfiguration. LockScreenBlockActionCenterNotifications 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AboveLock/AllowActionCenterNotifications

### <a name="windows10generalconfigurationlockscreenblockcortana"></a>Windows10GeneralConfiguration. LockScreenBlockCortana 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AboveLock/AllowCortanaAboveLock

### <a name="windows10generalconfigurationlockscreenblocktoastnotifications"></a>Windows10GeneralConfiguration. LockScreenBlockToastNotifications 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/AboveLock/AllowToasts

### <a name="windows10generalconfigurationlockscreencamera"></a>Windows10GeneralConfiguration. LockScreenCamera 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/koruyucu tenablinglockscreencamera

### <a name="windows10generalconfigurationlockscreenhidenetworkselectionui"></a>Windows10GeneralConfiguration.LockScreenHideNetworkSelectionUI 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsLogon/dontdisplaynetworkselectionuı

### <a name="windows10generalconfigurationlockscreenslideshow"></a>Windows10GeneralConfiguration. Lockscreenslayt gösterisi 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/preventlockscreenslayt gösterisi

### <a name="windows10generalconfigurationlockscreentimeoutinseconds"></a>Windows10GeneralConfiguration.LockScreenTimeoutInSeconds 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/ScreenTimeoutWhileLocked

### <a name="windows10generalconfigurationlogonblockfastuserswitching"></a>Windows10GeneralConfiguration. Logonblockfastuseranahtarlama 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsLogon/hidefastuseranahtarlama

### <a name="windows10generalconfigurationmessagingblockmms"></a>Windows10GeneralConfiguration. MessagingBlockMMS 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Messaging/allowmms

### <a name="windows10generalconfigurationmessagingblockrichcommunicationservices"></a>Windows10GeneralConfiguration. MessagingBlockRichCommunicationServices 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Messaging/allowrcs

### <a name="windows10generalconfigurationmessagingblocksync"></a>Windows10GeneralConfiguration. MessagingBlockSync 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Messaging/allowiletisync

### <a name="windows10generalconfigurationmicrosoftaccountblocked"></a>Windows10GeneralConfiguration. Microsoftaccountengellendi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/accounts/allowmicrosoftaccountconnection

### <a name="windows10generalconfigurationmicrosoftaccountblocksettingssync"></a>Windows10GeneralConfiguration. MicrosoftAccountBlockSettingsSync 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowSyncMySettings

### <a name="windows10generalconfigurationmicrosoftaccountsigninassistantsettings"></a>Windows10GeneralConfiguration. Microsoftaccountsignınyardım Tantsettings 
**CSP**:./Device/Vendor/MSFT/accounts  
**Konum URI 'si**:/Allowmicrosoftaccountsignınassistant

### <a name="windows10generalconfigurationnetworkproxyapplysettingsdevicewide"></a>Windows10GeneralConfiguration. NetworkProxyApplySettingsDeviceWide 
**CSP**:./Device/Vendor/MSFT/networkproxy  
**Konum URI 'si**:/Proxysettingsperuser

### <a name="windows10generalconfigurationnetworkproxyautomaticconfigurationurl"></a>Windows10GeneralConfiguration.NetworkProxyAutomaticConfigurationUrl 
**CSP**:./Device/Vendor/MSFT/networkproxy  
**Konum URI 'si**:/Setupscripturl

### <a name="windows10generalconfigurationnetworkproxydisableautodetect"></a>Windows10GeneralConfiguration. Networkproxydisableotomatik Algıla 
**CSP**:./Device/Vendor/MSFT/networkproxy  
**Konum URI 'si**:/otomatik algıla

### <a name="windows10generalconfigurationnetworkproxyserver"></a>Windows10GeneralConfiguration. NetworkProxyServer 
**CSP**:./Vendor/MSFT/networkproxy  
**Uzaklığa göre URI**:/ProxyAddress,/Exceptions ve/Useproxyforlocalaadresler

### <a name="windows10generalconfigurationnfcblocked"></a>Windows10GeneralConfiguration. Nfcbloke 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/allownfc

### <a name="windows10generalconfigurationonedrivedisablefilesync"></a>Windows10GeneralConfiguration. OneDriveDisableFileSync 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/disableonedrivefilesync

### <a name="windows10generalconfigurationpasswordblocksimple"></a>Windows10GeneralConfiguration. PasswordBlockSimple 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/allowsimpledevicepassword

### <a name="windows10generalconfigurationpasswordexpirationdays"></a>Windows10GeneralConfiguration.PasswordExpirationDays 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/devicepasswordexpiasyon

### <a name="windows10generalconfigurationpasswordminimumageindays"></a>Windows10GeneralConfiguration. Passwordminimumageındays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/en düşük öncelik

### <a name="windows10generalconfigurationpasswordminimumcharactersetcount"></a>Windows10GeneralConfiguration. Passwordminimumkaraktersetcount 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/mindevicepasswordcomplexcharacters

### <a name="windows10generalconfigurationpasswordminimumlength"></a>Windows10GeneralConfiguration. PasswordMinimumLength 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/mindevicepasswordlength

### <a name="windows10generalconfigurationpasswordminutesofinactivitybeforescreentimeout"></a>Windows10GeneralConfiguration. Passwordminutesofınactivitybeforescreentimeout 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/MaxInactivityTimeDeviceLock

### <a name="windows10generalconfigurationpasswordpreviouspasswordblockcount"></a>Windows10GeneralConfiguration. PasswordPreviousPasswordBlockCount 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/DevicePasswordHistory

### <a name="windows10generalconfigurationpasswordrequired"></a>Windows10GeneralConfiguration. PasswordRequired 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/DevicePasswordEnabled

### <a name="windows10generalconfigurationpasswordrequiredtype"></a>Windows10GeneralConfiguration. PasswordRequiredType 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/alfanümerik gerekli

### <a name="windows10generalconfigurationpasswordrequirewhenresumefromidlestate"></a>Windows10GeneralConfiguration. Passwordrequirewhenresumefromidtastate 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/AllowIdleReturnWithoutPassword

### <a name="windows10generalconfigurationpasswordsigninfailurecountbeforefactoryreset"></a>Windows10GeneralConfiguration.PasswordSignInFailureCountBeforeFactoryReset 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/DeviceLock/MaxDevicePasswordFailedAttempts

### <a name="windows10generalconfigurationpersonalizationdesktopimageurl"></a>Windows10GeneralConfiguration. Personalizationdesktopımageurl 
**CSP**:./Device/Vendor/MSFT/kişiselleştirmesi  
**Konum URI**'si:/Desktopımageurl

### <a name="windows10generalconfigurationpersonalizationlockscreenimageurl"></a>Windows10GeneralConfiguration. Personalizationlockscreenımageurl 
**CSP**:./Device/Vendor/MSFT/kişiselleştirmesi  
**Konum URI 'si**:/Lockscreenımageurl

### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhileonbattery"></a>Windows10GeneralConfiguration.PowerRequirePasswordOnWakeWhileOnBattery 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Power/RequirePasswordWhenComputerWakesOnBattery

### <a name="windows10generalconfigurationpowerrequirepasswordonwakewhilepluggedin"></a>Windows10GeneralConfiguration.PowerRequirePasswordOnWakeWhilePluggedIn 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Power/RequirePasswordWhenComputerWakesPluggedIn

### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhileonbattery"></a>Windows10GeneralConfiguration. Powerstandbystateswhenımepingwhileonpili 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Power/AllowStandbyStatesWhenSleepingOnBattery

### <a name="windows10generalconfigurationpowerstandbystateswhensleepingwhilepluggedin"></a>Windows10GeneralConfiguration. Powerstandbystateswhenımepingwhilepluggedın 
**CSP**:./Device/Vendor/MSFT/Policy  
**UZAKLıĞı URI**:/config/Power/allowstandbywhenuyıingpluggedın

### <a name="windows10generalconfigurationpreventinstallationofmatchingdeviceids"></a>windows10generalconfiguration. Preventınstalmatchingdevicıdds 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceınstald/preventınstalymatchingdevicıdds

### <a name="windows10generalconfigurationpreventinstallationofmatchingdevicesetupclasses"></a>windows10generalconfiguration. Preventınstalofmatchingdevicesetupclasses 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/deviceınstal/preventınstalofmatchingdevicesetupclasses

### <a name="windows10generalconfigurationprinterblockaddition"></a>Windows10GeneralConfiguration. Printerblockekleme 
**CSP**:./User/Vendor/MSFT/Policy  
**Kaydırma URI 'si**:/config/eğitication/önleyici taddingnewprinters

### <a name="windows10generalconfigurationprinterdefaultname"></a>Windows10GeneralConfiguration. PrinterDefaultName 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/eğitication/defaultyazıcıadı

### <a name="windows10generalconfigurationprinternames"></a>Windows10GeneralConfiguration. YazıcıAdı 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/eğitication/printernames

### <a name="windows10generalconfigurationprivacyadvertisingid"></a>Windows10GeneralConfiguration. Privacyadvertisingıd 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/privacy/disableadvertisingıd

### <a name="windows10generalconfigurationprivacyautoacceptpairingandconsentprompts"></a>Windows10GeneralConfiguration.PrivacyAutoAcceptPairingAndConsentPrompts 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/privacy/AllowAutoAcceptPairingAndPrivacyConsentPrompts

### <a name="windows10generalconfigurationprivacyblockactivityfeed"></a>Windows10GeneralConfiguration. PrivacyBlockActivityFeed 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/privacy/enableactivityfeed

### <a name="windows10generalconfigurationprivacyblockinputpersonalization"></a>Windows10GeneralConfiguration. Privacyblockinputkişiselleştirmesi 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/privacy/allowwınputkişiselleştirmesi

### <a name="windows10generalconfigurationprivacyblockpublishuseractivities"></a>Windows10GeneralConfiguration. PrivacyBlockPublishUserActivities 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/privacy/publishuseractivities

### <a name="windows10generalconfigurationsafesearchfilter"></a>Windows10GeneralConfiguration. SafeSearchFilter 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/safesearchpermissions

### <a name="windows10generalconfigurationscreencaptureblocked"></a>Windows10GeneralConfiguration. Screencaptureengelleniyor 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowScreenCapture

### <a name="windows10generalconfigurationsearchblockdiacritics"></a>Windows10GeneralConfiguration. Searchblockaksanlarını 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/allowusingaksanlar

### <a name="windows10generalconfigurationsearchblockwebresults"></a>Windows10GeneralConfiguration. SearchBlockWebResults 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/donotusewebresults

### <a name="windows10generalconfigurationsearchdisableautolanguagedetection"></a>Windows10GeneralConfiguration. Searchdisableoto Languagedetection 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/alwaysuseoto langdetection

### <a name="windows10generalconfigurationsearchdisableindexerbackoff"></a>Windows10GeneralConfiguration.SearchDisableIndexerBackoff 
**CSP**:./Device/Vendor/MSFT/Policy  
**Kayma URI 'si**:/config/Search/DisableBackoff

### <a name="windows10generalconfigurationsearchdisableindexingencrypteditems"></a>Windows10GeneralConfiguration. Searchdisableındexingencrypteditems 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/allowwındexingencryptedstoresorıtems

### <a name="windows10generalconfigurationsearchdisableindexingremovabledrive"></a>Windows10GeneralConfiguration. Searchdisableındexingremovabledrive 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/disableremovabledriveındexing

### <a name="windows10generalconfigurationsearchdisablelocation"></a>Windows10GeneralConfiguration. SearchDisableLocation 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/allowsearchtouselocation

### <a name="windows10generalconfigurationsearchdisableuselocation"></a>Windows10GeneralConfiguration. SearchDisableUseLocation 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/allowsearchtouselocation

### <a name="windows10generalconfigurationsearchenableautomaticindexsizemanangement"></a>Windows10GeneralConfiguration. Searchenableautomaticındexsizemananmi 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/preventındexinglowdiskspacemb

### <a name="windows10generalconfigurationsearchenableremotequeries"></a>Windows10GeneralConfiguration. SearchEnableRemoteQueries 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Search/preventremotequeries

### <a name="windows10generalconfigurationsecurityblockazureadjoineddevicesautoencryption"></a>Windows10GeneralConfiguration.SecurityBlockAzureADJoinedDevicesAutoEncryption 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Security/önleyici tautomaticdeviceencryptionforazureadjoineddevices

### <a name="windows10generalconfigurationsettingsblockaccountspage"></a>Windows10GeneralConfiguration. SettingsBlockAccountsPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockaddprovisioningpackage"></a>Windows10GeneralConfiguration. SettingsBlockAddProvisioningPackage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Security/allowaddprovisioningpackage

### <a name="windows10generalconfigurationsettingsblockappspage"></a>Windows10GeneralConfiguration. SettingsBlockAppsPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockchangelanguage"></a>Windows10GeneralConfiguration. SettingsBlockChangeLanguage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/allowlanguage

### <a name="windows10generalconfigurationsettingsblockchangepowersleep"></a>Windows10GeneralConfiguration. SettingsBlockChangePowerSleep 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/allowpowersleep

### <a name="windows10generalconfigurationsettingsblockchangeregion"></a>Windows10GeneralConfiguration. SettingsBlockChangeRegion 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/allowregion

### <a name="windows10generalconfigurationsettingsblockchangesystemtime"></a>Windows10GeneralConfiguration. Settingsblockchangessystemtime 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/allowdatetime

### <a name="windows10generalconfigurationsettingsblockdevicespage"></a>Windows10GeneralConfiguration. SettingsBlockDevicesPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockeaseofaccesspage"></a>Windows10GeneralConfiguration. SettingsBlockEaseOfAccessPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockeditdevicename"></a>Windows10GeneralConfiguration. Settingsblockeditaygıtadı 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/alloweditaygıtadı

### <a name="windows10generalconfigurationsettingsblockgamingpage"></a>Windows10GeneralConfiguration. SettingsBlockGamingPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblocknetworkinternetpage"></a>Windows10GeneralConfiguration. Settingsblocknetworkınternetsayfası 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockpersonalizationpage"></a>Windows10GeneralConfiguration. SettingsBlockPersonalizationPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockprivacypage"></a>Windows10GeneralConfiguration. SettingsBlockPrivacyPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockremoveprovisioningpackage"></a>Windows10GeneralConfiguration. SettingsBlockRemoveProvisioningPackage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Security/allowremoveprovisioningpackage

### <a name="windows10generalconfigurationsettingsblocksystempage"></a>Windows10GeneralConfiguration. SettingsBlockSystemPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblocktimelanguagepage"></a>Windows10GeneralConfiguration. SettingsBlockTimeLanguagePage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationsettingsblockupdatesecuritypage"></a>Windows10GeneralConfiguration. SettingsBlockUpdateSecurityPage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Settings/pagevisibilitylist

### <a name="windows10generalconfigurationshareduserappdataallowed"></a>Windows10GeneralConfiguration.SharedUserAppDataAllowed 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/allowshareduserappdata

### <a name="windows10generalconfigurationsmartscreenblockpromptoverride"></a>Windows10GeneralConfiguration.SmartScreenBlockPromptOverride 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/PreventSmartScreenPromptOverride

### <a name="windows10generalconfigurationsmartscreenblockpromptoverrideforfiles"></a>Windows10GeneralConfiguration.SmartScreenBlockPromptOverrideForFiles 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/PreventSmartScreenPromptOverrideForFiles

### <a name="windows10generalconfigurationsmartscreenenableappinstallcontrol"></a>Windows10GeneralConfiguration. Smartscreenenableappınstallcontrol 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/SmartScreen/enableappınstallcontrol

### <a name="windows10generalconfigurationstartblockunpinningappsfromtaskbar"></a>Windows10GeneralConfiguration. Startblockunpinningappsfromgörev çubuğu 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/nopinningtogörev çubuğu

### <a name="windows10generalconfigurationstartmenuapplistvisibility"></a>Windows10GeneralConfiguration.StartMenuAppListVisibility 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/HideAppList

### <a name="windows10generalconfigurationstartmenuhidechangeaccountsettings"></a>Windows10GeneralConfiguration. StartMenuHideChangeAccountSettings 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hidechangeaccountsettings

### <a name="windows10generalconfigurationstartmenuhidefrequentlyusedapps"></a>Windows10GeneralConfiguration. Startmenuhidefkarşılandığından Entlyusedapps 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hidefkarşılandığından entlyusedapps

### <a name="windows10generalconfigurationstartmenuhidehibernate"></a>Windows10GeneralConfiguration. Startmenuhidehazırda bekleme 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hidehazırda beklet

### <a name="windows10generalconfigurationstartmenuhidelock"></a>Windows10GeneralConfiguration. StartMenuHideLock 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hidelock

### <a name="windows10generalconfigurationstartmenuhidepowerbutton"></a>Windows10GeneralConfiguration.StartMenuHidePowerButton 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/HidePowerButton

### <a name="windows10generalconfigurationstartmenuhiderecentjumplists"></a>Windows10GeneralConfiguration.StartMenuHideRecentJumpLists 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/HideRecentJumplists

### <a name="windows10generalconfigurationstartmenuhiderecentlyaddedapps"></a>Windows10GeneralConfiguration.StartMenuHideRecentlyAddedApps 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/HideRecentlyAddedApps

### <a name="windows10generalconfigurationstartmenuhiderestartoptions"></a>Windows10GeneralConfiguration. StartMenuHideRestartOptions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hiderestart

### <a name="windows10generalconfigurationstartmenuhideshutdown"></a>Windows10GeneralConfiguration. Startmenuhidekapatması 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hidekapatmadan

### <a name="windows10generalconfigurationstartmenuhidesignout"></a>Windows10GeneralConfiguration.StartMenuHideSignOut 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/HideSignOut

### <a name="windows10generalconfigurationstartmenuhidesleep"></a>Windows10GeneralConfiguration. StartMenuHideSleep 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hidesleep

### <a name="windows10generalconfigurationstartmenuhideswitchaccount"></a>Windows10GeneralConfiguration. StartMenuHideSwitchAccount 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hideswitchaccount

### <a name="windows10generalconfigurationstartmenuhideusertile"></a>Windows10GeneralConfiguration. StartMenuHideUserTile 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/hideusertile

### <a name="windows10generalconfigurationstartmenulayoutedgeassetsxml"></a>Windows10GeneralConfiguration. StartMenuLayoutEdgeAssetsXml 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/ımportedgevarlıklarını

### <a name="windows10generalconfigurationstartmenulayoutxml"></a>Windows10GeneralConfiguration. Startmenulabir XML 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/startlayout

### <a name="windows10generalconfigurationstartmenumode"></a>Windows10GeneralConfiguration. StartMenuMode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/forcestartsize

### <a name="windows10generalconfigurationstartmenupinnedfolderdocuments"></a>Windows10GeneralConfiguration. Startmenupınnedfolderdocuments 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfolderdocuments

### <a name="windows10generalconfigurationstartmenupinnedfolderdownloads"></a>Windows10GeneralConfiguration. Startmenupınnedfolderdownloads 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfolderdownloads

### <a name="windows10generalconfigurationstartmenupinnedfolderfileexplorer"></a>Windows10GeneralConfiguration. Startmenupınnedfolderfileexplorer 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfolderfileexplorer

### <a name="windows10generalconfigurationstartmenupinnedfolderhomegroup"></a>Windows10GeneralConfiguration. Startmenupınnedfolderev grubu 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfolderev grubu

### <a name="windows10generalconfigurationstartmenupinnedfoldermusic"></a>Windows10GeneralConfiguration. Startmenupınnedfoldermusic 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfoldermusic

### <a name="windows10generalconfigurationstartmenupinnedfoldernetwork"></a>Windows10GeneralConfiguration. Startmenupınnedfoldernetwork 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfoldernetwork

### <a name="windows10generalconfigurationstartmenupinnedfolderpersonalfolder"></a>Windows10GeneralConfiguration. Startmenupınnedfolderpersonal klasörü 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfolderpersonfolder

### <a name="windows10generalconfigurationstartmenupinnedfolderpictures"></a>Windows10GeneralConfiguration. Startmenupınnedfolderresimlerim 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfolderresimlerim

### <a name="windows10generalconfigurationstartmenupinnedfoldersettings"></a>Windows10GeneralConfiguration. Startmenupınnedfoldersettings 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfoldersettings

### <a name="windows10generalconfigurationstartmenupinnedfoldervideos"></a>Windows10GeneralConfiguration. Startmenupınnedfoldervideolarım 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/start/allowpinnedfoldervideolarım

### <a name="windows10generalconfigurationstorageblockremovablestorage"></a>Windows10GeneralConfiguration. StorageBlockRemovableStorage 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/AllowStorageCard

### <a name="windows10generalconfigurationstoragerequiremobiledeviceencryption"></a>Windows10GeneralConfiguration. Storagerequiremobileşen Deviceencryption 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Security/requiredeviceencryption

### <a name="windows10generalconfigurationstoragerestrictappdatatosystemvolume"></a>Windows10GeneralConfiguration. StorageRestrictAppDataToSystemVolume 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/kısıttappdatatosystemvolume

### <a name="windows10generalconfigurationstoragerestrictappinstalltosystemvolume"></a>Windows10GeneralConfiguration. Storagerestrictappınstalltosystemvolume 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/kısıttapptosystemvolume

### <a name="windows10generalconfigurationsystembootstartdriverinitialization"></a>Windows10GeneralConfiguration. Systembootstartdriverınitialization 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/bootstartdriverınitialization

### <a name="windows10generalconfigurationsystemtelemetryproxyserver"></a>Windows10GeneralConfiguration.SystemTelemetryProxyServer 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/System/TelemetryProxy

### <a name="windows10generalconfigurationtaskmanagerblockendtask"></a>Windows10GeneralConfiguration. TaskManagerBlockEndTask 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/taskmanager/allowendtask

### <a name="windows10generalconfigurationtenantlockdownrequirenetworkduringoutofboxexperience"></a>Windows10GeneralConfiguration. Tenantlockdowntalep ırenetworkduringoutofboxexperience 
**CSP**:./Vendor/MSFT/tenantlockdown  
**Konum URI 'si**:/karşılandığından ırenetworkınoobe

### <a name="windows10generalconfigurationusbblocked"></a>Windows10GeneralConfiguration. Usbbloke 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/connectivity/allowusbconnection

### <a name="windows10generalconfigurationvoicerecordingblocked"></a>Windows10GeneralConfiguration. Voicerkaydedilmiş Dingengellenen 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowVoiceRecording

### <a name="windows10generalconfigurationwebrtcblocklocalhostipaddress"></a>Windows10GeneralConfiguration. Webrtcblocklocalhostıpaddress 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/önleyici tusinglocalhostıpaddressforwebrtc

### <a name="windows10generalconfigurationwifiblockautomaticconnecthotspots"></a>Windows10GeneralConfiguration.WiFiBlockAutomaticConnectHotspots 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WiFi/AllowAutoConnectToWiFiSenseHotspots

### <a name="windows10generalconfigurationwifiblocked"></a>Windows10GeneralConfiguration.WiFiBlocked 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WiFi/AllowWiFi

### <a name="windows10generalconfigurationwifiblockmanualconfiguration"></a>Windows10GeneralConfiguration.WiFiBlockManualConfiguration 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WiFi/AllowManualWiFi/Configuration

### <a name="windows10generalconfigurationwifiscaninterval"></a>Windows10GeneralConfiguration. Wifiscanınterval 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WiFi/WLANScanMode

### <a name="windows10generalconfigurationwindowslogonlocalusersondomainjoinedcomputers"></a>Windows10GeneralConfiguration. WindowsLogOnLocalUsersOnDomainJoinedComputers 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WindowsLogon/enumeratelocalusersondomainjoinedcomputers

### <a name="windows10generalconfigurationwindowsspotlightblockconsumerspecificfeatures"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockConsumerSpecificFeatures 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsConsumerFeatures

### <a name="windows10generalconfigurationwindowsspotlightblocked"></a>Windows10GeneralConfiguration.WindowsSpotlightBlocked 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsSpotlight

### <a name="windows10generalconfigurationwindowsspotlightblockonactioncenter"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockOnActionCenter 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsSpotlightOnActionCenter

### <a name="windows10generalconfigurationwindowsspotlightblocktailoredexperiences"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockTailoredExperiences 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowTailoredExperiencesWithDiagnosticData

### <a name="windows10generalconfigurationwindowsspotlightblockthirdpartynotifications"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockThirdPartyNotifications 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowThirdPartySuggestionsInWindowsSpotlight

### <a name="windows10generalconfigurationwindowsspotlightblockwelcomeexperience"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockWelcomeExperience 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsSpotlightWindowsWelcomeExperience

### <a name="windows10generalconfigurationwindowsspotlightblockwindowstips"></a>Windows10GeneralConfiguration.WindowsSpotlightBlockWindowsTips 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/AllowWindowsTips

### <a name="windows10generalconfigurationwindowsspotlightconfigureonlockscreen"></a>Windows10GeneralConfiguration.WindowsSpotlightConfigureOnLockScreen 
**CSP**:./User/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Experience/ConfigureWindowsSpotlightOnLockScreen

### <a name="windows10generalconfigurationwindowsstoreblockautoupdate"></a>Windows10GeneralConfiguration. WindowsStoreBlockAutoUpdate 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/allowappstoreautoupdate

### <a name="windows10generalconfigurationwindowsstoreblocked"></a>Windows10GeneralConfiguration. Windowsstoreengellendi 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/allowstore

### <a name="windows10generalconfigurationwindowsstoreenableprivatestoreonly"></a>Windows10GeneralConfiguration. WindowsStoreEnablePrivateStoreOnly 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/ApplicationManagement/requireprivatestoreonly

### <a name="windows10generalconfigurationwirelessdisplayblockprojectiontothisdevice"></a>Windows10GeneralConfiguration. Kablosuzdisplayblockprojectiontothisdevice 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kablolessdisplay/allowprojectiontopc

### <a name="windows10generalconfigurationwirelessdisplayblockuserinputfromreceiver"></a>Windows10GeneralConfiguration. Kablolessdisplayblockuserınputfromalıcısı 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/WirelessDisplay/AllowUserInputFromWirelessDisplayReceiver

### <a name="windows10generalconfigurationwirelessdisplayrequirepinforpairing"></a>Windows10GeneralConfiguration. Kablolessdisplayrequirepınforeşleştirmeye 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kablolessdisplay/requirepınforıdentifier

### <a name="windows10networkboundaryconfigurationwindowsnetworkisolationpolicy"></a>Windows10NetworkBoundaryConfiguration. Windowsnetworkısolationpolicy 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/networkısolation/enterprisecloudresources,/config/networkısolation/enterpriseiprange,/config/NetworkIsolation/EnterpriseIPRangesAreAuthoritative,/config/networkısolation/ Enterpriseınternalproxyservers,/config/networkısolation/enterprenetworkdomainnames,/config/networkısolation/enterpriseproxyservers,/config/networkısolation/enterpriseproxyserversareyetkilendirmeli,/config/networkısolation/ NeutralResources

### <a name="windows10policyoverrideconfigurationprefermdmovergrouppolicy"></a>Windows10PolicyOverrideConfiguration. PreferMdmOverGroupPolicy 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/controlpolicyconflict/mdmwinsovergp

### <a name="windows10secureassessmentconfigurationallowprinting"></a>Windows10SecureAssessmentConfiguration. AllowPrinting 
**CSP**:./Vendor/MSFT/secureastement  
**Konum URI 'si**:/Requireprinting

### <a name="windows10secureassessmentconfigurationallowscreencapture"></a>Windows10SecureAssessmentConfiguration. AllowScreenCapture 
**CSP**:./Vendor/MSFT/secureastement  
**Konum URI 'si**:/Allowscreenmonitoring

### <a name="windows10secureassessmentconfigurationallowtextsuggestion"></a>Windows10SecureAssessmentConfiguration. Allowtextöneriyi 
**CSP**:./Vendor/MSFT/secureastement  
**Konum URI 'si**:/Allowtextönerilere

### <a name="windows10secureassessmentconfigurationconfigurationaccount"></a>Windows10SecureAssessmentConfiguration. ConfigurationAccount 
**CSP**:./Vendor/MSFT/secureastement  
**Konum URI 'si**:/Testeraccount

### <a name="windows10secureassessmentconfigurationconfigurationaccounttype"></a>Windows10SecureAssessmentConfiguration. ConfigurationAccountType 
**CSP**:./Vendor/MSFT/secureastement  
**Konum URI 'si**:/Testeraccount

### <a name="windows10secureassessmentconfigurationlaunchuri"></a>Windows10SecureAssessmentConfiguration. LaunchUri 
**CSP**:./Vendor/MSFT/secureastement  
**Konum URI 'si**:/Launchuri

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsblocktelemetry"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsBlockTelemetry 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/MOMAgent/Workspace ID ve/MOMAgent/WorkspaceKey

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspaceid"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsWorkspaceId 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/MOMAgent/Workspace ID

### <a name="windows10teamgeneralconfigurationazureoperationalinsightsworkspacekey"></a>Windows10TeamGeneralConfiguration.AzureOperationalInsightsWorkspaceKey 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/MOMAgent/WorkspaceKey

### <a name="windows10teamgeneralconfigurationconnectappblockautolaunch"></a>Windows10TeamGeneralConfiguration. ConnectAppBlockAutoLaunch 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/ınboxapps/Connect/AUTOLAUNCH

### <a name="windows10teamgeneralconfigurationdeviceaccountblockexchangeservices"></a>Windows10TeamGeneralConfiguration. DeviceAccountBlockExchangeServices 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Deviceaccount/email

### <a name="windows10teamgeneralconfigurationdeviceaccountemailaddress"></a>Windows10TeamGeneralConfiguration. Deviceaccountemaadresi 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Deviceaccount/email

### <a name="windows10teamgeneralconfigurationdeviceaccountexchangeserveraddress"></a>Windows10TeamGeneralConfiguration. DeviceAccountExchangeServerAddress 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Deviceaccount/ExchangeServer

### <a name="windows10teamgeneralconfigurationdeviceaccountrequirepasswordrotation"></a>Windows10TeamGeneralConfiguration. DeviceAccountRequirePasswordRotation 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Deviceaccount/passwordrotationenabled

### <a name="windows10teamgeneralconfigurationdeviceaccountsessioninitiationprotocoladdress"></a>Windows10TeamGeneralConfiguration. Deviceaccountsessionınitiationprotocoladdress 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Deviceaccount/sıpaddress

### <a name="windows10teamgeneralconfigurationmaintenancewindowblocked"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowBlocked 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/MaintenanceHoursSimple/hours/Duration ve/MaintenanceHoursSimple/hours/StartTime

### <a name="windows10teamgeneralconfigurationmaintenancewindowdurationinhours"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowDurationInHours 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/MaintenanceHoursSimple/hours/Duration

### <a name="windows10teamgeneralconfigurationmaintenancewindowstarttime"></a>Windows10TeamGeneralConfiguration.MaintenanceWindowStartTime 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/MaintenanceHoursSimple/hours/StartTime

### <a name="windows10teamgeneralconfigurationmiracastblocked"></a>Windows10TeamGeneralConfiguration.MiracastBlocked 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Inboxapps/kablolu Lessprojection/Enabled

### <a name="windows10teamgeneralconfigurationmiracastchannel"></a>Windows10TeamGeneralConfiguration.MiracastChannel 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Inboxapps/kablolu Lessprojection/Channel

### <a name="windows10teamgeneralconfigurationmiracastrequirepin"></a>Windows10TeamGeneralConfiguration.MiracastRequirePin 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Inboxapps/kablolu Lessprojection/pinrequired

### <a name="windows10teamgeneralconfigurationsettingsblockmymeetingsandfiles"></a>Windows10TeamGeneralConfiguration. Settingsblockmymeeting ınsandfiles 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Kaydırma URI 'si**:/Properties/donotshowmymeeting ingsandfiles

### <a name="windows10teamgeneralconfigurationsettingsblocksessionresume"></a>Windows10TeamGeneralConfiguration. Settingsblocksessionözgeçmişi 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Properties/allowsessionözgeçmişi

### <a name="windows10teamgeneralconfigurationsettingsblocksigninsuggestions"></a>Windows10TeamGeneralConfiguration. Settingsblocksignınönerilere 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Properties/disablesignınönerilere

### <a name="windows10teamgeneralconfigurationsettingsdefaultvolume"></a>Windows10TeamGeneralConfiguration. SettingsDefaultVolume 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Properties/defaultvolume

### <a name="windows10teamgeneralconfigurationsettingsscreentimeoutinminutes"></a>Windows10TeamGeneralConfiguration.SettingsScreenTimeoutInMinutes 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Properties/ScreenTimeout

### <a name="windows10teamgeneralconfigurationsettingssessiontimeoutinminutes"></a>Windows10TeamGeneralConfiguration. Settingssessiontimeoutınminutes 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Properties/SessionTimeout

### <a name="windows10teamgeneralconfigurationsettingssleeptimeoutinminutes"></a>Windows10TeamGeneralConfiguration. Settingssleeptimeoutınminutes 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**UZAKLıĞı URI**:/Properties/uyeptimeout

### <a name="windows10teamgeneralconfigurationwelcomescreenbackgroundimageurl"></a>Windows10TeamGeneralConfiguration. kaynak Comescreenbackgroundımageurl 'Si 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/Inboxapps/Welcome/currentbackgroundpath

### <a name="windows10teamgeneralconfigurationwelcomescreenblockautomaticwakeup"></a>Windows10TeamGeneralConfiguration. kaynak Comescreenblockautomaticuyanma 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Konum URI 'si**:/InBoxApps/Welcome/AutoWakeScreen

### <a name="windows10teamgeneralconfigurationwelcomescreenmeetinginformation"></a>Windows10TeamGeneralConfiguration. karşılama Comescreenmeeting ınınformation 
**CSP**:./Vendor/MSFT/surçok yönlü hub  
**Kaydırma URI 'si**:/Inboxapps/Welcome/Meeting ingınfooption

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingblob"></a>Windowssavunma Deradvancedthreatprotectionconfiguration. AdvancedThreatProtectionOffboardingBlob 
**CSP**:./Device/Vendor/MSFT/windowsadvancedthreatprotection  
**Konum URI 'si**:/çıkarma 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectionoffboardingfilename"></a>Windowssavunma Deradvancedthreatprotectionconfiguration. AdvancedThreatProtectionOffboardingFilename
**CSP**:./Device/Vendor/MSFT/windowsadvancedthreatprotection  
**Konum URI 'si**:/çıkarma 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingblob"></a>Windowssavunma Deradvancedthreatprotectionconfiguration. AdvancedThreatProtectionOnboardingBlob 
**CSP**:./Device/Vendor/MSFT/windowsadvancedthreatprotection  
**Konum URI 'si**:/ekleme 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationadvancedthreatprotectiononboardingfilename"></a>Windowssavunma Deradvancedthreatprotectionconfiguration. AdvancedThreatProtectionOnboardingFilename 
**CSP**:./Device/Vendor/MSFT/windowsadvancedthreatprotection  
**Konum URI 'si**:/ekleme 

### <a name="windowsdefenderadvancedthreatprotectionconfigurationallowsamplesharing"></a>Windowssavunma Deradvancedthreatprotectionconfiguration. AllowSampleSharing 
**CSP**:./Device/Vendor/MSFT/windowsadvancedthreatprotection  
**Konum URI 'si**:/Configuration/samplesharing

### <a name="windowsdefenderadvancedthreatprotectionconfigurationenableexpeditedtelemetryreporting"></a>Windowssavunma Deradvancedthreatprotectionconfiguration. EnableExpeditedTelemetryReporting 
**CSP**:./Device/Vendor/MSFT/windowsadvancedthreatprotection  
**Konum URI 'si**:/Configuration/TelemetryReportingFrequency

### <a name="windowsdeliveryoptimizationconfigurationdeliveryoptimizationmode"></a>Windowsteslimat Yoptimizationconfiguration. Tesliyoptimizationmode 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/tesliyoptimization/dodownloadmode

### <a name="windowsidentityprotectionconfigurationenhancedantispoofingforfacialfeaturesenabled"></a>Windowsıdentityprotectionconfiguration. EnhancedAntiSpoofingForFacialFeaturesEnabled 
**CSP**:./Device/Vendor/MSFT/passportforwork  
**Konum URI 'si**:/Biometrics/FacialFeaturesUseEnhancedAntiSpoofing

### <a name="windowsidentityprotectionconfigurationpinexpirationindays"></a>Windowsıdentityprotectionconfiguration. Pinexpirationındays 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/Expiration

### <a name="windowsidentityprotectionconfigurationpinlowercasecharactersusage"></a>Windowsıdentityprotectionconfiguration. Pinalcasekarakterkullanımı 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/LowercaseLetters

### <a name="windowsidentityprotectionconfigurationpinmaximumlength"></a>Windowsıdentityprotectionconfiguration. PinMaximumLength 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/MaximumPINLength

### <a name="windowsidentityprotectionconfigurationpinminimumlength"></a>Windowsıdentityprotectionconfiguration. PinMinimumLength 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/MinimumPINLength

### <a name="windowsidentityprotectionconfigurationpinpreviousblockcount"></a>Windowsıdentityprotectionconfiguration. PinPreviousBlockCount 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/History

### <a name="windowsidentityprotectionconfigurationpinrecoveryenabled"></a>Windowsıdentityprotectionconfiguration. PinRecoveryEnabled 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/EnablePinRecovery

### <a name="windowsidentityprotectionconfigurationpinspecialcharactersusage"></a>Windowsıdentityprotectionconfiguration. Pinspecialkarakterkullanımı 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/SpecialCharacters

### <a name="windowsidentityprotectionconfigurationpinuppercasecharactersusage"></a>Windowsıdentityprotectionconfiguration. Pinüstecasekarakterkullanımı
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/PINComplexity/UppercaseLetters

### <a name="windowsidentityprotectionconfigurationsecuritydevicerequired"></a>Windowsıdentityprotectionconfiguration. SecurityDeviceRequired 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/RequireSecurityDevice

### <a name="windowsidentityprotectionconfigurationunlockwithbiometricsenabled"></a>Windowsıdentityprotectionconfiguration. UnlockWithBiometricsEnabled 
**CSP**:./Device/Vendor/MSFT/passportforwork  
**Uzaklığa göre URI**:/Biometrics/usebiyometri

### <a name="windowsidentityprotectionconfigurationusecertificatesforonpremisesauthenabled"></a>Windowsıdentityprotectionconfiguration. UseCertificatesForOnPremisesAuthEnabled 
**CSP**:./Device/Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/UseCertificateForOnPremAuth

### <a name="windowsidentityprotectionconfigurationwindowshelloforbusinessblocked"></a>Windowsıdentityprotectionconfiguration. Windowshelloforbusinessbloke 
**CSP**:./Vendor/MSFT/passportforwork  
**Konum URI 'si**:/{AADTenantId}/policies/UsePassportForWork

### <a name="windowskioskconfigurationedgekioskenablepublicbrowsing"></a>WindowsKioskConfiguration. Edgekioskenablepublicgözatma 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/configurekioskmode

### <a name="windowskioskconfigurationedgekioskresetafteridletimeinminutes"></a>WindowsKioskConfiguration. Edgekioskresetafteridletimeınminutes 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Browser/configurekioskresetafteridtatimeout

### <a name="windowskioskconfigurationkioskbrowserblockedurlexceptions"></a>WindowsKioskConfiguration. KioskBrowserBlockedUrlExceptions 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kioskbrowser/blockedurlexceptions

### <a name="windowskioskconfigurationkioskbrowserblockedurls"></a>WindowsKioskConfiguration. KioskBrowserBlockedURLs 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kioskbrowser/blockedurls

### <a name="windowskioskconfigurationkioskbrowserdefaulturl"></a>WindowsKioskConfiguration. KioskBrowserDefaultUrl 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kioskbrowser/DefaultUrl

### <a name="windowskioskconfigurationkioskbrowserenableendsessionbutton"></a>WindowsKioskConfiguration. KioskBrowserEnableEndSessionButton 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kioskbrowser/enableendsessionbutton

### <a name="windowskioskconfigurationkioskbrowserenablehomebutton"></a>WindowsKioskConfiguration. KioskBrowserEnableHomeButton 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kioskbrowser/enablehomebutton

### <a name="windowskioskconfigurationkioskbrowserenablenavigationbuttons"></a>WindowsKioskConfiguration. KioskBrowserEnableNavigationButtons 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/KioskBrowser/EnableNavigationButtons

### <a name="windowskioskconfigurationkioskbrowserrestartonidletimeinminutes"></a>WindowsKioskConfiguration. Kioskbrowserrestartonıdtimeınminutes 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/kioskbrowser/kioskbrowserrestartonıdtimeınminutes

### <a name="windowsupdateforbusinessconfigurationautomaticupdatemode"></a>WindowsUpdateForBusinessConfiguration. AutomaticUpdateMode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/allowotomatik güncelleştirme

### <a name="windowsupdateforbusinessconfigurationautorestartnotificationdismissal"></a>WindowsUpdateForBusinessConfiguration. AutoRestartNotificationDismissal 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/AutoRestartRequiredNotificationDismissal

### <a name="windowsupdateforbusinessconfigurationbusinessreadyupdatesonly"></a>WindowsUpdateForBusinessConfiguration. BusinessReadyUpdatesOnly 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/branchreadinesslevel

### <a name="windowsupdateforbusinessconfigurationdeliveryoptimizationmode"></a>WindowsUpdateForBusinessConfiguration. Tesliyoptimizationmode 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/tesliyoptimization/dodownloadmode

### <a name="windowsupdateforbusinessconfigurationdriversexcluded"></a>WindowsUpdateForBusinessConfiguration. DriversExcluded 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/ExcludeWUDriversInQualityUpdate

### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration. EngagedRestartDeadlineForFeatureUpdatesInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/EngagedRestartDeadlineForFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationengagedrestartdeadlineindays"></a>WindowsUpdateForBusinessConfiguration. EngagedRestartDeadlineInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/EngagedRestartDeadline

### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration. EngagedRestartSnoozeScheduleForFeatureUpdatesInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/EngagedRestartSnoozeScheduleForFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationengagedrestartsnoozescheduleindays"></a>WindowsUpdateForBusinessConfiguration. EngagedRestartSnoozeScheduleInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/EngagedRestartSnoozeSchedule

### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleforfeatureupdatesindays"></a>WindowsUpdateForBusinessConfiguration. EngagedRestartTransitionScheduleForFeatureUpdatesInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/EngagedRestartTransitionScheduleForFeatureUpdates

### <a name="windowsupdateforbusinessconfigurationengagedrestarttransitionscheduleindays"></a>WindowsUpdateForBusinessConfiguration. EngagedRestartTransitionScheduleInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/EngagedRestartTransitionSchedule

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesdeferralperiodindays"></a>WindowsUpdateForBusinessConfiguration. FeatureUpdatesDeferralPeriodInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/DeferFeatureUpdatesPeriodInDays

### <a name="windowsupdateforbusinessconfigurationfeatureupdatespaused"></a>WindowsUpdateForBusinessConfiguration. Featureupdatespakullandınız 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/pausefeatureupdates

### <a name="windowsupdateforbusinessconfigurationfeatureupdatespausestartdatetime"></a>WindowsUpdateForBusinessConfiguration. FeatureUpdatesPauseStartDateTime 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/pausefeatureupdatesstarttime

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesrollbackstartdatetime"></a>WindowsUpdateForBusinessConfiguration. FeatureUpdatesRollbackStartDateTime
**CSP**: n/a-Graph API yalnızca **fark URI 'si**: n/a-Graph API yalnızca

### <a name="windowsupdateforbusinessconfigurationfeatureupdateswillberolledback"></a>WindowsUpdateForBusinessConfiguration. FeatureUpdatesWillBeRolledBack 
**CSP**: n/a-Graph API yalnızca **fark URI 'si**: n/a-Graph API yalnızca

### <a name="windowsupdateforbusinessconfigurationfeatureupdatesrollbackwindowindays"></a>WindowsUpdateForBusinessConfiguration. Featureupdatesrollbackwindowındays
**CSP**: n/a-Graph API yalnızca **fark URI 'si**: n/a-Graph API yalnızca

### <a name="windowsupdateforbusinessconfigurationinstallationschedule"></a>WindowsUpdateForBusinessConfiguration. Yüklemezamanlaması
**CSP**:./Device/Vendor/MSFT/Policy **kayması URI**:/config/Update/ActiveHoursStart,/config/Update/ActiveHoursEnd,/config/Update/ScheduledInstallDay,/config/Update/scheduledınstalltime

### <a name="windowsupdateforbusinessconfigurationmicrosoftupdateserviceallowed"></a>WindowsUpdateForBusinessConfiguration. MicrosoftUpdateServiceAllowed 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/allowmuupdateservice

### <a name="windowsupdateforbusinessconfigurationpreviewbuildsetting"></a>WindowsUpdateForBusinessConfiguration. Önizleme Buildsetting 
**CSP**:./Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/managemodelderlemeleri

### <a name="windowsupdateforbusinessconfigurationqualityupdatesdeferralperiodindays"></a>WindowsUpdateForBusinessConfiguration. QualityUpdatesDeferralPeriodInDays 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/DeferQualityUpdatesPeriodInDays

### <a name="windowsupdateforbusinessconfigurationqualityupdatespaused"></a>WindowsUpdateForBusinessConfiguration. QualityUpdatesPaused 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/PauseQualityUpdates

### <a name="windowsupdateforbusinessconfigurationqualityupdatespausestartdatetime"></a>WindowsUpdateForBusinessConfiguration. QualityUpdatesPauseStartDateTime 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/PauseQualityUpdatesStartTime

### <a name="windowsupdateforbusinessconfigurationqualityupdatesrollbackstartdatetime"></a>WindowsUpdateForBusinessConfiguration. QualityUpdatesRollbackStartDateTime
**CSP**: n/a-Graph API yalnızca **fark URI 'si**: n/a-Graph API yalnızca

### <a name="windowsupdateforbusinessconfigurationqualityupdateswillberolledback"></a>WindowsUpdateForBusinessConfiguration. QualityUpdatesWillBeRolledBack 
**CSP**: n/a-Graph API yalnızca **fark URI 'si**: n/a-Graph API yalnızca

### <a name="windowsupdateforbusinessconfigurationscheduleimminentrestartwarninginminutes"></a>WindowsUpdateForBusinessConfiguration. Scheduleımminentrestartwarningınminutes 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/ScheduleImminentRestartWarning

### <a name="windowsupdateforbusinessconfigurationschedulerestartwarninginhours"></a>WindowsUpdateForBusinessConfiguration. ScheduleRestartWarningInHours 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/ScheduleRestartWarning

### <a name="windowsupdateforbusinessconfigurationskipchecksbeforerestart"></a>WindowsUpdateForBusinessConfiguration. SkipChecksBeforeRestart 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/setedurestart

### <a name="windowsupdateforbusinessconfigurationupdateweeks"></a>WindowsUpdateForBusinessConfiguration. Updatehaftaları 
**CSP**:./Device/Vendor/MSFT/Policy  
**Uzaklığa göre URI**:/config/Update/ScheduledInstallEveryWeek,/config/Update/scheduledınstallfirstweek,/config/Update/scheduledınstallonthweek,/config/Update/scheduledınstallsecondweek,/config/Update/scheduledınstallüçe dweek

### <a name="windowsupdateforbusinessconfigurationuserpauseaccess"></a>WindowsUpdateForBusinessConfiguration. UserPauseAccess 
**CSP**:./Device/Vendor/MSFT/Policy  
**Konum URI 'si**:/config/Update/setdisablepauseuxaccess


## <a name="next-steps"></a>Sonraki adımlar

- [Cihaz yapılandırmasına genel bakış](../configuration/device-profiles.md)
- [Yapılandırma hizmeti sağlayıcısı başvurusu](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (başka bir docs sitesini açar)
