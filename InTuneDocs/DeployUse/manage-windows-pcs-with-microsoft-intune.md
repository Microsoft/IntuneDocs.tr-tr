---
title: "İstemci yazılımı ile bilgisayarları yönetme | Microsoft Intune"
description: "Windows bilgisayarlarını Intune istemci yazılımını yükleyerek yönetin."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: f264dc3740ce9b117fcc01c39792904a2dc6e7ab


---

# Intune bilgisayar istemcisiyle Windows bilgisayarlarını yönetme
[Windows bilgisayarlarını mobil cihaz olarak kaydetmek](set-up-windows-device-management-with-microsoft-intune.md) yerine, Windows bilgisayarlarını Intune istemci yazılımını yükleyerek kaydedebilir ve yönetebilirsiniz.

Intune, Windows Server Active Directory Etki Alanı Hizmetleri (AD DS) Grup İlkesi Nesneleri’ne (GPO'lar) benzer bir biçimde, Windows bilgisayarlarını ilkelerle yönetir. Intune ile Active Directory etki alanına katılmış bilgisayarları yönetecekseniz kurumunuzda yürürlükte olan herhangi bir [GPO ile Intune ilkelerinin çakışmadığından emin olun](resolve-gpo-and-microsoft-intune-policy-conflicts.md).

Intune yazılımı istemcisi, yazılım güncelleştirmelerini, Windows güvenlik duvarını ve Endpoint Protection’ı yöneterek [bilgisayarları korumaya yardımcı olan yönetim özelliklerini](policies-to-protect-windows-pcs-in-microsoft-intune.md) desteklerken, diğer Intune ilkeleri, mobil cihaz yönetimine özgü **Windows** ilke ayarları da dahil olmak üzere Intune istemcisiyle yönetilen bilgisayarları hedefleyemez.

> [!NOTE]
> Windows 8.1 veya daha sonraki sürümleri çalıştıran cihazlar, Intune istemcisi kullanılarak yönetilebilir veya mobil cihaz olarak kaydedilebilir. Aşağıdaki bilgiler, Intune istemcisini çalıştıran bilgisayarlar için geçerlidir. Hem Intune bilgisayar istemcisini yüklemek hem de mobil cihaz yönetimi için Windows cihazını kaydetmek desteklenmez.

## Intune bilgisayar istemcisi yönetimi gereksinimleri

**Donanım**: Intune istemcisini yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve Bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

**Yazılım**: Aşağıda, istemciyi yüklemeye ilişkin yazılım gereksinimleri verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|İşletim sistemi | Windows 7 veya üstünü çalıştıran Windows cihazı. |
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu cihaz üzerinde yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.<br /><br />Bir bilgisayardaki Windows Installer sürümünü görüntülemek için:<br /><br />-   Bilgisayarda **%windir%\System32\msiexec.exe** dosyasına sağ tıklayın ve ardından **Özellikler**’e tıklayın.<br /><br />En son Windows Installer sürümünü Microsoft Developer Network web sitesindeki [Windows Installer Yeniden Dağıtılabilir Öğeleri](http://go.microsoft.com/fwlink/?LinkID=234258) bölümünden indirebilirsiniz.|
|Uyumsuz istemci yazılımını kaldırma|Intune istemci yazılımını yüklemeden önce, bu bilgisayardan tüm Configuration Manager veya System Management Server istemci yazılımlarını kaldırmalısınız.|

## Intune bilgisayar istemcisini yükleme
Intune istemci yazılımı aşağıdaki yollardan biri kullanılarak yüklenebilir:

-  [Microsoft Intune istemcisi yazılımını el ile dağıtabilirsiniz](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Bu dağıtım türünde bir yönetici Intune istemcisi yazılımını indirir ve yazılımı her bir bilgisayara el ile yükler.

  Intune istemcisi yazılımını indirmek için, [Intune yönetim konsolunu](https://manage.microsoft.com) açın, **Yönetici** > **İstemci Yazılımını İndirme**’yi seçin ve **İstemci Yazılımını İndir**’e tıklayın.

-  [Active Directory GPO’larını kullanarak istemciyi etki alanına katılmış bilgisayarlara dağıtmak](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy) için de indirdiğiniz dosyaları kullanarak Intune istemci yazılımını el ile yükleyin.

-  [İşletim sistemi dağıtımının bir parçası olarak](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image) Intune istemci yazılımını bilgisayarlara dağıtın.

-  Kullanıcılara Intune Şirket Portalı URL’sini ([https://portal.manage.microsoft.com](http://go.microsoft.com/fwlink/?LinkId=825632)) yönergeleri gönderin. Şirket Portalı’nı açtıklarında, kullanıcılardan Intune istemci yazılımını indirip çalıştırarak bilgisayarlarını kaydetmeleri istenir.

## Intune bilgisayar istemcisi ile bilgisayar yönetimi
Intune istemci yazılımı yüklendikten sonra, şunlar da dahil olmak üzere çeşitli bilgisayar yönetimi özellikleri sağlar: [uygulama yönetimi](deploy-apps-in-microsoft-intune.md), Endpoint Protection, donanım ve yazılım envanteri, uzaktan denetim (uzaktan yardım istekleri aracılığıyla), yazılım güncelleştirmeleri ve uyumluluk ayarlarını raporlama.

Bilgisayar istemcisi tarafından etkinleştirilen çeşitli bilgisayar yönetimi görevleri, aşağıdakiler gibi Intune ilkeleri kullanılarak yönetilir:

-   Yönetilen bilgisayarlarda [Windows Güvenlik Duvarı ayarlarını](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) yapılandırma.

-   Yönetilen bilgisayarların gerekli yazılım güncelleştirmelerini denetlemesi ve indirmesi için [yazılım güncelleştirme ayarlarını](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) yapılandırma.

-   [Gerçek zamanlı izleme ve Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) yönetimi aracılığıyla yönetilen bilgisayarların olası risklerden ve kötü amaçlı yazılımlardan korunmasına yardımcı olma.

![Windows bilgisayarlar için ilkeler şablonu](../media/pc_policy_template.png)

Tek tek bilgisayarlarda yerel olarak Intune istemci aracısı tarafından gerçekleştirilen eylemlere ek olarak, Intune yönetici konsolunu kullanarak istemcinin yüklendiği Windows bilgisayarlarında diğer [yaygın bilgisayar yönetimi görevlerini](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) de gerçekleştirebilirsiniz:

-   Yönetilen bilgisayarlar hakkında donanım ve yazılım envanteri bilgilerini görüntüleme

-   Bir bilgisayarı uzaktan yeniden başlatma

-   İstemci yazılımını kaldırmak için bir bilgisayarı kullanımdan kaldırma ve Intune ile yönetimden kaldırma

-   Kullanıcıları belirli yönetilen bilgisayarlara bağlama

-   Uzaktan yardım isteklerini yanıtlama

Intune istemci aracısı genellikle fazla kullanıcı etkileşimi veya sorun giderme gerektirmeden, arka planda sessizce çalışır. Ancak, bilgisayar yönetimi sorunlarını çözme konusunda yardıma ihtiyacınız olursa [sorunları çözmenize yardımcı olacak kaynaklar](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) vardır.



<!--HONumber=Aug16_HO4-->


