---
title: "İstemci yazılımı ile bilgisayarları yönetme | Microsoft Docs"
description: "Windows bilgisayarlarını Intune istemci yazılımını yükleyerek yönetin."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 2e7062169ceb855f03a13d1afb4b4de41af593ac
ms.openlocfilehash: 10ba007095182c9cb07710656ba5f275e254d92e
ms.lasthandoff: 02/15/2017


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Intune bilgisayar istemcisiyle Windows bilgisayarlarını yönetme
[Windows bilgisayarlarını mobil cihaz olarak kaydetme](set-up-windows-device-management-with-microsoft-intune.md), Windows bilgisayarlarını Intune’a kaydetmenin tercih edilen yöntemidir; ancak alternatif olarak, bu konuda açıklandığı gibi Intune istemci yazılımını yükleyerek Windows bilgisayarlarını kaydetmeyi ve yönetmeyi de seçebilirsiniz.

Intune, Windows Server Active Directory Domain Services (AD DS) Grup İlkesi Nesneleri’ne (GPO'lar) benzer bir biçimde, Windows bilgisayarlarını ilkelerle yönetir. Intune ile Active Directory etki alanına katılmış bilgisayarları yönetecekseniz kurumunuzda yürürlükte olan herhangi bir [GPO ile Intune ilkelerinin çakışmadığından emin olun](resolve-gpo-and-microsoft-intune-policy-conflicts.md). [GPO’lar](https://technet.microsoft.com/library/hh147307.aspx) hakkında daha fazla bilgi edinebilirsiniz.

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Intune yazılım istemcisi için ilkeler ve uygulama dağıtımları

Intune istemci yazılımı, yazılım güncelleştirmelerini, Windows güvenlik duvarını ve Endpoint Protection’ı yöneterek [bilgisayarları korumaya yardımcı olan yönetim özelliklerini](policies-to-protect-windows-pcs-in-microsoft-intune.md) desteklese de Intune istemci yazılımıyla yönetilen bilgisayarlara, mobil cihaz yönetimine özgü **Windows** ilke ayarları da dahil olmak üzere diğer Intune ilkeleri hedeflenemez. 

Windows bilgisayarlarını yönetmek için Intune istemci yazılımını kullandığınızda, yalnızca **Bilgisayar Yönetimi** bölümünün altında gösterilen ilkeleri kullanabilirsiniz.

  ![Yeni Windows bilgisayar ilkesi için şablon seçin](../media/select-template-for-pc-policy.png)

Ayarlayabileceğiniz ilkelerin ayrıntılı açıklamaları için bkz:

- [Intune istemci yazılımını çalıştıran Windows bilgisayarlarını korumaya yardımcı olmak için ilkeleri kullanma](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Microsoft Intune'da yazılım güncelleştirmeleri ile Windows bilgisayarlarını güncel tutma](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Microsoft Intune’da Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Microsoft Intune için Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Bunlara ek olarak, uygulamaları dağıtırken yalnızca Windows Installer’ı (.exe, .msi) kullanabilirsiniz.

  ![Bilgisayar istemci yazılımı dosyaları için platform ve konum seçin](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> Windows 8.1 veya üzeri cihazları, Intune istemci yazılımı ile bilgisayar olarak veya mobil cihaz yönetimi (MDM) işlevi ile mobil cihaz olarak yönetebilirsiniz. İki yöntem birlikte kullanılamaz. Bu nedenle, bilgisayarları Intune istemci yazılımını kullanarak yönetmeye karar vermeden önce dikkatlice düşünün. Bu konu, yalnızca Intune istemci yazılımını kullanarak cihazları bilgisayar olarak yönetme işlemi için geçerlidir.

## <a name="requirements-for-intune-pc-client-management"></a>Intune bilgisayar istemcisi yönetimi gereksinimleri

**Donanım**: Intune istemci yazılımını yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve Bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce&200; MB kullanılabilir disk alanı.|

**Yazılım**: İstemci yazılımını yüklemeye ilişkin yazılım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|İşletim sistemi | Windows Vista veya üstünü çalıştıran Windows cihazı. </br></br>**Home Edition sürümleri desteklenmez.**|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu cihaz üzerinde yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.<br /><br />Bir bilgisayardaki Windows Installer sürümünü görüntülemek için:<br /><br />  Bilgisayarda **%windir%\System32\msiexec.exe** dosyasına sağ tıklayın ve ardından **Özellikler**’e tıklayın.<br /><br />En son Windows Installer sürümünü Microsoft Developer Network web sitesindeki [Windows Installer Yeniden Dağıtılabilir Öğeleri](http://go.microsoft.com/fwlink/?LinkID=234258) bölümünden indirebilirsiniz.|
|Uyumsuz istemci yazılımını kaldırma|Intune istemci yazılımını yüklemeden önce, bu bilgisayardan tüm Configuration Manager, Operations Manager, Operations Management Suite ve Service Manager istemci yazılımlarını kaldırmalısınız.|

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Intune istemci yazılımıyla bilgisayar yönetimi özellikleri

Intune istemci yazılımı yüklendikten sonra yönetim özellikleri şunları içerir: 

- [Uygulama yönetimi](deploy-apps-in-microsoft-intune.md)

- [Gerçek zamanlı izleme ve Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md): Endpoint Protection, Windows Defender ile aynı şeydir. Endpoint Protection, Windows 7 ve Windows 8 için geçerlidir. Windows 10 ve üzeri için, ürün adı Windows Defender olarak değiştirilmiştir.

- [Windows Güvenlik Duvarı ayarları yönetimi](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), donanım ve yazılım envanteri, uzaktan denetim (uzaktan yardım istekleri aracılığıyla)

- [Yazılım güncelleştirme ayarları](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Uyumluluk ayarlarını bildirme

Intune yönetim konsolundaki "Güncelleştirmeler", "Koruma" ve "Lisanslar" gibi bazı bölümler, yalnızca Intune istemci yazılımını kullanarak cihazları kaydettiğinizde görüntülenir.

  ![Yalnızca bilgisayar istemcisi için gösterilen yönetim konsolu öğeleri](../media/admin-console-settings-only-for-pc-agent.png)

Intune yönetim konsolunu, istemcinin yüklendiği Windows bilgisayarlarında diğer genel bilgisayar yönetimi görevlerini yerine getirmek için de kullanabilirsiniz:

-   Yönetilen bilgisayarlar hakkında donanım ve yazılım envanteri bilgilerini görüntüleme
-   Bir bilgisayarı uzaktan yeniden başlatma
-   İstemci yazılımını kaldırmak için bir bilgisayarı kullanımdan kaldırma ve Intune ile yönetimden kaldırma
-   Kullanıcıları belirli yönetilen bilgisayarlara bağlama
-   Uzaktan yardım isteklerini yanıtlama

Yukarıdaki görevler hakkında daha fazla bilgi için [genel bilgisayar yönetimi görevlerine](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) bakın.

## <a name="management-limitations-of-the-intune-client-software"></a>Intune istemci yazılımının yönetim sınırlamaları

Bilgisayarları mobil cihaz olarak yönetmek için kullanılabilecek bazı yönetim seçenekleri, Intune istemci yazılımıyla yönetilen bilgisayarlar için kullanılamaz:

-   Tam silme (seçmeli silme bulunur)

-   Koşullu erişim

## <a name="help-with-troubleshooting"></a>Sorunları gidermeye yardımcı olma

Intune istemci yazılımı genellikle fazla kullanıcı etkileşimi veya sorun giderme gerektirmeden, sessizce arka planda çalışır. Bilgisayar yönetim sorunlarını çözmeniz gerekiyorsa, günlükleri gözden geçirebilirsiniz. Intune istemci yazılımı ve ilgili günlükler, %Program Files%\Microsoft\OnlineManagement dizini altına yüklenir.

Ortaya çıkabilecek sorunları ve çözümlerini veya geçici çözümlerini denetlemek için, [Microsoft Intune’da istemci kurulumu sorunlarını giderme](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) konusunu da gözden geçirebilirsiniz.

