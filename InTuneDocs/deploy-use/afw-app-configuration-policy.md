---
title: "Android for Work uygulama yapılandırma ilkesi | Microsoft Docs"
description: "Kullanıcılar bir Android for Work uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 008c0d20312e90f3897c3da8ae2226e3e2595225
ms.openlocfilehash: 6cb6b4b989d88289c5dffb693f98198ba6439aae


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Microsoft Intune’da Android for Work uygulamalarını mobil uygulama yapılandırma ilkeleri ile yapılandırma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Kullanıcılar bir iOS uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

-   Özel bağlantı noktası numarası.

-   Dil ayarları.

-   Bir şirket logosu gibi marka ayarları.

Bu ayarlar kullanıcılar tarafından hatalı girildiği takdirde, yardım masanız üzerindeki yük artabilir ve uygulamalara geçiş yavaşlayabilir.

Mobil uygulama yapılandırma ilkeleri, kullanıcılarınız uygulamayı çalıştırmadan önce bu ayarları kullanıcılara dağıtmanıza imkan vererek bu sorunları ortadan kaldırmanıza yardımcı olabilir. Daha sonra ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez.

Uygulama yapılandırma ilkelerinden yararlanmak için uygulama geliştiricisinin kurumsal uygulama yapılandırmalarını, bunları oluşturduğunda kullanıma sunması gerekir. Örneğin, Google Chrome varsayılan yer işaretlerini, izin verilen ve verilmeyen siteleri ve daha fazlasını ayarlamanıza olanak tanıyan ayarları kullanıma sunar. Bu ayarların desteklenip desteklenmediğini görmek ve bunların ilkede nasıl belirtileceğini öğrenmek için uygulama geliştiricisine başvurun.

Yapılandırmak istediğiniz uygulamayı dağıttığınız kullanıcılara uygulama yapılandırma ilkesini de dağıtırsınız. İlke ayarları uygulama her çalıştırıldığında kullanılır.

## <a name="configure-a-mobile-app-configuration-policy"></a>Mobil uygulama yapılandırma ilkesi yapılandırma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **İlke** &gt; **Genel Bakış** &gt; **İlke Ekle**’yi seçin.

2.  İlkeler listesinde, **Android for Work**’ü genişletin, **Mobil Uygulama Yapılandırma İlkesi (Android for Work)** seçin ve **İlke Oluştur** seçeneğini belirleyin.

    > [!TIP]
    > Bu ilke türü için yalnızca özel ayarlar yapılandırabilirsiniz. Önerilen ayarlar kullanılamaz.

3.  **İlke Oluştur** sayfasının **Genel** bölümünde, mobil uygulama yapılandırma ilkesi için bir ad ve isteğe bağlı bir açıklama sağlayın.

4. Sayfanın **Mobil Uygulama Yapılandırma İlkesi** kısmında, aşağıdaki bilgileri belirtin:
    - **Bu yapılandırmanın geçerli olduğu uygulamanın Paket Kimliği** - Paket Kimliği uygulama URL’sinin Google Play sayfasındaki “id=” bölümünde bulunabilir. Örneğin, Microsoft Excel uygulamasının paket kimliği **com.microsoft.office.excel**’dir.
    - Metin kutusunda, yapılandırmak istediğiniz uygulama ayarlarına yönelik verileri girin. Bu ayarları uygulama tedarikçisinden alırsınız. Bu ayarları tüm uygulamalar desteklemez.
5.  Girdiğiniz verilerin geçerli bir özellik listesi biçiminde olduğundan emin olmak için **Doğrula**’ya tıklayın.

    > [!IMPORTANT]
    > **Doğrula**’ya tıkladığınızda, Intune girdiğiniz yapılandırma verilerinin geçerli bir biçimde olup olmadığını denetler. Verilerin, ilişkilendirildiği uygulama ile çalışıp çalışmayacağını denetlemez.

6.  İşiniz bittiğinde **İlkeyi Kaydet**‘e tıklayın.

Yeni ilke **Yapılandırma İlkeleri** düğümünde görüntülenir.


## <a name="deploy-the-app-configuration-policy"></a>Uygulama yapılandırma ilkesini dağıtma
Bir mobil uygulama yapılandırma ilkesi oluşturduktan sonra, bunu ayarların geçerli olacağı uygulamanın kullanıcılarına dağıtmanız gerekir.

İlke dağıtma hakkında bilgi edinmek için bkz. [yapılandırma ilkesi dağıtma](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)

Android for Work cihazlara uygulama dağıtma hakkında bilgi edinmek için bkz. [Intune ile Android for Work uygulamaları dağıtma](android-for-work-apps.md).

Dağıtılan uygulama bir cihazda çalıştırıldığında, mobil uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

> [!TIP]
> Her uygulama için bir kullanıcıya yalnızca bir uygulama yapılandırma ilkesi dağıtın.



<!--HONumber=Jan17_HO4-->


