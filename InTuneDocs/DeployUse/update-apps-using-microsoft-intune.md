---
# required metadata

title: Uygulamaları güncelleştirme | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’u kullanarak uygulamaları güncelleştirme
Microsoft Intune, uygulama güncelleştirmelerini yönetmenize yardımcı olabilir. Yeni bir sürüm gerektiğinde uygulamaları nasıl güncelleştirebileceğinizi anlamak için, bu konu başlığı altında verilen bilgileri kullanın.

## Uygulamaları güncelleştirme
Dağıttığınız bir uygulamanın yeni sürümü yayımlandığında, Intune uygulamanın yeni sürümünü güncelleştirip dağıtmanıza imkan tanır. Bir dağıtımı yalnızca aynı uygulamanın daha yeni bir sürümüyle değiştirebilirsiniz (aynı tanımlayıcıyı kullanarak). Bir dağıtımı farklı bir uygulama paketiyle güncelleştirmek için uygulama güncelleştirmelerini kullanamazsınız.

> [!IMPORTANT]
> Bir uygulamayı **Zorunlu yükleme** dağıtım eylemiyle dağıtıp daha sonra dağıtım eylemini **Kullanılabilir yükleme**olarak değiştirdiğinizde, dağıtım değişikliği yapılmadığı sürece uygulama güncelleştirmeleri uygulamanın yüklü olduğu cihazlara otomatik olarak yüklenmez. Bu sorunu gidermek için aşağıdakileri yapabilirsiniz:
> 
> -   Cihaz kullanıcısının şirket portalına gitmesini, yüklü uygulamayı seçmesini ve **Yükle**'ye tıklamasını isteyin.
> -   Dağıtım eylemini **Kaldır**olarak değiştirin ve uygulama kaldırıldıktan sonra uygulamayı **Kullanılabilir yükleme**dağıtım eylemiyle yeniden dağıtın.

### Bir uygulamayı güncelleştirmek için

1.  [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Uygulamalar**’a tıklayın.

2.  **Uygulamalar** listesinde güncelleştirmek istediğiniz uygulamayı seçin ve ardından **Düzenle**'ye tıklayın.

3.  **Yazılım Düzenleme** sihirbazında uygulama paketinin yeni ayrıntılarını belirtin.

4.  İşiniz bittiğinde **Güncelleştir**'e tıklayın.

Cihazlar kullanılabilir uygulamaları bir daha denetlediğinde uygulama en son sürüme otomatik olarak güncelleştirilecektir.





<!--HONumber=May16_HO2-->


