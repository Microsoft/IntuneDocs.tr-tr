---
title: Microsoft Intune-Azure 'da Wi-Fi cihaz profili günlüklerini sorun giderme ve gözden geçirme | Microsoft Docs
description: Microsoft Intune 'de Android, iOS ve Windows cihazlarında Wi-Fi cihaz yapılandırma profili sorunlarını anlayın ve sorun giderin. Günlükleri gözden geçirin ve bazı yaygın sorunları ve olası çözümleri görüntüleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77f5787509438ec3280f29be8449d78979806042
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74542331"
---
# <a name="troubleshoot-wi-fi-device-configuration-profiles-in-microsoft-intune"></a>Microsoft Intune 'de Wi-Fi cihaz yapılandırma profillerinin sorunlarını giderme

Intune 'da, WiFi ağınız için bağlantı ayarlarını içeren cihaz yapılandırma profilleri oluşturabilirsiniz. Kullanıcıların Android, iOS ve Windows cihazlarını kuruluş ağına bağlamak için bu ayarları kullanın.

Bu makalede, bir Wi-Fi profilinin cihazlara başarıyla uygulandığı sırada nasıl göründüğü gösterilmektedir. Ayrıca günlük bilgilerini, yaygın sorunları ve daha fazlasını içerir. Wi-Fi profillerinizi sorun gidermeye yardımcı olması için bu makaleyi kullanın.

Intune 'da Wi-Fi profilleri hakkında daha fazla bilgi için, bkz. [cihazlarınızda Wi-Fi ayarlarını ekleme ve kullanma](wi-fi-settings-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

Bu makaledeki örneklerde, Intune profilleri için SCEP sertifikası kimlik doğrulaması kullanılır. Ayrıca, güvenilen kök ve SCEP profillerinin cihazda düzgün çalıştığını varsayar.

## <a name="android"></a>Android

Bu bölümde, bir Android cihazına yapılandırma profillerini yüklerken Son Kullanıcı deneyiminden ilerliyoruz.

### <a name="end-user-experience-example"></a>Son Kullanıcı deneyimi örneği

Bu senaryo bir Nokia 6,1 cihazı kullanır. Wi-Fi profili cihaza yüklenmeden önce güvenilen kök ve SCEP profillerini yükleme.

1. Son kullanıcılar, güvenilen kök sertifika profilini yüklemek için bir bildirim alır:

    > [!div class="mx-imgBorder"]
    > Güvenilen kök sertifika profili yüklemek için Android 'de ![örnek Şirket Portalı uygulama bildirimi](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-trusted-root.png)

2. Sonraki bildirim, SCEP sertifika profilini yüklemek için istemde bulunur:

    > [!div class="mx-imgBorder"]
    > SCEP sertifika profili yüklemek için Android 'de ![örnek Şirket Portalı uygulama bildirimi](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-scep-certificate.png)

    > [!TIP]
    > Cihaz Yöneticisi tarafından yönetilen bir Android cihaz kullanırken, birden fazla sertifika listelenmiş olabilir. Bir sertifika profili iptal edildiğinde veya kaldırıldığında, sertifika cihazda kalır. Bu senaryoda, en yeni sertifikayı seçin. Genellikle listede gösterilen son sertifikadır.
    >
    > Android Enterprise ve Samsung KNOX cihazlarında bu durum oluşmaz. Daha fazla bilgi için bkz. [Android iş profili cihazlarını yönetme](../enrollment/android-enterprise-overview.md) ve [SCEP ve PKCS sertifikalarını kaldırma](../protect/remove-certificates.md#android-knox-devices).

3. Ardından, kullanıcılar Wi-Fi profilini yüklemek için bir bildirim alır:

    > [!div class="mx-imgBorder"]
    > SCEP sertifika profili yüklemek için Android 'de ![örnek Şirket Portalı uygulama bildirimi](./media/troubleshoot-wi-fi-profiles/android-end-user-install-wifi-profile.png)

4. Tamamlandığında, Wi-Fi bağlantısı kayıtlı ağ olarak gösterilir:

    > [!div class="mx-imgBorder"]
    > ![Wi-Fi bağlantısı, kayıtlı ağ olarak gösterilir](./media/troubleshoot-wi-fi-profiles/android-end-user-saved-networks.png)

### <a name="review-company-portal-app-logs"></a>Şirket Portalı uygulama günlüklerini gözden geçirme

Android 'de **Omadmlog. log** dosyası, cihaza yüklendiğinde Wi-Fi profilinin etkinliklerini ayrıntılardır. En fazla beş Omadmlog günlük dosyasına sahip olabilirsiniz. Son eşitlemenin zaman damgasına sahip olduğunuzdan emin olun. Bu, ilgili günlük girdilerini bulmanıza yardımcı olacaktır.

Aşağıdaki örnekte, günlük okumak için [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace) 'i kullanın ve "wifimgr" ifadesini aratın:

> [!div class="mx-imgBorder"]
> ![Wi-Fi bağlantısı, kayıtlı ağ olarak gösterilir](./media/troubleshoot-wi-fi-profiles/android-cmtrace-filter-wifimgr.png)

Aşağıdaki günlük, arama sonuçlarınızı gösterir ve başarıyla uygulanan Wi-Fi profilini gösterir:

```log
2019-08-01T19:22:46.7340000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.7490000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:46.8100000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:46.8209999    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.8240000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected ca certificate with alias: 'user:205xxxxx.0' and thumbprint '<thumbprint>'.
2019-08-01T19:22:47.0990000    VERB    com.microsoft.omadm.platforms.android.certmgr.CertificateChainBuilder    15118    04142    Complete certificate chain built with Complete certs.
2019-08-01T19:22:47.1010000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    1 cert(s) matched criteria: User<ID>[i:<ID>,17CECEA1D337FAA7D167AD83A8CC7A8FCBF9xxxx;eku:1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2]
2019-08-01T19:22:47.1090000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    0 cert(s) excluded by criteria:
2019-08-01T19:22:47.1110000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected client cert with alias 'User<ID>' and requestId 'ModelName=<ModelName>%2FLogicalName_<LogicalName>;Hash=-912418295'.
2019-08-01T19:22:47.4120000    VERB    com.microsoft.omadm.Services    15118    04142    Successfully applied, enabled and saved wifi profile '<profile ID>'
2019-08-01T19:22:47.4240000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.4910000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.4970000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5080000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.5820000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.5900000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5910000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04142    Applied profile <profile ID>

```

## <a name="ios"></a>iOS

Wi-Fi profili cihaza yüklendikten sonra **Yönetim profilinde**gösterilir:

> [!div class="mx-imgBorder"]
> iOS cihazında yönetim profilini ![](./media/troubleshoot-wi-fi-profiles/ios-management-profile.png)

> [!div class="mx-imgBorder"]
> ![Wi-Fi bağlantısı iOS cihazında Wi-Fi ağı olarak gösterilir](./media/troubleshoot-wi-fi-profiles/ios-wifi-connection-in-management-profile.png)

### <a name="review-the-ios-console-and-device-logs"></a>İOS konsolunu ve cihaz günlüklerini gözden geçirme

İOS cihazlarında Şirket Portalı Uygulama günlüğü Wi-Fi profilleriyle ilgili bilgileri içermez. Wi-Fi profillerinizin yükleme ayrıntılarını görmek için konsol/cihaz günlüklerini kullanın:

1. İOS cihazını Mac 'e bağlayın. **Uygulamalar** > **yardımcı programlar**' a gidin ve konsol uygulamasını açın.
2. **Eylem**altında, **bilgi iletilerini dahil et** ve **hata ayıklama iletilerini içer**' i seçin:

    > [!div class="mx-imgBorder"]
    > ![bilgi Iletilerini dahil edin ve iOS konsol uygulamasına hata ayıklama Iletileri ekleyin](./media/troubleshoot-wi-fi-profiles/ios-console-app-include-info-messages-debug-messages.png)

3. Senaryoyu yeniden oluşturun ve günlükleri bir metin dosyasına kaydedin:

    1. Geçerli ekrandaki tüm iletileri seçin: **düzenle** > **Tümünü Seç**' i seçin.
    2. İletileri kopyalayın: **düzenle** > **Kopyala**.
    3. Günlük verilerini bir metin düzenleyicisine yapıştırın ve dosyayı kaydedin.

4. Ayrıntılı bilgileri görmek için kaydedilen günlük dosyasında arama yapın. Profil başarıyla yüklendiğinde, çıktılarınız aşağıdaki günlüğe benzer şekilde görünür:

    ```log
    Line 390870: debug    11:19:58.994815 -0400    profiled    Adding dependent www.windowsintune.com.wifi.Contoso to parent Microsoft.Profiles.MDM in domain ManagingProfileToManagedProfile to system\
    Line 390872: debug    11:19:58.995210 -0400    profiled    Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.wifi.Contoso in domain ManagedProfileToManagingProfile to system\
    Line 392346: default    11:19:59.360460 -0400    profiled    Profile \'93www.windowsintune.com.wifi.Contoso\'94 installed.\
    ```

## <a name="windows"></a>Windows

Wi-Fi profili cihaza yüklendikten sonra, **iş veya okula erişim** > **Ayarlar** > **hesaplar** ' a gidin. Hesap > **bilgilerinizi**seçin:

> [!div class="mx-imgBorder"]
> ![işe veya okula erişin ve Windows cihazında bilgi ' yi seçin](./media/troubleshoot-wi-fi-profiles/windows-access-work-school-info.png)

**Microsoft tarafından yönetilen alanlarda** **WiFi** gösterilmektedir:

> [!div class="mx-imgBorder"]
> Microsoft tarafından yönetilen alanlarda ![bkz. Windows 'da WiFi 'nin listelenmesi](./media/troubleshoot-wi-fi-profiles/windows-wifi-areas-managed-by-microsoft.png)

Wi-Fi bağlantısını görmek için, **ayarlar** > **ağ & Internet**  > **Wi-Fi**' a gidin:

> [!div class="mx-imgBorder"]
> Windows üzerinde ![, ayarlar bölümünde bilinen ağ olarak Wi-Fi bağlantısına bakın](./media/troubleshoot-wi-fi-profiles/windows-wifi-connection-known-networks.png)

### <a name="review-event-viewer-logs"></a>Olay Görüntüleyici günlüklerini gözden geçirme

Windows cihazlarında, Wi-Fi profilleriyle ilgili ayrıntılar Olay Görüntüleyicisi kaydedilir:

1. **Olay Görüntüleyicisi** uygulamasını açın.
2. **Görünüm** menüsünde **analitik ve hata ayıklama günlüklerini göster**' i seçin.
3. **Uygulama ve hizmet günlüklerini** genişletme > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **admin**

Çıktılarınız aşağıdaki günlüklere benzer:

```log
Log Name:      Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
Source:        Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider
Date:          8/7/2019 8:01:41 PM
Event ID:      1506
Task Category: (1)
Level:         Information
Keywords:      (2)
User:          SYSTEM
Computer:      <Computer Name>
Description:
WiFiConfigurationServiceProvider: Node set value, type: (0x4), Result: (The operation completed successfully.).
```

## <a name="common-issues"></a>Yaygın sorunlar

### <a name="issue-1-the-wi-fi-profile-isnt-deployed-to-the-device"></a>Sorun 1: Wi-Fi profili cihaza dağıtılmadı

- Wi-Fi profilinin doğru gruba atandığını onaylayın:

    1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde **cihazlar** > **yapılandırma profilleri**' ni seçin.
    2. Profilinizi > **atamaları**' nı seçin. Seçili grupların doğru olduğunu onaylayın.
    3. Uç nokta yöneticisinde, **sorun giderme + Destek**' i seçin. **Atamalar** bilgilerini gözden geçirin.

- Uç nokta yöneticisinde, **sorun giderme + Destek**' i seçin. **Son denetim** saatini denetleyerek cihazın Intune ile eşitlenebileceğine emin olun.

- Wi-Fi profili güvenilen kök ve SCEP profilleriyle bağlantılıysa, her iki profilin de cihaza dağıtıldığını onaylayın. Wi-Fi profilinin Bu profillere bağımlılığı vardır.

- Windows 10 ve daha yeni cihazlarda, MDM tanılama bilgileri günlüğünü gözden geçirin:

  1. **İş veya okula erişim** > **Ayarlar** > **hesaplar** ' a gidin.
  2. İş veya okul hesabınızın **bilgilerini**> seçin.
  3. **Ayarlar** sayfasının en altında **rapor oluştur**' u seçin.
  4. Günlük dosyalarının yolunu gösteren bir pencere açılır. **Export** (Dışarı aktar) öğesini seçin.
  5. `\Users\Public\Documents\MDMDiagnostics` yoluna gidin ve raporu görüntüleyin:

      > [!div class="mx-imgBorder"]
      > Windows 10 cihazlarında WiFi profili yapılandırmasını gösteren örnek MDM tanılama bilgilerini ![](./media/troubleshoot-wi-fi-profiles/windows-mdm-diagnostic-info.png)

  > [!TIP]
  > Daha fazla bilgi için bkz. [Windows 10 ' da MDM başarısızlıklarını tanılama](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).

- Android cihazlarda, güvenilir kök ve SCEP profilleri cihazda yüklü değilse, Şirket Portalı App Omadmlog dosyasında aşağıdaki girişi görürsünüz:

  ``` log
  2019-08-01T19:18:13.5120000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04105    Skipping Wifi profile <profile ID> because it is pending certificates.
  ```

  - Güvenilen kök ve SCEP profilleri, Android cihazındaki ve uyumlu olduğunda, Wi-Fi profili cihazda bulunmayabilir. Bu sorun, Şirket Portalı uygulamadan **Certificateselector** sağlayıcısı belirtilen ölçütlerle eşleşen bir sertifika bulmazsa oluşur. Belirli ölçütler sertifika şablonunda veya SCEP profilinde olabilir.

    Eşleşen sertifika bulunamazsa cihazdaki sertifikalar yüklenmez. Wi-Fi profili doğru sertifikaya sahip olmadığından uygulanmadı. Bu senaryoda, Şirket Portalı App Omadmlog dosyasında aşağıdaki girişi görürsünüz:

    ` Skipping Wifi profile <profile ID> because it is pending certificates.`

    Aşağıdaki örnek günlük, **herhangi bir amaç** genişletilmiş anahtar kullanımı (EKU) ölçütü belirtildiğinden, dışlanan sertifikaları gösterir. Ancak, cihaza atanan sertifikaların EKU 'SU yoktur:

    ```log
    2018-11-27T21:10:37.6390000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID1> and requestId <requestID1> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID2> and requestId <requestID2> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    0 cert(s) matched criteria:
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    2 cert(s) excluded by criteria:
    2018-11-27T21:10:37.6400000    INFO       com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager       14210                00948     Skipping Wifi profile <profile ID> because it is pending certificates.
    ```

    Aşağıdaki örnek, **herhangi bir amaç** EKU 'su IÇIN girilen SCEP profilini gösterir. Ancak, sertifika yetkilisinde (CA) sertifika şablonuna girilmemiş. Sorunu giderecek **bir amaç** seçeneğini sertifika şablonuna ekleyin. Ya da SCEP profilinden **herhangi bir amaç** seçeneğini kaldırın.

    > [!div class="mx-imgBorder"]
    > Android 'de ![, sertifika yetkilisinde sertifika şablonuna herhangi bir amaç ekleyin](./media/troubleshoot-wi-fi-profiles/android-add-any-purpose-eku.png)

    > [!div class="mx-imgBorder"]
    > Android 'de ![Intune 'daki SCEP sertifika yapılandırma profiline herhangi bir amaç ekleyin](./media/troubleshoot-wi-fi-profiles/android-any-purpose-scep-device-config-profile.png)

  - Tüm sertifika zincirindeki tüm gerekli sertifikaların Android cihazında olduğunu onaylayın. Aksi halde, Wi-Fi profili cihaza yüklenemez. Daha fazla bilgi için bkz. [ara sertifika yetkilisi eksik](https://developer.android.com/training/articles/security-ssl#MissingCa) (Android 'in Web sitesini açar).
  - Wi-Fi profilinde kullanılan sertifika ve profil başarıyla uygulanmışsa gibi bilgileri aramak için Omadmlog anahtar sözcükleriyle filtreleyin.

    Örneğin, günlükleri okumak için [CMTrace](https://docs.microsoft.com/sccm/core/support/cmtrace) ' i kullanın. "Wifimgr" filtrelemek için arama dizesini kullanın:

    > [!div class="mx-imgBorder"]
    > Android cihazlarda WiFiMgr yapılandırma profillerini aramak için CMTrace 'e filtre ![](./media/troubleshoot-wi-fi-profiles/cmtrace-filter-wifimgr.png)

    Çıktı aşağıdaki günlüğe benzer şekilde görünür:

    > [!div class="mx-imgBorder"]
    > ![, WiFi Intune yapılandırma profilinin cihazlara başarıyla uygulandığını gösteren örnek CMTrace günlük çıkışı](./media/troubleshoot-wi-fi-profiles/cmtrace-sample-log-output.png)

    Günlükte bir hata görürseniz hatanın zaman damgasını kopyalayın ve günlüğün filtresini kaldırın. Ardından, hatadan önce ne olduğunu görmek için zaman damgasıyla birlikte "bul" seçeneğini kullanın.

### <a name="issue-2-the-wi-fi-profile-is-deployed-to-the-device-but-the-device-cant-connect-to-the-network"></a>Sorun 2: Wi-Fi profili cihaza dağıtıldı, ancak cihaz ağa bağlanamıyor

Genellikle, bu soruna Intune dışından bir şey neden olur. Aşağıdaki görevler, bağlantı sorunlarını anlamanıza ve gidermenize yardımcı olabilir:

- Wi-Fi profilinde aynı ölçütlere sahip bir sertifika kullanarak ağa el ile bağlanın.

  Bağlantı kurmak için, el ile yapılan bağlantıda sertifika özelliklerine bakın. Daha sonra, Intune Wi-Fi profilini aynı sertifika özellikleriyle güncelleştirin.
- Bağlantı hataları genellikle RADIUS sunucu günlüğüne kaydedilir. Örneğin, cihazın Wi-Fi profiliyle bağlanmayı deneyip denemesinin denendiğinden, gösterilmesi gerekir.

## <a name="need-more-help"></a>Daha fazla yardım gerekiyor

- [Intune kullanıcı forumlarını](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc) kullanın veya [Microsoft 'tan destek alın](../fundamentals/get-support.md).

- Microsoft Intune 'daki Wi-Fi profilleri hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

  - [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md)ve [Windows 10 ve üzeri](wi-fi-settings-windows.md)çalıştıran cihazlar için Wi-Fi ayarlarını ekleyin.
  - [Destek Ipucu-Intune 'da SCEP sertifika dağıtımları için NDES 'yi yapılandırma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-How-to-configure-NDES-for-SCEP-certificate/ba-p/455125)
  - [SCEP sertifika profili dağıtımı](https://support.microsoft.com/help/4526725/troubleshooting-scep-profile-deployment-to-android-devices-in-intune) ve [NDES yapılandırması](https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune)sorunlarını giderin.

- En son haberler, bilgiler ve teknik ipuçları için resmi bloglara bakın:
  - [Microsoft Intune destek ekibi blogu](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
  - [Microsoft Enterprise Mobility ve Security blogu](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/bg-p/enterprisemobilityandsecurity)

## <a name="next-steps"></a>Sonraki adımlar

[Profillerinizi izleyin](device-profile-monitor.md).
