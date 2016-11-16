---
title: "MAM ilkeleri içeren iOS uygulamaları | Microsoft Intune"
description: "Bu konu başlığı altında, iOS uygulamanız mobil uygulama yönetimi ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# iOS uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler
 Bu konuda, MAM ilkeleri içeren uygulamalardaki kullanıcı deneyimi açıklanmıştır. Mobil uygulama yönetimi (MAM) ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: İş hesabınızı kullanarak uygulamalara veya şirketinizin OneDrive iş konumunda depolanan dosyalara erişmek gibi.
##  Uygulamalara erişme

Cihaz **Intune'a kayıtlı değilse**, son kullanıcı uygulamayı ilk kez kullandığında uygulamayı yeniden başlatması istenir.  Uygulamaya MAM ilkelerinin uygulanabilmesi için yeniden başlatma gereklidir. Aşağıdaki ekran görüntüsü bunu Skype uygulamasını kullanarak göstermektedir:


![PIN istemi gösteren iOS cihazının ekran görüntüsü](../media/appmanagement/iOS_AppPINPrompt.png)

**Yönetilmek üzere Intune’da kayıtlı cihazlarda**, son kullanıcı uygulamasının artık yönetildiğini belirten bir ileti görürsünüz:

![PIN istemiyle şirketiniz tarafından yönetiliyor iletisini gösteren iOS cihazının ekran görüntüsü](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Birden çok kimlik destekli uygulamaları kullanma

MAM ilkeleri uygulama kullanılırken yalnızca iş bağlamında uygulanır; bu nedenle bağlama (iş veya kişisel) bağlı olarak farklı uygulama davranışları görebilirsiniz.  

Intune, birden çok kimliği destekleyen uygulamalarda MAM ilkelerini yalnızca son kullanıcı uygulamayı iş bağlamında kullandığında uygular.  Örneğin, son kullanıcı iş verilerine erişirken bir PIN istenir.  **Outlook uygulamasında**, son kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, bu durum son kullanıcı iş hesabını yazdığında gerçekleşir.  Microsoft **Word**, **PowerPoint* ve **Excel** için bu, son kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde gerçekleşir.
##  Cihazda kullanıcı hesaplarını yönetme

Intune yalnızca, MAM ilkelerinin cihaz başına yalnızca bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir veya engellenmeyebilir. Ancak her durumda, yalnızca MAM ilkelerini alan ilk kullanıcı, ilkeden etkilenir.
  * **Microsoft Word**, **Excel**, ve **PowerPoint**, ikinci bir kullanıcı hesabını engellemez, ancak ikinci kullanıcı, MAM ilkelerinden etkilenmez.  

  * **OneDrive ve Outlook uygulamaları** için, yalnızca bir iş hesabı kullanabilirsiniz.  Birden çok iş hesabının eklenmesi bu uygulamalarda engellenmiştir.  Ancak, bir kullanıcıyı kaldırabilir ve cihaza farklı bir kullanıcı ekleyebilirsiniz.

* Bir cihazda, MAM ilkeleri dağıtılmadan önce birden çok kullanıcı hesabı varsa, MAM ilkelerinin dağıtıldığı hedef hesap, Intune MAM ilkeleri tarafından yönetilir.


Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor - **Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de MAM ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, MAM ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap MAM ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y ile ilişkili kullanıcı hesabının MAM ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız gerekir.
### İkinci hesap ekleme

iOS cihazı kullanıyorsanız, aynı cihaza ikinci bir iş hesabı eklemeye çalıştığınızda bir engelleme iletisi görebilirsiniz.  Hesaplar görüntülenir ve kaldırmak istediğiniz hesabı seçebilirsiniz.

![Engelleme iletisi ve Evet ile Hayır seçenekleri bulunan iletişim kutusunun ekran görüntüsü](../media/AppManagement/iOS_SwitchUser.PNG)
## Sonraki adımlar
[Android uygulamanız MAM ilkeleri tarafından yönetildiğinde beklemeniz gerekenler](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


