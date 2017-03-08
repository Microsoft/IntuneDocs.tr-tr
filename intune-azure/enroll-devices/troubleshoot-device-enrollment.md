---
title: "Cihaz kaydıyla ilgili sorunları giderme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Cihaz kaydı sorunlarını gidermeyi öğrenin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 9fff350240e4313994056bc5aebf82e204ab3c62
ms.lasthandoff: 02/18/2017


---

# <a name="troubleshoot-device-enrollment-in-intune"></a>Intune’da cihaz kaydıyla ilgili sorunları giderme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bu konuda, cihaz kayıt sorunlarının giderilmesi için tavsiyeler verilmektedir. Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).


## <a name="initial-troubleshooting-steps"></a>İlk sorun giderme adımları

Sorun gidermeye başlamadan önce, kaydı etkinleştirmek için Intune’u doğru yapılandırdığınızdan emin olun. Her platformun kayıt adımlarına ulaştıran bağlantılar için bkz. [Android ve Standard Knox cihazlarını kaydetme](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices.md).

Yönetilen cihaz kullanıcılarınız, gözden geçirmeniz için kayıt ve tanılama günlüklerini toplayabilir. Kullanıcılar için günlükleri toplama yönergeleri, şu konu başlıkları altında sağlanır:

- [Android kayıt hatalarını BT yöneticinize gönderme](https://docs.microsoft.com/intune/enduser/send-enrollment-errors-to-your-it-admin-android)
- [iOS hatalarını BT yöneticinize gönderme](https://docs.microsoft.com/intune/enduser/send-errors-to-your-it-admin-ios)

## <a name="general-enrollment-issues"></a>Genel kayıt sorunları
Bu sorunlar, tüm cihaz platformlarında oluşabilir.

### <a name="device-cap-reached"></a>Cihaz sınırına ulaşıldı
**Sorun:** Bir kullanıcı, kayıt sırasında cihazında bir hata aldı (iOS cihazında **Şirket Portalı Geçici Olarak Devre Dışı** hatası gibi) ve Configuration Manager’daki DMPdownloader.log dosyası **DeviceCapReached** hatasını içeriyor.

**Çözüm:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Kaydedilen ve izin verilen cihazların sayısını denetleme

Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin. Azure Portal’ın Intune dikey penceresinde **Cihazları kaydet** > **Kayıt Kısıtlamaları**’na gidin ve kullanıcıya atanmış cihazların sayısının, izin verilen üst sınır olan 15 cihazı aşmadığını doğrulayın.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Yöneticiler, Azure Active Directory portalında cihazları silebilir.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Azure Active Directory portalında cihazları silmek için

1.  [Http://aka.ms/accessaad](http://aka.ms/accessaad) bağlantısına göz atın veya [https://portal.office.com](https://portal.office.com) adresinde **Yönetici** &gt; **Azure AD**’yi seçin.

2.  Sayfanın sol tarafındaki bağlantıyı kullanarak Kuruluş Kimliğinizle oturum açın.

3.  Azure Aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem için kredi kartı veya ödeme gerekmez (**Ücretsiz Azure Active Directory kaydınız** abonelik bağlantısını seçin).

4.  **Active Directory** ’yi ve sonra da kuruluşunuzu seçin.

5.  **Kullanıcılar** sekmesini seçin.

6.  Cihazlarını silmek istediğiniz kullanıcıyı seçin.

7.  **Cihazlar**’ı seçin.

8.  Artık kullanımda olmayan veya tanımları yanlış olan cihazlar gibi uygun cihazları kaldırın.

> [!NOTE]

> [Cihaz kayıt yöneticisini kullanarak cihazları kaydetme](/intune-azure/enroll-devices/enroll-devices-using-device-enrollment-manager.md) bölümünde açıklandığı gibi Cihaz Kayıt Yöneticilerini kullanarak cihaz kaydı üst sınırından kaçınabilirsiniz.
>
> Bir kullanıcı oturumu için Koşullu Erişim ilkesi zorunlu tutulduysa, söz konusu kullanıcı hesabı Cihaz Kayıt Yöneticileri grubuna eklendiğinde kaydı tamamlayamaz.

### <a name="company-portal-temporarily-unavailable"></a>Şirket Portalı Geçici Olarak Devre Dışı
**Sorun:** Bir kullanıcı, cihazda **Şirket Portalı Geçici Olarak Devre Dışı** hatası alıyor.

**Çözüm:**

1.  Intune Şirket Portalı uygulamasını cihazınızdan kaldırın.

2.  Cihazda tarayıcıyı, [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)adresine göz atın ve kullanıcı oturum açma işlemi yapmayı deneyin.

3.  Kullanıcı oturum açamazsa, başka bir ağ denemelerini sağlayın.

4.  Bu da başarısız olursa, kullanıcının kimlik bilgilerinin Azure Active Directory ile doğru eşitlendiğinden emin olun.

5.  Kullanıcı başarıyla oturum açarsa, iOS cihazı Intune Şirket Portalı uygulamasını yüklemenizi ve kaydetmenizi ister. Android cihazında Intel Şirket Portalı uygulamasını el ile yüklemeniz gerekir ve bunu yaptıktan sonra kaydetmeyi deneyebilirsiniz.

### <a name="mdm-authority-not-defined"></a>MDM yetkilisi tanımlı değil
**Sorun:** Bir kullanıcı, **MDM yetkilisi tanımlı değil** hatası alıyor.

**Çözüm:**

1.  MDM Yetkilisinin, kullandığınız Intune hizmeti türü (Intune, Ofiice 365 veya Intune ile System Center Configuration Manager) için uygun şekilde ayarlandığını doğrulayın. Yönergeler için bkz. [Mobil cihaz yönetim yetkilisini ayarlama](https://docs.microsoft.com/en-us/intune-azure/enroll-devices/set-mdm-authority).

    > [!NOTE]
    > MDM yetkilisini, ayarlandıktan sonra yalnızca [Microsoft Intune için destek alma](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) bölümünde açıklandığı şekilde Destek birimine başvurularak değiştirilebilir.

2.  Kullanıcının kimlik bilgilerinin Azure Active Directory’yle doğru eşitlendiğinden emin olun. Bunun için UPN değerlerinin Hesap Portalı’ndaki Active Directory bilgileriyle eşleşip eşleşmediğini denetleyin.
    UPN Active Directory bilgileriyle eşleşmiyorsa:

    1.  Yerel sunucuda DirSync’i kapatın.

    2.  Eşleşmeyen kullanıcıyı **Intune Hesap Portalı** kullanıcı listesinden silin.

    3.  Azure hizmetinin yanlış verileri kaldırması için bir saat kadar bekleyin.

    4.  DirSync’i yeniden açın ve şimdi kullanıcının doğru eşitlenip eşitlenmediğini denetleyin.

3.  Intune ile System Center Configuration Manager’ı kullandığınız senaryolarda, kullanıcının geçerli bir Bulut Kullanıcı Kimliği olduğunu doğrulayın:

    1.  SQL Management Studio'yu açın.

    2.  Uygun veritabanına bağlanın.

    3.  Veritabanları klasörünü açın ve **CM_DBName** klasörünü bulup açın; burada DBName, müşteri veritabanının adıdır.

    4.  En üstte **Yeni Sorgu**’yu seçin ve aşağıdaki sorguları yürütün:

        -   Tüm kullanıcıları görmek için: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Belirli Kullanıcıları görmek için bu sorguyu kullanın; burada %testuser1%, aramak istediğiniz kullanıcının username@domain.com değerini temsil eder: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Sorguyu yazdıktan sonra **!Execute** öğesini seçin.
        Sonuçlar döndürüldüğünde, bulut kullanıcı kimliğine bakın.  Hiç kimlik bulunmazsa, kullanıcının Intune’u kullanma lisansı yok demektir.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Şirket adı özel karakterler içeriyorsa ilke oluşturulamaz veya cihazlar kaydedilemez
**Sorun:** İlke oluşturamıyor veya cihazları kaydedemiyorsunuz.

**Çözüm:** [Office 365 yönetim merkezinde](https://portal.office.com/), şirket adından özel karakterleri kaldırın ve şirket bilgilerini kaydedin.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>Birden çok doğrulanmış etki alanınız olduğunda oturum açılamaz veya cihazlar kaydedilemez
**Sorun:** AD FS’nize ikinci bir doğrulanmış etki alanı eklediğinizde, ikinci etki alanının kullanıcı asıl adı (UPN) sonekini taşıyan kullanıcılar portallarda oturum açamayabilir veya cihaz kaydedemeyebilir.


**Çözüm:** AD FS 2.0 aracılığıyla çoklu oturum açma (SSO) kullanan ve kuruluşlarında kullanıcıların UPN sonekleri için birden çok en üst düzey etki alanı bulunan (örneğin, her sonek için ayrı bir AD FS 2.0 Federasyon Hizmeti örneği dağıtmak üzere @contoso.com veya @fabrikam.com) gerekir) Microsoft Office 365 müşterileri.  Şimdi, ek AD FS 2.0 sunucularına gerek kalmadan AD FS sunucusunun bu senaryoyu destekleyebilmesi için, **SupportMultipleDomain** anahtarıyla birlikte çalışan bir [AD FS 2.0 dağıtımı](http://support.microsoft.com/kb/2607496) vardır. Daha fazla bilgi için [bu blog’a](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) bakın.


## <a name="android-issues"></a>Android sorunları
### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Cihazlar Intune hizmetini denetlemiyor ve Intune yönetici konsolunda "Uygun olmayan durumda" olarak görüntüleniyor
**Sorun:** Android sürüm 4.4.x ve 5.x çalıştıran bazı Samsung cihazlar, Intune hizmetini denetlemeyi durdurabiliyor. Hizmeti denetlemeyen cihazlar:

- Intune hizmetinden ilke, uygulama ve uzak komutları alamaz.
- Yönetici konsolunda Yönetim Durumu olarak **Uygun olmayan durumda** görüntülenir.
- Koşullu erişim ilkeleri tarafından korunan kullanıcılar şirket kaynaklarına erişimi kaybedebilir.

Samsung, belirli Samsung cihazlara yüklü gelen Samsung Smart Manager yazılımının, Şirket Portalı uygulamasını ve bileşenlerini devre dışı bırakabildiğini onayladı. Şirket Portalı devre dışı bırakıldığında arka planda çalışamaz ve bu nedenle Intune hizmetine bağlanamaz.

**1. Çözüm:**

Kullanıcılarınız Şirket Portalı uygulamasını el ile başlatmalarını söyleyin. Uygulama yeniden başlatıldığında Intune hizmeti ile bağlantıya geçer.

> [!IMPORTANT]
> Samsung Smart Manager, Şirket Portalı uygulamasını yeniden devre dışı bırakabileceği için Şirket Portalı uygulamasını el ile açmak geçici bir çözümdür.

**2. Çözüm:**

Kullanıcılarınıza cihazlarını Android 6.0 sürümüne yükseltmeyi denemelerini söyleyin. Devre dışı bırakma sorunu Android 6.0 cihazlarda yoktur. Güncelleştirmeleri denetlemek için kullanıcılar **Ayarlar** > **Cihaz hakkında** > **Güncellemeleri manuel indir** yolunu izleyip cihaz ekranındaki komutları izleyebilir.

**3. Çözüm:**

2. Çözüm işe yaramazsa, kullanıcılarınızın aşağıdaki adımları uygulayarak Şirket Portalı uygulamasını Smart Manager'da hariç tutmasını sağlayın:

1. Cihazda Smart Manager uygulamasını başlatın.

  ![Cihazda Smart Manager simgesini seçin](./media/smart-manager-app-icon.png)

2. **Pil** kutucuğunu seçin.

  ![Pil kutucuğunu seçin](./media/smart-manager-battery-tile.png)

3. **Uygulama güç tasarrufu** veya **Uygulama optimizasyonu** bölümünde **Ayrıntı**'yı seçin.

  ![Uygulama güç tasarrufu veya Uygulama optimizasyonu bölümünde Ayrıntı'yı seçin](./media/smart-manager-app-power-saving-detail.png)

4. Uygulama listesinden **Şirket Portalı**'nı seçin.

  ![Uygulama listesinden Şirket Portalı'nı seçin](./media/smart-manager-company-portal.png)

5. **Kapalı**'yı seçin.

  ![Uygulama optimizasyon iletişim kutusundan Kapalı'yı seçin](./media/smart-manager-app-optimization-turned-off.png)

6. **Uygulama güç tasarrufu** veya **Uygulama optimizasyonu** altında Şirket Portalı'nın kapalı olduğunu onaylayın.

  ![Şirket Portalı'nın kapalı olduğunu doğrulayın](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>Profil yüklemesi başarısız oldu
**Sorun:** Bir kullanıcı, bir Android cihazında **Profil yüklemesi başarısız oldu** hatasını alıyor.

**Çözüm:**

1.  Kullanıcıya, Intune hizmetinin kullandığınız sürümü için uygun lisansın atandığını onaylayın.

2.  Cihazın zaten başka bir MDM sağlayıcısıyla kaydedilmediğini ve cihaza önceden bir yönetim profili yüklenmediğini doğrulayın.

3.  Android için Chrome’un varsayılan tarayıcı olduğunu ve tanımlama bilgilerinin etkinleştirildiğini doğrulayın.

### <a name="android-certificate-issues"></a>Android sertifika sorunları

**Sorun**: Kullanıcılar cihazda şu iletiyi alıyor: *Cihazınızda gerekli bir sertifika eksik olduğundan oturum açamazsınız.*

**1. Çözüm**:

Kullanıcılarınızdan [Cihazınızda gerekli bir sertifika eksik](https://docs.microsoft.com/intune/enduser/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) bölümündeki yönergeleri izlemelerini isteyin. Kullanıcılar yönergeleri uyguladıktan sonra hata devam ederse, 2. Çözümü deneyin.

**2. Çözüm**:

Kullanıcılar şirket kimlik bilgilerini girdikten sonra hala eksik sertifika hatası alıyor ve federasyon oturum açma deneyimi için yeniden yönlendiriliyorsa, Active Directory Federasyon Hizmetleri (AD FS) sunucunuzda bir ara sertifika eksik olabilir.

Android cihazlar bir [SSL sunucu hello](https://technet.microsoft.com/library/cc783349.aspx)’sunda ara sertifikalar gerektirdiğinden sertifika hatası meydana gelir, ancak şu anda varsayılan AD FS sunucusu veya AD FS Proxy sunucusu yüklemesi, SSL sunucusu hello yanıtında SSL İstemci hello’suna yalnızca AD FS’nin hizmet SSL sertifikasını gönderir.

Sorunu düzeltmek için AD FS sunucusunda veya proxy’lerdeki Bilgisayar Kişisel Sertifikaları’na sertifikaları aşağıdaki gibi içeri aktarın:

1.    ADFS’de ve proxy sunucularında, yerel bilgisayar için Sertifika Yönetimi konsolunu başlatmak üzere **Başlat** düğmesine sağ tıklayın, **Çalıştır**’ı seçin ve **certlm.msc** yazın.
2.    **Kişisel**’i genişletip **Sertifikalar**’ı seçin.
3.    AD FS hizmeti iletişiminizin sertifikasını (ortak olarak imzalanmış bir sertifika) bulun ve özelliklerini görüntülemek için çift tıklayın.
4.    Sertifikanın üst sertifikasını (veya sertifikalarını) görmek için **Sertifika Yolu** sekmesini seçin.
5.    Her üst sertifikada, **Sertifikayı Görüntüle**’yi seçin.
6.    **Ayrıntılar** sekmesini ve **... dosyasına kopyala**’yı seçin.
7.    Sertifikanın ortak anahtarını istenen dosya konumuna kaydetmek veya dışarı aktarmak için sihirbaz yönergelerini izleyin.
8.    3. Adımda Local Computer\Personal\Certificates yoluna dışarı aktarılan üst sertifikaları içeri aktarmak için **Sertifikalar**’a sağ tıklayın, **Tüm Görevler** > **İçeri Aktar**’ı seçin ve sertifikayı (veya sertifikaları) içeri aktarmak için sihirbaz yönergelerini izleyin.
9.    AD FS sunucularını yeniden başlatın.
10.    Tüm AD FS ve proxy sunucularınızda yukarıdaki adımları yineleyin.
Kullanıcı artık Android cihazında Şirket Portalı uygulamasında oturum açabilmelidir.

**Sertifikanın düzgün yüklendiğini doğrulamak için**:

Aşağıdaki adımlar sertifikanın doğru yüklendiğini doğrulamak için kullanabileceğiniz birçok yöntem ve araçtan sadece birini açıklar.

1. [Ücretsiz Digicert aracı](ttps://www.digicert.com/help/)’na gidin.
2. AD FS sunucunuzun tam etki alanı adı (örneğin, sts.contoso.com) girin ve **SUNUCUYU DENETLE**’yi seçin.

Sunucu sertifikası düzgün yüklendiyse, sonuçlarda tüm onay işaretlerini görürsünüz. Yukarıdaki sorun mevcutsa, raporun “Sertifika Adı Eşleşiyor” ve "SSL Sertifikası Düzgün Yüklendi" bölümlerinde kırmızı bir X görürsünüz.


## <a name="ios-issues"></a>iOS sorunları

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Cihazlar etkin değil veya yönetici konsolu cihazlarla iletişim kuramıyor
**Sorun:** iOS cihazları Intune hizmetine giriş yapmıyor. Korumalı şirket kaynaklarına erişimin sürdürülmesi için cihazların hizmete düzenli olarak giriş yapması gerekir. Cihazlar giriş yapmazsa:

- Intune hizmetinden ilke, uygulama ve uzak komutları alamaz.
- Yönetici konsolunda Yönetim Durumu olarak **Uygun olmayan durumda** görüntülenir.
- Koşullu erişim ilkeleri tarafından korunan kullanıcılar şirket kaynaklarına erişimi kaybedebilir.

**Çözüm:** Şirket kaynaklarına erişimi yeniden sağlamaları için son kullanıcılarla aşağıdaki çözümleri paylaşın.

Kullanıcılar iOS Şirket Portalı uygulamasını başlattığında uygulama, cihazlarının Intune ile iletişiminin kesilip kesilmediğini bildirebilir. İletişim olmadığını algılarsa, yeniden bağlanmak için Intune ile eşitlemeyi otomatik olarak dener ve kullanıcılar **Eşitlemeye çalışılıyor...** şeklinde bir satır içi bildirim görür. 

  ![Eşitlemeye çalışılıyor bildirimi](./media/ios_cp_app_trying_to_sync_notification.png)

Eşitleme başarılı olursa, iOS Şirket Portalı uygulamasında cihazınızın iyi durumda olduğunu belirten **Eşitleme başarılı** satır içi bildirimini görürsünüz.

  ![Eşitleme başarılı bildirimi](./media/ios_cp_app_sync_successful_notification.png)

Eşitleme başarısız olursa, kullanıcılar iOS Şirket portalı uygulamasında **Eşitleme yapılamıyor** satır içi bildirimini görür. 

  ![Eşitleme yapılamıyor bildirimi](./media/ios_cp_app_unable_to_sync_notification.png)

Sorunu düzeltmek için kullanıcıların **Eşitleme yapılamıyor** bildiriminin sağındaki **Ayarla** düğmesini seçmesi gerekir. Ayarla düğmesi, kullanıcıları cihazlarını kaydetmek için istemleri takip edebilecekleri Şirket Erişim Kurulumu akış ekranına götürür. 

  ![Şirket Erişimi Kurulum ekranı](./media/ios_cp_app_company_access_setup.png)

Kaydedildikten sonra cihazlar, iyi duruma geri döner ve şirket kaynaklarına yeniden erişim kazanır.

### <a name="profile-installation-failed"></a>Profil yüklemesi başarısız oldu
**Sorun:** Bir kullanıcı, bir iOS cihazında **Profil yüklemesi başarısız oldu** hatasını alıyor.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Başarısız olan profil yüklemesi sorunlarını giderme adımları

1.  Kullanıcıya, Intune hizmetinin kullandığınız sürümü için uygun lisansın atandığını onaylayın.

2.  Cihazın zaten başka bir MDM sağlayıcısıyla kaydedilmediğini ve cihaza önceden bir yönetim profili yüklenmediğini doğrulayın.

3.  [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) adresine gidin ve istendiğinde profili yüklemeyi deneyin.

4.  iOS için Safari’nin varsayılan tarayıcı olduğunu ve tanımlama bilgilerinin etkinleştirildiğini doğrulayın.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Intune’la birlikte System Center Configuration Manager kullanıldığında kayıtlı iOS cihazı konsolda gösterilmiyor
**Sorun:** Kullanıcı iOS cihazını kaydediyor ancak cihaz Configuration Manager yönetici konsolunda gösterilmiyor. Cihaz kayıtlı olduğunu göstermiyor. Olası nedenler:

- Intune Bağlayıcınızı bir hesaba kaydettikten sonra bunu başka bir hesaba kaydetmiş olabilirsiniz.
- MDM sertifikasını bir hesaptan indirip başka bir hesapla kullanmış olabilirsiniz.


**Çözüm:** Aşağıdaki adımları uygulayın:

1. Windows Intune Bağlayıcısı’nın içinden iOS’u devre dışı bırakın.
    1. Intune aboneliğine sağ tıklayın ve **Özellikler**’i seçin.
    1. "iOS" sekmesinde "iOS kaydını etkinleştir" seçeneğinin işaretini kaldırın.



2. SQL’de, CAS DB’de aşağıdaki adımları çalıştırın

    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 7
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 11
    1. delete from MDMPolicyAssignment where PolicyType = 11
    1. DELETE Drs_Signals
3. SMS İdarecisi Hizmeti’ni yeniden başlatın veya CM Sunucusu’nu yeniden başlatın.

4. Yeni bir APN sertifikası alın ve karşıya yükleyin. Bunu yapmak için Configuration Manager’ın sol bölmesinde Intune aboneliğine sağ tıklayın. **APNs sertifikası isteği oluştur**’u seçin ve yönergeleri izleyin.
5. 
## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>System Center Configuration Manager’ı Intune kullanırken oluşan sorunlar

### <a name="mobile-devices-disappear"></a>Mobil cihazlar kayboluyor

**Sorun:** Mobil cihazı Configuration Manager’a başarıyla kaydettikten sonra, cihaz mobil cihaz koleksiyonundan kayboluyor; ancak hala Yönetim Profili var ve CSS Ağ Geçidi’nde listeleniyor.

**Çözüm:** Etki alanına katılmayan cihazları kaldıran özel bir işleminiz varsa veya kullanıcı cihazı abonelikte devre dışı bırakırsa bu sorun ortaya çıkabilir. Configuration Manager konsolunda cihazı hangi işlemin veya kullanıcı hesabının kaldırdığını denetlemek ve doğrulamak için, aşağıdaki adımları izleyerek cihazın nasıl kaldırıldığını denetleyin.

1.  Configuration Manager yönetim konsolunda **İzleme** &gt; **Sistem Durumu** &gt; **Durum İletisi Sorguları**’nı seçin.

2.  **Elle Silinen Koleksiyon Üye Kaynakları**’na sağ tıklayın ve **İletileri Göster**’i seçin.

3.  Uygun bir saat/tarih belirtin veya son 12 saati seçin.

4.  Söz konusu cihazı bulun ve cihazın nasıl kaldırıldığını gözden geçirin. Aşağıdaki örnekte, cihazın Bilinmeyen Uygulama yoluyla SCCMInstall hesabı tarafından silindiği gösterilir.

    ![Cihaz silme tanılamasının ekran görüntüsü](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  Configuration Manager’da etki alanı dışında olan, mobil veya ilgili cihazları otomatik olarak temizleyebilecek, zamanlanmış bir görev, komut dosyası veya başka bir işlemin bulunup bulunmadığını denetleyin.




### <a name="other-ios-enrollment-errors"></a>Diğer iOS kayıt hataları

Son kullanıcılara gösterilebilen [iOS kayıt hataları](https://docs.microsoft.com/intune/enduser/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios) listesini görüntüleyebilirsiniz. Listede, son kullanıcıların görebileceği hata iletileri ve sorunu çözmek için izleyebileceğiniz adımlar hakkında bilgi sağlanır.

## <a name="pc--issues"></a>PC Sorunları

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>Makine zaten kaydoldu - Hata hr 0x8007064c
**Sorun:** Kayıt işlemi **Makine zaten kaydoldu** hatasıyla başarısız oluyor. Kayıt günlüğünde **hr 0x8007064c** hatası gösteriliyor.

Bu hatanın nedeni bilgisayarın daha önce kaydolmuş olması veya kayıtlı bir bilgisayarın kopyalanmış görüntüsünü içermesi olabilir. Önceki hesabın hesap sertifikası hala bilgisayarda duruyordur.

**Çözüm:**

1.. **Başlangıç** menüsünde, **Çalıştır** -> **MMC** yazın.
1. **Dosya** > **Ek Bileşen Ekle/Kaldır**’ı seçin.
1. **Sertifikalar**’a çift tıklayın, **Bilgisayar hesabı** > **İleri**’yi ve sonra **Yerel Bilgisayar**’ı seçin.
1. **Sertifikalar (Yerel bilgisayar)** seçeneğine çift tıklayın ve **Kişisel/ Sertifikalar**’ı seçin.
1. Sc_Online_Issuing tarafından verilen Intune sertifikasını arayın ve bulursanız silin.
1. Şu kayıt defteri anahtarı varsa, tüm alt anahtarlarıyla birlikte silin: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**.
1. Yeniden kaydetmeyi deneyin.
1. Bilgisayar yine kaydedilemiyorsa, şu anahtarı arayın ve bulursanız silin: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Yeniden kaydetmeyi deneyin.

    > [!IMPORTANT]
    > Bu bölüm, yöntem veya görev kayıt defterinde nasıl değişiklik yapacağınızı gösteren adımlar içerir. Bununla birlikte, kayıt defterinde yanlış değişiklikler yaparsanız ciddi sorunlar çıkabilir. Bu nedenle, bu adımları dikkatle izlediğinizden emin olun. Ek bir koruma için, değişiklikleri yapmadan önce kayıt defterini yedekleyin. Böylece bir sorun ortaya çıktığında kayıt defterini geri yükleyebilirsiniz.
    > Kayıt defterini yedekleme ve geri yükleme hakkında daha fazla bilgi için, [Windows’da kayıt defterini yedekleme ve geri yükleme](https://support.microsoft.com/en-us/kb/322756) konusunu okuyun.

## <a name="general-enrollment-error-codes"></a>Genel kayıt hata kodları

|Hata kodu|Olası sorun|Önerilen çözüm|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |İstemci bilgisayarındaki saat doğru zamana ayarlanmadı.|İstemci bilgisayardaki saat ve saat diliminin doğru saat ve saat dilimine ayarlandığından emin olun.|
|0x80240438, 0x80CF0438, 0x80CF402C|Intune hizmetine bağlanılamıyor. İstemci proxy ayarlarını kontrol edin.|İstemci bilgisayardaki proxy ayarlarının Intune tarafından desteklendiğinden ve istemci bilgisayarın İnternet erişimi olduğundan emin olun.|
|0x80240438, 0x80CF0438|Internet Explorer ve Yerel Sistem proxy ayarları yapılandırılmadı.|Intune hizmetine bağlanılamıyor. İstemci proxy ayarlarını denetleyin ve istemci bilgisayardaki proxy yapılandırmasının Intune tarafından desteklendiğinden ve istemci bilgisayarın İnternet erişimi olduğundan emin olun.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Kayıt paketi güncel değil.|Yönetim çalışma alanından güncel istemci yazılımı paketini indirin ve yükleyin.|
|0x80043002, 0x80CF3002|Hesap bakım modunda.|Hesap bakım modunda olduğunda yeni istemci bilgisayarlar kaydedilemez. Hesap ayarlarınızı görüntülemek için hesabınızda oturum açın.|
|0x80043003, 0x80CF3003|Hesap silindi.|Hesabınızın ve Intune aboneliğinizin hala etkin olduğunu doğrulayın. Hesap ayarlarınızı görüntülemek için hesabınızda oturum açın.|
|0x80043005, 0x80CF3005|İstemci bilgisayar devre dışı bırakıldı.|Birkaç saat bekleyin, bilgisayardan istemci yazılımının daha eski sürümlerini kaldırın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|0x80043006, 0x80CF3006|İzin verilen maksimum bilgisayar lisansı sayısına ulaşıldı.|Kuruluşunuzun hizmete daha fazla istemci bilgisayar kaydedebilmek için ek bilgisayar lisansları satın alması gerekir.|
|0x80043007, 0x80CF3007|Yükleyici programla aynı klasörde sertifika dosyası bulunamadı.|Yüklemeyi başlatmadan önce tüm dosyaları ayıklayın. Ayıklanan dosyaları yeniden adlandırmayın veya yerini değiştirmeyin: tüm dosyalar aynı klasörde bulunmalıdır; aksi takdirde yükleme başarısız olur.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|İstemci bilgisayarın yeniden başlatılması beklendiğinden yazılım yüklenemiyor.|Bilgisayarı yeniden başlatın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|0x80070032|İstemci yazılımını yüklemek için bir veya daha fazla önkoşul istemci bilgisayarda bulunamadı.|Gerekli tüm güncelleştirmelerin istemci bilgisayarda yüklü olduğundan emin olun ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|0x80043008, 0x80CF3008|Microsoft Online Management Güncelleştirmeleri hizmeti başlatılamadı.|[Microsoft Intune için destek alma](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.|
|0x80043009, 0x80CF3009|İstemci bilgisayar hizmete zaten kayıtlı.|İstemci bilgisayarı bu hizmete yeniden kaydetmek için önce devre dışı bırakmanız gerekir.|
|0x8004300B, 0x80CF300B|İstemci üzerinde çalışan Windows sürümü desteklenmediğinden, istemci yazılımı yükleme paketi çalıştırılamıyor.|Intune istemci bilgisayarda çalışan Windows sürümünü desteklemiyor.|
|0xAB2|Windows Installer özel bir işlem için VBScript çalışma zamanına erişemedi.|Bu hata Dinamik Bağlantı Kitaplıkları'nı (DLLs) temel alan özel bir işlemden kaynaklanır. DLL sorunlarını giderirken, [Microsoft Desteği KB198038: Paket ve Dağıtım Sorunlarında Yararlı Araçlar](https://support.microsoft.com/en-us/kb/198038) makalesinde açıklanan araçları kullanmanız gerekebilir.|
|0x80cf0440|Hizmet uç noktası bağlantısı sonlandırıldı.|Deneme hesabı veya ücretli hesap askıya alındı. Yeni bir deneme hesabı veya ücretli hesap oluşturun ve yeniden kaydolun.|




### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.

