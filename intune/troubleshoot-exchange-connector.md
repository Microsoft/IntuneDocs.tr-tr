---
title: Exchange bağlayıcısı sorunlarını giderme
titleSuffix: Microsoft Intune
description: Intune şirket içi Exchange bağlayıcısı ile ilgili sorunları giderin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/18/2018
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea3ae66a32353b4aa6c782b13e6a587ee1f4464e
ms.sourcegitcommit: 1d4aec7b79c70d35ec3fc29df6ff9c6a1403412e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68491812"
---
# <a name="troubleshoot-the-intune-on-premises-exchange-connector"></a>Intune şirket içi Exchange bağlayıcısında sorun giderme

Bu makale, Intune şirket içi Exchange bağlayıcısı ile ilgili sorunların nasıl giderileceğini açıklar.

## <a name="steps-for-checking-the-connector-configuration"></a>Bağlayıcı yapılandırmasını denetleme adımları 

[Intune şirket içi Exchange bağlayıcısı kurulumunu](exchange-connector-install.md) denetleyerek bağlayıcının doğru yapılandırıldığından emin olun. Bazı yaygın görülen sorunlar aşağıda verilmiştir. Düzeltme yaptıktan sonra sorunun çözümlenmiş olup olmadığına bakın.

- Microsoft Intune Exchange Connector iletişim kutusunda, [gerekli Windows PowerShell Exchange cmdlet’lerini](exchange-connector-install.md#exchange-cmdlet-requirements) yürütmek için uygun izinlere sahip bir kullanıcı hesabı belirttiğinizden emin olun.
- Bildirimleri etkinleştirin ve bir bildirim hesabı belirtin.
- Exchange Connector’ı yapılandırırken, bir Exchange bağlayıcısı barındıran sunucuya olabildiğince yakın bir İstemci Erişimi Sunucusu (CAS) belirtin. CAS ile Exchange bağlayıcısı arasındaki iletişim gecikmesi, özellikle Exchange Online Dedicated kullanılırken cihaz bulmayı geciktirebilir.
- Yeni kaydedilen bir cihazın kullanıcısına sağlanacak erişim, Exchange bağlayıcısı ile Exchange CAS eşitlenene kadar gecikebilir. Tam eşitleme günde bir kez gerçekleşirken delta eşitlemesi (hızlı eşitleme) birkaç kez gerçekleşir.  Gecikmeleri olabildiğince azaltmak için [bir hızlı veya tam eşitlemeyi el ile zorlayabilirsiniz](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync).
 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Exchange’den bulunmayan Exchange ActiveSync cihazı
Exchange bağlayıcısının Exchange sunucusu ile eşitlenip eşitlenmediğini görmek için [Exchange bağlayıcısı etkinliğini izleyin](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support). Cihaz katıldıktan sonra bir tam veya hızlı eşitleme başarıyla tamamlandıysa aşağıda listelenen diğer olası sorunları denetleyebilirsiniz. Hiçbir eşitleme gerçekleşmediyse eşitleme günlüklerini toplayın ve bir destek isteğine ekleyin.

- Kullanıcının Intune lisansı olduğundan emin olun, aksi takdirde Exchange bağlayıcısı kullanıcının cihazlarını bulamaz.
- Kullanıcının birincil SMTP adresi, Azure Active Directory’deki (Azure AD) UPN’sinden farklıysa Exchange Connector bu kullanıcı için hiçbir cihaz bulamaz. Bu sorunu çözmek için birincil SMTP adresini düzeltin.
- Ortamınızda hem Exchange 2010 hem de Exchange 2013 posta kutusu sunucuları varsa Exchange bağlayıcısını bir Exchange 2013 CAS’sine yöneltmenizi öneririz. Aksi takdirde, Exchange bağlayıcısı Exchange 2010 CAS ile iletişim kurmak üzere ayarlanmışsa Exchange 2013 kullanıcılarının cihazlarını bulamaz. 
- Exchange Online Dedicated ortamlarında, bağlayıcı CAS ile yalnızca Powershell cmdlet’lerini çalıştırırken iletişim kuracağı için ayrılmış ortamda ilk kurulum sırasında Exchange bağlayıcısını bir Exchange 2013 CAS’sine (Exchange 2010 değil) yöneltmelisiniz.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Exchange Connector sorunlarına ilişkin daha fazla veri almak için Powershell kullanma
- Bir posta kutusunun tüm mobil cihazlarının listesini almak için, şunu kullanın`Get-ActiveSyncDeviceStatistics -mailbox mbx`
- Posta kutusu için SMTP adreslerinin bir listesini almak için kullanın`Get-Mailbox -Identity user | select emailaddresses | fl`
- Bir cihazın erişim durumu hakkında ayrıntılı bilgi almak için şunu kullanın`Get-CASMailbox <upn> | fl`

## <a name="next-steps"></a>Sonraki adımlar
Bu bilgiler işinize yaramazsa [Microsoft Intune desteği de alabilirsiniz](get-support.md).
