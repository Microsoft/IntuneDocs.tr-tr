---
title: Microsoft Intune - Azure’da ilke sorunlarını giderme | Microsoft Docs
description: Yerleşik sorun giderme özelliğini kullanın ve uyumluluk ilkeleri ve yapılandırma profillerini Intune kullanılırken karşılaşılan veya sorunları ve çözümleri hakkında okuyun bakın
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77e86912870b22168a7e2dd3e146b9410c482744
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841088"
---
# <a name="troubleshoot-policies-and-profiles-and-in-intune"></a>İlkeler ve Profiller sorun giderme ve ıntune

Microsoft Intune yerleşik bazı sorun giderme özellikleri içerir. Uyumluluk ilkeleri ve yapılandırma profillerini, ortamınızdaki gidermenize yardımcı olması için bu özellikleri kullanın.

Bu makalede bazı genel sorun giderme teknikleri listeler ve karşılaşabileceğiniz bazı sorunlar açıklanmaktadır.

## <a name="use-built-in-troubleshooting"></a>Yerleşik sorun giderme kullanın

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. Seçin **sorun giderme**:

    ![Intune, Yardım ve Destek gidin ve sorun giderme seçin](./media/help-and-support-troubleshoot.png)

3. Seçin **Kullanıcı Seç** > bir sorun bir kullanıcı seçin > **seçin**.
4. Onaylayın **Intune lisansı** ve **hesap durumu** her ikisini de yeşil denetimleri göster:

    ![Intune, kullanıcı seçin ve hesap durumu ve Intune lisansı, durum yeşil denetimleri işaretleri Göster onaylayın](./media/account-status-intune-license-show-green.png)

    **Faydalı bağlantılar**:

    - [Kullanıcıların cihazları kaydedebilmesi için lisans atama](licenses-assign.md)
    - [Intune’a kullanıcı ekleme](users-add.md)

5. Altında **cihazları**, sorun yaşıyor cihaz bulun. Farklı sütunlar gözden geçirin:

    - **Yönetilen**: Bu özellik bir cihaz uyumluluk veya yapılandırma ilkelerini almaya göstermesi **MDM** veya **EAS/MDM**.

      - Varsa **yönetilen** belirlendiğinden **MDM** veya **EAS/MDM**, sonra da bu cihaz kayıtlı değil. Kaydedilene kadar uyumluluk veya yapılandırma ilkeleri almaz.

      - Uygulama koruma ilkelerini (mobil uygulama yönetimi), cihazların kaydedilmesi gerekmez. Daha fazla bilgi için [uygulama koruma ilkeleri oluşturma ve atama](app-protection-policies.md).

    - **Azure AD katılım türü**: Ayarlanmalıdır **çalışma alanına** veya **AzureAD**.
 
      - Bu sütun ise **kayıtlı**, kayıt ile ilgili bir sorun olabilir. Genellikle, bu durum kaydını ve cihaz gerektireceğini çözümler.

    - **Intune ile uyumlu**: Olmalıdır **Evet**. Varsa **Hayır** gösterilir, cihazı Intune hizmetine değil veya uyumluluk ilkeleri ile ilgili bir sorun olabilir. Örneğin, cihaz kapalı olabilir veya bir ağ bağlantısı yok. Sonuç olarak, büyük olasılıkla 30 gün sonra cihaz uyumlu olmayan, olur.

      Daha fazla bilgi için [cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

    - **Azure AD uyumlu**: Olmalıdır **Evet**. Varsa **Hayır** gösterilir, cihazı Intune hizmetine değil veya uyumluluk ilkeleri ile ilgili bir sorun olabilir. Örneğin, cihaz kapalı olabilir veya bir ağ bağlantısı yok. Sonuç olarak, büyük olasılıkla 30 gün sonra cihaz uyumlu olmayan, olur.

      Daha fazla bilgi için [cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

    - **Son iade**: Son saat ve tarihi olmalıdır. Varsayılan olarak, Intune cihaz iade 8 saatte bir.

      - Varsa **son iade** 24 saatten uzun olduğundan, cihaz ile ilgili bir sorun olabilir. İade edilemiyor bir cihazı Intune'dan ilkelerinizi alamaz.

      - İade zorlamak için:
        - Android cihazında Şirket portalı uygulamasını açın > **cihazları** > listeden cihazı seçin > **cihaz ayarları denetle**.
        - İOS cihazında Şirket portalı uygulamasını açın > **cihazları** > listeden cihazı seçin > **ayarları denetle**. 
        - Bir Windows cihazında açın **ayarları** > **hesapları** > **işe veya okula erişim** > hesabını veya MDM kaydı seçin >  **Bilgi** > **eşitleme**.

    - İlkeye özgü belirli bilgi kaldırmak istediğiniz cihazı seçin.

      **Cihaz uyumluluğu** cihaza atanmış uyumluluk İlkesi durumlarını gösterir.

      **Cihaz Yapılandırması** yapılandırma ilkelerini cihaza atanan durumlarını gösterir.

      Beklenen ilkeleri altında gösterilmez, **cihaz uyumluluğu** veya **cihaz Yapılandırması**, ilkeleri doğru şekilde hedeflenen olmayan sonra. İlkeyi açın ve bu kullanıcı veya cihaz ilkeyi atayın.

      **İlke durumları**:

      - **Uygulanamaz**: Bu ilke, bu platformda desteklenmiyor. Örneğin, iOS ilkeleri Android'de çalışmaz. Windows cihazlarında Samsung KNOX ilkeleri çalışmaz.
      - **Çakışma**: Intune geçersiz kılınamaz cihaz üzerinde var olan bir ayar yoktur. Veya farklı değerler kullanarak aynı ayarı ile iki ilke dağıtılır.
      - **Bekleyen**: İlkeyi almak için Intune'a cihaz iade edilmemiş. Veya cihaz, ilke aldı ancak Intune'a durum bildirilmemiştir.
      - **Hataları**: Hataları ve olası çözünürlüklerde [şirket kaynak erişimi sorunlarını giderme](troubleshoot-company-resource-access-problems.md).

      **Faydalı bağlantılar**: 

      - [Cihaz uyumluluk ilkelerini dağıtma yolları](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies)
      - [Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)

## <a name="youre-unsure-if-a-profile-is-correctly-applied"></a>Bir profili doğru şekilde uygulanırsa emin değilseniz

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. Seçin **cihazları** > **tüm cihazlar** > cihazı seçin > **cihaz Yapılandırması**. 

    Her cihazda, kendi profilleri listeler. Her profiline sahip bir **durumu**. Tüm donanım ve işletim sistemi kısıtlamaları ve gereksinimleri dahil olmak üzere atanan profillerini birlikte kabul durumu uygulanır. Olası durumlar şunlardır:

    - **Uygun**: Cihaz profili ve raporları alınan ayarına uyan ıntune.

    - **Uygulanamaz**: Profil ayarı geçerli değil. Örneğin, iOS cihazları için e-posta ayarları bir Android cihazı için geçerli değildir.

    - **Bekleyen**: Profil cihaza gönderilir, ancak Intune'a durum bildirilmemiştir. Örneğin Android’de şifreleme, son kullanıcının şifrelemeyi etkinleştirmesi gerektirdiği için beklemede olarak görünebilir.

**Yararlı bağlantı**: [Yapılandırma cihaz profillerini izleme](device-profile-monitor.md)

> [!NOTE]
> Farklı kısıtlama düzeylerine sahip iki ilke aynı cihaz veya kullanıcıya uygulanırsa, daha kısıtlayıcı olan ilke uygulanır.

## <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a>Uyarı: Erişim kuralları Exchange'e kaydedilemedi

**Sorunu**: Uyarı aldığınız **erişim kuralları Exchange'e oldu** yönetim konsolundaki.

(Yönetici Konsolu) şirket içi Exchange İlkesi çalışma alanında ilkeler oluşturma, ancak Office 365 kullanıyorsanız, yapılandırılan ilke ayarları Intune tarafından zorunlu değildir. Uyarıda ilke kaynağını not alın. Şirket içi Exchange İlkesi çalışma alanında, eski kuralları silin. Eski kuralları, şirket içi Exchange için ıntune'daki genel Exchange kurallarıdır ve Office 365'e uygun değildir. Ardından, Office 365 için yeni ilke oluşturun.

[Intune şirket içi Exchange connector sorunlarını giderme](troubleshoot-exchange-connector.md) iyi bir kaynak olabilir.

## <a name="cant-change-security-policies-for-enrolled-devices"></a>Kayıtlı cihazlar için güvenlik ilkelerini değiştiremezsiniz

Windows Phone cihazları, bunları ayarladıktan sonra azaltılmasına için MDM veya EAS kullanarak ayarlamış güvenlik ilkelerinin izin vermez. Örneğin, bir **parolanın karakter sayısı alt sınırı** 8 ve sonra bunu 4'e indirmeyi deneyin. Daha kısıtlayıcı bir ilke cihaza uygulanır.

Cihaz platformuna bağlı olarak, ilkeyi daha az güvenli bir değerle değiştirmek isterseniz, güvenlik ilkelerini sıfırlamanız gerekebilir.

Örneğin Windows’da, masaüstünde sağdan içeri doğru çekerek **Düğmeler** çubuğunu açın. Seçin **ayarları** > **Denetim Masası** > **kullanıcı hesaplarını**. Sol taraftaki **Güvenlik İlkelerini Sıfırla**’yı seçin ve **İlkeleri Sıfırla**’ya tıklayın.

Android, iOS ve Windows Phone 8.1 gibi diğer MDM cihazlarında, devre dışı bırakılması ve daha az kısıtlayıcı bir ilkeyi uygulayabilmeniz için kaydedilmesi gerekebilir.

[Cihaz kaydıyla ilgili sorunları giderme](troubleshoot-device-enrollment-in-intune.md) iyi bir kaynak olabilir.

## <a name="pcs-using-the-intune-software-client---classic-portal"></a>Intune yazılım istemcisi - Klasik portalı kullanarak Windows bilgisayarlarının

> [!NOTE]
> Bu bölüm Klasik portalda geçerlidir. 

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>policyplatform.log dosyasındaki Microsoft Intune ilkesiyle ilgili hatalar

İlke hataları Intune yazılım istemcisi ile yönetilen Windows bilgisayarlar için `policyplatform.log` dosya, varsayılan olmayan ayarların cihazdaki Windows kullanıcı hesabı denetimi (UAC) içinde gelen olabilir. Varsayılan olmayan bazı UAC ayarları Microsoft Intune istemci yüklemelerini ve ilke yürütmesini etkileyebilir.

#### <a name="resolve-uac-issues"></a>UAC sorunlarını çözme

1. Bilgisayarı kullanımdan kaldırın. Bkz. [Cihaz kaldırma](devices-wipe.md).

2. İstemci yazılımının kaldırılması için 20 dakika bekleyin.

    > [!NOTE]
    > İstemciyi Programlar ve Özellikler menüsünden kaldırmaya çalışmayın.

3. Başlat menüsünde yazın **UAC** kullanıcı hesabı denetimi ayarlarını açın.

4. Bildirim kaydırıcısını varsayılan ayara getirin.

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a>HATA: Bilgisayarda, 0x80041013 değeri alınamıyor

Yerel sistemdeki saat beş dakika veya daha fazla farklı ise bu hata oluşur. Yerel bilgisayardaki saat eşitleme dışı ise zaman damgaları geçersiz olduğundan güvenli işlemler başarısız.

Bu sorunu çözmek için yerel sistem saatini Internet saatine mümkün olduğunca kapatmak ayarlayın. Veya, ağdaki etki alanı denetleyicilerinde zamana ayarlayın.

## <a name="next-steps"></a>Sonraki adımlar

Hala yardıma ihtiyacınız varsa, [Intune için destek alma](get-support.md).
