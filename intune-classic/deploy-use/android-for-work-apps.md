---
title: "Android for Work cihazlara uygulama dağıtma"
description: "Google Play for Work Store’dan uygulama eşitlemek ve ardından Android for Work cihazlara dağıtmak için bu konuyu kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: adc4a343e610a1a75f8a5bc51a1894f6fcf998bb
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2017
---
# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Intune ile Android for Work cihazlara uygulama dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Android for Work cihazlara uygulama dağıtma işlemi, standart Android cihazlara dağıtmaktan farklı bir yolla yapılır. Android for Work için yüklediğiniz tüm uygulamalar Google Play for Work mağazasından gelir. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız.
Uygulama daha sonra Intune konsolunun **Toplu Satın Alınan Uygulamalar** düğümünde görünür. Buradan, uygulamanın dağıtımını, herhangi başka bir uygulamanın dağıtımıyla aynı şekilde yönetebilirsiniz.

Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız onları aşağıdaki gibi dağıtabilirsiniz:
- Google Play Store'daki özel bir alanda uygulama yayımlamanıza olanak tanıyan bir Google Developer hesabı için kaydolun.
- Uygulamaları Intune ile eşitleyin.

## <a name="before-you-start"></a>Başlamadan önce

Intune ve Android for Work’ü Intune konsolunun **Yönetici** sekmesinde birlikte çalışacak şekilde yapılandırdığınızdan emin olun.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasından uygulama eşitleme


1. [Google Play for Work mağazasına](https://play.google.com/work) gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak dağıtmak istediğiniz uygulamayı mağazada arayın.
3. Seçtiğiniz uygulamanın sayfasında **Onayla**’yı seçin. Bu örnekte, Microsoft Excel uygulamasını seçtiniz.<br>
  ![Uygulama onaylama örneği](media/approve.png)
4. Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister. Devam etmek için **Onayla**'yı seçin.<br>
  ![Uygulama izinlerini onaylama örneği](media/approve-app-permissions.png)
5. Uygulama onaylanır ve BT yönetim konsolunda görüntülenir.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasından bir iş kolu uygulaması yayımlama ve eşitleme

1. Google Play Geliştirici Konsolu’na gidin, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın. İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
3. Konsolda, **Yeni uygulama ekle**’yi seçin.
4. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir:<br>
  ![Uygulamayı yalnızca kuruluşunuz tarafından kullanılabilir hale getirme seçeneği](media/restrict.png)<br>
Bu işlem, uygulamanın yalnızca kuruluşunuz tarafından kullanılabilmesini, genel Google Play mağazasında bulunmamasını sağlar.
Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Geliştirici Konsolu Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
5. Uygulamanızı yayımladıktan sonra, [Google Play for Work mağazası](https://play.google.com/work)’na gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
6. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamayı görebildiğinizi onaylayın. Intune ile eşitlenmesi için otomatik olarak onaylanır.

## <a name="deploy-an-android-for-work-app"></a>Bir Android for Work uygulaması dağıtma

Mağazada bir uygulamayı onayladıysanız ve **Uygulamalar** çalışma alanının **Toplu Satın Alınan Uygulamalar** düğümünde göremiyorsanız aşağıdaki gibi anında eşitlemeye zorlayın:

1. [Intune yönetim konsolunda](https://manage.microsoft.com), **Yönetici** > **Mobil Cihaz Yönetimi** > **Android for Work**’ü seçin.
2. **Android for Work Mobil Cihaz Yönetimi Kurulumu** sayfasında, **Şimdi Eşitle**’yi seçin.
3. Bu sayfa son eşitlemenin saatini ve durumunu da gösterir.

Uygulama **Uygulamalar** çalışma alanının **Toplu Satın Alınan Uygulamalar** düğümünde görüntülendiğinde, [uygulamayı diğer uygulamalarla aynı şekilde dağıtabilirsiniz](deploy-apps-in-microsoft-intune.md). Uygulamayı yalnızca kullanıcı gruplarına dağıtabilirsiniz. Şu anda yalnızca **Gerekli** ve **Kaldır** eylemlerini seçebilirsiniz.

Bir uygulamayı **Kullanılabilir** olarak dağıtmak, yeni gruplandırma ve hedefleme deneyiminde geçerlidir. Yeni sağlanan Intune hizmet hesapları, bu özelliği yayınlandığı andan itibaren kullanabilir. Mevcut Intune müşterileri, kiracılarının Intune Azure portalına geçişi yapıldıktan sonra bu özelliği kullanabilir. Mevcut müşteriler, kiracılarının geçişi yapılana kadar planlama ve bu özelliği sınama amacıyla bir Intune deneme hesabı oluşturabilir.

Uygulama dağıtıldıktan sonra, hedeflenen cihazlara yüklenir. Cihazın kullanıcısından onay istenmez.

## <a name="manage-app-permissions"></a>Uygulama izinlerini yönetme
İş için Android, uygulamaları Intune’a eşitlemeden ve kullanıcılarınıza dağıtmadan önce, Google’ın yönetilen Play web konsolunda onaylamanızı gerektirir.  İş için Android bu uygulamaları sessizce ve otomatik olarak kullanıcıların cihazlarına göndermenize izin verdiğinden, uygulamanın izinlerini tüm kullanıcılarınız adına kabul etmeniz gerekir.  Son kullanıcılar yüklediklerinde herhangi bir uygulama izni görmeyeceğinden, bu izinleri okumanız ve anlamanız önemlidir.

Bir uygulama geliştiricisi güncelleştirilmiş izinler ile bir uygulamanın yeni bir sürümünü yayınladığında, önceki izinleri kabul etmiş olsanız bile bu izinler otomatik olarak kabul edilmez. Uygulamanın eski sürümünü çalıştıran cihazlar bunu kullanmaya devam edebilir ancak yeni izinler onaylanana kadar uygulama yükseltilmez. Uygulamanın yüklü olmadığı cihazlarda, yeni izinler onaylanana kadar uygulama yüklenemez.

### <a name="how-to-update-app-permissions"></a>Uygulama izinlerini güncelleştirme

Yeni izinleri denetlemek için yönetilen Google Play konsolunu düzenli aralıklarla ziyaret edin. Google Play'i onaylanmış bir uygulama için yeni izinler gerekli olduğunda, size veya başkalarına e-posta göndermesi için yapılandırabilirsiniz. Bir uygulamayı atar ve cihazlarda yüklü olmadığını görürseniz, aşağıdaki adımlarla yeni izinleri denetleyin:

1. http://play.google.com/work adresine gidin
2. Uygulamaları yayınlamak ve onaylamak için kullandığınız Google hesabıyla oturum açın.
3. Herhangi bir uygulamanın güncelleştirme gerektirip gerektirmediğini görmek için **Güncelleştirmeler** sekmesini ziyaret edin.  Listelenen tüm uygulamalar yeni izinler gerektirir ve bunlar uygulanana kadar atanmaz.  

Alternatif olarak, Google Play'i uygulama izinlerini uygulama başına otomatik olarak yeniden onaylamak üzere yapılandırabilirsiniz. 
