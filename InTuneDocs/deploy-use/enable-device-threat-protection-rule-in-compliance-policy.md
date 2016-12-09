---
title: "Cihaz koruma kuralını uyumluluk ilkesinde etkinleştirme | Microsoft Intune"
description: "Cihaz uyumluluk ilkesinde mobil tehdit koruması kuralını etkinleştirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: efddf7645d0548c842ae8aa3b1ca5222023913b5


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme
Lookout mobil tehdit koruması özelliği ile Intune, size cihazda mobil tehditleri tespit etme ve bir risk değerlendirmesi yapma becerisi sağlar. Bir uyumluluk ilkesi kuralı oluşturup, cihazın uyumlu olup olmadığını belirlemek için risk değerlendirmesi ekleyebilirsiniz. Ardından Exchange, SharePoint ve cihaz uyumluluğuna dayalı diğer hizmetlere erişim izin vermek veya erişimi engellemek için koşullu erişim ilkesini kullanabilirsiniz.

Lookout cihaz tehdit algılama özelliğinin cihaza yönelik uyumluluk ilkesini etkilemesini sağlamak için:

* **Cihaz Tehdit Koruması** kuralının uyumluluk ilkesinde etkinleştirilmesi gerekir.

* **Intune yönetici konsolundaki** **Lookout Durumu** sayfasının **Etkin** olarak görünmesi gerekir. Lookout tümleştirmesinin nasıl etkinleştirileceğine ilişkin daha fazla bilgi ve yönergeler için [Intune'da Lookout MTP bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md) konusuna göz atın.


Uyumluluk ilkesinde cihaz tehdit koruması kuralı oluşturmadan önce [aboneliğinizi Lookout cihaz tehdit koruması için ayarlamanız](set-up-your-subscription-with-lookout-mtp.md), [Intune'da Lookout bağlantısını etkinleştirmeniz](enable-lookout-mtp-connection-in-intune.md) ve [Lookout for Work uygulamasını yapılandırmanız](configure-and-deploy-lookout-for-work-apps.md) önerilir. Uyumluluk kuralı, ancak kurulum tamamlandıktan sonra devreye girer.

Cihaz tehdit koruması kuralını etkinleştirmek için mevcut bir uyumluluk ilkesi kullanabilir veya yeni bir tane oluşturabilirsiniz.

Lookout cihaz tehdit koruması kurulumunun bir parçası olarak, [Lookout konsolunda](https://aad.lookout.com) çeşitli tehditleri yüksek, orta ve düşük düzeylerde sınıflandıran bir ilke oluşturulur. Intune uyumluluk ilkesinde izin verilen en yüksek tehdit düzeyini ayarlamak için tehdit düzeyini kullanırsınız.

**Intune yönetim konsolundaki** **Uyumluluk İlkeleri** sayfasında bulunan **Cihaz Sistem Durumu**’na giderek **Cihaz Tehdit Koruması** kuralını aç/kapa seçeneğini kullanarak etkinleştirin. Ardından izin verilen en yüksek tehdit düzeyini seçin. Bu düzey aşağıdakilerden biri olabilir:
* **Hiçbiri (güvenli)**: Bu en güvenli ayardır.  Bu, cihazda herhangi bir tehdit olamayacağı anlamına gelir.  Herhangi bir düzeyde tehdit bulunduğunda, cihaz uyumsuz olarak değerlendirilir.  
* **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
* **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumlu değil olarak değerlendirilir.
* **Yüksek**: Bu en az güvenli seçenektir. Temel olarak, tüm tehdit düzeylerine izin verir ve yalnızca raporlama amacıyla kullandığınızda yararlı olabilir.

![cihaz tehdit koruması kuralı ayarını gösteren ekran görüntüsü ](../media/mtp/mtp-compliance-policy-rule.png)

![cihaz tehdit koruması kuralı ayarına yönelik tehdit düzeyi seçeneğini gösteren ekran görüntüsü](../media/mtp/mtp-compliance-policy-setting.png)

Office 365 ve diğer hizmetler için koşullu erişim ilkeleri oluşturursanız, yukarıdaki uyumluluk değerlendirmesi dikkate alınır ve uyumlu olmayan cihazların şirket kaynaklarına erişimi tehdit giderilene kadar engellenir.

Bir cihazın uyumluluk durumunu **Intune yönetici konsolunun** **Tüm Cihazlar** sayfasında görebilirsiniz.

![Intune yönetici konsolundaki cihazlar sayfasında bir cihazın uyumluluk durumunu gösteren ekran görüntüsü](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Sonraki adımlar
* Koşullu erişim ilkesi oluşturma
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange Şirket İçi](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Kurumsal Çevrimiçi](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


