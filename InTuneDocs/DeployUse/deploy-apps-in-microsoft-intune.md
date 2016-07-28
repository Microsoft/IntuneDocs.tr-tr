---
title: "Uygulamaları dağıtma | Microsoft Intune"
description: "Bu konu başlığı altındaki bilgileri, uygulamaları Microsoft Intune’la dağıtmanıza yardımcı olması için kullanın."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ef1d2d69acfeea9670324f580d33b191001ffa9
ms.openlocfilehash: 8ab2517a11ecb6ae5395814472dfbb3e83da132b

---
# Microsoft Intune'da uygulamaları dağıtma

Bu konu başlığı altındaki bilgileri, uygulamaları Microsoft Intune’la dağıtmanıza yardımcı olması için kullanın.


## Uygulamayı dağıtma
Bu yordamda, uygulamayı seçilen cihaz veya kullanıcı gruplarına dağıtacaksınız.

### Uygulamayı dağıtmak için

1. Yönettiğiniz uygulamaların listesini görmek için, [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Uygulamalar**’a tıklayın.

2.  Dağıtmak istediğiniz uygulamayı seçin ve **Dağıtımı Yönet**'e tıklayın.

3.  İlk olarak, *&lt;uygulama adı&gt;* iletişim kutusunun **Grupları Seç** sayfasında, uygulamayı dağıtmak istediğiniz kullanıcı veya cihaz gruplarını seçin.

4.  **Dağıtım Eylemi** sayfasında aşağıdakileri yapılandırın:

    - **Onay** - Dağıtımın aşağıdakilerden hangisi olduğunu seçin:
        - **Gerekli** (zorunlu yükleme)
        - **Kullanılabilir** (kullanıcılar isteğe bağlı olarak şirket portalından yükler)
        - **Uygulanamaz** (uygulama yüklenmedi veya şirket portalında gösterilmiyor)
        - **Kaldır** (uygulama hedeflenen cihazlardan kaldırılacak)
    - **Son Tarih** - Gerekli yüklemeler için, uygulamanın ne zaman dağıtılacağını seçin. Önceden tanımlanmış değerler arasından seçim yapabilir veya **Özel**’i seçip kendi son tarihinizi yapılandırabilirsiniz.

5. Dağıttığınız uygulama mobil uygulama yönetimi ilkesiyle yapılandırılabiliyorsa, **Mobil Uygulama Yönetimi** sayfası görüntülenir. Bu sayfada, bu uygulamayla ilişkilendirmek istediğiniz mobil uygulama yönetimi ilkesini seçin.

    [Hangi Microsoft uygulamalarının mobil uygulama yönetimi ilkeleriyle uyumlu olduğuna bakın.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Dağıttığınız uygulama Intune VPN profilleriyle uyumluysa, **VPN Profili** sayfası görüntülenir. Bu sayfada, iOS uygulamalarını dağıttığınız bir VPN profiliyle ilişkilendirmeyi seçebilirsiniz. Uygulama başlatıldığında VPN bağlantısı otomatik olarak açılır. Bir VPN profilini kullanıma sunmak için **Uygulama Başına VPN** profil ayarının etkinleştirilmesi gerekir.
 Profilleri uygulamalarla ilişkilendirme desteği dahil olmak üzere VPN profillerini yapılandırma hakkında bilgi için bkz. [Kullanıcıların Microsoft Intune ile VPN profilleri kullanarak işlerine bağlanmasına yardımcı olun](vpn-connections-in-microsoft-intune.md).

## Örnek

Bu örnekte, uygulamayı bir iOS cihazına **Kullanılabilir** olarak dağıtıyorsunuz.
Uygulama kullanıcıların cihazında şirket portalında görüntülenir ve kullanıcılar uygulamayı oradan yükleyebilir. Örneğin bu ekran görüntüsünde, iOS için Bing uygulaması **Dış Bağlantı** yükleme türü kullanılarak dağıtılmıştır, özel bir simgesi vardır ve **Bunu özel bir uygulama olarak görüntüle ve şirket portalında vurgula** seçeneği belirtilmiştir.  
![iOS kullanılabilir uygulaması](./media/available-install-on-iOS.png)

Uygulamayı bir iOS cihazına **Gerekli** olarak dağıttıysanız, kullanıcı bir uygulamanın yüklemeye hazır olduğuna ilişkin bir bildirim alır. Örneğin bu ekran görüntüsünde, iOS için Çalışma Klasörleri uygulaması **Uygulama mağazasından yönetilen iOS uygulaması** yükleme türü kullanılarak dağıtılmıştır.  
![iOS gerekli uygulaması](./media/iOS-Required-install.PNG)

## Sonraki adımlar

Uygulamayı dağıttıktan sonra, ilerleme durumunu izlemek istersiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları izleme](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


