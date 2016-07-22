---
title: "Uygulamaları güncelleştirme | Microsoft Intune"
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
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 0581d1476fba5bedcdd4446df20f8f92b151f41b
ms.openlocfilehash: 9e5b8f4a467e8e58cc2f8fa495b5f008eee7e35b


---

# Microsoft Intune’u kullanarak uygulamaları güncelleştirme
Microsoft Intune, uygulama güncelleştirmelerini yönetmenize yardımcı olabilir. Yeni bir sürüm gerektiğinde uygulamaları nasıl güncelleştirebileceğinizi anlamak için, bu konu başlığı altında verilen bilgileri kullanın.

## Uygulamaları güncelleştirme
Dağıttığınız bir uygulamanın yeni sürümü yayımlandığında, Intune uygulamanın yeni sürümünü güncelleştirip dağıtmanıza imkan tanır. Bir dağıtımı yalnızca aynı uygulamanın daha yeni bir sürümüyle değiştirebilirsiniz (aynı tanımlayıcıyı kullanarak). Bir dağıtımı farklı bir uygulama paketiyle güncelleştirmek için uygulama güncelleştirmelerini kullanamazsınız.

> [!IMPORTANT]
> Bir uygulamayı **Zorunlu yükleme** dağıtım eylemiyle dağıtıp daha sonra dağıtım eylemini **Kullanılabilir yükleme**olarak değiştirdiğinizde, dağıtım değişikliği yapılmadığı sürece uygulama güncelleştirmeleri uygulamanın yüklü olduğu cihazlara otomatik olarak yüklenmez. Bu sorunu gidermek için aşağıdakileri yapabilirsiniz:
> 
> -   Cihaz kullanıcısının şirket portalına gitmesini, yüklü uygulamayı seçmesini ve **Yükle**'yi seçmesini isteyin.
> -   Dağıtım eylemini **Kaldır**olarak değiştirin ve uygulama kaldırıldıktan sonra uygulamayı **Kullanılabilir yükleme**dağıtım eylemiyle yeniden dağıtın.

### Bir uygulamayı güncelleştirmek için

1.  [Microsoft Intune yönetici konsolunda](https://manage.microsoft.com) **Uygulamalar** &gt; **Uygulamalar**’ı seçin.

2.  **Uygulamalar** listesinde güncelleştirmek istediğiniz uygulamayı seçin ve ardından **Düzenle**'yi seçin.

3.  **Yazılım Düzenleme** sihirbazında uygulama paketinin yeni ayrıntılarını belirtin.

4.  Bitirdiğinizde, **Güncelleştir**’i seçin.

Cihazlar kullanılabilir uygulamaları bir daha denetlediğinde uygulama en son sürüme otomatik olarak güncelleştirilecektir.
Bir uygulama paketinden yüklenen uygulamalar için (iş koşu uygulamaları), uygulamanın aynı tanımlayıcısı olduğu sürece, hem zorunlu hem de kullanılabilir uygulamalar için uygulama otomatik olarak yükseltilir.
Bir mağaza bağlantısı olarak dağıtılan uygulamalar için, güncelleştirme uygulamanın çıktığı mağaza tarafından yönetilir.






<!--HONumber=Jun16_HO3-->


