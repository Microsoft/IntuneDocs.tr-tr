---
title: "Intune bilgisayar yazılım istemcisi özellikleri | Microsoft Intune"
description: "Windows bilgisayarlarını Intune yazılım istemcisiyle yönetirken sağlanan Intune özelliklerini öğrenin."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 12d75bc67fd61a2e807eed2543f21b756a65a900
ms.openlocfilehash: 3066ef98c0a1df6fc0ae455860635e7c12f82c4f


---

# Intune yazılım istemcisi kullandığınızda Windows PC yönetimi özellikleri)
Çoğu senaryoda, cihazlarınızı Microsoft Intune’a kaydeder ve böylece daha büyük bir özellik kümesine sahip olursunuz. Bununla birlikte, bilgisayarlarınızı yönetmek için aşağıdaki özellikleri sağlayan Intune yazılım istemcisini de kullanabilirsiniz:

-   **Yazılım güncelleştirmelerini yönetme** - Bilgisayarları güncel tutup, güncelleştirmelerin ne zaman uygulanacağına karar verebilirsiniz.

-   **Windows Güvenlik Duvarı ilkesi** - Bu özellik şirketinizde kullanılan hiçbir bilgisayarın devre dışı veya yanlış yapılandırılmış bir Windows Güvenlik Duvarı’na sahip olmamasını sağlamaya yardımcı olur.

-   **Kötü amaçlı yazılımdan koruma** - Intune, bilgisayarlarınızın kötü amaçlı yazılımlara karşı korunmasına yardımcı olan Endpoint Protection’ı içerir.

-   **Uzaktan yardım** - Intune kullanıcıların BT destek personeliyle bağlantı kurmasına olanak tanır ve onlar da Intune’la birlikte gelen uzak masaüstü özelliğini kullanarak yardım sağlayabilir (TeamViewer yazılımı gerekir).

-   **Yazılım lisansı yönetimi** - Kullanılabilir yazılım lisanslarının sayısını ve bunlardan kaç tanesinin kullanıldığını izleyin.
-   **Uygulama dağıtımı** - Yönettiğiniz bilgisayarlarda yazılım dağıtımı yapın. Bilgisayarları yazılım istemcisiyle yönettiğinizde bazı uygulama yönetimi özellikleri kullanılamaz.


Intune, 7.000’e kadar Windows cihazında yazılım istemcisinin yüklenmesini destekler.

## İşletim sistemi gereksinimleri
Intune, aşağıdaki Windows sürümlerini çalıştıran bilgisayarları yönetebilir (hem 32 bit hem de 64 bit):


-   **Windows Vista** - Business, Enterprise ve Ultimate sürümleri

-   **Windows 7** - Pro, Enterprise ve Ultimate sürümleri (hizmet paketi yüklü olmayan veya SP1 yüklü)

-   **Windows 8** - Pro ve Enterprise sürümleri

-   **Windows 8.1** - Pro ve Enterprise sürümleri

- **Windows 10** - Pro, Education ve Enterprise sürümleri


## En düşük donanım gereksinimleri
Intune yazılım istemcisini yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Ayrıntılar|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

## Diğer gereksinimler
Intune yazılım istemcisini yüklemeye yönelik yazılım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Ayrıntılar|
|---------------|--------------------|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu bilgisayar için yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.|
|Uyumsuz istemci yazılımını kaldırma|Intune bilgisayar istemcisi yazılımını yüklemeden önce aşağıdaki istemci yazılımlarını ilgili bilgisayardan kaldırmanız gerekir:<br /><br />-   Configuration Manager’ın herhangi bir sürümü<br />-   Microsoft Systems Management Server’ın herhangi bir sürümü (SMS)|

### Ayrıca bkz.
[Microsoft Intune’un kayıtlı cihaz yönetimi özellikleri](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


