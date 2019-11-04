---
title: Microsoft Intune - Azure'da istemci yazılımı olan bilgisayarları yönetme | Microsoft Docs
description: Windows bilgisayarlarını Intune istemci yazılımını yükleyerek yönetin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/15/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb67cf2cb17b78c4034c3b73e229e160723d975e
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414401"
---
# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Intune yazılımı istemcisi ile Windows PC’leri bilgisayar olarak yönetme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

> [!WARNING]
> Microsoft [Windows 7 desteğinin 14 Ocak 2020'de sona erdiğini](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020) duyurdu. Aynı tarihte Intune'da Windows 7 çalıştıran cihazlar için desteğini kaldıracaktır. Microsft, hizmet ve destek kesintilerini önlemek için Windows 10'a geçmenizi özellikle önerir.
> 
> Daha fazla bilgi için bkz. [Intune için plan planı: Windows 7 için destek sonuna yaklaşma](../fundamentals/whats-new.md#intune-plan-for-change-nearing-end-of-support-for-windows-7).

> [!NOTE]
> Aşağıda açıklandığı gibi Windows bilgisayarlarını [mobil cihaz yönetimi (MDM) ile mobil cihazlar olarak](../enrollment/windows-enroll.md) ya da Intune yazılım istemcisi ile bilgisayarlar olarak yönetmek için Microsoft Intune’u kullanabilirsiniz. Ancak Microsoft, müşterilerin mümkün olan her durumda [MDM yönetim çözümünü kullanmasını](../enrollment/windows-enroll.md) önerir. Daha fazla bilgi için bkz. [Windows bilgisayarlarını bilgisayar veya mobil cihaz olarak yönetmeyi karşılaştırma](pc-management-comparison.md) 

Intune, mobil cihazların yönetimi için kuruluşlara yönelik kapsamlı bir çözüm sağlar. Intune, Windows 10 işletim sistemine yerleşik modern cihaz yönetim özelliklerini kullanarak Windows PC’leri mobil cihaz olarak yönetebilir. Kuruluşunuzun yönetim gereksinimlerini karşılamak için Intune, Intune yazılım istemcisi ile Windows PC’leri bilgisayar olarak da yönetebilir. Bu yönetim yöntemi eski Windows işletim sistemindeki geleneksel bilgisayar yönetimi özelliklerini kullanır.

Intune yazılım istemcisi, mobil cihaz olarak yönetilemeyen Windows 7 gibi eski işletim sistemlerini çalıştıran Windows PC’ler için uygundur. Intune yazılım istemcisi PC’leri buluttan yönetmek için Grup İlkesi gibi yönetim özelliklerini kullanır.

Intune, yazılım istemcisi kullanılarak Windows PC’lerin bilgisayar olarak yönetilmesini 7000 PC’ye kadar destekler. Daha büyük dağıtımlar için Windows 10 PC’leri mobil cihaz olarak yönetin. Her Intune sürümü ve Windows 10 güncelleştirmesi, mobil cihaz yönetimi mimarisine göre yönetim özellikleri içerir. Kuruluşunuzu mobil cihaz olarak yönetilen Windows 10’a taşımanızı kesinlikle öneririz.

> [!NOTE]
> Windows 8.1 ve üzeri cihazları, Intune istemci yazılımı ile bilgisayar olarak veya mobil cihaz olarak yönetebilirsiniz. İki yöntemi aynı cihazda birlikte kullanamazsınız. Bilgisayarları Intune istemci yazılımı ile yönetmeye karar vermeden önce dikkatlice düşünün. Bu konu, yalnızca Intune istemci yazılımını kullanarak cihazları bilgisayar olarak yönetme işlemi için geçerlidir.

## <a name="requirements-for-intune-pc-client-management"></a>Intune bilgisayar istemcisi yönetimi gereksinimleri

**Donanım**:  
Intune istemci yazılımını yüklemeye yönelik en düşük donanım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|Ağ|İstemci, bilgisayarınızın İnternet bağlantısının olmasını gerektirir.|
|İşlemci ve Bellek|Bilgisayarın işletim sistemine ait işlemci ve RAM gereksinimlerine bakın.|
|Disk alanı|İstemci yazılımı yüklenmeden önce 200 MB kullanılabilir disk alanı.|

**Yazılım**:  
İstemci yazılımını yüklemeye yönelik yazılım gereksinimleri aşağıda verilmiştir:

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------|
|İşletim sistemi | Windows 7 SP1 ve Windows 8.1 veya üstünü çalıştıran Windows cihazı. </br></br>**Home Edition sürümleri desteklenmez.**|
|Yönetim izinleri|İstemci yazılımını yükleyen hesabın bu cihaz üzerinde yerel yönetici izinleri olmalıdır.|
|Windows Installer 3.1|Bilgisayarda en azından Windows Installer 3.1 olmalıdır.<br /><br />Bir bilgisayardaki Windows Installer sürümünü görüntülemek için:<br /><br />  Bilgisayarda **%windir%\System32\msiexec.exe** dosyasına sağ tıklayın ve ardından **Özellikler**’e tıklayın.<br /><br />En son Windows Installer sürümünü Microsoft Developer Network web sitesindeki [Windows Installer Yeniden Dağıtılabilir Öğeleri](https://go.microsoft.com/fwlink/?LinkID=234258) bölümünden indirebilirsiniz.|
|Uyumsuz istemci yazılımını kaldırma|Intune istemci yazılımını yüklemeden önce, bu bilgisayardan tüm Configuration Manager, Operations Manager ve Service Manager istemci yazılımlarını kaldırmalısınız.|

## <a name="deploying-the-intune-software-client"></a>Intune yazılım istemcisini dağıtma
Bir Intune yöneticisi olarak, Intune yazılımı istemcisini çeşitli şekillerde kullanıcılara sunabilirsiniz. Yönergeler için bkz. [Windows PC’lere Intune yazılım istemcisini yükleme](../install-the-windows-pc-client-with-microsoft-intune.md).

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Intune istemci yazılımıyla bilgisayar yönetimi özellikleri
Çoğu senaryoda, cihazlarınızı Microsoft Intune’a kaydeder ve böylece daha büyük bir özellik kümesine sahip olursunuz. Bununla birlikte, bilgisayarlarınızı yönetmek için aşağıdaki özellikleri sağlayan Intune yazılım istemcisini de kullanabilirsiniz:

- **[Yazılım güncelleştirmelerini yönetme](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)** - Bilgisayarları güncel tutup güncelleştirmelerin ne zaman uygulanacağına karar verebilirsiniz.

- **[Windows Güvenlik Duvarı ilkesi](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)** - Bu özellik şirketinizde kullanılan bilgisayarların devre dışı veya yanlış yapılandırılmış bir Windows Güvenlik Duvarı’na sahip olmamasını sağlamaya yardımcı olur.

- **[Kötü amaçlı yazılımdan koruma](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)** - Intune, bilgisayarlarınızın kötü amaçlı yazılımlara karşı korunmasına yardımcı olan Endpoint Protection’ı içerir.

- **[Uzaktan yardım](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)** - Intune kullanıcıların BT destek personeliyle bağlantı kurmasına olanak tanır ve onlar da Intune’la birlikte gelen uzak masaüstü özelliğini kullanarak yardım sağlayabilir (TeamViewer yazılımı gerekir).

- **[Yazılım lisansı yönetimi](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)** - Kullanılabilir yazılım lisanslarının sayısını ve bunlardan kaç tanesinin kullanıldığını izleyin.
- **[Uygulama dağıtımı](add-apps-for-windows-pcs-in-microsoft-intune.md)** - Yönettiğiniz bilgisayarlarda yazılım dağıtımı yapın. Bilgisayarları yazılım istemcisiyle yönettiğinizde bazı uygulama yönetimi özellikleri kullanılamaz.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Intune yazılım istemcisi için ilkeler ve uygulama dağıtımları

Intune istemci yazılımı, yazılım güncelleştirmelerini, Windows güvenlik duvarını ve Endpoint Protection’ı yöneterek [bilgisayarları korumaya yardımcı olan yönetim özelliklerini](policies-to-protect-windows-pcs-in-microsoft-intune.md) desteklese de Intune istemci yazılımıyla yönetilen bilgisayarlara, mobil cihaz yönetimine özgü **Windows** ilke ayarları da dahil olmak üzere diğer Intune ilkeleri hedeflenemez.

Windows bilgisayarlarını yönetmek için Intune istemci yazılımını kullandığınızda, yalnızca **Bilgisayar Yönetimi** bölümünün altında gösterilen ilkeleri kullanabilirsiniz.

Intune, Windows Server Active Directory Etki Alanı Hizmetleri (AD DS) Grup İlkesi Nesneleri’ne (GPO'lar) benzer bir biçimde, Windows PC’leri ilkelerle yönetir. Intune ile Active Directory etki alanına katılmış bilgisayarları yönetiyorsanız, kuruluşunuzda kullanılan herhangi bir [GPO ile Intune ilkelerinin çakışmadığından emin olun](resolve-gpo-and-microsoft-intune-policy-conflicts.md). Daha fazla bilgi için bkz. [yeni başlayanlar için Grup İlkesi](https://technet.microsoft.com/library/hh147307.aspx).

  ![Yeni Windows bilgisayar ilkesi için şablon seçin](./media/manage-windows-pcs-with-microsoft-intune/select-template-for-pc-policy.png)

Uygulamaları dağıtırken yalnızca Windows Installer’ı (.exe, .msi) kullanabilirsiniz.

  ![Bilgisayar istemci yazılımı dosyaları için platform ve konum seçin](./media/manage-windows-pcs-with-microsoft-intune/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Windows PC’ler için ortak görevler

Intune yönetim konsolunu, istemcinin yüklendiği Windows PC’lerde diğer genel bilgisayar yönetimi görevlerini yerine getirmek için kullanabilirsiniz:
- [PC yönetimini basitleştirmek için ilkeleri kullanma](use-policies-to-simplify-windows-pc-management.md) -Intune'un **Bilgisayar Yönetimi** ilkeleri açıklanır ve Microsoft Intune Center ayarları listelenir.

- [Windows bilgisayarları için donanım ve yazılım envanterini görüntüleme](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md) - Bilgisayarların donanım özellikleri ve donanım üzerinde yüklü olan yazılım özellikleri hakkındaki bilgileri listeleyen bir raporun nasıl oluşturulacağı açıklanır. Ayrıca, güncel olduğundan emin olmak için bilgisayar envanterinin nasıl yenileneceği açıklanır.
- [Bir Windows bilgisayarını devre dışı bırakma](retire-a-windows-pc-with-microsoft-intune.md) - Bir Windows bilgisayarını devre dışı bırakma adımları ve bir bilgisayarı devre dışı bıraktığınızda ne olacağı açıklanır.
- [Windows bilgisayarlar için kullanıcı cihazı bağlamayı yönetme](../manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md) - Bir kullanıcıya yazılım dağıtmadan önce bir kullanıcının bilgisayara ne zaman ve nasıl bağlamanız gerektiği açıklanır.
- [Windows bilgisayarlar için uzaktan yardım isteme ve sağlama](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md) - Intune bilgisayar kullanıcılarının sizden nasıl uzaktan yardım alabileceği, önkoşullar ve TeamViewer kurulumu açıklanır.

Yukarıdaki görevler hakkında daha fazla bilgi için [genel bilgisayar yönetimi görevlerine](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) bakın.

## <a name="management-limitations-of-the-intune-client-software"></a>Intune istemci yazılımının yönetim sınırlamaları

Bilgisayarları mobil cihaz olarak yönetmek için kullanılabilecek bazı yönetim seçenekleri, Intune istemci yazılımıyla yönetilen bilgisayarlar için kullanılamaz:

- Tam silme (seçmeli silme bulunur)
- Conditional Access

Intune yönetim konsolundaki **Güncelleştirmeler**, **Koruma** ve **Lisanslar** gibi bazı bölümlerin, yalnızca Intune istemci yazılımını kullanarak cihazları kaydettiğinizde görüntülendiğini de aklınızda bulundurun.

  ![Yalnızca bilgisayar istemcisi için gösterilen yönetim konsolu öğeleri](./media/manage-windows-pcs-with-microsoft-intune/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Sorunları gidermeye yardımcı olma

Intune istemci yazılımı genellikle fazla kullanıcı etkileşimi veya sorun giderme gerektirmeden, sessizce arka planda çalışır. Bilgisayar yönetim sorunlarını çözmeniz gerekiyorsa, günlükleri gözden geçirebilirsiniz. Intune istemci yazılımı ve ilgili günlükler, %Program Files%\Microsoft\OnlineManagement dizini altına yüklenir.

Cihazları Microsoft Intune’a kaydetme hakkında daha fazla bilgi için [cihaz kaydını](../enrollment/device-enrollment.md) da gözden geçirebilirsiniz.
