---
title: "Exchange Connector sorunlarını giderme | Microsoft Intune"
description: "Intune Exchange bağlayıcısı ile ilgili sorunları giderin."
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b16c19c95384655e170c199597dd6bd31afb90d
ms.openlocfilehash: 04ac69a30f6c1d91fe755f9720fbc2adc51745f7


---

# Exchange Connector’ın sorunlarını giderme
Bu konu, Intune Exchange Connector ile ilgili olabilecek sorunların nasıl giderilebileceğini açıklamaktadır.

## Bağlayıcı yapılandırmasını denetleme adımları 

Exchange Connector yapılandırmasını denetleyip sorunun çözülüp çözülmediğine bakın.

- Exchange Connector’ın ilk kurulumunda bir bildirim hesabı belirttiğinizden emin olun.
- Exchange Connector Hizmet Hesabı, Exchange Connector tarafından kullanılan PowerShell cmdlet'lerini çalıştırmak için uygun izinlere sahip olmalıdır.
- Exchange Connector’ı yapılandırırken, bir Exchange Connector’ı barındıran sunucuya olabildiğince yakın olan bir İstemci Erişimi Sunucusu (CAS) belirtin. CAS ile Exchange Connector arasındaki iletişim gecikmesi, özellikle O365 Dedicated kullanılırken cihaz bulma gecikmelerine neden olabilir.
- Exchange CAS ile yapılan Exchange Connector eşitlemeleri arasında bir zaman gecikmesi olduğunu unutmayın. Tam bir eşitleme günde bir, bir delta eşitlemesi (hızlı eşitleme) iki saatte bir gerçekleşir. Yeni kaydedilmiş bir cihazı olan kullanıcının erişim edinmede bir gecikme yaşaması olasıdır.
- 
## Exchange’den bulunmayan Exchange ActiveSync cihazı
Exchange Connector’ın Exchange sunucusu ile eşitlenip eşitlenmediğine bakın. Bunun için tam eşitleme veya delta eşitlemesi günlüklerini bulun. Bkz. Exchange Connector Günlükleri. Cihaz katıldığından bu yana bir tam eşitleme veya delta eşitlemesi başarıyla tamamlandıysa, bunun sorunun kaynağı olmadığı anlaşılmış olur. Hiçbir eşitleme gerçekleşmediyse, eşitleme günlüklerini toplayın ve destek isteğinize ekleyin.

- Kullanıcının Intune lisansı yoksa, Exchange bağlayıcısı kullanıcının cihazlarını bulamaz.
- Kullanıcının Birincil SMTP adresi AAD’deki UPN’sinden farklıysa, Exchange Connector bu Intune/AAD kullanıcısı için hiçbir cihaz bulamaz. Birincil SMTP adresini düzeltin.
- Exchange Connector’ın bir bulma döngüsü sırasında iletişim kurduğu CAS, bir Exchange 2010 CAS’iyse ve hem Exchange 2010 hem de 2013 posta kutusu sunucunuz varsa, Exchange Connector hiçbir Exchange 2013 kullanıcısının cihazını bulamaz. Bu sorunu gidermek için Exchange Connector’ı bir Exchange 2013 CAS’ine işaret edecek şekilde yapılandırın.  Bu sorun öncelikle O365 Dedicated topolojilerini ilgilendirmekle birlikte, en iyi yöntem olarak diğer topolojilerde de bir Exchange 2013 CAS’e işaret edilmesini öneririz.
- Exchange Dedicated (O365 Dedicated) ortamlarında, ayrılmış ortamda ilk kurulum sırasında, CAS ile yalnızca Powershell cmdlet’lerini çalıştırırken iletişim kuracağından Exchange Connector’ı bir (2010 değil) Exchange 2013 CAS’ine işaret ettirmelisiniz.


## Exchange Connector sorunlarına ilişkin daha fazla veri almak için Powershell kullanma
- Bir posta kutusunun tüm mobil cihazlarının listesini almak için Get-ActiveSyncDeviceStatistics -mailbox mbx kullanın
- Bir posta kutusunun SMTP adreslerinin bir listesini almak için Get-Mailbox -Identity user | select emailaddresses | fl kullanın.
- Bir cihazın erişim durumu hakkında ayrıntılı bilgi almak için Get-CASMailbox <upn> | fl kullanın

### Sonraki adımlar
Bu sorun giderme bilgileri işe yaramazsa, [Microsoft Intune için destek alma](how-to-get-support-for-microsoft-intune.md) konusunda açıklandığı gibi Microsoft Desteği ile iletişim kurun.



<!--HONumber=Aug16_HO1-->

