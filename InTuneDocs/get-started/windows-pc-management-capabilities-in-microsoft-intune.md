---
title: "Intune bilgisayar yazılım istemcisi özellikleri | Microsoft Docs"
description: "Windows bilgisayarlarını Intune yazılım istemcisiyle yönetirken sağlanan Intune özelliklerini öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 36a20feed1756ea8dde2230db81099b6c5f8c7f6


---

# <a name="windows-pc-management-capabilities-when-you-use-the-intune-software-client"></a>Intune yazılım istemcisi kullandığınızda Windows bilgisayarı yönetim özellikleri

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Çoğu senaryoda, cihazlarınızı Microsoft Intune’a kaydeder ve böylece daha büyük bir özellik kümesine sahip olursunuz. Bununla birlikte, bilgisayarlarınızı yönetmek için aşağıdaki özellikleri sağlayan Intune yazılım istemcisini de kullanabilirsiniz:

-   **[Yazılım güncelleştirmelerini yönetme](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)** - Bilgisayarları güncel tutup, güncelleştirmelerin ne zaman uygulanacağına karar verebilirsiniz.

-   **[Windows Güvenlik Duvarı ilkesi](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)** - Bu özellik şirketinizde kullanılan bilgisayarların devre dışı veya yanlış yapılandırılmış bir Windows Güvenlik Duvarı’na sahip olmamasını sağlamaya yardımcı olur.

-   **[Kötü amaçlı yazılımdan koruma](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)** - Intune, bilgisayarlarınızın kötü amaçlı yazılımlara karşı korunmasına yardımcı olan Endpoint Protection’ı içerir.

-   **[Uzaktan yardım](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )** - Intune kullanıcıların BT destek personeliyle bağlantı kurmasına olanak tanır ve onlar da Intune’la birlikte gelen uzak masaüstü özelliğini kullanarak yardım sağlayabilir (TeamViewer yazılımı gerekir).

-   **[Yazılım lisansı yönetimi](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)** - Kullanılabilir yazılım lisanslarının sayısını ve bunlardan kaç tanesinin kullanıldığını izleyin.
-   **[Uygulama dağıtımı](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)** - Yönettiğiniz bilgisayarlarda yazılım dağıtımı yapın. Bilgisayarları yazılım istemcisiyle yönettiğinizde bazı uygulama yönetimi özellikleri kullanılamaz.


Intune, 7.000’e kadar Windows cihazında yazılım istemcisinin yüklenmesini destekler.

## <a name="operating-system-requirements"></a>İşletim sistemi gereksinimleri
Intune, aşağıdaki Windows sürümlerini çalıştıran bilgisayarları yönetebilir (hem 32 bit hem de 64 bit):


-   **Windows Vista** - Business, Enterprise ve Ultimate sürümleri

-   **Windows 7** - Pro, Enterprise ve Ultimate sürümleri (hizmet paketi yüklü olmayan veya SP1 yüklü)

-   **Windows 8** - Pro ve Enterprise sürümleri

-   **Windows 8.1** - Pro ve Enterprise sürümleri

- **Windows 10** - Pro, Education ve Enterprise sürümleri


## <a name="minimum-hardware-requirements"></a>En düşük donanım gereksinimleri
Intune yazılım istemcisini yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Ayrıntılar|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

## <a name="further-requirements"></a>Diğer gereksinimler
Intune yazılım istemcisini yüklemeye yönelik yazılım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Ayrıntılar|
|---------------|--------------------|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu bilgisayar için yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.|
|Uyumsuz istemci yazılımını kaldırma|Intune bilgisayar istemcisi yazılımını yüklemeden önce aşağıdaki istemci yazılımlarını ilgili bilgisayardan kaldırmanız gerekir:<br /><br />-   Configuration Manager’ın herhangi bir sürümü<br />-   Microsoft Systems Management Server’ın herhangi bir sürümü (SMS)|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune’un kayıtlı cihaz yönetimi özellikleri](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


