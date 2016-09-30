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
ms.sourcegitcommit: c4d05b9ba7249e4068d21480b1c9db342277757e
ms.openlocfilehash: 687a102ccb34cb7acfaab1e8a1d4b67cb54b9e92


---

# Lookout for Work uygulamalarını yapılandırma ve dağıtma
Bu makalede, kayıtlı olan ve Android 4.1 veya üstünü çalıştıran cihazlarda Lookout for Work uygulamasının nasıl yapılandırılacağı ve dağıtılacağı açıklanır.

* **1. Adım:**   [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar**’a gidin ve **Uygulama Ekleme**’yi seçin.   
* **2. Adım:**   Yayımcının **Yazılım Kurulumu** sayfasında **Dış bağlantı**’yı seçin ve şu URL'yi belirtin: https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Yönetilen tarayıcı gerekliliğine yönelik kutuya tıklamayın.

* **3. Adım:**   **Yazılım açıklaması** sayfasında aşağıdaki bilgileri doldurun:
  * **Yayımcı:** Lookout Mobile Security
  * **Adı:**   Lookout for Work
  * **Açıklama:**  Lookout cihazınızı güvenli tutmak için mobil tehditlere karşı en iyi korumayı sunar. Lookout uygulaması cihaza yüklendiğinde, uygulama cihazınızı tehditlerden korur ve herhangi bir tehdit bulunursa sizi ve şirket yöneticinizi uyarır.
  * **Kategori:** Bilgisayar Yönetimi
* **4. Adım:** İşlemin başarıyla tamamlanmasından sonra **Microsoft Intune’a veri yükleme başarıyla tamamlandı** iletisini görürsünüz.

Intune yönetici konsolunda **Uygulamalar**’a tıkladığınızda artık Lookout for Work uygulamasını listede görürsünüz ![Lookout for Work uygulamalarını listede gösteren Intune yönetici konsolu uygulamaları sayfasının ekran görüntüsü](../media/mtp/lookout-app-listed-intune-console.png)

**Uygulamayı kullanıcılara dağıtmak için**, yukarıdaki ekranda gösterilen Lookout for Work uygulamasını seçin ve ardından **Dağıtımı Yönet**’i seçin.

Lookout MTP konsolundaki Kayıt Yönetimi seçeneğine eklenmiş olan kullanıcıları seçmeniz gerekir.  Lookout MTP’ye kullanıcı grupları ekleme hakkında daha fazla bilgi için [Lookout MTP bölümü ile aboneliğinizi yapılandırma](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) bölümünün 3. Adımına göz atın.
>[!IMPORTANT]
> Intune uygulama dağıtım sihirbazı, Azure AD kullanıcı gruplarını tanımaz ve bunun yerine Intune kullanıcı gruplarını kullanır; dolayısıyla [bu](plan-your-user-and-device-groups.md) konu başlığı altında açıklandığı gibi, Lookout MTP konsoluna kayıtlı Azure AD kullanıcı grubunu temel alan bir Intune kullanıcı grubu oluşturmalısınız.

**Gerekli Yükleme** seçeneğini belirleyerek Lookout uygulamasının kullanıcı cihazında yüklü olmasını zorunlu hale getirin.


Dağıtım için **Gerekli Yükleme** seçeneği belirlendiğinde, Intune, Lookout for Work uygulamasını cihaza gönderir.   

Kullanıcı cihazda Lookout for Work’ü açtığında uygulamayı etkinleştirmeleri ve Azure Active Directory seçeneği ile Oturum Açmaları istenir. Son kullanıcı akışı ile ayrıntılı bir rehber aşağıdaki konularda bulunabilir:

* [Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Lookout for Work’ün Android cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Sonraki adımlar
* [Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO3-->


