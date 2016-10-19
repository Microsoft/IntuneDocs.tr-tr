---
title: "Uygulamaları dağıtma | Microsoft Intune"
description: "Bu konu başlığı altındaki bilgileri, uygulamaları Microsoft Intune’la dağıtmanıza yardımcı olması için kullanın."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b6a5e2435a3cdffeaf27b0045dee9b8263cdc7a
ms.openlocfilehash: 1e6e0656fb3da0d77dab10736e7b1607d77e6335

---
# Microsoft Intune'da uygulamaları dağıtma

Bu konu başlığı altındaki bilgileri, uygulamaları Microsoft Intune’la dağıtmanıza yardımcı olması için kullanın.


## Uygulamayı dağıtma
Bu yordamda, seçilen cihaz veya kullanıcı gruplarına bir uygulama dağıtacaksınız.

### Uygulamayı dağıtmak için

1. Yönettiğiniz uygulamaların listesini görmek için [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Uygulamalar**’a tıklayın.

2.  Dağıtmak istediğiniz uygulamayı seçin ve **Dağıtımı Yönet**'e tıklayın.

3.  *&lt;Uygulama adı&gt;* iletişim kutusunun **Grupları Seç** sayfasında, uygulamayı dağıtmak istediğiniz kullanıcı veya cihaz gruplarını seçin.

4.  **Dağıtım Eylemi** sayfasında aşağıdakileri yapılandırın:

    - **Onay** - Dağıtımın aşağıdakilerden hangisi olduğunu seçin:
        - **Gerekli** (zorunlu yükleme)
        - **Kullanılabilir** (kullanıcılar isteğe bağlı olarak şirket portalından yükler)
        - **Uygulanamaz** (uygulama yüklenmedi veya şirket portalında gösterilmiyor)
        - **Kaldır** (uygulama hedeflenen cihazlardan kaldırılır)
    - **Son Tarih** - Gerekli yüklemeler için uygulamanın ne kadar kısa sürede dağıtılacağını seçin. Önceden tanımlanmış değerler arasından seçim yapabilir veya **Özel**’i seçip kendi son tarihinizi yapılandırabilirsiniz.

5. Dağıttığınız uygulama mobil uygulama yönetimi ilkesiyle yapılandırılabiliyorsa, **Mobil Uygulama Yönetimi** sayfası görüntülenir. Bu sayfada, bu uygulamayla ilişkilendirmek istediğiniz mobil uygulama yönetimi ilkesini seçin.

    [Hangi Microsoft uygulamalarının mobil uygulama yönetimi ilkeleriyle uyumlu olduğuna bakın.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Dağıttığınız uygulama Intune VPN profilleriyle uyumluysa, **VPN Profili** sayfası görüntülenir. Bu sayfada, iOS uygulamalarını dağıttığınız bir VPN profiliyle ilişkilendirmeyi seçebilirsiniz. Uygulama başlatıldığında VPN bağlantısı otomatik olarak açılır. Bir VPN profilini kullanıma sunmak için **Uygulama Başına VPN** profil ayarının etkinleştirilmesi gerekir.
 Profilleri uygulamalarla ilişkilendirmeyle ilgili bilgiler dahil olmak üzere VPN profillerini yapılandırma hakkında bilgi edinmek için bkz. [Microsoft Intune’da VPN bağlantıları](vpn-connections-in-microsoft-intune.md).

## Örnek

Bu örnekte, uygulamayı bir iOS cihazına **Kullanılabilir** olarak dağıtıyorsunuz.
Uygulama, kullanıcıların cihazlarında şirket portalında görünür ve kullanıcılar tarafından buradan yüklenebilir.

Örneğin bu ekran görüntüsünde, özel bir simgeye sahip **Dış Bağlantı** yükleme türü kullanılarak iOS için Bing uygulaması dağıtılmış. **Şirket portalında bu uygulamayı öne çıkan uygulama olarak görüntüleyin ve vurgulayın** seçeneği belirlenmiş.  
![iOS kullanılabilir uygulaması](./media/available-install-on-iOS.png)

Uygulamayı bir iOS cihazına **Gerekli** olarak dağıttıysanız, kullanıcı bir uygulamanın yüklemeye hazır olduğuna ilişkin bir bildirim alır. Örneğin bu ekran görüntüsünde, iOS için Çalışma Klasörleri uygulaması **Uygulama mağazasından yönetilen iOS uygulaması** yükleme türü kullanılarak dağıtılmıştır.  
![iOS gerekli uygulaması](./media/iOS-Required-install.PNG)

## Sonraki adımlar

Uygulamayı dağıttıktan sonra, ilerleme durumunu izleyebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları izleme](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Aug16_HO5-->


