---
title: Uygulama yükleme sorunlarını giderme
titleSuffix: Microsoft Intune
description: Uygulama yükleme sorunlarını gidermenize yardımcı olması için Microsoft Intune sorun giderme bölmesini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be66f99006b06dce9f9bfe21eafa9f2be302e7b9
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540988"
---
# <a name="troubleshoot-app-installation-issues"></a>Uygulama yükleme sorunlarını giderme

Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Microsoft Intune, kullanıcı yardım isteklerini ele almak yardım masası operatörleri ve Intune yöneticilerinin uygulama bilgilerini görüntülemek için uygulama yükleme hatası ayrıntıları sağlar. Intune içindeki sorun giderme bölmesi, kullanıcının cihazında yönetilen uygulamalar dahil hata ayrıntılarını sağlar. Bir uygulamanın uçtan uca yaşam döngüsü hakkındaki ayrıntıları, **Yönetilen Uygulamalar** bölmesinde her bir cihaz altında sağlanır. Uygulamanın ne zaman yüklendiği, değiştirildiği, hedeflendiği ve bir cihaza teslim edildiği gibi yükleme sorunlarını görüntüleyebilirsiniz. 

> [!NOTE]
> Belirli uygulama yüklemesi hata kodu bilgileri için bkz. [Intune uygulama yükleme hatası başvurusu](~/apps/app-install-error-codes.md).

## <a name="app-troubleshooting-details"></a>Uygulama sorunlarını giderme ayrıntıları

Intune, belirli bir kullanıcının cihazında yüklü uygulamalar temelinde sorun giderme ayrıntıları sağlar.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Sorun gider + destek**' i seçin.
4. Sorun gidermek üzere bir kullanıcı belirlemek için **Seçin**’e tıklayın. **Seçili kullanıcılar** bölmesi görüntülenir.
5. Adını veya e-posta adresini yazarak bir kullanıcı seçin. Bölmenin altındaki **Seçin**’e tıklayın. Kullanıcı için sorun giderme bilgileri, **Sorun Giderme** bölmesinde görüntülenir. 
6. **Cihazlar** listesinden sorun gidermek istediğiniz cihazı seçin.
    ![Intune Sorun Giderme bölmesi.](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. Seçili cihaz bölmesinden **Yönetilen Uygulamalar**’ı seçin. Yönetilen uygulamaların bir listesi görüntülenir.
    ![Intune tarafından yönetilen belirli bir cihazın ayrıntıları.](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. Listeden **Yükleme Durumu**’nun hata gösterdiği bir uygulamayı seçin.
    ![Yükleme hatası ayrıntıları gösteren seçili bir uygulama.](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > Aynı uygulama, birden çok gruba atanabilir ancak uygulama için amaçlanan farklı eylemleri (amaçları) olmalıdır. Örneğin uygulama ataması sırasında bir kullanıcı için uygulama dışlandıysa uygulama için çözümlenen amaç **dışlandı** olarak görüntülenecektir. Daha fazla bilgi için bkz. [Uygulama amaçları arasındaki çakışmalar nasıl çözümlenir](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Gerekli bir uygulama için yükleme hatası oluşursa siz veya yardım masanız tarafından cihaz eşitlenebilir ve uygulama yüklemesi yeniden denenebilir.

Uygulama yükleme hatası ayrıntıları, sorunu gösterecektir. Sorunu çözmek için yapılacak en iyi eylemi belirlemek üzere bu ayrıntıları kullanabilirsiniz. Uygulama yükleme sorunlarını giderme hakkında daha fazla bilgi için bkz. [Android uygulama yükleme hataları](app-install-error-codes.md#android-app-installation-errors) ve [iOS uygulama yükleme hataları](app-install-error-codes.md#ios-app-installation-errors).

> [!Note]  
> **Sorun giderme** bölmesine tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Kullanıcı grubu hedeflenen uygulama yüklemesi cihaza ulaşmıyor
Uygulamaları yüklerken sorun yaşadığınızda aşağıdaki eylemler göz önünde bulundurulmalıdır:
- Uygulama Şirket Portalı görünmüyorsa, uygulamanın **kullanılabilir** amaç ile dağıtıldığından ve kullanıcının, uygulama tarafından desteklenen cihaz türüyle Şirket portalı eriştiğinden emin olun.
- Windows BYOD cihazlarında, kullanıcının cihaza bir Iş hesabı eklemesi gerekir.
- Kullanıcının AAD cihaz sınırının üzerinde olup olmadığını denetleyin:
  1. [Azure Active Directory cihaz ayarları](https://portal.azure.com/#pane/Microsoft_AAD_IAM/DevicesMenupane/DeviceSettings/menuId)' na gidin.
  2. **Kullanıcı başına en fazla cihaz**için ayarlanan değeri unutmayın.
  3. [Azure Active Directory kullanıcılara](https://portal.azure.com/#pane/Microsoft_AAD_IAM/UsersManagementMenupane/AllUsers)gidin.
  4. Etkilenen kullanıcıyı seçin ve **cihazlar**' a tıklayın.
  5. Kullanıcı ayarlanan sınırın üzerinde ise artık gerekli olmayan eski kayıtları silin.
- İOS DEP cihazları için, kullanıcının Intune cihazına genel bakış bölmesinde **Kullanıcı tarafından kaydedilmiş** olarak listelendiğinden emin olun. Varsa, Intune Şirket Portalı için bir yapılandırma ilkesi dağıtın. Daha fazla bilgi için bkz. [Şirket Portalı uygulamasını yapılandırma](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices).

## <a name="win32-app-installation-troubleshooting"></a>Win32 uygulaması yükleme sorunlarını giderme

Intune yönetim uzantısı kullanılarak dağıtılan Win32 uygulamasını seçin. Win32 uygulamanızın yüklemesi başarısız olduğunda **günlükleri topla** seçeneğini belirleyebilirsiniz. 

> [!IMPORTANT]
> Win32 uygulaması cihaza başarıyla yüklendiğinde **günlükleri topla** seçeneği etkinleştirilmeyecektir.<p>Win32 uygulama günlüğü bilgilerini toplayabilmeniz için önce Intune yönetim uzantısının Windows istemcisinde yüklü olması gerekir. Bir PowerShell betiği veya bir Win32 uygulaması bir kullanıcı veya cihaz güvenlik grubuna dağıtıldığında, Intune yönetim uzantısı yüklenir. Daha fazla bilgi için bkz. [Intune yönetim uzantısı-Önkoşullar](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Günlük dosyası topla

Win32 uygulama yükleme günlüklerinizi toplamak için öncelikle [uygulama sorun giderme ayrıntıları](troubleshoot-app-install.md#app-troubleshooting-details)bölümünde belirtilen adımları izleyin. Ardından, aşağıdaki adımlarla devam edin:

1. **Yükleme ayrıntıları** bölmesindeki **günlükleri topla** seçeneğine tıklayın.

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. Günlük dosyası toplama işlemini başlatmak için günlük dosyası adlarıyla dosya yolları sağlayın ve **Tamam**' a tıklayın.

    > [!NOTE]
    > Günlük toplama, iki saatten daha az sürer. Desteklenen dosya türleri: *. log,. txt,. dmp,. cab,. zip,. xml,. evtx ve. evtl*. En fazla 25 dosya yoluna izin verilir.

3. Günlük dosyaları toplandıktan sonra günlük dosyalarını indirmek için **Günlükler** bağlantısını seçebilirsiniz.

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Uygulama günlüğü koleksiyonunun başarısını belirten bir bildirim görüntülenir.

#### <a name="win32-log-collection-requirements"></a>Win32 günlük toplama gereksinimleri

Günlük dosyalarını toplamak için izlenmesi gereken belirli gereksinimler vardır:

- Günlük dosyası yolunun tamamını belirtmeniz gerekir. 
- Günlük toplama için aşağıdaki gibi ortam değişkenlerini belirtebilirsiniz:<br>
  *% PROGRAMFILES%,% PROGRAMDATA%% PUBLIC%,% WINDIR%,% TEMP%,% TMP%*
- Yalnızca tam dosya uzantılarına izin verilir, örneğin:<br>
  *. log,. txt,. dmp,. cab,. zip,. xml*
- Karşıya yüklenecek en fazla günlük dosyası 60 MB veya 25 dosya, hangisi önce gerçekleşir. 
- Win32 uygulama yükleme günlüğü koleksiyonu, gerekli, kullanılabilir ve kaldırma uygulama atama hedefini karşılayan uygulamalar için etkinleştirilir.
- Saklanan Günlükler, günlüklerde yer alan kişisel bilgileri korumak için şifrelenir.
- Win32 uygulama hataları için destek biletlerini açarken, yukarıda belirtilen adımları kullanarak ilgili hata günlüklerini iliştirin.

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Microsoft Mağazası'ndan uygulama sorunlarını giderme

[Microsoft Mağazası uygulamalarının paketleme, dağıtım ve sorgu sorunlarını giderme](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) konusunda yer alan bilgiler, Intune’u veya diğer araçları kullanarak Microsoft Mağazası’nden uygulama yüklerken karşılaşabileceğiniz genel sorunları gidermenize yardımcı olur.

## <a name="app-troubleshooting-resources"></a>Uygulama sorun giderme kaynakları
- [Office Pro Plus dağıtımınızın bir parçası olarak Visio ve proje dağıtma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Windows 10 1903 ' de Intune yüklemesi aracılığıyla dağıtılan MSfB uygulamalarının sağlandığından emin olmak için Işlem yapın](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Microsoft Intune 'de MSI uygulama dağıtımları sorunlarını giderme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Klasik Intune Windows bılgısayar aracısına yazılım dağıtımı için en iyi uygulamalar](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Sonraki adımlar

- Ek Intune sorun giderme bilgileri için bkz. [Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma](../fundamentals/help-desk-operators.md). 
- Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Intune müşteri başarısı](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).
