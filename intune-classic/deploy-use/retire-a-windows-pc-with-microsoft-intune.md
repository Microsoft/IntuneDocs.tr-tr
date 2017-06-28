---
title: "Bir Windows bilgisayarı devre dışı bırakma"
description: "Intune tarafından yönetilen bir Windows bilgisayar nasıl devre dışı bırakılır?"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 09bba1ea199b51fdd1503cb1f0a3beeb97b6aa47
ms.contentlocale: tr-tr
ms.lasthandoff: 06/08/2017


---

# <a name="retire-a-windows-pc"></a>Bir Windows bilgisayarı devre dışı bırakma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bilgisayar olarak yönettiğiniz masaüstü cihazları, Intune yazılımını bunlar üzerinde çalıştırarak devre dışı bırakmak için aşağıdaki adımları uygulayın. Bir bilgisayarı devre dışı bıraktığınızda, yazılım söz konusu bilgisayarı Intune yönetiminden kaldırır. Bir bilgisayarı özgün fabrika ayarlarına döndürmek için Intune’dan fabrika sıfırlaması gerçekleştiremezsiniz.

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com/) **Gruplar** &gt; **Tüm Cihazlar**’ı (veya devre dışı bırakmak istediğiniz bilgisayarı içeren başka bir grubu) seçin.

2.  Devre dışı bırakmak istediğiniz cihazları seçin ve ardından **Devre Dışı Bırak/Temizle**'yi seçin.

Bir bilgisayarı Intune’a yeniden kaydetmek için [Windows bilgisayar istemcisini Microsoft Intune ile yükleme](install-the-windows-pc-client-with-microsoft-intune.md)’deki yönergeleri kullanarak yazılım istemcisini bilgisayara yükleyin.

Bilgisayar Intune’a bağlanamıyorsa, **Pano** çalışma alanında bir ileti görüntülenir.

Bir bilgisayarı devre dışı bıraktığınızda:

-   Intune yönetimi ve envanterinden kaldırılır ve bilgisayarla ilişkili lisans yeniden kullanılabilir hale gelir. Devre Dışı Bırak/Sil, Intune yazılım istemcisini bilgisayardan kaldırır ancak uygulamaları veya verileri kaldırmaz. Bu kullanımdan kaldırma bilgisayarda tam silme gerçekleştirmez.

-   Intune bilgisayarın durumunu artık görüntülemez.

-   Intune, yazılım istemcisini bilgisayardan kaldırır. Bilgisayar, Intune hizmetine bağlı değilse yazılım istemcisi bir sonraki bağlanışında kaldırılır.

-   Microsoft Intune Endpoint Protection bilgisayardan kaldırılır. Bilgisayarda başka bir uç nokta uygulaması yüklüyse ve devre dışı bırakıldıysa bilgisayarlarınızın korunduğundan emin olmak için Microsoft Intune Endpoint Protection kaldırıldıktan sonra bu uygulama yeniden etkinleştirilebilir.

-   Bilgisayardaki tüm ilkeler kaldırılır ve ilke tarafından ayarlanan değerler değiştirilir.

-   Bilgisayar artık Intune hizmetinden yazılım güncelleştirmeleri veya kötü amaçlı yazılım tanımı güncelleştirmeleri almaz.

-   Yapılandırmaya bağlı olarak, devre dışı bırakılan bilgisayarlar Windows Server Update Services, Windows Update veya Microsoft Update'i kullanarak güncelleştirmeleri almaya devam edebilir.

    > [!IMPORTANT]
    > İstemci yazılımı bir Grup İlkesi Nesnesi (GPO) kullanılarak yüklendiyse, yazılımın yeniden yüklenmesini önlemek için istemci yazılımı kaldırmadan önce Grup İlkesi Nesnesi'ni (GPO) kaldırmanız gerekir.

    Endpoint Protection istemcisini kaldırma işlemi başarısız olursa daha fazla yardım için [Endpoint Protection’da sorun giderme](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) konusunu okuyun.

### <a name="see-also"></a>Ayrıca bkz.

[Intune yazılım istemcisi ile genel Windows bilgisayar yönetim görevleri](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
