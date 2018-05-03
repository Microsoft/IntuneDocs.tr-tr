---
title: Microsoft Intune - Azure’da Windows Holographic for Business cihazlar için özel ayarlar | Microsoft Docs
description: Microsoft Intune’da Windows Holographic for Business çalıştıran cihazlar için OMA-URI ayarlarını kullanmak üzere özel bir profil oluşturun. AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates ve ApplicationLaunchRestrictions ilke yapılandırma hizmet sağlayıcısı (CSP) ayarlarını ayarlayabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1825d99243654c9fecac7729153a95234d435ff
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>Intune’da Windows Holographic for Business çalıştıran cihazlar için özel cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows Holographic for Business için Microsoft Intune **özel** profilini kullanın. Windows Holographic for Business, pek çok yapılandırma hizmet sağlayıcıları (CSP’ler) ayarını kullanılabilir hale getirir. CSP’ye genel bakış için bkz. [BT uzmanları için yapılandırma hizmet sağlayıcılarına (CSP’ler) giriş](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Windows Holographic tarafından desteklenen belirli CSP’ler için bkz. [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Belirli bir ayarı arıyorsanız, [Windows Holographic for Business cihaz kısıtlama profilinin](device-restrictions-windows-holographic.md) pek çok yerleşik ayarı içerdiğini ve özel değerler belirlemeyi gerektirmediğini aklınızda bulundurun.

## <a name="create-the-custom-oma-uri-profile"></a>Özel OMA-URI profilini oluşturma
1. Başlamak için [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
2. Bir veya birden çok OMA-URI ayarı eklemek için, **Profil Oluştur** kısmında **Ayarlar**’ı seçin.
3. **Özel OMA-URI Ayarları** kısmında, yeni değer eklemek için **Ekle**’ye tıklayın. Ayrıca, virgülle ayrılmış değerler (.csv) dosyasında yapılandırdığınız tüm değerlerin listesini oluşturmak için **Dışarı Aktar**’a da tıklayabilirsiniz.
4. Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin:
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
1. Bitirdiğinizde **Profil Oluştur** kısmına geri dönün ve **Oluştur**'a tıklayın.
Profil oluşturulur ve profil listesinde görüntülenir.

## <a name="recommended-custom-settings"></a>Önerilen özel ayarlar

Bu ayarlar, Windows Holographic for Business çalıştıran cihazlar için faydalıdır:

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Tamsayı<br>0 - izin verilmiyor<br>1 - izin veriliyor (varsayılan)|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Tamsayı<br>0 - izin verilmiyor<br>1 - izin veriliyor (varsayılan)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Tamsayı<br>0 – Güncelleştirme hizmetine izin verilmiyor <br>1 – Güncelleştirme hizmetine izin veriliyor (varsayılan).|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Dize<br>URL - Cihaz, güncelleştirmeleri belirtilen URL’deki WSUS sunucusunda denetler.<br>Yapılandırılmamış - Cihaz, güncelleştirmeleri Microsoft Update'ten denetler.|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Tamsayı<br>0 – Yapılandırılmamış. Cihaz geçerli tüm güncelleştirmeleri yükler.<br>1 – Cihaz sadece geçerli olan güncelleştirmeleri ve Onaylanmış Güncelleştirmeler listesindekileri yükler. Dağıtımdan önce sınamanın gerektiği durumlar gibi BT, cihazlardaki güncelleştirmelerin dağıtımını kontrol etmek istiyorsa bu ilkeyi 1 olarak ayarlayın.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br><br>**Önemli**<br>Son kullanıcılarınız adına güncelleştirme EULA'larını okumalı ve kabul etmelisiniz. Bunun yapılmaması, yasal veya sözleşmeye dayalı yükümlülüklerin ihlalidir.|Güncelleştirme onayları için düğüm ve son kullanıcı adına EULA kabulü.<br/><br/>Daha fazla bilgi için bkz. [CSP’yi güncelleştirme](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

---
|OMA URI|Veri türü  |
|---------|---------|
|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Önemli**<br>AppLocker CSP makalesi, atlanan XML örneklerini kullanır. Ayarları Intune özel profilleri ile yapılandırmak için düz XML kullanmanız gerekir.|Dize<br>Daha fazla bilgi için bkz. [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp).|

## <a name="find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows Holographic’in desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP’ler) tam listesini [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) bölümünde bulabilirsiniz. Tüm ayarlar, Windows Holographic sürümlerinin tümüyle uyumlu değildir. Windows makalesindeki tablo, her CSP için hangi sürümlerin desteklendiğini bildirir.

Buna ek olarak Intune, makalede listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.
