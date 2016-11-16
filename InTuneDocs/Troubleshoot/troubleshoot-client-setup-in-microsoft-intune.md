---
title: "İstemci kurulumu sorunlarını giderme | Microsoft Intune"
description: "Sık karşılaşılan istemci kurulumu sorunlarını giderin."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 08/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 889a13bd50943b9cdf0f40d50b6f8ce263dde56d
ms.openlocfilehash: e37b5da81150f89fce1ee3d57bd84de0ff7fb76f


---

# <a name="troubleshoot-client-setup-in-microsoft-intune"></a>Microsoft Intune’da istemci kurulumu sorunlarını giderme
Sık karşılaşılan istemci kurulum sorunlarını gidermenize yardımcı olması için aşağıdaki bilgileri kullanın. Bu bilgiler sorununuzu çözmezse, yardım almanın daha fazla yolunu öğrenmek için bkz. [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md).

## <a name="client-installation-fails"></a>İstemci yüklemesi başarısız oldu

-   [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) bilgisayar için hiç istemci yazılım dağıtımı uyarısı görüntülemezse, bilgisayarın İnternet bağlantısı ve proxy yapılandırmasını denetleyin, ayrıca bilgisayarın hizmet URL'si ([https://manage.microsoft.com](https://manage.microsoft.com/)) ile iletişim kurabildiğinden emin olun. Ardından İstemci yazılımını yüklemeyi yeniden deneyin.

-    **Yönetici** çalışma alanında bir bildirim kuralı yapılandırarak bir istemci yazılımı dağıtım hatası oluşursa seçili alıcılara bir e-posta gönderilmesini sağlayabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune Uyarıları ile bilgi edinin](/intune/deploy-use/get-notified-by-alerts).

-   İstemci yazılımı dağıtılamazsa, Intune **İstemci Yazılımı Dağıtım Hatası** kritik uyarısını gösterir. Bu uyarı, [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Sisteme Genel Bakış** sayfası ve **Uyarılar** sayfalarında gösterilir. Uyarılar şöyle denetlenir:

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Uyarılar** &gt; **Genel Bakış**’ı seçin.

2.   **Uyarılar genel bakış** sayfasında, aşağıdaki bilgileri gözden geçirebilirsiniz:

    -   Tarih, kategori veya öneme göre sıralanabilen ilk üç uyarı

    -   Toplam etkin uyarı sayısı

3.  **Uyarılar** sayfasında aşağıdaki bilgileri görüntülemek için **Tüm Uyarılar**'ı seçin. Kritik uyarılar önce görüntülenir:

    -   **Ad** – Uyarıyı üreten uyarı türünün adı.

    -   **Kaynak** – Uyarının kaynağına ait bir bağlantı.  Uyarı türünün görüntüleme eşiği **Tümü**olarak ayarlanırsa, bu bağlantı etkilenen tek bir cihazı gösterir.  Uyarı türünün görüntüleme eşiği bir değer olarak ayarlanırsa, bu bağlantı bu uyarıdan etkilenen tüm cihazların bir listesini gösterir.

    -   **Son Güncelleştirme** – Bu, uyarının son değiştirilme zamanı belirtir. Bir uyarı kapatıldıysa, uyarının kapatıldığı zaman görüntülenir.

    -   **Önem** – Uyarının önemini gösterir

## <a name="computer-enrollment-package-doesnt-download"></a>Bilgisayar kayıt paketi indirilmedi
**Sorun:** Bilgisayarı kaydetmeyi denerken aşağıdaki durumla karşılaştınız:
-  Kayıt paketi indirilemedi
-  İndirme iletişim kutusu görüntüleniyor ancak zaman aşımına uğruyor

**Çözüm:** İndirme işleminde kullandığınız tarayıcıda, indirme süresi için indirme işlemlerinin etkinleştirildiğinden ve şifrelenmiş dosyaların yerel diskinize kaydedilebildiğinden emin olun.

## <a name="client-installation-hangs-with-error-code-0x80040154"></a>İstemci yüklemesi 0x80040154 hata koduyla kilitleniyor
**Sorun:**

-  İstemci yüklemesi kayıt sırasında kilitleniyor

-  Cihaz kaydedilemiyor

-  WindowsUpdate.log dosyasında 0x80040154 hatası

Bilgisayarda kritik yazılım güncelleştirmelerinin eksik olması buna neden olabilir.

**Çözüm:** [Microsoft Intune'da yazılım güncelleştirmeleriyle Windows bilgisayarlarını güncel tutun](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune) konu başlığı altında açıklandığı gibi, yazılım güncelleştirme ilkenizin kritik güncelleştirmelerin yüklenmesine olanak tanıdığından emin olun.


## <a name="microsoft-intune-policyrelated-errors-in-policyplatformlog"></a>policyplatform.log dosyasındaki Microsoft Intune ilkesiyle ilgili hatalar
MDM olmayan Windows cihazları için policyplatform.log dosyasındaki ilke hataları cihazdaki Windows Kullanıcı Hesabı Denetimi’nde (UAC) bulunan varsayılan olmayan ayarların sonucu olabilir. Varsayılan olmayan bazı UAC ayarları Microsoft Intune istemci yüklemelerini ve ilke yürütmesini etkileyebilir.

### <a name="to-resolve-uac-issues"></a>UAC sorunlarını çözmek için

1.  [Verileri ve cihazları Microsoft Intune yönetiminde kullanımdan kaldırma](/intune/deploy-use/retire-devices-from-microsoft-intune-management) konu başlığı altında açıklandığı gibi bilgisayarı devre dışı bırakın.

2.  İstemci yazılımının kaldırılması için 20 dakika bekleyin.

    > [!NOTE]
    > İstemciyi Programlar ve Özellikler menüsünden kaldırmaya çalışmayın.

3.  Başlat menüsünde **UAC** yazarak Kullanıcı Hesabı Denetimi ayarlarını açın.

4.  Bildirim kaydırıcısını varsayılan ayara getirin.

## <a name="what-to-do-if-the-client-will-not-uninstall-from-the-microsoft-intune-administrator-console"></a>İstemci Microsoft Intune yönetici konsolundan kaldırılamazsa yapmanız gerekenler

### <a name="to-remove-the-client-software-by-using-the-microsoft-intune-command-line-tool"></a>İstemci yazılımını Microsoft Intune komut satırı aracını kullanarak kaldırma

1.  Yönetici modunda bir komut istemi açın.

2.  *%programfiles%\Microsoft\OnlineManagement\Common* klasörüne gidin

3.  Şu komutu çalıştırın: ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## <a name="client-installation-error-codes"></a>İstemci yüklemesi hata kodları
Aşağıdaki tabloda istemci yazılımı yüklemesi başarısız olursa **Uyarılar** 'da görüntülenecek hata kodları açıklanmaktadır. Her hata kodunun temsil ettiği sorunu çözmek için öneriler içerir.

|Hata kodu|Olası sorun|Önerilen çözüm|
|--------------|--------------------|------------------------|
|**0x80CF0437**|İstemci bilgisayarındaki saat doğru zamana ayarlanmadı.|İstemci bilgisayardaki saat ve saat diliminin doğru saat ve saat dilimine ayarlandığından emin olun.|
|**0x80240438**, **0x80CF0438**, **0x80CF401B**|Intune hizmetine bağlanılamıyor. İstemci proxy ayarlarını kontrol edin.|İstemci bilgisayardaki proxy ayarlarının Intune tarafından desteklendiğinden ve istemci bilgisayarın İnternet erişimi olduğundan emin olun. Desteklenen proxy yapılandırmaları hakkında daha fazla bilgi için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80CF402C**|Intune hizmetine bağlanılamıyor. Ağ bağlantısını denetleyin.|Bilgisayarın ağ bağlantısı olduğunu doğrulayın. Ağ kablosunun bağlı olduğundan veya kablosuz ağın açık olduğundan emin olun.|
|**0x80240438, 0x80CF0438**|Internet Explorer ve Yerel Sistem proxy ayarları yapılandırılmadı.|İstemci proxy ayarlarını denetleyin ve istemci bilgisayardaki proxy yapılandırmasının Intune tarafından desteklendiğinden ve istemci bilgisayarın İnternet erişimi olduğundan emin olun. Desteklenen proxy yapılandırmaları hakkında daha fazla bilgi için bkz. [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).|
|**0x80043001**|Kayıt paketi güncel değil.| **Yönetici** çalışma alanından güncel istemci yazılımı paketini indirin ve yükleyin. Yönergeler için [Microsoft Intune ile Windows bilgisayar istemcisini yükleme](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune) konusuna bakın.|
|**0x80043004**|Abonelik yok veya devre dışı bırakıldı.|Hesabınızın ve Intune aboneliğinizin hala etkin olduğunu doğrulayın. Hesap ayarlarınızı görüntülemek için [Office 365 yönetici merkezi](http://go.microsoft.com/fwlink/?LinkId=698854%20) hesabınızda oturum açın.|
|**0x80043002**|Hesap bakım modunda.|Hesap bakım modunda olduğunda yeni istemci bilgisayarlar kaydedilemez. Hesap ayarlarınızı görüntülemek için [Office 365 yönetici merkezi](http://go.microsoft.com/fwlink/?LinkId=698854%20) hesabınızda oturum açın.|
|**0x80043003**|Hesap silindi.|Hesabınızın ve Intune aboneliğinizin hala etkin olduğunu doğrulayın. Hesap ayarlarınızı görüntülemek için hesabınızda oturum açın.|
|**0x80043005**|İstemci bilgisayar devre dışı.|Birkaç saat bekleyin, bilgisayardan istemci yazılımının daha eski sürümlerini kaldırın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin. Yönergeler için yukarıdaki **İstemci Microsoft Intune yönetici konsolundan kaldırılamazsa yapmanız gerekenler** bölümüne bakın.|
|**0x80043006**|Hesap için izin verilen maksimum bilgisayar lisansı sayısına ulaşıldı.|Kuruluşunuzun hizmete daha fazla istemci bilgisayar kaydedebilmek için ek bilgisayar lisansları satın alması gerekir.|
|**0x80043007**|Yükleyici programla aynı klasörde sertifika dosyası bulunamadı.|Yüklemeyi başlatmadan önce tüm dosyaları ayıklayın. Ayıklanan dosyaları yeniden adlandırmayın veya yerini değiştirmeyin: tüm dosyalar aynı klasörde bulunmalıdır; aksi takdirde yükleme başarısız olur. Daha fazla bilgi için bkz. [Microsoft Intune ile Windows bilgisayar istemcisini yükleme](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).|
|**0x8024D015**, **0x00240005**, **0x80070BC2**, **0x80070BC9**, **0x80CFD015**|İstemci bilgisayarın yeniden başlatılması beklendiğinden yazılım yüklenemiyor.|Bilgisayarı yeniden başlatın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|**0x80070032**|İstemci yazılımını yüklemek için bir veya daha fazla önkoşul istemci bilgisayarda bulunamadı.|Gerekli tüm güncelleştirmelerin istemci bilgisayarda yüklü olduğundan emin olun ve ardından istemci yazılımı yükleme işlemini yeniden deneyin. İstemci yazılımını yükleme önkoşulları hakkında daha fazla bilgi için bkz. [Microsoft Intune için ağ altyapısı gereksinimleri](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0x80043008**|Microsoft Online Yönetim Güncelleştirmeleri hizmeti başlatılamadı.|[Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Destek ile iletişim kurun.|
|**0x80043009**|İstemci bilgisayar hizmete zaten kayıtlı.|İstemci bilgisayarı bu hizmete yeniden kaydetmek için önce devre dışı bırakmanız gerekir. Yönergeler için bkz. [Microsoft Intune yönetiminden cihazları devre dışı bırakma](/intune/deploy-use/retire-devices-from-microsoft-intune-management).|
|**0x8004300B**|İstemci üzerinde çalışan Windows sürümü desteklenmediğinden, istemci yazılımı yükleme paketi çalıştırılamıyor.|Intune istemci bilgisayarda çalışan Windows sürümünü desteklemiyor. Desteklenen işletim sistemlerinin listesi için bkz. [Microsoft Intune için ağ altyapısı gereksinimleri](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune).|
|**0xAB2**|Windows Installer özel bir işlem için VBScript çalışma zamanına erişemedi.|Bu hata Dinamik Bağlantı Kitaplıkları'nı (DLLs) temel alan özel bir işlemden kaynaklanır. DLL sorunlarını giderirken, [Microsoft Desteği KB198038: Paket ve Dağıtım Sorunlarında Yararlı Araçlar](http://go.microsoft.com/fwlink/?LinkID=234255) makalesinde açıklanan araçları kullanmanız gerekebilir.|
|**0x8004300f**|System Center Configuration Manager istemcisi zaten yüklü olduğundan yazılım yüklenemiyor.|Configuration Manager istemcisini kaldırın ve ardından istemci yazılımı yükleme işlemini yeniden deneyin.|
|**0x80043010**|Open Mobile Alliance Device Management (OMADM) istemcisi zaten yüklü olduğundan bu yazılım yüklenemiyor.|OMADM istemcisinin kaydını kaldırın ve ardından istemci yazılımı yüklemesini yeniden deneyin.|
Yükleme sorunu devam ediyorsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Destek ile iletişim kurun. Destek mühendislerine göstermek için istemci bilgisayar kayıt günlüğü (%*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log ve %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollement.log konumlarında bulunur) ve Windows Update günlüğünü (%*windir*%\windowsupdate.log) hazır bulundurun.

### <a name="next-steps"></a>Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Nov16_HO1-->


