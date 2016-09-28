---
title: "Lookout for Work uygulamasını dağıtma | Microsoft Intune"
description: "Android için Lookout for Work uygulamasını yapılandırın ve dağıtın."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Lookout for Work uygulamalarını yapılandırma ve dağıtma
Bu sürümde, Lookout for Work uygulaması 4.1 ve üzeri sürümleri çalıştıran Android cihazlarda desteklenir.
## Android
Bu bölümde, Intune'a kayıtlı Android cihazlar için Lookout for Work uygulamasının nasıl yapılandırılacağı ve dağıtılacağı anlatılmaktadır.  
* 1. Adım: [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar**’a giderek **Uygulamalar Ekleme**’yi seçin.   
* 2. Adım: Yayımcının **Yazılım Kurulumu** sayfasında, **Dış Bağlantı**’yı seçin ve aşağıdaki URL'yi belirtin: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Yönetilen tarayıcı gerekliliğine yönelik kutuya tıklamayın.

* 3. Adım: **Yazılım açıklaması** sayfasında aşağıdaki bilgileri doldurun:
  * **Yayımcı:** Lookout Mobile Security
  * **Adı:**   Lookout for Work
  * **Açıklama:**  Lookout cihazınızı güvenli tutmak için mobil tehditlere karşı en iyi korumayı sunar. Lookout uygulaması cihaza yüklendiğinde, uygulama cihazınızı tehditlerden korur ve herhangi bir tehdit bulunursa size ve şirket yöneticinize uyarı verir.
  * **Kategori:** Bilgisayar Yönetimi
* 4. Adım: İşlemin başarıyla tamamlanmasından sonra **Microsoft Intune’a veri yüklemesi başarıyla tamamlandı** iletisini görürsünüz.

Intune konsolunda **Uygulamalar**’a tıkladığınızda artık Lookout for Work uygulamasını listede görürsünüz ![Lookout for work uygulamalarını listede gösteren Intune yönetici konsolu uygulamaları sayfasının ekran görüntüsü](../media/mtp/lookout-app-listed-intune-console.png)

5. Adım: Bu noktada Intune, Lookout for work android uygulamasını nasıl dağıtacağını bilir.   Yukarıdaki ekranda gösterilen Lookout for Work uygulamasını ve ardından **Dağıtımı Yönet**’i seçerek uygulamayı kullanıcılara dağıtabilirsiniz.

Lookout MTP konsolundaki Kayıt Yönetimi seçeneğine eklenen kullanıcıları seçmeniz gerekir.  Lookout MTP’ye kullanıcı grupları ekleme hakkında daha fazla bilgi için [Lookout MTP bölümü ile aboneliğinizi yapılandırma](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) bölümünün 3. Adımına göz atın.
>[!IMPORTANT]
> Intune uygulama dağıtım Sihirbazı, Azure AD kullanıcı gruplarını tanımaz ve bunun yerine Intune kullanıcı gruplarını kullanır. Dolayısıyla [bu](plan-your-user-and-device-groups.md) bölümde açıklandığı üzere Lookout MTP konsolunda kayıtlı Azure AD kullanıcı grubuna dayalı bir Intune kullanıcı grubu oluşturmanız gerekir.

6. Adım: **Gerekli Yükleme** seçeneğini belirleyerek Lookout uygulamasının kullanıcı cihazında yüklü olmasını zorunlu hale getirin.

### Cihaz etkinleştirme
Dağıtım için **Gerekli Yükleme** seçeneği belirlendiğinde, Intune, Lookout for Work uygulamasını cihaza gönderir.   

Kullanıcı cihazda Lookout for Work’ü açtığında uygulamayı etkinleştirmeleri ve Azure Active Directory seçeneği ile Oturum Açmaları istenir. Son kullanıcı akışı ile ayrıntılı bir rehber aşağıdaki konularda bulunabilir:

* [Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Lookout for Work’ün Android cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Sonraki adımlar
* [Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->


