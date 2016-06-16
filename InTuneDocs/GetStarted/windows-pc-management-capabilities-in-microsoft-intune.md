---
# required metadata

title: Windows bilgisayarı yönetim özellikleri | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: owenyen
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows bilgisayarı yönetim özellikleri (Microsoft Intune bilgisayar istemcisiyle)
Çoğu senaryoda, cihazlarınızı Microsoft Intune’a kaydedersiniz ve bu da Intune bilgisayar istemcisinden daha büyük bir özellik kümesi sağlar. Bununla birlikte bilgisayarlarınızı yönetmek için aşağıdaki özellikleri sağlayan Intune bilgisayar istemcisini de kullanabilirsiniz:

-   **Yazılım güncelleştirmelerini yönetme** - Bilgisayarları güncel tutup, güncelleştirmelerin ne zaman uygulanacağını yönetebilirsiniz.

-   **Windows Güvenlik Duvarı ilkesi** - Bu özellik şirketinizin kullandığı hiçbir bilgisayarın devre dışı veya yanlış yapılandırılmış bir Windows Güvenlik Duvarı’na sahip olmamasını sağlamaya yardımcı olur.

-   **Kötü amaçlı yazılımdan koruma** - Intune, bilgisayarlarınızın kötü amaçlı yazılımlara karşı korunmasına yardımcı olan Endpoint Protection’ı içerir.

-   **Uzaktan yardım** - Intune kullanıcıların BT destek personeliyle bağlantı kurmasına olanak tanır ve onlar da Intune <!--- (requires TeamViewer software)---> ile birlikte gelen uzak masaüstü özelliğini kullanarak yardım sağlayabilir.

-   **Yazılım lisansı yönetimi** - Kullanılabilir yazılım lisanslarının sayısını ve bunlardan kaç tanesinin kullanıldığını izleyin.
-   **Uygulama dağıtımı** - Yönettiğiniz bilgisayarlarda yazılım dağıtımı yapın. Bilgisayarları istemci yazılımıyla yönettiğinizde bazı uygulama yönetimi özellikleri kullanılamaz.


## İşletim sistemi gereksinimleri
Intune, aşağıdaki Windows sürümlerini çalıştıran bilgisayarları yönetebilir (hem x86 hem de x64):


-   **Windows Vista**: Business, Enterprise ve Ultimate sürümleri.

-   **Windows 7**: Pro, Enterprise ve Ultimate sürümleri (hizmet paketi yüklü olmayan veya SP1 yüklü).

-   **Windows 8**: Pro ve Enterprise sürümleri.

-   **Windows 8.1**: Pro ve Enterprise sürümleri.

- **Windows 10** - Home, Pro, Education ve Enterprise sürümleri.


## En düşük donanım gereksinimleri
Intune bilgisayar istemcisini yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Ayrıntılar|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve Bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

## Diğer gereksinimler
Intune bilgisayar istemcisini yüklemeye yönelik yazılım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Ayrıntılar|
|---------------|--------------------|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu bilgisayarda yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 yüklü olmalıdır.|
|Uyumsuz istemci yazılımını kaldırma|Intune bilgisayar istemcisi yazılımını yüklemeden önce aşağıdaki istemci yazılımlarını ilgili bilgisayardan kaldırmanız gerekir:<br /><br />-   Configuration Manager’ın herhangi bir sürümü<br />-   Microsoft Systems Management Server’ın herhangi bir sürümü (SMS)|

### Ayrıca bkz.
[Microsoft Intune'da mobil cihaz yönetimi özellikleri](./mobile-device-management-capabilities-in-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


