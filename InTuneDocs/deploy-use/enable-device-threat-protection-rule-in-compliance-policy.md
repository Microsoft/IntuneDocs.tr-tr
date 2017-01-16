---
title: "Cihaz koruma kuralını uyumluluk ilkesinde etkinleştirme | Microsoft Docs"
description: "Cihaz uyumluluk ilkesinde mobil tehdit koruması kuralını etkinleştirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 80e96003c584c67cb6b0289a7e2ed1ff3a833c2c
ms.openlocfilehash: 3dea6c35d5fc035a5aef6dda52543b64cd5ce177


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Lookout mobil tehdit koruması ile Intune mobil cihazlardaki tehditleri algılamanıza ve bu cihazlardaki riski değerlendirmenize olanak tanır. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir uyumluluk ilkesi oluşturabilirsiniz. Ardından cihaz uyumluluğuna dayalı olarak hizmetlere erişimi engellemek için koşullu erişim ilkesini kullanabilirsiniz.

Lookout cihaz tehdit koruması ile uyumluluk ilkesinin önkoşulları:

- [Lookout cihaz tehdit koruması aboneliğini ayarlama](set-up-your-subscription-with-lookout-mtp.md)
- [Intune’da Lookout bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md)
- [Lookout for Work uygulamasını yapılandırma](configure-and-deploy-lookout-for-work-apps.md)

Lookout cihaz tehdit koruması kurulumunun bir parçası olarak, [Lookout konsolunda](https://aad.lookout.com) çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturulur. Intune uyumluluk ilkesinde izin verilen en yüksek tehdit düzeyi ayarlanır.

1. [Intune yönetim konsolunda](https://manage.microsoft.com), **Uyumluluk İlkeleri** sayfasına gidin. Mevcut bir uyumluluk ilkesi kullanabilir veya yeni bir tane oluşturabilirsiniz. **Cihaz Durumu**’na gidin ve **Cihaz Tehdit Koruması**’nı etkinleştirin.
  ![](../media/mtp/mtp-compliance-policy-rule.png) üzerindeki cihaz tehdit koruması kuralı ayarını gösteren ekran görüntüsü

2. **İzin verilen en yüksek tehdit düzeyini** seçin:
  * **Hiçbiri (Güvenli)**: Bu, en güvenli ayardır.  Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir.  Herhangi bir tehdit bulunduğunda, cihaz uyumsuz olarak değerlendirilir.  
  * **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  * **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumlu değil olarak değerlendirilir.
  * **Yüksek**: Bu en az güvenli seçenektir. Bu tüm tehdit düzeylerine izin verir ve Lookout mobil tehdit korumasını yalnızca raporlama amacıyla kullanır.

![cihaz tehdit koruması kuralı ayarına yönelik tehdit düzeyi seçeneğini gösteren ekran görüntüsü](../media/mtp/mtp-compliance-policy-setting.png)

Office 365 veya diğer hizmetler için koşullu erişim ilkeleri oluşturursanız bu uyumluluk değerlendirmesi dikkate alınır ve uyumlu olmayan cihazların bu hizmetlere erişimi tehdit giderilene kadar engellenir.

## <a name="monitor-device-threats"></a>Cihaz tehditlerini izleme
Bir cihazın uyumluluk durumunu görmek için [Intune yönetim konsoluna](https://manage.microsoft.com) giderek **Tüm Cihazlar**’ı görüntüleyin.

![Intune yönetici konsolundaki cihazlar sayfasında bir cihazın uyumluluk durumunu gösteren ekran görüntüsü](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Sonraki adımlar
* Koşullu erişim ilkesi oluşturma
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange Şirket İçi](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Kurumsal Çevrimiçi](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Dec16_HO4-->


