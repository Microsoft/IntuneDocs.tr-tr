---
title: Microsoft Intune - Azure’da ilke sorunlarını giderme | Microsoft Docs
description: Bkz. yerleşik sorun giderme özelliğini kullanma ve Microsoft Intune ' de uyumluluk ilkeleri ve yapılandırma profillerini kullanırken yaygın sorunlar ve sorunlar ve bunların çözümleri hakkında bilgi edinin
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2afdd358af19c28ff18e4e6e65839d7e314996b1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731529"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>İlke ve profillerin ve Intune 'da sorun giderme

Microsoft Intune, bazı yerleşik sorun giderme özellikleri içerir. Ortamınızdaki uyumluluk ilkeleri ve yapılandırma profillerinin sorunlarını gidermeye yardımcı olması için bu özellikleri kullanın.

Bu makalede bazı yaygın sorun giderme teknikleri listelenmekte ve karşılaşabileceğiniz bazı sorunlar açıklanmaktadır.

## <a name="check-tenant-status"></a>Kiracı durumunu denetle
[Kiracı durumunu](../fundamentals/tenant-status.md) denetleyin ve aboneliğin etkin olduğunu onaylayın. İlkeyi veya profil dağıtımınızı etkileyebilecek etkin olaylar ve Danışma belgeleri ayrıntılarını da görüntüleyebilirsiniz.

## <a name="use-built-in-troubleshooting"></a>Yerleşik sorun giderme kullanın

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'Da **sorun gider**' i seçin:

    ![Intune 'da yardım ve destek ' e gidin ve sorun giderme ' yi seçin.](./media/troubleshoot-policies-in-microsoft-intune/help-and-support-troubleshoot.png)

2. **Kullanıcı seç** > seçin > bir sorun yaşayan Kullanıcı Seç ' **i seçin**.
3. **Intune lisansının** ve **hesap durumunun** her ikisinin de yeşil denetimleri göstermesini onaylayın:

    ![Intune 'da Kullanıcı seçin ve hesap durumunu onaylayın ve Intune lisansı durum için yeşil denetim işaretlerini göster](./media/troubleshoot-policies-in-microsoft-intune/account-status-intune-license-show-green.png)

    **Faydalı bağlantılar**:

    - [Kullanıcıların cihazları kaydedebilmesi için lisans atama](../fundamentals/licenses-assign.md)
    - [Intune’a kullanıcı ekleme](../fundamentals/users-add.md)

4. **Cihazlar**' ın altında, sorun bulunan cihazı bulun. Farklı sütunları gözden geçirin:

    - **Yönetilen**: bir cihazın uyumluluk veya yapılandırma ilkeleri alması için bu özellik **MDM** veya **EAS/MDM**öğesini göstermelidir.

        - **Yönetilen** **MDM** veya **EAS/MDM**olarak ayarlanmamışsa, cihaz kayıtlı değildir. Bu, kaydedilinceye kadar uyumluluk veya yapılandırma ilkeleri almaz.

        - Uygulama koruma ilkeleri (mobil uygulama yönetimi) cihazların kaydedilmesini gerektirmez. Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri oluşturma ve atama](../apps/app-protection-policies.md).

    - **Azure AD katılma türü**: **Workplace** veya **azuread**olarak ayarlanmalıdır.
 
        - Bu sütun **kayıtlı değilse**, kayıt ile ilgili bir sorun olabilir. Genellikle, cihazın kaydı geri ve yeniden kaydedilmesi bu durumu çözer.

    - **Intune uyumlu**: **Evet**olmalıdır. **Hayır gösterilmediğinde** , uyumluluk ilkeleriyle ilgili bir sorun olabilir veya cihaz Intune hizmetine bağlanmıyor olabilir. Örneğin, cihaz kapalı olabilir veya bir ağ bağlantısına sahip olmayabilir. Sonuç olarak, cihaz, genellikle 30 gün sonra uyumsuz hale gelir.

        Daha fazla bilgi için bkz. [cihaz uyumluluk ilkelerini kullanmaya başlama](../protect/device-compliance-get-started.md).

    - **Azure AD uyumlu**: **Evet**olmalıdır. **Hayır gösterilmediğinde** , uyumluluk ilkeleriyle ilgili bir sorun olabilir veya cihaz Intune hizmetine bağlanmıyor olabilir. Örneğin, cihaz kapalı olabilir veya bir ağ bağlantısına sahip olmayabilir. Sonuç olarak, cihaz, genellikle 30 gün sonra uyumsuz hale gelir.

        Daha fazla bilgi için bkz. [cihaz uyumluluk ilkelerini kullanmaya başlama](../protect/device-compliance-get-started.md).

    - **Son iade etme**: son tarih ve saat olmalıdır. Varsayılan olarak, Intune cihazları her 8 saatte bir denetler.

        - **Son iade etme** işlemi 24 saatten fazla ise, cihazla ilgili bir sorun olabilir. İade etme yapamıyor bir cihaz, ilkeleri Intune 'dan alamıyor.

        - İade etmeye zorlamak için:
            - Android cihazında Şirket Portalı App > **cihazlarını** açın > cihazı listeden seçin > **cihaz ayarlarını denetleyin**.
            - İOS cihazında, Şirket portalı uygulaması > **cihazları** açın > cihazı listeden seçin > **ayarları denetle**' ye tıklayın.

        - Bir Windows cihazında **ayarlar** > **Hesap** > **erişim iş veya okul** > hesap veya MDM kayıt > **bilgi** > **eşitleme**' yi seçin.

    - İlkeye özgü bilgileri görmek için cihazı seçin.

        **Cihaz uyumluluğu** , cihaza atanan uyumluluk ilkelerinin durumlarını gösterir.

        **Cihaz yapılandırması** cihaza atanan yapılandırma ilkelerinin durumlarını gösterir.

        Beklenen ilkeler **cihaz uyumluluğu** veya **cihaz yapılandırması**altında gösterilmiyorsa, ilkeler doğru şekilde hedeflenmez. İlkeyi açın ve ilkeyi bu kullanıcıya veya cihaza atayın.

        **İlke durumları**:

        - **Uygulanamaz**: Bu ilke bu platformda desteklenmiyor. Örneğin, iOS ilkeleri Android üzerinde çalışmaz. Samsung KNOX ilkeleri Windows cihazlarında çalışmaz.
        - **Çakışma**: cihazda Intune 'un geçersiz kılamadığı bir ayar var. Ya da, farklı değerleri kullanarak aynı ayarla iki ilke dağıttınız.
        - **Bekliyor**: cihaz, ilkeyi almak için Intune 'a iade edilmedi. Ya da cihaz ilkeyi aldı, ancak durumu Intune 'a bildirmemiştir.
        - **Hatalar**: [Şirket kaynağına erişim sorunlarını gidermeye yönelik](../fundamentals/troubleshoot-company-resource-access-problems.md)hataları ve olası çözümleri arama.

        **Faydalı bağlantılar**: 

        - [Cihaz uyumluluk ilkelerini dağıtma yolları](../protect/device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
        - [Cihaz uyumluluk ilkelerini izleme](../protect/compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Bir profilin doğru bir şekilde uygulanmış olması konusunda emin değilseniz

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Cihazlar** > **tüm cihazlar** ' ı seçin > Cihaz > cihaz **yapılandırmasını**seçin. 

    Her cihazda profillerini listeler. Her profilin bir **durumu**vardır. Bu durum, donanım ve işletim sistemi kısıtlamaları ve gereksinimleri de dahil olmak üzere tüm atanan profillerin birlikte kabul edildiği durumlarda geçerlidir. Olası durumlar şunlardır:

    - **Uyumlu**: Cihaz profili ve raporları, ayara uygun olan Intune 'a aldı.

    - **Uygulanamaz**: profil ayarı geçerli değil. Örneğin, iOS cihazları için e-posta ayarları bir Android cihazına uygulanmaz.

    - **Bekliyor**: profil cihaza gönderilir, ancak durum Intune 'a bildirilmemiştir. Örneğin Android’de şifreleme, son kullanıcının şifrelemeyi etkinleştirmesi gerektirdiği için beklemede olarak görünebilir.

**Faydalı bağlantı**: [yapılandırma cihaz profillerini izleme](../configuration/device-profile-monitor.md)

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, daha kısıtlayıcı olan ilke uygulanır.

## <a name="policy-troubleshooting-resources"></a>İlke sorunlarını giderme kaynakları

- [İOS veya Android Ilkelerinin sorun giderme cihazlara uygulanmıyor](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-tip-Troubleshooting-iOS-or-Android-policies-not-applying/ba-p/280154) (başka bir Microsoft sitesi açar)
- [Windows 10 Intune ilkesi hatalarında sorun giderme](https://blogs.technet.microsoft.com/configmgrdogs/2018/08/09/troubleshooting-windows-10-intune-policy-failures/) (bir blog açar)
- [Windows 10 IÇIN CSP özel ayarları sorunlarını giderme](https://support.microsoft.com/en-us/help/4055338/troubleshoot-csp-setting-windows-10-computer-intune) (başka bir Microsoft sitesi açar)
- [Windows 10 Grup İlkesi vs ıNTUNE MDM ilkesi](https://blogs.technet.microsoft.com/cbernier/2018/04/02/windows-10-group-policy-vs-intune-mdm-policy-who-wins/) (başka bir Microsoft sitesini açar)

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Uyarı: Erişim Kuralları Exchange’e Kaydedilemedi

**Sorun**: Yönetici konsolunda **Erişim Kuralları Exchange’e Kaydedilemedi**  hatasını alıyorsunuz.

Şirket Içi Exchange Ilkesi çalışma alanında (Yönetici Konsolu) ilkeler oluşturursanız, ancak Office 365 kullanıyorsanız, yapılandırılan ilke ayarları Intune tarafından zorlanmaz. Uyarıda, ilke kaynağını aklınızda edin. Şirket içi Exchange Ilkesi çalışma alanında eski kuralları silin. Eski kurallar, şirket içi Exchange için Intune 'daki genel Exchange kurallarıdır ve Office 365 ile ilgili değildir. Ardından, Office 365 için yeni ilke oluşturun.

[Intune şirket Içi Exchange Connector 'Da sorun giderme](../protect/troubleshoot-exchange-connector.md) iyi bir kaynak olabilir.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Kayıtlı cihazlar için güvenlik ilkeleri değiştirilemiyor

Windows Phone cihazlar, MDM veya EAS kullanılarak ayarlandıktan sonra güvenliği azaltmak için güvenlik ilkelerine izin vermez. Örneğin, **en az sayıda karakter parolası** 8 olarak ayarlanır ve ardından 4 ' e azaltmayı deneyin. Cihaza daha kısıtlayıcı olan ilke uygulanır.

İlke atamasını kaldırdığınızda Windows 10 cihazları güvenlik ilkelerini kaldıramayabilir (dağıtımı Durdur). İlkeyi atanmış bırakmanız ve ardından güvenlik ayarlarını varsayılan değerlere geri değiştirmeniz gerekebilir.

Cihaz platformuna bağlı olarak, ilkeyi daha az güvenli bir değerle değiştirmek isterseniz, güvenlik ilkelerini sıfırlamanız gerekebilir.

Örneğin, Windows 8.1 Masaüstünde, sağ taraftaki içeri doğru kaydırın ve sonra da **Charms** çubuğunu açın. @No__t **ayarları**-1**Denetim Masası** > **Kullanıcı hesabı**' nı seçin. Sol taraftaki **Güvenlik İlkelerini Sıfırla**’yı seçin ve **İlkeleri Sıfırla**’ya tıklayın.

Android, iOS ve Windows Phone 8,1 gibi diğer platformların devre dışı bırakılması ve daha az kısıtlayıcı bir ilke uygulamak için yeniden kaydedilmesi gerekebilir.

[Cihaz kaydı sorunlarını giderme](../enrollment/troubleshoot-device-enrollment-in-intune.md) iyi bir kaynak olabilir.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Intune yazılım istemcisi ile klasik portalı kullanan bilgisayarlar

> [!NOTE]
> Bu bölüm, klasik Portal için geçerlidir. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>policyplatform.log dosyasındaki Microsoft Intune ilkesiyle ilgili hatalar

Intune yazılım istemcisiyle yönetilen Windows bilgisayarlarında, `policyplatform.log` dosyasındaki ilke hataları, cihazdaki Windows Kullanıcı hesabı denetimi 'nde (UAC) varsayılan olmayan ayarlardan olabilir. Varsayılan olmayan bazı UAC ayarları Microsoft Intune istemci yüklemelerini ve ilke yürütmesini etkileyebilir.

#### <a name="resolve-uac-issues"></a>UAC sorunlarını çözme

1. Bilgisayarı kullanımdan kaldırın. Bkz. [Cihaz kaldırma](../remote-actions/devices-wipe.md).

2. İstemci yazılımının kaldırılması için 20 dakika bekleyin.

    > [!NOTE]
    > İstemciyi Programlar ve Özellikler menüsünden kaldırmaya çalışmayın.

3. Başlat menüsünde, Kullanıcı hesabı denetimi ayarlarını açmak için **UAC** yazın.

4. Bildirim kaydırıcısını varsayılan ayara taşıyın.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>HATA: Bilgisayardan değer alınamadı, 0x80041013

Yerel sistemdeki saat beş dakika veya daha fazla farklı ise bu hata oluşur. Yerel bilgisayardaki süre eşitlenmemiş ise, zaman damgaları geçersiz olduğundan güvenli işlemler başarısız olur.

Bu sorunu çözmek için, yerel sistem saatini Internet saatine olabildiğince yakın olarak ayarlayın. Ya da, ağ üzerindeki etki alanı denetleyicilerde zaman olarak ayarlayın.

## <a name="next-steps"></a>Sonraki adımlar

[E-posta profilleriyle ilgili yaygın sorunlar ve çözümler](../configuration/troubleshoot-email-profiles-in-microsoft-intune.md)

[Microsoft 'un destek yardımına](../fundamentals/get-support.md)ulaşın veya [topluluk forumlarını](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune)kullanın.
