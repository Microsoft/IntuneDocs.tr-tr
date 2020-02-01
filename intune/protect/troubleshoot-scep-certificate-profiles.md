---
title: Microsoft Intune ile sertifika sağlamak için SCEP Sertifika profillerinin kullanımıyla ilgili sorunları giderin | Microsoft Docs
description: Cihazlarla NDES, sertifika yetkililerine NDES ve Intune sertifika bağlayıcısından Intune hizmetine yönelik iletişim dahil olmak üzere Intune ile birlikte kullanmak üzere sertifika istemek için, cihazların SCEP kullanımını giderin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae7ffe5a8c20aa7edd67853ff86ef9e28cf2d175
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76913182"
---
# <a name="overview-for-troubleshooting-scep-certificate-profiles-with-microsoft-intune"></a>Microsoft Intune ile SCEP sertifika profillerinde sorun gidermeye genel bakış

Basit Sertifika Kayıt Protokolü (SCEP) Sertifika profillerinin kullanılması, Intune 'da sorun giderme zor olabilir. Bu makalede, sorunları çözmenize yardımcı olabilecek bir genel bakış sunulmaktadır:

- SCEP işleminin mimarisini ve iletişim akışını açıklayan
- Bu iletişim akışında bir sorun olduğunu daraltmanıza yardımcı olma
- Sertifika profillerinin sorunlarını gidermeye yönelik sonraki makalelerde başvurulan anahtar günlük dosyalarını tanımlama

Bu ve ilgili SCEP sertifikası sorunlarını giderme makalelerinde bulunan bilgiler, Android, iOS/iPad ve Windows cihazlarıyla SCEP sertifika profillerini kullanma için geçerlidir. MacOS için benzer bilgiler şu anda kullanılamıyor.

Ağ cihazı kayıt hizmeti (NDES) sorunlarını gidermek için, support.microsoft.com adresinden aşağıdaki makalelere bakın:

- [Intune 'da SCEP sertifikaları için şirket içinde NDES yapılandırmasını doğrulama](https://support.microsoft.com/help/4490130/ndes-configuration-on-premises-for-scep-certificates-in-intune)
- [Microsoft Intune sertifika profilleriyle kullanılmak üzere NDES yapılandırması sorunlarını giderme]( https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune)

Devam etmeden önce, güvenilir bir sertifika profili aracılığıyla kök sertifika dağıtımı dahil olmak üzere [SCEP sertifika profillerini kullanma önkoşullarını](certificates-scep-configure.md#prerequisites-for-using-scep-for-certificates)karşıladığınızdan emin olun.

## <a name="scep-communication-flow-overview"></a>SCEP iletişim akışına genel bakış

Aşağıdaki grafikte, Intune 'daki SCEP iletişim işlemine temel bir genel bakış gösterilmektedir.

![SCEP sertifika profili akışı](../protect/media/troubleshoot-scep-certificate-profiles/scep-certificate-profile-flow.png)

1. [BIR SCEP sertifika profili dağıtın](troubleshoot-scep-certificate-profile-deployment.md). Intune, belirli bir Kullanıcı, sertifika amacı ve sertifika türü gerektiren bir sınama dizesi oluşturur.

2. [CIHAZDAN NDES sunucusuna iletişim](troubleshoot-scep-certificate-device-to-ndes.md). Cihaz, bir Challenge sunabilmesi için NDES 'in URL 'sini, NDES sunucusuyla iletişim kurmak için kullanır.

3. [İlke modülü Iletişimine NDES](troubleshoot-scep-certificate-ndes-policy-module.md). NDES, testi sunucuda Intune sertifika Bağlayıcısı ilke modülüne iletir ve isteği doğrular.

4. [Sertifika yetkilisine NDES](troubleshoot-scep-certificate-ndes-policy-module.md). NDES, sertifika yetkilisine (CA) bir sertifika vermek için geçerli istekleri geçirir.

5. [Cihaza sertifika teslimi](troubleshoot-scep-certificate-delivery.md). Sertifika cihaza teslim edilir.

6. [Intune 'a dağıtım raporlaması](troubleshoot-scep-certificate-reporting.md). Intune sertifika Bağlayıcısı, sertifika verme olayını Intune 'a bildirir.

## <a name="log-files"></a>Günlük dosyaları

İletişim ve sertifika sağlama iş akışı sorunlarını belirlemek için, hem sunucu altyapısından hem de cihazlardan günlük dosyalarını gözden geçirin. SCEP Sertifika profillerinin sorunlarını gidermeye yönelik sonraki bölümler, bu bölümde başvurulan günlük dosyalarına başvurur.

- [Altyapı ve sunucu günlükleri](#logs-for-on-premises-infrastructure)

Cihaz günlükleri cihaz platformuna bağlıdır:  

- [iOS ve ıpados](#logs-for-ios-and-ipados-devices)
- [Outlook Web Access (OWA)](#logs-for-android-devices)
- [Windows](#logs-for-windows-devices)

### <a name="logs-for-on-premises-infrastructure"></a>Şirket içi altyapı günlükleri
  
Sertifika dağıtımları için SCEP Sertifika profillerinin kullanımını destekleyen şirket içi altyapı Microsoft Intune Sertifika Bağlayıcısı, bir Windows Server üzerinde çalışan NDES ve sertifika yetkilisini içerir.

Bu roller için günlük dosyaları, Windows Olay Görüntüleyicisi, sertifika konsollarının yanı sıra Intune sertifika Bağlayıcısı, NDES veya şirket içi altyapının parçası olan diğer rol ve işlemlere özgü çeşitli günlük dosyaları içerir.

Aşağıdaki listede, sonraki SCEP sorun giderme makalelerinde başvurulan Günlükler veya konsollar yer almaktadır. 

- **NDESConnector_date_time. svclog**:

  Bu günlük Microsoft Intune Sertifika Bağlayıcısı ile Intune bulut hizmeti arasındaki iletişimi gösterir. Bu günlük dosyasını görüntülemek için [hizmet Izleme Görüntüleyicisi aracını](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) kullanabilirsiniz.

  İlgili kayıt defteri anahtarı: *Hklm\sw\microsoft\microsofıntune\ndesconnector\connectionstatus*

  Konum: NDES 'Yi barındıran sunucuda *% Program_Files% \ Microsoft ıntune\ndesconnectorsvc\logs\logs*

- **CertificateRegistrationPoint_date_time. svclog**:

  Bu günlük, sertifika isteklerini alıp doğrulayan NDES ilke modülünü gösterir. Bu günlük dosyasını görüntülemek için [hizmet Izleme Görüntüleyicisi aracını](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) kullanabilirsiniz.

  Konum: NDES 'Yi barındıran sunucuda *% Program_Files% \ Microsoft ıntune\ndesconnectorsvc\logs\logs*

- **NDESPlugin. log**:

  Bu günlük, sertifika isteklerinin sertifika kayıt noktasına geçişini ve bu isteklerin sonuçtaki doğrulanmasını gösterir.

  Konum: NDES 'Yi barındıran sunucuda *% Program_Files% \ Microsoft Intune\NDESPolicyModule\logs*

- **IIS günlükleri**:

  IIS günlükleri NDES 'yi girerek mobil cihazlardan gelen sertifika isteklerini gösterir.

  Konum: *C:\inetpub\logs\LogFiles\W3SVC1* ' de NDES 'yi barındıran sunucuda

- **Windows uygulama günlüğü**:

  Bu günlük, SCEP uygulama havuzu gibi IIS sorunlarını araştırırken faydalıdır.

  Konum: NDES 'yi barındıran sunucuda: Windows Olay Görüntüleyicisi açmak için **eventvwr. msc** dosyasını çalıştırın




### <a name="logs-for-android-devices"></a>Android cihazları için Günlükler

Android çalıştıran cihazlar için **android Şirket portalı** app günlük dosyası **OMADM. log**dosyasını kullanın. Günlükleri toplamadan ve gözden geçirebilmeniz için, [ayrıntılı günlük kaydının](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android.md) etkinleştirildiğinden emin olun ve ardından sorunu yeniden oluşturun.

Bir cihazdan OMADM. logs toplamak için bkz. [USB kablosu kullanarak karşıya yükleme ve e-posta günlükleri](/intune-user-help/send-logs-to-your-it-admin-using-cable-android.md).

Ayrıca, destek için [e-posta günlükleri de yükleyebilir](/intune-user-help/send-logs-to-your-it-admin-by-email-android.md#upload-and-email-logs-from-microsoft-intune-app) .

### <a name="logs-for-ios-and-ipados-devices"></a>İOS ve ıpados cihazları için Günlükler

İOS veya ıpados çalıştıran cihazlarda, bir Mac bilgisayarda çalışan hata ayıklama günlükleri ve **Xcode** kullanın:

1. İOS cihazını Mac 'e bağlayın ve ardından **uygulamalar** > **yardımcı programlar** ' a giderek konsol uygulamasını açın. 

2. **Eylem**altında, **bilgi Iletilerini Içer** ve **hata ayıklama iletilerini içer**' i seçin.

   ![Günlük seçeneklerini seçin](../protect/media/troubleshoot-scep-certificate-profiles/message-options.png)

3. Sorunu yeniden oluşturun ve sonra günlükleri bir metin dosyasına kaydedin:
   1. **Düzenle** > Seç ' i seçin ve geçerli ekrandaki tüm iletileri seçmek Için **Tümünü Seç** ' **i seçin ve** ardından iletileri panoya kopyalamak için > **Kopyala** ' yı seçin. 
   2. TextEdit uygulamasını açın, kopyalanmış günlükleri yeni bir metin dosyasına yapıştırın ve dosyayı kaydedin.


İOS ve ıpados cihazlarının Şirket Portalı günlüğü, SCEP sertifika profilleri hakkında bilgi içermez.

### <a name="logs-for-windows-devices"></a>Windows cihazları için Günlükler

Windows çalıştıran cihazlarda, Intune ile yönettiğiniz cihazların kayıt veya cihaz yönetimi sorunlarını tanılamak için Windows olay günlüklerini kullanın.

Cihazda **Olay Görüntüleyicisi** > **uygulama ve hizmet günlükleri** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** ' ı açın.

![Windows olay günlükleri](../protect/media/troubleshoot-scep-certificate-profiles/windows-event-log.png)

## <a name="next-steps"></a>Sonraki adımlar

[SCEP Sertifika profillerinin dağıtımını](troubleshoot-scep-certificate-profile-deployment.md) gözden geçirme 
