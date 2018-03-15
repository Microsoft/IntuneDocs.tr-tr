---
title: "Microsoft Intune kullanılan cihazlarda fabrika sıfırlaması kullanma veya şirket verilerini kaldırma"
titlesuffix: 
description: "Bir cihazdaki şirket verilerini kaldırmayı veya cihazı fabrika ayarlarına sıfırlamayı öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b56f7d7bcf576a0b2342c7c5394c08661b6a45fd
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Fabrika sıfırlaması kullanarak cihazları kaldırma veya şirket verilerini kaldırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Artık ihtiyaç duyulmayan, başka amaçla kullanılacak olan veya kaybolan cihazları Intune’dan kaldırabilirsiniz. Bu işlemi **şirket verilerini kaldırma** veya **fabrika ayarlarına sıfırlama** komutu vererek yapabilirsiniz. Kullanıcılar Intune'a kayıtlı kişisel cihazlara Intune Şirket Portalı’ndan uzaktan komut da verebilir.

> [!NOTE]
> Bir kullanıcıyı Azure Active Directory'den kaldırmadan önce, bu kullanıcı ile ilişkili tüm cihazlara **fabrika ayarlarına sıfırlama** veya **şirket verilerini kaldırma** komutu verin. Azure Active Directory'den yönetilen cihazların kullanıcılarını kaldırırsanız, Intune bu cihazlara fabrika sıfırlaması veya şirket verilerini kaldırma komutu veremez.

## <a name="factory-reset"></a>Fabrika sıfırlaması

**Fabrika sıfırlaması**, tüm şirket ve kullanıcı verileriyle ayarlarını kaldırarak cihazı fabrika varsayılan ayarlarına geri yükler. Cihaz Intune yönetiminden kaldırılır. Cihazı yeni bir kullanıcıya vermeden önce sıfırlamak için ya da cihazın kaybolması veya çalınması durumunda, fabrika sıfırlaması yararlı olur. Fabrika sıfırlamasını seçerken dikkatli olun. Cihazdaki veriler kurtarılamaz.

### <a name="to-factory-reset-a-device"></a>Bir cihazı fabrika ayarlarına sıfırlamak için

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
4. Fabrika sıfırlamasını uygulamak istediğiniz cihazın adını seçin.
5. Cihazın adını gösteren dikey pencerede **Fabrika sıfırlaması**’nı seçin.
6. Windows 10 sürüm 1709 veya üstünde, fazladan "Kayıt durumunu ve kullanıcı hesabını tut" seçeneği vardır. 
    
    |Fabrika sıfırlaması aracılığıyla tutuldu|Tutulmadı|
    | -------------|------------|
    |Cihazla ilişkilendirilen kullanıcı hesapları|Kullanıcı dosyaları|
    |Makine durumu \(etki alanına katılım, Azure Active Directory'ye katılım)| Kullanıcı tarafından yüklenen uygulamalar \(mağaza ve Win32 uygulamaları)|
    |MDM kaydı|Varsayılan olmayan cihaz ayarları|
    |OEM tarafından yüklenen uygulamalar \(mağaza ve Win32 uygulamaları)||
    |Kullanıcı profili||
    |Kullanıcı profili dışındaki kullanıcı verileri||
    |Kullanıcı otomatik oturum açma|| 
    
         
7. Fabrika sıfırlamasını onaylamak için **Evet**'i seçin.

Cihaz açık ve bağlı olduğu sürece, bir fabrika sıfırlaması komutunun tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

## <a name="remove-company-data"></a>Şirket verilerini kaldırma

**Şirket verilerini kaldırma** komutu, (uygunsa) yönetilen uygulama verilerini, ayarlarını ve Intune kullanarak atanmış e-posta profillerini kaldırır. Şirket verilerini kaldırma, kullanıcının kişisel verilerini cihazda bırakır. Cihaz Intune yönetiminden kaldırılır. Aşağıdaki tablolarda, şirket verileri kaldırıldıktan sonra, hangi verilerin kaldırıldığı ve bu işlemin cihazda kalan veriler üzerindeki etkisi açıklanmıştır.

### <a name="ios"></a>iOS

|Veri türü|iOS|
|-------------|-------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler|Uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.<br /><br />Mobil uygulama yönetimini kullanan Microsoft uygulamalarından gelen uygulama verileri kaldırılır. Uygulama kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim Aracısı|Yönetim profili kaldırılır.|
|E-posta|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|
|Outlook|iOS için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır.|
|Azure Active Directory (AD) Ayrılma|Azure AD kaydı kaldırılır.|
|Kişiler | Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler kaldırılamaz. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

### <a name="android"></a>Android

|Veri türü|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Web bağlantıları|Kaldırıldı.|Kaldırıldı.|
|Yönetilmeyen Google Play uygulamaları|Uygulamalar ve veriler yüklü kalır.|Uygulamalar ve veriler yüklü kalır.|
|Yönetilmeyen iş kolu uygulamaları|Uygulamalar ve veriler yüklü kalır.|Uygulamalar kaldırılır ve sonuç olarak uygulamada bulunan veriler kaldırılır. Uygulama dışındaki (örneğin, bir SD karttaki) hiçbir veri kaldırılmaz.|
|Yönetilen Google Play uygulamaları|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. bir SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ancak kaldırılmaz.|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. bir SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş durumda kalır ancak kaldırılmaz.|
|Yönetilen iş kolu uygulamaları|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. bir SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ancak kaldırılmaz.|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. bir SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ancak kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikaları iptal edilir, ancak kaldırılmaz.|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim Aracısı|Cihaz Yöneticisi ayrıcalığı iptal edilir.|Cihaz Yöneticisi ayrıcalığı iptal edilir.|
|E-posta|yok (e-posta profilleri Android cihazları tarafından desteklenmez)|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|
|Outlook|Yalnızca Outlook MAM ilkeleriyle korunuyorsa, Android için Microsoft Outlook uygulaması tarafından alınan e-posta kaldırılır. Aksi takdirde, kayıt kaldırıldığında Outlook temizlenmez.|Yalnızca Outlook MAM ilkeleriyle korunuyorsa, Android için Microsoft Outlook uygulaması tarafından alınan e-posta kaldırılır. Aksi takdirde, kayıt kaldırıldığında Outlook temizlenmez.|
|Azure Active Directory (AD) Ayrılma|Azure AD Kaydı kaldırıldı.|Azure AD Kaydı kaldırıldı.|
|Kişiler | Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler kaldırılamaz. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.|Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler kaldırılamaz. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

### <a name="android-for-work"></a>Android for Work

Bir Android for Work cihazından şirket verilerinin kaldırılması, cihazdaki iş profilinde bulunan tüm verileri, uygulamaları ve ayarları kaldırır. Bu, cihazın Intune ile yönetilmesini devre dışı bırakır. Fabrika sıfırlaması Android for Work’te desteklenmez.


### <a name="macos"></a>Mac OS

|Veri türü|Mac OS|
|-------------|-------|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|
|Sertifika profili ayarları|MDM üzerinden dağıtılan sertifikalar kaldırılır ve iptal edilir.|
|Yönetim Aracısı|Yönetim profili kaldırılır.|
|Outlook|Koşullu erişim etkinse, cihaz yeni e-posta almayacaktır.|
|Azure Active Directory (AD) Ayrılma|Azure AD kaydı kaldırılır.|

### <a name="windows"></a>Windows

|Veri türü|Windows 8.1 (MDM) ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler|EFS tarafından korunan dosyaların anahtarı iptal edilmez ve kullanıcı dosyaları açamaz.|Şirket uygulamalarını kaldırmaz.|İlk olarak şirket portalı üzerinden yüklenen uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.|Uygulamalar ve dışarıdan yükleme anahtarları kaldırılır.<br>Windows 10 sürüm 1703 (Creator Update) ve üzerinde Office 365 ProPlus uygulamaları kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|Kaldırıldı.|Desteklenmez.|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|Sertifikalar kaldırılır ve iptal edilir.|Desteklenmez.|Sertifikalar kaldırılır ve iptal edilir.|
|E-posta|Windows e-posta ve ekleri için Posta uygulamasını da içeren EFS özellikli e-postalar kaldırılır.|Desteklenmez.|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|Windows e-posta ve ekleri için Posta uygulamasını da içeren EFS özellikli e-postalar kaldırılır. Intune tarafından sağlanan posta hesaplarını kaldırır.|
|Azure Active Directory (AD) Ayrılma|Hayır.|Hayır.|Azure AD Kaydı kaldırıldı.|Yok. Windows 10, Azure Active Directory’ye katılmış cihazlarda şirket verilerinin kaldırılmasını desteklemez.|

### <a name="to-remove-company-data"></a>Şirket verilerini kaldırmak için

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
4. Şirket verilerini kaldırmak istediğiniz cihazın adını seçin.
5. Cihazın adını gösteren dikey pencerede **Şirket verilerini kaldır**’ı seçin ve ardından onaylamak için **Evet**’i seçin.

Cihaz açık ve bağlı olduğu sürece, verileri kaldırma komutunun tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Azure Active Directory portalından cihazları silme

İletişim sorunları veya eksik cihazlar nedeniyle, cihazları Azure Active Directory’den (AD) silmeniz gerekebilir. Sil komutu bir cihazı yönetimden kaldırmaz ancak ulaşılamaz olduğunu ve Azure ile yeniden iletişim kurmasının pek olası olmadığını bildiğiniz cihaz kayıtlarını Azure portalından kaldırmak için **Sil** komutunu kullanabilirsiniz.

1.  Yönetici kimlik bilgilerinizle [Azure portalında Azure Active Directory](http://aka.ms/accessaad)’de oturum açın. Ayrıca [Office 365 portalında](https://portal.office.com) oturum açarak ve ardından sayfanın sol tarafındaki bağlantıyı kullanarak **Yönetici merkezleri** &gt; **Azure AD**’yi seçebilirsiniz.
3.  Azure aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem için kredi kartı veya ödeme gerekmez (**Ücretsiz Azure Active Directory kaydınız** abonelik bağlantısını seçin).
4.  **Azure Active Directory**’yi ve sonra kuruluşunuzu seçin.
5.  **Kullanıcılar** sekmesini seçin.
6.  Cihazlarını silmek istediğiniz kullanıcıyı seçin.
7.  **Cihazlar**’ı seçin.
8.  Artık kullanımda olmayan veya tanımları yanlış olan cihazlar gibi uygun cihazları kaldırın.
