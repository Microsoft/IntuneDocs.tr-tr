---
title: Android for Work cihazlara uygulama atama
titleSuffix: Intune on Azure
description: "Google Play for Work Store’dan Android for Work cihazlarına uygulama eşitlemek ve atamak için bu konuyu kullanın.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bbe5be4afead5d80f38e2ef56d12c0b26351dfd8
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Intune ile Android for Work cihazlara uygulama atama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android for Work cihazlara uygulama atama işlemi, standart Android cihazlara atamaktan farklı bir yolla yapılır. Android for Work için yüklediğiniz tüm uygulamalar Google Play for Work mağazasından gelir. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız.
Ardından uygulama, Intune portalının **Lisanslı uygulamalar** düğümünde görüntülenir. Buradan, uygulamanın atamasını, herhangi başka bir uygulamanın atamasıyla aynı şekilde yönetebilirsiniz.

Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız, bunları aşağıdaki gibi atayabilirsiniz:
- Google Play Store'daki özel bir alanda uygulama yayımlamanıza olanak tanıyan bir Google Developer hesabı için kaydolun.
- Uygulamaları Intune ile eşitleyin.

## <a name="before-you-start"></a>Başlamadan önce

Intune ve Android for Work’ü Intune konsolunun **Cihaz kaydı** iş yüküyle birlikte çalışacak şekilde yapılandırdığınızdan emin olun.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasından uygulama eşitleme

1. [Google Play for Work mağazasına](https://play.google.com/work) gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak atamak istediğiniz uygulamayı mağazada arayın.
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
6. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamayı görebildiğinizi onaylayın. Uygulama, Intune ile eşitlenmesi için otomatik olarak onaylanır.

## <a name="assign-an-android-for-work-app"></a>Android for Work uygulamasını atama

Mağazadan bir uygulamayı onayladıysanız ve **Mobil uygulamalar** iş yükünün **Lisanslı uygulamalar** düğümünde göremiyorsanız, aşağıdaki gibi bir anında eşitleme zorlayın:

1. Azure Portal’da oturum açın.
2. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
3. **Mobil uygulamalar** iş yükünde **Kurulum** > **Android for Work** öğesini seçin.
4. Android for Work dikey penceresinde **Şimdi Eşitle**’yi seçin.
5. Bu sayfa son eşitlemenin saatini ve durumunu da gösterir.

**Mobil uygulamalar** iş yükünün **Lisanslı uygulamalar** düğümünde görüntülendiğinde, uygulamayı, [diğer herhangi bir uygulamayı atadığınız gibi atayabilirsiniz](/intune-azure/manage-apps/deploy-apps). Uygulamayı yalnızca kullanıcı gruplarına atayabilirsiniz.

Uygulama atandıktan sonra, hedeflenen cihazlara yüklenir. Cihazın kullanıcısından yüklemeyi onaylaması istenmez.

## <a name="manage-android-for-work-app-permissions"></a>Android for Work uygulama izinlerini yönetme
Android for Work, uygulamaları Intune’a eşitlemeden ve kullanıcılarınıza atamadan önce, Google’ın yönetilen Play web konsolunda onaylamanızı gerektirir.  İş için Android bu uygulamaları sessizce ve otomatik olarak kullanıcıların cihazlarına göndermenize izin verdiğinden, uygulamanın izinlerini tüm kullanıcılarınız adına kabul etmeniz gerekir.  Son kullanıcılar yüklediklerinde herhangi bir uygulama izni görmeyeceğinden, bu izinleri okumanız ve anlamanız önemlidir.

Bir uygulama geliştiricisi güncelleştirilmiş izinler ile bir uygulamanın yeni bir sürümünü yayınladığında, önceki izinleri kabul etmiş olsanız bile bu izinler otomatik olarak kabul edilmez. Eski sürümünü çalıştıran cihazlar, uygulamayı kullanmaya devam edebilir. Ancak uygulama, yeni izinler onaylanana kadar yükseltilmez. Yüklü olmadığı cihazlarda, uygulama, yeni izinler onaylanana kadar yüklenmez.

### <a name="how-to-update-app-permissions"></a>Uygulama izinlerini güncelleştirme

Yeni izinleri denetlemek için yönetilen Google Play konsolunu düzenli aralıklarla ziyaret edin. Google Play'i onaylanmış bir uygulama için yeni izinler gerekli olduğunda, size veya başkalarına e-posta göndermesi için yapılandırabilirsiniz. Bir uygulamayı atar ve cihazlarda yüklü olmadığını görürseniz, aşağıdaki adımlarla yeni izinleri denetleyin:

1. http://play.google.com/work adresine gidin
2. Uygulamaları yayınlamak ve onaylamak için kullandığınız Google hesabıyla oturum açın.
3. Herhangi bir uygulamanın güncelleştirme gerektirip gerektirmediğini görmek için **Güncelleştirmeler** sekmesini ziyaret edin.  Listelenen tüm uygulamalar yeni izinler gerektirir ve uygulama, yeni izinler uygulanana kadar atanmaz.  

Alternatif olarak, Google Play'i uygulama izinlerini uygulama başına otomatik olarak yeniden onaylamak üzere yapılandırabilirsiniz. 



