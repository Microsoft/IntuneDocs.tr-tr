---
# required metadata

title: Microsoft Intune’da uyumluluk ilkesini dağıtma ve izleme | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da cihaz uyumluluk ilkesini dağıtma ve izleme
## Uyumluluk ilkesini dağıtma
[Oluşturduğunuz](create-a-device-compliance-policy-in-microsoft-intune.md) uyumluluk ilkesini kuruluşunuzdaki bir veya daha fazla kullanıcı ya da cihaz grubuna dağıtın.

1.  **İlke** çalışma alanında, dağıtmak istediğiniz ilkeyi ve ardından **Dağıtımı Yönet**’i seçin.
![En üstte Dağıtımı Yönet menü seçeneğinin gösterildiği uyumluluk ilkesi sayfasının ekran görüntüsü](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  **Dağıtımı Yönet** iletişim kutusunda ilkeyi dağıtmak istediğiniz bir veya daha fazla grup seçin ve ardından **Ekle > Tamam**'a tıklayın.
![Dağıtımı Yönet iletişim kutusunun ekran görüntüsü Uyumluluk ilkesini kullanıcılara ve/veya cihazlara dağıtabilirsiniz. Daha önce oluşturduğunuz ve Intune ile eşitlenen Active Directory gruplarını kullanın ya da Intune konsolunda bu grupları el ile oluşturun.

İlkeleri dağıtma hakkında daha fazla bilgi edinmek için, bkz. [Yapılandırma ilkesini dağıtma](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) Dikkat etmeniz gereken ilkeyle ilgili sorunları belirlemek için **İlke** çalışma alanının **Genel Bakış** sayfasında durum özeti ve uyarılarını kullanın.

> [!IMPORTANT]Ayrıca, **Pano** çalışma alanında bir durum özeti görüntülenir.

## Bir uyumluluk ilkesi dağıtmadıysanız ve sonra bir Exchange koşullu erişim ilkesini etkinleştirirseniz, tüm hedeflenen cihazların erişimine izin verilir.
Intune ilke çakışmalarını çözümleme Bir cihaza birden çok Intune ilkesi uygulandığında ilke çakışmaları olabilir.

-   İlke ayarları çakışırsa, Intune tüm çakışmaları aşağıdaki kuralları kullanarak çözer:

-   Çakışan ayarlar bir Intune yapılandırma ilkesine ve bir uyumluluk ilkesine aitse, yapılandırma ilkesindeki ayarlar daha güvenli olsa bile uyumluluk ilkesindeki ayarlar yapılandırma ilkesindeki ayarlara göre önceliklidir.

## Birden çok uyumluluk ilkesi dağıttıysanız bu ilkelerin en güvenli olanı kullanılır.

#### Uyumluluk ilkesini izleme

1.  Uyumluluk ilkesine uymayan cihazları görüntülemek için

2.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Gruplar > Tüm Cihazlar**’ı seçin.

3.  Cihazlar listesinde bir cihazın adına çift tıklayın.

4.  İlgili cihaza ilişkin ilkelerin listesini görmek için **İlke** sekmesini seçin.
![**Filtreler** açılan listesinden **Uyumluluk ilkesine uygun değil** öğesini seçin.](./media/intune-sa-3e-view-device-noncompliance.png)

#### Filtreler listesindeki seçenekleri gösteren ekran görüntüsü

1.  Durum Kanıtlama Raporlarını görüntülemek için

2.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Raporlar**’ı seçin. **Durum Kanıtlama Raporu - Yeni rapor oluştur** sayfasında Intune tarafından toplanan tüm Windows 10 durum kanıtlama verileriyle birlikte bir raporu görüntüleyebilirsiniz. Ayrıca filtreleri kullanarak verilerin bir alt kümesi ile rapor oluşturabilirsiniz.


## Filtreler cihaz türüne, işletim sistemine veya yalnızca bir veri noktaları alt kümesine göre uygulanabilir.
Sonraki adımlar

[Kuruluşunuzdaki hizmetlere erişimi denetlemek için artık koşullu erişim ilkeleriyle birlikte uyumluluk ilkesini kullanabilirsiniz.](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


### E-posta ve O365 hizmetlerine erişimi kısıtlama
[Ayrıca bkz.](introduction-to-device-compliance-policies-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->


