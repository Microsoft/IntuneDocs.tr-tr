---
title: "Desteklenen mobil cihazlar ve tarayıcılar | Microsoft Intune"
description: "Intune’un desteklediği mobil cihazlar ve bilgisayarlar"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Desteklenen mobil cihazlar ve bilgisayarlar

Kaydolup aşağıdaki cihaz türlerini yönetebilirsiniz:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Cihazları kaydetmek [bu özelliklerin](/Intune/get-started/choose-how-to-manage-devices) kullanılmasını sağlar.

Alternatif olarak, Windows bilgisayarları Intune PC istemci yazılımıyla yönetebilirsiniz. Intune bilgisayar istemci yazılımı, Windows 7 ve sonraki sürümleri (Windows 10 Home hariç) destekler. Bilgisayarları istemci yazılımıyla yönetmek [bu özelliklerden](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) yararlanmanızı sağlar.

Enterprise Management Suite kullanan müşteriler, Windows 10 cihazlarını kaydetmek için Azure Active Directory’yi de kullanabilir.

## <a name="microsoft-intune-supported-web-browsers"></a>Microsoft Intune tarafından desteklenen web tarayıcıları

Farklı yönetim görevleri aşağıdaki yönetim web sitelerinden birini kullanmanızı gerektirir.

- [Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune yönetici konsolu](https://admin.manage.microsoft.com/)

> [!Note]
> Microsoft Edge ve mobil tarayıcılar, [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) desteklemediklerinden yönetici konsolu için desteklenmez. Intune konsolu belirli bir zaman dilimi içinde Silverlight deneyiminden uzaklaşacaktır; bir süre sonra Intune’un tüm mobil cihaz ve uygulama yönetimi özellikleri [yeni Microsoft Azure portalında kullanılabilir olacaktır](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Intune özelliği |Desteklenen tarayıcılar|
|---------|---------|
|Intune Yönetici konsolu     |  Internet Explorer 10 veya üstü<br /><br />Google Chrome (42. sürümden önceki sürümler)<br /><br />Silverlight özelliği etkin Mozilla Firefox<br /><br />**Not:** Yönetici konsolunda Microsoft Edge ve mobil tarayıcılar desteklenmez.                      
|Office 365 Yönetici Portalı     |Mobil tarayıcılar ve yönetilen tarayıcılar dahil tüm tarayıcılar  |
|Şirket Portalı web sitesi     |**Mobil cihazlarda:** desteklenen her platform için varsayılan web tarayıcısını kullanın   <br /><br />**Windows bilgisayarlarında:** Internet Explorer 10 veya üstü ya da Microsoft Edge<br /><br />**Mac OS X 10.9 veya sonraki sürümlerde:** Apple Safari    |

> [!Note]
> Microsoft Edge ve mobil tarayıcılar, [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx) desteklemediklerinden yönetici konsolu için desteklenmez. Intune konsolu belirli bir zaman dilimi içinde Silverlight deneyiminden uzaklaşacaktır; bir süre sonra Intune’un tüm mobil cihaz ve uygulama yönetimi özellikleri [yeni Microsoft Azure portalında kullanılabilir olacaktır](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Office 365 portalı](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Kiracı yöneticisi olarak bu portalı**, yöneticiniz izin verdiğinde aşağıdaki görevler de dahil olmak üzere aboneliğinizi yönetmek için kullanın:

- Aboneliğin kullanıcı hesaplarını yönetme ve dizin eşitlemesini şirket içi Active Directory'den yapılandırma.
- Güvenlik grupları olarak anılan kullanıcı gruplarını yönetme.
- Kullanıcılara Intune kullanma lisansları atama.
- Aboneliğiniz ile birlikte kullandığınız etki alanı adını yapılandırma. Etki alanı adı, kullanıcıların oturum açtığı hesabı tanımlar.
- Aboneliğiniz için sahip olduğunuz lisans sayısı veya kullanabileceğiniz bulut depolama alanı miktarı gibi faturalama ve satın alma ayrıntılarını yönetme.
- Intune hizmetinin durumunu görüntüleyen bağlantılar bulma.
- Kiracı yöneticisi olarak, Office 365 portalında oturum açarak, hesabınıza Intune kullanmak için bir lisans atanmadığında bile aboneliğinizi yönetebilirsiniz.
- Intune lisansına sahip olan ancak yönetici olmayan tüm kullanıcılar bu portalı kullanarak hesap parolalarını sıfırlayabilir ve profillerini düzenleyebilir.
- Office 365 portalına erişmek için hesabınızın oturum açma durumu **İzin Verildi** olmalıdır. Bu durum, aboneliğin lisansına sahip olmaktan farklıdır. Varsayılan olarak, tüm kullanıcı hesapları **İzin Verildi** durumundadır.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Microsoft Intune yönetici konsolu](https://manage.microsoft.com/)

**Hizmet yöneticisi olarak günlük işlemlerinizi yönetmek için bu portalı kullanın**, örneğin:

- Bilgisayarlar ve mobil cihazlar için ilkeler ayarlama.
- Yazılım güncelleştirmeleri ve uygulamalar gibi yazılımları karşıya yükleme ve dağıtma.
- Bilgisayarlarda Endpoint Protection'ı yönetme.
- Cihaz durumunu görüntüleme ve raporları çalıştırma.
- Bu portalda oturum açın. Bu portalda oturum açabilmek için, hizmet yöneticisi izinlerine sahip olmanız veya genel yönetici rolüne sahip bir kiracı yöneticisi olmanız gerekir.


Yalnızca hizmet yöneticisi izinlerine sahip olan veya genel yönetici rolüne sahip bir kiracı yöneticisi olan kullanıcılar bu portalda oturum açabilir. Yönetim konsoluna erişmek için hesabınız Intune kullanma lisansına ve **İzin Verildi** oturum açma durumuna sahip olmalıdır.



<!--HONumber=Nov16_HO4-->


