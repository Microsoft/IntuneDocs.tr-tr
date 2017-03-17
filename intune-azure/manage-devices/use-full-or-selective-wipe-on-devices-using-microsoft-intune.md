---
title: "Intune kullanarak cihazlarda tam veya seçmeli silme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Cihazda şirket verilerini seçmeli temizleme işlemi yapmayı veya cihazda tam temizleme işlemi yapıp fabrika ayarlarına sıfırlamayı öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 6b723069108ff2cbe85951f7d65ef803323eceb9
ms.lasthandoff: 03/13/2017


---

# <a name="use-full-or-selective-wipe"></a>Tam veya seçmeli temizleme kullanma

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Artık ihtiyaç duyulmayan, başka amaçla kullanılacak olan veya kaybolan ve Intune tarafından yönetilen cihazlardaki uygulamaları ve verileri temizleyebilirsiniz. Bunu yapmak için, Intune seçmeli temizleme ve tam temizleme özellikleri sağlar. Kullanıcılar ayrıca Intune'a kayıtlı şahsi cihazlara Intune Şirket Portalı uygulamasından uzaktan cihaz temizleme komutu da verebilir.

  > [!NOTE]
  > Bu konu yalnızca, Intune mobil cihaz yönetimi tarafından yönetilen cihazların temizlenmesi ile ilgilidir. Aynı zamanda [Azure portalını](https://portal.azure.com) kullanarak da [şirket verilerini uygulamalardan silebilirsiniz](https://docs.microsoft.com/intune/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). [Intune istemci yazılımıyla yönetilen bilgisayarları devre dışı bırakma](https://docs.microsoft.com/intune/deploy-use/retire-a-windows-pc-with-microsoft-intune) seçeneğine de sahipsiniz.

## <a name="full-wipe"></a>Tam temizleme

**Tam temizleme**, tüm şirket ve kullanıcı verileriyle ayarlarını kaldırarak cihazı fabrika varsayılan ayarlarına geri yükler. Cihaz Intune’dan kaldırılır. Cihazı yeni bir kullanıcıya vermeden önce sıfırlamak için ya da cihazın kaybolması veya çalınması durumunda, tam temizleme yararlı olur.  **Tam temizlemeyi seçerken dikkatli olun. Cihazdaki veriler kurtarılamaz**.


> [!Warning]
> 4 GB’tan az RAM’i olan Windows 10 RTM cihazları (Windows 10 sürüm 1511’den önceki cihazlar), temizlendiğinde erişilemez duruma gelebilir. Yanıt vermemeye başlayan Windows 10 cihazına erişmek için cihazı bir USB sürücüsünden yeniden başlatabilirsiniz.


**Cihazda tam temizleme (fabrika sıfırlaması) yapmak için**:

1.  **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.

2.  Temizlemek istediğiniz cihazın adını seçin.

3.  Cihazın adını gösteren dikey pencerede **Fabrika sıfırlaması**’nı seçin ve ardından temizleme işlemini onaylamak için **Evet**’i seçin.

Cihaz açık ve bağlı olduğu sürece, bir temizleme komutunun tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Azure Active Directory portalında cihazları silmek için

1.  [Http://aka.ms/accessaad](http://aka.ms/accessaad) bağlantısına göz atın veya [https://portal.office.com](https://portal.office.com) adresinde **Yönetici** &gt; **Azure AD**’yi seçin.

2.  Sayfanın sol tarafındaki bağlantıyı kullanarak Kuruluş Kimliğinizle oturum açın.

3.  Azure Aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem için kredi kartı veya ödeme gerekmez (**Ücretsiz Azure Active Directory kaydınız** abonelik bağlantısını seçin).

4.  **Active Directory** ’yi ve sonra da kuruluşunuzu seçin.

5.  **Kullanıcılar** sekmesini seçin.

6.  Cihazlarını silmek istediğiniz kullanıcıyı seçin.

7.  **Cihazlar**’ı seçin.

8.  Artık kullanımda olmayan veya tanımları yanlış olan cihazlar gibi uygun cihazları kaldırın.


## <a name="selective-wipe"></a>Seçmeli temizleme

**Seçmeli silme**, cihazdan şirket verilerini mobil uygulama yönetimi (MAM) verileri de dahil (uygun durumlarda), ayarlarını ve e-posta profillerini kaldırır. Seçmeli temizleme, kullanıcının kişisel verilerini cihazda bırakır. Cihaz Intune’dan kaldırılır. Aşağıdaki tablolarda, seçmeli silme işleminden sonra, hangi verilerin kaldırıldığı ve bu işlemin cihazda kalan veriler üzerindeki etkisi açıklanmıştır. (Tablolar platforma göre düzenlenmiştir.)

**iOS**

|Veri türü|iOS|
|-------------|-------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler|Uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.<br /><br />Mobil uygulama yönetimini kullanan Microsoft uygulamalarından gelen uygulama verileri kaldırılır. Uygulama kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim Aracısı|Yönetim profili kaldırılır.|
|E-posta|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir. Microsoft Exchange şirket içinde barındırılıyorsa e-posta profilleri ve önbelleğe alınan e-postalar kaldırılmaz.|
|Outlook|iOS için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır.</br>Özel durum: Exchange şirket içinde barındırılıyorsa e-postalar kaldırılmaz.|
|Azure Active Directory (AAD) Ayrılma|AAD Kaydı kaldırılır.|
|Kişiler | Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

**Android**

|Veri türü|Android|Android Samsung KNOX Standard|
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
|E-posta|Android için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır.|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|
|Outlook|iOS için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır.</br>Özel durum: Exchange şirket içinde barındırılıyorsa e-postalar kaldırılmaz.|iOS için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır.</br>Özel durum: Exchange şirket içinde barındırılıyorsa e-postalar kaldırılmaz.|
|Azure Active Directory (AAD) Ayrılma|AAD Kaydı kaldırılır.|AAD Kaydı kaldırılır.|
|Kişiler | Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.|Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

**Android for Work**

Bir İş için Android cihazında seçmeli temizleme gerçekleştirilmesi, cihazdaki iş profilinde bulunan tüm verileri, uygulamaları ve ayarları kaldırır. Bu, cihazın Intune ile yönetilmesini devre dışı bırakır. İş için Android’de tam temizleme desteklenmez.

**Windows**

|Veri türü|Windows 8.1 (MDM) ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler|EFS tarafından korunan dosyaların anahtarı iptal edilmez ve kullanıcı dosyaları açamaz.|Şirket uygulamalarını kaldırmaz.|İlk olarak şirket portalı üzerinden yüklenen uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.|Uygulamalar ve dışarıdan yükleme anahtarları kaldırılır.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırıldı.|Kaldırıldı.|Desteklenmez.|Kaldırıldı.|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|Sertifikalar kaldırılır ve iptal edilir.|Desteklenmez.|Sertifikalar kaldırılır ve iptal edilir.|
|E-posta|Windows e-posta ve ekleri için Posta uygulamasını da içeren EFS özellikli e-postalar kaldırılır.|Desteklenmez.|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|Windows e-posta ve ekleri için Posta uygulamasını da içeren EFS özellikli e-postalar kaldırılır. Intune tarafından sağlanan posta hesaplarını kaldırır.</br>**Özel durum**: Microsoft Exchange şirket içinde barındırılıyorsa e-posta hesapları kaldırılmaz.|
|Azure Active Directory (AAD) Ayrılma|Hayır.|Hayır.|AAD Kaydı kaldırılır.|Yok. Windows 10, Azure Active Directory’ye katılmış cihazlarda seçmeli temizlemeyi desteklemez.|

**Seçmeli temizleme yapmak için**:

1.  **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.

2.  Temizlemek istediğiniz cihazın adını seçin.

3.  Cihazın adını gösteren dikey pencerede **Şirket veri...** (Şirket verilerini kaldır) öğesini seçin ve ardından temizleme işlemini onaylamak için **Evet**’i seçin.

Cihaz açık ve bağlı olduğu sürece, bir temizleme komutunun tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

