---
title: "Uyumluluk ilkesini dağıtma ve izleme"
description: "Cihaz uyumluluk ilkesini dağıtmak ve izlemek için, bu konu başlığı altında verilen adım adım yönergeleri kullanın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ae914e755b809eda55abc5dc069c9ee2897d9ff4
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Microsoft Intune’da cihaz uyumluluk ilkesini dağıtma ve izleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Uyumluluk ilkesini dağıtma
[Oluşturduğunuz](create-a-device-compliance-policy-in-microsoft-intune.md) uyumluluk ilkesini kuruluşunuzdaki bir veya daha fazla kullanıcı grubuna dağıtın. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır.

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.
![En üstte Dağıtımı Yönet menü seçeneğinin gösterildiği uyumluluk ilkesi sayfasının ekran görüntüsü](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  **Dağıtımı Yönet** iletişim kutusunda ilkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin, sonra **Ekle** > **Tamam**’ı seçin.
![Dağıtımı Yönet iletişim kutusunun ekran görüntüsü](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Daha önce oluşturduğunuz ve Intune ile eşitlenen Active Directory gruplarını kullanın ya da Intune konsolunda bu grupları el ile oluşturun. İlke dağıtma hakkında daha fazla bilgi için bkz. [Yapılandırma ilkesi dağıtma](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Dikkat etmeniz gereken ilkeyle ilgili sorunları belirlemek için **İlke** çalışma alanının **Genel Bakış** sayfasında durum özeti ve uyarılarını kullanın. Ayrıca, **Pano** çalışma alanında bir durum özeti görüntülenir.

> [!IMPORTANT]
> Bir uyumluluk ilkesi dağıtmadıysanız ve sonra bir Exchange koşullu erişim ilkesini etkinleştirirseniz, tüm hedeflenen cihazların erişimi olur.

## <a name="monitor-the-compliance-policy"></a>Uyumluluk ilkesini izleme

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Uyumluluk ilkesine uymayan cihazları görüntülemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Gruplar** > **Tüm Cihazlar**’ı seçin.

2.  Cihazlar listesinde bir cihazın adına çift tıklayın.

3.  İlgili cihaza ilişkin ilkelerin listesini görmek için **İlke** sekmesini seçin.

4.  **Filtreler** açılır listesinden **Uyumluluk ilkesine uygun değil** öğesini seçin.
![Filtreler listesindeki seçenekleri gösteren ekran görüntüsü](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Durum kanıtlama raporlarını görüntülemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Raporlar**’ı seçin.

2.  **Durum Kanıtlama Raporu - Yeni rapor oluştur** sayfasında Intune tarafından toplanan tüm Windows 10 durum kanıtlama verileriyle birlikte bir raporu görüntüleyebilirsiniz. Ayrıca filtreleri kullanarak verilerin bir alt kümesi ile rapor oluşturabilirsiniz. Filtreler cihaz türüne, işletim sistemine veya yalnızca bir veri noktaları alt kümesine göre uygulanabilir.

## <a name="how-intune-resolves-policy-conflicts"></a>Intune ilke çakışmalarını nasıl çözümler?
Bir cihaza birden çok Intune ilkesi uygulandığında ilke çakışmaları olabilir. İlke ayarları çakışırsa, Intune tüm çakışmaları aşağıdaki kuralları kullanarak çözer:

-   Çakışan ayarlar bir Intune yapılandırma ilkesine ve bir uyumluluk ilkesine aitse, uyumluluk ilkesindeki ayarlar yapılandırma ilkesindeki ayarlara göre önceliklidir. Bu, yapılandırma ilkesindeki ayarlar daha güvenli olsa bile gerçekleşir.

-   Birden çok uyumluluk ilkesi dağıttıysanız, Intune bu ilkelerin en güvenli olanını kullanır.

## <a name="next-steps"></a>Sonraki adımlar
Kuruluşunuzdaki hizmetlere erişimi denetlemek için koşullu erişim ilkeleriyle birlikte uyumluluk ilkesini nasıl kullanacağınızı öğrenmek için bkz. [E-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).


### <a name="see-also"></a>Ayrıca bkz.
[Intune’da cihaz uyumluluk ilkelerine giriş](introduction-to-device-compliance-policies-in-microsoft-intune.md)
