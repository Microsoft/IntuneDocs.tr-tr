---
title: Android for Work uygulama yapılandırma ilkesi
description: Kullanıcılar bir Android for Work uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 02/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7bebf6137b7378c52741195a1dce048caaa03e3d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Microsoft Intune’da Android for Work uygulamalarını mobil uygulama yapılandırma ilkeleri ile yapılandırma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Kullanıcılar bir iOS uygulamasını çalıştırdığında gerekebilecek ayarları sağlamak için Intune’daki mobil uygulama yapılandırma ilkelerini kullanın. Örneğin, bir uygulama kullanıcıların şunları belirtmesini gerektirebilir:

-   Özel bağlantı noktası numarası
-   Dil ayarları
-   Bir şirket logosu gibi marka ayarları

Ayarlar kullanıcılar tarafından hatalı girildiği takdirde, yardım masanız üzerindeki yük artabilir ve uygulamalara geçiş yavaşlayabilir.

Mobil uygulama yapılandırma ilkeleri, bu ayarları kullanıcılar uygulamayı çalıştırmadan önce cihazlara dağıtmanızı sağlar. Ayarlar otomatik olarak sağlanır ve kullanıcıların herhangi bir eylem yapması gerekmez.

Uygulama yapılandırma ilkelerinden yararlanmak için uygulama geliştiricisinin kurumsal uygulama yapılandırmalarını, bunları oluşturduğunda kullanıma sunması gerekir. Örneğin, Google Chrome varsayılan yer işaretlerini, izin verilen ve verilmeyen siteleri ve daha fazlasını ayarlamanıza olanak tanıyan ayarları kullanıma sunar. Bu ayarların desteklenip desteklenmediğini görmek ve bunların ilkede nasıl belirtileceğini öğrenmek için uygulama geliştiricisine başvurun.

Yapılandırmak istediğiniz uygulamayı dağıttığınız kullanıcılara uygulama yapılandırma ilkesini de dağıtırsınız. Uygulama ayarları, uygulama çalıştırıldığında uygulanır.

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

İlke dağıtma hakkında bilgi edinmek için bkz. [yapılandırma ilkesi dağıtma](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)

Android for Work cihazlara uygulama dağıtma hakkında bilgi edinmek için bkz. [Intune ile Android for Work uygulamaları dağıtma](android-for-work-apps.md).

Dağıtılan uygulama bir cihazda çalıştırıldığında, mobil uygulama yapılandırma ilkesinde yapılandırdığınız ayarlarla çalışır.

> [!TIP]
> Her uygulama için bir kullanıcıya yalnızca bir uygulama yapılandırma ilkesi dağıtın.
