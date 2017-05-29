---
title: "Android for Work cihazlarına uygulama atama | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Google Play for Work Store’dan uygulama eşitlemek ve ardından Android for Work cihazlara atamak için bu konuyu kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 49e86ab665d9022739c0330092734ba897ea3b02
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Intune ile Android for Work cihazlara uygulama atama

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Android for Work cihazlara uygulama atama işlemi, standart Android cihazlara atamaktan farklı bir yolla yapılır. Android for Work için yüklediğiniz tüm uygulamalar Google Play for Work mağazasından gelir. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız.
Ardından uygulama, Intune portalının **Lisanslı uygulamalar** düğümünde görüntülenir. Buradan, uygulamanın atamasını, herhangi başka bir uygulamanın atamasıyla aynı şekilde yönetebilirsiniz.

Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız, onları da atayabilirsiniz. Bunu yapmak için uygulamaları Google Play mağazasında özel bir alanda yayımlamanıza olanak tanıyan bir Google Geliştirici hesabına kaydolmanız ve bunları Intune ile eşitlemeniz gerekir.

## <a name="before-you-start"></a>Başlamadan önce

Intune ve Android for Work’ü Intune konsolunun **Cihaz kaydı** iş yüküyle birlikte çalışacak şekilde yapılandırdığınızdan emin olun.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasından uygulama eşitleme


1. [Google Play for Work mağazasına](https://play.google.com/work) gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak atamak istediğiniz uygulamayı mağazada arayın.
3. Seçtiğiniz uygulamanın sayfasında **Onayla**’yı seçin. Bu örnekte, Microsoft Excel uygulamasını seçtiniz.<br>
  ![Uygulama onaylama örneği](media/approve.png)
4. Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister. Devam etmek için **Onayla**’yı seçmeniz gerekir.<br>
  ![Uygulama izinlerini onaylama örneği](media/approve-app-permissions.png)
5. Kısa bir süre sonra, uygulamanın onaylandığını ve BT yönetim konsolunda kullanılabilir olduğunu belirten bir onay iletisi görürsünüz.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasında bir iş kolu uygulaması yayımlama ve ardından eşitleme

1. Google Play Geliştirici Konsolu’na gidin, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın. İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
3. Konsolda, **Yeni uygulama ekle**’yi seçin.
4. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, aşağıdaki gösterildiği gibi **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir.<br>
  ![Uygulamayı yalnızca kuruluşunuz tarafından kullanılabilir hale getirme seçeneği](media/restrict.png)<br>
Bu, uygulamanın yalnızca kuruluşunuz tarafından kullanılabilmesini ve genel Google Play mağazasında kullanılamamasını sağlar.
Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Geliştirici Konsolu Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
5. Uygulamanızı yayımladıktan sonra, [Google Play for Work mağazası](https://play.google.com/work)’na gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
6. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamayı görebildiğinizi onaylayın. Intune ile eşitlenmek üzere otomatik olarak onaylandığını göreceksiniz.

## <a name="assign-an-android-for-work-app"></a>Android for Work uygulamasını atama

Mağazada bir uygulamayı onayladıysanız ve henüz **Mobil uygulamalar** iş yükünün **Lisanslı uygulamalar** düğümünde göremiyorsanız, aşağıdaki gibi anında eşitlemeye zorlayabilirsiniz:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Kurulum** > **Android for Work** öğesini seçin.
5. Android for Work dikey penceresinde **Şimdi Eşitle**’yi seçin.
6. Bu sayfa son eşitlemenin saatini ve durumunu da gösterir.

Uygulama **Mobil uygulamalar** iş yükünün **Lisanslı uygulamalar** düğümünde görüntülendiğinde, [uygulamayı aynı diğer herhangi bir uygulamayı atadığınız gibi atayabilirsiniz](/intune-azure/manage-apps/deploy-apps). Uygulamayı yalnızca kullanıcı gruplarına atayabilirsiniz.

Uygulama atandıktan sonra, hedeflenen cihazlara yüklenir. Cihazın kullanıcısından yüklemeyi onaylaması istenmez.

## <a name="manage-app-permissions"></a>Uygulama izinlerini yönetme
Android for Work, uygulamaları Intune’a eşitlemeden ve kullanıcılarınıza atamadan önce, Google’ın yönetilen Play web konsolunda onaylamanızı gerektirir.  İş için Android bu uygulamaları sessizce ve otomatik olarak kullanıcıların cihazlarına göndermenize izin verdiğinden, uygulamanın izinlerini tüm kullanıcılarınız adına kabul etmeniz gerekir.  Son kullanıcılar uygulama yüklediklerinde herhangi bir uygulama izni görmeyeceğinden, bu izinleri okumanız ve anlamanız önemlidir.

Bir uygulama geliştiricisi güncelleştirilmiş izinler ile bir uygulamanın yeni bir sürümünü yayınladığında, önceki izinleri kabul etmiş olsanız bile bu izinler otomatik olarak kabul edilmez. Uygulamanın eski sürümünü çalıştıran cihazlar bunu kullanmaya devam edebilir ancak yeni izinler onaylanana kadar uygulama yükseltilmez. Uygulamanın yüklü olmadığı cihazlarda, yeni izinler onaylanana kadar uygulama yüklenemez.

### <a name="how-to-update-app-permissions"></a>Uygulama izinlerini güncelleştirme

Yeni izinleri denetlemek için yönetilen Google Play konsolunu düzenli aralıklarla ziyaret etmeniz gerekir. Bir uygulamayı atar ve cihazlarda yüklü olmadığını görürseniz, aşağıdaki adımlarla yeni izinleri denetleyin:

1. http://play.google.com/work adresine gidin
2. Uygulamaları yayınlamak ve onaylamak için kullandığınız Google hesabıyla oturum açın.
3. Herhangi bir uygulamanın güncelleştirme gerektirip gerektirmediğini görmek için **Güncelleştirmeler** sekmesini ziyaret edin.  Listelenen tüm uygulamalar yeni izinler gerektirir ve bunlar uygulanana kadar atanmaz.  

