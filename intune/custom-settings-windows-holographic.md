---
title: "Windows Holographic for Business cihazlar için Intune özel ayarları"
titlesuffix: Azure portal
description: "Bir Windows Holographic for Business özel profilinde kullanabileceğiniz ayarlar hakkında bilgi edinin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 2/26/2018
ms.article: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d204f9de5c02835fe059783807558496b0cff039
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows Holographic for Business cihazlar için özel cihaz ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows Holographic for Business için Microsoft Intune **özel** profilini kullanın. Windows Holographic for Business, pek çok yapılandırma hizmet sağlayıcıları (CSP’ler) ayarını kullanılabilir hale getirir. CSP’ye genel bakış için bkz. [BT uzmanları için yapılandırma hizmet sağlayıcılarına (CSP’ler) giriş](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Windows Holographic tarafından desteklenen belirli CSP’ler için bkz. [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Belirli bir ayarı arıyorsanız, [Windows Holographic for Business cihaz kısıtlama profilinin](device-restrictions-windows-holographic.md) pek çok yerleşik ayarı içerdiğini ve özel değerler belirlemeyi gerektirmediğini aklınızda bulundurun.

1. Başlamak için, [Microsoft Intune’da özel cihaz ayarlarını yapılandırma](custom-settings-configure.md) başlığı altında verilen yönergeleri kullanın.
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


|Ayar adı|OMA URI|Veri türü  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Tamsayı<br>0 - izin verilmiyor<br>1 - izin veriliyor (varsayılan)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Tamsayı<br>0 - izin verilmiyor<br>1 - izin veriliyor (varsayılan)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Tamsayı<br>0 – Güncelleştirme hizmetine izin verilmiyor <br>1 – Güncelleştirme hizmetine izin veriliyor (varsayılan).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Dize<br>URL - Cihaz, güncelleştirmeleri belirtilen URL’deki WSUS sunucusunda denetler.<br>Yapılandırılmamış - Cihaz, güncelleştirmeleri Microsoft Update'ten denetler.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Tamsayı<br>0 – Yapılandırılmamış. Cihaz geçerli tüm güncelleştirmeleri yükler.<br>1 – Cihaz sadece geçerli olan güncelleştirmeleri ve Onaylanmış Güncelleştirmeler listesindekileri yükler. Dağıtımdan önce sınamanın gerektiği durumlar gibi BT, cihazlardaki güncelleştirmelerin dağıtımını kontrol etmek istiyorsa bu ilkeyi 1 olarak ayarlayın.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Önemli**<br>Son kullanıcılarınız adına güncelleştirme EULA'larını okumalı ve kabul etmelisiniz. Bunun yapılmaması, yasal veya sözleşmeye dayalı yükümlülüklerin ihlalidir.|Güncelleştirme onayları için düğüm ve son kullanıcı adına EULA kabulü.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Önemli**<br>AppLocker CSP makalesi, atlanan XML örneklerini kullanır. Ayarları Intune özel profilleri ile yapılandırmak için düz XML kullanmanız gerekir.|Dize<br>Daha fazla bilgi için bkz. [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) makalesi. 

## <a name="how-to-find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows Holographic’in desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP’ler) tam listesini [Windows Holographic’te desteklenen CSP’ler](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) bölümünde bulabilirsiniz. Tüm ayarlar, Windows Holographic sürümlerinin tümüyle uyumlu değildir. Windows makalesindeki tablo, her CSP için hangi sürümlerin desteklendiğini bildirir.

Buna ek olarak Intune, makalede listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için ilgili ayarın makalesini açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.
