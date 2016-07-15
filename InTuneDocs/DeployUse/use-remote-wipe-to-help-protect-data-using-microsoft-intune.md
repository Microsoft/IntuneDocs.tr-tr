---
title: "Verilerin korunmasına yardımcı olmak için uzaktan temizlemeyi kullanma | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa4dc77c66a34d9d50b83d072ed5e03674b4d293
ms.openlocfilehash: bfb82684d8c4347297c3ed8659cc44e70ad4706c


---

# Microsoft Intune kullanarak tam veya seçmeli temizleme ile verilerinizin korunmasına yardımcı olma
Aynı cihazlarda olduğu gibi, bir noktada bilgisayarlara ve mobil cihazlara dağıttığınız [uygulamaları devre dışı bırakmak](retire-apps-using-microsoft-intune.md) istersiniz veya bunu yapmanız gerekir, çünkü bunlar artık gerekli olmaktan çıkmıştır. Ayrıca, cihazdan şirket verilerini de kaldırmak isteyebilirsiniz. Bunu yapmak için, Intune seçmeli temizleme ve tam temizleme özellikleri sağlar. Mobil cihazlar hassas şirket verileri depolayabildiği ve birçok kurumsal kaynağa erişim sağlayabildiği için, bir cihaz çalınırsa veya kaybolursa, Intune üzerinden o cihaza uzaktan cihaz temizleme komutu gönderebilirsiniz. Ayrıca kullanıcılar, Intune’a kayıtlı özel mülkiyete ait cihazlarda Intune içinden uzaktan cihaz temizleme komutu da verebilir.

  > [!NOTE]
  > Bu konu yalnızca, Intune tarafından yönetilen cihazların silinmesi ile ilgilidir. Aynı zamanda [Azure önizleme portalını](https://portal.azure.com) kullanarak da [şirket verilerini uygulamalardan silebilirsiniz](wipe-managed-company-app-data-with-microsoft-intune.md).

## Tam temizleme


**Tam temizleme**, tüm şirket ve kullanıcı verileriyle ayarlarını kaldırarak cihazı fabrika varsayılan ayarlarına geri yükler. Cihaz Intune’dan kaldırılır. Cihazı yeni bir kullanıcıya vermeden önce sıfırlamak için ya da cihazın kaybolması veya çalınması durumunda, tam temizleme yararlı olur.  **Tam temizlemeyi seçerken dikkatli olun. Cihazdaki veriler kurtarılamaz**.

## Seçmeli temizleme

**Seçmeli temizleme**, cihazdan şirket verilerini (uygun durumlarda mobil uygulama yönetimi (MAM) verileri de dahil), ayarlarını ve e-posta profillerini kaldırır. Seçmeli temizleme, kullanıcının kişisel verilerini cihazda bırakır. Cihaz Intune’dan kaldırılır. Aşağıdaki tablolarda, seçmeli silme işleminden sonra, hangi verilerin kaldırıldığı ve bu işlemin cihazda kalan veriler üzerindeki etkisi platforma göre açıklanmıştır.

**iOS**

|Veri türü|iOS|
|-------------|-------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler.|Uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.<br /><br />Mobil uygulama yönetimini kullanan Microsoft uygulamalarından gelen uygulama verileri kaldırılır. Uygulama kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırılır|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim Aracısı|Yönetim profili kaldırılır.|
|E-posta|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|
|Azure Active Directory (AAD) Ayrılma|AAD Kaydı kaldırılır|
|Kişiler | Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

**Android**

|Veri türü|Android|Android Samsung KNOX|
|-------------|-----------|------------------------|
|Web bağlantıları|Kaldırıldı.|Kaldırılır|
|Yönetilmeyen Google Play uygulamaları|Uygulamalar ve veriler yüklü kalır|Uygulamalar ve veriler yüklü kalır|
|Yönetilmeyen iş kolu uygulamaları|Uygulamalar ve veriler yüklü kalır|Uygulamalar kaldırılır ve sonuç olarak uygulamada bulunan veriler kaldırılır. Uygulama dışındaki hiçbir veri (örn. SD kart) kaldırılmaz.|
|Yönetilen Google Play uygulamaları|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ancak kaldırılmaz.|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş olarak kalır, ancak kaldırılmaz.|
|Yönetilen iş kolu uygulamaları|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş ve kullanılamaz durumda kalır ancak kaldırılmaz.|Uygulama verileri kaldırılır. Uygulama kaldırılmaz. Uygulama dışında (ör. SD kart) MAM şifrelemesi ile korunan veriler şifrelenmiş olarak kalır, ancak kaldırılmaz.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırılır|Kaldırılır|
|Sertifika profili ayarları|Sertifikaları iptal edilir, ancak kaldırılmaz.|Sertifikalar kaldırılır ve iptal edilir.|
|Yönetim Aracısı|Cihaz Yöneticisi ayrıcalığı iptal edilir.|Cihaz Yöneticisi ayrıcalığı iptal edilir.|
|E-posta|Android için Microsoft Outlook uygulaması tarafından alınan e-postalar kaldırılır.|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|
|Azure Active Directory (AAD) Ayrılma|AAD Kaydı kaldırılır|AAD Kaydı kaldırılır|
|Kişiler | Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.|Uygulamadan yerel adres defterine doğrudan eşitlenen kişiler kaldırılır.  Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. <br /> <br />Şu anda yalnızca Outlook uygulaması desteklenir.

**Windows**

|Veri türü|Windows 8.1 (MDM) ve Windows RT 8.1|Windows RT|Windows Phone 8 ve Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Intune tarafından yüklenen şirket uygulamaları ve ilişkili veriler.|EFS tarafından korunan dosyaların anahtarı iptal edilmez ve kullanıcı dosyaları açamaz.|Şirket uygulamalarını kaldırmaz.|İlk olarak şirket portalı üzerinden yüklenen uygulamalar kaldırılır. Şirket uygulama verileri kaldırılır.|Uygulamalar ve dışarıdan yükleme anahtarları kaldırılır.|
|Ayarlar|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|Intune ilkesi tarafından ayarlanan yapılandırmalar artık zorunlu tutulmaz ve kullanıcılar ayarları değiştirebilir.|
|Wi-Fi ve VPN profili ayarları|Kaldırılır|Kaldırılır|Desteklenmez|Kaldırılır|
|Sertifika profili ayarları|Sertifikalar kaldırılır ve iptal edilir.|Sertifikalar kaldırılır ve iptal edilir.|Desteklenmez|Sertifikalar kaldırılır ve iptal edilir.|
|E-posta|Windows e-posta ve ekleri için Posta uygulamasını da içeren EFS özellikli e-postalar kaldırılır.|Desteklenmez|Intune üzerinden sağlanan e-posta profilleri kaldırılır ve cihazın önbelleğindeki e-postalar silinir.|Windows e-posta ve ekleri için Posta uygulamasını da içeren EFS özellikli e-postalar kaldırılır. Intune tarafından sağlanan posta hesaplarını kaldırır.|
|Azure Active Directory (AAD) Ayrılma|Hayır|Hayır|AAD Kaydı kaldırılır|Yok. Windows 10, Azure Active Directory’ye katılmış cihazlarda seçmeli temizlemeyi desteklemez.|

### Cihazı Intune yönetici konsolundan uzaktan silme

1.  Silinecek cihazları seçin. Bu cihazları kullanıcı veya cihaza göre bulabilirsiniz.

    -   **Kullanıcıya göre:**

        1.  [Intune yönetici konsolunda](https://manage.microsoft.com/) **Gruplar**&gt;**Tüm Kullanıcılar**’ı seçin.

        2.  Mobil cihazını silmek istediğiniz kullanıcının adını seçin. **Özellikleri Görüntüle**’yi seçin.

        3.  Kullanıcının **Özellikler** sayfasında **Cihazlar**’ı seçin ve ardından silmek istediğiniz mobil cihazın adını seçin. Çoklu cihaz seçimi için Ctrl tuşunu basılı tutarak tıklamayı kullanın.

    -   **Cihaza göre:**

        1.  [Intune yönetici konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Mobil Cihazlar**’ı seçin.

      ![Devre dışı bırakma veya silme işlemi başlatma](../media/dev-sa-wipe.png)

        2.  **Cihazlar**’ı ve ardından silmek istediğiniz mobil cihazın adını seçin. Çoklu cihaz seçimi için Ctrl tuşunu basılı tutarak tıklamayı kullanın.

2.  **Devre Dışı Bırak/Sil**’i seçin.

3.  Cihazı devre dışı bırakmak istediğinizi onaylamanızı isteyen bir ileti görünür.

    -   Yalnızca şirket uygulamalarını ve verilerini kaldıran bir **Seçmeli temizleme** gerçekleştirmek için **Evet**'i seçin.

    -   Tüm uygulamaları ve verileri silip cihazı fabrika varsayılan ayarlarına döndüren **Tam temizleme** işlemini gerçekleştirmek için **Devre dışı bırakmadan önce cihazı sil**’i seçin. Bu eylem, Windows 8.1 dışında tüm platformlar için geçerlidir. **Tam silme işlemi ile kaldırılan verileri kurtaramazsınız**.

Bir silme işleminin tüm cihaz türlerine yayılması 15 dakikadan kısa sürer.

## Şifreleme dosya sistemi (EFS) özellikli içeriği silme
EFS ile şifrelenmiş içeriklerin seçilerek silinmesi Windows 8.1 ve Windows RT 8.1 tarafından desteklenir. Aşağıdakiler, EFS özellikli içeriklere yönelik seçmeli silme işlemi için geçerlidir:

-   Yalnızca Intune hesabıyla aynı İnternet etki alanını kullanan EFS korumalı uygulamalar ve veriler seçmeli olarak temizlenir. Daha fazla bilgi için bkz. [Cihaz Veri Yönetimi için Windows Seçmeli Silme](http://technet.microsoft.com/library/dn486874.aspx).

-   EFS ile ilişkili etki alanında yapılan herhangi bir değişiklik varsa, yeni etki alanını kullanan uygulama ve verilerin seçilerek silinmesinden önce değişikliklerin uygulanması 48 saati bulabilir.

-   Intune’a kayıtlı olan her etki alanı temizlenir.

Şu anda EFS seçmeli silme tarafından desteklenen veriler ve uygulamalar şunlardır:

-   Windows için Posta uygulaması

-   İş Klasörleri

-   EFS tarafından şifrelenmiş dosya ve klasörler. Daha fazla bilgi için bkz. [Şifreleme Dosya Sistemi için en iyi uygulamalar](http://support.microsoft.com/kb/223316).

-   Kuruluşunuz Active Directory'de kimliğini koruyorsa, EFS seçmeli silmenin düzgün çalışması için AAD ile verileri eşitlemek için Dizin Eşitleme (DirSync) aracını kullanmalıdır.  DirSync hakkında daha fazla bilgi için Azure Active Directory belgelerindeki [Dizin Eşitleme Senaryosu](http://technet.microsoft.com/library/dn441212.aspx)'na bakın.

## Devre dışı bırakma ve silme eylemlerini izleme
Devre dışı bırakılan veya silinen cihazlara ve eylemi gerçekleştiren kişiye ilişkin bir rapor almak için:

1.  [Intune yönetici konsolunda](https://manage.microsoft.com/) **Raporlar** &gt; **Cihaz Geçmişi Raporları**’nı seçin.

2.  Rapor için bir başlangıç ve bitiş tarihi sağlayın, sonra **Raporu Görüntüle**'yi seçin.


### Ayrıca bkz.
[Cihazları devre dışı bırakma](retire-devices-from-microsoft-intune-management.md)

[Cihaz Veri Yönetimi için Windows Seçmeli Silme](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jun16_HO4-->


