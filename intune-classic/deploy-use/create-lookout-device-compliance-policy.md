---
title: Cihaz koruma kuralını etkinleştirme
description: Cihaz uyumluluk ilkesinde mobil tehdit koruması kuralını etkinleştirin.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b39f7cac8c09813eb9db94e761ec6fa6ab53c7a0
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a>Intune'da Lookout cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Lookout Mobile Threat Defense ile Intune mobil cihazlardaki tehditleri algılamanıza ve bu cihazlardaki riski değerlendirmenize olanak tanır. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir uyumluluk ilkesi oluşturabilirsiniz. Ardından cihaz uyumluluğuna dayalı olarak hizmetlere erişimi engellemek için koşullu erişim ilkesini kullanabilirsiniz.

Lookout Mobile Threat Defense ile uyumluluk ilkesinin önkoşulları:

- [Lookout Mobile Threat Defense aboneliğini ayarlama](setup-your-lookout-mtd-subscription.md)
- [Intune’da Lookout bağlantısını etkinleştirme](enable-lookout-mtd-connection.md)
- [Lookout for Work uygulamasını yapılandırma ve dağıtma](configure-deploy-lookout-for-work-app.md)

Lookout Mobile Threat Defense kurulumunun bir parçası olarak, [Lookout konsolunda](https://aad.lookout.com) çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturulur. Intune uyumluluk ilkesinde izin verilen en yüksek tehdit düzeyi ayarlanır.

1. [Intune yönetim konsolunda](https://manage.microsoft.com), **Uyumluluk İlkeleri** sayfasına gidin. Mevcut bir uyumluluk ilkesi kullanabilir veya yeni bir tane oluşturabilirsiniz. **Cihaz Durumu**’na gidin ve **Cihaz Tehdit Koruması**’nı etkinleştirin.
   ![](../media/mtp/mtp-compliance-policy-rule.png) üzerindeki cihaz tehdit koruması kuralı ayarını gösteren ekran görüntüsü

2. **İzin verilen en yüksek tehdit düzeyini** seçin:
   * **Hiçbiri (Güvenli)**: Bu, en güvenli ayardır.  Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir.  Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir.  
   * **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
   * **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
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
