---
title: "Cihaz koruma kuralını uyumluluk ilkesinde etkinleştirme | Microsoft Intune"
description: "Cihaz uyumluluk ilkesinde mobil tehdit koruması kuralını etkinleştirin."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 761372b2c8b81699bc2584ab1ef8d0f9d523abe9


---

# Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme
Lookout mobil tehdit koruması özelliği ile Intune, size cihazda mobil tehditleri tespit etme ve bir risk değerlendirmesi yapma becerisi sağlar.  
Uyumluluk ilkesi kuralı, cihazın ilkenizle uyumlu olup olmadığını belirlemek için bu risk değerlendirmesini kullanmanıza olanak tanır. Ardından Exchange, SharePoint ve cihaz uyumluluğuna dayalı diğer hizmetlere izin vermek veya bunları engellemek için koşullu erişim ilkesini kullanabilirsiniz.

Lookout MTP tehdit algılama özelliğinin cihaza yönelik uyumluluk ilkesini etkilemesini sağlamak için:

1.  **Cihaz Tehdit Koruması** kuralının uyumluluk ilkesinde etkinleştirilmesi gerekir.

2.  Intune yönetici konsolundaki **Lookout Durumu** sayfasının **Etkin** olarak görünmesi gerekir. Lookout tümleştirmesinin nasıl etkinleştirileceğine ilişkin daha fazla bilgi ve yönergeler için [Intune'da Lookout MTP bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md) konusuna göz atın.


## Cihaz tehdit koruması kuralını yapılandırın

Uyumluluk ilkesinde cihaz tehdit koruması kuralı oluşturmadan önce [Lookout MTP aboneliğinizi oluşturmanızı](set-up-your-subscription-with-lookout-mtp.md), [Intune'da Lookout bağlantısını etkinleştirmenizi](enable-lookout-mtp-connection-in-intune.md) ve [Lookout for Work uygulamasını yapılandırmanızı](configure-and-deploy-lookout-for-work-apps.md) öneririz. Uyumluluk kuralı, kurulum tamamlandıktan sonra devreye girer.

Cihaz tehdit koruması kuralını etkinleştirmek için mevcut bir uyumluluk ilkesi kullanabilir veya yeni bir tane oluşturabilirsiniz.

Lookout MTP kurulumunun bir parçası olarak, [Lookout MTP konsolunda](https://aad.lookout.com), çeşitli tehditleri yüksek, orta ve düşük düzeylerde sınıflandıran bir ilke oluşturulur. Intune uyumluluk ilkesinde izin verilen en yüksek tehdit düzeyini ayarlamak için tehdit düzeyini kullanırsınız.

Intune yönetim konsolundaki uyumluluk ilkesi sayfasında bulunan **Cihaz Durumu**’na giderek **Cihaz Tehdit Koruması** kuralını aç/kapa seçeneğini kullanarak etkinleştirin. Ardından izin verilen en yüksek tehdit düzeyini seçin. Bu düzey aşağıdakilerden biri olabilir:
* **Hiçbiri (güvenli)**: Bu en güvenli ayardır.  Bu, cihazda herhangi bir tehdit olamayacağı anlamına gelir.  Cihazın herhangi bir tehdit düzeyine sahip olduğu algılanırsa uyumlu değil olarak değerlendirilir.  
* **Düşük**: Yalnızca düşük düzeyli tehditler mevcutsa cihaz uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
* **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Cihazda yüksek düzeyde tehditler algılanırsa, uyumlu değil olarak belirlenir.
* **Yüksek**: Bu en az güvenli seçenektir. Temel olarak bu, tüm tehdit düzeylerine izin verir ve bu çözüm sadece bildirme amacıyla kullandığınızda faydalıdır.

![cihaz tehdit koruması kuralı ayarını gösteren ekran görüntüsü ](../media/mtp/mtp-compliance-policy-rule.png)

![cihaz tehdit koruması kuralı ayarına yönelik tehdit düzeyi seçeneğini gösteren ekran görüntüsü](../media/mtp/mtp-compliance-policy-setting.png)

O365 ve diğer hizmetler için koşullu erişim ilkeleri oluşturursanız, yukarıdaki uyumluluk değerlendirmesi dikkate alınır ve uyumlu olmayan cihazların erişimi tehdit giderilene kadar engellenir.

Bir cihazın uyumluluk durumunu Intune yönetici konsolunun cihazlar sayfasında görebilirsiniz.

![Intune yönetici konsolundaki cihazlar sayfasında bir cihazın uyumluluk durumunu gösteren ekran görüntüsü](../media/mtp/mtp-device-status-intune-console.png)

## Sonraki adımlar
* Koşullu erişim ilkesi oluşturma
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange Şirket İçi](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Kurumsal Çevrimiçi](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


