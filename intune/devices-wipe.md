---
title: Microsoft Intune - Azure kullanarak cihazlardaki şirket verilerini kaldırma | Microsoft Docs
description: Microsoft Intune kullanarak cihazdaki şirket verilerini kaldırın ya da bir Android, Android iş profili, iOS, macOS veya Windows cihazda fabrika sıfırlaması yapın. Ayrıca cihazı Azure Active Directory'den de silin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41d8f70dd72e845663f39e151c393f5edc0ad394
ms.sourcegitcommit: 391755a4c8a38e3a22744516fd27d75e40438899
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39028754"
---
# <a name="remove-devices-by-using-factory-reset-removing-company-data-or-manually-unenrolling-the-device"></a>Fabrika sıfırlamasını kullanarak, şirket verilerini kaldırarak veya cihazın kaydını el ile kaldırarak cihazları kaldırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Şirket verilerini kaldır** veya **Fabrika sıfırlaması** eylemlerini kullanarak artık ihtiyaç duyulmayan, başka amaçla kullanılacak olan veya kaybolan cihazları Intune’dan kaldırabilirsiniz. Kullanıcılar Intune'a kayıtlı kişiye ait cihazlara Intune Şirket Portalı’ndan uzaktan komut da verebilir.

> [!NOTE]
> Bir kullanıcıyı Azure Active Directory'den (Azure AD) kaldırmadan önce, bu kullanıcıyla ilişkili tüm cihazlar için **Fabrika sıfırlaması** veya **Şirket verilerini kaldır** eylemlerini kullanın. Yönetilen cihazların kullanıcılarını Azure AD'den kaldırırsanız, Intune artık bu cihazlar için fabrika sıfırlaması veya şirket verilerini kaldırma komutu veremez.

## <a name="factory-reset"></a>Fabrika sıfırlaması

**Fabrika sıfırlaması** eylemi, cihazı fabrika varsayılan ayarlarına geri yükler. **Kayıt durumu ve kullanıcı hesabını koru** onay kutusunu seçerseniz kullanıcı verileri saklanır. Aksi takdirde sürücü güvenli bir şekilde silinir.

|Fabrika sıfırlaması eylemi|**Kayıt durumu ve kullanıcı hesabını koru**|Intune yönetiminden kaldırıldı|Description|
|:-------------:|:------------:|:------------:|------------|
|**Fabrika Sıfırlaması**| İşaretli değil | Evet | Tüm kullanıcı hesapları, verileri, MDM ilkeleri ve ayarlarını siler. İşletim sistemini varsayılan durum ve ayarlarına sıfırlar.|
|**Fabrika Sıfırlaması**| İşaretli | Hayır | Tüm MDM ilkelerini temizler. Kullanıcı hesapları ve verilerini saklar. Kullanıcı ayarlarını varsayılana sıfırlar. İşletim sistemini varsayılan durum ve ayarlarına sıfırlar.|

**Kayıt durumu ve kullanıcı hesabını koru** seçeneği yalnızca Windows 10 sürüm 1709 veya sonraki sürümlerde kullanılabilir.

MDM ilkeleri, cihazın Intune’a bir sonraki bağlanışında yeniden uygulanır.

Cihazı yeni bir kullanıcıya vermeden önce sıfırlamak için ya da cihaz kaybolduğunda veya çalındığında, fabrika sıfırlaması yararlı olur. **Fabrika sıfırlaması**'nı seçerken dikkatli olun. Cihazdaki veriler kurtarılamaz.

### <a name="factory-reset-a-device"></a>Cihazı fabrika ayarlarına sıfırlama

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar** > **Tüm cihazlar**’ı seçin.
4. Fabrika sıfırlamasını uygulamak istediğiniz cihazın adını seçin.
5. Cihaz adının gösterildiği bölmede **Fabrika sıfırlaması**'nı seçin.
6. Windows 10 sürüm 1709 veya sonraki sürümlerde, **Kayıt durumunu ve kullanıcı hesabını tut** seçeneği de sağlanır. 
    
    |Fabrika sıfırlaması sırasında tutuldu|Tutulmadı|
    | -------------|------------|
    |Cihazla ilişkilendirilen kullanıcı hesapları|Kullanıcı dosyaları|
    |Makine durumu \(etki alanına katılmış, Azure AD'ye katılmış)| Kullanıcı tarafından yüklenen uygulamalar \(mağaza ve Win32 uygulamaları)|
    |Mobil cihaz yönetimi (MDM) kaydı|Varsayılan olmayan cihaz ayarları|
    |OEM tarafından yüklenen uygulamalar \(mağaza ve Win32 uygulamaları)||
    |Kullanıcı profili||
    |Kullanıcı profili dışındaki kullanıcı verileri||
    |Kullanıcı otomatik oturum açma|| 
    
         
7. Fabrika sıfırlamasını onaylamak için **Evet**'i seçin.

Cihaz açık ve bağlı olduğu sürece, **Fabrika sıfırlaması** eyleminin tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

## <a name="remove-company-data"></a>Şirket verilerini kaldırma

**Şirket verilerini kaldır** eylemi, (uygunsa) yönetilen uygulama verilerini, ayarlarını ve Intune kullanarak atanmış e-posta profillerini kaldırır. Cihaz Intune yönetiminden kaldırılır. Bu durum cihazın bir sonraki sefer iade edildiğinde ve **Şirket verilerini kaldır** uzak eylemini aldığında ortaya çıkar.

**Şirket verilerini kaldır**, kullanıcının kişisel verilerini cihazda bırakır.  

Aşağıdaki tablolarda, hangi verilerin kaldırıldığı ve **Şirket verilerini kaldır** eyleminin şirket verileri kaldırıldıktan sonra cihazda kalan veriler üzerindeki etkisi açıklanır.

### <a name="ios"></a>iOS

|Veri türü|iOS|
|-------------|-------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler|Uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.<br /><br />Mobil uygulama yönetimini kullanan Microsoft uygulamalarından gelen uygulama verileri kaldırılır. Uygulama kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim aracısı|Yönetim profili kaldırılır.|
|E-posta|Intune üzerinden sağlanan e-posta profilleri kaldırılır. Cihazın önbelleğindeki e-postalar silinir.|
|Outlook|iOS için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır. Bu, önce Outlook mobil uygulamasının iOS kullanıcılarına Gerekli uygulama olarak dağıtılmasını gerektirir.|
|Azure AD'den ayrılma|Azure AD kaydı kaldırılır.|
|Kişiler |Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler kaldırılamaz. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

### <a name="android"></a>Android

|Veri türü|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Web bağlantıları|Kaldırıldı.|Kaldırıldı.|
|Yönetilmeyen Google Play uygulamaları|Uygulamalar ve veriler yüklü kalır.|Uygulamalar ve veriler yüklü kalır.|
|Yönetilmeyen iş kolu uygulamaları|Uygulamalar ve veriler yüklü kalır.|Uygulamalar kaldırılır ve uygulamada yerel olarak bulunan veriler kaldırılır. Uygulama dışındaki (örneğin, SD kartındaki) hiçbir veri kaldırılmaz.|
|Yönetilen Google Play uygulamaları|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (örneğin, SD kartında) Mobil Uygulama Yönetimi (MAM) şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ama kaldırılmaz.|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (örneğin, SD kartında) MAM şifrelemesi ile korunan veriler şifrelenmiş durumda kalır ama kaldırılmaz.|
|Yönetilen iş kolu uygulamaları|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (örneğin, SD kartında) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ama kaldırılmaz.|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (örneğin, SD kartında) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ama kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikaları iptal edilir ama kaldırılmaz.|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim aracısı|Cihaz Yöneticisi ayrıcalığı iptal edilir.|Cihaz Yöneticisi ayrıcalığı iptal edilir.|
|E-posta|Yok (E-posta profilleri Android cihazları tarafından desteklenmez)|Intune üzerinden sağlanan e-posta profilleri kaldırılır. Cihazın önbelleğindeki e-postalar silinir.|
|Outlook|Yalnızca Outlook MAM ilkeleriyle korunuyorsa, Android için Outlook uygulaması tarafından alınan e-posta kaldırılır. Aksi takdirde, cihazın kaydı kaldırıldığında Outlook temizlenmez.|Yalnızca Outlook MAM ilkeleriyle korunuyorsa, Android için Outlook uygulaması tarafından alınan e-posta kaldırılır. Aksi takdirde, cihazın kaydı kaldırıldığında Outlook temizlenmez.|
|Azure AD'den ayrılma|Azure AD kaydı kaldırılır.|Azure AD kaydı kaldırılır.|
|Kişiler |Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler kaldırılamaz. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.|Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler kaldırılamaz. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

### <a name="android-work-profile"></a>Android iş profili

Bir Android iş profili cihazdan şirket verilerinin kaldırılması, cihazdaki iş profilinde bulunan tüm verileri, uygulamaları ve ayarları kaldırır. Cihaz Intune yönetiminde devre dışı bırakıldı. Fabrika sıfırlaması Android iş profillerinde desteklenmez.

### <a name="android-enterprise-kiosk-devices"></a>Android kurumsal bilgi noktası cihazları

Android bilgi noktası cihazlarda yalnızca fabrika sıfırlaması yapabilirsiniz. Android bilgi noktası cihazlardan şirket verilerini kaldıramazsınız.


### <a name="macos"></a>Mac OS

|Veri türü|Mac OS|
|-------------|-------|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|
|Sertifika profili ayarları|MDM üzerinden dağıtılan sertifikalar kaldırılır ve iptal edilir.|
|Yönetim aracısı|Yönetim profili kaldırılır.|
|Outlook|Koşullu erişim etkinse, cihaz yeni e-posta almaz.|
|Azure AD'den ayrılma|Azure AD kaydı kaldırılır.|

### <a name="windows"></a>Windows

|Veri türü|Windows 8.1 (MDM) ve Windows RT 8.1|Windows RT|Windows Phone 8.1 ve Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler|EFS tarafından korunan dosyalar için anahtarlar iptal edilir. Kullanıcı dosyaları açamaz.|Şirket uygulamaları kaldırılmaz.|Başlangıçta Şirket Portalı üzerinden yüklenen uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.|Uygulamalar kaldırılır. Dışarıdan yükleme anahtarları kaldırılır.<br>Windows 10 sürüm 1703 (Creators Update) ve üzerinde Office 365 ProPlus uygulamaları kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz. Kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|Kaldırıldı.|Desteklenmez.|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|Sertifikalar kaldırılır ve iptal edilir.|Desteklenmez.|Sertifikalar kaldırılır ve iptal edilir.|
|E-posta|EFS'nin etkinleştirildiği e-postalar kaldırılır. Bunlar, Windows için Posta uygulamasındaki e-postalar ve eklerdir.|Desteklenmez.|Intune üzerinden sağlanan e-posta profilleri kaldırılır. Cihazın önbelleğindeki e-postalar silinir.|EFS'nin etkinleştirildiği e-postalar kaldırılır. Bunlar, Windows için Posta uygulamasındaki e-postalar ve eklerdir. Intune tarafından sağlanan posta hesaplarını kaldırır.|
|Azure AD'den ayrılma|Hayır.|Hayır.|Azure AD kaydı kaldırılır.|Yok. Windows 10'da, Azure AD'ye katılmış cihazlarda şirket verilerini kaldıramazsınız.|

### <a name="remove-company-data"></a>Şirket verilerini kaldırma

1. [Azure portalında Intune'da](https://aka.ms/intuneportal) oturum açın.
2. **Cihazlar** bölmesinde **Tüm cihazlar**'ı seçin.
3. Şirket verilerini kaldırmak istediğiniz cihazın adını seçin.
4. Cihaz adının gösterildiği bölmede **Şirket verilerini kaldır**'ı seçin. Onaylamak için **Evet**'i seçin.

Cihaz açık ve bağlı olduğu sürece, **Şirket verilerini kaldır** eyleminin tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

## <a name="delete-devices-from-the-intune-portal"></a>Cihazları Intune portalından silme

Cihazları Intune portalından kaldırmak istiyorsanız, bunları belirli bir cihaz bölmesinden silebilirsiniz. Cihazın bir sonraki iade edilişinde, üzerindeki tüm şirket verileri kaldırılır.

1. [Azure portalında Intune’da](https://aka.ms/intuneportal) oturum açın.
2. **Cihazlar** > **Tüm cihazlar** > silmek istediğiniz cihazları seçin > **Sil**'i seçin.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Temizleme kuralları ile cihazları otomatik olarak silme
Intune’u etkin olmayan, eski veya yanıt vermeyen cihazları otomatik olarak silmek üzere yapılandırabilirsiniz. Bu temizleme kuralları, cihaz kayıtlarınızın güncel kalması için cihazınızı kesintisiz bir şekilde izler. Bu şekilde silinen cihazlar, Intune yönetiminden kaldırılır.
1. [Azure portalında Intune'da](https://aka.ms/intuneportal) oturum açın.
2. **Cihazlar** > **Cihaz temizleme kuralları** > **Evet**’i seçin.
3. **Şu kadar gün boyunca iade etme işlemi yapmayan cihazları sil** kutusuna 90 ila 270 arasında bir sayı girin.
4. **Kaydet**’i seçin.



## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Azure Active Directory portalından cihazları silme

İletişim sorunları veya eksik cihazlar nedeniyle, cihazları Azure AD'den silmeniz gerekebilir. Ulaşılamaz olduğunu ve Azure ile yeniden iletişim kurmasının pek olası olmadığını bildiğiniz cihazlarda, cihaz kayıtlarını Azure portalından kaldırmak için **Sil** eylemini kullanabilirsiniz. **Sil** eylemi, cihazı yönetimden kaldırmaz.

1.  Yönetici kimlik bilgilerinizi kullanarak [Azure portalında Azure Active Directory](http://aka.ms/accessaad)’de oturum açın. [Office 365 portalında](https://portal.office.com) da oturum açabilirsiniz. Menüden **Yönetim merkezleri** > **Azure AD**'yi seçin.
2.  Azure aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem için kredi kartı veya ödeme gerekmez ( **Ücretsiz Azure Active Directory kaydınız** abonelik bağlantısını seçin).
3.  **Azure Active Directory**’yi ve sonra da kuruluşunuzu seçin.
4.  **Kullanıcılar** sekmesini seçin.
5. Silmek istediğiniz cihazla ilişkilendirilmiş olan kullanıcıyı seçin.
6.  **Cihazlar**’ı seçin.
7.  Gereken cihazları kaldırın. Örneğin, artık kullanımda olmayan veya tanımları yanlış olan cihazları kaldırabilirsiniz.

## <a name="retire-an-apple-dep-device-from-intune"></a>Intune’daki Apple DEP cihazını devre dışı bırakma

Apple DEP cihazını Intune yönetiminden tamamen kaldırmak istiyorsanız bu adımları izleyin:

1. [Azure portalında Intune'da](https://aka.ms/intuneportal) oturum açın.
2. **Cihazlar** > **Tüm cihazlar**'i seçin, cihazı seçin ve sonra da **Şirket verilerini kaldır**’ı seçin.
![Şirket verilerini kaldır için ekran görüntüsü](./media/devices-wipe/remove-company-data.png)
3. **Cihaz kaydı** > **Apple Kaydı** > **Kayıt programı belirteçleri**'ni seçin, belirteci seçin, ardından **Cihazlar**'ı ve cihazın onay kutusunu belirttikten sonra **Sil** > **Evet**’i seçin.
![Cihazı sil için ekran görüntüsü](./media/devices-wipe/delete-device.png)
4. [Deploy.apple.com](http://deploy.apple.com)’u ziyaret edin ve seri numarasıyla cihazı arayın.
5. **Atanan** menüsünde **Atanmış**’ı seçin.

6. **Yeniden Ata**’yı seçin.

    ![Apple yeniden atama ekran görüntüsü](./media/devices-wipe/apple-reassign.png)

## <a name="next-steps"></a>Sonraki adımlar

Silinen cihazı yeniden kaydetmek istiyorsanız bkz. [Kayıt seçenekleri](enrollment-options.md).

