---
title: "MAM ilkeleri içeren iOS uygulamaları | Microsoft Docs"
description: "Bu konu başlığı altında, iOS uygulamanız mobil uygulama yönetimi ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b068da7685792757825a4bc0d555e28ee0168cb1
ms.openlocfilehash: f5a26d3d5ed060571892d91637dc12cae08f1a69


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 Bu konu başlığı altında, mobil erişim yönetimi (MAM) ilkeleri içeren uygulamalardaki kullanıcı deneyimi açıklanmıştır. MAM ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: Örneğin, kullanıcı iş hesabı kullanarak uygulamalara veya şirketinizin OneDrive iş konumunda depolanan dosyalara eriştiğinde.

##  <a name="access-apps"></a>Erişim uygulamaları

Cihaz **Intune'a kayıtlı değilse**, kullanıcı uygulamayı ilk kez kullandığında uygulamayı yeniden başlatması istenir.  Uygulamaya MAM ilkelerinin uygulanabilmesi için yeniden başlatma gereklidir. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

**Yönetilmek üzere Intune’da kayıtlı cihazlarda**, kullanıcı uygulamasının artık yönetildiğini belirten bir ileti görür:

![PIN istemiyle, uygulamanın şimdi şirketiniz tarafından yönetildiğini belirten iletiyi gösteren iOS cihazının ekran görüntüsü](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>Çoklu kimlik desteği olan uygulamaları kullanma

MAM ilkeleri yalnızca iş bağlamında uygulanır. Bu nedenle uygulama, bağlamın iş veya kişisel olmasına göre farklı davranış gösterebilir.

 Örneğin, kullanıcı iş verilerine erişirken kendisinden bir PIN istenir. **Outlook uygulamasında**, kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, kullanıcı iş hesabında yazdığında bir PIN istenir.  Microsoft **Word**, **PowerPoint** ve **Excel** için, kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde PIN istenir.

##  <a name="manage-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune, MAM ilkelerinin cihaz başına yalnızca bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir. Ancak her durumda, yalnızca MAM ilkelerini alan ilk kullanıcı, ilkeden etkilenir.
  * **Microsoft Word**, **Excel**, ve **PowerPoint**, ikinci bir kullanıcı hesabını engellemez, ancak ikinci kullanıcı, MAM ilkelerinden etkilenmez.  

  * **OneDrive** ve **Outlook uygulamaları** için yalnızca bir iş hesabı kullanabilirsiniz. Bu uygulamalar için birden çok iş hesabı ekleyemezsiniz. Ancak, bir kullanıcıyı kaldırabilir ve cihaza farklı bir kullanıcı ekleyebilirsiniz.

* Bir cihazda, MAM ilkeleri dağıtılmadan önce birden çok kullanıcı hesabı varsa, MAM ilkelerinin dağıtıldığı hedef hesap, Intune MAM ilkeleri tarafından yönetilir.


Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor—**Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de MAM ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, MAM ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap MAM ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y ile ilişkili kullanıcı hesabının MAM ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız gerekir.

### <a name="add-a-second-account"></a>İkinci hesap ekleme

iOS cihazı kullanıyorsanız, bu cihaza ikinci bir iş hesabı eklemeye çalıştığınızda bir engelleme iletisi görebilirsiniz. Hesaplar görüntülenir ve sonra kaldırmak istediğiniz hesabı seçebilirsiniz.

![Engelleme iletisi ve Evet ile Hayır seçenekleri bulunan iletişim kutusunun ekran görüntüsü](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>Sonraki adımlar
[Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO3-->


