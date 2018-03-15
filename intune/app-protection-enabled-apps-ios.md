---
title: "Uygulama koruma ilkeleri içeren iOS uygulamaları"
titlesuffix: Microsoft Intune
description: "Koruma ilkelerine sahip bir iOS uygulamasından neler bekleyebileceğinizi öğrenin."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13833d41603e24e4471f0bb5fdda40d000f29a34
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Uygulama koruma ilkelerine sahip iOS uygulamaları için kullanıcı deneyimi hakkında bilgi edinin. Uygulama koruma ilkeleri, yalnızca uygulamalar çalışma bağlamında kullanıldığında uygulanır. Örneğin, bir iş hesabına sahip bir uygulamaya eriştiğinizde veya şirketinizin OneDrive konumunda kayıtlı dosyalara eriştiğinizde.
##  <a name="accessing-apps"></a>Uygulamalara erişme

Cihaz **Intune'a kayıtlı değilse**, kullanıcı uygulamayı ilk kez kullandığında uygulamayı yeniden başlatması istenir.  Uygulamaya uygulama koruma ilkelerinin uygulanabilmesi için yeniden başlatma gereklidir. Aşağıdaki ekran görüntüsü bunu Skype uygulamasını kullanarak göstermektedir:


![PIN istemi gösteren iOS cihazının ekran görüntüsü](./media/ios-pin-prompt.png)

**Yönetilmek üzere Intune’da kayıtlı cihazlarda**, kullanıcı uygulamasının artık yönetildiğini belirten bir ileti görürsünüz:

![PIN istemiyle şirketiniz tarafından yönetiliyor iletisini gösteren iOS cihazının ekran görüntüsü](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Birden çok kimlik destekli uygulamaları kullanma

Uygulama koruma ilkeleri, bir kullanıcı işle ilgili verilere erişmeye çalıştığında etkinleşir.  Kullanıcı kişisel kullanım için uygulamaya erişirse farklı davranışlar görebilirsiniz. 

Çoklu kimliği destekleyen uygulamalar için, Intune yalnızca bir kullanıcı iş verilerine eriştiğinde uygulama koruma ilkelerini uygular.  Örneğin, bir kullanıcı bir PIN istemi alabilir.  **Outlook uygulamasında**, kullanıcı uygulamayı başlattığında bir istem oluşur. **OneDrive uygulamasında**, kullanıcı iş hesabına yazdığında istem oluşur.  Microsoft **Word**, **PowerPoint** ve **Excel**’de, bir kullanıcı şirketin OneDrive belgelerine eriştiğinde bir istem oluşur.
##  <a name="managing-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune yalnızca, uygulama koruma ilkelerinin cihaz başına tek bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir veya engellenmeyebilir. Ancak her durumda, yalnızca uygulama koruma ilkelerini alan ilk kullanıcı, ilkeden etkilenir.
  * **Microsoft Word**, **Excel** ve **PowerPoint** ek bir kullanıcı hesabına erişimi engellemez. Ancak, kullanıcı hesabı uygulama koruma ilkelerinden etkilenmez.

  * **OneDrive ve Outlook uygulamaları** için, yalnızca bir iş hesabı kullanabilirsiniz.  Birden çok iş hesabının eklenmesi bu uygulamalarda engellenmiştir.  Bununla birlikte, bir kullanıcıyı bir cihazdan kaldırabilir ve ardından cihaza farklı bir kullanıcı ekleyebilirsiniz.

* Bir cihazda, uygulama koruma ilkeleri dağıtılmadan önce birden fazla kullanıcı hesabı bulunabilir. Bu durumda, uygulama koruma ilkelerinin dağıtıldığı ilk hesap, Intune uygulama koruma ilkeleri tarafından yönetilir.


Intune’un çoklu kullanıcı hesaplarını nasıl işlediğini öğrenmek için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor: **Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de uygulama koruma ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, uygulama koruma ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap uygulama koruma ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini sağlamak için, Kullanıcı A’nın, Şirket X kullanıcı hesabını kaldırması gerekir.
### <a name="adding-a-second-account"></a>İkinci hesap ekleme

iOS cihazı kullanıyorsanız, aynı cihaza ikinci bir iş hesabı eklemeye çalıştığınızda bir engelleme iletisi görebilirsiniz.  Hesaplar görüntülenir ve kaldırmak istediğiniz hesabı seçebilirsiniz.

![Engelleme iletisi ve Evet ile Hayır seçenekleri bulunan iletişim kutusunun ekran görüntüsü](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Sonraki adımlar
[Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Ayrıca bkz:
[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
