---
title: Android iş profili cihazlarına uygulama atama
titlesuffix: Microsoft Intune
description: Yönetilen Google Play mağazasından Android iş profili cihazlarına uygulama eşitlemeyi ve atamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b65daa6e098954d88c502114fc7a33ad4cf5efcd
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37909295"
---
# <a name="assign-apps-to-android-work-profile-devices-with-intune"></a>Intune ile Android iş profili cihazlarına uygulama atama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android kurumsal, Android iş profili cihazları ve bilgi noktası cihazları için bir programdır. Android iş profili cihazları için Android kurumsal, kişisel uygulamaları ve verileri iş uygulama ve verilerinden ayıran bir özellik ve hizmet kümesidir. Android iş profili, kullanıcılar Android cihazlarını iş için kullandıklarında ek yönetim seçenekleri ve gizlilik sağlar. Intune, iş bilgileriyle kişisel bilgilerin ayrı olmasını sağlamak için Android iş profili cihazlarına uygulamalar ve ayarlar dağıtmanıza yardımcı olur. Android iş profili cihazları için yüklediğiniz tüm uygulamalar Yönetilen Google Play mağazasından gelir. Android iş profili cihazlarına uygulama atama işlemi, standart Android cihazlara uygulama atamaktan farklıdır. Mağazada oturum açar, istediğiniz uygulamalara göz atar ve bunları onaylarsınız. Daha sonra uygulama, Azure portalının **Lisanslı uygulamalar** düğümünde görünür ve uygulamanın atamasını diğer uygulamalarda olduğu gibi yaparsınız.

Ayrıca, kendi iş kolu (LOB) uygulamalarınızı oluşturduysanız, bunları aşağıdaki gibi atayabilirsiniz:
- Google Play Store'daki özel bir alanda uygulama yayımlamanıza olanak tanıyan bir Google Developer hesabı için kaydolun.
- Uygulamaları Intune ile eşitleyin.

## <a name="before-you-start"></a>Başlamadan önce

Intune ve Android iş profillerini Azure portalın **Cihaz kaydı** iş yüküyle birlikte çalışacak şekilde yapılandırdığınızdan emin olun. Daha fazla bilgi için bkz. [Android cihazları kaydetme](android-work-profile-enroll.md).

## <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Yönetilen Google Play mağazasından uygulama eşitleme

1. [Yönetilen Google Play mağazası](https://play.google.com/work)’na gidin. Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla oturum açın.
2. Intune kullanarak atamak istediğiniz uygulamayı mağazada arayın ve seçin.
3. Uygulamanın görüntülendiği sayfada **Onayla**’yı seçin.  
    Aşağıdaki örneklerde Microsoft Excel uygulaması seçilmiştir.

    ![Yönetilen Google Play mağazasında Onayla düğmesi](media/approve.png)
    
   Uygulamada bir pencere açılır ve çeşitli işlemler gerçekleştirmek için izin vermenizi ister. 

4. Uygulama izinlerini kabul edip devam etmek için **Onayla**’yı seçin.

    ![Uygulama izinleri için Onayla düğmesi](media/approve-app-permissions.png)

5. Yeni uygulama izin isteklerini işlemek için bir seçenek belirleyin ve daha sonra **Kaydet**’i seçin.

    ![Yeni uygulama izni isteklerini işleme seçenekleri](media/approve-app-settings.png)

    Uygulama onaylanır ve BT yönetici konsolunuzda görüntülenir. Ardından [Android iş profili uygulamasını Intune ile eşitleyebilirsiniz](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-a-managed-google-play-app-with-intune"></a>Yönetilen Google Play uygulamalarını Intune ile eşitleme

Mağazadan bir uygulamayı onayladıysanız ve **Mobil uygulamalar** iş yükünün **Lisanslı uygulamalar** düğümünde göremiyorsanız, aşağıdaki gibi bir anında eşitleme zorlayın:

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükü bölmesinde, **Kurulum** altında **Yönetilen Google Play**’i seçin.
5. **Yönetilen Google Play** bölmesinde **Yenile**’yi seçin.  
    Bu sayfa son eşitlemenin zamanını ve durumunu güncelleştirir.
6. **Mobil uygulamalar** iş yükü bölmesinde **Uygulamalar**’ı seçin.  
    Yeni eklenen Yönetilen Google Play uygulaması görüntülenir.

Uygulama, **Mobil uygulamalar** iş yükü bölmesinin **Uygulama lisansları** düğümünde göründüğünde, bunu [diğer herhangi bir uygulamayı atadığınız gibi atayabilirsiniz](/intune-azure/manage-apps/deploy-apps). Uygulamayı yalnızca kullanıcı gruplarına atayabilirsiniz.

Uygulama atandıktan sonra hedeflediğiniz cihazlara yüklenir. Cihazın kullanıcısından yüklemeyi onaylaması istenmez.

## <a name="manage-android-enterprise-app-permissions"></a>Android kurumsal uygulama izinlerini yönetme
Android kurumsal, uygulamaları Intune ile eşitlemeden ve kullanıcılarınıza atamadan önce, yönetilen Google Play web konsolunda onaylamanızı gerektirir. Android iş profili bu uygulamaları sessizce ve otomatik olarak kullanıcıların cihazlarına göndermenize izin verdiğinden, uygulama izinlerini tüm kullanıcılarınız adına kabul etmeniz gerekir. Kullanıcılar uygulamayı yüklediklerinde herhangi bir uygulama izni görmeyeceğinden, sizin bu izinleri anlamanız önemlidir.

Bir uygulama geliştiricisi bir uygulamanın yeni bir sürümüyle izinleri güncelleştirdiğinde, önceki izinleri kabul etmiş olsanız bile bu izinler otomatik olarak kabul edilmez. Önceki sürümü çalıştıran cihazlar, uygulamayı kullanmaya devam edebilir. Ancak uygulama, yeni izinler onaylanana kadar yükseltilmez. Yüklü olmadığı cihazlarda, uygulama, yeni izinler onaylanana kadar yüklenmez.

### <a name="update-app-permissions"></a>Uygulama izinlerini güncelleştirme

Yeni izinleri denetlemek için yönetilen Google Play konsolunu düzenli aralıklarla ziyaret edin. Google Play’i onaylanmış bir uygulama için yeni izinler gerekli olduğunda, size veya başkalarına e-posta göndermesi için yapılandırabilirsiniz. Bir uygulamayı atar ve cihazlarda yüklü olmadığını görürseniz, aşağıdaki adımları izleyerek yeni izinleri denetleyin:

1. [Google Play](http://play.google.com/work)’e gidin.
2. Uygulamaları yayınlamak ve onaylamak için kullandığınız Google hesabıyla oturum açın.
3. **Güncelleştirmeler** sekmesini seçin ve herhangi bir uygulamanın güncelleştirme gerektirip gerektirmediğine bakın.  
    Listelenen tüm uygulamalar yeni izinler gerektirir ve uygulama, yeni izinler uygulanana kadar atanmaz.

Alternatif olarak, Google Play’i uygulama izinlerini uygulama başına otomatik olarak yeniden onaylamak üzere yapılandırabilirsiniz. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Yönetilen Google Play mağazasından bir iş kolu uygulaması ile çalışma

1. Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Google Play Developer Console](https://play.google.com/apps/publish)’da oturum açın.  
    İlk kez oturum açıyorsanız, Google Geliştirici programının üyesi olmak için kaydolmanız ve bir ücret ödemeniz gerekir.
2. Konsolda **Yeni uygulama ekle**’yi seçin.
3. Uygulamanızı karşıya yüklemek ve hakkında bilgi sağlamak, Google Play mağazasında herhangi bir uygulama yayımlamak ile aynı şekilde yapılır. Ancak, **Bu uygulama yalnızca kuruluşum tarafından kullanılabilsin (<*kuruluş adı*>)** ayarını seçmeniz gerekir.

    ![Uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirme](media/restrict.png)

    Bu işlem, uygulamayı yalnızca kuruluşunuz için kullanılabilir hale getirir. Uygulama, genel Google Play mağazasında kullanılabilir olmayacaktır.

    Android uygulamalarını karşıya yükleme ve yayımlama hakkında daha fazla bilgi için bkz. [Google Developer Console Yardımı](https://support.google.com/googleplay/android-developer/answer/113469).
4. Uygulamanızı yayımladıktan sonra Intune ve Android kurumsal arasındaki bağlantıyı yapılandırmak için kullandığınız hesapla [Yönetilen Google Play mağazası](https://play.google.com/work)’nda oturum açın.
5. Mağazanın **Uygulamalar** düğümünde, yayımladığınız uygulamanın görüntülendiğini onaylayın.  
    Uygulama, Intune ile eşitlenmesi için otomatik olarak onaylanır.

## <a name="next-steps"></a>Sonraki adımlar

- [Gruplara uygulama ekleme](apps-deploy.md) 

