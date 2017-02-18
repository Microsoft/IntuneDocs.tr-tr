---
title: "Uygulamaları dağıtma | Microsoft Docs"
description: "Bu konu başlığı altındaki bilgileri, uygulamaları Microsoft Intune’la dağıtmanıza yardımcı olması için kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 32653a46d8758eac5b884f4f6f7a2e07447c1e36

---
# <a name="deploy-apps-in-microsoft-intune"></a>Microsoft Intune'da uygulamaları dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altındaki bilgileri, uygulamaları Microsoft Intune’la dağıtmanıza yardımcı olması için kullanın.


## <a name="deploy-an-app"></a>Uygulamayı dağıtma
Bu yordamda, seçilen cihaz veya kullanıcı gruplarına bir uygulama dağıtacaksınız.

### <a name="to-deploy-an-app"></a>Uygulamayı dağıtmak için

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

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a>Örnek

Bu örnekte, uygulamayı bir iOS cihazına **Kullanılabilir** olarak dağıtıyorsunuz.
Uygulama, kullanıcıların cihazlarında şirket portalında görünür ve kullanıcılar tarafından buradan yüklenebilir.

Örneğin bu ekran görüntüsünde, özel bir simgeye sahip **Dış Bağlantı** yükleme türü kullanılarak iOS için Bing uygulaması dağıtılmış. **Şirket portalında bu uygulamayı öne çıkan uygulama olarak görüntüleyin ve vurgulayın** seçeneği belirlenmiş.  
![iOS kullanılabilir uygulaması](./media/available-install-on-iOS.png)

Uygulamayı bir iOS cihazına **Gerekli** olarak dağıttıysanız, kullanıcı bir uygulamanın yüklemeye hazır olduğuna ilişkin bir bildirim alır. Örneğin bu ekran görüntüsünde, iOS için Çalışma Klasörleri uygulaması **Uygulama mağazasından yönetilen iOS uygulaması** yükleme türü kullanılarak dağıtılmıştır.  
![iOS gerekli uygulaması](./media/iOS-Required-install.PNG)

## <a name="next-steps"></a>Sonraki adımlar

Uygulamayı dağıttıktan sonra, ilerleme durumunu izleyebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları izleme](monitor-apps-in-microsoft-intune.md).



<!--HONumber=Dec16_HO5-->


