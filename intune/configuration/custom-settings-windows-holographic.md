---
title: Özel ayarları - Windows Holographic for Business cihazlar - Microsoft Intune
description: Microsoft Intune’da Microsoft Hololens dahil olmak üzere Windows Holographic for Business çalıştıran cihazlar için OMA-URI ayarlarını kullanmak üzere bir özel profil ekleyin veya oluşturun. AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates ve ApplicationLaunchRestrictions ilke yapılandırma hizmet sağlayıcısı (CSP) ayarlarını ayarlayabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.article: article
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.topic: reference
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d986097f4f3dda0278d767c911b8c1e957e9c010
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206746"
---
# <a name="use-custom-settings-for-windows-holographic-for-business-devices-in-intune"></a>Intune’da Windows Holographic for Business cihazlar için özel ayarlar kullanma

Microsoft Intune’u kullanarak, “özel profiller” kullanan Windows Holographic for Business cihazlarınız için özel ayarlar ekleyebilir veya oluşturabilirsiniz. Özel profiller, bir Intune özelliğidir. Intune’da yerleşik olarak bulunmayan cihaz ayarları ve özelliklerini eklemek için tasarlanmıştır.

Windows Holographic for Business özel profilleri, Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ayarlarını kullanarak cihazlardaki farklı özellikleri yapılandırır. Bu ayarlar normalde mobil cihaz üreticileri tarafından cihazdaki özellikleri denetlemek için kullanılır.

Windows Holographic for Business, pek çok yapılandırma hizmet sağlayıcıları (CSP’ler) ayarını kullanılabilir hale getirir. CSP’ye genel bakış için bkz. [BT uzmanları için yapılandırma hizmet sağlayıcılarına (CSP’ler) giriş](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Windows Holographic tarafından desteklenen belirli CSP’ler için bkz. [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Belirli bir ayarı arıyorsanız [Windows Holographic for Business cihaz kısıtlama profilinde](device-restrictions-windows-holographic.md) yerleşik olarak pek çok ayar bulunduğunu unutmayın. Bu sayede, özel değerler girmeniz gerekmeyebilir.

Bu makale, Windows Holographic for Business cihazlar için özel profil oluşturma işlemini gösterir. Önerilen OMA-URI ayarlarının bir listesini de içerir.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı **HoloLens özel profilidir**.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve diğer önemli ayrıntıları veren bir açıklama girin.
    - **Platform**: **Windows 10 ve üstünü**seçin.
    - **Profil türü**: **özel**' i seçin.

4. **Özel OMA-URI Ayarları**’nda **Ekle**’yi seçin. Aşağıdaki ayarları girin:

    - **Ad**: Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarına benzersiz bir ad girin.
    - **Açıklama**: Ayara genel bir bakış sağlayan ve diğer önemli ayrıntıları veren bir açıklama girin.
    - **OMA-URI ** (büyük/küçük harfe duyarlı): Ayar olarak kullanmak istediğiniz OMA-URI’yi girin.
    - **Veri türü**: Bu OMA-URI ayarı için kullanacağınız veri türünü seçin. Seçenekleriniz şunlardır:

        - Dize
        - Dize (XML dosyası)
        - Tarih ve saat
        - Tamsayı
        - Kayan nokta
        - Boole değeri
        - Base64 (dosya)

    - **Değer**: Girdiğiniz OMA-URI ile ilişkilendirmek istediğiniz veri değerini girin. Değer, seçtiğiniz veri türüne bağlıdır. Örneğin, **Tarih ve saat**' i seçerseniz, bir tarih seçicisinden değeri seçin.

    Bazı ayarları ekledikten sonra **Dışarı Aktar**’ı seçebilirsiniz. **Dışarı Aktar**, virgülle ayrılmış değerler (.csv) dosyasına eklediğiniz tüm değerlerin listesini oluşturur.

5. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. Gerekirse diğer ayarları eklemeye devam edin.
6. İşiniz bittiğinde, Intune profilini oluşturmak için **tamam** > **Oluştur** ' u seçin. Bu tamamlandığında, profiliniz **cihazlar-yapılandırma profilleri** listesinde gösterilir.

## <a name="recommended-custom-settings"></a>Önerilen özel ayarlar

Bu ayarlar, Windows Holographic for Business çalıştıran cihazlar için faydalıdır:

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Tamsayı<br/>0 - izin verilmiyor<br/>1 - izin veriliyor (varsayılan)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Tamsayı<br/>0 – Güncelleştirme hizmetine izin verilmiyor <br/>1 – Güncelleştirme hizmetine izin veriliyor (varsayılan).|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Tamsayı<br/>0 - izin verilmiyor<br/>1 - izin veriliyor (varsayılan)|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Tamsayı<br/>0 – Yapılandırılmamış. Cihaz geçerli tüm güncelleştirmeleri yükler.<br/>1 – Cihaz sadece geçerli olan güncelleştirmeleri ve Onaylanmış Güncelleştirmeler listesindekileri yükler. Dağıtımdan önce sınamanın gerektiği durumlar gibi BT, cihazlardaki güncelleştirmelerin dağıtımını kontrol etmek istiyorsa bu ilkeyi 1 olarak ayarlayın.|

### <a name="scheduledinstalltimehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|0-23 arasında tamsayı, 0=12 ÖÖ ve 23=11 ÖS ifade eder<br/>Varsayılan değer 3’tür.|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Dize<br/>URL - Cihaz, güncelleştirmeleri belirtilen URL’deki WSUS sunucusunda denetler.<br/>Yapılandırılmamış - Cihaz, güncelleştirmeleri Microsoft Update'ten denetler.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Önemli**<br/>Son kullanıcılarınız adına güncelleştirme EULA'larını okumalı ve kabul etmelisiniz. Bunun yapılmaması, yasal veya sözleşmeye dayalı yükümlülüklerin ihlalidir.|Güncelleştirme onayları için düğüm ve son kullanıcı adına EULA kabulü.<br/><br/>Daha fazla bilgi için bkz. [CSP’yi güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Önemli**<br/>AppLocker CSP makalesi, atlanan XML örneklerini kullanır. Ayarları Intune özel profilleri ile yapılandırmak için düz XML kullanmanız gerekir.|Dize<br/>Daha fazla bilgi için bkz. [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).|

### <a name="deletionpolicyhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Tamsayı<br/>0 - cihaz aktif kullanıcısı olmayan bir duruma döndüğünde hemen sil<br/>1 - depolama kapasitesi eşiğinde sil (varsayılan)<br/>2 - depolama kapasitesi eşiğinde ve profil inaktifliği eşiğinde sil|

### <a name="enableprofilemanagerhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Boole değeri<br/>True - etkinleştir<br/>False - devre dışı bırak (varsayılan)|

### <a name="profileinactivitythresholdhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Tamsayı<br/>Varsayılan değer 30’dur.|


### <a name="storagecapacitystartdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Tamsayı<br/>Varsayılan değer 25’tir.|

### <a name="storagecapacitystopdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA URI|Veri türü|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Tamsayı<br/>Varsayılan değer 50’dir.|

## <a name="find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows Holographic’in desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP’ler) tam listesini [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) bölümünde bulabilirsiniz. Tüm ayarlar, Windows Holographic sürümlerinin tümüyle uyumlu değildir. [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) bölümündeki tablo, her bir CSP için desteklenen sürümleri listeler.

Ancak Intune, [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) bölümünde listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfası, desteklediği işlemi gösterir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).

[Windows 10 cihazlarında özel bir profil](../custom-settings-windows-10.md)oluşturun.
