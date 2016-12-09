---
title: "Android for Work cihazlara uygulama dağıtma | Microsoft Intune"
description: "Google Play for Work Store’dan uygulama eşitlemek ve ardından Android for Work cihazlara dağıtmak için bu konuyu kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/6/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 35ee89248e42c67f48d4607f5d415896e35b90e9


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Intune ile Android for Work cihazlara uygulama dağıtma

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Android for Work cihazlara uygulama dağıtma işlemi, standart Android cihazlara dağıtmaktan farklı bir yolla yapılır. Android for Work için yüklediğiniz tüm uygulamalar Google Play for Work mağazasından gelir. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız.
Uygulama daha sonra Intune konsolunun **Toplu Satın Alınan Uygulamalar** düğümünde görünür. Buradan, uygulamanın dağıtımını, herhangi başka bir uygulamanın dağıtımıyla aynı şekilde yönetebilirsiniz.
Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız, onları dağıtabilirsiniz. Bunu yapmak için uygulamaları Google Play mağazasında özel bir alanda yayımlamanıza olanak tanıyan bir Google Geliştirici hesabına kaydolmanız ve bunları Intune ile eşitlemeniz gerekir.

## <a name="before-you-start"></a>Başlamadan önce

1. Intune ve Android for Work’ü Intune konsolunun **Yönetici** sekmesinde birlikte çalışacak şekilde yapılandırdığınızdan emin olun.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasından uygulama eşitleme


1. [Google Play for Work mağazasına](https://play.google.com/work) gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak dağıtmak istediğiniz uygulamayı mağazada arayın.
3. Seçtiğiniz uygulamanın sayfasında **Onayla**’yı seçin. Bu örnekte, Microsoft Excel uygulamasını seçtiniz.<br>
  ![Uygulama onaylama örneği](/intune/deploy-use/media/approve.png)
4. Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister. Devam etmek için **Onayla**’yı seçmeniz gerekir.<br>
  ![Uygulama izinlerini onaylama örneği](/intune/deploy-use/media/approve-app-permissions.png)
5. Kısa bir süre sonra, uygulamanın onaylandığını ve BT yönetim konsolunda kullanılabilir olduğunu belirten bir onay iletisi görürsünüz.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Google Play for Work mağazasında bir iş kolu uygulaması yayımlama ve ardından eşitleme

1. Google Play Geliştirici Konsolu’na gidin, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın. İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
3. Konsolda, **Yeni uygulama ekle**’yi seçin.
4. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, aşağıdaki gösterildiği gibi **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir.<br>
  ![Uygulamayı yalnızca kuruluşunuz tarafından kullanılabilir hale getirme seçeneği](/intune/deploy-use/media/restrict.png)<br>
Bu, uygulamanın yalnızca kuruluşunuz tarafından kullanılabilmesini ve genel Google Play mağazasında kullanılamamasını sağlar.
Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Geliştirici Konsolu Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
5. Uygulamanızı yayımladıktan sonra, [Google Play for Work mağazası](https://play.google.com/work)’na gidin. Intune ve Android for Work arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
6. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamayı görebildiğinizi onaylayın. Intune ile eşitlenmek üzere otomatik olarak onaylandığını göreceksiniz.

## <a name="deploy-an-android-for-work-app"></a>Bir Android for Work uygulaması dağıtma

Genellikle Intune, Google Play for Work mağazasıyla günde iki kez eşitlenir. Mağazada bir uygulamayı onayladıysanız ve henüz **Uygulamalar** çalışma alanının **Toplu Satın Alınan Uygulamalar** düğümünde göremiyorsanız, aşağıdaki gibi anında eşitlemeye zorlayabilirsiniz:

1. [Intune yönetim konsolunda](https://manage.microsoft.com), **Yönetici** > **Mobil Cihaz Yönetimi** > **Android for Work**’ü seçin.
2. **Android for Work Mobil Cihaz Yönetimi Kurulumu** sayfasında, **Şimdi Eşitle**’yi seçin.
3. Bu sayfa son eşitlemenin saatini ve durumunu da gösterir.

Uygulama **Uygulamalar** çalışma alanının **Toplu Satın Alınan Uygulamalar** düğümünde görüntülendiğinde, [uygulamayı diğer uygulamalarla aynı şekilde dağıtabilirsiniz](deploy-apps-in-microsoft-intune.md). Uygulamayı yalnızca kullanıcı gruplarına dağıtabilirsiniz. Şu anda yalnızca **Gerekli** ve **Kaldır** eylemlerini seçebilirsiniz. Ekim 2016'dan itibaren, yeni kiracılara **Kullanılabilir** dağıtım eylemini eklemeye başlayacağız.

Uygulama dağıtıldıktan sonra, hedeflenen cihazlara yüklenir. Cihazın kullanıcısından onay istenmez.



<!--HONumber=Dec16_HO2-->


