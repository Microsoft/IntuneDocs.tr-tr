---
title: "Uygulama koruma ilkeleri içeren iOS uygulamaları"
titlesuffix: Azure portal
description: "Bu konu başlığı altında, iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde neler bekleyebileceğiniz açıklanır.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9ca6341d57eb57ec97e487c516c0919653f327e3
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>iOS uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konuda, uygulama koruma ilkeleri içeren uygulamalardaki kullanıcı deneyimi açıklanmıştır. Uygulama koruma ilkeleri yalnızca uygulamalar iş bağlamında kullanıldığında uygulanır: İş hesabınızı kullanarak uygulamalara veya şirketinizin OneDrive İş konumunda depolanan dosyalara erişmek gibi.
##  <a name="accessing-apps"></a>Uygulamalara erişme

Cihaz **Intune'a kayıtlı değilse**, son kullanıcı uygulamayı ilk kez kullandığında uygulamayı yeniden başlatması istenir.  Uygulamaya uygulama koruma ilkelerinin uygulanabilmesi için yeniden başlatma gereklidir. Aşağıdaki ekran görüntüsü bunu Skype uygulamasını kullanarak göstermektedir:


![PIN istemi gösteren iOS cihazının ekran görüntüsü](./media/ios-pin-prompt.png)

**Yönetilmek üzere Intune’da kayıtlı cihazlarda**, son kullanıcı uygulamasının artık yönetildiğini belirten bir ileti görürsünüz:

![PIN istemiyle şirketiniz tarafından yönetiliyor iletisini gösteren iOS cihazının ekran görüntüsü](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Birden çok kimlik destekli uygulamaları kullanma

Uygulama koruma ilkeleri uygulama kullanılırken yalnızca iş bağlamında uygulanır; bu nedenle bağlama (iş veya kişisel) bağlı olarak farklı uygulama davranışları görebilirsiniz.  

Intune, birden çok kimliği destekleyen uygulamalarda uygulama koruma ilkelerini yalnızca son kullanıcı uygulamayı iş bağlamında kullandığında uygular.  Örneğin, son kullanıcı iş verilerine erişirken bir PIN istenir.  **Outlook uygulamasında**, son kullanıcı uygulamayı açarken bir PIN istenir. **OneDrive uygulamasında**, bu durum son kullanıcı iş hesabını yazdığında gerçekleşir.  Microsoft **Word**, **PowerPoint* ve **Excel** için bu, son kullanıcı şirketin OneDrive İş konumunda depolanan belgelere eriştiğinde gerçekleşir.
##  <a name="managing-user-accounts-on-the-device"></a>Cihazda kullanıcı hesaplarını yönetme

Intune yalnızca, uygulama koruma ilkelerinin cihaz başına tek bir kullanıcı hesabına dağıtılmasını destekler.

* Kullanmakta olduğunuz uygulamaya bağlı olarak, ikinci kullanıcı cihazda engellenebilir veya engellenmeyebilir. Ancak her durumda, yalnızca uygulama koruma ilkelerini alan ilk kullanıcı, ilkeden etkilenir.
  * **Microsoft Word**, **Excel** ve **PowerPoint**, ikinci bir kullanıcı hesabını engellemez ama ikinci kullanıcı uygulama koruma ilkelerinden etkilenmez.  

  * **OneDrive ve Outlook uygulamaları** için, yalnızca bir iş hesabı kullanabilirsiniz.  Birden çok iş hesabının eklenmesi bu uygulamalarda engellenmiştir.  Ancak, bir kullanıcıyı kaldırabilir ve cihaza farklı bir kullanıcı ekleyebilirsiniz.

* Bir cihazda, uygulama koruma ilkeleri dağıtılmadan önce birden çok kullanıcı hesabı varsa, uygulama koruma ilkelerinin ilk dağıtıldığı hedef hesap, Intune uygulama koruma ilkeleri tarafından yönetilir.


Birden çok kullanıcı hesabının nasıl ele alındığını daha iyi anlamak için aşağıdaki örnek senaryoyu okuyun.

Kullanıcı A, iki şirkette çalışıyor - **Şirket X** ve **Şirket Y**. Kullanıcı A’nın, her şirket için bir iş hesabı var ve ikisi de uygulama koruma ilkelerini dağıtmak için Intune kullanıyor. **Şirket X**, uygulama koruma ilkelerini **Şirket Y**’den **önce** dağıtıyor. **Şirket X** ile ilişkili hesap uygulama koruma ilkesini alır, ancak Şirket Y ile ilişkili hesap almaz. Şirket Y ile ilişkili kullanıcı hesabının uygulama koruma ilkeleri tarafından yönetilmesini istiyorsanız, Şirket X ile ilişkili kullanıcı hesabını kaldırmanız gerekir.
### <a name="adding-a-second-account"></a>İkinci hesap ekleme

iOS cihazı kullanıyorsanız, aynı cihaza ikinci bir iş hesabı eklemeye çalıştığınızda bir engelleme iletisi görebilirsiniz.  Hesaplar görüntülenir ve kaldırmak istediğiniz hesabı seçebilirsiniz.

![Engelleme iletisi ve Evet ile Hayır seçenekleri bulunan iletişim kutusunun ekran görüntüsü](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Sonraki adımlar
[Android uygulamanız uygulama koruma ilkeleriyle yönetildiğinde beklemeniz gerekenler](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile uygulama koruma ilkelerini oluşturma ve dağıtma](app-protection-policies.md)
