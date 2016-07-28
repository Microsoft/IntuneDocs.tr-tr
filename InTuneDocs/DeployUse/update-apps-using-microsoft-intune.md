---
title: "Uygulamaları güncelleştirme | Microsoft Intune"
description: "Yeni bir sürüm gerektiğinde uygulamaları nasıl güncelleştirebileceğinizi anlamak için, bu konu başlığı altında verilen bilgileri kullanın."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: bb077902e33d6ab18dea33a6ab2d1ff9a70ce937


---

# Microsoft Intune’u kullanarak uygulamaları güncelleştirme
Microsoft Intune, uygulama güncelleştirmelerini yönetmenize yardımcı olabilir. Yeni bir sürüm gerektiğinde uygulamaları nasıl güncelleştirebileceğinizi anlamak için, bu konu başlığı altında verilen bilgileri kullanın.

## Uygulamaları güncelleştirme
Dağıttığınız bir uygulamanın yeni sürümü yayımlandığında, Intune uygulamanın yeni sürümünü güncelleştirip dağıtmanıza imkan tanır. Bir dağıtımı yalnızca aynı uygulamanın daha yeni bir sürümüyle değiştirebilirsiniz (aynı tanımlayıcıyı kullanarak). Bir dağıtımı farklı bir uygulama paketiyle güncelleştirmek için uygulama güncelleştirmelerini kullanamazsınız.

### Uygulama tanımlayıcıları
Uygulama tanımlayıcısı, uygulamayı benzersiz olarak tanımlayan bir özelliktir. Tanımlayıcısı aynı olan birden çok uygulama kopyasını yükleyemezsiniz. Örneğin:

- **iOS** - Paket kimliği (örneğin: com.microsoft.excel)
- **Android** - Paket kimliği (örneğin: com.microsoft.excel)
- **Windows Phone** - (xap yükleyicisi) Ürün kimliğini (GUID) kullanın
- **Windows** - (appx/appxbundle), Paket Tam Adı’nı kullanın



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






<!--HONumber=Jul16_HO3-->


