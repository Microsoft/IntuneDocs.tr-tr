---
title: "Intune ile Windows bilgisayarlarını yönetme | Microsoft Intune"
description: 
keywords: 
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0335b80afa8e330263baad054f0e902f019f75bb
ms.openlocfilehash: 92f4ddde3336fd4cf07c701596f5ebe4c0aeb49f


---

# Microsoft Intune ile Windows bilgisayarlarını yönetme
Cihazları kaydetmenin yanı sıra, Intune’u kullanarak desteklenen işletim sistemlerini çalıştıran Windows bilgisayarlarını da Windows bilgisayar istemcisi yazılımıyla yönetebilirsiniz. Bilgisayar istemcisini çalıştırmak için donanım ve yazılım gereksinimleri düşüktür; Windows 7 veya üzerini çalıştırabilen neredeyse tüm sistemler desteklenir.  İstemci yazılımı, etki alanına katılmış (herhangi bir etki alanında) bilgisayarlarda veya hiçbir etki alanına katılmamış bilgisayarlarda da kolayca yüklenebilir.

Intune, Windows Server Active Directory Etki Alanı Hizmetleri (AD DS) Grup İlkesi Nesneleri’ne (GPO'lar) benzer bir biçimde, Windows bilgisayarlarını ilkelerle yönetir. Intune ile Active Directory etki alanına katılmış bilgisayarları yönetecekseniz kurumunuzda yürürlükte olan herhangi bir [GPO ile Intune ilkelerinin çakışmadığından emin olun](resolve-gpo-and-microsoft-intune-policy-conflicts.md).

> [!NOTE]
> Tek başına bir hizmet olarak Microsoft Intune, bilgisayarları yönetmek için bu özellikleri sunar. Windows 8.1 çalıştıran cihazlar Intune istemcisi kullanılarak yönetilebilir veya mobil cihaz olarak kaydedilebilir. Aşağıdaki bilgiler, Intune istemcisini çalıştıran bilgisayarlar için geçerlidir.

## Intune bilgisayar yönetimi gereksinimleri

**Donanım**: Intune istemcisini yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve Bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

**Yazılım**: Aşağıda, istemciyi yüklemeye ilişkin yazılım gereksinimleri verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu bilgisayarda yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.<br /><br />Bir bilgisayardaki Windows Installer sürümünü görüntülemek için:<br /><br />-   Bilgisayarda **%windir%\System32\msiexec.exe** dosyasına sağ tıklayın ve ardından **Özellikler**’e tıklayın.<br /><br />En son Windows Installer sürümünü Microsoft Developer Network web sitesindeki [Windows Installer Yeniden Dağıtılabilir Öğeleri](http://go.microsoft.com/fwlink/?LinkID=234258) bölümünden indirebilirsiniz.|
|Uyumsuz istemci yazılımını kaldırma|Intune istemci yazılımını yüklemeden önce, bu bilgisayardan tüm Configuration Manager veya System Management Server istemci yazılımlarını kaldırmalısınız.|

## Intune bilgisayar istemcisini yükleme
Intune’la Windows bilgisayarlarını yönetmenin ilk adımı istemciyi yüklemektir. İstemci yazılımı, bir bilgisayar aşağıdaki yollardan biriyle Intune hizmeti tarafından yönetime kaydedildiğinde yüklenebilir:

-   [Microsoft Intune istemcisi yazılımını el ile dağıtabilirsiniz](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Bu dağıtım türünde bir yönetici Intune istemcisi yazılımını indirir ve yazılımı her bir bilgisayara el ile yükler.

    Intune istemcisi yazılımını indirmek için Intune yönetim konsolunu açın ve İstemci Yazılımını İndirme alanından istemci yazılımı paketini indirin. İstemci yazılımı yüklendikten sonra Intune, bilgisayarı yönetmek için gereken ek yazılımları otomatik olarak yükler.

-   [Active Directory GPO'larını kullanarak Intune istemcisini etki alanına katılmış bilgisayarlara dağıtmak](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy) için de indirdiğiniz dosyaları kullanarak istemciyi el ile yükleyebilirsiniz.

-   Intune Şirket Portalı üzerinden, [son kullanıcılar sahip oldukları her bilgisayarı kendileri kaydedebilir](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers). Daha sonra, kaydedilen her bilgisayar, Intune istemcisi yazılımını yüklemek için kullanılan kullanıcı hesabına otomatik olarak bağlanır.

-   Son olarak, Intune istemcisi yazılımını bilgisayarlara [işletim sistemi dağıtımının](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image) bir parçası olarak da dağıtabilirsiniz.

## Intune bilgisayar istemcisi ile bilgisayar yönetimi
Intune istemcisi yüklendikten sonra, istemci yazılımı aşağıdakiler de dahil olmak üzere çeşitli bilgisayar yönetimi özellikleri sağlar: [uygulama yönetimi](deploy-apps-in-microsoft-intune.md), Endpoint Protection, donanım ve yazılım envanteri, uzaktan denetim (uzaktan yardım istekleri aracılığıyla), yazılım güncelleştirmeleri ve uyumluluk ayarlarını raporlama.

Bilgisayar istemcisi tarafından etkinleştirilen çeşitli bilgisayar yönetimi görevleri, aşağıdakiler gibi Intune ilkeleri kullanılarak yönetilir:

-   Yönetilen bilgisayarlarda [Windows Güvenlik Duvarı ayarlarını](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) yapılandırma.

-   Yönetilen bilgisayarların gerekli yazılım güncelleştirmelerini denetlemesi ve indirmesi için [yazılım güncelleştirme ayarlarını](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) yapılandırma.

-   [Gerçek zamanlı izleme ve Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) yönetimi aracılığıyla yönetilen bilgisayarların olası risklerden ve kötü amaçlı yazılımlardan korunmasına yardımcı olma.

Tek tek bilgisayarlarda yerel olarak Intune istemci aracısı tarafından gerçekleştirilen eylemlere ek olarak, Intune yönetici konsolunu kullanarak istemcinin yüklendiği Windows bilgisayarlarında diğer [yaygın bilgisayar yönetimi görevlerini](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) de gerçekleştirebilirsiniz:

-   Yönetilen bilgisayarlar hakkında donanım ve yazılım envanteri bilgilerini görüntüleme

-   Bir bilgisayarı uzaktan yeniden başlatma

-   İstemci yazılımını kaldırmak için bir bilgisayarı kullanımdan kaldırma ve Intune ile yönetimden kaldırma

-   Kullanıcıları belirli yönetilen bilgisayarlara bağlama

-   Uzaktan yardım isteklerini yanıtlama

Intune istemci aracısı genellikle fazla kullanıcı etkileşimi veya sorun giderme gerektirmeden, arka planda sessizce çalışır. Ancak, bilgisayar yönetimi sorunlarını çözme konusunda yardıma ihtiyacınız olursa [sorunları çözmenize yardımcı olacak kaynaklar](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) vardır.



<!--HONumber=Jun16_HO4-->


